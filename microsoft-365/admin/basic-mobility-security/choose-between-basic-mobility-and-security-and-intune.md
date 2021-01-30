---
title: Wählen Sie zwischen Basic Mobility and Security und Intune
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
ms.openlocfilehash: ec3ffa8879bf14ab3116bbbbf5cf2a1a3fd7c6e6
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053801"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Wählen Sie zwischen Basic Mobility and Security oder Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) ist ein eigenständiges Produkt, das in bestimmten Microsoft 365-Plänen enthalten ist, während Basic Mobility and Security Teil der Microsoft 365-Pläne ist.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Verfügbarkeit von Basic Mobility and Security und Intune

Sowohl Basic Mobility and Security als auch Intune sind in einer Vielzahl von Plänen enthalten, wie in der folgenden Tabelle beschrieben.

| Plan | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|Ja|Nein|
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
|Enterprise Mobility & Security E5 |Nein|Ja|

>[!NOTE]
>Sie können mit der Verwendung von Basic Mobility and Security nicht beginnen, wenn Sie bereits Microsoft Intune verwenden.

 Ausführliche Informationen finden Sie unter Beschreibungen des [Microsoft 365- und Office 365-Plattformdiensts.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Unterschiede in den Funktionen

Microsoft Intune und integrierte Basic Mobility and Security bieten Ihnen beide die Möglichkeit, mobile Geräte in Ihrer Organisation zu verwalten, es gibt jedoch wesentliche Unterschiede in der Funktion, die in der folgenden Tabelle beschrieben werden.

>[!NOTE]
>Sie können Benutzer und ihre mobilen Geräte sowohl mit Intune als auch mit Basic Mobility and Security in derselben Microsoft 365 Business Standard Organisation *verwalten,* indem Sie zunächst Basic Mobility and Security einrichten und dann Microsoft Intune hinzufügen. Auf diese Weise können Sie "Basic Mobility and Security" oder die funktionsreichere Intune-Lösung auswählen. Weisen Sie eine Lizenz für Intune zu, um die Features von Intune zu aktivieren.

| Funktionsbereich | Wesentliche Elemente des Features | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Gerätetypen|Verwalten verschiedener Betriebssystemplattformen und hauptverwaltungsmodusvarianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Jailbreakerkennung. |Einschränkungen für Android 9- und höher-Geräte. Weitere [Informationen finden Sie unter](capabilities.md). |Ja|
|Bedingter Zugriff basierend auf Gerätekonformität |Verhindern, dass nicht kompatible Geräte auf Unternehmens-E-Mails und -Daten aus der Cloud zugreifen. |Wird unter Windows 10 nicht unterstützt.<br/>Beschränkt auf die Steuerung des Zugriffs auf Exchange Online, SharePoint Online und Outlook. |Ja |
|Gerätekonfiguration  |Konfigurieren von Geräteeinstellungen (z. B. Deaktivieren der Kamera)|Beschränkter Satz von Einstellungen.|Ja|
|Gerätekompatibilität  |Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Jailbreakerkennung. |Einschränkungen auf Android 9- und höher-Geräten. Weitere [Informationen finden Sie unter](capabilities.md). |Ja|
|E-Mail-Profile  |Bereitstellen eines systemeigenen E-Mail-Profils auf dem Gerät. |Ja|Ja|
|WLAN-Profile |Bereitstellen eines systemeigenen WLAN-Profils auf dem Gerät. |Nein|Ja|
|VPN-Profile |Bereitstellen eines nativen VPN-Profils auf dem Gerät. |Nein|Ja|
|Grundlegende Verwaltung von Anwendungen für Mobilität und Sicherheit  |Stellen Sie Ihre internen Line-of-Business-Apps und Aus-App-Stores für Benutzer zur Verfügung. |Nein|Ja|
|Schutz mobiler Anwendungen  |Ermöglichen Sie Ihren Benutzern den sicheren Zugriff auf Unternehmensinformationen mithilfe der office-mobilen und Line-of-Business-Apps, die sie kennen, und gleichzeitig die Sicherheit von Daten zu gewährleisten, indem Sie Aktionen wie Kopieren, Ausschneiden, Einfügen und Speichern auf diejenigen Apps beschränken, die für Unternehmensdaten genehmigt wurden. Funktioniert auch dann, wenn die Geräte nicht für Basic Mobility and Security registriert sind. Siehe "Schützen von App-Daten mithilfe von MAM-Richtlinien". |Nein|Ja|
|Verwalteter Browser  |Aktivieren Sie sichereres Surfen im Web mithilfe der Edge-App. |Nein|Ja|
|Zero touch enrollment programs Autopilot) |Registrieren Sie eine große Anzahl unternehmenseigener Geräte und vereinfachen Sie gleichzeitig die Benutzereinrichtung. |Nein|Ja|
|||

Zusätzlich zu den in der vorstehenden Tabelle aufgeführten Funktionen enthalten Basic Mobility and Security und Intune eine Reihe von Remoteaktionen, die Befehle über das Internet an Geräte senden. Sie können z. B. die Daten eines Mitarbeiters vom Gerät eines Mitarbeiters entfernen, während sie personenbezogene Daten erhalten (zurückziehen), office-Apps vom Gerät eines Mitarbeiters entfernen (Zurücksetzen) oder ein Gerät auf die Werkseinstellungen zurücksetzen (vollständige Zurücksetzung). 

Zu den grundlegenden Remoteaktionen für Mobilität und Sicherheit gehören "Zurückziehen", "Zurückziehen" und "Vollständige Zurückziehen". Weitere Informationen zu grundlegenden Mobilitäts- und Sicherheitsaktionen finden Sie unter ["Grundlegende Mobilität und Sicherheit".](capabilities.md)

Mit Intune haben Sie die folgenden Aktionen:

-   Zurücksetzen von Autopilot (nur Windows)
-  [Drehung von Bitlocker-Schlüsseln](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (nur Windows)
-  [Verwenden des Zurückziehens, Zurückziehens oder manuellen Entfernens der Registrierung des Geräts](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Aktivierungsort deaktivieren](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (nur iOS)
-  [Neuanfang](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (nur Windows)
- [Vollständiger Scan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (nur Windows 10)
- [Gerät suchen](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (nur iOS)
- [Modus "Verloren"](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (nur iOS) – [Schnellscan](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(nur Windows 10)
- [Remotesteuerung für Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Remotesperre](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Gerät umbenennen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Zurücksetzen des Kennungsneustarts](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (nur Windows)
-  Aktualisieren Windows Defender Security Intelligence (nur Windows)
-  Zurücksetzen der Windows 10-PIN (nur Windows)
-  [Senden von benutzerdefinierten Benachrichtigungen](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Gerät synchronisieren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Weitere Informationen zu Intune-Aktionen finden Sie in der [Microsoft Intune-Dokumentation.](https://docs.microsoft.com/mem/intune/)
