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
ms.openlocfilehash: 8724b3dccbdb5949190ceda4b804b9f1f2a5d4b2
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561495"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Auswählen zwischen Basis Mobilität und Sicherheit oder InTune

[Microsoft InTune](https://docs.microsoft.com/mem/intune/) ist ein eigenständiges Produkt, das in bestimmten Plänen von Microsoft 365 enthalten ist, während die grundlegende Mobilität und Sicherheit Teil der Microsoft 365-Pläne ist. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Verfügbarkeit von grundlegender Mobilität und Sicherheit und InTune
 
Sowohl grundlegende Mobilität und Sicherheit als auch InTune sind in einer Vielzahl von Plänen enthalten, die in der folgenden Tabelle beschrieben werden.

| Plan | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
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
|Microsoft 365 Education a1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nein|Ja|
|Enterprise Mobility & Security E3 |Nein|Ja|
|Enterprise Mobility & Sicherheit E5 |Nein|Ja|

>[!NOTE]
>Sie können nicht mit der Verwendung von Basic Mobility and Security beginnen, wenn Sie bereits mit Microsoft InTune arbeiten.

 Ausführliche Informationen finden Sie unter [Microsoft 365 und Office 365 Platform Service descriptions](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Unterschiede bei den Funktionen

Mit Microsoft InTune und integrierter grundlegender Mobilität und Sicherheit können Sie mobile Geräte in Ihrer Organisation verwalten, es gibt jedoch wesentliche Unterschiede in der Funktion, die in der folgenden Tabelle beschrieben werden.

>[!NOTE]
>Sie können Benutzer und Ihre mobilen Geräte sowohl mit InTune als auch mit Basic Mobility and Security in derselben Microsoft 365 Business Standard-Organisation verwalten *, indem Sie zuerst grundlegende Mobilität und Sicherheit einrichten und dann Microsoft InTune hinzufügen*. Auf diese Weise können Sie die grundlegende Mobilität und Sicherheit oder die mehr funktionsreiche InTune-Lösung auswählen. Weisen Sie eine InTune-Lizenz zum Aktivieren der InTune-Funktionen zu.

| Funktionsbereich | Wesentliche Elemente des Features | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Gerätetypen|Verwalten verschiedener Betriebssystemplattformen und Haupt Verwaltungsmodi-Varianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung Knox<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung Knox<br/>Mac OS, iPad OS|
|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien wie PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen auf Android 9-und höher-Geräten. Siehe [Details](capabilities.md). |Ja|
|Bedingter Zugriff basierend auf der Geräte Konformität |Verhindern, dass nicht konforme Geräte auf Firmen-e-Mails und Daten aus der Cloud zugreifen. |Wird in Windows 10 nicht unterstützt.<br/>Ist auf die Steuerung des Zugriffs auf Exchange Online, SharePoint Online und Outlook limitiert. |Ja |
|Gerätekonfiguration  |Konfigurieren von Geräteeinstellungen (beispielsweise Deaktivieren der Kamera)|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien wie PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen auf Android 9-und höher-Geräten. Siehe [Details](capabilities.md). |Ja|
 |Beschränkte Gruppe von Einstellungen. |Ja|
|E-Mail-Profile  |Stellen Sie ein systemeigenes e-Mail-Profil auf dem Gerät. |Ja|Ja|
|WiFi-profile |Stellen Sie ein systemeigenes WiFi-Profil auf dem Gerät zur Verfügung. |Nein|Ja|
|VPN-profile |Stellen Sie ein systemeigenes VPN-Profil auf dem Gerät zur Verfügung. |Nein|Ja|
|MDM-Anwendungsverwaltung |Stellen Sie Ihre internen Branchen-apps und apps-Stores für Benutzer bereit. |Nein|Ja|
|MAM |Stellen Sie sicher, dass Ihre Benutzer über die Office Mobile-und Branchen-apps sicher auf Unternehmensinformationen zugreifen können, indem Sie Aktionen wie "Kopieren", "Ausschneiden", "Einfügen" und "Speichern unter" nur auf die für Unternehmensdaten genehmigten apps beschränken. |Nein|Ja|
|Verwalteter Browser  |Aktivieren Sie sicheres Browsen mit der Edge-app. |Nein|Ja|
|Zero Touch-Registrierungsprogramme Autopilot) |Registrieren Sie eine große Anzahl von unternehmenseigenen Geräten, während Sie das Benutzer Setup vereinfachen. |Nein|Ja|
|||

Zusätzlich zu den in der vorstehenden Tabelle aufgeführten Features umfassen Basic Mobility and Security und InTune eine Reihe von Remote Aktionen, die Befehle an Geräte über das Internet senden. Beispielsweise können Sie Office-Daten aus dem Gerät eines Mitarbeiters entfernen, während persönliche Daten hinterlassen werden (zurückziehen), Office-Apps aus dem Gerät eines Mitarbeiters entfernen (Wischen) oder ein Gerät auf seine Werkseinstellungen zurücksetzen (vollständige Zurücksetzung). 

Zu den grundlegenden Mobilitäts-und Sicherheits Remote Aktionen gehören Ruhestand, wischen und vollständige Löschung. Weitere Informationen zu grundlegenden Mobilitäts-und Sicherheitsaktionen finden Sie unter [Features of Basic Mobility and Security](capabilities.md).

Mit InTune haben Sie die folgenden Aktionen:

-   Autopilot-Reset (nur Windows
-  [BitLocker-Schlüsselrotation](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Nur Windows)
-  [Verwenden von wischen, zurückziehen oder manuelles aufhoben der Registrierung für das Gerät](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Aktivierung deaktivieren Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (nur IOS)
-  [Neuer Anfang](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Nur Windows)
- [Vollständige Überprüfung](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Nur Windows 10)
- [Gerät suchen](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (nur IOS)
- [Verlorener Modus](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (nur IOS) – [Schnellüberprüfung](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(nur Windows 10)
- [Remote Steuerung für Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Remotesperre](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Gerät umbenennen](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Zurücksetzen des Code](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [Neustarts](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (nur Windows)
-  Aktualisieren von Windows Defender Security Intelligence (nur Windows)
-  Windows 10-Pin-Reset (nur Windows)
-  [Senden benutzerdefinierter Benachrichtigungen](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, Ios, iPad OS)
-  [Gerät synchronisieren](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Weitere Informationen zu InTune-Aktionen finden Sie in der [Dokumentation zu Microsoft InTune](https://docs.microsoft.com/mem/intune/).
