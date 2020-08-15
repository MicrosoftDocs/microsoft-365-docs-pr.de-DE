---
title: Optimieren der Leistung von Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, in denen Sie erfahren, wie Sie die Leistung von Exchange Online verbessern.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690725"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="afb3f-103">Optimieren der Leistung von Exchange Online</span><span class="sxs-lookup"><span data-stu-id="afb3f-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="afb3f-104">Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, in denen Sie erfahren, wie Sie die Leistung von Exchange Online verbessern, insbesondere vor einer Migration.</span><span class="sxs-lookup"><span data-stu-id="afb3f-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="afb3f-105">Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune) -Projekt.</span><span class="sxs-lookup"><span data-stu-id="afb3f-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="afb3f-106">Dinge, die Sie beachten sollten, um Exchange Online Leistung zu verbessern</span><span class="sxs-lookup"><span data-stu-id="afb3f-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="afb3f-107">Um die Geschwindigkeit der Migration zu verbessern und die Bandbreiteneinschränkungen Ihrer Organisation für Exchange Online zu reduzieren, sollten Sie folgendes befolgen:</span><span class="sxs-lookup"><span data-stu-id="afb3f-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="afb3f-108">**Verringern der Postfachgröße**</span><span class="sxs-lookup"><span data-stu-id="afb3f-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="afb3f-109">Die geringere Postfachgröße verbessert die Migrations Geschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="afb3f-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="afb3f-110">**Verwenden Sie die Post Fach Verschiebefunktionen mit einer Exchange-hybridbereitstellung.**</span><span class="sxs-lookup"><span data-stu-id="afb3f-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="afb3f-111">Bei einer Exchange-hybridbereitstellung werden Offline Nachrichten (in Form von. Ost-Dateien) erfordert keinen erneuten Download bei der Migration zu Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="afb3f-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="afb3f-112">Dadurch werden die Anforderungen an die Download Bandbreite erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="afb3f-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="afb3f-113">**Planen von Postfachverschiebungen, die während Zeiträumen mit niedrigem Internet Datenverkehr und niedriger lokaler Exchange-Nutzung ausgeführt werden.**</span><span class="sxs-lookup"><span data-stu-id="afb3f-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="afb3f-114">Beim Planen von Verschiebungen werden Migrationsanforderungen an den Proxy für die Post Fach Replikation übermittelt und möglicherweise nicht sofort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="afb3f-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="afb3f-115">**Verwenden Sie Lean Popouts für Outlook im Internet.**</span><span class="sxs-lookup"><span data-stu-id="afb3f-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="afb3f-116">Lean-Popouts bieten kleinere, weniger arbeitsspeicherintensive Versionen bestimmter e-Mail-Nachrichten in Microsoft Edge oder Internet Explorer, indem einige Komponenten auf dem Server gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="afb3f-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="afb3f-117">Weitere Informationen finden Sie unter [Verwenden von Lean Popouts zum Reduzieren des beim Lesen von e-Mail-Nachrichten verwendeten Arbeitsspeichers](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="afb3f-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="afb3f-118">Allgemeine Ratschläge</span><span class="sxs-lookup"><span data-stu-id="afb3f-118">General advice</span></span>

- <span data-ttu-id="afb3f-119">Stellen Sie sicher, dass DNS-Lookup für Outlook.Office.com das MS-Datacenter an einem logischen eintragsort für Ihren Standort eingibt.</span><span class="sxs-lookup"><span data-stu-id="afb3f-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="afb3f-120">Recherchieren Sie die Post Fach Zwischenspeicherung, und wählen Sie die entsprechenden Optionen aus (Re.</span><span class="sxs-lookup"><span data-stu-id="afb3f-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="afb3f-121">zwischen Speicherungszeitraum, Zwischenspeicherung von freigegebenen Postfächern, usw.).</span><span class="sxs-lookup"><span data-stu-id="afb3f-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="afb3f-122">Halten Sie Ihre Outlook-Daten davon ab, VPN-Verbindungen (an ein zentrales Büro) weiterzugeben, bevor Sie über das Internet übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="afb3f-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="afb3f-123">Stellen Sie sicher, dass die Postfachdaten den Einschränkungen für Ordner und Element, Beträge entsprechen.</span><span class="sxs-lookup"><span data-stu-id="afb3f-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="afb3f-124">Weitere Informationen zur Leistung der Exchange-Migration finden Sie unter [Office 365 Migrationsleistung und bewährte Methoden](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span><span class="sxs-lookup"><span data-stu-id="afb3f-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  

