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
description: Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, die Ihnen mitteilen, wie Sie die Leistung von Exchange Online verbessern können.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909442"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="e6892-103">Optimieren der Leistung von Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6892-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="e6892-104">Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, die Ihnen mitteilen, wie Sie die Leistung von Exchange Online verbessern können, insbesondere vor einer Migration.</span><span class="sxs-lookup"><span data-stu-id="e6892-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="e6892-105">Dieser Artikel ist Teil des [Projekts Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="e6892-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="e6892-106">Zu berücksichtigende Dinge zur Verbesserung der Exchange Online-Leistung</span><span class="sxs-lookup"><span data-stu-id="e6892-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="e6892-107">Um die Geschwindigkeit der Migration zu verbessern und die Bandbreiteneinschränkungen Ihrer Organisation für Exchange Online zu reduzieren, sollten Sie Folgendes beachten:</span><span class="sxs-lookup"><span data-stu-id="e6892-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="e6892-108">**Reduzieren Sie die Postfachgrößen.**</span><span class="sxs-lookup"><span data-stu-id="e6892-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="e6892-109">Die geringere Postfachgröße verbessert die Migrationsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="e6892-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="e6892-110">**Verwenden Sie die Postfach verschieben-Funktionen mit einer Exchange-Hybridbereitstellung.**</span><span class="sxs-lookup"><span data-stu-id="e6892-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="e6892-111">Bei einer Exchange-Hybridbereitstellung werden Offline-E-Mails (in Form von . OST-Dateien) erfordert keinen erneuten Download bei der Migration zu Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6892-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="e6892-112">Dadurch werden die Anforderungen an die Downloadbandbreite erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="e6892-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="e6892-113">**Planen Sie, dass Postfachbewegungen in Zeiten mit geringem Internetverkehr und geringer lokalen Exchange-Nutzung stattfinden.**</span><span class="sxs-lookup"><span data-stu-id="e6892-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="e6892-114">Beim Planen von Verschieben werden Migrationsanforderungen an den Postfachreplikationsproxy übermittelt und werden möglicherweise nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e6892-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="e6892-115">**Verwenden Sie schlanke Popouts für Outlook im Web.**</span><span class="sxs-lookup"><span data-stu-id="e6892-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="e6892-116">Schlanke Popouts bieten kleinere, weniger arbeitsspeicherintensive Versionen bestimmter E-Mail-Nachrichten in Microsoft Edge oder Internet Explorer, indem einige Komponenten auf dem Server gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="e6892-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="e6892-117">Weitere Informationen finden Sie unter Verwenden von schlanken Popouts zum Reduzieren des beim [Lesen von E-Mail-Nachrichten verwendeten Arbeitsspeichers.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)</span><span class="sxs-lookup"><span data-stu-id="e6892-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="e6892-118">Allgemeine Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6892-118">General advice</span></span>

- <span data-ttu-id="e6892-119">Stellen Sie sicher, dass die DNS-Suche nach outlook.office.com das MS-Datencenter an einem logischen Eintragsspeicherort für Ihren Standort einbetritt.</span><span class="sxs-lookup"><span data-stu-id="e6892-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="e6892-120">Suchen Sie das Zwischenspeichern von Postfächern, und wählen Sie die entsprechenden Optionen (re.</span><span class="sxs-lookup"><span data-stu-id="e6892-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="e6892-121">Zwischenspeicherungszeitraum, Zwischenspeicherung freigegebener Postfächer usw.).</span><span class="sxs-lookup"><span data-stu-id="e6892-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="e6892-122">Halten Sie Ihre Outlook-Daten davon ab, VPN-Verbindungen (an eine Zentralstelle) zu übergeben, bevor sie über das Internet übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e6892-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="e6892-123">Achten Sie darauf, dass Ihre Postfachdaten die Einschränkungen für Ordner- und Elementbeträge einhalten.</span><span class="sxs-lookup"><span data-stu-id="e6892-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="e6892-124">Weitere Informationen zur Leistung der Exchange-Migration finden Sie unter [Office 365-Migrationsleistung und bewährte Methoden](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span><span class="sxs-lookup"><span data-stu-id="e6892-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
