---
title: Siem-Integration mit erweitertem Bedrohungsschutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrieren Sie den Siem-Server Ihrer Organisation mit Office 365 Advanced Threat Protection und den zugehörigen Threat-Ereignissen in die API für die Office 365-Aktivitätsverwaltung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327165"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Siem-Integration mit erweitertem Bedrohungsschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Ihre Organisation einen Siem-Server (Security Incident and Event Management) verwendet, können Sie Office 365 Advanced Threat Protection (Office 365 ATP) mit Ihrem Siem-Server integrieren. Sie können diese Integration mithilfe der API für die [Office 365 Aktivitätsverwaltung](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)einrichten. 

Mit der Siem-Integration können Sie Informationen wie Malware oder von Office 365 ATP erkannte Phishing in ihren Siem-Server Berichten anzeigen. 

- Ein Beispiel für Siem-Integration in Office 365 ATP finden Sie unter [Tech Community Blog: verbessern Sie die Effektivität ihrer SoC mit Office 365 ATP und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Weitere Informationen zu den APIs für die Office 365 Verwaltung finden Sie unter [Office 365 Management APIs Overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Funktionsweise von Siem-Integration

Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab. Wenn Ihre Organisation Office 365 ATP-Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Office 365 ATP-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.  

Kürzlich wurden Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in [Office 365 ATP-Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) zur API für die Office 365-Verwaltungsaktivität hinzugefügt. Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält die API auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.

Der Siem-Server oder ein ähnliches System fragt die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse ab. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Office 365 ATP-Ereignisse relevant sind:

|Wert|Elementname|Beschreibung|
|---|---|---|
|28|ThreatIntelligence|Phishing-und Schadsoftware-Ereignisse aus Exchange Online Schutz und Office 365 ATP.|
|41|ThreatIntelligenceUrl|Sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse aus Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams aus Office 365 ATP.|
|64|AirInvestigation|Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte aus Office 365 ATP-Plan 2.|
|

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um Siem-Integration mit Office 365 Advanced Threat Protection einzurichten.<br/>Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein. Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Mehr dazu

[Untersuchung von und Antwort auf Bedrohungen in Office 365](office-365-ti.md)

[Automatische Untersuchung und Reaktion (Air) in Office 365](automated-investigation-response-office.md)


