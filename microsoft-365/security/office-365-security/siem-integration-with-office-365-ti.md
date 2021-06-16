---
title: SIEM-Integration in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrieren Sie den SIEM-Server Ihrer Organisation in Microsoft Defender für Office 365 und verwandte Bedrohungsereignisse in die Office 365 Aktivitätsverwaltungs-API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929779"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-Integration in Microsoft Defender für Office 365

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Ihre Organisation einen SIEM-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender für Office 365 in Ihren SIEM-Server integrieren. Sie können diese Integration mithilfe der [Office 365 Aktivitätsverwaltungs-API](/office/office-365-management-api/office-365-management-activity-api-reference)einrichten.

Mit der SIEM-Integration können Sie Informationen, z. B. Schadsoftware oder Phishing, die von Microsoft Defender für Office 365 erkannt wurden, in Ihren SIEM-Serverberichten anzeigen.

- Ein Beispiel für die SIEM-Integration in Microsoft Defender für Office 365 finden Sie im [Tech Community Blog: Verbessern der Effektivität Ihres SOC mit Defender für Office 365 und der O365-Verwaltungs-API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Weitere Informationen zu den Office 365-Verwaltungs-APIs finden Sie unter [Office 365 Management APIs Overview](/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Funktionsweise der SIEM-Integration

Die Office 365 Aktivitätsverwaltungs-API ruft Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus den Aktivitätsprotokollen Microsoft 365 und Azure Active Directory Ihrer Organisation ab. Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Microsoft Defender for Office 365-Schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.

Kürzlich wurden Ereignisse aus automatisierten Untersuchungs- und Reaktionsfunktionen in [Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) zur Office 365 Verwaltungsaktivitäts-API hinzugefügt. Die API enthält nicht nur Daten zu wichtigen Untersuchungsdetails wie ID, Name und Status, sie enthält auch allgemeine Informationen zu Untersuchungsaktionen und Entitäten.

Der SIEM-Server oder ein anderes ähnliches System fragt die **audit.general-Workload** ab, um auf Erkennungsereignisse zuzugreifen. Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender für Office 365 Ereignisse relevant sind:

|Wert|Elementname|Beschreibung|
|---|---|---|
|28|ThreatIntelligence|Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Microsoft Defender für Office 365.|
|41|ThreatIntelligenceUrl|Ereignisse für die Außerkraftsetzung von "Sichere Links" in Microsoft Defender für Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing- und Schadsoftwareereignisse für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams von Microsoft Defender für Office 365.|
|64|AirInvestigation|Automatisierte Untersuchungs- und Reaktionsereignisse, z. B. Untersuchungsdetails und relevante Artefakte, aus Microsoft Defender für Office 365 Plan 2.|
|

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein oder der Sicherheitsadministratorrolle für das Microsoft 365 Defender-Portal zugewiesen sein, um die SIEM-Integration mit Microsoft Defender für Office 365 einzurichten.
>
> Die Überwachungsprotokollierung muss für Ihre Microsoft 365 Umgebung aktiviert sein. Hilfe hierzu finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Siehe auch

[Untersuchung von und Antwort auf Bedrohungen in Office 365](office-365-ti.md)

[Automatisierte Untersuchung und Reaktion (AIR) in Office 365](automated-investigation-response-office.md)