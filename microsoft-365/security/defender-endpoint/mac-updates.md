---
title: Bereitstellen von Updates für Microsoft Defender for Endpoint auf Dem Mac
description: Steuern von Updates für Microsoft Defender for Endpoint auf Mac in Unternehmensumgebungen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
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
ms.openlocfilehash: e08781455888595d57bd8a9e6f792796ea1853cd
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684207"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Bereitstellen von Updates für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt unter Mac OS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.

Zum Aktualisieren von Microsoft Defender for Endpoint auf macOS wird ein Programm mit dem Namen Microsoft AutoUpdate (MAU) verwendet. Mau sucht standardmäßig täglich automatisch nach Updates, Sie können dies jedoch wöchentlich, monatlich oder manuell ändern.

![MAU-Screenshot](images/MDATP-34-MAU.png)

Wenn Sie sich für die Bereitstellung von Updates mit Ihren Softwareverteilungstools entscheiden, sollten Sie MAU so konfigurieren, dass sie manuell auf Softwareupdates überprüft. Sie können Einstellungen bereitstellen, um zu konfigurieren, wie und wann MAU nach Updates für die Macs in Ihrer Organisation sucht.

## <a name="use-msupdate"></a>Msupdate verwenden

MAU enthält ein Befehlszeilentool namens *msupdate,* das für IT-Administratoren entwickelt wurde, damit sie präziser steuern können, wann Updates angewendet werden. Anweisungen zur Verwendung dieses Tools finden Sie unter [Update Office für Mac using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).

In MAU ist die Anwendungs-ID für Microsoft Defender for Endpoint auf macOS *WDAV00*. Führen Sie den folgenden Befehl aus einem Terminalfenster aus, um die neuesten Updates für Microsoft Defender for Endpoint unter macOS herunterzuladen und zu installieren:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Festlegen von Einstellungen für Microsoft AutoUpdate

In diesem Abschnitt werden die gängigsten Einstellungen beschrieben, die zum Konfigurieren von MAU verwendet werden können. Diese Einstellungen können als Konfigurationsprofil über die Verwaltungskonsole bereitgestellt werden, die Ihr Unternehmen verwendet. Ein Beispiel für ein Konfigurationsprofil wird in den folgenden Abschnitten gezeigt.

### <a name="set-the-channel-name"></a>Festlegen des Kanalnamens

Der Kanal bestimmt den Typ und die Häufigkeit von Updates, die über MAU angeboten werden. Geräte in `Beta` können neue Features ausprobieren, bevor Geräte in `Preview` und verwendet `Current` werden. 

Der `Current` Kanal enthält die stabilste Version des Produkts.

>[!IMPORTANT]
> Vor Microsoft AutoUpdate, Version 4.29, hatten Kanäle unterschiedliche Namen: 
> 
> - `Beta` wurde benannt `InsiderFast` (Insider Fast)
> - `Preview` wurde benannt `External` (Insider Slow)
> - `Current` wurde benannt `Production`

>[!TIP]
>Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen auf oder `Beta` zu `Preview` konfigurieren.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | ChannelName |
| **Datentyp** | String |
| **Mögliche Werte** | Beta <br/> Vorschau <br/> Current |
|||

>[!WARNING]
>Mit dieser Einstellung wird der Kanal für alle Anwendungen geändert, die über Microsoft AutoUpdate aktualisiert werden. Um den Kanal nur für Microsoft Defender for Endpoint unter macOS zu ändern, führen Sie nach dem Ersetzen durch den gewünschten Kanal den folgenden `[channel-name]` Befehl aus:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Festlegen der Häufigkeit der Aktualisierungsüberprüfung

Ändern Sie, wie oft MAU nach Updates sucht.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | UpdateCheckFrequency |
| **Datentyp** | Ganze Zahl |
| **Standardwert** | 720 (Minuten) |
| **Kommentar** | Dieser Wert wird in Minuten festgelegt. |


### <a name="change-how-mau-interacts-with-updates"></a>Ändern der Interaktion von MAU mit Updates

Ändern sie, wie MAU nach Updates sucht.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | HowToCheck |
| **Datentyp** | String |
| **Mögliche Werte** | Manuell <br/> AutomaticCheck <br/> AutomaticDownload |
| **Kommentar** |  Beachten Sie, dass AutomaticDownload nach Möglichkeit automatisch heruntergeladen und installiert wird. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Ändern, ob die Schaltfläche "Auf Updates überprüfen" aktiviert ist

Ändern Sie, ob lokale Benutzer auf der Benutzeroberfläche von Microsoft AutoUpdate auf die Option "Nach Updates suchen" klicken können.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | EnableCheckForUpdatesButton |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | True (Standard) <br/> Falsch |


### <a name="disable-insider-checkbox"></a>Kontrollkästchen Insider deaktivieren

Auf true festgelegt, um das "Join the Office Insider Program..." zu erstellen. Kontrollkästchen für Benutzer nicht verfügbar/ausgegraut.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | DisableInsiderCheckbox |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | False (Standard) <br/> Wahr |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Einschränken der Telemetrie, die von MAU gesendet wird

Auf false festgelegt, um minimale Taktdaten, keine Anwendungsverwendung und keine Umgebungsdetails zu senden.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | SendAllTelemetryEnabled |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | True (Standard) <br/> Falsch |


## <a name="example-configuration-profile"></a>Beispielkonfigurationsprofil

Das folgende Konfigurationsprofil wird verwendet für:
- Platzieren des Geräts im Produktionskanal
- Updates automatisch herunterladen und installieren
- Aktivieren der Schaltfläche "Auf Updates überprüfen" auf der Benutzeroberfläche
- Zulassen, dass Sich Benutzer auf dem Gerät bei den Insiderkanälen registrieren


>[!WARNING]
>Die folgende Konfiguration ist eine Beispielkonfiguration und sollte nicht in der Produktion ohne ordnungsgemäße Überprüfung der Einstellungen und Anpassung der Konfigurationen verwendet werden.

>[!TIP]
>Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen auf oder `Beta` zu `Preview` konfigurieren.

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Zum Konfigurieren von MAU können Sie dieses Konfigurationsprofil über das Verwaltungstool bereitstellen, das Ihr Unternehmen verwendet:
- Laden Sie aus JAMF dieses Konfigurationsprofil hoch, und legen Sie die Einstellungsdomäne *auf com.microsoft.autoupdate2 fest.*
- Laden Sie in Intune dieses Konfigurationsprofil hoch, und legen Sie den namen des benutzerdefinierten *Konfigurationsprofils auf com.microsoft.autoupdate2 .*

## <a name="resources"></a>Ressourcen

- [msupdate-Referenz](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
