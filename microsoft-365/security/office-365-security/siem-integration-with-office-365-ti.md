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
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600553"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="30f63-103">Siem-Integration mit erweitertem Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="30f63-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="30f63-104">Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet, können Sie Office 365 Advanced Threat Protection (Office 365 ATP) mit Ihrem Siem-Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="30f63-104">If your organization is using a security information and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="30f63-105">Sie können diese Integration mithilfe der API für die [Office 365 Aktivitätsverwaltung](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)einrichten.</span><span class="sxs-lookup"><span data-stu-id="30f63-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="30f63-106">Mit der Siem-Integration können Sie Informationen wie Malware oder von Office 365 ATP erkannte Phishing in ihren Siem-Server Berichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="30f63-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="30f63-107">Ein Beispiel für Siem-Integration in Office 365 ATP finden Sie unter [Tech Community Blog: verbessern Sie die Effektivität ihrer SoC mit Office 365 ATP und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="30f63-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="30f63-108">Weitere Informationen zu den APIs für die Office 365 Verwaltung finden Sie unter [Office 365 Management APIs Overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="30f63-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="30f63-109">Funktionsweise von Siem-Integration</span><span class="sxs-lookup"><span data-stu-id="30f63-109">How SIEM integration works</span></span>

<span data-ttu-id="30f63-110">Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="30f63-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="30f63-111">Wenn Ihre Organisation Office 365 ATP-Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Office 365 ATP-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.</span><span class="sxs-lookup"><span data-stu-id="30f63-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="30f63-112">Kürzlich wurden Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in [Office 365 ATP-Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) zur API für die Office 365-Verwaltungsaktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="30f63-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="30f63-113">Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält die API auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.</span><span class="sxs-lookup"><span data-stu-id="30f63-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="30f63-114">Der Siem-Server oder ein ähnliches System fragt die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse ab.</span><span class="sxs-lookup"><span data-stu-id="30f63-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="30f63-115">Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="30f63-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="30f63-116">Enum: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="30f63-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="30f63-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="30f63-117">AuditLogRecordType</span></span>

<span data-ttu-id="30f63-118">In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Office 365 ATP-Ereignisse relevant sind:</span><span class="sxs-lookup"><span data-stu-id="30f63-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="30f63-119">Wert</span><span class="sxs-lookup"><span data-stu-id="30f63-119">Value</span></span>|<span data-ttu-id="30f63-120">Elementname</span><span class="sxs-lookup"><span data-stu-id="30f63-120">Member name</span></span>|<span data-ttu-id="30f63-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30f63-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="30f63-122">28</span><span class="sxs-lookup"><span data-stu-id="30f63-122">28</span></span>|<span data-ttu-id="30f63-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="30f63-123">ThreatIntelligence</span></span>|<span data-ttu-id="30f63-124">Phishing-und Schadsoftware-Ereignisse aus Exchange Online Schutz und Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="30f63-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="30f63-125">41</span><span class="sxs-lookup"><span data-stu-id="30f63-125">41</span></span>|<span data-ttu-id="30f63-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="30f63-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="30f63-127">Sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse aus Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="30f63-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="30f63-128">47</span><span class="sxs-lookup"><span data-stu-id="30f63-128">47</span></span>|<span data-ttu-id="30f63-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="30f63-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="30f63-130">Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams aus Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="30f63-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="30f63-131">64</span><span class="sxs-lookup"><span data-stu-id="30f63-131">64</span></span>|<span data-ttu-id="30f63-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="30f63-132">AirInvestigation</span></span>|<span data-ttu-id="30f63-133">Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte aus Office 365 ATP-Plan 2.</span><span class="sxs-lookup"><span data-stu-id="30f63-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="30f63-134">Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um Siem-Integration mit Office 365 Advanced Threat Protection einzurichten.</span><span class="sxs-lookup"><span data-stu-id="30f63-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="30f63-135">Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="30f63-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="30f63-136">Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="30f63-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30f63-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30f63-137">See also</span></span>

[<span data-ttu-id="30f63-138">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="30f63-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="30f63-139">Automatische Untersuchung und Reaktion (Air) in Office 365</span><span class="sxs-lookup"><span data-stu-id="30f63-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

