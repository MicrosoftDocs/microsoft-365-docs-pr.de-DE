---
title: Verwenden von benutzerdefinierten Berichterstellungslösungen mit automatischer Untersuchung und Reaktion in Office 365
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie Office 365 automatisierte Untersuchung und Antwort mit einer benutzerdefinierten oder Drittanbieter-Berichtslösung integrieren.
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175928"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Verwenden der API für die Office 365-Verwaltungsaktivität für benutzerdefinierte oder Drittanbieter-Berichtslösungen

Mit [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)erhalten Sie [detaillierte Informationen zu automatisierten Untersuchungen](air-view-investigation-results.md). Einige Organisationen verwenden jedoch auch eine benutzerdefinierte oder eine Drittanbieter-Berichtslösung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen mit einer solchen Lösung integrieren möchte, können Sie die API für die Office 365-Verwaltungsaktivität verwenden.

Verwenden Sie die folgenden Ressourcen, um dies einzurichten:

|Ressource  |Beschreibung  |
|---------|---------|
|[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).     |Die Office 365-Verwaltungsaktivitäts-API bietet Informationen über verschiedene Benutzer-, Verwaltungs-, System- und Richtlinienaktionen und -ereignisse aus Office 365 und Azure Active Directory-Aktivitätsprotokollen.         |
|[Erste Schritte mit den Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung bereitzustellen, um auf Office 365 Daten zuzugreifen. Führen Sie die Schritte in diesem Artikel aus, um dies einzurichten.          |
|[Office 365-Verwaltungsaktivitäts-API – Referenz](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Sie können die Office 365-Verwaltungs Aktivitäts-API verwenden, um Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus Office 365-und Azure AD-Aktivitätsprotokollen abzurufen. Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.        |
|[Office 365-Verwaltungsaktivitäts-API –Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Erhalten Sie einen Überblick über das [allgemeine Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) und das [Office 365 ATP-und Threat-Ermittlungs-und-Antwortschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) , um sich über bestimmte Arten von Daten zu informieren, die über die API für die Office 365-Verwaltungsaktivität verfügbar sind.         |

## <a name="related-articles"></a>Verwandte Artikel

- [Office 365 Advanced Threat Protection](office-365-atp.md)

- [Informationen zu automatisierten Untersuchungen und Antworten in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)