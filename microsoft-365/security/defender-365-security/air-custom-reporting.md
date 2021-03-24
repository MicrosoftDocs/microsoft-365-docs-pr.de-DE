---
title: Benutzerdefinierte Berichterstellungslösungen mit automatisierter Untersuchung und Reaktion
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
description: Erfahren Sie, wie Sie automatisierte Untersuchungen und Reaktionen in eine benutzerdefinierte Oder Drittanbieterberichtslösung integrieren.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065632"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365

Mit [Microsoft Defender für Office 365](defender-for-office-365.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterberichtslösung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen [in](office-365-air.md) eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Mit [Microsoft Defender für Office 365](defender-for-office-365.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md) Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterberichtslösung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.

|Ressource|Beschreibung|
|:---|:---|
|[Übersicht über die Office 365-Verwaltungs-APIs](/office/office-365-management-api/office-365-management-apis-overview).|Die Office 365-Verwaltungsaktivitäts-API bietet Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen.|
|[Erste Schritte mit den Office 365-Verwaltungs-APIs](/office/office-365-management-api/get-started-with-office-365-management-apis)|Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365-Daten zur Verfügung zu stellen. Führen Sie die Schritte in diesem Artikel aus, um diese Einrichtung zu erstellen.|
|[Office 365-Verwaltungsaktivitäts-API – Referenz](/office/office-365-management-api/office-365-management-activity-api-reference)|Sie können die Office 365-Verwaltungsaktivitäts-API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure AD-Aktivitätsprotokollen abzurufen. Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.|
|[Office 365-Verwaltungsaktivitäts-API –Schema](/office/office-365-management-api/office-365-management-activity-api-schema)|Erhalten Sie eine Übersicht über das [allgemeine Schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) und das Defender for [Office 365-](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) und Bedrohungsuntersuchungs- und Reaktionsschema, um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365-Verwaltungsaktivitäts-API verfügbar sind.|
|

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Office 365](defender-for-office-365.md)
- [Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
