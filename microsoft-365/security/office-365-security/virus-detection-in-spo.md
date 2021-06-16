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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die Benutzer hochladen, und wie Benutzer die Dateien nicht herunterladen oder synchronisieren können.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ab11d4c1e2a064ad0717e6619f72a38b0cbc831
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932830"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)

Microsoft 365 verwendet ein gängiges Virenerkennungsmodul zum Scannen von Dateien, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen. Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams enthalten.

> [!IMPORTANT]
> Die integrierten Antivirenfunktionen stellen eine Möglichkeit dar, Viren einzudämmen. Sie sind nicht als einzelner Schutz gegen Schadsoftware für Ihre Umgebung vorgesehen. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden zum Sichern ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie in der [Sicherheits-Roadmap.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Das Microsoft 365 Virenerkennungsmodul wird asynchron (unabhängig von Dateiuploads) in SharePoint Online ausgeführt. **Alle Dateien werden nicht automatisch gescannt.** Heuristiken bestimmen die zu scannenden Dateien. Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet. Im April 2018 wurde der Grenzwert von 25 MB für gescannte Dateien entfernt.

Dies geschieht:

1. Ein Benutzer lädt eine Datei in SharePoint Online hoch.
2. SharePoint Online ermittelt im Rahmen der Virenüberprüfung später, ob die Datei die Kriterien für eine Überprüfung erfüllt.
3. Wenn die Datei die Kriterien für eine Überprüfung erfüllt, scannt das Virenerkennungsmodul die Datei.
4. Wenn in der gescannten Datei ein Virus gefunden wird, legt das Virenmodul eine Eigenschaft für die Datei fest, die angibt, dass sie infiziert ist.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über SharePoint Online mithilfe eines Browsers herunterladen.

Dies geschieht:

1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.
2. Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde. Standardmäßig erhält der Benutzer die Möglichkeit, die Datei herunterzuladen und zu versuchen, sie mithilfe der Antivirensoftware auf ihrem eigenen Gerät zu bereinigen.

> [!NOTE]
>
> Administratoren können den *Parameter DisallowInfectedFileDownload* im [Cmdlet "Set-SPOTenant"](/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online-PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, auch im Fenster mit Virenwarnungen. Anweisungen finden Sie unter [Verwenden von SharePoint Online-PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Sobald Sie den *Parameter DisallowInfectedFileDownload* aktivieren, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der OneDrive-Synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?

Wenn eine schädliche Datei in OneDrive hochgeladen wird, wird sie mit dem lokalen Computer synchronisiert, bevor sie als Schadsoftware gekennzeichnet wird. Nachdem sie als Schadsoftware gekennzeichnet wurde, kann der Benutzer die synchronisierte Datei nicht mehr auf dem lokalen Computer öffnen.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Erweiterte Funktionen mit Microsoft Defender für Office 365

Microsoft 365 Organisationen, die [Microsoft Defender für Office 365](defender-for-office-365.md) in ihrem Abonnement enthalten oder als Add-On erworben haben, können sichere Anlagen für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichterstellung und Schutz aktivieren. Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Verwandte Artikel

[Schutz vor Schadsoftware und Ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Weitere Informationen zu Virenschutz in SharePoint Online- OneDrive und Microsoft Teams finden Sie unter ["Schutz vor Bedrohungen"](protect-against-threats.md) und [Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)
