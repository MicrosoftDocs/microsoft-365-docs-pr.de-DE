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
ms.openlocfilehash: e11d1e64b7c8c3b9d5b93516fe05aed3d5937290
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105632"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="9ee08-103">SIEM-Integration in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="9ee08-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9ee08-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="9ee08-104">**Applies to**</span></span>
- [<span data-ttu-id="9ee08-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ee08-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9ee08-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="9ee08-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9ee08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ee08-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9ee08-108">Wenn Ihre Organisation einen SIEM-Server (Security Information and Event Management) verwendet, können Sie Microsoft Defender für Office 365 in Ihren SIEM-Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="9ee08-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="9ee08-109">Sie können diese Integration mithilfe der [Office 365 Aktivitätsverwaltungs-API](/office/office-365-management-api/office-365-management-activity-api-reference)einrichten.</span><span class="sxs-lookup"><span data-stu-id="9ee08-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="9ee08-110">Mit der SIEM-Integration können Sie Informationen wie Schadsoftware oder Phishing, die von Microsoft Defender für Office 365 erkannt wurden, in Ihren SIEM-Serverberichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ee08-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="9ee08-111">Ein Beispiel für die SIEM-Integration in Microsoft Defender for Office 365 finden Sie im [Tech Community Blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="9ee08-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>
- <span data-ttu-id="9ee08-112">Weitere Informationen zu den Office 365-Verwaltungs-APIs finden Sie unter [Office 365 Management APIs Overview](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="9ee08-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="9ee08-113">Funktionsweise der SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="9ee08-113">How SIEM integration works</span></span>

<span data-ttu-id="9ee08-114">Die Office 365 Aktivitätsverwaltungs-API ruft Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus den Microsoft 365- und Azure Active Directory Aktivitätsprotokollen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="9ee08-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="9ee08-115">Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 1 oder 2 oder Office 365 E5 verfügt, können Sie das [Microsoft Defender für Office 365 Schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ee08-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="9ee08-116">Kürzlich wurden Ereignisse aus automatisierten Untersuchungs- und Reaktionsfunktionen in [Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) der Office 365-Verwaltungsaktivitäts-API hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9ee08-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="9ee08-117">Die API enthält nicht nur Daten zu wichtigen Untersuchungsdetails wie ID, Name und Status, sie enthält auch allgemeine Informationen zu Untersuchungsaktionen und Entitäten.</span><span class="sxs-lookup"><span data-stu-id="9ee08-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="9ee08-118">Der SIEM-Server oder ein anderes ähnliches System fragt die **audit.general-Workload** ab, um auf Erkennungsereignisse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ee08-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="9ee08-119">Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="9ee08-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="9ee08-120">Enum: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="9ee08-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="9ee08-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="9ee08-121">AuditLogRecordType</span></span>

<span data-ttu-id="9ee08-122">In der folgenden Tabelle sind die Werte von **AuditLogRecordType** zusammengefasst, die für Microsoft Defender für Office 365 Ereignisse relevant sind:</span><span class="sxs-lookup"><span data-stu-id="9ee08-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

<br>

****

|<span data-ttu-id="9ee08-123">Wert</span><span class="sxs-lookup"><span data-stu-id="9ee08-123">Value</span></span>|<span data-ttu-id="9ee08-124">Elementname</span><span class="sxs-lookup"><span data-stu-id="9ee08-124">Member name</span></span>|<span data-ttu-id="9ee08-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee08-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="9ee08-126">28</span><span class="sxs-lookup"><span data-stu-id="9ee08-126">28</span></span>|<span data-ttu-id="9ee08-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="9ee08-127">ThreatIntelligence</span></span>|<span data-ttu-id="9ee08-128">Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ee08-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9ee08-129">41</span><span class="sxs-lookup"><span data-stu-id="9ee08-129">41</span></span>|<span data-ttu-id="9ee08-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="9ee08-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="9ee08-131">Tresor Verknüpft Ereignisse zum Zeitpunkt des Blockierens und Blockierens von Außerkraftsetzungen von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ee08-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9ee08-132">47</span><span class="sxs-lookup"><span data-stu-id="9ee08-132">47</span></span>|<span data-ttu-id="9ee08-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="9ee08-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="9ee08-134">Phishing- und Schadsoftwareereignisse für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams von Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ee08-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9ee08-135">64</span><span class="sxs-lookup"><span data-stu-id="9ee08-135">64</span></span>|<span data-ttu-id="9ee08-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="9ee08-136">AirInvestigation</span></span>|<span data-ttu-id="9ee08-137">Automatisierte Untersuchungs- und Reaktionsereignisse, z. B. Untersuchungsdetails und relevante Artefakte, von Microsoft Defender für Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="9ee08-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="9ee08-138">Sie müssen ein globaler Administrator sein oder der Sicherheitsadministratorrolle im Microsoft 365 Defender Portal zugewiesen sein, um die SIEM-Integration mit Microsoft Defender für Office 365 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9ee08-138">You must be a global administrator or have the Security Administrator role assigned in the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9ee08-139">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="9ee08-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
>
> <span data-ttu-id="9ee08-140">Die Überwachungsprotokollierung muss für Ihre Microsoft 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="9ee08-140">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="9ee08-141">Hilfe hierzu finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="9ee08-141">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ee08-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ee08-142">See also</span></span>

[<span data-ttu-id="9ee08-143">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="9ee08-143">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="9ee08-144">Automatisierte Untersuchung und Reaktion (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="9ee08-144">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)