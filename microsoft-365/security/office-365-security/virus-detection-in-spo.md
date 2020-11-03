---
title: Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams
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
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844236"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 verwendet ein allgemeines Viruserkennungsmodul zum Überprüfen von Dateien, die von Benutzern in SharePoint Online, OneDrive und Microsoft Teams hochgeladen werden. Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams umfassen.

> [!IMPORTANT]
> Die integrierten Antiviren-Funktionen sind eine Möglichkeit, Viren zu unterstützen. Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Das Microsoft 365-Viruserkennungsmodul wird in SharePoint Online asynchron ausgeführt. **Alle Dateien werden beim Hochladen nicht automatisch gescannt**. Heuristik legt fest, welche Dateien gescannt werden sollen. Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet, sodass Sie nicht erneut heruntergeladen werden kann. Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.

Folgendes geschieht:

1. Ein Benutzer lädt eine Datei in SharePoint Online hoch.
2. SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.
3. Das Viruserkennungsmodul scannt die Datei.
4. Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei infiziert ist, können Benutzer die Datei nicht mithilfe eines Browsers aus SharePoint Online herunterladen.

Folgendes geschieht:

1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.
2. Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde. Standardmäßig hat der Benutzer die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit der Antivirensoftware auf seinem eigenen Gerät zu säubern.

> [!NOTE]
>
> Administratoren können den Parameter *DisallowInfectedFileDownload* im Cmdlet [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, selbst im Fenster Antivirus-Warnung. Anweisungen finden Sie unter [use SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Sobald Sie den *DisallowInfectedFileDownload* -Parameter aktiviert haben, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?

OneDrive-Synchronisierungs Clients können keine Dateien herunterladen, die Viren enthalten. Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Erweiterte Funktionen mit Microsoft Defender für Office 365

Microsoft 365-Organisationen mit [Microsoft Defender für Office 365](office-365-atp.md) , die in Ihrem Abonnement enthalten sind oder als Add-on erworben wurden, können ATP für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichte und Schutz aktivieren. Weitere Informationen finden Sie unter [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Virenschutz in SharePoint Online, OneDrive und Microsoft Teams finden Sie unter [Protect Against Threats](protect-against-threats.md) und [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
