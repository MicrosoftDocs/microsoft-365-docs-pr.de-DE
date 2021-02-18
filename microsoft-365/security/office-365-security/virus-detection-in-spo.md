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
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286501"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)

Microsoft 365 verwendet ein gängiges Virenerkennungsmodul zum Scannen von Dateien, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen. Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams umfassen.

> [!IMPORTANT]
> Die integrierten Antivirenfunktionen sind eine Möglichkeit, virenschutz zu unterstützen. Sie sind nicht als ein einzelner Schutzpunkt gegen Schadsoftware für Ihre Umgebung vorgesehen. Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden zum Schutz ihrer Unternehmensinfrastruktur anzuwenden. Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter ["Sicherheits-Roadmap".](security-roadmap.md)

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?

Das Microsoft 365-Virenerkennungsmodul wird asynchron in SharePoint Online ausgeführt. **Alle Dateien werden beim Hochladen nicht automatisch überprüft.** Heuristiken bestimmen die zu scannenden Dateien. Wenn festgestellt wird, dass eine Datei einen Virus enthält, wird die Datei gekennzeichnet, sodass sie nicht erneut heruntergeladen werden kann. Im April 2018 wurde der Grenzwert von 25 MB für gescannte Dateien entfernt.

Dies geschieht:

1. Ein Benutzer lädt eine Datei in SharePoint Online hoch.
2. SharePoint Online bestimmt, ob die Datei die Kriterien für eine Überprüfung erfüllt.
3. Das Virenerkennungsmodul überprüft die Datei.
4. Wenn ein Virus gefunden wird, legt das Virenmodul eine Eigenschaft für die Datei fest, die angibt, dass er infiziert ist.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?

Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über einen Browser aus SharePoint Online herunterladen.

Dies geschieht:

1. Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.
2. Dem Benutzer wird eine Warnung angezeigt, dass ein Virus erkannt wurde. Standardmäßig kann der Benutzer die Datei herunterladen und versuchen, sie mithilfe der Antivirensoftware auf ihrem eigenen Gerät zu bereinigen.

> [!NOTE]
>
> Administratoren können den Parameter *"DisallowInfectedFileDownload"* für das [Cmdlet "Set-SPOTenant"](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, auch im Fenster mit der Virenschutzwarnung. Anweisungen finden Sie unter [Verwenden von SharePoint Online PowerShell,](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)um zu verhindern, dass Benutzer schädliche Dateien herunterladen.
>
> Sobald Sie den Parameter *"DisallowInfectedFileDownload"* aktivieren, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Was geschieht, wenn der #A0 versucht, eine infizierte Datei zu synchronisieren?

#A0 laden keine Dateien herunter, die Viren enthalten. Der Synchronisierungsclient zeigt eine Benachrichtigung an, dass die Datei nicht synchronisiert werden kann.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Erweiterte Funktionen mit Microsoft Defender für Office 365

Microsoft 365-Organisationen, in denen [Microsoft Defender für Office 365](office-365-atp.md) in ihrem Abonnement enthalten ist oder die als #A0 erworben wurden, können sichere Anlagen für SharePoint, OneDrive und Microsoft Teams für verbesserte Berichterstellung und besseren Schutz aktivieren. Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Verwandte Artikel

[Schutz vor Schadsoftware und Ransomware in Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Weitere Informationen zu Virenschutz in SharePoint Online, OneDrive [](protect-against-threats.md) und Microsoft Teams finden Sie unter "Schutz vor Bedrohungen und Aktivieren sicherer Anlagen für [SharePoint, OneDrive und Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)
