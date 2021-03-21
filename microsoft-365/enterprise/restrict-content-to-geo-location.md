---
title: Einschränken der SharePoint-Websiteinhalte auf einen geografischen Standort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In diesem Artikel erfahren Sie, wie Sie SharePoint-Websites auf einen angegebenen geografischen Standort in einer Multi-Geo-Umgebung beschränken.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927264"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="37393-103">Einschränken der SharePoint-Websiteinhalte auf einen geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="37393-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="37393-104">Unter bestimmten Umständen können Sie möglicherweise erzwingen, dass eine Seite und Ihre Inhalte an dem geographischen Standort verbleiben, an dem Sie erstellt wurden. Dies ist möglich, indem Sie entweder die Seite daran hindern, verschoben zu werden, oder indem Sie das Zwischenspeichern der Dateiinhalte der Seite an einem anderen geographischen Standort verhindern.</span><span class="sxs-lookup"><span data-stu-id="37393-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="37393-105">Um dies zu tun, verwenden Sie [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet mit dem Parameter **RestrictedToGeo**.</span><span class="sxs-lookup"><span data-stu-id="37393-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="37393-106">Dieser Parameter hat einen Standardwert von NULL, aber Sie können ihn wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="37393-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="37393-107">Einschränkung</span><span class="sxs-lookup"><span data-stu-id="37393-107">Restriction</span></span>|<span data-ttu-id="37393-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37393-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="37393-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="37393-109">NoRestriction</span></span>|<span data-ttu-id="37393-110">Die Website kann an einen anderen Geo-Standort verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="37393-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="37393-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="37393-111">BlockMoveOnly</span></span>|<span data-ttu-id="37393-112">Seite kann nicht an einen anderen Geo-Standort verschoben werden, aber Seiteninhalte können an einem anderen geografischen Standort zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="37393-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="37393-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="37393-113">BlockFull</span></span>|<span data-ttu-id="37393-114">Seite kann nicht an einen anderen Geo-Standort verschoben werden und der gesamte Seiteninhalt wird nicht an anderen geografischen Standorten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="37393-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="37393-115">Der Titel der Datei (aus dem Inhalt abgerufen), der Dateiname und andere Eigenschaften der Datei können weiterhin an anderen geographischen Standorten zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="37393-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="37393-116">Inhalte, die vor der Konfiguration als BlockFull auf der Seite gespeichert wurden, können möglicherweise weiterhin an anderen geographischen Standorten zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="37393-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="37393-117">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="37393-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="37393-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37393-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`