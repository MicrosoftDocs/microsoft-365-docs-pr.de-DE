---
title: Benutzerdefinierte Berichterstellungslösungen mit automatischer Untersuchung und Reaktion
keywords: SIEM, API, AIR, AutoIR, ATP, automatisierte Untersuchung, Integration, benutzerdefinierter Bericht
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie, wie Sie eine automatisierte Untersuchung und Reaktion mit einer benutzerdefinierten Oder Drittanbieterlösung für Die Berichterstellung integrieren.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287137"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="b1119-104">Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="b1119-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1119-105">Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="b1119-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="b1119-106">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="b1119-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="b1119-107">Wenn Ihre Organisation Informationen [](office-365-air.md) zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1119-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="b1119-108">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="b1119-108">**Applies to**</span></span>
- [<span data-ttu-id="b1119-109">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="b1119-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b1119-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1119-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b1119-111">Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="b1119-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="b1119-112">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="b1119-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="b1119-113">Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1119-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="b1119-114">Ressource</span><span class="sxs-lookup"><span data-stu-id="b1119-114">Resource</span></span>|<span data-ttu-id="b1119-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1119-115">Description</span></span>|
|:---|:---|
|<span data-ttu-id="b1119-116">[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="b1119-116">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="b1119-117">Die Office 365-Verwaltungsaktivitäts-API stellt Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen bereit.</span><span class="sxs-lookup"><span data-stu-id="b1119-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="b1119-118">Erste Schritte mit den Office 365-Verwaltungs-APIs</span><span class="sxs-lookup"><span data-stu-id="b1119-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="b1119-119">Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365-Daten zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="b1119-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="b1119-120">Führen Sie die Schritte in diesem Artikel aus, um dies zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="b1119-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="b1119-121">Office 365-Verwaltungsaktivitäts-API – Referenz</span><span class="sxs-lookup"><span data-stu-id="b1119-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="b1119-122">Sie können die Office 365-Verwaltungsaktivitäts-API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure AD-Aktivitätsprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b1119-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="b1119-123">In diesem Artikel erfahren Sie mehr über die Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="b1119-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="b1119-124">Office 365-Verwaltungsaktivitäts-API –Schema</span><span class="sxs-lookup"><span data-stu-id="b1119-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="b1119-125">Erhalten Sie einen [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) Überblick über das allgemeine Schema und das Schema für Die Untersuchung und Reaktion auf Bedrohungen für Defender für [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365-Verwaltungsaktivitäts-API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b1119-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="b1119-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1119-126">See also</span></span>

- [<span data-ttu-id="b1119-127">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="b1119-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="b1119-128">Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1119-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)
