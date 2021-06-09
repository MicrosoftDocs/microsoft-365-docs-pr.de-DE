---
title: Bereitstellen von Updates für Microsoft Defender für Endpunkt auf dem Mac
description: Steuern von Updates für Microsoft Defender für Endpunkt auf dem Mac in Unternehmensumgebungen.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Updates, bereitstellen
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
ms.openlocfilehash: 6447aa4182846020312e9be870c5548d9415ac71
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842830"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Bereitstellen von Updates für Microsoft Defender für Endpunkt unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt unter Mac OS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft veröffentlicht regelmäßig Softwareupdates, um Leistung, Sicherheit und neue Features zu verbessern.

Zum Aktualisieren von Microsoft Defender für Endpunkt unter macOS wird ein Programm namens Microsoft AutoUpdate (MAU) verwendet. Standardmäßig sucht MAU täglich automatisch nach Updates, sie können dies jedoch wöchentlich, monatlich oder manuell ändern.

![MAU-Screenshot](images/MDATP-34-MAU.png)

Wenn Sie updates mit ihren Softwareverteilungstools bereitstellen möchten, sollten Sie MAU so konfigurieren, dass manuell nach Softwareupdates gesucht wird. Sie können Einstellungen bereitstellen, um zu konfigurieren, wie und wann MAU nach Updates für Macs in Ihrer Organisation sucht.

## <a name="use-msupdate"></a>Msupdate verwenden

MAU enthält ein Befehlszeilentool namens *msupdate,* das für IT-Administratoren entwickelt wurde, damit sie präziser steuern können, wann Updates angewendet werden. Anweisungen zur Verwendung dieses Tools finden Sie unter [Update Office für Mac mithilfe von msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).

In MAU ist der Anwendungsbezeichner für Microsoft Defender für Endpunkt unter macOS *WDAV00.* Um die neuesten Updates für Microsoft Defender für Endpunkt unter macOS herunterzuladen und zu installieren, führen Sie den folgenden Befehl aus einem Terminalfenster aus:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Festlegen von Einstellungen für Microsoft AutoUpdate

In diesem Abschnitt werden die gängigsten Einstellungen beschrieben, die zum Konfigurieren von MAU verwendet werden können. Diese Einstellungen können über die Verwaltungskonsole, die Ihr Unternehmen verwendet, als Konfigurationsprofil bereitgestellt werden. Ein Beispiel für ein Konfigurationsprofil finden Sie in den folgenden Abschnitten.

### <a name="set-the-channel-name"></a>Festlegen des Kanalnamens

Der Kanal bestimmt den Typ und die Häufigkeit von Updates, die über MAU angeboten werden. Geräte `Beta` in können neue Features testen, bevor Geräte in `Preview` und `Current` . 

Der `Current` Kanal enthält die stabilste Version des Produkts.

>[!IMPORTANT]
> Vor Microsoft AutoUpdate, Version 4.29, hatten Kanäle unterschiedliche Namen: 
> 
> - `Beta` wurde benannt `InsiderFast` (Insider Fast)
> - `Preview` wurde benannt `External` (Insider Slow)
> - `Current` benannt wurde `Production`

>[!TIP]
>Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen für oder zu `Beta` `Preview` konfigurieren.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | ChannelName |
| **Datentyp** | String |
| **Mögliche Werte** | Beta <br/> Vorschau <br/> Current |
|||

>[!WARNING]
>Diese Einstellung ändert den Kanal für alle Anwendungen, die über Microsoft AutoUpdate aktualisiert werden. Um den Kanal nur für Microsoft Defender für Endpunkt unter macOS zu ändern, führen Sie den folgenden Befehl aus, nachdem Sie ihn durch den gewünschten Kanal ersetzt `[channel-name]` haben:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Festlegen der Häufigkeit der Updateüberprüfung

Ändern, wie oft MAU nach Updates sucht.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | UpdateCheckFrequency |
| **Datentyp** | Ganze Zahl |
| **Standardwert** | 720 (Minuten) |
| **Kommentar** | Dieser Wert wird in Minuten festgelegt. |


### <a name="change-how-mau-interacts-with-updates"></a>Ändern der Interaktion von MAU mit Updates

Ändern, wie MAU nach Updates sucht.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | HowToCheck |
| **Datentyp** | String |
| **Mögliche Werte** | Manuell <br/> AutomaticCheck <br/> AutomaticDownload |
| **Kommentar** |  Beachten Sie, dass AutomaticDownload nach Möglichkeit automatisch heruntergeladen und installiert wird. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Ändern, ob die Schaltfläche "Nach Updates suchen" aktiviert ist

Ändern Sie, ob lokale Benutzer auf der Microsoft AutoUpdate-Benutzeroberfläche auf die Option "Nach Updates suchen" klicken können.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | EnableCheckForUpdatesButton |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | True (Standard) <br/> Falsch |


### <a name="disable-insider-checkbox"></a>Deaktivieren des Insider-Kontrollkästchens

Legen Sie "true" fest, um "am Office-Insider-Programm teilzunehmen..." Kontrollkästchen für Benutzer nicht verfügbar/abgeblendet.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | DisableInsiderCheckbox |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | False (Standard) <br/> Wahr |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Einschränken der Telemetrie, die von MAU gesendet wird

Auf "false" festgelegt, um minimale Taktdaten, keine Anwendungsverwendung und keine Umgebungsdetails zu senden.

|Abschnitt|Wert|
|:--|:--|
| **Domäne** | `com.microsoft.autoupdate2` |
| **Schlüssel** | SendAllTelemetryEnabled |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | True (Standard) <br/> Falsch |


## <a name="example-configuration-profile"></a>Beispielkonfigurationsprofil

Das folgende Konfigurationsprofil wird verwendet, um:
- Platzieren des Geräts im Produktionskanal
- Updates automatisch herunterladen und installieren
- Aktivieren Sie die Schaltfläche "Nach Updates suchen" auf der Benutzeroberfläche.
- Zulassen, dass sich Benutzer auf dem Gerät bei den Insider-Kanälen registrieren


>[!WARNING]
>Die folgende Konfiguration ist eine Beispielkonfiguration und sollte nicht in der Produktion verwendet werden, ohne die Einstellungen ordnungsgemäß zu überprüfen und Konfigurationen anzupassen.

>[!TIP]
>Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen für oder zu `Beta` `Preview` konfigurieren.

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

Zum Konfigurieren von MAU können Sie dieses Konfigurationsprofil über das von Ihrem Unternehmen verwendeten Verwaltungstool bereitstellen:
- Laden Sie dieses Konfigurationsprofil von JAMF hoch, und legen Sie die Einstellungsdomäne auf *com.microsoft.autoupdate2* fest.
- Laden Sie dieses Konfigurationsprofil von Intune hoch, und legen Sie den Namen des benutzerdefinierten Konfigurationsprofils auf *"com.microsoft.autoupdate2"* fest.

## <a name="resources"></a>Ressourcen

- [Msupdate-Referenz](/deployoffice/mac/update-office-for-mac-using-msupdate)
