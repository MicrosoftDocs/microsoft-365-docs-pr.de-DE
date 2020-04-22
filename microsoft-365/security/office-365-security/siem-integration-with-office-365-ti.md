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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integrieren Sie den Siem-Server Ihrer Organisation mit Office 365 Advanced Threat Protection und den zugehörigen Threat-Ereignissen in die API für die Office 365-Aktivitätsverwaltung.
ms.openlocfilehash: 770e2348c4e5729531118fb4a014a72c352a0dd1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638296"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Siem-Integration mit erweitertem Bedrohungsschutz

Wenn Ihre Organisation einen Siem-Server (Security Incident and Event Management) verwendet, können Sie Office 365 Advanced Threat Protection mit Ihrem Siem-Server integrieren. Mit der Siem-Integration können Sie in ihren Siem-Server Berichten Informationen wie Malware oder Phishing anzeigen, die von Office 365 Advanced Protection erkannt wurden. Um Siem-Integration einzurichten, verwenden Sie die [Office 365-Aktivitäts Verwaltungs-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und Ereignissen aus den Microsoft 365 for Business-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab. Das [Office 365 Advanced Threat Protection-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funktioniert mit Advanced Threat Protection, wenn Ihre Organisation also über die Office 365 Advanced Threat Protection Plan 1 oder Plan 2 oder Office 365 E5 verfügt, können Sie die gleiche API für Ihre Siem-Server Integration weiterhin verwenden. 

Im Rahmen unserer jüngsten Updates haben wir auch Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in Office 365 ATP-Plan 2 in der API für die Office 365-Verwaltungsaktivität hinzugefügt. Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält es auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.   

Der Siem-Server oder ein ähnliches System sollten die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse Abfragen. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Darüber hinaus sind die folgenden Werte von **AuditLogRecordType** für Office 365 ATP-Ereignisse relevant:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Wert|Elementname|Beschreibung|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|ATP-sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse von Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams aus Office 365 Advanced Threat Protection.|
|64|AirInvestigation|Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte aus Office 365 Advanced Threat Protection-Plan 2.|


> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um Siem-Integration mit Office 365 Advanced Threat Protection einzurichten.<br/>Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein. Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Verwandte Themen

[Untersuchung von und Antwort auf Bedrohungen in Office 365](office-365-ti.md)

[Automatische Untersuchung und Reaktion (Air) in Office 365](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Intelligente Berichte und Einblicke im &amp; Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Berechtigungen im Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
