---
title: Verwenden von benutzerdefinierten Berichterstellungslösungen mit automatischer Untersuchung und Antwort
keywords: Siem, API, Air, autoIR, ATP, automatisierte Untersuchung, Integration, benutzerdefinierter Bericht
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
description: In diesem Artikel erfahren Sie, wie Sie automatisierte Untersuchungen und Antworten mit einer benutzerdefinierten oder Drittanbieter-Berichtslösung integrieren.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 08502516ae03dc7c6e7b58aa77939723e7532ef0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308920"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Verwenden der Verwaltungs Aktivitäts-API für benutzerdefinierte oder Drittanbieter-Berichtslösungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Mit [Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)erhalten Sie [detaillierte Informationen zu automatisierten Untersuchungen](air-view-investigation-results.md). Einige Organisationen verwenden jedoch auch eine benutzerdefinierte oder eine Drittanbieter-Berichtslösung. Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen mit einer solchen Lösung integrieren möchte, können Sie die API für die Office 365-Verwaltungsaktivität verwenden.

Verwenden Sie die folgenden Ressourcen, um dies einzurichten:

****

|Ressource|Beschreibung|
|---|---|
|[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).|Die Office 365-Verwaltungs Aktivitäts-API enthält Informationen zu verschiedenen Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen.|
|[Erste Schritte mit den Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung bereitzustellen, um auf Microsoft 365-Daten zuzugreifen. Führen Sie die Schritte in diesem Artikel aus, um dies einzurichten.|
|[Office 365-Verwaltungsaktivitäts-API – Referenz](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Sie können die Office 365-Verwaltungs Aktivitäts-API verwenden, um Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure AD-Aktivitätsprotokollen abzurufen. Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.|
|[Office 365-Verwaltungsaktivitäts-API –Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Erhalten Sie einen Überblick über das [allgemeine Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) und das [Office 365 ATP-und Threat-Ermittlungs-und-Antwortschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) , um sich über bestimmte Arten von Daten zu informieren, die über die API für die Office 365-Verwaltungsaktivität verfügbar sind.|
|

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Office 365](office-365-atp.md)

- [Automatische Untersuchung und Antwort in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
