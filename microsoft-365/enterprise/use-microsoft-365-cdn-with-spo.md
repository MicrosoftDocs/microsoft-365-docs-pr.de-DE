---
title: Verwenden von Office 365 Content Delivery Network (CDN) mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Erfahren Sie, wie Sie die Office 365 Content Delivery Network (CDN) verwenden, um die Bereitstellung Ihrer SharePoint Online-Ressourcen zu beschleunigen.
ms.openlocfilehash: e6cce93be0e8d893d68ae8bcdb15fde325a2cb59
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169556"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="9848c-103">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="9848c-104">Sie können statische Objekte im Office 365-Netzwerk für die Inhaltsübermittlung (CDN) hosten, um eine bessere Leistung für Ihre SharePoint Online-Seiten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9848c-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="9848c-105">Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="9848c-106">Außerdem verwendet das Office 365 CDN das [HTTP/2-Protokoll](https://en.wikipedia.org/wiki/HTTP/2) für eine verbesserte Komprimierung und HTTP-Pipelining.</span><span class="sxs-lookup"><span data-stu-id="9848c-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="9848c-107">Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.</span><span class="sxs-lookup"><span data-stu-id="9848c-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-108">Die Office 365 CDN ist nur für Mandanten in der **Produktionscloud** (weltweit) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9848c-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="9848c-109">Mandanten in den Clouds von US-Behörden, China und Deutschland unterstützen derzeit die Office 365 CDN nicht.</span><span class="sxs-lookup"><span data-stu-id="9848c-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="9848c-110">Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="9848c-111">In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="9848c-112">Weitere Informationen zum Unterschied zwischen öffentlichen und privaten Ursprüngen finden Sie unter ["Auswählen, ob jeder Ursprung öffentlich oder privat sein soll".](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="9848c-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="9848c-113">![Office 365 CDN konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN konzeptionelles Diagramm")</span><span class="sxs-lookup"><span data-stu-id="9848c-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="9848c-114">Wenn Sie bereits mit der Funktionsweise von CDNs vertraut sind, müssen Sie nur einige Schritte ausführen, um die Office 365 CDN für Ihren Mandanten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="9848c-115">In diesem Thema wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="9848c-115">This topic describes how.</span></span> <span data-ttu-id="9848c-116">Lesen Sie weiter, um Informationen zu den ersten Schritten beim Hosten ihrer statischen Objekte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9848c-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="9848c-117">Es gibt andere von Microsoft gehostete CDNs, die mit Office 365 für spezielle Verwendungsszenarien verwendet werden können, aber in diesem Thema nicht behandelt werden, da sie nicht in den Bereich der Office 365 CDN fallen.</span><span class="sxs-lookup"><span data-stu-id="9848c-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="9848c-118">Weitere Informationen finden Sie unter [Andere Microsoft CDNs.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="9848c-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="9848c-119">**Kehren Sie zur [Netzwerkplanung und Leistungsoptimierung für Office 365](./network-planning-and-performance.md)zurück.**</span><span class="sxs-lookup"><span data-stu-id="9848c-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="9848c-120">Übersicht über die Arbeit mit den Office 365 CDN in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="9848c-121">Führen Sie die folgenden grundlegenden Schritte aus, um die Office 365 CDN für Ihre Organisation einzurichten:</span><span class="sxs-lookup"><span data-stu-id="9848c-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="9848c-122">Planen der Bereitstellung der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="9848c-123">[Bestimmen Sie, welche statischen Objekte auf dem CDN gehostet werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="9848c-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="9848c-124">[Bestimmen Sie, wo Ihre Objekte gespeichert werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="9848c-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="9848c-125">Dieser Speicherort kann eine SharePoint Website, Bibliothek oder Ordner sein und wird als _Ursprung_ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9848c-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="9848c-126">[Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="9848c-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="9848c-127">Sie können mehrere Ursprünge von öffentlichen und privaten Typen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="9848c-128">Einrichten und Konfigurieren der CDN mithilfe von PowerShell oder der SharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="9848c-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="9848c-129">Einrichten und Konfigurieren der CDN mithilfe der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9848c-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="9848c-130">Einrichten und Konfigurieren der CDN mithilfe von PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="9848c-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="9848c-131">Einrichten und Konfigurieren der CDN mithilfe der Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="9848c-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="9848c-132">Wenn Sie diesen Schritt abschließen, haben Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9848c-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="9848c-133">Die CDN für Ihre Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9848c-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="9848c-134">Ihre Ursprünge hinzugefügt, wobei jeder Ursprung als öffentlich oder privat identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="9848c-135">Sobald Sie mit der Einrichtung fertig sind, können Sie die Office 365 CDN im Laufe der Zeit [verwalten,](use-microsoft-365-cdn-with-spo.md#CDNManage) indem Sie:</span><span class="sxs-lookup"><span data-stu-id="9848c-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="9848c-136">Hinzufügen, Aktualisieren und Entfernen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="9848c-137">Hinzufügen und Entfernen von Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-137">Adding and removing origins</span></span>
+ <span data-ttu-id="9848c-138">Konfigurieren CDN Richtlinien</span><span class="sxs-lookup"><span data-stu-id="9848c-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="9848c-139">Falls erforderlich, deaktivieren Sie die CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="9848c-140">Weitere Informationen zum Zugriff auf Ihre CDN Ressourcen von öffentlichen und privaten Ursprüngen finden Sie unter ["Verwenden Ihrer CDN-Ressourcen".](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)</span><span class="sxs-lookup"><span data-stu-id="9848c-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="9848c-141">Anleitungen zum Beheben allgemeiner Probleme finden Sie unter ["Problembehandlung der Office 365 CDN".](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="9848c-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="9848c-142">Planen der Bereitstellung der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="9848c-143">Bevor Sie die Office 365 CDN für Ihren Office 365 Mandanten bereitstellen, sollten Sie die folgenden Faktoren im Rahmen Ihres Planungsprozesses berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9848c-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="9848c-144">Bestimmen, welche statischen Objekte auf dem CDN gehostet werden sollen</span><span class="sxs-lookup"><span data-stu-id="9848c-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="9848c-145">Bestimmen, wo Ihre Ressourcen gespeichert werden sollen</span><span class="sxs-lookup"><span data-stu-id="9848c-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="9848c-146">Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="9848c-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="9848c-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="9848c-148">Bestimmen Sie, welche statischen Objekte auf dem CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9848c-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="9848c-149">Im Allgemeinen sind CDNs am effektivsten für das Hosten _statischer Objekte_ oder Objekte, die sich nicht sehr oft ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="9848c-150">Eine gute Faustregel besteht darin, Dateien zu identifizieren, die einige oder alle dieser Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9848c-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="9848c-151">Statische Dateien, die in eine Seite eingebettet sind (z. B. Skripts und Bilder), die erhebliche inkrementelle Auswirkungen auf die Seitenladezeiten haben können</span><span class="sxs-lookup"><span data-stu-id="9848c-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="9848c-152">Große Dateien wie ausführbare Dateien und Installationsdateien</span><span class="sxs-lookup"><span data-stu-id="9848c-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="9848c-153">Ressourcenbibliotheken, die clientseitigen Code unterstützen</span><span class="sxs-lookup"><span data-stu-id="9848c-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="9848c-154">Beispielsweise können kleine Dateien, die wiederholt angefordert werden, z. B. Websiteimages und Skripts, die Leistung beim Rendern von Websites erheblich verbessern und die Last auf Ihren SharePoint Onlinewebsites inkrementell reduzieren, wenn Sie sie einem CDN Ursprung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="9848c-155">Größere Dateien, z. B. ausführbare Installationsdateien, können aus dem CDN heruntergeladen werden, was sich positiv auf die Leistung auswirkt und die Last auf Ihrer SharePoint Onlinewebsite verringert, auch wenn nicht so häufig auf sie zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="9848c-156">Die Leistungsverbesserung auf Dateibasis hängt von vielen Faktoren ab, einschließlich der Nähe des Clients zum nächstgelegenen CDN Endpunkt, vorübergehenden Bedingungen im lokalen Netzwerk usw.</span><span class="sxs-lookup"><span data-stu-id="9848c-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="9848c-157">Viele statische Dateien sind recht klein und können in weniger als einer Sekunde von Office 365 heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="9848c-158">Eine Webseite kann jedoch viele eingebettete Dateien mit einer kumulativen Downloadzeit von mehreren Sekunden enthalten.</span><span class="sxs-lookup"><span data-stu-id="9848c-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="9848c-159">Die Bereitstellung dieser Dateien aus dem CDN kann die Gesamtladezeit der Seite erheblich reduzieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="9848c-160">Sehen Sie sich [an, welche Leistungsvorteile ein CDN bietet?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9848c-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="9848c-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="9848c-162">Bestimmen, wo Ihre Ressourcen gespeichert werden sollen</span><span class="sxs-lookup"><span data-stu-id="9848c-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="9848c-163">Die CDN ruft Ihre Objekte von einem Speicherort ab, der als Ursprung bezeichnet _wird._</span><span class="sxs-lookup"><span data-stu-id="9848c-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="9848c-164">Ein Ursprung kann eine SharePoint Website, Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="9848c-165">Sie haben große Flexibilität, wenn Sie Ursprünge für Ihre Organisation angeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="9848c-166">Sie können z. B. mehrere Ursprünge oder einen einzelnen Ursprung angeben, in den Sie alle CDN Ressourcen einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="9848c-167">Sie können sowohl öffentliche als auch private Ursprünge für Ihre Organisation auswählen.</span><span class="sxs-lookup"><span data-stu-id="9848c-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="9848c-168">Die meisten Organisationen entscheiden sich dafür, eine Kombination der beiden zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="9848c-169">Sie können einen neuen Container für Ihre Ursprünge erstellen, z. B. Ordner oder Dokumentbibliotheken, und Dateien hinzufügen, die Sie über die CDN verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="9848c-170">Dies ist ein guter Ansatz, wenn Sie über einen bestimmten Satz von Ressourcen verfügen, die über die CDN verfügbar sein sollen, und den Satz von CDN Ressourcen auf diese Dateien im Container beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="9848c-171">Sie können auch eine vorhandene Websitesammlung, Website, Bibliothek oder einen vorhandenen Ordner als Ursprung konfigurieren, wodurch alle berechtigten Ressourcen im Container über die CDN verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="9848c-172">Bevor Sie einen vorhandenen Container als Ursprung hinzufügen, müssen Sie sicherstellen, dass Sie dessen Inhalte und Berechtigungen kennen, damit Sie Objekte nicht versehentlich für anonymen Zugriff oder nicht autorisierte Benutzer verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="9848c-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="9848c-173">Sie können _CDN Richtlinien_ definieren, um Inhalte in Ihren Ursprüngen von der CDN auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="9848c-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="9848c-174">CDN Richtlinien Ressourcen in öffentlichen oder privaten Ursprüngen durch Attribute wie _Dateityp_ und _Websiteklassifizierung_ ausschließen und auf alle Ursprünge des CdnType (privat oder öffentlich) angewendet werden, die Sie in der Richtlinie angeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="9848c-175">Wenn Sie beispielsweise einen privaten Ursprung hinzufügen, der aus einer Website besteht, die mehrere Unterwebsites enthält, können Sie eine Richtlinie definieren, um Websites auszuschließen, die als **vertraulich** gekennzeichnet sind, damit Inhalte von Websites mit dieser Klassifizierung nicht vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="9848c-176">Die Richtlinie gilt für Inhalte _aller_ privaten Ursprünge, die Sie dem CDN hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="9848c-177">Bedenken Sie, dass je größer die Anzahl der Ursprünge ist, desto größer ist die Auswirkung auf die Zeit, die der CDN Dienst für die Verarbeitung von Anforderungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="9848c-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="9848c-178">Es wird empfohlen, die Anzahl der Ursprünge so weit wie möglich zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="9848c-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="9848c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="9848c-180">Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="9848c-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="9848c-181">Wenn Sie einen Ursprung identifizieren, geben Sie an, ob er _öffentlich_ oder _privat_ sein soll.</span><span class="sxs-lookup"><span data-stu-id="9848c-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="9848c-182">Der Zugriff auf CDN Ressourcen in öffentlichen Ursprüngen ist anonym, und CDN Inhalte in privaten Ursprüngen werden durch dynamisch generierte Token für eine höhere Sicherheit gesichert.</span><span class="sxs-lookup"><span data-stu-id="9848c-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="9848c-183">Unabhängig davon, welche Option Sie auswählen, erledigt Microsoft die gesamte Arbeit, wenn es um die Verwaltung der CDN selbst geht.</span><span class="sxs-lookup"><span data-stu-id="9848c-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="9848c-184">Außerdem können Sie Ihre Meinung später ändern, nachdem Sie die CDN eingerichtet und Ihre Ursprünge identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="9848c-185">Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungsvorteile, weisen jedoch jeweils eindeutige Attribute und Vorteile auf.</span><span class="sxs-lookup"><span data-stu-id="9848c-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="9848c-186">**Öffentliche** Ursprünge innerhalb der Office 365 CDN sind anonym zugänglich, und auf gehostete Objekte kann von jeder Person zugegriffen werden, die über die URL zu dem Objekt verfügt.</span><span class="sxs-lookup"><span data-stu-id="9848c-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="9848c-187">Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder.</span><span class="sxs-lookup"><span data-stu-id="9848c-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="9848c-188">**Private** Ursprünge innerhalb der Office 365 CDN bieten privaten Zugriff auf Benutzerinhalte wie SharePoint Online-Dokumentbibliotheken, Websites und proprietäre Bilder.</span><span class="sxs-lookup"><span data-stu-id="9848c-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="9848c-189">Der Zugriff auf Inhalte in privaten Ursprüngen wird durch dynamisch generierte Token gesichert, sodass nur Benutzer mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den ursprünglichen Speicherort darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9848c-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="9848c-190">Private Ursprünge im Office 365 CDN können nur für SharePoint Onlineinhalte verwendet werden, und Sie können nur über die Umleitung von Ihrem SharePoint Onlinemandanten auf Ressourcen in privaten Ursprüngen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9848c-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="9848c-191">Weitere Informationen dazu, wie CDN Zugriff auf Objekte in einem privaten Ursprung funktioniert, finden Sie unter [Verwendung von Ressourcen in privaten Ursprüngen.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="9848c-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="9848c-192">Attribute und Vorteile des Hostings von Ressourcen in öffentlichen Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="9848c-193">Objekte, die an einem öffentlichen Ursprung verfügbar gemacht werden, sind für jeden Benutzer anonym zugänglich.</span><span class="sxs-lookup"><span data-stu-id="9848c-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="9848c-194">Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung.</span><span class="sxs-lookup"><span data-stu-id="9848c-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="9848c-195">Wenn Sie ein Objekt aus einem öffentlichen Ursprung entfernen, ist es unter Umständen bis zu 30 Tage lang weiterhin über den Cache verfügbar. Links zu dem Objekt im CDN werden jedoch innerhalb von 15 Minuten ungültig.</span><span class="sxs-lookup"><span data-stu-id="9848c-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="9848c-196">Wenn Sie Stylesheets (CSS-Dateien) an einem öffentlichen Ursprung hosten, können Sie im Code relative Pfade und URIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="9848c-197">Dies bedeutet, dass Sie auf den Speicherort von Hintergrundbildern und anderen Objekten relativ zum Speicherort des Objekts, das sie aufruft, verweisen können.</span><span class="sxs-lookup"><span data-stu-id="9848c-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="9848c-198">Während Sie die URL eines öffentlichen Ursprungs erstellen können, sollten Sie mit Vorsicht vorgehen und sicherstellen, dass Sie die Seitenkontexteigenschaft verwenden und die Anleitung dazu befolgen.</span><span class="sxs-lookup"><span data-stu-id="9848c-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="9848c-199">Der Grund hierfür ist folgender: Wenn der Zugriff auf das CDN nicht mehr verfügbar ist, wird die URL nicht automatisch auf Ihre Organisation in SharePoint Online aufgelöst, was zu fehlerhaften Links und anderen Fehlern führen kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="9848c-200">Die URL kann auch geändert werden, weshalb sie nicht nur hartcodiert werden sollte, um ihren aktuellen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="9848c-201">Die Standarddateitypen, die für öffentliche Ursprünge enthalten sind, sind CSS, EOT, .gif, ICO, JPEG, .jpg, .js, MAP, .png, SVG, TTF, WOFF und WOFF2.</span><span class="sxs-lookup"><span data-stu-id="9848c-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="9848c-202">Sie können zusätzliche Dateitypen angeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="9848c-203">Sie können eine Richtlinie so konfigurieren, dass Ressourcen ausgeschlossen werden, die durch von Ihnen angegebene Websiteklassifizierungen identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="9848c-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="9848c-204">Beispielsweise können Sie alle Objekte ausschließen, die als „vertraulich“ oder „eingeschränkt“ gekennzeichnet sind, auch wenn sie einen zulässigen Dateityp haben und sich an einem öffentlichen Ursprung befinden.</span><span class="sxs-lookup"><span data-stu-id="9848c-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="9848c-205">Attribute und Vorteile des Hostings von Ressourcen in privaten Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="9848c-206">Private Ursprünge können nur für SharePoint Onlineressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="9848c-207">Benutzer können nur von einem privaten Ursprung aus auf die Objekte zugreifen, wenn sie über Berechtigungen für den Zugriff auf den Container verfügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="9848c-208">Der anonyme Zugriff auf diese Objekte wird verhindert.</span><span class="sxs-lookup"><span data-stu-id="9848c-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="9848c-209">Auf Objekte in privaten Ursprüngen muss vom SharePoint Onlinemandanten verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="9848c-210">Der direkte Zugriff auf private CDN Ressourcen funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="9848c-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="9848c-211">Wenn Sie eine Ressource aus dem privaten Ursprung entfernen, ist die Ressource möglicherweise bis zu einer Stunde lang aus dem Cache verfügbar. Links zu der Ressource im CDN werden jedoch innerhalb von 15 Minuten nach dem Entfernen der Ressource ungültig.</span><span class="sxs-lookup"><span data-stu-id="9848c-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="9848c-212">Die standardmäßigen Dateitypen, die für private Ursprünge eingeschlossen werden, sind GIF, ICO, JPEG, JPG, JS und PNG.</span><span class="sxs-lookup"><span data-stu-id="9848c-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="9848c-213">Sie können zusätzliche Dateitypen angeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="9848c-214">Genau wie bei öffentlichen Ursprüngen können Sie eine Richtlinie so konfigurieren, dass Ressourcen ausgeschlossen werden, die durch von Ihnen angegebene Websiteklassifizierungen identifiziert wurden, auch wenn Sie Platzhalter verwenden, um alle Ressourcen in einen Ordner oder eine Dokumentbibliothek einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9848c-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="9848c-215">Weitere Informationen dazu, warum Sie die Office 365 CDN, allgemeine CDN Konzepte und andere Microsoft CDNs verwenden, die Sie mit Ihrem Office 365 Mandanten verwenden können, finden Sie unter [Content Delivery Networks](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="9848c-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="9848c-216">Standardmäßige CDN Ursprünge</span><span class="sxs-lookup"><span data-stu-id="9848c-216">Default CDN origins</span></span>

<span data-ttu-id="9848c-217">Wenn Sie nichts anderes angeben, richten Office 365 einige Standardursprungseinträge für Sie ein, wenn Sie die Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="9848c-218">Wenn Sie sich zunächst dafür entscheiden, sie nicht bereitzustellen, können Sie diese Ursprünge nach Abschluss der Einrichtung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="9848c-219">Wenn Sie die Folgen des Überspringens der Einrichtung der Standardursprungs nicht verstehen und einen bestimmten Grund dafür haben, sollten Sie zulassen, dass sie erstellt werden, wenn Sie die CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="9848c-220">Standardmäßige private CDN Ursprünge:</span><span class="sxs-lookup"><span data-stu-id="9848c-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="9848c-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="9848c-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="9848c-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="9848c-222">\*/siteassets</span></span>

<span data-ttu-id="9848c-223">Standardmäßige öffentliche CDN Ursprünge:</span><span class="sxs-lookup"><span data-stu-id="9848c-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="9848c-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="9848c-224">\*/masterpage</span></span>
+ <span data-ttu-id="9848c-225">\*/style library</span><span class="sxs-lookup"><span data-stu-id="9848c-225">\*/style library</span></span>
+ <span data-ttu-id="9848c-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="9848c-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span><span class="sxs-lookup"><span data-stu-id="9848c-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="9848c-228">Dieser Ursprung muss vorhanden sein, damit SharePoint-Framework Lösungen im CDN funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="9848c-229">Wenn Sie die Office 365 CDN vor Dezember 2017 aktiviert oder die Einrichtung der Standardursprungs beim Aktivieren der CDN übersprungen haben, können Sie diesen Ursprung manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="9848c-230">Weitere Informationen finden Sie unter ["Mein clientseitiges Webpart" oder SharePoint-Framework Lösung nicht funktioniert.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="9848c-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="9848c-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="9848c-232">Einrichten und Konfigurieren der Office 365 CDN mithilfe der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9848c-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="9848c-233">Für die Verfahren in diesem Abschnitt müssen Sie die SharePoint Online-Verwaltungsshell verwenden, um eine Verbindung mit SharePoint Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9848c-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="9848c-234">Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="9848c-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="9848c-235">Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Ressourcen in SharePoint Online mithilfe der SharePoint Online-Verwaltungsshell einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="9848c-236">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="9848c-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="9848c-237">Ermöglichen Sie Ihrer Organisation die Verwendung der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="9848c-238">Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der Konfiguration für private CDN in Ihrem Office 365 Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="9848c-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="9848c-239">Verbinden zu Ihrem Mandanten mithilfe der SharePoint Online-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="9848c-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="9848c-240">Verwenden Sie nun das Cmdlet **"Get-SPOTenantCdnEnabled",** um die CDN Statuseinstellungen vom Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="9848c-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="9848c-241">Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="9848c-242">Verwenden Sie das Cmdlet **"Set-SPOTenantCdnEnabled",** um Ihrer Organisation die Verwendung der Office 365 CDN zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9848c-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="9848c-243">Sie können Ihrer Organisation ermöglichen, öffentliche Ursprünge, private Ursprünge oder beide gleichzeitig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="9848c-244">Sie können auch die CDN konfigurieren, um die Einrichtung der Standardursprungs beim Aktivieren zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="9848c-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="9848c-245">Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9848c-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="9848c-246">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="9848c-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="9848c-247">Geben Sie beispielsweise den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9848c-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="9848c-248">Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen, aber das Einrichten der Standardursprungs zu überspringen:</span><span class="sxs-lookup"><span data-stu-id="9848c-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="9848c-249">Informationen zu den Standardmäßigen [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, und zu den potenziellen Auswirkungen des Überspringens der Einrichtung von Standardursprungsarten finden Sie unter "Default CDN origins".</span><span class="sxs-lookup"><span data-stu-id="9848c-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="9848c-250">Um Ihrer Organisation die Verwendung von öffentlichen Ursprüngen zu ermöglichen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="9848c-251">Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9848c-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="9848c-252">Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-SPOTenantCdnEnabled".](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="9848c-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="9848c-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="9848c-254">Ändern der Liste der Dateitypen, die in die Office 365 CDN eingeschlossen werden sollen (optional)</span><span class="sxs-lookup"><span data-stu-id="9848c-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="9848c-255">Wenn Sie Dateitypen mithilfe des Cmdlets **"Set-SPOTenantCdnPolicy"** definieren, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-256">Wenn Sie der Liste zusätzliche Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.</span><span class="sxs-lookup"><span data-stu-id="9848c-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="9848c-257">Verwenden Sie das Cmdlet **"Set-SPOTenantCdnPolicy",** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen im CDN gehostet werden können.</span><span class="sxs-lookup"><span data-stu-id="9848c-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="9848c-258">Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.</span><span class="sxs-lookup"><span data-stu-id="9848c-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="9848c-259">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="9848c-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="9848c-260">Um beispielsweise die CDN zum Hosten von CSS- und .png-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="9848c-261">Verwenden Sie das Cmdlet **"Get-SPOTenantCdnPolicies",** um zu sehen, welche Dateitypen derzeit vom CDN zugelassen werden:</span><span class="sxs-lookup"><span data-stu-id="9848c-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="9848c-262">Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-SPOTenantCdnPolicy"](/powershell/module/sharepoint-online/) und ["Get-SPOTenantCdnPolicies".](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="9848c-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="9848c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="9848c-264">Ändern der Liste der Websiteklassifizierungen, die Sie von der Office 365 CDN ausschließen möchten (optional)</span><span class="sxs-lookup"><span data-stu-id="9848c-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="9848c-265">Wenn Sie Websiteklassifizierungen mithilfe des Cmdlets **"Set-SPOTenantCdnPolicy"** ausschließen, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-266">Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9848c-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="9848c-267">Verwenden Sie das Cmdlet **Set-SPOTenantCdnPolicy** -Cmdlet zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="9848c-268">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9848c-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="9848c-269">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="9848c-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="9848c-270">Verwenden Sie das Cmdlet **"Get-SPOTenantCdnPolicies",** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:</span><span class="sxs-lookup"><span data-stu-id="9848c-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="9848c-271">Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="9848c-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="9848c-272">Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-273">Die Standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten Dateierweiterungen.</span><span class="sxs-lookup"><span data-stu-id="9848c-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="9848c-274">Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifizierungen, die Sie aus dem CDN ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="9848c-275">Beispielsweise können Sie Websites ausschließen, die als **vertraulich** gekennzeichnet sind, damit Inhalte von Websites mit dieser Klassifizierung nicht vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="9848c-276">Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus dem CDN basierend auf den _NoScript-Attributeinstellungen_ auf Websiteebene aus.</span><span class="sxs-lookup"><span data-stu-id="9848c-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="9848c-277">Standardmäßig ist das _NoScript-Attribut_ auf **"Enabled"** für _moderne_ Websites und **"Disabled"** für _klassische_ Websites festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9848c-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="9848c-278">Dies hängt von Ihren Mandanteneinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="9848c-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="9848c-279">Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-SPOTenantCdnPolicy"](/powershell/module/sharepoint-online/) und ["Get-SPOTenantCdnPolicies".](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="9848c-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="9848c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="9848c-281">Hinzufügen eines Ursprungs für Ihre Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-281">Add an origin for your assets</span></span>

<span data-ttu-id="9848c-282">Verwenden Sie das **Cmdlet "Add-SPOTenantCdnOrigin",** um einen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="9848c-283">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-283">You can define multiple origins.</span></span> <span data-ttu-id="9848c-284">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9848c-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9848c-285">Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung.</span><span class="sxs-lookup"><span data-stu-id="9848c-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="9848c-286">Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="9848c-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="9848c-287">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="9848c-288">Ursprünge unterstützen Platzhalter, die der URL vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="9848c-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="9848c-289">Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Websites erstrecken.</span><span class="sxs-lookup"><span data-stu-id="9848c-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="9848c-290">Um beispielsweise alle Ressourcen in den Masterpages-Ordner für alle Ihre Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="9848c-291">Der Platzhaltermodifizierer \* **/** kann nur am Anfang des Pfads verwendet werden und gleicht alle URL-Segmente unter der angegebenen URL ab.</span><span class="sxs-lookup"><span data-stu-id="9848c-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="9848c-292">Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen.</span><span class="sxs-lookup"><span data-stu-id="9848c-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="9848c-293">Beispielsweise entspricht der Pfad _\*/site1_ allen Dokumentbibliotheken unter der Website.</span><span class="sxs-lookup"><span data-stu-id="9848c-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="9848c-294">Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="9848c-295">Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="9848c-296">In diesem Beispiel wird ein privater Ursprung der Websiteassets-Bibliothek auf einer bestimmten Website hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="9848c-297">In diesem Beispiel wird ein privater Ursprung des Ordners _"folder1"_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="9848c-298">Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen umgeben oder das Leerzeichen durch die URL-Codierung %20 ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9848c-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="9848c-299">In den folgenden Beispielen wird ein privater Ursprung des _Ordners 1_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="9848c-300">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-301">In privaten Ursprüngen müssen Ressourcen, die von einem Ursprung freigegeben werden, über eine Hauptversion verfügen, bevor über die CDN auf sie zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="9848c-302">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-303">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="9848c-305">Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Formatbibliothek für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="9848c-306">Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="9848c-307">Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="9848c-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="9848c-308">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um die Formatbibliothek als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="9848c-309">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="9848c-310">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="9848c-311">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-312">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="9848c-314">Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteressourcen, Websiteseiten und Veröffentlichungsbilder für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="9848c-315">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Websiteressourcenordner als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="9848c-316">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Ordner "Websiteseiten" als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="9848c-317">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Ordner "Veröffentlichungsimages" als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="9848c-318">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="9848c-319">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-320">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="9848c-322">Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="9848c-323">Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um eine Websitesammlung als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="9848c-324">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9848c-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="9848c-325">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="9848c-326">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-327">Möglicherweise wird eine _ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Onlinemandant eine Verbindung mit dem CDN Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="9848c-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="9848c-328">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="9848c-330">Verwalten der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="9848c-331">Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder wenn sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9848c-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="9848c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="9848c-333">Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="9848c-334">Nachdem Sie die Einrichtungsschritte abgeschlossen haben, können Sie neue Ressourcen hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="9848c-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="9848c-335">Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint Bibliothek vor, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="9848c-336">Wenn Sie ein neues Objekt hinzufügen, ist es sofort über die CDN verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9848c-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="9848c-337">Wenn Sie die Ressource jedoch aktualisieren, dauert es bis zu 15 Minuten, bis die neue Kopie verteilt und im CDN verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9848c-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="9848c-338">Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das Cmdlet **"Get-SPOTenantCdnOrigins"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="9848c-339">Informationen zur Verwendung dieses Cmdlets finden Sie unter ["Get-SPOTenantCdnOrigins".](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)</span><span class="sxs-lookup"><span data-stu-id="9848c-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="9848c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="9848c-341">Entfernen eines Ursprungs aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="9848c-342">Sie können den Zugriff auf einen Ordner oder eine SharePoint Bibliothek entfernen, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="9848c-343">Verwenden Sie dazu das Cmdlet **"Remove-SPOTenantCdnOrigin".**</span><span class="sxs-lookup"><span data-stu-id="9848c-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="9848c-344">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="9848c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="9848c-346">Ändern eines Ursprungs in der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="9848c-347">Sie können einen von Ihnen erstellten Ursprung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="9848c-348">Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9848c-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="9848c-349">Weitere Informationen finden Sie unter ["So entfernen Sie einen Ursprung aus dem Office 365 CDN"](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) und ["So fügen Sie einen Ursprung für Ihre Ressourcen hinzu".](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="9848c-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="9848c-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="9848c-351">Deaktivieren der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="9848c-352">Verwenden Sie das Cmdlet **"Set-SPOTenantCdnEnabled",** um die CDN für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="9848c-353">Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9848c-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="9848c-354">Um die Verwendung öffentlicher Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="9848c-355">Um die Verwendung der privaten Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="9848c-356">Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-SPOTenantCdnEnabled".](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="9848c-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="9848c-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="9848c-358">Einrichten und Konfigurieren der Office 365 CDN mithilfe von PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="9848c-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="9848c-359">Für die Verfahren in diesem Abschnitt müssen Sie PnP PowerShell verwenden, um eine Verbindung mit SharePoint Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9848c-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="9848c-360">Anweisungen finden Sie unter ["Erste Schritte mit PnP PowerShell".](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="9848c-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="9848c-361">Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Objekte in SharePoint Online mithilfe von PnP PowerShell einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="9848c-362">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="9848c-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="9848c-363">Ermöglichen Sie Ihrer Organisation die Verwendung der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="9848c-364">Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der Konfiguration für private CDN in Ihrem Office 365 Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="9848c-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="9848c-365">Verbinden zu Ihrem Mandanten mithilfe von PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9848c-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="9848c-366">Verwenden Sie nun das Cmdlet **"Get-PnPTenantCdnEnabled",** um die CDN Statuseinstellungen vom Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="9848c-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="9848c-367">Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9848c-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="9848c-368">Verwenden Sie das Cmdlet **"Set-PnPTenantCdnEnabled",** um Ihrer Organisation die Verwendung der Office 365 CDN zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9848c-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="9848c-369">Sie können Ihrer Organisation ermöglichen, öffentliche Ursprünge, private Ursprünge oder beide gleichzeitig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="9848c-370">Sie können die CDN auch so konfigurieren, dass die Einrichtung der Standardursprungs beim Aktivieren übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="9848c-371">Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9848c-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="9848c-372">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9848c-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="9848c-373">Geben Sie beispielsweise den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9848c-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="9848c-374">Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen, aber das Einrichten der Standardursprungs zu überspringen:</span><span class="sxs-lookup"><span data-stu-id="9848c-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="9848c-375">Informationen zu den Standardmäßigen [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, und zu den potenziellen Auswirkungen des Überspringens der Einrichtung von Standardursprungsarten finden Sie unter "Default CDN origins".</span><span class="sxs-lookup"><span data-stu-id="9848c-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="9848c-376">Um Ihrer Organisation die Verwendung von öffentlichen Ursprüngen zu ermöglichen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="9848c-377">Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9848c-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="9848c-378">Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-PnPTenantCdnEnabled".](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="9848c-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="9848c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="9848c-380">Ändern der Liste der Dateitypen, die in die Office 365 CDN eingeschlossen werden sollen (optional)</span><span class="sxs-lookup"><span data-stu-id="9848c-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="9848c-381">Wenn Sie Dateitypen mithilfe des Cmdlets **"Set-PnPTenantCdnPolicy"** definieren, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-382">Wenn Sie der Liste zusätzliche Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.</span><span class="sxs-lookup"><span data-stu-id="9848c-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="9848c-383">Verwenden Sie das Cmdlet **"Set-PnPTenantCdnPolicy",** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen im CDN gehostet werden können.</span><span class="sxs-lookup"><span data-stu-id="9848c-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="9848c-384">Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.</span><span class="sxs-lookup"><span data-stu-id="9848c-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="9848c-385">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9848c-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="9848c-386">Um beispielsweise die CDN zum Hosten von CSS- und .png-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="9848c-387">Verwenden Sie das Cmdlet **"Get-PnPTenantCdnPolicies",** um zu sehen, welche Dateitypen derzeit vom CDN zugelassen werden:</span><span class="sxs-lookup"><span data-stu-id="9848c-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="9848c-388">Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-PnPTenantCdnPolicy"](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und ["Get-PnPTenantCdnPolicies".](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="9848c-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="9848c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="9848c-390">Ändern der Liste der Websiteklassifizierungen, die Sie von der Office 365 CDN ausschließen möchten (optional)</span><span class="sxs-lookup"><span data-stu-id="9848c-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="9848c-391">Wenn Sie Websiteklassifizierungen mithilfe des Cmdlets **"Set-PnPTenantCdnPolicy"** ausschließen, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-392">Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9848c-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="9848c-393">Verwenden Sie das Cmdlet **"Set-PnPTenantCdnPolicy",** um Websiteklassifizierungen auszuschließen, die Sie nicht über die CDN verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="9848c-394">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9848c-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="9848c-395">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9848c-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="9848c-396">Verwenden Sie das Cmdlet **"Get-PnPTenantCdnPolicies",** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:</span><span class="sxs-lookup"><span data-stu-id="9848c-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="9848c-397">Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="9848c-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="9848c-398">Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-399">Die Standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten Dateierweiterungen.</span><span class="sxs-lookup"><span data-stu-id="9848c-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="9848c-400">Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifizierungen, die Sie aus dem CDN ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="9848c-401">Sie können z. B. Websites ausschließen, die als **vertraulich** gekennzeichnet sind, sodass Inhalte von Websites mit dieser Klassifizierung nicht vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="9848c-402">Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus dem CDN basierend auf den _NoScript-Attributeinstellungen_ auf Websiteebene aus.</span><span class="sxs-lookup"><span data-stu-id="9848c-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="9848c-403">Standardmäßig ist das _NoScript-Attribut_ auf **"Enabled"** für _moderne_ Websites und **"Disabled"** für _klassische_ Websites festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9848c-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="9848c-404">Dies hängt von Ihren Mandanteneinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="9848c-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="9848c-405">Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-PnPTenantCdnPolicy"](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und ["Get-PnPTenantCdnPolicies".](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="9848c-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="9848c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="9848c-407">Hinzufügen eines Ursprungs für Ihre Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-407">Add an origin for your assets</span></span>

<span data-ttu-id="9848c-408">Verwenden Sie das **Cmdlet "Add-PnPTenantCdnOrigin",** um einen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="9848c-409">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-409">You can define multiple origins.</span></span> <span data-ttu-id="9848c-410">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9848c-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9848c-411">Sie sollten niemals Ressourcen, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung platzieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="9848c-412">Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="9848c-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="9848c-413">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="9848c-414">Ursprünge unterstützen Platzhalter, die der URL vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="9848c-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="9848c-415">Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Websites erstrecken.</span><span class="sxs-lookup"><span data-stu-id="9848c-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="9848c-416">Um beispielsweise alle Ressourcen in den Masterpages-Ordner für alle Ihre Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="9848c-417">Der Platzhaltermodifizierer \* **/** kann nur am Anfang des Pfads verwendet werden und gleicht alle URL-Segmente unter der angegebenen URL ab.</span><span class="sxs-lookup"><span data-stu-id="9848c-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="9848c-418">Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen.</span><span class="sxs-lookup"><span data-stu-id="9848c-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="9848c-419">Beispielsweise entspricht der Pfad _\*/site1_ allen Dokumentbibliotheken unter der Website.</span><span class="sxs-lookup"><span data-stu-id="9848c-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="9848c-420">Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="9848c-421">Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="9848c-422">In diesem Beispiel wird ein privater Ursprung der Websiteressourcenbibliothek auf einer bestimmten Website hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="9848c-423">In diesem Beispiel wird ein privater Ursprung des Ordners _"folder1"_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="9848c-424">Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen umgeben oder das Leerzeichen durch die URL-Codierung %20 ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9848c-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="9848c-425">In den folgenden Beispielen wird ein privater Ursprung des _Ordners 1_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9848c-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="9848c-426">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-427">In privaten Ursprüngen müssen Ressourcen, die von einem Ursprung freigegeben werden, über eine Hauptversion verfügen, bevor über die CDN auf sie zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="9848c-428">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-429">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="9848c-431">Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Formatbibliothek für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="9848c-432">Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="9848c-433">Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="9848c-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="9848c-434">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um die Formatbibliothek als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="9848c-435">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="9848c-436">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="9848c-437">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-438">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="9848c-440">Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteressourcen, Websiteseiten und Veröffentlichungsbilder für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="9848c-441">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Websiteressourcenordner als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="9848c-442">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Ordner "Websiteseiten" als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="9848c-443">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Ordner "Veröffentlichungsimages" als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="9848c-444">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="9848c-445">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-446">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="9848c-448">Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="9848c-449">Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um eine Websitesammlung als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="9848c-450">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9848c-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="9848c-451">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="9848c-452">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="9848c-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="9848c-453">Möglicherweise wird eine _ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Onlinemandant eine Verbindung mit dem CDN Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="9848c-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="9848c-454">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9848c-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="9848c-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="9848c-456">Verwalten der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="9848c-457">Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder wenn sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9848c-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="9848c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="9848c-459">Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="9848c-460">Nachdem Sie die Einrichtungsschritte abgeschlossen haben, können Sie neue Ressourcen hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="9848c-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="9848c-461">Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint Bibliothek vor, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="9848c-462">Wenn Sie ein neues Objekt hinzufügen, ist es sofort über die CDN verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9848c-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="9848c-463">Wenn Sie die Ressource jedoch aktualisieren, dauert es bis zu 15 Minuten, bis die neue Kopie verteilt und im CDN verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9848c-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="9848c-464">Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das Cmdlet **"Get-PnPTenantCdnOrigin"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="9848c-465">Informationen zur Verwendung dieses Cmdlets finden Sie unter ["Get-PnPTenantCdnOrigin".](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="9848c-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="9848c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="9848c-467">Entfernen eines Ursprungs aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="9848c-468">Sie können den Zugriff auf einen Ordner oder eine SharePoint Bibliothek entfernen, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="9848c-469">Verwenden Sie dazu das Cmdlet **"Remove-PnPTenantCdnOrigin".**</span><span class="sxs-lookup"><span data-stu-id="9848c-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="9848c-470">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="9848c-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="9848c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="9848c-472">Ändern eines Ursprungs in der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="9848c-473">Sie können einen von Ihnen erstellten Ursprung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="9848c-474">Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9848c-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="9848c-475">Weitere Informationen finden Sie unter [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and To add an origin for your [assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="9848c-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="9848c-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="9848c-477">Deaktivieren der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="9848c-478">Verwenden Sie das Cmdlet **"Set-PnPTenantCdnEnabled",** um die CDN für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="9848c-479">Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9848c-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="9848c-480">Um die Verwendung öffentlicher Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="9848c-481">Um die Verwendung der privaten Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9848c-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="9848c-482">Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-PnPTenantCdnEnabled".](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="9848c-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="9848c-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="9848c-484">Einrichten und Konfigurieren des Office 365 CDN mithilfe von Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="9848c-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="9848c-485">Die Verfahren in diesem Abschnitt erfordern, dass Sie die [Office 365 CLI](https://aka.ms/o365cli)installiert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="9848c-486">Stellen Sie als Nächstes mithilfe des [Anmeldebefehls](https://pnp.github.io/office365-cli/cmd/login/) eine Verbindung mit Ihrem Office 365 Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="9848c-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="9848c-487">Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Ressourcen in SharePoint Online mithilfe der Office 365 CLI einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="9848c-488">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="9848c-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="9848c-489">Aktivieren der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="9848c-490">Sie können den Status des Office 365 CDN in Ihrem Mandanten mithilfe des Cmdlets [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) verwalten.</span><span class="sxs-lookup"><span data-stu-id="9848c-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="9848c-491">Um das öffentliche Office 365 CDN in Ihrem Mandanten zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="9848c-492">Führen Sie Folgendes aus, um die Office 365 SharePoint CDN zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9848c-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="9848c-493">Anzeigen des aktuellen Status des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="9848c-494">Um zu überprüfen, ob der bestimmte Typ von Office 365 CDN aktiviert oder deaktiviert ist, verwenden Sie den Befehl [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="9848c-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="9848c-495">Um zu überprüfen, ob das öffentliche Office 365 CDN aktiviert ist, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="9848c-496">Anzeigen der Office 365 CDN Ursprünge</span><span class="sxs-lookup"><span data-stu-id="9848c-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="9848c-497">Um die derzeit konfigurierten öffentlichen Office 365 CDN-Ursprünge anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="9848c-498">Informationen zu den [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, finden Sie unter "Standard CDN Ursprünge".</span><span class="sxs-lookup"><span data-stu-id="9848c-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="9848c-499">Hinzufügen eines Office 365 CDN Ursprungs</span><span class="sxs-lookup"><span data-stu-id="9848c-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9848c-500">Sie sollten Ressourcen, die für Ihre Organisation als vertraulich gelten, niemals in einer SharePoint Dokumentbibliothek platzieren, die als öffentlicher Ursprung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9848c-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="9848c-501">Verwenden Sie den Befehl [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) zum Definieren eines CDN-Ursprungs.</span><span class="sxs-lookup"><span data-stu-id="9848c-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="9848c-502">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-502">You can define multiple origins.</span></span> <span data-ttu-id="9848c-503">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9848c-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="9848c-504">Gibt `path` den relativen Pfad zu dem Ordner an, der die Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="9848c-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="9848c-505">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="9848c-506">Führen Sie Folgendes aus, um alle Objekte in den **Gestaltungsvorlagenkatalog** aller Websites als öffentlichen Ursprung einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="9848c-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="9848c-507">Um einen privaten Ursprung für eine bestimmte Websitesammlung zu konfigurieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="9848c-508">Nach dem Hinzufügen eines CDN-Ursprungs dauert es bis zu 15 Minuten, bis Sie Dateien mithilfe des CDN-Diensts abrufen können.</span><span class="sxs-lookup"><span data-stu-id="9848c-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="9848c-509">Sie können überprüfen, ob der betreffende Ursprung bereits aktiviert wurde, indem Sie den Befehl [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="9848c-510">Entfernen eines Office 365 CDN Ursprungs</span><span class="sxs-lookup"><span data-stu-id="9848c-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="9848c-511">Verwenden Sie den Befehl [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/), um einen CDN-Ursprung für den angegebenen CDN-Typ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9848c-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="9848c-512">Um einen öffentlichen Ursprung aus der CDN Konfiguration zu entfernen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="9848c-513">Das Entfernen eines CDN Ursprungs wirkt sich nicht auf die Dateien aus, die in einer Dokumentbibliothek gespeichert sind, die diesem Ursprung entspricht.</span><span class="sxs-lookup"><span data-stu-id="9848c-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="9848c-514">Wenn auf diese Ressourcen mit ihrer SharePoint URL verwiesen wurde, wechseln SharePoint automatisch zurück zur ursprünglichen URL, die auf die Dokumentbibliothek verweist.</span><span class="sxs-lookup"><span data-stu-id="9848c-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="9848c-515">Wenn auf Ressourcen jedoch über eine öffentliche CDN URL verwiesen wurde, wird durch entfernen des Ursprungs der Link beschädigt, und Sie müssen sie manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="9848c-516">Ändern eines Office 365 CDN Ursprungs</span><span class="sxs-lookup"><span data-stu-id="9848c-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="9848c-517">Es ist nicht möglich, einen vorhandenen CDN-Ursprung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="9848c-518">Stattdessen sollten Sie den zuvor definierten CDN-Ursprung mit dem Befehl `spo cdn origin remove` entfernen und mit dem Befehl `spo cdn origin add` einen neuen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9848c-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="9848c-519">Ändern der Dateitypen, die in die Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="9848c-520">Standardmäßig sind die folgenden Dateitypen im CDN enthalten: _CSS, EOT, .gif, ICO, JPEG, .jpg, .js, MAP, .png, SVG, TTF, WOFF UND WOFF2._</span><span class="sxs-lookup"><span data-stu-id="9848c-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="9848c-521">Wenn Sie weitere Dateitypen in das CDN einbeziehen müssen, können Sie die CDN-Konfiguration mit dem Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) ändern.</span><span class="sxs-lookup"><span data-stu-id="9848c-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-522">Durch das Ändern der Liste von Dateitypen überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-523">Wenn Sie weitere Dateitypen einbeziehen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), um herauszufinden, welche Dateitypen derzeit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9848c-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="9848c-524">Führen Sie Folgendes aus, um den _JSON-Dateityp_ der Standardliste der im öffentlichen CDN enthaltenen Dateitypen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="9848c-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="9848c-525">Ändern der Liste von Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="9848c-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="9848c-526">Verwenden Sie den Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="9848c-527">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9848c-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-528">Durch das Ändern der Liste der ausgeschlossenen Websiteklassifizierungen überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="9848c-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="9848c-529">Wenn Sie zusätzliche Klassifizierungen ausschließen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), um herauszufinden, welche Klassifizierungen derzeit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9848c-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="9848c-530">Um als _HBI_ klassifizierte Websites von der öffentlichen CDN auszuschließen, führen Sie</span><span class="sxs-lookup"><span data-stu-id="9848c-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="9848c-531">Deaktivieren der Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="9848c-532">Um das Office 365 CDN zu deaktivieren, verwenden Sie den Befehl `spo cdn set`. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9848c-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="9848c-533">Verwenden Ihrer CDN-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-533">Using your CDN assets</span></span>

<span data-ttu-id="9848c-534">Nachdem Sie nun die CDN und konfigurierten Ursprünge und Richtlinien aktiviert haben, können Sie mit der Verwendung Ihrer CDN-Ressourcen beginnen.</span><span class="sxs-lookup"><span data-stu-id="9848c-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="9848c-535">In diesem Abschnitt erfahren Sie, wie Sie CDN URLs in Ihren SharePoint Seiten und Inhalten verwenden, damit SharePoint Anforderungen für Ressourcen in öffentlichen und privaten Ursprüngen an die CDN weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="9848c-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="9848c-536">Aktualisieren von Links zu CDN Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="9848c-537">Verwenden von Ressourcen in öffentlichen Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="9848c-538">Verwenden von Ressourcen in privaten Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="9848c-539">Informationen zur Verwendung der CDN zum Hosten clientseitiger Webparts finden Sie im Thema [Hosten ihres clientseitigen Webparts aus Office 365 CDN (Hello World Teil 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="9848c-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-540">Wenn Sie den Ordner _"ClientSideAssets"_ der Liste der **privaten** CDN Ursprünge hinzufügen, können CDN gehostete benutzerdefinierte Webparts nicht gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="9848c-541">Dateien, die von SPFX-Webparts verwendet werden, können nur die öffentliche CDN verwenden, und der ClientSideAssets-Ordner ist ein Standardursprung für öffentliche CDN.</span><span class="sxs-lookup"><span data-stu-id="9848c-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="9848c-542">Aktualisieren von Links zu CDN Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-542">Updating links to CDN assets</span></span>

<span data-ttu-id="9848c-543">Um Ressourcen zu verwenden, die Sie einem Ursprung hinzugefügt haben, aktualisieren Sie einfach Links zur Originaldatei mit dem Pfad zu der Datei im Ursprung.</span><span class="sxs-lookup"><span data-stu-id="9848c-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="9848c-544">Bearbeiten Sie die Seite oder den Inhalt, die Links zu Ressourcen enthält, die Sie einem Ursprung hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="9848c-545">Sie können auch eine von mehreren Methoden verwenden, um Links über eine Eingabewebsite oder Websitesammlung hinweg global zu suchen und zu ersetzen, wenn Sie den Link zu einem bestimmten Objekt überall dort aktualisieren möchten, wo er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="9848c-546">Ersetzen Sie für jeden Link zu einer Ressource in einem Ursprung den Pfad durch den Pfad zur Datei im CDN Ursprung.</span><span class="sxs-lookup"><span data-stu-id="9848c-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="9848c-547">Sie können relative Pfade verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-547">You can use relative paths.</span></span>
+ <span data-ttu-id="9848c-548">Speichern Sie die Seite oder den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="9848c-548">Save the page or content.</span></span>

<span data-ttu-id="9848c-549">Betrachten Sie beispielsweise das Bild _/site/SiteAssets/images/image.png_, das Sie in den Dokumentbibliotheksordner _/site/CDN_origins/public/_ kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="9848c-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="9848c-550">Um die CDN Ressource zu verwenden, ersetzen Sie den ursprünglichen Pfad zum Speicherort der Bilddatei durch den Pfad zum Ursprung, um die neue URL _/site/CDN_origins/public/image.png_ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9848c-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="9848c-551">Wenn Sie die vollständige URL zu der Ressource anstelle eines relativen Pfads verwenden möchten, erstellen Sie den Link wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9848c-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="9848c-552">Im Allgemeinen sollten Sie URLs nicht direkt in Ressourcen im CDN hartcodieren.</span><span class="sxs-lookup"><span data-stu-id="9848c-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="9848c-553">Sie können jedoch bei Bedarf manuell URLs für Ressourcen in öffentlichen Ursprüngen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9848c-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="9848c-554">Weitere Informationen finden Sie unter [Hardcoding CDN URLs für öffentliche Ressourcen.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="9848c-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="9848c-555">Weitere Informationen dazu, wie Sie überprüfen, ob Ressourcen von der CDN bereitgestellt werden, finden Sie unter ["Wie kann ich bestätigen, dass Ressourcen von der CDN bereitgestellt werden?"](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [der Problembehandlung für die Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9848c-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="9848c-556">Verwenden von Ressourcen in öffentlichen Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-556">Using assets in public origins</span></span>

<span data-ttu-id="9848c-557">Das **Veröffentlichungsfeature** in SharePoint Online schreibt URLs von Ressourcen, die in öffentlichen Ursprüngen gespeichert sind, automatisch in ihre CDN Entsprechungen um, sodass Ressourcen vom CDN Dienst anstatt von SharePoint bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="9848c-558">Wenn sich Ihr Ursprung in einer Website mit aktivierter Veröffentlichungsfunktion befindet und die Objekte, die Sie an die CDN auslagern möchten, in einer der folgenden Kategorien sind, werden SharePoint URLs für Ressourcen im Ursprung automatisch neu schreiben, vorausgesetzt, dass die Ressource nicht von einer CDN Richtlinie ausgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9848c-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="9848c-559">Es folgt eine Übersicht über die Links, die automatisch vom SharePoint-Veröffentlichungsfeature umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="9848c-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="9848c-560">IMG/LINK/CSS-URLs in den HTML-Antworten klassischer Veröffentlichungsseiten</span><span class="sxs-lookup"><span data-stu-id="9848c-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="9848c-561">Dies schließt von Autoren im HTML-Inhalt einer Seite hinzugefügte Bilder ein.</span><span class="sxs-lookup"><span data-stu-id="9848c-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="9848c-562">Bild-URLs des Webparts „Bildbibliothek-Bildschirmpräsentation“</span><span class="sxs-lookup"><span data-stu-id="9848c-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="9848c-563">Bildfelder in Ergebnissen der SPList-REST-API (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="9848c-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="9848c-564">Verwenden Sie die neue Eigenschaft _ImageFieldsToTryRewriteToCdnUrls,_ um eine durch Kommas getrennte Liste von Feldern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9848c-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="9848c-565">Unterstützt Hyperlinkfelder und PublishingImage-Felder</span><span class="sxs-lookup"><span data-stu-id="9848c-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="9848c-566">SharePoint Bilddarstellungen</span><span class="sxs-lookup"><span data-stu-id="9848c-566">SharePoint image renditions</span></span>

<span data-ttu-id="9848c-567">Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite mit Ressourcen von einem öffentlichen Ursprung empfängt.</span><span class="sxs-lookup"><span data-stu-id="9848c-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="9848c-568">![Workflowdiagramm: Abrufen Office 365 CDN Ressourcen von einem öffentlichen Ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Abrufen Office 365 CDN Ressourcen von einem öffentlichen Ursprung")</span><span class="sxs-lookup"><span data-stu-id="9848c-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="9848c-569">Wenn Sie das automatische Umschreiben für bestimmte URLs auf einer Seite deaktivieren möchten, können Sie die Seite auschecken und den Abfragezeichenfolgenparameter **hinzufügen? NoAutoReWrites=true** bis zum Ende jedes Links, den Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9848c-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="9848c-570">Erstellen CDN URLs für öffentliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9848c-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="9848c-571">Wenn das _Veröffentlichungsfeature_ für einen öffentlichen Ursprung nicht aktiviert ist oder die Ressource nicht einer der Linktypen ist, die vom Feature für die automatische Neuschreibung des CDN Diensts unterstützt werden, können Sie URLs manuell an den CDN Speicherort der Ressourcen erstellen und diese URLs in Ihren Inhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-572">Sie können CDN URLs nicht für Objekte in einem privaten Ursprung hartcodieren oder erstellen, da das erforderliche Zugriffstoken, das den letzten Abschnitt der URL bildet, zum Zeitpunkt der Anforderung der Ressource generiert wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="9848c-573">Sie können die URL für öffentliche CDN erstellen, und die URL sollte nicht hartcodiert sein, da sie geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="9848c-574">Für öffentliche CDN Ressourcen sieht das URL-Format wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="9848c-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="9848c-575">Ersetzen Sie **TenantHostName** durch Ihren Mandantennamen.</span><span class="sxs-lookup"><span data-stu-id="9848c-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="9848c-576">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9848c-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="9848c-577">Die Seitenkontexteigenschaft sollte verwendet werden, um das Präfix zu erstellen, anstatt hartcodieren zu https://publiccdn.sharepointonline.com müssen.</span><span class="sxs-lookup"><span data-stu-id="9848c-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="9848c-578">Die URL kann geändert werden und sollte nicht hartcodiert sein.</span><span class="sxs-lookup"><span data-stu-id="9848c-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="9848c-579">Wenn Sie Anzeigevorlagen mit klassischem SharePoint Online verwenden, können Sie die Eigenschaft "window._spPageContextInfo.publicCdnBaseUrl" in Der Anzeigevorlage für das Präfix der URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="9848c-580">Wenn Sie SPFx Webparts für moderne und klassische SharePoint können Sie die Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="9848c-581">Dadurch wird das Präfix bereitgestellt, sodass bei einer Änderung die Implementierung mit ihr aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="9848c-582">Als Beispiel für SPFx kann die URL mithilfe der Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="9848c-583">Weitere Informationen finden Sie unter [Verwenden von CDN im clientseitigen Code,](https://youtu.be/IH1RbQlbhIA) der Teil der Leistungsserie der [1. Spielzeit](https://aka.ms/sppnp-perfvideos) ist.</span><span class="sxs-lookup"><span data-stu-id="9848c-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="9848c-584">Verwenden von Ressourcen in privaten Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-584">Using assets in private origins</span></span>

<span data-ttu-id="9848c-585">Für die Verwendung von Ressourcen in privaten Ursprüngen ist keine zusätzliche Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9848c-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="9848c-586">SharePoint Online schreibt URLs für Objekte in privaten Ursprüngen automatisch um, sodass Anforderungen für diese Ressourcen immer vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="9848c-587">Sie können keine URLs manuell erstellen, um Ressourcen in privaten Ursprüngen zu CDN, da diese URLs Token enthalten, die automatisch von SharePoint Online generiert werden müssen, wenn die Ressource angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="9848c-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="9848c-588">Der Zugriff auf Ressourcen in privaten Ursprüngen wird durch dynamisch generierte Token basierend auf Benutzerberechtigungen für den Ursprung geschützt, mit den in den folgenden Abschnitten beschriebenen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9848c-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="9848c-589">Benutzer müssen mindestens **Lesezugriff** auf die Ursprünge haben, damit die CDN Inhalte rendern kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="9848c-590">Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite mit Ressourcen von einem privaten Ursprung empfängt.</span><span class="sxs-lookup"><span data-stu-id="9848c-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="9848c-591">![Workflowdiagramm: Abrufen Office 365 CDN Ressourcen von einem privaten Ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Abrufen von Office 365 CDN Ressourcen von einem privaten Ursprung")</span><span class="sxs-lookup"><span data-stu-id="9848c-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="9848c-592">Tokenbasierte Autorisierung in privaten Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="9848c-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="9848c-593">Der Zugriff auf Objekte in privaten Ursprüngen im Office 365 CDN wird durch Token gewährt, die von SharePoint Online generiert werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="9848c-594">Benutzern, die bereits über die Berechtigung zum Zugriff auf den vom Ursprung festgelegten Ordner oder die Bibliothek verfügen, werden automatisch Token gewährt, mit denen der Benutzer basierend auf seiner Berechtigungsstufe auf die Datei zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="9848c-595">Diese Zugriffstoken sind 30 bis 90 Minuten gültig, nachdem sie generiert wurden, um Tokenwiederholungsangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9848c-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="9848c-596">Nachdem das Zugriffstoken generiert wurde, gibt SharePoint Online einen benutzerdefinierten  URI an den Client zurück, der zwei Autorisierungsparameter (Edgeautorisierungstoken) und _Oat_ (Ursprungsautorisierungstoken) enthält.</span><span class="sxs-lookup"><span data-stu-id="9848c-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="9848c-597">Die Struktur der einzelnen Token ist _<'Ablaufzeit im Epoch-Zeitformat'>__<'sichere Signatur'>._</span><span class="sxs-lookup"><span data-stu-id="9848c-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="9848c-598">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9848c-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="9848c-599">Jeder Benutzer, der das Token besitzt, kann auf die Ressource im CDN zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9848c-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="9848c-600">URLs, die diese Zugriffstoken enthalten, werden jedoch nur über HTTPS freigegeben. Es sei denn, die URL wird explizit von einem Endbenutzer freigegeben, bevor das Token abläuft, sodass nicht autorisierten Benutzern auf die Ressource zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9848c-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="9848c-601">Berechtigungen auf Elementebene werden für Objekte in privaten Ursprüngen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9848c-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="9848c-602">Es ist wichtig zu beachten, dass SharePoint Online berechtigungen auf Elementebene für Objekte in privaten Ursprüngen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9848c-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="9848c-603">Bei einer Datei, die sich unter befindet, haben Benutzer unter `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` den folgenden Bedingungen effektiven Zugriff auf die Datei:</span><span class="sxs-lookup"><span data-stu-id="9848c-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="9848c-604">Benutzer</span><span class="sxs-lookup"><span data-stu-id="9848c-604">User</span></span>  |<span data-ttu-id="9848c-605">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9848c-605">Permissions</span></span>  |<span data-ttu-id="9848c-606">Effektiver Zugriff</span><span class="sxs-lookup"><span data-stu-id="9848c-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9848c-607">Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="9848c-607">User 1</span></span>     |<span data-ttu-id="9848c-608">Hat Zugriff auf Ordner1</span><span class="sxs-lookup"><span data-stu-id="9848c-608">Has access to folder1</span></span>         |<span data-ttu-id="9848c-609">Kann über die CDN auf image1.jpg zugreifen</span><span class="sxs-lookup"><span data-stu-id="9848c-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="9848c-610">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="9848c-610">User 2</span></span>     |<span data-ttu-id="9848c-611">Hat keinen Zugriff auf Ordner1</span><span class="sxs-lookup"><span data-stu-id="9848c-611">Does not have access to folder1</span></span>         |<span data-ttu-id="9848c-612">CDN kann nicht auf image1.jpg zugreifen</span><span class="sxs-lookup"><span data-stu-id="9848c-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="9848c-613">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="9848c-613">User 3</span></span>     |<span data-ttu-id="9848c-614">Hat keinen Zugriff auf Ordner1, aber erhält explizite Berechtigung für den Zugriff auf image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9848c-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="9848c-615">Kann direkt über SharePoint Online auf die Ressource image1.jpg zugreifen, jedoch nicht über die CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="9848c-616">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="9848c-616">User 4</span></span>     |<span data-ttu-id="9848c-617">Hat Zugriff auf Ordner1, wurde jedoch explizit der Zugriff auf image1.jpg in SharePoint Online verweigert.</span><span class="sxs-lookup"><span data-stu-id="9848c-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="9848c-618">Der Zugriff auf das Objekt kann nicht über SharePoint Online, aber über die CDN auf das Objekt zugreifen, obwohl der Zugriff auf die Datei in SharePoint Online verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="9848c-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="9848c-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="9848c-620">Problembehandlung beim Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="9848c-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="9848c-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="9848c-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="9848c-622">Wie kann ich bestätigen, dass Ressourcen vom CDN bereitgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="9848c-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="9848c-623">Nachdem Sie Links zu CDN Ressourcen zu einer Seite hinzugefügt haben, können Sie bestätigen, dass das Objekt vom CDN bereitgestellt wird, indem Sie zur Seite navigieren, mit der rechten Maustaste auf das Bild klicken, nachdem es gerendert wurde, und die Bild-URL überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9848c-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="9848c-624">Sie können auch die Entwicklertools Ihres Browsers verwenden, um die URL für jede Ressource auf einer Seite anzuzeigen, oder ein Netzwerküberwachungstool eines Drittanbieters verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="9848c-625">Wenn Sie ein Netzwerktool wie Fiddler verwenden, um Ihre Ressourcen außerhalb des Renderns der Ressource von einer SharePoint Seite zu testen, müssen Sie den Verweiserheader "Referer: " manuell `https://yourdomain.sharepoint.com` zur GET-Anforderung hinzufügen, wobei die URL die Stamm-URL Ihres SharePoint Onlinemandanten ist.</span><span class="sxs-lookup"><span data-stu-id="9848c-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="9848c-626">Sie können CDN URLs nicht direkt in einem Webbrowser testen, da ein Verweiser von SharePoint Online stammen muss.</span><span class="sxs-lookup"><span data-stu-id="9848c-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="9848c-627">Wenn Sie jedoch die CDN Objekt-URL zu einer SharePoint Seite hinzufügen und dann die Seite in einem Browser öffnen, wird die CDN Ressource auf der Seite gerendert.</span><span class="sxs-lookup"><span data-stu-id="9848c-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="9848c-628">Weitere Informationen zur Verwendung der Entwicklertools im Microsoft Edge Browser finden Sie unter [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="9848c-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="9848c-629">Ein kurzes Video, das im [YouTube-Kanal SharePoint Developer Patterns and Practices](https://aka.ms/sppnp-videos) gehostet wird und zeigt, wie Sie überprüfen können, ob Ihre CDN funktioniert, finden Sie unter ["Überprüfen Ihrer CDN Nutzung und Sicherstellen einer optimalen Netzwerkkonnektivität".](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)</span><span class="sxs-lookup"><span data-stu-id="9848c-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="9848c-630">Warum sind Ressourcen aus einem neuen Ursprung nicht verfügbar?</span><span class="sxs-lookup"><span data-stu-id="9848c-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="9848c-631">Ressourcen in neuen Ursprüngen stehen nicht sofort zur Verwendung zur Verfügung, da es zeitaufwendige Zeit dauert, bis die Registrierung über die CDN verteilt wird und die Objekte vom Ursprung in CDN Speicher hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9848c-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="9848c-632">Die für die Verfügbarkeit von Ressourcen im CDN erforderliche Zeit hängt von der Anzahl der Ressourcen und der Dateigrößen ab.</span><span class="sxs-lookup"><span data-stu-id="9848c-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="9848c-633">Mein clientseitiges Webpart oder SharePoint-Framework Lösung funktioniert nicht</span><span class="sxs-lookup"><span data-stu-id="9848c-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="9848c-634">Wenn Sie die Office 365 CDN für öffentliche Ursprünge aktivieren, erstellt der CDN Dienst automatisch die folgenden Standardursprungs:</span><span class="sxs-lookup"><span data-stu-id="9848c-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="9848c-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="9848c-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="9848c-636">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="9848c-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="9848c-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="9848c-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="9848c-638">Wenn der \*/clientsideassets-Ursprung fehlt, schlagen SharePoint-Framework Lösungen fehl, und es werden keine Warnungen oder Fehlermeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="9848c-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="9848c-639">Dieser Ursprung fehlt möglicherweise, weil die CDN mit dem auf **$true** festgelegten Parameter _"-NoDefaultOrigins"_ aktiviert war oder weil der Ursprung manuell gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="9848c-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="9848c-640">Mit dem folgenden PowerShell-Befehl können Sie überprüfen, welche Ursprünge vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="9848c-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="9848c-641">Sie können auch die Office 365 CLI überprüfen:</span><span class="sxs-lookup"><span data-stu-id="9848c-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="9848c-642">So fügen Sie den Ursprung in PowerShell hinzu:</span><span class="sxs-lookup"><span data-stu-id="9848c-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="9848c-643">So fügen Sie den Ursprung in der Office 365 CLI hinzu:</span><span class="sxs-lookup"><span data-stu-id="9848c-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="9848c-644">Welche PowerShell-Module und CLI-Shells muss ich mit dem Office 365 CDN verwenden?</span><span class="sxs-lookup"><span data-stu-id="9848c-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="9848c-645">Sie können die Office 365 CDN entweder mit dem powerShell-Modul SharePoint **Onlineverwaltungsshell** oder mit der **Office 365 CLI** verwenden.</span><span class="sxs-lookup"><span data-stu-id="9848c-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="9848c-646">Erste Schritte mit der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9848c-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="9848c-647">Installieren von Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="9848c-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="9848c-648">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9848c-648">See also</span></span>

[<span data-ttu-id="9848c-649">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="9848c-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="9848c-650">Netzwerkplanung und Leistungsoptimierung für Office 365</span><span class="sxs-lookup"><span data-stu-id="9848c-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="9848c-651">SharePoint Performance Series – Office 365 CDN Videoreihe</span><span class="sxs-lookup"><span data-stu-id="9848c-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
