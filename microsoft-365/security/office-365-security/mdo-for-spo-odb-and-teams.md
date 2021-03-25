---
title: Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie mehr über Microsoft Defender für Office 365 für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205534"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams in [Microsoft Defender für Office 365](whats-new-in-defender-for-office-365.md) bietet eine zusätzliche Schutzebene für Dateien, die bereits beim Hochladen vom allgemeinen Virenerkennungsmodul in Microsoft [365](virus-detection-in-spo.md)überprüft wurden. Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams helfen beim Erkennen und Blockieren vorhandener Dateien, die in Teamwebsites und Dokumentbibliotheken als schädlich identifiziert werden.

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind standardmäßig nicht aktiviert. Informationen zum Aktivieren finden Sie [unter Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funktionsweise sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams

Wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind und eine Datei als bösartig identifiziert wird, wird die Datei mithilfe der direkten Integration in die Dateispeicher gesperrt. Die folgende Abbildung zeigt ein Beispiel für eine in einer Bibliothek erkannten böswilligen Datei.

![Dateien in OneDrive for Business, bei der eine als schädlich erkannt wurde](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in Web-, Mobile- oder Desktopanwendungen aufgeführt ist, können Benutzer die Datei nicht öffnen, kopieren, verschieben oder freigeben. Sie können die blockierte Datei jedoch löschen.

Im Folgenden finden Sie ein Beispiel dafür, wie eine blockierte Datei auf einem mobilen Gerät aussieht:

![Löschen einer blockierten Datei aus OneDrive for Business aus der mobilen OneDrive-App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standardmäßig können Benutzer eine blockierte Datei herunterladen. So sieht das Herunterladen einer blockierten Datei auf einem mobilen Gerät aus:

![Herunterladen einer blockierten Datei in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-Administratoren können verhindern, dass Benutzer schädliche Dateien herunterladen. Anweisungen finden Sie unter [Use SharePoint Online PowerShell to prevent users from download malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Weitere Informationen zur Benutzeroberfläche, wenn eine Datei als schädlich erkannt wurde, finden Sie unter Was tun, wenn eine schädliche Datei [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)oder Microsoft Teams gefunden wird.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Anzeigen von Informationen zu schädlichen Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt wurden

Dateien, die von Microsoft Defender für Office 365 als bösartig identifiziert werden, werden in Berichten für [Microsoft Defender für Office 365](view-reports-for-mdo.md) und im Explorer (und Echtzeiterkennungen) [angezeigt.](threat-explorer.md)

Ab Mai 2018, wenn eine Datei von Microsoft Defender für Office 365 als schädlich identifiziert wird, ist die Datei auch in Quarantäne verfügbar. Weitere Informationen finden Sie unter [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Beachten Sie diese Punkte

- Defender for Office 365 scannt nicht jede einzelne Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams. Es handelt sich hierbei um ein beabsichtigtes Verhalten. Dateien werden asynchron überprüft. Der Prozess verwendet Freigabe- und Gastaktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungssignalen, um schädliche Dateien zu identifizieren.

- Stellen Sie sicher, dass Ihre SharePoint-Websites für die Verwendung der modernen [Benutzung konfiguriert sind.](/sharepoint/guide-to-sharepoint-modern-experience) Defender for Office 365-Schutz gilt unabhängig davon, ob die moderne Oder die klassische Ansicht verwendet wird. Visuelle Indikatoren, dass eine Datei blockiert wird, sind jedoch nur in der modernen Benutzererfahrung verfügbar.

- Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams ist Teil der gesamten Strategie zum Schutz vor Bedrohungen In Ihrer Organisation, die Antispam- und Anschmungsschutz in Exchange Online Protection (EOP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 umfasst. Weitere Informationen finden Sie unter [Protect against threats in Office 365](protect-against-threats.md).