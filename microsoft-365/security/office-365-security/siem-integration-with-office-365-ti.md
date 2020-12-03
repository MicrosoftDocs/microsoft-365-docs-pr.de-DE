---
title: Siem-Integration mit Microsoft Defender für Office 365
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
description: Integrieren Sie den Siem-Server Ihrer Organisation mit Microsoft Defender für Office 365-und zugehörige Threat-Ereignisse in der API für die Office 365-Aktivitätsverwaltung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6253ed0133bf53bdbeca71bb595a850e25441311
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561699"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Siem-Integration mit Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender für Office 365 mit Ihrem Siem-Server integrieren. Sie können diese Integration mithilfe der API für die [Office 365 Aktivitätsverwaltung](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)einrichten.

Mit der Siem-Integration können Sie in ihren Siem-Server Berichten Informationen wie Malware oder Phishing anzeigen, die von Microsoft Defender für Office 365 erkannt wurden.

- Ein Beispiel für eine Siem-Integration mit Microsoft Defender für Office 365 finden Sie unter [Tech Community Blog: verbessern der Effektivität ihrer SoC mit Defender für Office 365 und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Weitere Informationen zu den APIs für die Office 365 Verwaltung finden Sie unter [Office 365 Management APIs Overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Funktionsweise von Siem-Integration

Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab. Wenn Ihre Organisation Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie [Microsoft Defender für Office 365 Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.

In letzter Zeit wurden Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in [Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) zur API für die Office 365-Verwaltungsaktivität hinzugefügt. Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält die API auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.

Der Siem-Server oder ein ähnliches System fragt die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse ab. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender für Office 365-Ereignisse relevant sind:

|Wert|Elementname|Beschreibung|
|---|---|---|
|28|ThreatIntelligence|Phishing-und Schadsoftware-Ereignisse von Exchange Online Protection und Microsoft Defender für Office 365.|
|41|ThreatIntelligenceUrl|Sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse von Microsoft Defender für Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams von Microsoft Defender für Office 365.|
|64|AirInvestigation|Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte von Microsoft Defender für Office 365 Plan 2.|
|

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um die Siem-Integration mit Microsoft Defender für Office 365 einzurichten.<br/>Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein. Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Siehe auch

[Untersuchung von und Antwort auf Bedrohungen in Office 365](office-365-ti.md)

[Automatische Untersuchung und Reaktion (Air) in Office 365](automated-investigation-response-office.md)

