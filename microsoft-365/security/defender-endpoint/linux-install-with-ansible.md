---
title: Bereitstellen von Microsoft Defender for Endpoint unter Linux mit Ansible
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender for Endpoint unter Linux mithilfe von Ansible bereitgestellt wird.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 697fcddad595c6883fe1e1f7258ca6154c48b94d
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903904"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Bereitstellen von Microsoft Defender for Endpoint unter Linux mit Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Sie Defender for Endpoint für Linux mithilfe von Ansible bereitstellen. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Herunterladen des Onboardingpakets](#download-the-onboarding-package)
- [Erstellen von ansiblen YAML-Dateien](#create-ansible-yaml-files)
- [Bereitstellung](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie auf der Hauptseite [von Defender for Endpoint für Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

Darüber hinaus müssen Sie für die Ansible-Bereitstellung mit ansiblen Verwaltungsaufgaben vertraut sein, ansible konfigurieren und wissen, wie Sie Playbooks und Aufgaben bereitstellen. Ansible hat viele Möglichkeiten, dieselbe Aufgabe auszuführen. Diese Anweisungen setzen voraus, dass unterstützte Ansible-Module verfügbar sind, z. B. *apt* und *unarchive,* um das Paket bereitstellen zu können. Ihre Organisation kann einen anderen Workflow verwenden. Ausführliche Informationen finden Sie in [der Ansible-Dokumentation.](https://docs.ansible.com/)

- Ansible muss auf mindestens einem Computer installiert werden (wir nennen ihn den primären Computer).
- SSH muss für ein Administratorkonto zwischen dem primären Computer und allen Clients konfiguriert sein, und es wird empfohlen, die Authentifizierung mit öffentlichen Schlüsseln zu verwenden.
- Die folgende Software muss auf allen Clients installiert sein:
  - locken
  - python-apt

- Alle Hosts müssen in der oder den relevanten Dateien im folgenden `/etc/ansible/hosts` Format aufgeführt werden:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Pingtest:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Herunterladen des Onboardingpakets

Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:

1. Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.
2. Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdownmenü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.
3. Wählen **Sie Onboardingpaket herunterladen aus.** Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen. Extrahieren sie den Inhalt des Archivs:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Erstellen von ansiblen YAML-Dateien

Erstellen Sie eine Unteraufgabe oder Rollendateien, die zu einem Playbook oder einer Aufgabe beitragen.

- Erstellen Sie die `onboarding_setup.yml` Onboardingaufgabe:

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Fügen Sie das Defender for Endpoint-Repository und den Schlüssel hinzu.

    Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository.

    Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden. Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.

    Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*

    > [!WARNING]
    > Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.

    Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen.

    > [!NOTE]
    > Ersetzen Sie bei Oracle Linux *[distro] durch* "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Erstellen Sie die Ansible-Installation und deinstallieren Sie YAML-Dateien.

    - Verwenden Sie für apt-basierte Verteilungen die folgende YAML-Datei:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - Verwenden Sie für dnf-basierte Verteilungen die folgende YAML-Datei:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Bereitstellung)

Führen Sie nun die Aufgabendateien unter `/etc/ansible/playbooks/` oder relevantem Verzeichnis aus.

- Installation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.

- Validierung/Konfiguration:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Deinstallation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Probleme bei der Protokollinstallation

Weitere [Informationen zum](linux-resources.md#log-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollinstallationsprobleme.

## <a name="operating-system-upgrades"></a>Betriebssystemupgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.

## <a name="references"></a>Informationsquellen

- [Hinzufügen oder Entfernen von YUM-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Verwalten von Paketen mit dem dnf-Paket-Manager](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Hinzufügen und Entfernen von APT-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Verwalten von apt-packages](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
