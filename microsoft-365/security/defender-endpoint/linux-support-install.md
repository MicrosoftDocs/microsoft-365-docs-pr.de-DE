---
title: Beheben von Installationsproblemen für Microsoft Defender for Endpoint unter Linux
ms.reviewer: ''
description: Beheben von Installationsproblemen für Microsoft Defender for Endpoint unter Linux
keywords: microsoft, defender, atp, linux, installation
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 270ad1145308aaa2af703cda84307a4a96097a53
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903130"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Beheben von Installationsproblemen für Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Überprüfen, ob die Installation erfolgreich war

Ein Fehler bei der Installation kann zu einer aussagekräftigen Fehlermeldung des Paket-Managers führen. Um zu überprüfen, ob die Installation erfolgreich war, rufen Sie die Installationsprotokolle ab, und überprüfen Sie sie mit:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Eine Ausgabe des vorherigen Befehls mit dem richtigen Datum und der richtigen Installationszeit zeigt den Erfolg an.

Überprüfen Sie außerdem die [Clientkonfiguration,](linux-install-manually.md#client-configuration) um die Integrität des Produkts zu überprüfen und die EICAR-Textdatei zu erkennen.

## <a name="make-sure-you-have-the-correct-package"></a>Stellen Sie sicher, dass Sie über das richtige Paket verfügen

Beachten Sie, dass das paket, das Sie installieren, mit der Hostverteilung und -version übereinstimmen.

| package                       | Verteilung                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL und CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL und CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian und Ubuntu 16.04, 18.04 und 20.04 |

Stellen Sie bei der [manuellen](linux-install-manually.md)Bereitstellung sicher, dass die richtige Distro- und Version ausgewählt wurde.

## <a name="installation-failed"></a>Installation fehlgeschlagen

Überprüfen Sie, ob der mdatp-Dienst ausgeführt wird:

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Schritte zur Problembehandlung, wenn der mdatp-Dienst nicht ausgeführt wird

1. Überprüfen Sie, ob "mdatp"-Benutzer vorhanden ist:

    ```bash
    id "mdatp"
    ```

    Wenn keine Ausgabe angezeigt wird, führen Sie

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Versuchen Sie, den Dienst zu aktivieren und neu zu starten:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Wenn mdatp.service beim Ausführen des vorherigen Befehls nicht gefunden wird, führen Sie aus:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    Dabei handelt es sich um Ubuntu- und ```<systemd_path>``` ```/lib/systemd/system``` Debian-Distributionen sowie für ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle und SLES.
   Führen Sie dann Schritt 2 erneut aus.

4. Wenn die oben genannten Schritte nicht funktionieren, überprüfen Sie, ob SELinux installiert ist und ob der Erzwingungsmodus aktiviert ist. Wenn ja, versuchen Sie, ihn auf den zulässigen (vorzugsweise) oder deaktivierten Modus zu setzen. Dies kann durch Festlegen des Parameters auf "zulässig" oder "deaktiviert" in der Datei, gefolgt von `SELINUX` `/etc/selinux/config` einem Neustart, geschehen. Weitere Informationen finden Sie auf der Man-Seite von selinux.
Versuchen Sie nun, den mdatp-Dienst mithilfe von Schritt 2 neu zu starten. Stellen Sie die Konfigurationsänderung nach dem Versuch und dem Neustart aus Sicherheitsgründen sofort wieder ein.

5. Wenn `/opt` Directory ein symbolischer Link ist, erstellen Sie eine Bindungs mount für `/opt/microsoft` .

6. Stellen Sie sicher, dass der Daemon über ausführbare Berechtigungen verfügt.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Wenn der Daemon nicht über ausführbare Berechtigungen verfügt, machen Sie ihn mithilfe von:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    und wiederholen Sie die Ausführung von Schritt 2.

7. Stellen Sie sicher, dass das Dateisystem, das wdavdaemon enthält, nicht mit "noexec" bereitgestellt ist.

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Wenn der mdatp-Dienst ausgeführt wird, die ERKENNUNG von EICAR-Textdateien jedoch nicht funktioniert

1. Überprüfen Sie den Dateisystemtyp mithilfe von:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Derzeit unterstützte Dateisysteme für On-Access-Aktivitäten sind hier [aufgeführt.](microsoft-defender-endpoint-linux.md#system-requirements) Alle Dateien außerhalb dieser Dateisysteme werden nicht überprüft.

## <a name="command-line-tool-mdatp-isnt-working"></a>Befehlszeilentool "mdatp" funktioniert nicht

1. Wenn beim Ausführen des Befehlszeilentools `mdatp` ein Fehler `command not found` auftritt, führen Sie den folgenden Befehl aus:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    und versuchen Sie es erneut.

    Wenn keiner der obigen Schritte hilfreich ist, erfassen Sie die Diagnoseprotokolle:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Der Pfad zu einer ZIP-Datei, die die Protokolle enthält, wird als Ausgabe angezeigt. Mit diesen Protokollen erreichen Sie unseren Kundensupport.
