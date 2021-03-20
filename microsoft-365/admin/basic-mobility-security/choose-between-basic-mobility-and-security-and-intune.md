---
title: Wählen Sie zwischen Basic Mobility and Security und Intune aus.
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
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904264"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Wählen Sie zwischen Basic Mobility and Security oder Intune aus.

[Microsoft Intune](/mem/intune/) ist ein eigenständiges Produkt, das in bestimmten Microsoft 365-Plänen enthalten ist, während Basic Mobility and Security Teil der Microsoft 365-Pläne ist.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Verfügbarkeit von Basic Mobility and Security und Intune

Sowohl Basic Mobility als auch Security und Intune sind in einer Vielzahl von Plänen enthalten, die in der folgenden Tabelle beschrieben sind.

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
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nein|Ja|
|Enterprise Mobility & Security E3 |Nein|Ja|
|Enterprise Mobility + Security (EMS) E5 |Nein|Ja|

>[!NOTE]
>Sie können mit der Verwendung von Basic Mobility and Security nicht beginnen, wenn Sie bereits Microsoft Intune verwenden.

 Ausführliche Informationen finden Sie unter [Microsoft 365- und Office 365-Plattformdienstbeschreibungen](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Unterschiede bei den Funktionen

Microsoft Intune und integrierte Grundlegende Mobilität und Sicherheit bieten Ihnen beide die Möglichkeit, mobile Geräte in Ihrer Organisation zu verwalten, es gibt jedoch wesentliche Unterschiede in der Funktion, die in der folgenden Tabelle beschrieben werden.

>[!NOTE]
>Sie können Benutzer und ihre mobilen Geräte sowohl mithilfe von Intune als auch mit Basic Mobility and Security in derselben Microsoft 365 Business Standard-Organisation verwalten, indem Sie zunächst Grundlegende Mobilität und Sicherheit einrichten und *dann Microsoft Intune hinzufügen.* Auf diese Weise können Sie grundlegende Mobilität und Sicherheit oder die funktionsreichere Intune-Lösung auswählen. Weisen Sie eine Intune-Lizenz zu, um die Intune-Features zu aktivieren.

| Funktionsbereich | Wesentliche Elemente des Features | Grundlegende Mobilität und Sicherheit | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Gerätetypen|Verwalten verschiedener Betriebssystemplattformen und hauptverwaltungsmodusvarianten. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Gerätekompatibilität|Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen auf Android 9- und höher-Geräten. Weitere [Informationen finden Sie unter](capabilities.md)Details . |Ja|
|Bedingter Zugriff basierend auf der Gerätekonformität |Verhindern, dass nicht kompatible Geräte auf Unternehmens-E-Mails und -Daten aus der Cloud zugreifen. |Wird unter Windows 10 nicht unterstützt.<br/>Beschränkt auf die Steuerung des Zugriffs auf Exchange Online, SharePoint Online und Outlook. |Ja |
|Gerätekonfiguration  |Konfigurieren von Geräteeinstellungen (z. B. Deaktivieren der Kamera)|Eingeschränkter Satz von Einstellungen.|Ja|
|Gerätekompatibilität  |Festlegen und Verwalten von Sicherheitsrichtlinien, z. B. PIN-Sperre auf Geräteebene und Erkennung von Jailbreaks. |Einschränkungen auf Android 9- und höher-Geräten. Weitere [Informationen finden Sie unter](capabilities.md)Details . |Ja|
|E-Mail-Profile  |Bereitstellen eines systemeigenen E-Mail-Profils auf dem Gerät. |Ja|Ja|
|WLAN-Profile |Bereitstellen eines systemeigenen WLAN-Profils auf dem Gerät. |Nein|Ja|
|VPN-Profile |Bereitstellen eines systemeigenen VPN-Profils auf dem Gerät. |Nein|Ja|
|Mobile Anwendungsverwaltung (Mobile Application Management)  |Stellen Sie Ihre internen Line-of-Business-Apps und apps-Stores für Benutzer zur Verfügung. |Nein|Ja|
|Schutz mobiler Anwendungen  |Ermöglichen Sie Ihren Benutzern den sicheren Zugriff auf Unternehmensinformationen mithilfe der mobilen Und Line-of-Business-Apps von Office, die sie kennen, und gleichzeitig die Sicherheit von Daten zu gewährleisten, indem Sie Aktionen wie Kopieren, Ausschneiden, Einfügen und Speichern unter auf die apps beschränken, die für Unternehmensdaten genehmigt wurden. Funktioniert auch dann, wenn die Geräte nicht für Basic Mobility and Security registriert sind. Weitere Informationen finden Sie unter Schützen von App-Daten mithilfe von MAM-Richtlinien. |Nein|Ja|
|Verwalteter Browser  |Aktivieren Sie sichereres Browsen im Web mithilfe der Edge-App. |Nein|Ja|
|Zero Touch Enrollment Programs (AutoPilot) |Registrieren Sie eine große Anzahl von Unternehmensgeräten, während die Benutzereinrichtung vereinfacht wird. |Nein|Ja|
|||

Neben den in der vorstehenden Tabelle aufgeführten Features enthalten Basic Mobility and Security und Intune beide eine Reihe von Remoteaktionen, die Befehle über das Internet an Geräte senden. Sie können z. B. Office-Daten vom Gerät eines Mitarbeiters entfernen, während personenbezogene Daten gespeichert werden (zurückziehen), Office-Apps vom Gerät eines Mitarbeiters entfernen (Zurücksetzen) oder ein Gerät auf die Werkseinstellungen zurücksetzen (vollständiges Zurücksetzen). 

Grundlegende Mobilitäts- und Sicherheits-Remoteaktionen umfassen das Zurückziehen, Löschen und vollständiges Löschen. Weitere Informationen zu grundlegenden Mobilitäts- und Sicherheitsaktionen finden Sie [unter Funktionen von Basic Mobility and Security](capabilities.md).

Mit Intune haben Sie die folgenden Aktionen:

-   Zurücksetzen des Autopiloten (nur Windows)
-  [Bitlocker-Schlüsseldrehung](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (nur Windows)
-  [Verwenden des Wischens, Zurückziehens oder manuellen Entrollens des Geräts](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Aktivierungsort deaktivieren](/mem/intune/remote-actions/device-activation-lock-disable)   (nur iOS)
-  [Neuanfang](/mem/intune/remote-actions/device-fresh-start)   (nur Windows)
- [Vollständiger Scan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (nur Windows 10)
- [Gerät suchen](/mem/intune/remote-actions/device-locate)   (nur iOS)
- [Modus "Verloren"](/mem/intune/remote-actions/device-lost-mode)   (nur iOS)- [Schnellscan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(nur Windows 10)
- [Remotesteuerung für Android](/mem/intune/remote-actions/teamviewer-support)
- [Remotesperre](/mem/intune/remote-actions/device-remote-lock)
- [Gerät umbenennen](/mem/intune/remote-actions/device-rename)
-  Zurücksetzen des [Kennungsneustarts](/mem/intune/remote-actions/device-restart) [](/mem/intune/remote-actions/device-passcode-reset)   (nur Windows)
-  Update Windows Defender Security Intelligence (nur Windows)
-  Zurücksetzen der Windows 10-PIN (nur Windows)
-  [Senden benutzerdefinierter Benachrichtigungen](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Synchronisieren des Geräts](/mem/intune/remote-actions/device-sync)

Weitere Informationen zu Intune-Aktionen finden Sie in [der Microsoft Intune-Dokumentation](/mem/intune/).