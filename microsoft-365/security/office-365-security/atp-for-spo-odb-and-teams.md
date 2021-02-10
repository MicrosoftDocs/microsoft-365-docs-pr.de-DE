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
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175727"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams in [Microsoft Defender für Office 365](office-365-atp.md) bietet eine zusätzliche Schutzebene für Dateien, die bereits beim Hochladen vom allgemeinen Virenerkennungsmodul in Microsoft [365](virus-detection-in-spo.md)überprüft wurden. Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams helfen beim Erkennen und Blockieren vorhandener Dateien, die in Teamwebsites und Dokumentbibliotheken als bösartig identifiziert werden.

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind standardmäßig nicht aktiviert. Informationen zum Aktivieren finden Sie unter ["Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funktionsweise sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams

Wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind und eine Datei als bösartig identifiziert wird, wird die Datei mithilfe der direkten Integration in die Dateispeicher gesperrt. Die folgende Abbildung zeigt ein Beispiel für eine in einer Bibliothek erkannten böswilligen Datei.

![Dateien in OneDrive for Business mit einer als bösartig erkannten Datei](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in Web-, Mobil- oder Desktopanwendungen aufgeführt ist, können Benutzer die Datei nicht öffnen, kopieren, verschieben oder freigeben. Sie können jedoch die blockierte Datei löschen.

Hier ist ein Beispiel dafür, wie eine blockierte Datei auf einem mobilen Gerät aussieht:

![Löschen einer blockierten Datei aus OneDrive for Business aus der mobilen #A0](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standardmäßig können Benutzer eine blockierte Datei herunterladen. So sieht das Herunterladen einer gesperrten Datei auf einem mobilen Gerät aus:

![Herunterladen einer blockierten Datei in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-Administratoren können verhindern, dass Personen schädliche Dateien herunterladen. Anweisungen finden Sie unter [Verwenden von SharePoint Online PowerShell,](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)um zu verhindern, dass Benutzer schädliche Dateien herunterladen.

Weitere Informationen zur Benutzeroberfläche, wenn eine Datei als schädlich erkannt wurde, finden Sie unter "Was tun, wenn eine schädliche Datei [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)oder Microsoft Teams gefunden wird".

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Anzeigen von Informationen zu schädlichen Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt wurden

Dateien, die von Microsoft Defender für Office 365 als bösartig identifiziert werden, werden in Berichten für [Microsoft Defender für Office 365](view-reports-for-atp.md) und in Explorer (und Echtzeiterkennungen) [angezeigt.](threat-explorer.md)

Ab Mai 2018, wenn eine Datei von Microsoft Defender für Office 365 als bösartig identifiziert wird, ist die Datei auch in Quarantäne verfügbar. Weitere Informationen finden Sie im Security & Compliance Center zum Verwalten [von Isolierten Dateien.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Beachten Sie diese Punkte

- Defender für Office 365 scannt nicht jede einzelne Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams. Es handelt sich hierbei um ein beabsichtigtes Verhalten. Dateien werden asynchron überprüft. Der Prozess verwendet Freigabe- und Gastaktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungssignalen, um schädliche Dateien zu identifizieren.

- Stellen Sie sicher, dass Ihre SharePoint-Websites für die Verwendung der modernen [Be benutzererfahrung konfiguriert sind.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) Defender für Office 365-Schutz gilt unabhängig davon, ob die moderne Ansicht oder die klassische Ansicht verwendet wird. Visuelle Indikatoren, die eine Datei blockieren, sind jedoch nur in der modernen Be benutzererfahrung verfügbar.

- Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind Teil der gesamten Bedrohungsschutzstrategie Ihrer Organisation, die Antispam- und Ansoftwareschutz in Exchange Online Protection (EOP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 umfasst. Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen in Office 365".](protect-against-threats.md)
