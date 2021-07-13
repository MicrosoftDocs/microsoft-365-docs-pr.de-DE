---
title: Wählen Zwischen grundlegender Mobilität und Sicherheit und Intune
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
- AdminTemplateSet
search.appverid:
- MET150
description: Grundlegende Mobilität und Sicherheit sind Teil der Microsoft 365 Pläne.
ms.openlocfilehash: 3404d2aeecd047fecec573bf1d60407ad3659efe
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393295"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Wählen Zwischen Basic Mobility und Security oder Intune

[Microsoft Intune](/mem/intune/) ist ein eigenständiges Produkt, das in bestimmten Microsoft 365 Plänen enthalten ist, während Basic Mobility and Security Teil der Microsoft 365 Pläne ist.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Verfügbarkeit von Grundlegender Mobilität und Sicherheit und Intune

Sowohl Basic Mobility als auch Security und Intune sind in einer Vielzahl von Plänen enthalten, die in der folgenden Tabelle beschrieben werden.

| Plan | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|Ja|Nein|
|Microsoft 365 Business Basic|Ja|Nein|
|Microsoft 365 Business Standard|Ja|Nein|
|Office 365 E1 |Ja|Nein|
|Office 365 E3 |Ja|Nein|
|Office 365 E5 |Ja|Nein|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 Firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 Education A1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nein|Ja|
|Enterprise Mobility & Security E3 |Nein|Ja|
|Enterprise Mobility + Security (EMS) E5 |Nein|Ja|

> [!NOTE]
> Sie können nicht mit der Verwendung von Basic Mobility and Security beginnen, wenn Sie bereits Microsoft Intune verwenden.

 Ausführliche Informationen finden Sie unter [Microsoft 365 und Office 365 Plattformdienstbeschreibungen.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)

## <a name="differences-in-capabilities"></a>Unterschiede bei den Funktionen

Microsoft Intune und integrierte Grundlegende Mobilität und Sicherheit bieten Ihnen beide die Möglichkeit, mobile Geräte in Ihrer Organisation zu verwalten, aber es gibt wichtige Unterschiede bei der Funktionalität, die in der folgenden Tabelle beschrieben werden.

> [!NOTE]
> Sie können Benutzer und ihre mobilen Geräte mit Intune und Basic Mobility and Security in derselben Microsoft 365 Business Standard Organisation *verwalten, indem Sie zuerst "Basic Mobility and Security" einrichten und dann Microsoft Intune hinzufügen.* Auf diese Weise können Sie grundlegende Mobilität und Sicherheit oder die funktionsreichere Intune-Lösung auswählen. Weisen Sie eine Intune-Lizenz zu, um die Intune-Features zu aktivieren.

| Funktionsbereich | Wesentliche Elemente des Features | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Gerätetypen|Verwalten verschiedener Betriebssystemplattformen und hauptverwaltungsmodusvarianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen für Android 9 und neuere Geräte. Details finden Sie [unter](capabilities.md). |Ja|
|Bedingter Zugriff basierend auf gerätekonformem Zugriff |Verhindern, dass nicht konforme Geräte auf Unternehmens-E-Mails und -Daten aus der Cloud zugreifen. |Wird für Windows 10 nicht unterstützt.<br/>Beschränkt auf die Steuerung des Zugriffs auf Exchange Online, SharePoint Online und Outlook. |Ja |
|Gerätekonfiguration  |Konfigurieren von Geräteeinstellungen (z. B. Deaktivieren der Kamera)|Begrenzter Satz von Einstellungen.|Ja|
|Gerätekompatibilität  |Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen für Android 9 und neuere Geräte. Details finden Sie [unter](capabilities.md). |Ja|
|E-Mail-Profile  |Stellen Sie ein systemeigenes E-Mail-Profil auf dem Gerät bereit. |Ja|Ja|
|WLAN-Profile |Stellen Sie ein systemeigenes WLAN-Profil auf dem Gerät bereit. |Nein|Ja|
|VPN-Profile |Stellen Sie ein systemeigenes VPN-Profil auf dem Gerät bereit. |Nein|Ja|
|Mobile Anwendungsverwaltung (Mobile Application Management)  |Stellen Sie Ihre internen Branchen-Apps und aus App-Stores für Benutzer bereit. |Nein|Ja|
|Schutz mobiler Anwendungen  |Ermöglichen Sie Ihren Benutzern den sicheren Zugriff auf Unternehmensinformationen mithilfe der Office mobilen und branchenspezifischen Apps, die sie kennen, und stellen Sie gleichzeitig die Sicherheit von Daten sicher, indem Sie Aktionen wie Kopieren, Ausschneiden, Einfügen und Speichern unter auf diejenigen Apps beschränken, die für Unternehmensdaten genehmigt wurden. Funktioniert auch, wenn die Geräte nicht für Basic Mobility and Security registriert sind. Siehe "Schützen von App-Daten mithilfe von MAM-Richtlinien". |Nein|Ja|
|Verwalteter Browser  |Aktivieren Sie sichereres Webbrowsen mithilfe der Edge-App. |Nein|Ja|
|Zero Touch-Registrierungsprogramme (AutoPilot) |Registrieren Sie eine große Anzahl unternehmenseigener Geräte, während die Benutzereinrichtung vereinfacht wird. |Nein|Ja|
|||

Zusätzlich zu den in der vorherigen Tabelle aufgeführten Features umfassen basic Mobility and Security und Intune eine Reihe von Remoteaktionen, die Befehle über das Internet an Geräte senden. Sie können z. B. Office Daten aus dem Gerät eines Mitarbeiters entfernen, während Sie personenbezogene Daten beibehalten (zurückziehen), Office Apps vom Gerät eines Mitarbeiters entfernen (Zurücksetzen) oder ein Gerät auf die Werkseinstellungen zurücksetzen (vollständige Zurücksetzung).

Zu den grundlegenden Remoteaktionen für Mobilität und Sicherheit gehören "Ausmustern", "Zurücksetzen" und "Vollständiges Zurücksetzen". Weitere Informationen zu grundlegenden Mobilitäts- und Sicherheitsaktionen finden Sie unter ["Grundlegende Mobilität und Sicherheit".](capabilities.md)

Mit Intune haben Sie die folgenden Aktionen:

-   Autopilot-Zurücksetzung (nur Windows
-  [Bitlocker-Schlüsselrotation](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (nur Windows)
-  [Verwenden des Zurücksetzens, Zurückziehens oder manuellen Aufhebens der Registrierung des Geräts](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Deaktivieren der Aktivierungs-loc](/mem/intune/remote-actions/device-activation-lock-disable)   (nur iOS)
-  [Neuanfang](/mem/intune/remote-actions/device-fresh-start)   (nur Windows)
- [Vollständiger Scan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (nur Windows 10)
- [Gerät suchen](/mem/intune/remote-actions/device-locate)   (nur iOS)
- [Modus "Verloren"](/mem/intune/remote-actions/device-lost-mode)   (nur iOS) – [Schnellscan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(nur Windows 10)
- [Remotesteuerung für Android](/mem/intune/remote-actions/teamviewer-support)
- [Remotesperre](/mem/intune/remote-actions/device-remote-lock)
- [Umbenennen des Geräts](/mem/intune/remote-actions/device-rename)
-  Neustart der [Kennung zurücksetzen](/mem/intune/remote-actions/device-passcode-reset) [](/mem/intune/remote-actions/device-restart)   (nur Windows)
-  Aktualisieren Windows Defender Security Intelligence (nur Windows)
-  Windows 10 Zurücksetzen der PIN (nur Windows)
-  [Senden von benutzerdefinierten Benachrichtigungen](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad BETRIEBSSYSTEM)
-  [Synchronisieren des Geräts](/mem/intune/remote-actions/device-sync)

Weitere Informationen zu Intune-Aktionen finden Sie [in Microsoft Intune Dokumentation.](/mem/intune/)