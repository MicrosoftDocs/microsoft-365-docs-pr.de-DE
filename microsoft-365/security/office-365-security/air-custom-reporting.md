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
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142970"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="acda7-104">Benutzerdefinierte oder Drittanbieterberichtslösungen für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="acda7-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="acda7-105">Mit [Microsoft Defender für Office 365](office-365-atp.md)erhalten Sie detaillierte Informationen zu [automatisierten Untersuchungen.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="acda7-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="acda7-106">Einige Organisationen verwenden jedoch auch eine benutzerdefinierte Oder Drittanbieterlösung für die Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="acda7-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="acda7-107">Wenn Ihre Organisation Informationen [](office-365-air.md) zu automatisierten Untersuchungen in eine solche Lösung integrieren möchte, können Sie die Office 365-Verwaltungsaktivitäts-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="acda7-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="acda7-108">Ressourcen zum Konfigurieren der Integration</span><span class="sxs-lookup"><span data-stu-id="acda7-108">Resources to configure integration</span></span>

|<span data-ttu-id="acda7-109">Ressource</span><span class="sxs-lookup"><span data-stu-id="acda7-109">Resource</span></span>|<span data-ttu-id="acda7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acda7-110">Description</span></span>|
|:---|:---|
|<span data-ttu-id="acda7-111">[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="acda7-111">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="acda7-112">Die Office 365-Verwaltungsaktivitäts-API stellt Informationen zu verschiedenen Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure Active Directory-Aktivitätsprotokollen bereit.</span><span class="sxs-lookup"><span data-stu-id="acda7-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="acda7-113">Erste Schritte mit den Office 365-Verwaltungs-APIs</span><span class="sxs-lookup"><span data-stu-id="acda7-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="acda7-114">Die Office 365-Verwaltungs-API verwendet Azure AD, um Authentifizierungsdienste für Ihre Anwendung für den Zugriff auf Microsoft 365-Daten zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="acda7-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="acda7-115">Führen Sie die Schritte in diesem Artikel aus, um dies zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="acda7-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="acda7-116">Office 365-Verwaltungsaktivitäts-API – Referenz</span><span class="sxs-lookup"><span data-stu-id="acda7-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="acda7-117">Sie können die Office 365-Verwaltungsaktivitäts-API verwenden, um Informationen zu Benutzer-, Administrator-, System- und Richtlinienaktionen und -ereignissen aus Microsoft 365- und Azure AD-Aktivitätsprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="acda7-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="acda7-118">In diesem Artikel erfahren Sie mehr über die Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="acda7-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="acda7-119">Office 365-Verwaltungsaktivitäts-API –Schema</span><span class="sxs-lookup"><span data-stu-id="acda7-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="acda7-120">Erhalten Sie einen [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) Überblick über das allgemeine Schema und das Schema für Die Untersuchung und Reaktion auf Bedrohungen für Defender für [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) um mehr über bestimmte Arten von Daten zu erfahren, die über die Office 365-Verwaltungsaktivitäts-API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="acda7-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="acda7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acda7-121">See also</span></span>

- [<span data-ttu-id="acda7-122">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="acda7-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="acda7-123">Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acda7-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
