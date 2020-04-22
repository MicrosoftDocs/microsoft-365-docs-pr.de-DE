---
title: Durchsuchen des Überwachungsprotokolls nach Benutzer-und Administratoraktivitäten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'Das Überwachungsprotokoll ist ein einheitliches Überwachungsprotokoll. Warum ein einheitliches Überwachungsprotokoll? Da Ereignisse von den meisten Diensten, die Ihre Organisation abonniert, in einem einzigen Überwachungsprotokoll aufgezeichnet werden, das Sie durchsuchen können. Das bedeutet, dass Sie in diesen Diensten nach Benutzer-und Administratoraktivitäten suchen können:'
ms.openlocfilehash: 95f5025e4831223c93251c7c22d1f43d44086d48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625095"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="0fa99-106">Durchsuchen des Überwachungsprotokolls nach Benutzer-und Administratoraktivitäten</span><span class="sxs-lookup"><span data-stu-id="0fa99-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="0fa99-107">Das Überwachungsprotokoll ist ein einheitliches Überwachungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="0fa99-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="0fa99-108">Warum ein einheitliches Überwachungsprotokoll?</span><span class="sxs-lookup"><span data-stu-id="0fa99-108">Why a unified audit log?</span></span> <span data-ttu-id="0fa99-109">Da Ereignisse von den meisten Diensten, die Sie als Organisation abonniert haben, in einem einzigen Überwachungsprotokoll aufgezeichnet werden, das Sie durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="0fa99-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="0fa99-110">Das bedeutet, dass Sie in diesen Diensten nach Benutzer-und Administratoraktivitäten suchen können:</span><span class="sxs-lookup"><span data-stu-id="0fa99-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="0fa99-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0fa99-111">SharePoint</span></span>
- <span data-ttu-id="0fa99-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0fa99-112">OneDrive</span></span>
- <span data-ttu-id="0fa99-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="0fa99-113">Exchange</span></span>
- <span data-ttu-id="0fa99-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0fa99-114">Azure Active Directory</span></span>
- <span data-ttu-id="0fa99-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0fa99-115">Microsoft Teams</span></span>
- <span data-ttu-id="0fa99-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0fa99-116">eDiscovery</span></span>
- <span data-ttu-id="0fa99-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="0fa99-117">Power BI</span></span>
- <span data-ttu-id="0fa99-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="0fa99-118">Yammer</span></span>
- <span data-ttu-id="0fa99-119">Sway</span><span class="sxs-lookup"><span data-stu-id="0fa99-119">Sway</span></span>
- <span data-ttu-id="0fa99-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="0fa99-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="0fa99-121">Einrichten der Überwachung</span><span class="sxs-lookup"><span data-stu-id="0fa99-121">Set up auditing</span></span>
  
<span data-ttu-id="0fa99-122">Es gibt nur wenige Schritte, die Sie ausführen müssen, bevor Sie das Überwachungsprotokoll durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="0fa99-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="0fa99-123">[Aktivieren Sie die Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md) , um die Aufzeichnung von Ereignissen zu starten, nach denen Sie suchen können.</span><span class="sxs-lookup"><span data-stu-id="0fa99-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="0fa99-124">[Aktivieren der postfachüberwachung](enable-mailbox-auditing.md) , damit Sie nach Post fachbezogenen Ereignissen suchen können; beispielsweise wenn sich ein Benutzer bei seinem Postfach anmeldet oder Elemente aus dem Ordner "refundable Items" löscht.</span><span class="sxs-lookup"><span data-stu-id="0fa99-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="0fa99-125">Durchsuchen des Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="0fa99-125">Search the audit log</span></span>
  
<span data-ttu-id="0fa99-126">Nachdem Sie die Überwachung aktiviert haben, suchen Sie nach Hunderten von einzelnen Ereignistypen aus mehreren Microsoft 365-Diensten.</span><span class="sxs-lookup"><span data-stu-id="0fa99-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="0fa99-127">[Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md) nach Benutzer-und Administratoraktivitäten</span><span class="sxs-lookup"><span data-stu-id="0fa99-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="0fa99-128">Grund [Legendes zu den detaillierten Eigenschaften](detailed-properties-in-the-office-365-audit-log.md) in jedem Überwachungsdatensatz, der in den Suchergebnissen enthalten ist</span><span class="sxs-lookup"><span data-stu-id="0fa99-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="0fa99-129">[Suchen nach eDiscovery-bezogenen Aktivitäten](search-for-ediscovery-activities-in-the-audit-log.md) , die von Administratoren und Compliance-Managern ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="0fa99-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
