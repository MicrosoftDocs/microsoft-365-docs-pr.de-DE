---
title: Bereitstellen von Microsoft Defender für Endpunkt unter Linux mit Ansible
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux mithilfe von Ansible bereitgestellt wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, bereitstellen, Deinstallation, entinstallation, ansible, linux, redhat, ubuntu, git, sles, suse, centos
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
ms.openlocfilehash: 13bcbc74fcb9c540c45a6eec7e7e506b6943986a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841792"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Bereitstellen von Microsoft Defender für Endpunkt unter Linux mit Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Sie Defender für Endpunkt unter Linux mithilfe von Ansible bereitstellen. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Herunterladen des Onboardingpakets](#download-the-onboarding-package)
- [Erstellen von Ansible YAML-Dateien](#create-ansible-yaml-files)
- [Bereitstellung](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie [auf der Hauptseite von Defender für Endpunkt unter Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

Darüber hinaus müssen Sie für die Ansible-Bereitstellung mit Ansible-Verwaltungsaufgaben vertraut sein, Ansible konfiguriert haben und wissen, wie Playbooks und Aufgaben bereitgestellt werden. Ansible hat viele Möglichkeiten, dieselbe Aufgabe auszuführen. Bei diesen Anweisungen wird davon ausgegangen, dass unterstützte Ansible-Module verfügbar sind, z. *B. apt* und *die Archivierung* aufheben, um die Bereitstellung des Pakets zu unterstützen. Ihre Organisation kann einen anderen Workflow verwenden. Weitere Informationen finden Sie in der [Ansible-Dokumentation.](https://docs.ansible.com/)

- Ansible muss auf mindestens einem Computer installiert sein (Ansible ruft dies als Steuerknoten auf).
- SSH muss für ein Administratorkonto zwischen dem Steuerknoten und allen verwalteten Knoten konfiguriert werden (Geräte, auf denen Defender für Endpunkt installiert ist), und es wird empfohlen, mit der Authentifizierung mit öffentlichem Schlüssel konfiguriert zu werden.
- Die folgende Software muss auf allen verwalteten Knoten installiert sein:
  - Curl
  - python-apt

- Alle verwalteten Knoten müssen in der oder der relevanten Datei im folgenden Format aufgeführt `/etc/ansible/hosts` werden:

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

Laden Sie das Onboardingpaket von Microsoft Defender Security Center herunter:

1. Wechseln Sie in Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding.**
2. Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdownmenü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.
3. Wählen Sie **"Onboardingpaket herunterladen"** aus. Speichern Sie die Datei als WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. Überprüfen Sie an einer Eingabeaufforderung, ob Die Datei vorhanden ist. Extrahieren Sie den Inhalt des Archivs:

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

## <a name="create-ansible-yaml-files"></a>Erstellen von Ansible YAML-Dateien

Erstellen Sie eine Teilaufgabe oder Rollendateien, die zu einem Playbook oder einer Aufgabe beitragen.

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

- Fügen Sie das Repository und den Schlüssel für Defender für Endpunkt `add_apt_repo.yml` hinzu:

    Defender für Endpunkt unter Linux kann von einem der folgenden Kanäle bereitgestellt werden (unten als *[Kanal]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Software-Repository.

    Die Wahl des Kanals bestimmt den Typ und die Häufigkeit von Updates, die auf Ihrem Gerät angeboten werden. Geräte in *Insider-Fast* sind die ersten Geräte, die Updates und neue Features erhalten, gefolgt von *insider-slow* und schließlich von *prod*.

    Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insiderschnell* oder langsam verwendet *werden.*

    > [!WARNING]
    > Um den Kanal nach der Erstinstallation zu wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät erneut für die Verwendung des neuen Kanals, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.

    Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen.

    > [!NOTE]
    > Ersetzen Sie *[distro]* bei Oracle Linux durch "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
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

Führen Sie nun die Aufgabendateien unter `/etc/ansible/playbooks/` oder im relevanten Verzeichnis aus.

- Installation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischadsoftwaredefinitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.

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

## <a name="log-installation-issues"></a>Protokollieren von Installationsproblemen

Weitere Informationen zum Auffinden des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter ["Protokollinstallationsprobleme".](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Betriebssystemupgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zuerst Defender für Endpunkt unter Linux deinstallieren, das Upgrade installieren und defender für Endpunkt auf Linux auf Ihrem Gerät neu konfigurieren.

## <a name="references"></a>Informationsquellen

- [Hinzufügen oder Entfernen von YUM-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Verwalten von Paketen mit dem dnf-Paket-Manager](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Hinzufügen und Entfernen von APT-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Verwalten von apt-packages](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Siehe auch
- [Untersuchen von Problemen mit der Agent-Integrität](health-status.md)
