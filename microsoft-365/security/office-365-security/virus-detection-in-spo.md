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
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die Benutzer hochladen, und verhindert, dass Benutzer die Dateien herunterladen oder synchronisieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a651d198f441c26525cbfb5d7406ae350db8b79e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908082"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)

Microsoft 365 verwendet ein gängiges Virenerkennungsmodul zum Scannen von Dateien, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen. Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams enthalten.

> [!IMPORTANT]
> Die integrierten Antivirenfunktionen sind eine Möglichkeit, Viren zu enthalten. Sie sind nicht als einzelner Schutzpunkt gegen Schadsoftware für Ihre Umgebung vorgesehen. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden für die Sicherung ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security roadmap](security-roadmap.md).

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Das Microsoft 365-Virenerkennungsmodul wird asynchron (unabhängig von Dateiuploads) in SharePoint Online ausgeführt. **Alle Dateien werden nicht automatisch gescannt.** Heuristiken bestimmen die zu scannenden Dateien. Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet. Im April 2018 wurde der Grenzwert von 25 MB für gescannte Dateien aufgehoben.

Dies geschieht:

1. Ein Benutzer lädt eine Datei nach SharePoint Online hoch.
2. SharePoint Online bestimmt im Rahmen seiner Virenscanprozesse später, ob die Datei die Kriterien für eine Überprüfung erfüllt.
3. Wenn die Datei die Kriterien für eine Überprüfung erfüllt, überprüft das Virenerkennungsmodul die Datei.
4. Wenn ein Virus in der gescannten Datei gefunden wird, legt das Virenmodul eine Eigenschaft für die Datei fest, die angibt, dass er infiziert ist.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über einen Browser von SharePoint Online herunterladen.

Dies geschieht:

1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.
2. Dem Benutzer wird eine Warnung angezeigt, dass ein Virus erkannt wurde. Standardmäßig hat der Benutzer die Möglichkeit, die Datei herunterzuladen und mithilfe der Antivirensoftware auf seinem eigenen Gerät zu löschen.

> [!NOTE]
>
> Administratoren können den *Parameter DisallowInfectedFileDownload* im [Cmdlet Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, auch im Warnungsfenster für Viren. Anweisungen finden Sie unter [Use SharePoint Online PowerShell to prevent users from download malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Sobald Sie den *Parameter DisallowInfectedFileDownload* aktivieren, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der #A0 versucht, eine infizierte Datei zu synchronisieren?

#A0 laden keine Dateien herunter, die Viren enthalten. Der Synchronisierungsclient zeigt eine Benachrichtigung an, dass die Datei nicht synchronisiert werden kann.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Erweiterte Funktionen mit Microsoft Defender für Office 365

Microsoft 365-Organisationen, die [Microsoft Defender für Office 365](office-365-atp.md) in ihrem Abonnement enthalten oder als #A0 erworben haben, können sichere Anlagen für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichte und Schutz aktivieren. Weitere Informationen finden Sie unter [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Verwandte Artikel

[Schutz vor Schadsoftware und Ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Weitere Informationen zum Virenschutz in SharePoint Online, OneDrive und Microsoft Teams finden Sie unter [Schützen](protect-against-threats.md) vor Bedrohungen und Aktivieren sicherer Anlagen für [SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).