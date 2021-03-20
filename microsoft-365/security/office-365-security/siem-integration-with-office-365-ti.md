---
title: SIEM-Integration in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrieren Sie den SIEM-Server Ihrer Organisation in Microsoft Defender für Office 365 und verwandte Bedrohungsereignisse in der Office 365 Activity Management-API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86a716499a25af2a2907d9c502d31474b27ef7bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916598"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-Integration in Microsoft Defender für Office 365

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Ihre Organisation einen SieM-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender for Office 365 in Ihren SIEM-Server integrieren. Sie können diese Integration mithilfe der [Office 365-Aktivitätsverwaltungs-API einrichten.](/office/office-365-management-api/office-365-management-activity-api-reference)

Mit der SIEM-Integration können Sie Informationen wie Schadsoftware oder Phish, die von Microsoft Defender für Office 365 erkannt werden, in Ihren SIEM-Serverberichten anzeigen.

- Ein Beispiel für die SIEM-Integration in Microsoft Defender für Office 365 finden Sie unter [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Weitere Informationen zu den Office 365-Verwaltungs-APIs finden Sie unter [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Funktionsweise der SIEM-Integration

Die Office 365-Aktivitätsverwaltungs-API ruft Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus den Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab. Wenn Ihre Organisation Über Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Microsoft Defender for Office 365-Schema verwenden.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Kürzlich wurden Ereignisse aus automatisierten Untersuchungs- und Reaktionsfunktionen in [Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) der Office 365-Verwaltungsaktivitäts-API hinzugefügt. Die API enthält nicht nur Daten zu grundlegenden Untersuchungsdetails wie ID, Name und Status, sondern enthält auch informationen auf hoher Ebene zu Untersuchungsaktionen und -entitäten.

Der SIEM-Server oder ein anderes ähnliches System abruft die **audit.general-Arbeitsauslastung,** um auf Erkennungsereignisse zu zugreifen. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender for Office 365-Ereignisse relevant sind:

|Wert|Elementname|Beschreibung|
|---|---|---|
|28|ThreatIntelligence|Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Microsoft Defender für Office 365.|
|41|ThreatIntelligenceUrl|Ereignisse für die Blockierung und Blocküberschreibung sicherer Links von Microsoft Defender für Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing- und Schadsoftwareereignisse für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams von Microsoft Defender für Office 365.|
|64|AirInvestigation|Automatisierte Untersuchungs- und Reaktionsereignisse, z. B. Untersuchungsdetails und relevante Artefakte, aus Microsoft Defender für Office 365 Plan 2.|
|

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein oder die Rolle des Sicherheitsadministrators für das Security & Compliance Center zugewiesen haben, um die SIEM-Integration in Microsoft Defender für Office 365 einrichten zu können.
>
> Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein. Hilfe dazu finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Siehe auch

[Untersuchung von und Antwort auf Bedrohungen in Office 365](office-365-ti.md)

[Automatisierte Untersuchung und Reaktion (AIR) in Office 365](automated-investigation-response-office.md)