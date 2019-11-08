---
title: Siem-Integration mit Office 365 Advanced Threat Protection
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
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: Integrieren Sie den Siem-Server Ihrer Organisation mit Office 365 Advanced Threat Protection und den zugehörigen Threat-Ereignissen in die API für die Office 365-Aktivitätsverwaltung.
ms.openlocfilehash: a9d6c8db8ca3090bb2a10ec1bd9b6f5edb48991e
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033886"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>Siem-Integration mit Office 365 Advanced Threat Protection

Wenn Ihre Organisation einen Siem-Server (Security Incident and Event Management) verwendet, können Sie Office 365 Advanced Threat Protection mit Ihrem Siem-Server integrieren. Mit der Siem-Integration können Sie in ihren Siem-Server Berichten Informationen wie Malware oder Phishing anzeigen, die von Office 365 Advanced Protection erkannt wurden. Um Siem-Integration einzurichten, verwenden Sie die [Office 365-Aktivitäts Verwaltungs-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und Ereignissen aus den Office 365-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab. Das [Office 365 Advanced Threat Protection-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funktioniert mit Advanced Threat Protection, wenn Ihre Organisation also über die Office 365 Advanced Threat Protection Plan 1 oder Plan 2 oder Office 365 E5 verfügt, können Sie die gleiche API für Ihre Siem-Server Integration weiterhin verwenden. 

Der Siem-Server oder ein ähnliches System sollten die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse Abfragen. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Darüber hinaus sind die folgenden Werte von **AuditLogRecordType** für Office 365 ATP-Ereignisse relevant:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Wert|Elementname|Beschreibung|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|ATP-sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse von Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams aus Office 365 Advanced Threat Protection.|

> [!IMPORTANT]
> Sie müssen ein Office 365 globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security #a0 Compliance Center zugewiesen sein, um Siem-Integration mit Office 365 Advanced Threat Protection einzurichten.<br/>Die Überwachungsprotokollierung muss für Ihre Office 365 Umgebung aktiviert sein. Informationen dazu finden Sie unter [Turn Office 365 Audit Log Search on or off](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Verwandte Themen

[Untersuchung und Reaktion der Office 365 Bedrohung](office-365-ti.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Intelligente Berichte und Einblicke im Office 365 &amp; Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
