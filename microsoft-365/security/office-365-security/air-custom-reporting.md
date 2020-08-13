---
title: Verwenden von benutzerdefinierten Berichterstellungslösungen mit automatischer Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie automatisierte Untersuchungen und Antworten mit einer benutzerdefinierten oder Drittanbieter-Berichtslösung integrieren.
ms.openlocfilehash: cd7eb016ecd250eef56039e0135237c1caebadf8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656897"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="64d5b-104">Verwenden der Verwaltungs Aktivitäts-API für benutzerdefinierte oder Drittanbieter-Berichtslösungen</span><span class="sxs-lookup"><span data-stu-id="64d5b-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="64d5b-105">Mit [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)erhalten Sie [detaillierte Informationen zu automatisierten Untersuchungen](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="64d5b-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="64d5b-106">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte oder eine Drittanbieter-Berichtslösung.</span><span class="sxs-lookup"><span data-stu-id="64d5b-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="64d5b-107">Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen mit einer solchen Lösung integrieren möchte, können Sie die API für die Office 365-Verwaltungsaktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="64d5b-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="64d5b-108">Verwenden Sie die folgenden Ressourcen, um dies einzurichten:</span><span class="sxs-lookup"><span data-stu-id="64d5b-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="64d5b-109">Ressource</span><span class="sxs-lookup"><span data-stu-id="64d5b-109">Resource</span></span>|<span data-ttu-id="64d5b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64d5b-110">Description</span></span>|
|---|---|
|<span data-ttu-id="64d5b-111">[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="64d5b-111">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="64d5b-112">Die Office 365-Verwaltungs Aktivitäts-API enthält Informationen zu verschiedenen Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus Microsoft 365-und Azure Active Directory-Aktivitätsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="64d5b-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="64d5b-113">Erste Schritte mit den Office 365-Verwaltungs-APIs</span><span class="sxs-lookup"><span data-stu-id="64d5b-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="64d5b-114">Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung bereitzustellen, um auf Microsoft 365-Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="64d5b-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="64d5b-115">Führen Sie die Schritte in diesem Artikel aus, um dies einzurichten.</span><span class="sxs-lookup"><span data-stu-id="64d5b-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="64d5b-116">Office 365-Verwaltungsaktivitäts-API – Referenz</span><span class="sxs-lookup"><span data-stu-id="64d5b-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="64d5b-117">Sie können die Office 365-Verwaltungs Aktivitäts-API verwenden, um Informationen zu Benutzer-, Verwaltungs-, System-und Richtlinienaktionen und-Ereignissen aus den Microsoft 365-und Azure AD-Aktivitätsprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="64d5b-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="64d5b-118">Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="64d5b-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="64d5b-119">Office 365-Verwaltungsaktivitäts-API –Schema</span><span class="sxs-lookup"><span data-stu-id="64d5b-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="64d5b-120">Erhalten Sie einen Überblick über das [allgemeine Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) und das [Office 365 ATP-und Threat-Ermittlungs-und-Antwortschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) , um sich über bestimmte Arten von Daten zu informieren, die über die API für die Office 365-Verwaltungsaktivität verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="64d5b-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="related-articles"></a><span data-ttu-id="64d5b-121">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="64d5b-121">Related articles</span></span>

- [<span data-ttu-id="64d5b-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="64d5b-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="64d5b-123">Informationen zu automatisierten Untersuchungen und Antworten in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="64d5b-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)