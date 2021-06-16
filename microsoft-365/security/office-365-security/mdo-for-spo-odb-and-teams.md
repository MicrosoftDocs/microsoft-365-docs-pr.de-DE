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
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932842"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams in Microsoft [Defender für Office 365](whats-new-in-defender-for-office-365.md) bieten eine zusätzliche Schutzebene für Dateien, die bereits zum Uploadzeitpunkt vom [allgemeinen Virenerkennungsmodul in Microsoft 365](virus-detection-in-spo.md)gescannt wurden. Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams helfen dabei, vorhandene Dateien zu erkennen und zu blockieren, die in Teamwebsites und Dokumentbibliotheken als bösartig erkannt werden.

Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind nicht standardmäßig aktiviert. Informationen zum Aktivieren finden Sie unter ["Sichere Anlagen aktivieren" für SharePoint, OneDrive und Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funktionsweise sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams

Wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind und eine Datei als bösartig identifiziert wird, wird die Datei durch direkte Integration in die Dateispeicher gesperrt. Die folgende Abbildung zeigt ein Beispiel für eine in einer Bibliothek erkannten böswilligen Datei.

![Dateien in OneDrive for Business mit einer als bösartig erkannten Datei](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in Web-, Mobil- oder Desktopanwendungen aufgeführt ist, können Benutzer die Datei nicht öffnen, kopieren, verschieben oder freigeben. Sie können die blockierte Datei jedoch löschen.

Hier ist ein Beispiel, wie eine blockierte Datei auf einem mobilen Gerät aussieht:

![Löschen einer blockierten Datei aus OneDrive for Business aus der OneDrive mobilen App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standardmäßig können Benutzer eine blockierte Datei herunterladen. Das Herunterladen einer blockierten Datei sieht auf einem mobilen Gerät wie folgt aus:

![Herunterladen einer blockierten Datei in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Onlineadministratoren können verhindern, dass Benutzer schädliche Dateien herunterladen. Anweisungen finden Sie unter [Verwenden von SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Weitere Informationen zur Benutzererfahrung, wenn eine Datei als bösartig erkannt wurde, finden Sie unter ["Was tun, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird."](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Anzeigen von Informationen zu schädlichen Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt wurden

Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams als bösartig erkannt werden, werden in [Berichten für Microsoft Defender für Office 365](view-reports-for-mdo.md) und im Explorer [(und Echtzeiterkennungen)](threat-explorer.md)angezeigt.

Ab Mai 2018 ist eine Datei, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams als bösartig erkannt wird, auch in Quarantäne verfügbar. Weitere Informationen finden Sie unter [Verwalten von isolierten Dateien in Defender für Office 365.](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)

## <a name="keep-these-points-in-mind"></a>Beachten Sie diese Punkte

- Defender für Office 365 überprüft nicht jede einzelne Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams. Es handelt sich hierbei um ein beabsichtigtes Verhalten. Dateien werden asynchron gescannt. Der Prozess verwendet Freigabe- und Gastaktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungssignalen, um schädliche Dateien zu identifizieren.

- Stellen Sie sicher, dass Ihre SharePoint Websites für die Verwendung der [modernen Benutzeroberfläche](/sharepoint/guide-to-sharepoint-modern-experience)konfiguriert sind. Defender für Office 365 Schutz gilt unabhängig davon, ob die moderne oder die klassische Ansicht verwendet wird. Visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche verfügbar.

- Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind Teil der allgemeinen Bedrohungsschutzstrategie Ihrer Organisation, die den Schutz vor Spam und Antischadsoftware in Exchange Online Protection (EOP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 umfasst. Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen in Office 365."](protect-against-threats.md)
