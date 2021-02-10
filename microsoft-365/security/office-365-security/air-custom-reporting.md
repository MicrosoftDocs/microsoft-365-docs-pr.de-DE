---
title: Benutzerdefinierte Berichterstellungslösungen mit automatischer Untersuchung und Reaktion
keywords: SIEM, API, AIR, AutoIR, ATP, automatisierte Untersuchung, Integration, benutzerdefinierter Bericht
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie, wie Sie eine automatisierte Untersuchung und Reaktion mit einer benutzerdefinierten Oder Drittanbieterlösung für Die Berichterstellung integrieren.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175811"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365

Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung. Wenn Ihre Organisation Informationen [](office-365-air.md) zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

**Gilt für**
- [Microsoft Defender für Office 365 Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

|Ressource|Beschreibung|
|:---|:---|
|[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).|Die Office 365-Verwaltungsaktivitäts-API stellt Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen bereit.|
|[Erste Schritte mit den Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365-Daten zur Verfügung zu stellen. Führen Sie die Schritte in diesem Artikel aus, um dies zu einrichten.|
|[Office 365-Verwaltungsaktivitäts-API – Referenz](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Sie können die Office 365-Verwaltungsaktivitäts-API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure AD-Aktivitätsprotokollen abzurufen. In diesem Artikel erfahren Sie mehr über die Funktionsweise.|
|[Office 365-Verwaltungsaktivitäts-API –Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Erhalten Sie einen [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) Überblick über das allgemeine Schema und das Schema für Die Untersuchung und Reaktion auf Bedrohungen für Defender für [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365-Verwaltungsaktivitäts-API verfügbar sind.|
|

## <a name="see-also"></a>Weitere Informationen:

- [Microsoft Defender für Office 365](office-365-atp.md)
- [Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
