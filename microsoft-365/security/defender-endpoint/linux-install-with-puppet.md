---
title: Bereitstellen von Microsoft Defender ATP für Linux mit Puppet
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender ATP für Linux mithilfe von Puppet bereitstellen.
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
ms.openlocfilehash: 562433ee52b2e39716e933c67c706f030195bd2f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688417"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>Bereitstellen von Microsoft Defender for Endpoint unter Linux mit "Puppet"

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Artikel wird beschrieben, wie Sie Defender for Endpoint für Linux mithilfe von Puppet bereitstellen. Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:

- [Herunterladen des Onboardingpakets](#download-the-onboarding-package)
- [Erstellen eines "Puppet"-Manifests](#create-a-puppet-manifest)
- [Bereitstellung](#deployment)
- [Überprüfen des Onboardingstatus](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

 Eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion finden Sie auf der [Hauptseite von Defender for Endpoint für Linux](microsoft-defender-endpoint-linux.md).

Darüber hinaus müssen Sie für die Bereitstellung von "Puppet" mit den Verwaltungsaufgaben von "Puppet" vertraut sein, "Puppet" konfiguriert haben und wissen, wie Sie Pakete bereitstellen. "Puppet" bietet viele Möglichkeiten, dieselbe Aufgabe auszuführen. Diese Anweisungen setzen die Verfügbarkeit von unterstützten Puppet-Modulen voraus, z. B. *apt,* um das Paket bereitstellen zu können. Ihre Organisation kann einen anderen Workflow verwenden. Ausführliche Informationen finden Sie in [der Dokumentation zu Denkfiguren.](https://puppet.com/docs)

## <a name="download-the-onboarding-package"></a>Herunterladen des Onboardingpakets

Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:

1. Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.
2. Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus. Wählen Sie im zweiten Dropdownmenü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.
3. Wählen **Sie Onboardingpaket herunterladen aus.** Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Extrahieren Sie den Inhalt des Archivs.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Erstellen eines Puppet-Manifests

Sie müssen ein Puppet-Manifest für die Bereitstellung von Defender for Endpoint für Linux auf Geräten erstellen, die von einem Puppet-Server verwaltet werden. In diesem Beispiel werden die *apt-* und *yumrepo-Module* verwendet, die in den Puppetlabs verfügbar sind, und es wird davon ausgegangen, dass die Module auf Dem Puppet-Server installiert wurden.

Erstellen Sie die *Ordner install_mdatp/Dateien* *und install_mdatp/Manifeste* unter dem Modulordner Ihrer Puppet-Installation. Dieser Ordner befindet sich in der Regel in */etc/puppetlabs/code/environments/production/modules* auf Ihrem Puppet-Server. Kopieren Sie mdatp_onboard.json-Datei, die oben erstellt wurde, in den *ordner install_mdatp/files.* Erstellen eines *init.pp* datei, die die Bereitstellungsanweisungen enthält:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Inhalt von `install_mdatp/manifests/init.pp`

Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository.

Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden. Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.

Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*

> [!WARNING]
> Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.

Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .

Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:

> [!NOTE]
> Ersetzen Sie bei RedHat, Oracle EL und CentOS 8 *[distro]* durch "rhel".

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Bereitstellung)

Schließen Sie das oben beschriebene Manifest in Ihre website.pp ein. Datei:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

Registrierte Agentgeräte suchen regelmäßig den Puppet Server ab, und installieren neue Konfigurationsprofile und -richtlinien, sobald sie erkannt werden.

## <a name="monitor-puppet-deployment"></a>Überwachen der Bereitstellung von "Puppet"

Auf dem Agentgerät können Sie auch den Onboardingstatus überprüfen, indem Sie:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **lizenziert**: Dadurch wird bestätigt, dass das Gerät an Ihre Organisation gebunden ist.

- **orgId**: Dies ist Ihr Defender for Endpoint-Organisationsbezeichner.

## <a name="check-onboarding-status"></a>Überprüfen des Onboardingstatus

Sie können überprüfen, ob Geräte ordnungsgemäß onboardiert wurden, indem Sie ein Skript erstellen. Das folgende Skript überprüft beispielsweise registrierte Geräte auf den Onboardingstatus:

```bash
mdatp health --field healthy
```

Der obige Befehl `1` druckt, wenn das Produkt wie erwartet onboarded ist und funktioniert.

> [!IMPORTANT]
> Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen. Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern. Während dieser Zeit gibt der obige Befehl den Wert `0` zurück.

Wenn das Produkt nicht fehlerfrei ist, gibt der Exitcode (der durchcheckt werden `echo $?` kann) das Problem an:

- 1, wenn das Gerät noch nicht onboarded ist.
- 3, wenn die Verbindung zum Daemon nicht hergestellt werden kann.

## <a name="log-installation-issues"></a>Probleme bei der Protokollinstallation

 Weitere Informationen zum Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter [Log installation issues](linux-resources.md#log-installation-issues).

## <a name="operating-system-upgrades"></a>Betriebssystemupgrades

Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.

## <a name="uninstallation"></a>Deinstallation

Erstellen eines *Moduls remove_mdatp* ähnlich *install_mdatp* Inhalten in *init.pp* Datei:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
