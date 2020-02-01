---
title: Virenerkennung in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: Office 365 können zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Sie Viren in Dateien erkennen, die von Benutzern in SharePoint Online hochgeladen werden. Dateien werden nach dem Hochladen auf Viren überprüft. Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.
ms.openlocfilehash: 1a41c5bb00e7169878206be2db076af0b0745e30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598002"
---
# <a name="virus-detection-in-sharepoint-online"></a>Virenerkennung in SharePoint Online

Office 365 können zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Sie Viren in Dateien erkennen, die von Benutzern in SharePoint Online hochgeladen werden. Dateien werden nach dem Hochladen möglicherweise auf Viren überprüft. Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.
  
> [!IMPORTANT]
> Diese Antivirus-Funktionen in SharePoint Online sind eine Möglichkeit, Viren einzudämmen. Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu bewerten und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md). 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Office 365 verwendet ein allgemeines Viruserkennungsmodul. Das Modul wird in SharePoint Online asynchron ausgeführt, und einige Dateien werden nach dem Hochladen überprüft. Heuristiken werden verwendet, um zu bestimmen, welche Dateien gescannt werden. Wenn eine Datei gefunden wird, die einen Virus enthält, wird Sie gekennzeichnet, damit Sie nicht erneut heruntergeladen werden kann. Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.
  
Folgendes geschieht:
  
1. Ein Benutzer lädt eine Datei in SharePoint Online hoch.

2. SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.

3. Das Viruserkennungsmodul scannt die Datei.
    
4. Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei mit einem Virus infiziert ist, können Benutzer die Datei nicht über den Browser aus SharePoint Online herunterladen.
  
Folgendes geschieht:
  
1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.
    
2. Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde. Der Benutzer erhält die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit ihrer eigenen Viren Software zu säubern.

> [!NOTE]
> Sie können das Cmdlet "SPOTenant" mit dem Parameter " **DisallowInfectedFileDownload** " verwenden, um Benutzern das Herunterladen einer erkannten Datei zu ermöglichen, selbst im Fenster "Antivirus-Warnung". Siehe [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?

Unabhängig davon, ob Benutzer Dateien mit dem neuen OneDrive-synchronisierungsclient (OneDrive. exe) oder dem vorherigen OneDrive für Unternehmen synchronisierungsclient (Groove. exe) synchronisieren, wenn eine Datei einen Virus enthält, wird Sie vom synchronisierungsclient nicht heruntergeladen. Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.
  

