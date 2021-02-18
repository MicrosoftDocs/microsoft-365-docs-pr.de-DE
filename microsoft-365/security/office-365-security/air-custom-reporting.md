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
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287137"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365

Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung. Wenn Ihre Organisation Informationen [](office-365-air.md) zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

|Ressource|Beschreibung|
|:---|:---|
|[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).|Die Office 365-Verwaltungsaktivitäts-API stellt Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen bereit.|
|[Erste Schritte mit den Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365-Daten zur Verfügung zu stellen. Führen Sie die Schritte in diesem Artikel aus, um dies zu einrichten.|
|[Office 365-Verwaltungsaktivitäts-API – Referenz](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Sie können die Office 365-Verwaltungsaktivitäts-API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure AD-Aktivitätsprotokollen abzurufen. In diesem Artikel erfahren Sie mehr über die Funktionsweise.|
|[Office 365-Verwaltungsaktivitäts-API –Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Erhalten Sie einen [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) Überblick über das allgemeine Schema und das Schema für Die Untersuchung und Reaktion auf Bedrohungen für Defender für [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365-Verwaltungsaktivitäts-API verfügbar sind.|
|

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Office 365](office-365-atp.md)
- [Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](../mtp/mtp-autoir.md)
