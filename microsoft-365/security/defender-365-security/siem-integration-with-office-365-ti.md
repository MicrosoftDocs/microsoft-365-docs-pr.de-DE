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
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064464"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="8a4bf-103">SIEM-Integration in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="8a4bf-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8a4bf-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8a4bf-104">**Applies to**</span></span>
- [<span data-ttu-id="8a4bf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8a4bf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8a4bf-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8a4bf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8a4bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a4bf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8a4bf-108">Wenn Ihre Organisation einen SieM-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender for Office 365 in Ihren SIEM-Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="8a4bf-109">Sie können diese Integration mithilfe der [Office 365-Aktivitätsverwaltungs-API einrichten.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="8a4bf-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="8a4bf-110">Mit der SIEM-Integration können Sie Informationen wie Schadsoftware oder Phish, die von Microsoft Defender für Office 365 erkannt werden, in Ihren SIEM-Serverberichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="8a4bf-111">Ein Beispiel für die SIEM-Integration in Microsoft Defender für Office 365 finden Sie unter [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="8a4bf-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="8a4bf-112">Weitere Informationen zu den Office 365-Verwaltungs-APIs finden Sie unter [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="8a4bf-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="8a4bf-113">Funktionsweise der SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="8a4bf-113">How SIEM integration works</span></span>

<span data-ttu-id="8a4bf-114">Die Office 365-Aktivitätsverwaltungs-API ruft Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus den Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="8a4bf-115">Wenn Ihre Organisation Über Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Microsoft Defender for Office 365-Schema verwenden.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="8a4bf-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="8a4bf-116">Kürzlich wurden Ereignisse aus automatisierten Untersuchungs- und Reaktionsfunktionen in [Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) der Office 365-Verwaltungsaktivitäts-API hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="8a4bf-117">Die API enthält nicht nur Daten zu grundlegenden Untersuchungsdetails wie ID, Name und Status, sondern enthält auch informationen auf hoher Ebene zu Untersuchungsaktionen und -entitäten.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="8a4bf-118">Der SIEM-Server oder ein anderes ähnliches System abruft die **audit.general-Arbeitsauslastung,** um auf Erkennungsereignisse zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="8a4bf-119">Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="8a4bf-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="8a4bf-120">Enum: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="8a4bf-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="8a4bf-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="8a4bf-121">AuditLogRecordType</span></span>

<span data-ttu-id="8a4bf-122">In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender for Office 365-Ereignisse relevant sind:</span><span class="sxs-lookup"><span data-stu-id="8a4bf-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="8a4bf-123">Wert</span><span class="sxs-lookup"><span data-stu-id="8a4bf-123">Value</span></span>|<span data-ttu-id="8a4bf-124">Elementname</span><span class="sxs-lookup"><span data-stu-id="8a4bf-124">Member name</span></span>|<span data-ttu-id="8a4bf-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a4bf-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="8a4bf-126">28</span><span class="sxs-lookup"><span data-stu-id="8a4bf-126">28</span></span>|<span data-ttu-id="8a4bf-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="8a4bf-127">ThreatIntelligence</span></span>|<span data-ttu-id="8a4bf-128">Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="8a4bf-129">41</span><span class="sxs-lookup"><span data-stu-id="8a4bf-129">41</span></span>|<span data-ttu-id="8a4bf-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="8a4bf-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="8a4bf-131">Ereignisse für die Blockierung und Blocküberschreibung sicherer Links von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="8a4bf-132">47</span><span class="sxs-lookup"><span data-stu-id="8a4bf-132">47</span></span>|<span data-ttu-id="8a4bf-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="8a4bf-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="8a4bf-134">Phishing- und Schadsoftwareereignisse für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="8a4bf-135">64</span><span class="sxs-lookup"><span data-stu-id="8a4bf-135">64</span></span>|<span data-ttu-id="8a4bf-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="8a4bf-136">AirInvestigation</span></span>|<span data-ttu-id="8a4bf-137">Automatisierte Untersuchungs- und Reaktionsereignisse, z. B. Untersuchungsdetails und relevante Artefakte, aus Microsoft Defender für Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="8a4bf-138">Sie müssen ein globaler Administrator sein oder die Rolle des Sicherheitsadministrators für das Security & Compliance Center zugewiesen haben, um die SIEM-Integration in Microsoft Defender für Office 365 einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="8a4bf-139">Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="8a4bf-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="8a4bf-140">Hilfe dazu finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="8a4bf-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a4bf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a4bf-141">See also</span></span>

[<span data-ttu-id="8a4bf-142">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="8a4bf-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="8a4bf-143">Automatisierte Untersuchung und Reaktion (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="8a4bf-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)