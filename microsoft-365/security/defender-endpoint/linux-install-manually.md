---
title: Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux manuell über die Befehlszeile bereitgestellt wird.
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
ms.openlocfilehash: 4c4ed845a31f044e17c97e0b43adfc86dd3f68ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454805"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Sie Microsoft Defender für Endpunkt manuell unter Linux bereitstellen. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [Voraussetzungen und Systemanforderungen](#prerequisites-and-system-requirements)
  - [Konfigurieren des Linux-Software-Repositorys](#configure-the-linux-software-repository)
    - [RHEL und Varianten (CentOS und Oracle Linux)](#rhel-and-variants-centos-and-oracle-linux)
    - [SLES und Varianten](#sles-and-variants)
    - [Ubuntu- und Ubuntu-Systeme](#ubuntu-and-debian-systems)
  - [Anwendungsinstallation](#application-installation)
  - [Herunterladen des Onboardingpakets](#download-the-onboarding-package)
  - [Clientkonfiguration](#client-configuration)
  - [Installer-Skript](#installer-script)
  - [Protokollieren von Installationsproblemen](#log-installation-issues)
  - [Betriebssystemupgrades](#operating-system-upgrades)
  - [Deinstallation](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie unter [Microsoft Defender für Endpunkt unter Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

## <a name="configure-the-linux-software-repository"></a>Konfigurieren des Linux-Software-Repositorys

Defender für Endpunkt unter Linux kann von einem der folgenden Kanäle bereitgestellt werden (unten als *[Kanal]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Software-Repository. Anweisungen zum Konfigurieren Ihres Geräts für die Verwendung eines dieser Repositorys finden Sie unten.

Die Wahl des Kanals bestimmt den Typ und die Häufigkeit von Updates, die auf Ihrem Gerät angeboten werden. Geräte in *Insider-Fast* sind die ersten Geräte, die Updates und neue Features erhalten, gefolgt von *insider-slow* und schließlich von *prod*.

Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insiderschnell* oder langsam verwendet *werden.*

> [!WARNING]
> Um den Kanal nach der Erstinstallation zu wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät erneut für die Verwendung des neuen Kanals, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort zu installieren.

### <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL und Varianten (CentOS und Oracle Linux)

- Installieren `yum-utils` Sie, wenn es noch nicht installiert ist:

    ```bash
    sudo yum install yum-utils
    ```

- Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config/` . Beispielsweise liegt RHEL 7.9 näher bei 7,4 als bei 8.

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:

    > [!NOTE]
    > Ersetzen Sie *[distro]* bei Oracle Linux durch "rhel".

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Wenn Sie z. B. CentOS 7 ausführen und Defender für Endpunkt unter Linux über den *Prod-Kanal* bereitstellen möchten:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    Oder wenn Sie neue Features auf ausgewählten Geräten erkunden möchten, sollten Sie Microsoft Defender für Endpunkt unter Linux im *Insider-Fast-Kanal* bereitstellen:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- Laden Sie alle Metadaten für die derzeit aktivierten Yum-Repositorys herunter, und verwenden Sie sie:

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a>SLES und Varianten

- Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config/` .

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Wenn Sie beispielsweise SLES 12 ausführen und Microsoft Defender für Endpunkt unter Linux über den *prod-Kanal* bereitstellen möchten:

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Ubuntu- und Ubuntu-Systeme

- Installieren `curl` Sie, wenn es noch nicht installiert ist:

    ```bash
    sudo apt-get install curl
    ```

- Installieren `libplist-utils` Sie, wenn es noch nicht installiert ist:

    ```bash
    sudo apt-get install libplist-utils
    ```

- Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config` .

    Ersetzen Sie im folgenden Befehl *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    Wenn Sie beispielsweise Ubuntu 18.04 ausführen und MDE für Linux über den *Prod-Kanal* bereitstellen möchten:

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- Installieren Sie die Repositorykonfiguration:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    Wenn Sie *z. B. "Prod Channel"* ausgewählt haben:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- Installieren Sie das `gpg` Paket, wenn es nicht bereits installiert ist:

    ```bash
    sudo apt-get install gpg
    ```

  Wenn `gpg` nicht verfügbar, installieren Sie `gnupg` .

- Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- Installieren Sie den HTTPS-Treiber, wenn er noch nicht vorhanden ist:

    ```bash
    sudo apt-get install apt-transport-https
    ```

- Aktualisieren Sie die Repositorymetadaten:

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>Anwendungsinstallation

- RHEL und Varianten (CentOS und Oracle Linux):

    ```bash
    sudo yum install mdatp
    ```

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden. Je nach Verteilung und Version des Servers kann sich der Repositoryalias von dem im folgenden Beispiel unterscheiden.

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- SLES und Varianten:

    ```bash
    sudo zypper install mdatp
    ```

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- Ubuntu- und Ubuntu-System:

    ```bash
    sudo apt-get install mdatp
    ```

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a>Herunterladen des Onboardingpakets

Laden Sie das Onboardingpaket aus Microsoft 365 Defender Portal herunter:

1. Wechseln Sie im Microsoft 365 Defender Portal zu **Einstellungen > Endpunkte > Geräteverwaltung > Onboarding.**
2. Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdownmenü **"Lokales Skript"** als Bereitstellungsmethode aus.
3. Wählen Sie **"Onboardingpaket herunterladen"** aus. Speichern Sie die Datei als WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot des Microsoft 365 Defender Portals](images/atp-portal-onboarding-linux.png)

4. Überprüfen Sie an einer Eingabeaufforderung, ob Die Datei vorhanden ist.
    Extrahieren Sie den Inhalt des Archivs:

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a>Clientkonfiguration

1. Kopieren Sie MicrosoftDefenderATPOnboardingLinuxServer.py auf das Zielgerät.

    Anfangs ist das Clientgerät keiner Organisation zugeordnet. Beachten Sie, dass das *orgId-Attribut* leer ist:

    ```bash
    mdatp health --field org_id
    ```

2. Führen Sie MicrosoftDefenderATPOnboardingLinuxServer.py aus. 
   
    >[!NOTE]
    >Zum Ausführen dieses Befehls müssen Sie `python` auf dem Gerät installiert sein. Wenn Sie RHEL 8.x oder Ubuntu 20.04 oder höher ausführen, müssen Sie Python 3 anstelle von Python verwenden.



    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und melden Sie einen gültigen Organisationsbezeichner:

    ```bash
    mdatp health --field org_id
    ```

4. Einige Minuten nach Abschluss der Installation können Sie den Status anzeigen, indem Sie den folgenden Befehl ausführen. Ein Rückgabewert, der `1` angibt, dass das Produkt erwartungsgemäß funktioniert:

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischadsoftwaredefinitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern. Während dieser Zeit gibt der obige Befehl den Wert `false` . Mit dem folgenden Befehl können Sie den Status der Definitionsaktualisierung überprüfen:
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > Bitte beachten Sie, dass Sie nach Abschluss der Erstinstallation möglicherweise auch einen Proxy konfigurieren müssen. Siehe [Konfigurieren von Defender für Endpunkt unter Linux für statische Proxyermittlung: Konfiguration nach der Installation.](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)

5. Führen Sie einen Erkennungstest aus, um sicherzustellen, dass das Gerät ordnungsgemäß integriert ist, und melden Sie sich an den Dienst. Führen Sie die folgenden Schritte auf dem neu eingebundenen Gerät durch:

    - Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (angegeben durch ein Ergebnis der `1` Ausführung des folgenden Befehls):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - Öffnen Sie ein Terminal-Fenster. Kopieren Sie den folgenden Befehl und führen Sie ihn aus:

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - Die Datei sollte von Defender für Endpunkt unter Linux in Quarantäne gestellt worden sein. Verwenden Sie den folgenden Befehl, um alle entdeckten Bedrohungen aufzulisten:

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a>Erfahrung der Funktionen von Linux EDR (EDR) mit simulierten Angriffen

Um die Funktionen von EDR für Linux zu testen, führen Sie die folgenden Schritte aus, um eine Erkennung auf Ihrem Linux-Server zu simulieren und den Fall zu untersuchen. 

1.  Stellen Sie sicher, dass der integrierte Linux-Server in Microsoft 365 Defender angezeigt wird. Wenn es sich um das erste Onboarding des Computers handelt, kann es bis zu 20 Minuten dauern, bis er angezeigt wird. 

2.  Laden Sie die [Skriptdatei](https://aka.ms/LinuxDIY) herunter, extrahieren Sie sie auf einen integrierten Linux-Server, und führen Sie den folgenden Befehl aus: `./mde_linux_edr_diy.sh`

3.  Nach ein paar Minuten sollte eine Erkennung in Microsoft 365 Defender ausgelöst werden.

4.  Sehen Sie sich die Warnungsdetails, die Computerzeitachse und die typischen Untersuchungsschritte an.




## <a name="installer-script"></a>Installer-Skript

Alternativ können Sie ein automatisiertes [Installer-Bash-Skript](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) verwenden, das in unserem [öffentlichen GitHub-Repository](https://github.com/microsoft/mdatp-xplat/)bereitgestellt wird.
Das Skript identifiziert die Verteilung und Version und richtet das Gerät so ein, dass das neueste Paket abgerufen und installiert wird.
Sie können das Onboarding auch mit einem bereitgestellten Skript ausführen.

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

Weitere Informationen finden Sie [hier.](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)

## <a name="log-installation-issues"></a>Protokollieren von Installationsproblemen

Weitere Informationen zum Auffinden des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter ["Protokollinstallationsprobleme".](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Betriebssystemupgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zuerst Defender für Endpunkt unter Linux deinstallieren, das Upgrade installieren und schließlich Defender für Endpunkt unter Linux auf Ihrem Gerät neu konfigurieren.

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>Migrieren von Insiders-Fast zum Produktionskanal

1. Deinstallieren Sie die Version "Insiders-Fast Channel" von Defender für Endpunkt unter Linux.

    ``
    sudo yum remove mdatp
    ``

1. Deaktivieren des Repositorys für Defender für Endpunkt unter Linux Insiders-Fast  ``
    sudo yum repolist
    ``

    > [!NOTE]
    > Die Ausgabe sollte "packages-microsoft-com-fast-prod" anzeigen.

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. Stellen Sie MDE für Linux unter Verwendung des "Produktionskanals" erneut bereit.


## <a name="uninstallation"></a>Deinstallation

Weitere Informationen zum Entfernen von Defender für Endpunkt auf Linux von Clientgeräten finden Sie unter ["Deinstallieren".](linux-resources.md#uninstall)

## <a name="see-also"></a>Siehe auch
- [Untersuchen von Problemen mit der Agent-Integrität](health-status.md)
