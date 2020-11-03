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
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843576"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="2c363-103">Siem-Integration mit Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="2c363-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2c363-104">Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender für Office 365 mit Ihrem Siem-Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="2c363-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="2c363-105">Sie können diese Integration mithilfe der API für die [Office 365 Aktivitätsverwaltung](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)einrichten.</span><span class="sxs-lookup"><span data-stu-id="2c363-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="2c363-106">Mit der Siem-Integration können Sie in ihren Siem-Server Berichten Informationen wie Malware oder Phishing anzeigen, die von Microsoft Defender für Office 365 erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="2c363-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span> 

- <span data-ttu-id="2c363-107">Ein Beispiel für eine Siem-Integration mit Microsoft Defender für Office 365 finden Sie unter [Tech Community Blog: verbessern der Effektivität ihrer SoC mit Defender für Office 365 und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="2c363-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="2c363-108">Weitere Informationen zu den APIs für die Office 365 Verwaltung finden Sie unter [Office 365 Management APIs Overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="2c363-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="2c363-109">Funktionsweise von Siem-Integration</span><span class="sxs-lookup"><span data-stu-id="2c363-109">How SIEM integration works</span></span>

<span data-ttu-id="2c363-110">Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="2c363-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="2c363-111">Wenn Ihre Organisation Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie [Microsoft Defender für Office 365 Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c363-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="2c363-112">In letzter Zeit wurden Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in [Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) zur API für die Office 365-Verwaltungsaktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c363-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="2c363-113">Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält die API auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.</span><span class="sxs-lookup"><span data-stu-id="2c363-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="2c363-114">Der Siem-Server oder ein ähnliches System fragt die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse ab.</span><span class="sxs-lookup"><span data-stu-id="2c363-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="2c363-115">Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="2c363-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="2c363-116">Enum: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="2c363-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="2c363-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="2c363-117">AuditLogRecordType</span></span>

<span data-ttu-id="2c363-118">In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender für Office 365-Ereignisse relevant sind:</span><span class="sxs-lookup"><span data-stu-id="2c363-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="2c363-119">Wert</span><span class="sxs-lookup"><span data-stu-id="2c363-119">Value</span></span>|<span data-ttu-id="2c363-120">Elementname</span><span class="sxs-lookup"><span data-stu-id="2c363-120">Member name</span></span>|<span data-ttu-id="2c363-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c363-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="2c363-122">28</span><span class="sxs-lookup"><span data-stu-id="2c363-122">28</span></span>|<span data-ttu-id="2c363-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="2c363-123">ThreatIntelligence</span></span>|<span data-ttu-id="2c363-124">Phishing-und Schadsoftware-Ereignisse von Exchange Online Protection und Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c363-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2c363-125">41</span><span class="sxs-lookup"><span data-stu-id="2c363-125">41</span></span>|<span data-ttu-id="2c363-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="2c363-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="2c363-127">Sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c363-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2c363-128">47</span><span class="sxs-lookup"><span data-stu-id="2c363-128">47</span></span>|<span data-ttu-id="2c363-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="2c363-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="2c363-130">Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c363-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2c363-131">64</span><span class="sxs-lookup"><span data-stu-id="2c363-131">64</span></span>|<span data-ttu-id="2c363-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="2c363-132">AirInvestigation</span></span>|<span data-ttu-id="2c363-133">Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte von Microsoft Defender für Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="2c363-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="2c363-134">Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um die Siem-Integration mit Microsoft Defender für Office 365 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="2c363-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span><br/><span data-ttu-id="2c363-135">Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2c363-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="2c363-136">Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2c363-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c363-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c363-137">See also</span></span>

[<span data-ttu-id="2c363-138">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c363-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="2c363-139">Automatische Untersuchung und Reaktion (Air) in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c363-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

