---
title: Bereitstellen von Microsoft Defender für Endpoint unter Linux mit Ansible
ms.reviewer: ''
description: Beschreibt die Bereitstellung von Microsoft Defender for Endpoint unter Linux mithilfe von Ansible.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, deinstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572729"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Bereitstellen von Microsoft Defender für Endpoint unter Linux mit Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Melden Sie sich für eine kostenlose Testversion an.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Defender for Endpoint unter Linux mithilfe von Ansible bereitgestellt wird. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Laden Sie das Onboarding-Paket herunter](#download-the-onboarding-package)
- [Erstellen von Ansible YAML-Dateien](#create-ansible-yaml-files)
- [Bereitstellung](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie auf [der Hauptseite Defender for Endpoint unter Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

Darüber hinaus müssen Sie für die Ansible-Bereitstellung mit Ansible-Verwaltungsaufgaben vertraut sein, Ansible konfigurieren und wissen, wie Playbooks und Aufgaben bereitgestellt werden. Ansible hat viele Möglichkeiten, die gleiche Aufgabe abzuschließen. Diese Anweisungen setzen die Verfügbarkeit unterstützter Ansible-Module voraus, z. B. *apt* und *unarchive,* um die Bereitstellung des Pakets zu unterstützen. Ihre Organisation verwendet möglicherweise einen anderen Workflow. Weitere Informationen finden Sie in der [Ansible-Dokumentation.](https://docs.ansible.com/)

- Ansible muss auf mindestens einem Computer installiert werden (Ansible nennt dies den Steuerknoten).
- SSH muss für ein Administratorkonto zwischen dem Steuerknoten und allen verwalteten Knoten (Geräte, auf denen Defender for Endpoint installiert ist) konfiguriert werden, und es wird empfohlen, mit der Authentifizierung öffentlicher Schlüssel konfiguriert zu werden.
- Die folgende Software muss auf allen verwalteten Knoten installiert sein:
  - Curl
  - python-apt

- Alle verwalteten Knoten müssen im folgenden Format in der oder relevanten Datei aufgeführt `/etc/ansible/hosts` sein:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping-Test:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Laden Sie das Onboarding-Paket herunter

Laden Sie das Onboarding-Paket von Microsoft Defender Security Center herunter:

1. Wechseln Sie Microsoft Defender Security Center zu **Einstellungen > Device Management > Onboarding**.
2. Wählen Sie im ersten Dropdown-Menü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdown-Menü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.
3. Wählen Sie **Onboarding-Paket herunterladen** aus . Speichern Sie die Datei als WindowsDefenderATPOnboardingPackage.zip.

    ![Microsoft Defender Security Center Screenshot](images/atp-portal-onboarding-linux-2.png)

4. Überprüfen Sie in einer Eingabeaufforderung, ob die Datei über sie verfügt. Extrahieren Sie den Inhalt des Archivs:

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

Erstellen Sie eine Teilaufgabe oder Rollendateien, die zu einem Spielbuch oder einer Aufgabe beitragen.

- Erstellen Sie die Onboarding-Aufgabe: `onboarding_setup.yml`

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

- Fügen Sie das Defender for Endpoint-Repository und den Schlüssel `add_apt_repo.yml` hinzu:

    Defender for Endpoint unter Linux kann von einem der folgenden Kanäle bereitgestellt werden (unten als *[Kanal]* bezeichnet): *Insider-schnell*, *insiders-slow*, oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Software-Repository.

    Die Wahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die Ihrem Gerät angeboten werden. Geräte in *Insider-schnell* sind die ersten, die Updates und neue Funktionen erhalten, gefolgt von *Insider-langsam* und schließlich von *prod*.

    Um eine Vorschau neuer Funktionen anzuzeigen und frühzeitiges Feedback zu geben, wird empfohlen, dass Sie einige Geräte in Ihrem Unternehmen so konfigurieren, dass sie entweder *Insider-schnell* oder *Insider-slow* verwenden.

    > [!WARNING]
    > Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.

    Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen.

    > [!NOTE]
    > Im Falle von Oracle Linux, ersetzen Sie *[distro]* durch "rhel".

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

- Erstellen Sie die Ansible-Installation und Deinstallation von YAML-Dateien.

    - Verwenden Sie für apt-basierte Distributionen die folgende YAML-Datei:

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

    - Verwenden Sie für dnf-basierte Distributionen die folgende YAML-Datei:

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

Führen Sie nun die Aufgabendateien unter oder im `/etc/ansible/playbooks/` relevanten Verzeichnis aus.

- Installation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischadsoftware-Definitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.

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

Weitere Informationen zum Auffinden des automatisch generierten Protokolls, das vom Installationsprogramm erstellt wird, wenn ein Fehler auftritt, finden Sie unter Probleme bei der [Protokollinstallation.](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Betriebssystem-Upgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zuerst Defender for Endpoint unter Linux deinstallieren, das Upgrade installieren und Defender for Endpoint unter Linux auf Ihrem Gerät neu konfigurieren.

## <a name="references"></a>Informationsquellen

- [Hinzufügen oder Entfernen von YUM-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Verwalten von Paketen mit dem dnf-Paketmanager](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Hinzufügen und Entfernen von APT-Repositorys](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Verwalten von apt-Paketen](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Siehe auch
- [Untersuchen von Problemen mit der Agent-Integrität](health-status.md)
