---
title: Auswählen zwischen Basis Mobilität und Sicherheit und InTune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Grundlegende Mobilität und Sicherheit sind Teil der Microsoft 365-Pläne.
ms.openlocfilehash: d4595428dd2e2b14948b9f788720fcadcf9eb895
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336913"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Auswählen zwischen Basis Mobilität und Sicherheit und InTune

Microsoft InTune ist ein eigenständiges Produkt, das in bestimmten Plänen von Microsoft 365 enthalten ist, während die grundlegende Mobilitäts & Sicherheit Teil der Microsoft 365-Pläne ist. Beide sind in einer Vielzahl von Plänen enthalten, die in der folgenden Tabelle beschrieben werden.

|**Planen**|**Grundlegende Mobilität und Sicherheit**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365 Apps|Ja|Nein|
|Microsoft 365 Business Basic|Ja|Nein|
|Microsoft 365 Business Standard|Ja|Nein|
|Office 365 E1 |Ja|Nein|
|Office 365 E3 |Ja|Nein|
|Office 365 E5 |Ja|Nein|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365-erst-3 |Ja|Ja|
|Microsoft 365 Enterprise E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 Eductation a1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nein|Ja|
|Enterprise Mobility & Security E3 |Nein|Ja|
|Enterprise Mobility & Sicherheit E5 |Nein|Ja|

>[!NOTE]
>Sie können nicht mit der Verwendung von Basic Mobility and Security beginnen, wenn Sie bereits mit Microsoft InTune arbeiten.

## <a name="differences-in-capabilities"></a>Unterschiede bei den Funktionen

Mit Microsoft InTune und integrierter grundlegender Mobilität und Sicherheit können Sie mobile Geräte in Ihrer Organisation verwalten, es gibt jedoch wesentliche Unterschiede in der Funktion, die in der folgenden Tabelle beschrieben werden.

>[!NOTE]
>Sie können Benutzer und Ihre mobilen Geräte sowohl mit InTune als auch mit Basic Mobility and Security in derselben Microsoft 365 Business Standard-Organisation verwalten, indem Sie zuerst grundlegende Mobilität und Sicherheit einrichten und dann Microsoft InTune hinzufügen. Auf diese Weise können Sie auswählen, ob Sie die Geräte eines Benutzers mit grundlegender Mobilität und Sicherheit oder mit der funktionsreicheren InTune-Lösung verwalten. Im Modus bestimmt die Lizenzzuweisung, für welchen Dienst das Gerät registriert ist. Weisen Sie eine InTune-Lizenz zu, um die nur InTune-Funktionen zu aktivieren.

|**Funktionsbereich**|**Wesentliche Elemente des Features**|**Grundlegende Mobilität und Sicherheit**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Gerätetypen|Verschiedene Betriebssystemplattformen und Haupt Verwaltungsmodus-Varianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung Knox<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung Knox<br/>Mac OS<br/>iPad OS|
|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien wie PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen auf Android 9-und höher-Geräten. Ausführliche Informationen finden Sie unter [capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).|Ja|
|Bedingter Zugriff basierend auf der Geräte Konformität |Verhindern, dass nicht konforme Geräte auf Firmen-e-Mails und Daten aus der Cloud zugreifen. |-Wird in Windows 10 nicht unterstützt.<br/>– Beschränkung auf die Steuerung des Zugriffs auf Exchange Online, SharePoint Online und Outlook Services. |Nein|
|Gerätekonfiguration  |Konfigurieren von Geräteeinstellungen (z. b. Deaktivieren der Kamera) |Beschränkte Gruppe von Einstellungen.Ausführliche Informationen finden Sie unter [capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md). |Ja|
|Remote-Aktionen  |Senden von Befehlen an Geräte über das Internet. Beispielsweise können Sie Office-Daten aus dem Gerät eines Mitarbeiters entfernen, während personenbezogene Daten hinterlassen werden (zurückziehen). |Zurückziehen<br/>Wischen<br/>Löschen|-Autopilot-Reset (nur Windows)<br/>- [BitLocker-Schlüsselrotation](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Nur Windows)<br/>- [Löschen](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Aktivierung deaktivieren Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (nur IOS)<br/>- [Neuer Anfang](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Nur Windows)<br/>- [Vollständige Überprüfung](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Nur Windows 10)<br/>- [Gerät suchen](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (nur IOS)<br/>- [Verlorener Modus](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (nur IOS)<br/>- [Schnellüberprüfung](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(nur Windows 10)<br/>- [Remote Steuerung für Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Remote Sperre](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Gerät umbenennen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Kennwort zurücksetzen](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Neustart](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Nur Windows)<br/>- [Ruhestand](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Aktualisieren von Windows Defender Security Intelligence (nur Windows)<br/>-Windows 10-Pin-Reset (nur Windows)<br/>- [Zurücksetzung](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Senden benutzerdefinierter Benachrichtigungen](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, Ios, iPad OS)<br/>- [Gerät synchronisieren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|E-Mail-Profile  |Stellen Sie ein systemeigenes e-Mail-Profil auf dem Gerät. |Ja|Ja|
|WiFi-profile |Stellen Sie ein systemeigenes WiFi-Profil auf dem Gerät zur Verfügung. |Nein|Ja|
|VPN-profile |Stellen Sie ein systemeigenes VPN-Profil auf dem Gerät zur Verfügung. |Nein|Ja|
|MDM-Anwendungsverwaltung  |Stellen Sie Ihre internen Branchen-apps und apps-Stores für Benutzer bereit. |Nein|Ja|
|Schutz mobiler Anwendungen  |Ermöglichen Sie Ihren Benutzern den sicheren Zugriff auf Unternehmensinformationen mithilfe der bekannten Office Mobile-und Branchen-apps, während Sie die Sicherheit der Daten sicherstellen, indem Sie Aktionen wie "Kopieren", "Ausschneiden", "Einfügen" und "Speichern unter" nur auf apps verwalten, die für Unternehmensdaten genehmigt wurden. Funktioniert auch dann, wenn die Geräte nicht für MDM registriert sind. Siehe Schützen von App-Daten mithilfe von MAM-Richtlinien. |Nein|Ja|
|Verwalteter Browser  |Aktivieren Sie sicheres Browsen mit der Edge-app. |Nein|Ja|
|Zero Touch-Registrierungsprogramme |Registrieren Sie eine große Anzahl von unternehmenseigenen Geräten, während Sie die Benutzer Einrichtung vereinfachen. |Nein|Ja|
