---
title: Virenerkennung in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die von Benutzern hochgeladen werden, und verhindert, dass Benutzer die Dateien herunterladen oder synchronisieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653509"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Virenerkennung in SharePoint Online-, OneDrive-und Microsoft Teams

Microsoft 365 kann zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Viren in Dateien erkannt werden, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen. Dateien werden nach dem Hochladen möglicherweise auf Viren überprüft. Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.

> [!IMPORTANT]
> Diese Antivirus-Funktionen in SharePoint Online sind eine Möglichkeit, Viren einzudämmen. Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu bewerten und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Microsoft 365 verwendet ein allgemeines Viruserkennungsmodul. Das Modul wird in SharePoint Online asynchron ausgeführt, und einige Dateien werden nach dem Hochladen überprüft. Heuristiken werden verwendet, um zu bestimmen, welche Dateien gescannt werden. Wenn eine Datei gefunden wird, die einen Virus enthält, wird Sie gekennzeichnet, damit Sie nicht erneut heruntergeladen werden kann. Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.

Folgendes geschieht:

1. Ein Benutzer lädt eine Datei in SharePoint Online hoch.

2. SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.

3. Das Viruserkennungsmodul scannt die Datei.

4. Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über den Browser aus SharePoint Online herunterladen.

Folgendes geschieht:

1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.

2. Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde. Der Benutzer hat die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit ihrer eigenen Antivirus-Software zu säubern.

> [!NOTE]
>
> Sie können den Parameter *DisallowInfectedFileDownload* im Cmdlet [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer eine infizierte Datei herunterladen, selbst im Fenster Antivirus-Warnung.
>
> Beachten Sie auch, dass der Zugriff auf die erkannten/blockierten Dateien, sobald Sie den *DisallowInfectedFileDownload* -Parameter aktiviert haben, für Benutzer und Administratoren vollständig blockiert ist.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?

Unabhängig davon, ob Benutzer Dateien mit dem neuen OneDrive-synchronisierungsclient (OneDrive.exe) oder dem vorherigen OneDrive für Unternehmen-synchronisierungsclient (Groove.exe) synchronisieren, wenn eine Datei einen Virus enthält, wird Sie vom synchronisierungsclient nicht heruntergeladen. Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.

## <a name="extended-capabilities-with-office-365-atp"></a>Erweiterte Funktionen mit Office 365 ATP

Kunden, die Office 365 ATP für SharePoint, OneDrive und Microsoft Teams aktiviert haben, [aktivieren ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) können das Security & Compliance Center verwenden, um isolierte Dateien für AV-und ATP-Erkennungen zu verwalten. [Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Konfigurieren von SharePoint Online Antivirus finden Sie unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) und [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .


