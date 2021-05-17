---
title: Internetwebsites in Microsoft Azure mit SharePoint Server 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 0d93ff4a-8fbd-42b8-9227-d817dba0046d
description: Dieser Artikel enthält Ressourcen zum Entwerfen und Implementieren von Sharepoint Server 2013-Internetwebsites, die in Azure Infrastructure Services gehostet werden.
ms.openlocfilehash: f6c7bec1dccc48c1080f76c30bb31b98a473f66e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909762"
---
# <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a><span data-ttu-id="72e5a-103">Internetwebsites in Microsoft Azure mit SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e5a-103">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>

 <span data-ttu-id="72e5a-104">Internetwebsites, die SharePoint Server 2013 verwenden, profitieren davon, dass sie in Azure Infrastructure Services gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="72e5a-104">Internet sites that use SharePoint Server 2013 benefit by being hosted in Azure Infrastructure Services.</span></span> <span data-ttu-id="72e5a-105">Dieser Artikel bietet Ressourcen für den Entwurf und die Implementierung dieser Lösung.</span><span class="sxs-lookup"><span data-stu-id="72e5a-105">This article provides resources for designing and implementing this solution.</span></span>

## <a name="using-azure-infrastructure-services-for-internet-sites"></a><span data-ttu-id="72e5a-106">Verwenden von Windows Azure-Infrastrukturdiensten für Internetwebsites</span><span class="sxs-lookup"><span data-stu-id="72e5a-106">Using Azure Infrastructure Services for Internet sites</span></span>

<span data-ttu-id="72e5a-p102">Microsoft Azure bietet eine überzeugende Möglichkeit für das Hosting von Internetwebsites, die auf SharePoint Server 2013 basieren. Es ergeben sich folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="72e5a-p102">Microsoft Azure provides a compelling option for hosting Internet sites based on SharePoint Server 2013. Advantages include the following:</span></span>

- <span data-ttu-id="72e5a-109">Konzentration auf die Entwicklung einer überzeugenden Website anstatt auf den Aufbau von Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="72e5a-109">Focus on developing a great site instead of building infrastructure.</span></span>

- <span data-ttu-id="72e5a-110">Flexibilität bei der Skalierung der Lösung entsprechend der Nachfrage</span><span class="sxs-lookup"><span data-stu-id="72e5a-110">Flexibility to scale your solution based on demand by scaling out and in.</span></span>

- <span data-ttu-id="72e5a-111">Gebühren ausschließlich für die Ressourcen, die Sie benötigen und verwenden</span><span class="sxs-lookup"><span data-stu-id="72e5a-111">Pay only for the resources that you need and use.</span></span>

- <span data-ttu-id="72e5a-112">Nutzung von Azure Active Directory für Kundenkonten</span><span class="sxs-lookup"><span data-stu-id="72e5a-112">Take advantage of Azure Active Directory for customer accounts.</span></span>

- <span data-ttu-id="72e5a-113">Fügen Sie Features hinzu, die derzeit nicht in Microsoft 365 verfügbar sind, z. B. tiefe Berichte und Analysen.</span><span class="sxs-lookup"><span data-stu-id="72e5a-113">Add features that are not currently available in Microsoft 365, such as deep reporting and analytics.</span></span>

## <a name="resources"></a><span data-ttu-id="72e5a-114">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="72e5a-114">Resources</span></span>

<span data-ttu-id="72e5a-115">Die folgenden technischen Abbildungen und Artikel bieten Informationen zum Entwerfen und Implementieren von Internetwebsites in Azure mit SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72e5a-115">The following technical illustrations and articles provide information about how to design and implement Internet sites in Azure by using SharePoint Server 2013.</span></span>

|<span data-ttu-id="72e5a-116">Ressource</span><span class="sxs-lookup"><span data-stu-id="72e5a-116">Resource</span></span>|<span data-ttu-id="72e5a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72e5a-117">More information</span></span>|
|---|---|
|<span data-ttu-id="72e5a-118">**SharePoint Server 2013-Internetwebsites in Azure**</span><span class="sxs-lookup"><span data-stu-id="72e5a-118">**SharePoint Server 2013 Internet sites in Azure**</span></span> <br/> <span data-ttu-id="72e5a-119">[![Bild der Internetwebsites in Azure mit SharePoint](../media/MS-AZ-SPInternetSites.jpg)](https://go.microsoft.com/fwlink/p/?LinkId=392552)</span><span class="sxs-lookup"><span data-stu-id="72e5a-119">[![Image of Internet sites in Azure using SharePoint](../media/MS-AZ-SPInternetSites.jpg)](https://go.microsoft.com/fwlink/p/?LinkId=392552)</span></span> <br/> <span data-ttu-id="72e5a-120">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)</span><span class="sxs-lookup"><span data-stu-id="72e5a-120">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)</span></span>|<span data-ttu-id="72e5a-121">Dieses Architekturmodell zeigt wichtige Entwurfsaktivitäten und empfohlene Architekturentscheidungen für Internetwebsites in Azure.</span><span class="sxs-lookup"><span data-stu-id="72e5a-121">This architecture model outlines key design activities and recommended architecture choices for Internet sites in Azure.</span></span>|
|<span data-ttu-id="72e5a-122">**Entwurfsbeispiel: Internetwebsites in Azure für SharePoint Server 2013**</span><span class="sxs-lookup"><span data-stu-id="72e5a-122">**Design sample: Internet Sites in Azure for SharePoint Server 2013**</span></span> <br/> <span data-ttu-id="72e5a-123">[ ![ Abbildung des Entwurfsbeispiels: Internetwebsites in Microsoft Azure für SharePoint 2013 ](../media/MS-AZ-InternetSitesDesignSample.jpg) ]</span><span class="sxs-lookup"><span data-stu-id="72e5a-123">[![Image of the Design sample: Internet sites in Microsoft Azure for SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)]</span></span> <br/> <span data-ttu-id="72e5a-124">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)</span><span class="sxs-lookup"><span data-stu-id="72e5a-124">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)</span></span>|<span data-ttu-id="72e5a-125">Verwenden Sie dieses Entwurfsbeispiel als Ausgangspunkt für Ihre eigene Architektur.</span><span class="sxs-lookup"><span data-stu-id="72e5a-125">Use this design sample as a starting point for your own architecture.</span></span>|
|<span data-ttu-id="72e5a-126">**[Microsoft Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)**</span><span class="sxs-lookup"><span data-stu-id="72e5a-126">**[Microsoft Azure Architectures for SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)**</span></span> <br/> |<span data-ttu-id="72e5a-127">In diesem Artikel wird beschrieben, wie Sie Azure-Architekturen zum Hosten von SharePoint-Lösungen entwerfen.</span><span class="sxs-lookup"><span data-stu-id="72e5a-127">This article describes how to design Azure architectures to host SharePoint solutions.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="72e5a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e5a-128">See Also</span></span>

[<span data-ttu-id="72e5a-129">Microsoft 365-Lösungs- und Architekturcenter</span><span class="sxs-lookup"><span data-stu-id="72e5a-129">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)