---
title: Aktivieren von SharePoint Multi-Geo am Satellitenstandort
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Dieser Artikel enthält Informationen für globale oder SharePoint Administratoren zum Aktivieren SharePoint Multi-Geo in geografischen Satellitenstandorten.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690856"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="f3dc0-103">Aktivieren von SharePoint Multi-Geo am Satellitenstandort</span><span class="sxs-lookup"><span data-stu-id="f3dc0-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="f3dc0-104">Dieser Artikel richtet sich an globale oder SharePoint-Administratoren, die einen Multi-Geo-Satellitenstandort erstellt haben, **bevor** SharePoint Multi-Geo-Funktionen am 27. März 2019 allgemein zur Verfügung gestellt wurden, und SharePoint Multi-Geo nicht an ihrem Satellitenstandort aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="f3dc0-105">Wenn Sie einen neuen geografischen Standort **nach dem 27. März** hinzugefügt haben, müssen Sie die folgenden Anweisungen nicht befolgen, da Ihr neuer geografischer Standort bereits für OneDrive und SharePoint Multi-Geo aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="f3dc0-106">Anhand dieser Anweisungen können Sie SharePoint an Ihrem Satellitenstandort aktivieren, sodass Multi-Geo-Satellitenbenutzer sowohl von OneDrive als auch von SharePoint Multi-Geo-Funktionen in Office 365 profitieren können.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="f3dc0-107">Beachten Sie, dass dies eine unidirektionale Aktivierung ist.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="f3dc0-108">Sobald der SPO-Modus festgelegt wurde, können Sie nicht mehr zum OneDrive Multi-Geo-Modus ohne eine Eskalation an den Support wechseln.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="f3dc0-109">So legen Sie den SPO-Modus für einen geografischen Standort fest</span><span class="sxs-lookup"><span data-stu-id="f3dc0-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="f3dc0-110">Um den SPO-Modus für einen geografischen Standort festzulegen, stellen Sie eine Verbindung zu dem geografischen Standort fest, für den der SPO-Modus festgelegt werden soll:</span><span class="sxs-lookup"><span data-stu-id="f3dc0-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="f3dc0-111">Öffnen Sie die SharePoint Online-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="f3dc0-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span><span class="sxs-lookup"><span data-stu-id="f3dc0-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="f3dc0-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="f3dc0-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="f3dc0-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="f3dc0-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="f3dc0-115">Dieser Vorgang nimmt in der Regel etwa eine Stunde in Anspruch. Es werden verschiedene Veröffentlichungen im Dienst zurückgenommen, und der Mandant erhält einen neuen Stempel.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="f3dc0-116">Warten Sie mindestens eine Stunde, und führen Sie dann Get-SPOMultiGeoExperience aus.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="f3dc0-117">Mit diesem Befehl wird angezeigt, ob dieser geografische Standort den SPO-Modus aufweist.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="f3dc0-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="f3dc0-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="f3dc0-119">Bestimmte Caches im Dienst werden alle 24 Stunden aktualisiert. Es kann also sein, dass sich Ihr Satellitenstandort bis zu 24 Stunden zeitweise so verhält, als wäre immer noch der ODB-Modus für diesen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="f3dc0-120">Dies verursacht keine technischen Probleme.</span><span class="sxs-lookup"><span data-stu-id="f3dc0-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="f3dc0-121">Weitere Informationen zu SharePoint Multi-Geo finden Sie unter [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc0-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


