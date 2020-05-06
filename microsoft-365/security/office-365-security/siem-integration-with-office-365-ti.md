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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035272"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="15bfd-103">Siem-Integration mit erweitertem Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="15bfd-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="15bfd-104">Wenn Ihre Organisation einen Siem-Server (Security Incident and Event Management) verwendet, können Sie Office 365 Advanced Threat Protection mit Ihrem Siem-Server integrieren.</span><span class="sxs-lookup"><span data-stu-id="15bfd-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="15bfd-105">Mit der Siem-Integration können Sie in ihren Siem-Server Berichten Informationen wie Malware oder Phishing anzeigen, die von Office 365 Advanced Protection erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="15bfd-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="15bfd-106">Um Siem-Integration einzurichten, verwenden Sie die [Office 365-Aktivitäts Verwaltungs-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="15bfd-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="15bfd-107">Die API für die Office 365 Aktivitätsverwaltung Ruft Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und Ereignissen aus den Microsoft 365 for Business-und Azure Active Directory-Aktivitätsprotokollen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="15bfd-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="15bfd-108">Das [Office 365 Advanced Threat Protection-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funktioniert mit Advanced Threat Protection, wenn Ihre Organisation also über die Office 365 Advanced Threat Protection Plan 1 oder Plan 2 oder Office 365 E5 verfügt, können Sie die gleiche API für Ihre Siem-Server Integration weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="15bfd-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="15bfd-109">Im Rahmen unserer jüngsten Updates haben wir auch Ereignisse aus automatisierten Ermittlungs-und Antwortfunktionen in Office 365 ATP-Plan 2 in der API für die Office 365-Verwaltungsaktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="15bfd-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="15bfd-110">Zusätzlich zum Einschließen von Daten zu Kern Ermittlungs Details wie ID, Name und Status enthält es auch allgemeine Informationen zu Ermittlungsaktionen und Entitäten.</span><span class="sxs-lookup"><span data-stu-id="15bfd-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="15bfd-111">Der Siem-Server oder ein ähnliches System sollten die **Audit. allgemeine** Arbeitsauslastung für den Zugriff auf Erkennungsereignisse Abfragen.</span><span class="sxs-lookup"><span data-stu-id="15bfd-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="15bfd-112">Weitere Informationen finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="15bfd-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="15bfd-113">Darüber hinaus sind die folgenden Werte von **AuditLogRecordType** für Office 365 ATP-Ereignisse relevant:</span><span class="sxs-lookup"><span data-stu-id="15bfd-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="15bfd-114">Enum: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="15bfd-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="15bfd-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="15bfd-115">AuditLogRecordType</span></span>

|<span data-ttu-id="15bfd-116">Wert</span><span class="sxs-lookup"><span data-stu-id="15bfd-116">Value</span></span>|<span data-ttu-id="15bfd-117">Elementname</span><span class="sxs-lookup"><span data-stu-id="15bfd-117">Member name</span></span>|<span data-ttu-id="15bfd-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15bfd-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15bfd-119">28</span><span class="sxs-lookup"><span data-stu-id="15bfd-119">28</span></span>|<span data-ttu-id="15bfd-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="15bfd-120">ThreatIntelligence</span></span>|<span data-ttu-id="15bfd-121">Phishing- und Schadsoftwareereignisse aus Exchange Online Protection und Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="15bfd-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="15bfd-122">41</span><span class="sxs-lookup"><span data-stu-id="15bfd-122">41</span></span>|<span data-ttu-id="15bfd-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="15bfd-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="15bfd-124">ATP-sichere Links Time-of-Block-und Block Außerkraftsetzungs Ereignisse von Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="15bfd-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="15bfd-125">47</span><span class="sxs-lookup"><span data-stu-id="15bfd-125">47</span></span>|<span data-ttu-id="15bfd-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="15bfd-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="15bfd-127">Phishing-und Schadsoftware-Ereignisse für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams aus Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="15bfd-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="15bfd-128">64</span><span class="sxs-lookup"><span data-stu-id="15bfd-128">64</span></span>|<span data-ttu-id="15bfd-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="15bfd-129">AirInvestigation</span></span>|<span data-ttu-id="15bfd-130">Automatisierte Ermittlungs-und Antwortereignisse wie Ermittlungs Details und relevante Artefakte aus Office 365 Advanced Threat Protection-Plan 2.</span><span class="sxs-lookup"><span data-stu-id="15bfd-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="15bfd-131">Sie müssen ein globaler Administrator sein oder der Sicherheitsadministrator Rolle für das Security & Compliance Center zugewiesen sein, um Siem-Integration mit Office 365 Advanced Threat Protection einzurichten.</span><span class="sxs-lookup"><span data-stu-id="15bfd-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="15bfd-132">Die Überwachungsprotokollierung muss für Ihre Microsoft 365-Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="15bfd-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="15bfd-133">Informationen dazu finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="15bfd-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="15bfd-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="15bfd-134">Related topics</span></span>

[<span data-ttu-id="15bfd-135">Untersuchung von und Antwort auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="15bfd-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="15bfd-136">Automatische Untersuchung und Reaktion (Air) in Office 365</span><span class="sxs-lookup"><span data-stu-id="15bfd-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="15bfd-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="15bfd-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="15bfd-138">Intelligente Berichte und Einblicke im &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="15bfd-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="15bfd-139">Berechtigungen im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="15bfd-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
