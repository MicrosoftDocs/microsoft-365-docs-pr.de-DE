---
title: Benutzerdefinierte Berichterstellungslösungen mit automatisierter Untersuchung und Reaktion
keywords: SIEM, API, AIR, AutoIR, Microsoft Defender for Endpoint, automatisierte Untersuchung, Integration, benutzerdefinierter Bericht
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
description: Erfahren Sie, wie Sie automatisierte Untersuchungen und Reaktionen in eine benutzerdefinierte Oder Drittanbieterberichtslösung integrieren.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275012"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="f7cea-104">Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f7cea-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f7cea-105">Mit [Microsoft Defender for Office 365](defender-for-office-365.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f7cea-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f7cea-106">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterberichtslösung.</span><span class="sxs-lookup"><span data-stu-id="f7cea-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f7cea-107">Wenn Ihre Organisation Informationen [](office-365-air.md) zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365 Management Activity API verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7cea-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f7cea-108">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f7cea-108">**Applies to**</span></span>
- [<span data-ttu-id="f7cea-109">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="f7cea-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f7cea-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7cea-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f7cea-111">Mit [Microsoft Defender for Office 365](defender-for-office-365.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f7cea-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f7cea-112">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterberichtslösung.</span><span class="sxs-lookup"><span data-stu-id="f7cea-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f7cea-113">Wenn Ihre Organisation Informationen zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365 Management Activity API verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7cea-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="f7cea-114">Ressource</span><span class="sxs-lookup"><span data-stu-id="f7cea-114">Resource</span></span>|<span data-ttu-id="f7cea-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7cea-115">Description</span></span>|
|:---|:---|
|<span data-ttu-id="f7cea-116">[Übersicht über die Office 365-Verwaltungs-APIs](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="f7cea-116">[Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="f7cea-117">Die Office 365 Management Activity API enthält Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory Aktivitätsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="f7cea-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="f7cea-118">Erste Schritte mit den Office 365-Verwaltungs-APIs</span><span class="sxs-lookup"><span data-stu-id="f7cea-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="f7cea-119">Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f7cea-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="f7cea-120">Führen Sie die Schritte in diesem Artikel aus, um diese Einrichtung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7cea-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="f7cea-121">Office 365-Verwaltungsaktivitäts-API – Referenz</span><span class="sxs-lookup"><span data-stu-id="f7cea-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="f7cea-122">Sie können die Office 365 Management Activity API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365 und Azure AD-Aktivitätsprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f7cea-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="f7cea-123">Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="f7cea-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="f7cea-124">Office 365-Verwaltungsaktivitäts-API –Schema</span><span class="sxs-lookup"><span data-stu-id="f7cea-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="f7cea-125">Erhalten Sie eine [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) Übersicht über das allgemeine Schema und das [Defender for Office 365-](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) und Bedrohungsuntersuchungs- und Reaktionsschema, um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365 Management Activity API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f7cea-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="f7cea-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7cea-126">See also</span></span>

- [<span data-ttu-id="f7cea-127">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f7cea-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f7cea-128">Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7cea-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
