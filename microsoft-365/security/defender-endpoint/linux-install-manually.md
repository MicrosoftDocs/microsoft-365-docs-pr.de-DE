---
title: Manuelles Bereitstellen von Microsoft Defender for Endpoint unter Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender for Endpoint unter Linux manuell über die Befehlszeile bereitstellen.
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
ms.openlocfilehash: 2beb46c62de2e9720d1626e0e1e5ce806a6d7e19
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903916"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>Manuelles Bereitstellen von Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Sie Microsoft Defender for Endpoint auf Linux manuell bereitstellen. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Manuelles Bereitstellen von Microsoft Defender for Endpoint unter Linux](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [Voraussetzungen und Systemanforderungen](#prerequisites-and-system-requirements)
  - [Konfigurieren des Linux-Softwarerepositorys](#configure-the-linux-software-repository)
    - [RHEL und Varianten (CentOS und Oracle Linux)](#rhel-and-variants-centos-and-oracle-linux)
    - [SLES und Varianten](#sles-and-variants)
    - [Ubuntu- und Debian-Systeme](#ubuntu-and-debian-systems)
  - [Anwendungsinstallation](#application-installation)
  - [Herunterladen des Onboardingpakets](#download-the-onboarding-package)
  - [Clientkonfiguration](#client-configuration)
  - [Installerskript](#installer-script)
  - [Probleme bei der Protokollinstallation](#log-installation-issues)
  - [Betriebssystemupgrades](#operating-system-upgrades)
  - [Deinstallation](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie unter [Microsoft Defender for Endpoint unter Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

## <a name="configure-the-linux-software-repository"></a>Konfigurieren des Linux-Softwarerepositorys

Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository. Anweisungen zum Konfigurieren Ihres Geräts für die Verwendung eines dieser Repositorys finden Sie unten.

Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden. Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.

Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*

> [!WARNING]
> Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.

### <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL und Varianten (CentOS und Oracle Linux)

- Installieren, `yum-utils` wenn es noch nicht installiert ist:

    ```bash
    sudo yum install yum-utils
    ```

- Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config/` . Rhel 7.9 ist beispielsweise näher an 7,4 als 8.

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:

    > [!NOTE]
    > Ersetzen Sie bei Oracle Linux *[distro] durch* "rhel".

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Beispiel: Wenn Sie CentOS 7 ausführen und Defender for Endpoint für Linux über den *prod-Kanal bereitstellen* möchten:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    Oder wenn Sie neue Features auf ausgewählten Geräten erkunden möchten, sollten Sie MDE für Linux für *insiders-fast channel* bereitstellen:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- Installieren sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- Laden Sie alle Metadaten für die derzeit aktivierten yum-Repositorys herunter, und verwenden Sie sie:

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a>SLES und Varianten

- Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config/` .

    Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Beispiel: Wenn Sie SLES 12 ausführen und MDE für Linux über den *prod-Kanal bereitstellen* möchten:

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- Installieren sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Ubuntu- und Debian-Systeme

- Installieren, `curl` wenn es noch nicht installiert ist:

    ```bash
    sudo apt-get install curl
    ```

- Installieren, `libplist-utils` wenn es noch nicht installiert ist:

    ```bash
    sudo apt-get install libplist-utils
    ```

- Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config` .

    Ersetzen Sie im folgenden Befehl *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    Wenn Sie beispielsweise Ubuntu 18.04 ausführen und MDE für Linux über den *prod-Kanal bereitstellen* möchten:

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- Installieren Sie die Repositorykonfiguration:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    Wenn Sie z. B. prod channel *ausgewählt* haben:
    
    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```   

- Installieren Sie `gpg` das Paket, wenn es noch nicht installiert ist:

    ```bash
    sudo apt-get install gpg
    ```

  Wenn `gpg` nicht verfügbar, installieren Sie `gnupg` .

- Installieren sie den öffentlichen Microsoft GPG-Schlüssel:

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- Installieren Sie den https-Treiber, wenn er noch nicht vorhanden ist:

    ```bash
    sudo apt-get install apt-transport-https
    ```

- Aktualisieren der Repositorymetadaten:

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>Anwendungsinstallation

- RHEL und Varianten (CentOS und Oracle Linux):

    ```bash
    sudo yum install mdatp
    ```

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden. Je nach Verteilung und Version des Servers kann sich der Repositoryalias von dem im folgenden Beispiel unterscheiden.

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

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.

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

- Ubuntu- und Debian-System:

    ```bash
    sudo apt-get install mdatp
    ```

    Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll. Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben. Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.

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

Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:

1. Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.
2. Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdownmenü lokales Skript (für bis zu **10 Geräte)** als Bereitstellungsmethode aus.
3. Wählen **Sie Onboardingpaket herunterladen aus.** Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux.png)

4. Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen.
    Extrahieren sie den Inhalt des Archivs:

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

1. Kopieren MicrosoftDefenderATPOnboardingLinuxServer.py auf das Zielgerät.

    Anfangs ist das Clientgerät nicht einer Organisation zugeordnet. Beachten Sie, dass *das orgId-Attribut* leer ist:

    ```bash
    mdatp health --field org_id
    ```

2. Führen MicrosoftDefenderATPOnboardingLinuxServer.py aus, und beachten Sie, dass Sie zum Ausführen dieses Befehls auf dem `python` Gerät installiert sein müssen:

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und meldet eine gültige Organisations-ID:

    ```bash
    mdatp health --field org_id
    ```

4. Ein paar Minuten nach Abschluss der Installation können Sie den Status anzeigen, indem Sie den folgenden Befehl ausführen. Ein Rückgabewert von `1` gibt an, dass das Produkt wie erwartet funktioniert:

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern. Während dieser Zeit gibt der obige Befehl den Wert `false` zurück. Sie können den Status der Definitionsaktualisierung mithilfe des folgenden Befehls überprüfen:
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > Bitte beachten Sie, dass Sie nach Abschluss der Erstinstallation möglicherweise auch einen Proxy konfigurieren müssen. Weitere Informationen finden Sie unter [Configure Defender for Endpoint for Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).

5. Führen Sie einen Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst. Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:

    - Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (wird durch das Ausführen des folgenden `1` Befehls bezeichnet):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - Öffnen Sie ein Terminalfenster. Kopieren Sie den folgenden Befehl, und führen Sie diesen aus:

        ``` bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - Die Datei sollte von Defender for Endpoint für Linux isoliert worden sein. Verwenden Sie den folgenden Befehl, um alle erkannten Bedrohungen auflisten:

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a>Installerskript

Alternativ können Sie ein automatisiertes [Installer-Bash-Skript verwenden,](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) das in unserem [öffentlichen GitHub-Repository bereitgestellt wird.](https://github.com/microsoft/mdatp-xplat/)
Das Skript identifiziert die Verteilung und Version und richtet das Gerät ein, um das neueste Paket zu ziehen und zu installieren.
Sie können auch ein Onboarding mit einem bereitgestellten Skript ausführen.

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

Weitere Informationen [finden Sie hier](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).

## <a name="log-installation-issues"></a>Probleme bei der Protokollinstallation

Weitere [Informationen zum](linux-resources.md#log-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollinstallationsprobleme.

## <a name="operating-system-upgrades"></a>Betriebssystemupgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>Migrieren von Insiders-Fast zum Produktionskanal

1. Deinstallieren Sie die Version "Insiders-Fast channel" von MDE für Linux.

    ``
    sudo yum remove mdatp
    ``

1. Deaktivieren des MDE für Linux Insiders-Fast Repository  ``
    sudo yum repolist
    ``

    > [!NOTE]
    > Die Ausgabe sollte "packages-microsoft-com-fast-prod" enthalten.

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. Erneute Bereitstellung von MDE für Linux mithilfe des "Produktionskanals".


## <a name="uninstallation"></a>Deinstallation

Weitere Informationen zum Entfernen von Defender for Endpoint für Linux von Clientgeräten finden Sie unter [Deinstallieren.](linux-resources.md#uninstall)
