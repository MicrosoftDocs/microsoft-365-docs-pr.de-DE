---
title: Verwenden Sie Office 365 Inhalts Zustellungs Netzwerk (CDN) mit SharePoint Online
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
description: In diesem Artikel erfahren Sie, wie Sie das Office 365 Content Delivery Network (CDN) verwenden, um die Zustellung Ihrer SharePoint Online Ressourcen zu beschleunigen.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690307"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="89de2-103">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="89de2-104">Sie können statische Objekte im Office 365-Netzwerk für die Inhaltsübermittlung (CDN) hosten, um eine bessere Leistung für Ihre SharePoint Online-Seiten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89de2-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="89de2-105">Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="89de2-106">Außerdem verwendet das Office 365 CDN das [http/2-Protokoll](https://en.wikipedia.org/wiki/HTTP/2) für verbesserte Komprimierung und HTTP-Pipelining.</span><span class="sxs-lookup"><span data-stu-id="89de2-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="89de2-107">Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.</span><span class="sxs-lookup"><span data-stu-id="89de2-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-108">Das Office 365 CDN steht nur Mandanten in der **Produktionsumgebung** (weltweit) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89de2-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="89de2-109">Die Mandanten in der US-Regierung, in China und in Deutschland unterstützen derzeit nicht die Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="89de2-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="89de2-110">Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="89de2-111">In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="89de2-112">Weitere Informationen zum Unterschied zwischen öffentlichen und privaten Quellen finden Sie unter [Choose, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) .</span><span class="sxs-lookup"><span data-stu-id="89de2-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="89de2-113">![Office 365 CDN-konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-konzeptionelles Diagramm")</span><span class="sxs-lookup"><span data-stu-id="89de2-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="89de2-114">Wenn Sie bereits mit der Funktionsweise von CDNs vertraut sind, müssen Sie nur einige Schritte ausführen, um das Office 365 CDN für Ihren Mandanten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="89de2-115">In diesem Thema wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="89de2-115">This topic describes how.</span></span> <span data-ttu-id="89de2-116">Weitere Informationen zum Einstieg in das Hosten Ihrer statischen Objekte finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="89de2-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="89de2-117">Es gibt andere von Microsoft gehostete CDNs, die mit Office 365 für spezielle Verwendungsszenarien verwendet werden können, aber in diesem Thema nicht behandelt werden, da Sie nicht in den Bereich des Office 365 CDN fallen.</span><span class="sxs-lookup"><span data-stu-id="89de2-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="89de2-118">Weitere Informationen finden Sie unter [andere Microsoft-CDNs](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="89de2-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="89de2-119">**Wechseln Sie zurück zu [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune).**</span><span class="sxs-lookup"><span data-stu-id="89de2-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="89de2-120">Übersicht über das Arbeiten mit dem Office 365 CDN in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="89de2-121">Um die Office 365 CDN für Ihre Organisation einzurichten, führen Sie die folgenden grundlegenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="89de2-122">Planen der Bereitstellung des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="89de2-123">[Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="89de2-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="89de2-124">[Bestimmen Sie, wo Ihre Objekte gespeichert werden sollen](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span><span class="sxs-lookup"><span data-stu-id="89de2-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="89de2-125">Bei diesem Speicherort kann es sich um eine SharePoint-Website,-Bibliothek oder-Ordner handeln, die als _Ursprung_bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="89de2-126">[Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="89de2-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="89de2-127">Sie können mehrere Ursprünge sowohl für öffentliche als auch für private Typen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="89de2-128">Einrichten und Konfigurieren des CDN mithilfe von PowerShell oder der SharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="89de2-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="89de2-129">Einrichten und Konfigurieren des CDN mithilfe der SharePoint Online Management-Shell</span><span class="sxs-lookup"><span data-stu-id="89de2-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="89de2-130">Einrichten und Konfigurieren des CDN mithilfe von PNP-PowerShell</span><span class="sxs-lookup"><span data-stu-id="89de2-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="89de2-131">Einrichten und Konfigurieren des CDN mithilfe der Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="89de2-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="89de2-132">Wenn Sie diesen Schritt ausführen, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="89de2-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="89de2-133">Das CDN für Ihre Organisation wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="89de2-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="89de2-134">Origins hinzugefügt, wobei jeder Ursprung als öffentlich oder privat identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="89de2-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="89de2-135">Nachdem Sie das Setup abgeschlossen haben, können Sie [das Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) im Laufe der Zeit verwalten:</span><span class="sxs-lookup"><span data-stu-id="89de2-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="89de2-136">Hinzufügen, aktualisieren und Entfernen von Objekten</span><span class="sxs-lookup"><span data-stu-id="89de2-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="89de2-137">Hinzufügen und Entfernen von Ursprüngen</span><span class="sxs-lookup"><span data-stu-id="89de2-137">Adding and removing origins</span></span>
+ <span data-ttu-id="89de2-138">Konfigurieren von CDN-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="89de2-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="89de2-139">Falls erforderlich, Deaktivieren des CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="89de2-140">Weitere Informationen zum Zugreifen auf Ihre CDN-Ressourcen sowohl aus öffentlichen als auch aus privaten Quellen finden Sie unter [using your CDN Assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) .</span><span class="sxs-lookup"><span data-stu-id="89de2-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="89de2-141">Anleitungen zum Beheben häufig auftretender Probleme finden Sie unter [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="89de2-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="89de2-142">Planen der Bereitstellung des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="89de2-143">Bevor Sie das Office 365 CDN für Ihren Office 365-Mandanten bereitstellen, sollten Sie die folgenden Faktoren im Rahmen Ihres Planungsprozesses berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="89de2-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="89de2-144">Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="89de2-145">Bestimmen, wo Ihre Objekte gespeichert werden sollen</span><span class="sxs-lookup"><span data-stu-id="89de2-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="89de2-146">Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="89de2-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="89de2-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="89de2-148">Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="89de2-149">Im Allgemeinen sind CDNs am effektivsten für das Hosten von _statischen Objekten_oder von Objekten, die sich nicht sehr häufig ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="89de2-150">Eine gute Faustregel besteht darin, Dateien zu identifizieren, die einige oder alle dieser Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="89de2-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="89de2-151">In einer Seite eingebettete statische Dateien (wie Skripts und Bilder), die sich möglicherweise erheblich inkrementell auf die Seitenladezeiten auswirken</span><span class="sxs-lookup"><span data-stu-id="89de2-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="89de2-152">Große Dateien wie ausführbare Dateien und Installationsdateien</span><span class="sxs-lookup"><span data-stu-id="89de2-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="89de2-153">Ressourcen Bibliotheken, die clientseitigen Code unterstützen</span><span class="sxs-lookup"><span data-stu-id="89de2-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="89de2-154">Beispielsweise können kleine Dateien, die wiederholt wie Website Bilder und Skripts angefordert werden, die Leistung von Website Renderings erheblich verbessern und die Last auf Ihren SharePoint Online Websites inkrementell reduzieren, wenn Sie Sie einem CDN-Ursprung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="89de2-155">Größere Dateien wie Installationsdateien können aus dem CDN heruntergeladen werden, was sich positiv auf die Leistung auswirkt und die Last auf Ihrer SharePoint Online Website verringert, auch wenn Sie nicht so häufig auf Sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="89de2-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="89de2-156">Die Leistungsverbesserung pro Datei hängt von vielen Faktoren ab, einschließlich der Nähe des Clients zum nächstgelegenen CDN-Endpunkt, der vorübergehenden Bedingungen im lokalen Netzwerk und so weiter.</span><span class="sxs-lookup"><span data-stu-id="89de2-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="89de2-157">Viele statische Dateien sind relativ klein und können in weniger als einer Sekunde von Office 365 heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="89de2-158">Eine Webseite enthält jedoch möglicherweise viele eingebettete Dateien mit einer kumulierten Downloadzeit von mehreren Sekunden.</span><span class="sxs-lookup"><span data-stu-id="89de2-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="89de2-159">Das servieren dieser Dateien aus dem CDN kann die Ladezeit der gesamten Seite erheblich verkürzen.</span><span class="sxs-lookup"><span data-stu-id="89de2-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="89de2-160">Sehen Sie, [welche Leistungssteigerungen ein CDN bietet?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="89de2-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="89de2-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="89de2-162">Bestimmen, wo Ihre Objekte gespeichert werden sollen</span><span class="sxs-lookup"><span data-stu-id="89de2-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="89de2-163">Das CDN ruft Ihre Objekte von einem Standort ab, der als _Ursprung_bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="89de2-164">Ein Ursprung kann eine SharePoint-Website, eine Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="89de2-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="89de2-165">Sie haben eine große Flexibilität, wenn Sie den Ursprung für Ihre Organisation angeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="89de2-166">Sie können beispielsweise mehrere Ursprünge oder einen einzelnen Ursprung angeben, in dem Sie alle CDN-Objekte ablegen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="89de2-167">Sie können festlegen, dass sowohl öffentliche als auch private Ursprünge für Ihre Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="89de2-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="89de2-168">Die meisten Organisationen entscheiden sich für die Implementierung einer Kombination aus beiden.</span><span class="sxs-lookup"><span data-stu-id="89de2-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="89de2-169">Sie können neuen Container für ihre Herkunft wie Ordner oder Dokumentbibliotheken erstellen und Dateien hinzufügen, die Sie im CDN zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="89de2-170">Dies ist ein guter Ansatz, wenn Sie über einen bestimmten Satz von Objekten verfügen, die im CDN verfügbar sein sollen, und den Satz von CDN-Objekten auf diese Dateien im Container beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="89de2-171">Sie können auch eine vorhandene Websitesammlung, Website, Bibliothek oder einen Ordner als Ursprung konfigurieren, mit der alle berechtigten Ressourcen im Container im CDN verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="89de2-172">Bevor Sie einen vorhandenen Container als Ursprung hinzufügen, müssen Sie sicherstellen, dass Sie den Inhalt und die Berechtigungen kennen, damit Sie Objekte nicht versehentlich anonymen Zugriffen oder nicht autorisierten Benutzern offen legen.</span><span class="sxs-lookup"><span data-stu-id="89de2-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="89de2-173">Sie können _CDN-Richtlinien_ definieren, um Inhalte in ihren Ursprüngen aus dem CDN auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="89de2-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="89de2-174">CDN-Richtlinien schließen Objekte in öffentlichem oder privatem Ursprung durch Attribute wie _Dateityp_ und _Website Klassifizierung_aus und werden auf alle Ursprünge der CdnType (privat oder öffentlich) angewendet, die Sie in der Richtlinie angeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="89de2-175">Wenn Sie beispielsweise einen privaten Ursprung hinzufügen, der aus einer Website besteht, die mehrere Unterwebsites enthält, können Sie eine Richtlinie definieren, um als **vertraulich** gekennzeichnete Websites auszuschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="89de2-176">Die Richtlinie wird auf Inhalte _aller_ privaten Ursprünge angewendet, die Sie dem CDN hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="89de2-177">Beachten Sie, dass je größer die Anzahl der Ursprünge ist, desto größer sind die Auswirkungen auf die Zeit, die der CDN-Dienst zum Verarbeiten von Anforderungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="89de2-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="89de2-178">Es wird empfohlen, die Anzahl der Ursprünge so weit wie möglich zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="89de2-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="89de2-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="89de2-180">Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="89de2-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="89de2-181">Wenn Sie einen Ursprung identifizieren, geben Sie an, ob er _öffentlich_ oder _Privat_sein soll.</span><span class="sxs-lookup"><span data-stu-id="89de2-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="89de2-182">Der Zugriff auf CDN-Objekte im öffentlichen Ursprung ist anonym, und CDN-Inhalte in privater Herkunft werden durch dynamisch generierte Token für mehr Sicherheit gesichert.</span><span class="sxs-lookup"><span data-stu-id="89de2-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="89de2-183">Unabhängig davon, welche Option Sie auswählen, bietet Microsoft für Sie alle Schwerlasten, wenn es um die Verwaltung des CDN selbst geht.</span><span class="sxs-lookup"><span data-stu-id="89de2-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="89de2-184">Außerdem können Sie Ihre Meinung später ändern, nachdem Sie das CDN eingerichtet und ihre Ursprünge identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="89de2-185">Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungssteigerungen, aber jedes verfügt über eindeutige Attribute und Vorteile.</span><span class="sxs-lookup"><span data-stu-id="89de2-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="89de2-186">**Öffentliche** Ursprünge im Office 365 CDN sind anonym zugänglich, und auf gehostete Objekte kann jeder zugreifen, der über die URL der Ressource verfügt.</span><span class="sxs-lookup"><span data-stu-id="89de2-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="89de2-187">Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder.</span><span class="sxs-lookup"><span data-stu-id="89de2-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="89de2-188">**Private** Ursprünge im Office 365 CDN bieten privaten Zugriff auf Benutzer Inhalte wie SharePoint Online Dokumentbibliotheken, Websites und proprietäre Bilder.</span><span class="sxs-lookup"><span data-stu-id="89de2-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="89de2-189">Der Zugriff auf Inhalte in privater Herkunft wird durch dynamisch generierte Token gesichert, sodass nur Benutzer mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den Speicherort darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="89de2-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="89de2-190">Private Ursprünge im Office 365 CDN können nur für SharePoint Online Inhalte verwendet werden, und Sie können nur über die Umleitung von Ihrem SharePoint Online Mandanten auf Objekte im privaten Ursprung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="89de2-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="89de2-191">Sie können mehr darüber erfahren, wie der CDN-Zugriff auf Objekte in einem privaten Ursprung in der [Verwendung von Objekten in privater](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)Herkunft funktioniert.</span><span class="sxs-lookup"><span data-stu-id="89de2-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="89de2-192">Attribute und Vorteile des Hostens von Objekten im öffentlichen Ursprung</span><span class="sxs-lookup"><span data-stu-id="89de2-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="89de2-193">Objekte, die an einem öffentlichen Ursprung verfügbar gemacht werden, sind für jeden Benutzer anonym zugänglich.</span><span class="sxs-lookup"><span data-stu-id="89de2-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="89de2-194">Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="89de2-195">Wenn Sie ein Objekt aus einem öffentlichen Ursprung entfernen, ist es unter Umständen bis zu 30 Tage lang weiterhin über den Cache verfügbar. Links zu dem Objekt im CDN werden jedoch innerhalb von 15 Minuten ungültig.</span><span class="sxs-lookup"><span data-stu-id="89de2-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="89de2-196">Wenn Sie Stylesheets (CSS-Dateien) an einem öffentlichen Ursprung hosten, können Sie im Code relative Pfade und URIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="89de2-197">Dies bedeutet, dass Sie auf den Speicherort von Hintergrundbildern und anderen Objekten relativ zum Speicherort des Objekts, das sie aufruft, verweisen können.</span><span class="sxs-lookup"><span data-stu-id="89de2-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="89de2-198">Die URL eines öffentlichen Ursprungs kann zwar hartcodiert werden, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="89de2-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="89de2-199">Der Grund hierfür ist folgender: Wenn der Zugriff auf das CDN nicht mehr verfügbar ist, wird die URL nicht automatisch auf Ihre Organisation in SharePoint Online aufgelöst, was zu fehlerhaften Links und anderen Fehlern führen kann.</span><span class="sxs-lookup"><span data-stu-id="89de2-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="89de2-200">Zu den standardmäßigen Dateitypen, die für öffentliche Ursprünge gehören, Gehören CSS, EOT, GIF, ICO, JPEG, JPG, JS, map, PNG, SVG, ttf, WOFF und woff2.</span><span class="sxs-lookup"><span data-stu-id="89de2-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="89de2-201">Sie können zusätzliche Dateitypen angeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="89de2-202">Sie können eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die durch von Ihnen angegebene Website Klassifikationen identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="89de2-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="89de2-203">Beispielsweise können Sie alle Objekte ausschließen, die als „vertraulich“ oder „eingeschränkt“ gekennzeichnet sind, auch wenn sie einen zulässigen Dateityp haben und sich an einem öffentlichen Ursprung befinden.</span><span class="sxs-lookup"><span data-stu-id="89de2-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="89de2-204">Attribute und Vorteile des Hostens von Objekten in privater Herkunft</span><span class="sxs-lookup"><span data-stu-id="89de2-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="89de2-205">Private Origins können nur für SharePoint Online Objekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="89de2-206">Benutzer können nur auf die Objekte von einem privaten Ursprung aus zugreifen, wenn Sie über Berechtigungen für den Zugriff auf den Container verfügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="89de2-207">Der anonyme Zugriff auf diese Objekte wird verhindert.</span><span class="sxs-lookup"><span data-stu-id="89de2-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="89de2-208">Objekte im privaten Ursprung müssen vom SharePoint Online Mandanten verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="89de2-209">Der direkte Zugriff auf private CDN-Objekte funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="89de2-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="89de2-210">Wenn Sie ein Objekt aus dem privaten Ursprung entfernen, ist das Objekt möglicherweise bis zu einer Stunde nach dem Cache verfügbar. Es werden jedoch Links zu dem Objekt im CDN innerhalb von 15 Minuten nach dem Entfernen der Ressource ungültig.</span><span class="sxs-lookup"><span data-stu-id="89de2-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="89de2-211">Die standardmäßigen Dateitypen, die für private Ursprünge eingeschlossen werden, sind GIF, ICO, JPEG, JPG, JS und PNG.</span><span class="sxs-lookup"><span data-stu-id="89de2-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="89de2-212">Sie können zusätzliche Dateitypen angeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="89de2-213">Wie beim öffentlichen Ursprung können Sie eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die anhand von Website Klassifikationen identifiziert wurden, die Sie selbst dann angeben, wenn Sie Platzhalter verwenden, um alle Objekte in einen Ordner oder eine Dokumentbibliothek einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="89de2-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="89de2-214">Weitere Informationen dazu, warum Sie die Office 365 CDN, allgemeine CDN-Konzepte und andere Microsoft-CDNs verwenden können, die Sie mit Ihrem Office 365-Mandanten verwenden können, finden Sie unter [Content Delivery Networks](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="89de2-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="89de2-215">Standard-CDN-Ursprünge</span><span class="sxs-lookup"><span data-stu-id="89de2-215">Default CDN origins</span></span>

<span data-ttu-id="89de2-216">Wenn Sie nichts anderes angeben, legt Office 365 eine Standard Herkunft fest, wenn Sie das Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="89de2-217">Wenn Sie diese ursprünglich nicht anbieten möchten, können Sie diese Ursprünge nach Abschluss des Setups hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="89de2-218">Wenn Sie die Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen nicht verstehen und einen bestimmten Grund dafür haben, sollten Sie Sie beim Aktivieren des CDN erstellen lassen.</span><span class="sxs-lookup"><span data-stu-id="89de2-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="89de2-219">Standardmäßige private CDN-Ursprünge:</span><span class="sxs-lookup"><span data-stu-id="89de2-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="89de2-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="89de2-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="89de2-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="89de2-221">\*/siteassets</span></span>

<span data-ttu-id="89de2-222">Standardmäßige öffentliche CDN-Ursprünge:</span><span class="sxs-lookup"><span data-stu-id="89de2-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="89de2-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="89de2-223">\*/masterpage</span></span>
+ <span data-ttu-id="89de2-224">\*/Style-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="89de2-224">\*/style library</span></span>
+ <span data-ttu-id="89de2-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="89de2-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-226">_clientsideassets_ ist ein öffentlicher Standardursprung, der dem Office 365 CDN-Dienst im Dezember 2017 hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="89de2-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="89de2-227">Dieser Ursprung muss vorhanden sein, damit SharePoint-Framework-Lösungen im CDN funktionieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="89de2-228">Wenn Sie das Office 365 CDN vor Dezember 2017 aktiviert haben oder wenn Sie das Setup der Standard Ursprünge übersprungen haben, als Sie das CDN aktiviert haben, können Sie diesen Ursprung manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="89de2-229">Weitere Informationen finden Sie unter [meine clientseitige Webparts oder SharePoint Framework-Lösung funktioniert nicht](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span><span class="sxs-lookup"><span data-stu-id="89de2-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="89de2-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="89de2-231">Einrichten und Konfigurieren des Office 365 CDN mithilfe der SharePoint Online Management-Shell</span><span class="sxs-lookup"><span data-stu-id="89de2-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="89de2-232">Für die Verfahren in diesem Abschnitt müssen Sie die SharePoint Online-Verwaltungsshell verwenden, um eine Verbindung mit SharePoint Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="89de2-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="89de2-233">Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="89de2-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="89de2-234">Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe der SharePoint Online-Verwaltungsshell hostet.</span><span class="sxs-lookup"><span data-stu-id="89de2-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="89de2-235">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="89de2-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="89de2-236">Aktivieren Ihrer Organisation für die Verwendung des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="89de2-237">Bevor Sie Änderungen an den Mandanten-CDN-Einstellungen vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="89de2-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="89de2-238">Stellen Sie über die SharePoint Online-Verwaltungsshell eine Verbindung zu Ihrem Mandanten her:</span><span class="sxs-lookup"><span data-stu-id="89de2-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="89de2-239">Verwenden Sie nun das Cmdlet **Get-SPOTenantCdnEnabled** , um die CDN-Statuseinstellungen aus dem Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="89de2-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="89de2-240">Der Status des CDN für das angegebene CdnType-Objekt wird auf dem Bildschirm ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="89de2-241">Verwenden Sie das Cmdlet " **SPOTenantCdnEnabled** ", um Ihrer Organisation die Verwendung des Office 365 CDN zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89de2-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="89de2-242">Sie können Ihre Organisation in die Lage versetzen, öffentliche Ursprünge, private Ursprünge oder beides gleichzeitig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="89de2-243">Sie können das CDN auch so konfigurieren, dass das Setup von Standard Ursprüngen übersprungen wird, wenn Sie es aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="89de2-244">Sie können diese Ursprünge immer später wie in diesem Thema beschrieben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="89de2-245">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="89de2-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="89de2-246">Geben Sie beispielsweise den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="89de2-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="89de2-247">Geben Sie den folgenden Befehl ein, um zu ermöglichen, dass Ihre Organisation sowohl öffentliche als auch private Ursprünge verwendet, aber das Einrichten der Standard Ursprünge überspringt:</span><span class="sxs-lookup"><span data-stu-id="89de2-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="89de2-248">Unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) finden Sie Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, und die potenziellen Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen.</span><span class="sxs-lookup"><span data-stu-id="89de2-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="89de2-249">Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung von öffentlichen Ursprüngen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="89de2-250">Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung privater Origins zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="89de2-251">Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="89de2-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="89de2-253">Ändern der Liste der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen (optional)</span><span class="sxs-lookup"><span data-stu-id="89de2-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="89de2-254">Wenn Sie Dateitypen mithilfe des Cmdlets "Cmdlet **festlegen-SPOTenantCdnPolicy** " definieren, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-255">Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit ihren neuen Dateien in die Liste ein.</span><span class="sxs-lookup"><span data-stu-id="89de2-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="89de2-256">Verwenden Sie das Cmdlet " **SPOTenantCdnPolicy** ", um statische Dateitypen zu definieren, die von öffentlichen und privaten Quellen im CDN gehostet werden können.</span><span class="sxs-lookup"><span data-stu-id="89de2-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="89de2-257">Standardmäßig sind allgemeine Objekttypen zulässig, beispielsweise CSS, GIF, JPG und JS.</span><span class="sxs-lookup"><span data-stu-id="89de2-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="89de2-258">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="89de2-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="89de2-259">Um beispielsweise das CDN zum Hosten von CSS-und PNG-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="89de2-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="89de2-260">Verwenden Sie das Cmdlet **Get-SPOTenantCdnPolicies** , um zu sehen, welche Dateitypen derzeit im CDN zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="89de2-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="89de2-261">Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) und [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="89de2-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="89de2-263">Ändern Sie die Liste der Website Klassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional).</span><span class="sxs-lookup"><span data-stu-id="89de2-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="89de2-264">Wenn Sie Website Klassifizierungen mithilfe des Cmdlets " **SPOTenantCdnPolicy** " ausschließen, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-265">Wenn Sie zusätzliche Website Klassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie Sie dann zusammen mit ihren neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="89de2-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="89de2-266">Verwenden Sie das Cmdlet **Set-SPOTenantCdnPolicy** -Cmdlet zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="89de2-267">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="89de2-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="89de2-268">In Windows PowerShell für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="89de2-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="89de2-269">Um anzuzeigen, welche Website Klassifizierungen derzeit eingeschränkt sind, verwenden Sie das Cmdlet **Get-SPOTenantCdnPolicies** :</span><span class="sxs-lookup"><span data-stu-id="89de2-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="89de2-270">Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="89de2-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="89de2-271">Die _IncludeFileExtensions_ -Eigenschaft enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-272">Die standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten.</span><span class="sxs-lookup"><span data-stu-id="89de2-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="89de2-273">Die _ExcludeRestrictedSiteClassifications_ -Eigenschaft enthält die Website Klassifizierungen, die Sie aus dem CDN ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="89de2-274">Beispielsweise können Sie als **vertraulich** gekennzeichnete Websites ausschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="89de2-275">Die _ExcludeIfNoScriptDisabled_ -Eigenschaft schließt Inhalte aus dem CDN basierend auf den _NoScript_ -Attributeinstellungen auf Websiteebene aus.</span><span class="sxs-lookup"><span data-stu-id="89de2-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="89de2-276">Standardmäßig ist das _NoScript_ -Attribut auf für _moderne_ Websites **aktiviert** und für _klassische_ Websites **deaktiviert** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="89de2-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="89de2-277">Dies hängt von ihren Mandanten Einstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="89de2-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="89de2-278">Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) und [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="89de2-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="89de2-280">Hinzufügen eines Ursprungs für Ihre Objekte</span><span class="sxs-lookup"><span data-stu-id="89de2-280">Add an origin for your assets</span></span>

<span data-ttu-id="89de2-281">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um einen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="89de2-282">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-282">You can define multiple origins.</span></span> <span data-ttu-id="89de2-283">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89de2-284">Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="89de2-285">Der Wert von _path_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="89de2-286">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="89de2-287">Origins unterstützen Platzhalter für die URL.</span><span class="sxs-lookup"><span data-stu-id="89de2-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="89de2-288">Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Standorte erstrecken.</span><span class="sxs-lookup"><span data-stu-id="89de2-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="89de2-289">Geben Sie beispielsweise den folgenden Befehl ein, um alle Objekte im MasterPages-Ordner für alle Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="89de2-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="89de2-290">Der Platzhalter-Modifizierer \* **/** kann nur am Anfang des Pfads verwendet werden und wird allen URL-Segmenten unter der angegebenen URL zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="89de2-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="89de2-291">Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website deuten.</span><span class="sxs-lookup"><span data-stu-id="89de2-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="89de2-292">Beispielsweise wird der Pfad _\*/site1_ alle Dokumentbibliotheken unter der Website entsprechen.</span><span class="sxs-lookup"><span data-stu-id="89de2-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="89de2-293">Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="89de2-294">Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="89de2-295">In diesem Beispiel wird ein privater Ursprung der SiteAssets-Bibliothek auf einem bestimmten Standort hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="89de2-296">In diesem Beispiel wird ein privater Ursprung des _Folder1_ -Ordners in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="89de2-297">Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie entweder den Pfad in doppelte Anführungszeichen einschließen oder den Platz durch die URL-Codierung %20 ersetzen.</span><span class="sxs-lookup"><span data-stu-id="89de2-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="89de2-298">In den folgenden Beispielen wird ein privater Ursprung des Ordners _Folder 1_ in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="89de2-299">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-300">In privaten Quellen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor auf Sie über das CDN zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="89de2-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="89de2-301">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-302">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="89de2-304">Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Stilbibliothek für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="89de2-305">Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie das Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="89de2-306">Wenn Sie Sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="89de2-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="89de2-307">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um die Formatbibliothek als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="89de2-308">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="89de2-309">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="89de2-310">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-311">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="89de2-313">Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Website Objekte, Website Seiten und Veröffentlichungs Bilder für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="89de2-314">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Website Objekte als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="89de2-315">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Website Seiten als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="89de2-316">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Veröffentlichungs Bilder als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="89de2-317">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="89de2-318">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-319">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="89de2-321">Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="89de2-322">Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um eine Websitesammlung als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="89de2-323">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89de2-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="89de2-324">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="89de2-325">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-326">Möglicherweise wird eine _ausstehende Konfigurations_ Meldung angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="89de2-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="89de2-327">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="89de2-329">Verwalten des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="89de2-330">Nachdem Sie das CDN eingerichtet haben, können Sie, wie in diesem Abschnitt beschrieben, Änderungen an der Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder Ihre Anforderungen ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="89de2-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="89de2-332">Hinzufügen, aktualisieren oder Entfernen von Objekten aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="89de2-333">Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte aktualisieren oder entfernen, wann immer Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="89de2-334">Nehmen Sie einfach Ihre Änderungen an den Objekten im Ordner oder in der SharePoint-Bibliothek vor, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="89de2-335">Wenn Sie ein neues Objekt hinzufügen, steht es sofort über das CDN zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89de2-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="89de2-336">Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie weitergegeben wird und im CDN verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="89de2-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="89de2-337">Wenn Sie den Speicherort des Ursprungs abrufen möchten, können Sie das Cmdlet **Get-spotenantcdnorigins ausführen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="89de2-338">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-spotenantcdnorigins ausführen](https://technet.microsoft.com/library/mt790770.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="89de2-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="89de2-340">Entfernen eines Ursprungs aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="89de2-341">Sie können den Zugriff auf einen Ordner oder eine SharePoint-Bibliothek, den Sie als Ursprung identifiziert haben, entfernen.</span><span class="sxs-lookup"><span data-stu-id="89de2-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="89de2-342">Verwenden Sie dazu das Cmdlet **Remove-SPOTenantCdnOrigin** .</span><span class="sxs-lookup"><span data-stu-id="89de2-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="89de2-343">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="89de2-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="89de2-345">Ändern eines Ursprungs im Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="89de2-346">Sie können einen erstellten Ursprung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="89de2-347">Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen ein.</span><span class="sxs-lookup"><span data-stu-id="89de2-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="89de2-348">Weitere Informationen finden Sie unter [So entfernen Sie einen Ursprung aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) und [fügen einen Ursprung für Ihre Objekte hinzu](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span><span class="sxs-lookup"><span data-stu-id="89de2-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="89de2-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="89de2-350">Deaktivieren des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="89de2-351">Verwenden Sie das Cmdlet " **SPOTenantCdnEnabled** ", um das CDN für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="89de2-352">Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für das CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89de2-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="89de2-353">Geben Sie den folgenden Befehl ein, um die Verwendung der öffentlichen Herkunft im CDN zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="89de2-354">Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="89de2-355">Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="89de2-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="89de2-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="89de2-357">Einrichten und Konfigurieren des Office 365 CDN mithilfe von PNP PowerShell</span><span class="sxs-lookup"><span data-stu-id="89de2-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="89de2-358">Für die Verfahren in diesem Abschnitt müssen Sie PNP PowerShell verwenden, um eine Verbindung mit SharePoint Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="89de2-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="89de2-359">Anweisungen finden Sie unter [Erste Schritte mit PNP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span><span class="sxs-lookup"><span data-stu-id="89de2-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="89de2-360">Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe von PNP PowerShell hostet.</span><span class="sxs-lookup"><span data-stu-id="89de2-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="89de2-361">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="89de2-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="89de2-362">Aktivieren Ihrer Organisation für die Verwendung des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="89de2-363">Bevor Sie Änderungen an den Mandanten-CDN-Einstellungen vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="89de2-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="89de2-364">Stellen Sie über PNP PowerShell eine Verbindung zu Ihrem Mandanten her:</span><span class="sxs-lookup"><span data-stu-id="89de2-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="89de2-365">Verwenden Sie nun das Cmdlet **Get-PnPTenantCdnEnabled** , um die CDN-Statuseinstellungen aus dem Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="89de2-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="89de2-366">Der Status des CDN für das angegebene CdnType-Objekt wird auf dem Bildschirm ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="89de2-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="89de2-367">Verwenden Sie das Cmdlet " **PnPTenantCdnEnabled** ", um Ihrer Organisation die Verwendung des Office 365 CDN zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89de2-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="89de2-368">Sie können Ihre Organisation zur gleichzeitigen Verwendung von öffentlichem Ursprung, privatem Ursprung oder beides aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="89de2-369">Sie können das CDN auch so konfigurieren, dass das Setup von Standard Ursprüngen übersprungen wird, wenn Sie es aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="89de2-370">Sie können diese Ursprünge immer später wie in diesem Thema beschrieben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="89de2-371">In PNP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89de2-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="89de2-372">Geben Sie beispielsweise den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="89de2-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="89de2-373">Geben Sie den folgenden Befehl ein, um zu ermöglichen, dass Ihre Organisation sowohl öffentliche als auch private Ursprünge verwendet, aber das Einrichten der Standard Ursprünge überspringt:</span><span class="sxs-lookup"><span data-stu-id="89de2-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="89de2-374">Unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) finden Sie Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, und die potenziellen Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen.</span><span class="sxs-lookup"><span data-stu-id="89de2-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="89de2-375">Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung von öffentlichen Ursprüngen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="89de2-376">Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung privater Origins zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="89de2-377">Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="89de2-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="89de2-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="89de2-379">Ändern der Liste der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen (optional)</span><span class="sxs-lookup"><span data-stu-id="89de2-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="89de2-380">Wenn Sie Dateitypen mithilfe des Cmdlets "Cmdlet **festlegen-PnPTenantCdnPolicy** " definieren, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-381">Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit ihren neuen Dateien in die Liste ein.</span><span class="sxs-lookup"><span data-stu-id="89de2-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="89de2-382">Verwenden Sie das Cmdlet " **PnPTenantCdnPolicy** ", um statische Dateitypen zu definieren, die von öffentlichen und privaten Quellen im CDN gehostet werden können.</span><span class="sxs-lookup"><span data-stu-id="89de2-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="89de2-383">Standardmäßig sind allgemeine Objekttypen zulässig, beispielsweise CSS, GIF, JPG und JS.</span><span class="sxs-lookup"><span data-stu-id="89de2-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="89de2-384">In PNP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89de2-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="89de2-385">Um beispielsweise das CDN zum Hosten von CSS-und PNG-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="89de2-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="89de2-386">Verwenden Sie das Cmdlet **Get-PnPTenantCdnPolicies** , um zu sehen, welche Dateitypen derzeit im CDN zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="89de2-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="89de2-387">Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="89de2-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="89de2-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="89de2-389">Ändern Sie die Liste der Website Klassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional).</span><span class="sxs-lookup"><span data-stu-id="89de2-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="89de2-390">Wenn Sie Website Klassifizierungen mithilfe des Cmdlets " **PnPTenantCdnPolicy** " ausschließen, überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-391">Wenn Sie zusätzliche Website Klassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie Sie dann zusammen mit ihren neuen hinzu.</span><span class="sxs-lookup"><span data-stu-id="89de2-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="89de2-392">Verwenden Sie das Cmdlet " **PnPTenantCdnPolicy** ", um Website Klassifizierungen auszuschließen, die nicht über das CDN verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="89de2-393">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="89de2-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="89de2-394">In PNP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89de2-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="89de2-395">Um anzuzeigen, welche Website Klassifizierungen derzeit eingeschränkt sind, verwenden Sie das Cmdlet **Get-PnPTenantCdnPolicies** :</span><span class="sxs-lookup"><span data-stu-id="89de2-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="89de2-396">Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="89de2-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="89de2-397">Die _IncludeFileExtensions_ -Eigenschaft enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-398">Die standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten.</span><span class="sxs-lookup"><span data-stu-id="89de2-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="89de2-399">Die _ExcludeRestrictedSiteClassifications_ -Eigenschaft enthält die Website Klassifizierungen, die Sie aus dem CDN ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="89de2-400">Beispielsweise können Sie als **vertraulich** gekennzeichnete Websites ausschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="89de2-401">Die _ExcludeIfNoScriptDisabled_ -Eigenschaft schließt Inhalte aus dem CDN basierend auf den _NoScript_ -Attributeinstellungen auf Websiteebene aus.</span><span class="sxs-lookup"><span data-stu-id="89de2-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="89de2-402">Standardmäßig ist das _NoScript_ -Attribut auf für _moderne_ Websites **aktiviert** und für _klassische_ Websites **deaktiviert** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="89de2-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="89de2-403">Dies hängt von ihren Mandanten Einstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="89de2-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="89de2-404">Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="89de2-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="89de2-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="89de2-406">Hinzufügen eines Ursprungs für Ihre Objekte</span><span class="sxs-lookup"><span data-stu-id="89de2-406">Add an origin for your assets</span></span>

<span data-ttu-id="89de2-407">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um einen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="89de2-408">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-408">You can define multiple origins.</span></span> <span data-ttu-id="89de2-409">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89de2-410">Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="89de2-411">Der Wert von _path_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="89de2-412">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="89de2-413">Origins unterstützen Platzhalter für die URL.</span><span class="sxs-lookup"><span data-stu-id="89de2-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="89de2-414">Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Standorte erstrecken.</span><span class="sxs-lookup"><span data-stu-id="89de2-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="89de2-415">Geben Sie beispielsweise den folgenden Befehl ein, um alle Objekte im MasterPages-Ordner für alle Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="89de2-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="89de2-416">Der Platzhalter-Modifizierer \* **/** kann nur am Anfang des Pfads verwendet werden und wird allen URL-Segmenten unter der angegebenen URL zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="89de2-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="89de2-417">Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website deuten.</span><span class="sxs-lookup"><span data-stu-id="89de2-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="89de2-418">Beispielsweise wird der Pfad _\*/site1_ alle Dokumentbibliotheken unter der Website entsprechen.</span><span class="sxs-lookup"><span data-stu-id="89de2-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="89de2-419">Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="89de2-420">Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="89de2-421">In diesem Beispiel wird ein privater Ursprung der Bibliothek Website Objekte auf einem bestimmten Standort hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="89de2-422">In diesem Beispiel wird ein privater Ursprung des _Folder1_ -Ordners in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="89de2-423">Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie entweder den Pfad in doppelte Anführungszeichen einschließen oder den Platz durch die URL-Codierung %20 ersetzen.</span><span class="sxs-lookup"><span data-stu-id="89de2-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="89de2-424">In den folgenden Beispielen wird ein privater Ursprung des Ordners _Folder 1_ in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="89de2-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="89de2-425">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-426">In privaten Quellen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor auf Sie über das CDN zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="89de2-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="89de2-427">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-428">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="89de2-430">Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Stilbibliothek für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="89de2-431">Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie das Office 365 CDN aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="89de2-432">Wenn Sie Sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="89de2-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="89de2-433">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um die Formatbibliothek als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="89de2-434">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="89de2-435">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="89de2-436">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-437">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="89de2-439">Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Website Objekte, Website Seiten und Veröffentlichungs Bilder für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="89de2-440">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Website Objekte als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="89de2-441">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Website Seiten als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="89de2-442">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Veröffentlichungs Bilder als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="89de2-443">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="89de2-444">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-445">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="89de2-447">Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="89de2-448">Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um eine Websitesammlung als privaten Ursprung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="89de2-449">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89de2-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="89de2-450">Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="89de2-451">Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg.</span><span class="sxs-lookup"><span data-stu-id="89de2-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="89de2-452">Möglicherweise wird eine _ausstehende Konfigurations_ Meldung angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="89de2-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="89de2-453">Dies kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="89de2-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="89de2-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="89de2-455">Verwalten des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="89de2-456">Nachdem Sie das CDN eingerichtet haben, können Sie, wie in diesem Abschnitt beschrieben, Änderungen an der Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder Ihre Anforderungen ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="89de2-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="89de2-458">Hinzufügen, aktualisieren oder Entfernen von Objekten aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="89de2-459">Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte aktualisieren oder entfernen, wann immer Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="89de2-460">Nehmen Sie einfach Ihre Änderungen an den Objekten im Ordner oder in der SharePoint-Bibliothek vor, die Sie als Ursprung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="89de2-461">Wenn Sie ein neues Objekt hinzufügen, steht es sofort über das CDN zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89de2-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="89de2-462">Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie weitergegeben wird und im CDN verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="89de2-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="89de2-463">Wenn Sie den Speicherort des Ursprungs abrufen möchten, können Sie das Cmdlet **Get-PnPTenantCdnOrigin** verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="89de2-464">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="89de2-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="89de2-466">Entfernen eines Ursprungs aus dem Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="89de2-467">Sie können den Zugriff auf einen Ordner oder eine SharePoint-Bibliothek, den Sie als Ursprung identifiziert haben, entfernen.</span><span class="sxs-lookup"><span data-stu-id="89de2-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="89de2-468">Verwenden Sie dazu das Cmdlet **Remove-PnPTenantCdnOrigin** .</span><span class="sxs-lookup"><span data-stu-id="89de2-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="89de2-469">Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="89de2-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="89de2-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="89de2-471">Ändern eines Ursprungs im Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="89de2-472">Sie können einen erstellten Ursprung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="89de2-473">Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen ein.</span><span class="sxs-lookup"><span data-stu-id="89de2-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="89de2-474">Weitere Informationen finden Sie unter [So entfernen Sie einen Ursprung aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) und [fügen einen Ursprung für Ihre Objekte hinzu](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="89de2-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="89de2-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="89de2-476">Deaktivieren des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="89de2-477">Verwenden Sie das Cmdlet " **PnPTenantCdnEnabled** ", um das CDN für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="89de2-478">Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für das CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89de2-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="89de2-479">Geben Sie den folgenden Befehl ein, um die Verwendung der öffentlichen Herkunft im CDN zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="89de2-480">Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="89de2-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="89de2-481">Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="89de2-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="89de2-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="89de2-483">Einrichten und Konfigurieren des Office 365 CDN mithilfe von Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="89de2-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="89de2-484">Für die Verfahren in diesem Abschnitt müssen Sie die [Office 365 CLI](https://aka.ms/o365cli)installiert haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="89de2-485">Stellen Sie als nächstes eine Verbindung mit dem Office 365-Mandanten mithilfe des [Login](https://pnp.github.io/office365-cli/cmd/login/) -Befehls her.</span><span class="sxs-lookup"><span data-stu-id="89de2-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="89de2-486">Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe der Office 365 CLI hostet.</span><span class="sxs-lookup"><span data-stu-id="89de2-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="89de2-487">Zum Erweitern klicken</span><span class="sxs-lookup"><span data-stu-id="89de2-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="89de2-488">Aktivieren Sie das Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="89de2-489">Sie können den Status des Office 365 CDN in Ihrem Mandanten mithilfe des Cmdlets [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) verwalten.</span><span class="sxs-lookup"><span data-stu-id="89de2-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="89de2-490">Um das öffentliche Office 365 CDN in Ihrem Mandanten zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="89de2-491">Um die Office 365 SharePoint CDN zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="89de2-492">Anzeigen des aktuellen Status des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="89de2-493">Um zu überprüfen, ob der bestimmte Typ von Office 365 CDN aktiviert oder deaktiviert ist, verwenden Sie den Befehl [SPO CDN Get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .</span><span class="sxs-lookup"><span data-stu-id="89de2-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="89de2-494">Um zu überprüfen, ob das öffentliche Office 365 CDN aktiviert ist, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="89de2-495">Anzeigen der Office 365 CDN-Ursprünge</span><span class="sxs-lookup"><span data-stu-id="89de2-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="89de2-496">Um die derzeit konfigurierten öffentlichen Office 365 CDN-Ursprünge anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="89de2-497">Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, finden Sie unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) .</span><span class="sxs-lookup"><span data-stu-id="89de2-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="89de2-498">Hinzufügen eines Office 365 CDN-Ursprungs</span><span class="sxs-lookup"><span data-stu-id="89de2-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89de2-499">Sie sollten niemals Ressourcen, die als vertraulich für Ihre Organisation betrachtet werden, in einer SharePoint-Dokumentbibliothek platzieren, die als öffentlicher Ursprung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="89de2-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="89de2-500">Verwenden Sie den Befehl [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) zum Definieren eines CDN-Ursprungs.</span><span class="sxs-lookup"><span data-stu-id="89de2-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="89de2-501">Sie können mehrere Ursprünge definieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-501">You can define multiple origins.</span></span> <span data-ttu-id="89de2-502">Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89de2-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="89de2-503">Dabei `path` ist der relative Pfad zu dem Ordner, der die Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="89de2-504">Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="89de2-505">Wenn Sie alle Objekte im **gestaltungsvorlagenkatalog** aller Websites als öffentlichen Ursprung einbeziehen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="89de2-506">Um einen privaten Ursprung für eine bestimmte Websitesammlung zu konfigurieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="89de2-507">Nach dem Hinzufügen eines CDN-Ursprungs dauert es bis zu 15 Minuten, bis Sie Dateien mithilfe des CDN-Diensts abrufen können.</span><span class="sxs-lookup"><span data-stu-id="89de2-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="89de2-508">Sie können überprüfen, ob der betreffende Ursprung bereits aktiviert wurde, indem Sie den Befehl [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="89de2-509">Entfernen eines Office 365 CDN-Ursprungs</span><span class="sxs-lookup"><span data-stu-id="89de2-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="89de2-510">Verwenden Sie den Befehl [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/), um einen CDN-Ursprung für den angegebenen CDN-Typ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="89de2-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="89de2-511">Wenn Sie einen öffentlichen Ursprung aus der CDN-Konfiguration entfernen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="89de2-512">Das Entfernen eines CDN-Ursprungs wirkt sich nicht auf die Dateien aus, die in einer Dokumentbibliothek gespeichert sind, die diesem Ursprung entspricht.</span><span class="sxs-lookup"><span data-stu-id="89de2-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="89de2-513">Wenn auf diese Objekte über Ihre SharePoint-URL verwiesen wurde, wechselt SharePoint automatisch wieder zu der ursprünglichen URL, die auf die Dokumentbibliothek zeigt.</span><span class="sxs-lookup"><span data-stu-id="89de2-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="89de2-514">Wenn jedoch auf Objekte mithilfe einer öffentlichen CDN-URL verwiesen wurde, wird durch das Entfernen des Ursprungs die Verknüpfung aufgehoben, und Sie müssen Sie manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="89de2-515">Ändern eines Office 365 CDN-Ursprungs</span><span class="sxs-lookup"><span data-stu-id="89de2-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="89de2-516">Es ist nicht möglich, einen vorhandenen CDN-Ursprung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="89de2-517">Stattdessen sollten Sie den zuvor definierten CDN-Ursprung mit dem Befehl `spo cdn origin remove` entfernen und mit dem Befehl `spo cdn origin add` einen neuen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89de2-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="89de2-518">Ändern der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="89de2-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="89de2-519">Standardmäßig sind die folgenden Dateitypen in den CDN-Dateien enthalten: _CSS, EOT, GIF, ICO, JPEG, JPG, JS, map, PNG, SVG, ttf, WOFF und woff2_.</span><span class="sxs-lookup"><span data-stu-id="89de2-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="89de2-520">Wenn Sie weitere Dateitypen in das CDN einbeziehen müssen, können Sie die CDN-Konfiguration mit dem Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) ändern.</span><span class="sxs-lookup"><span data-stu-id="89de2-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-521">Durch das Ändern der Liste von Dateitypen überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-522">Wenn Sie weitere Dateitypen einbeziehen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), um herauszufinden, welche Dateitypen derzeit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="89de2-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="89de2-523">Um den _JSON_ -Dateityp der Standardliste der im öffentlichen CDN enthaltenen Dateitypen hinzuzufügen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89de2-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="89de2-524">Ändern der Liste von Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="89de2-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="89de2-525">Verwenden Sie den Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="89de2-526">Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="89de2-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-527">Durch das Ändern der Liste der ausgeschlossenen Websiteklassifizierungen überschreiben Sie die aktuell definierte Liste.</span><span class="sxs-lookup"><span data-stu-id="89de2-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="89de2-528">Wenn Sie zusätzliche Klassifizierungen ausschließen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), um herauszufinden, welche Klassifizierungen derzeit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="89de2-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="89de2-529">Zum Ausschließen von als _HBI_ klassifizierten Websites aus dem öffentlichen CDN führen Sie</span><span class="sxs-lookup"><span data-stu-id="89de2-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="89de2-530">Deaktivieren des Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="89de2-531">Um das Office 365 CDN zu deaktivieren, verwenden Sie den Befehl `spo cdn set`. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89de2-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="89de2-532">Verwenden Ihrer CDN-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="89de2-532">Using your CDN assets</span></span>

<span data-ttu-id="89de2-533">Nachdem Sie nun das CDN und die konfigurierten Ursprünge und Richtlinien aktiviert haben, können Sie mit der Verwendung ihrer CDN-Objekte beginnen.</span><span class="sxs-lookup"><span data-stu-id="89de2-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="89de2-534">In diesem Abschnitt erfahren Sie, wie Sie CDN-URLs in SharePoint-Seiten und-Inhalten verwenden, damit SharePoint-Anforderungen für Objekte sowohl in öffentlichen als auch privaten Quellen an das CDN umleiten.</span><span class="sxs-lookup"><span data-stu-id="89de2-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="89de2-535">Aktualisieren von Links zu CDN-Objekten</span><span class="sxs-lookup"><span data-stu-id="89de2-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="89de2-536">Verwenden von Objekten im öffentlichen Ursprung</span><span class="sxs-lookup"><span data-stu-id="89de2-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="89de2-537">Verwenden von Objekten im privaten Ursprung</span><span class="sxs-lookup"><span data-stu-id="89de2-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="89de2-538">Informationen zum Verwenden des CDN zum Hosten clientseitiger Webparts finden Sie im Thema Hosten des [clientseitigen Webparts aus Office 365 CDN (Hello World Teil 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span><span class="sxs-lookup"><span data-stu-id="89de2-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-539">Wenn Sie den Ordner _ClientSideAssets_ der Liste **private** CDN Origins hinzufügen, wird das Rendern von in CDN gehosteten benutzerdefinierten Webparts nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="89de2-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="89de2-540">Dateien, die von SPFX-Webparts verwendet werden, können nur das öffentliche CDN verwenden, und der ClientSideAssets-Ordner ist ein Standardursprung für das öffentliche CDN.</span><span class="sxs-lookup"><span data-stu-id="89de2-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="89de2-541">Aktualisieren von Links zu CDN-Objekten</span><span class="sxs-lookup"><span data-stu-id="89de2-541">Updating links to CDN assets</span></span>

<span data-ttu-id="89de2-542">Um Objekte zu verwenden, die Sie einem Ursprung hinzugefügt haben, aktualisieren Sie einfach Links zur ursprünglichen Datei mit dem Pfad zur Datei im Ursprung.</span><span class="sxs-lookup"><span data-stu-id="89de2-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="89de2-543">Bearbeiten Sie die Seite oder den Inhalt, die Links zu Objekten enthält, die Sie zu einem Ursprung hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="89de2-544">Sie können auch eine von mehreren Methoden verwenden, um Links in einer Website oder Websitesammlung Global zu suchen und zu ersetzen, wenn Sie den Link zu einem bestimmten Objekt überall dort aktualisieren möchten, wo es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="89de2-545">Ersetzen Sie für jeden Link zu einem Objekt in einem Ursprung den Pfad durch den Pfad zu der Datei im CDN-Ursprung.</span><span class="sxs-lookup"><span data-stu-id="89de2-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="89de2-546">Sie können relative Pfade verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-546">You can use relative paths.</span></span>
+ <span data-ttu-id="89de2-547">Speichern Sie die Seite oder den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="89de2-547">Save the page or content.</span></span>

<span data-ttu-id="89de2-548">Sehen Sie sich beispielsweise das Bild _/Site/SiteAssets/Images/image.png_an, das Sie in den Dokumentbibliotheksordner _/Site/CDN_origins/Public/_ kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="89de2-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="89de2-549">Um das CDN-Objekt zu verwenden, ersetzen Sie den ursprünglichen Pfad zum Speicherort der Bild Datei durch den Pfad zum Ursprung, um die neue URL _/Site/CDN_origins/Public/image.png_zu machen.</span><span class="sxs-lookup"><span data-stu-id="89de2-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="89de2-550">Wenn Sie die vollständige URL für das Objekt anstelle eines relativen Pfads verwenden möchten, erstellen Sie den Link wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89de2-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="89de2-551">Im Allgemeinen sollten Sie URLs nicht direkt in Objekten im CDN hartcodieren.</span><span class="sxs-lookup"><span data-stu-id="89de2-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="89de2-552">Sie können jedoch URLs für Objekte im öffentlichen Ursprung bei Bedarf manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="89de2-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="89de2-553">Weitere Informationen finden Sie unter [hartcodieren von CDN-URLs für öffentliche Objekte](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="89de2-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="89de2-554">Informationen dazu, wie Sie überprüfen können, ob Objekte aus dem CDN bedient werden, finden Sie unter [wie kann ich bestätigen, dass Objekte vom CDN bedient werden?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in der [Problembehandlung im Abschnitt Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="89de2-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="89de2-555">Verwenden von Objekten im öffentlichen Ursprung</span><span class="sxs-lookup"><span data-stu-id="89de2-555">Using assets in public origins</span></span>

<span data-ttu-id="89de2-556">Das **Veröffentlichungsfeature** in SharePoint Online schreibt automatisch URLs von Objekten, die im öffentlichen Ursprung gespeichert sind, in Ihre CDN-äquivalente um, sodass Objekte vom CDN-Dienst anstelle von SharePoint bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="89de2-557">Wenn sich Ihr Ursprung in einer Website befindet, in der das Veröffentlichungsfeature aktiviert ist, und die Objekte, die Sie an das CDN Abladen möchten, sich in einer der folgenden Kategorien befinden, werden von SharePoint automatisch URLs für Objekte im Ursprung umgeschrieben, vorausgesetzt, das Objekt wurde nicht durch eine CDN-Richtlinie ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="89de2-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="89de2-558">Es folgt eine Übersicht über die Links, die automatisch vom SharePoint-Veröffentlichungsfeature umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="89de2-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="89de2-559">IMG/LINK/CSS-URLs in den HTML-Antworten klassischer Veröffentlichungsseiten</span><span class="sxs-lookup"><span data-stu-id="89de2-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="89de2-560">Dies schließt von Autoren im HTML-Inhalt einer Seite hinzugefügte Bilder ein.</span><span class="sxs-lookup"><span data-stu-id="89de2-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="89de2-561">Bild-URLs des Webparts „Bildbibliothek-Bildschirmpräsentation“</span><span class="sxs-lookup"><span data-stu-id="89de2-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="89de2-562">Bildfelder in Ergebnissen der SPList-REST-API (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="89de2-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="89de2-563">Verwenden Sie die neue Eigenschaft _ImageFieldsToTryRewriteToCdnUrls_ , um eine durch Kommas getrennte Liste von Feldern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="89de2-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="89de2-564">Unterstützt Hyperlink-Felder und Publishing Image-Felder</span><span class="sxs-lookup"><span data-stu-id="89de2-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="89de2-565">SharePoint-Bildwiedergaben</span><span class="sxs-lookup"><span data-stu-id="89de2-565">SharePoint image renditions</span></span>

<span data-ttu-id="89de2-566">Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite erhält, die Objekte aus einem öffentlichen Ursprung enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="89de2-567">![Workflow Diagramm: Abrufen Office 365 CDN-Ressourcen von einem öffentlichen Ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Abrufen von Office 365 CDN-Ressourcen von einem öffentlichen Ursprung")</span><span class="sxs-lookup"><span data-stu-id="89de2-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="89de2-568">Wenn Sie die automatische Umschreibung für bestimmte URLs auf einer Seite deaktivieren möchten, können Sie die Seite Auschecken und den Abfragezeichenfolgenparameter hinzufügen **? NoAutoReWrites = true** an das Ende jeder Verknüpfung, die Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="89de2-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="89de2-569">Codieren von CDN-URLs für öffentliche Objekte</span><span class="sxs-lookup"><span data-stu-id="89de2-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="89de2-570">Wenn das _Veröffentlichungs_ Feature nicht für einen öffentlichen Ursprung aktiviert ist oder wenn es sich nicht um einen der Linktypen handelt, die von der Funktion zum automatischen Umschreiben des CDN-Diensts unterstützt werden, können Sie URLs manuell für den CDN-Speicherort der Objekte erstellen und diese URLs in ihren Inhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="89de2-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-571">Sie können CDN-URLs nicht für Objekte in einem privaten Ursprung hartcodieren, da das erforderliche Zugriffstoken, das den letzten Abschnitt der URL bildet, zu dem Zeitpunkt generiert wird, zu dem die Ressource angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="89de2-572">Für öffentliche CDN-Objekte wird das URL-Format wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="89de2-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="89de2-573">Ersetzen Sie **TenantHostName** durch ihren Mandantennamen.</span><span class="sxs-lookup"><span data-stu-id="89de2-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="89de2-574">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89de2-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="89de2-575">Verwenden von Objekten im privaten Ursprung</span><span class="sxs-lookup"><span data-stu-id="89de2-575">Using assets in private origins</span></span>

<span data-ttu-id="89de2-576">Für die Verwendung von Objekten in privater Herkunft ist keine zusätzliche Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89de2-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="89de2-577">SharePoint Online automatisch URLs für Objekte in privater Herkunft umschreibt, sodass Anforderungen für diese Objekte immer vom CDN bedient werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="89de2-578">Sie können keine URLs manuell für CDN-Objekte in privater Herkunft erstellen, da diese URLs Token enthalten, die von SharePoint Online automatisch generiert werden müssen, wenn das Objekt angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="89de2-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="89de2-579">Der Zugriff auf Objekte im privaten Ursprung wird durch dynamisch generierte Token geschützt, die auf Benutzerberechtigungen für den Ursprung basieren, wobei die in den folgenden Abschnitten beschriebenen Einschränkungen beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="89de2-580">Benutzer benötigen mindestens **Lese** Zugriff auf die Ursprünge des CDN zum Rendern von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="89de2-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="89de2-581">Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite erhält, die Objekte aus einem privaten Ursprung enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="89de2-582">![Workflow Diagramm: Abrufen von Office 365 CDN-Ressourcen aus einem privaten Ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Abrufen von Office 365 CDN-Ressourcen aus einem privaten Ursprung")</span><span class="sxs-lookup"><span data-stu-id="89de2-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="89de2-583">Token-basierte Autorisierung in privater Herkunft</span><span class="sxs-lookup"><span data-stu-id="89de2-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="89de2-584">Der Zugriff auf Objekte im privaten Ursprung im Office 365 CDN wird durch von SharePoint Online generierte Token gewährt.</span><span class="sxs-lookup"><span data-stu-id="89de2-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="89de2-585">Benutzer, die bereits über Berechtigungen für den Zugriff auf den vom Ursprung benannten Ordner oder die Bibliothek verfügen, erhalten automatisch Token, die dem Benutzer den Zugriff auf die Datei basierend auf Ihrer Berechtigungsstufe ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89de2-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="89de2-586">Diese Zugriffstoken sind gültig für 30 bis 90 Minuten, nachdem Sie generiert wurden, um die Wiedergabe von Token zu schützen.</span><span class="sxs-lookup"><span data-stu-id="89de2-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="89de2-587">Nachdem das Zugriffstoken generiert wurde, gibt SharePoint Online einen benutzerdefinierten URI an den Client zurück, der zwei Autorisierungsparameter " _Eat_ " (Edge Authorization Token) und _OAT_ (Origin Authorization Token) enthält.</span><span class="sxs-lookup"><span data-stu-id="89de2-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="89de2-588">Die Struktur der einzelnen Token ist _< "Ablaufzeit im Epoch Time-Format" >__< "Secure Signature" >_.</span><span class="sxs-lookup"><span data-stu-id="89de2-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="89de2-589">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89de2-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="89de2-590">Jeder, der das Token besitzt, kann auf die Ressource im CDN zugreifen.</span><span class="sxs-lookup"><span data-stu-id="89de2-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="89de2-591">URLs, die diese Zugriffstoken enthalten, werden jedoch nur über HTTPS freigegeben, sodass nicht autorisierte Benutzer auf das Objekt nicht zugreifen können, wenn die URL nicht explizit von einem Endbenutzer freigegeben wird, bevor das Token abläuft.</span><span class="sxs-lookup"><span data-stu-id="89de2-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="89de2-592">Berechtigungen auf Elementebene werden für Objekte im privaten Ursprung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89de2-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="89de2-593">Es ist wichtig zu beachten, dass SharePoint Online keine Berechtigungen auf Elementebene für Objekte in privater Herkunft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89de2-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="89de2-594">Beispielsweise haben Benutzer bei einer Datei `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , die sich unter den folgenden Bedingungen befindet, effektiven Zugriff auf die Datei:</span><span class="sxs-lookup"><span data-stu-id="89de2-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="89de2-595">Benutzer</span><span class="sxs-lookup"><span data-stu-id="89de2-595">User</span></span>  |<span data-ttu-id="89de2-596">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="89de2-596">Permissions</span></span>  |<span data-ttu-id="89de2-597">Effektiver Zugriff</span><span class="sxs-lookup"><span data-stu-id="89de2-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="89de2-598">Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="89de2-598">User 1</span></span>     |<span data-ttu-id="89de2-599">Zugriff auf Folder1</span><span class="sxs-lookup"><span data-stu-id="89de2-599">Has access to folder1</span></span>         |<span data-ttu-id="89de2-600">Zugriff auf image1.jpg aus dem CDN möglich</span><span class="sxs-lookup"><span data-stu-id="89de2-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="89de2-601">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="89de2-601">User 2</span></span>     |<span data-ttu-id="89de2-602">Kein Zugriff auf Folder1</span><span class="sxs-lookup"><span data-stu-id="89de2-602">Does not have access to folder1</span></span>         |<span data-ttu-id="89de2-603">Zugriff auf image1.jpg aus dem CDN nicht möglich</span><span class="sxs-lookup"><span data-stu-id="89de2-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="89de2-604">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="89de2-604">User 3</span></span>     |<span data-ttu-id="89de2-605">Verfügt nicht über Zugriff auf Folder1, erhält jedoch explizite Berechtigungen für den Zugriff auf image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="89de2-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="89de2-606">Kann direkt von SharePoint Online auf das Objekt image1.jpg zugreifen, jedoch nicht aus dem CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="89de2-607">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="89de2-607">User 4</span></span>     |<span data-ttu-id="89de2-608">Hat Zugriff auf Folder1, wurde jedoch explizit den Zugriff auf image1.jpg in SharePoint Online verweigert.</span><span class="sxs-lookup"><span data-stu-id="89de2-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="89de2-609">Der Zugriff auf das Objekt ist nicht von SharePoint Online möglich, kann jedoch aus dem CDN auf das Objekt zugreifen, obwohl der Zugriff auf die Datei in SharePoint Online verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="89de2-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="89de2-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="89de2-611">Problembehandlung beim Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="89de2-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="89de2-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="89de2-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="89de2-613">Wie bestätige ich, dass Objekte vom CDN bereitgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="89de2-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="89de2-614">Nachdem Sie einer Seite Links zu CDN-Objekten hinzugefügt haben, können Sie überprüfen, ob das Objekt vom CDN bedient wird, indem Sie zur Seite navigieren, mit der rechten Maustaste auf das Bild klicken, nachdem es gerendert und die Bild-URL überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="89de2-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="89de2-615">Sie können auch die Entwicklertools Ihres Browsers verwenden, um die URL für jedes Objekt auf einer Seite anzuzeigen, oder verwenden Sie ein Netzwerk Ablaufverfolgungstool eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="89de2-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="89de2-616">Wenn Sie ein Netzwerktool wie Fiddler verwenden, um Ihre Objekte außerhalb des Renderings des Objekts von einer SharePoint-Seite zu testen, müssen Sie den Referer-Header "Referer: `https://yourdomain.sharepoint.com` " manuell zur Get-Anforderung hinzufügen, wobei die URL die Stamm-URL des SharePoint Online Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="89de2-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="89de2-617">Sie können CDN-URLs nicht direkt in einem Webbrowser testen, da ein Referer aus SharePoint Online stammen muss.</span><span class="sxs-lookup"><span data-stu-id="89de2-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="89de2-618">Wenn Sie jedoch die CDN-Ressourcen-URL zu einer SharePoint-Seite hinzufügen und dann die Seite in einem Browser öffnen, wird das auf der Seite gerenderte CDN-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89de2-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="89de2-619">Weitere Informationen zur Verwendung der Entwicklertools im Microsoft Edge-Browser finden Sie unter [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="89de2-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="89de2-620">Wenn Sie ein kurzes Video im [YouTube-Kanal für SharePoint-Entwickler Muster und-Methoden](https://aka.ms/sppnp-videos) sehen möchten, in dem gezeigt wird, wie Sie überprüfen können, ob Ihr CDN funktioniert, lesen Sie bitte [Überprüfen der CDN-Nutzung und sicherstellen einer optimalen Netzwerkkonnektivität](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span><span class="sxs-lookup"><span data-stu-id="89de2-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="89de2-621">Warum sind Objekte aus einem neuen Ursprung nicht verfügbar?</span><span class="sxs-lookup"><span data-stu-id="89de2-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="89de2-622">Objekte in neuem Ursprung stehen nicht sofort zur Verwendung zur Verfügung, da es Zeit dauert, bis sich die Registrierung über das CDN verbreitet und die Ressourcen vom Ursprung bis zum CDN-Speicher hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="89de2-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="89de2-623">Die erforderliche Zeit für die Verfügbarkeit von Objekten im CDN hängt davon ab, wie viele Objekte und Dateigrößen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="89de2-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="89de2-624">Mein clientseitiges Webpart oder SharePoint Framework-Lösung funktioniert nicht</span><span class="sxs-lookup"><span data-stu-id="89de2-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="89de2-625">Wenn Sie das Office 365 CDN für öffentliche Ursprünge aktivieren, erstellt der CDN-Dienst automatisch diese Standard Ursprünge:</span><span class="sxs-lookup"><span data-stu-id="89de2-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="89de2-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="89de2-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="89de2-627">\*/Style-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="89de2-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="89de2-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="89de2-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="89de2-629">Wenn der \*/clientsideassets-Ursprung fehlt, treten bei SharePoint-Framework-Lösungen Fehler auf, und es werden keine Warnungen oder Fehlermeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="89de2-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="89de2-630">Dieser Ursprung fehlt möglicherweise, weil das CDN aktiviert wurde, wenn der Parameter _-NoDefaultOrigins_ auf **$true**festgelegt wurde oder der Ursprung manuell gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="89de2-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="89de2-631">Sie können überprüfen, welche Ursprünge mit dem folgenden PowerShell-Befehl vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="89de2-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="89de2-632">Oder Sie können mit der Office 365 CLI überprüfen:</span><span class="sxs-lookup"><span data-stu-id="89de2-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="89de2-633">So fügen Sie den Ursprung in PowerShell hinzu:</span><span class="sxs-lookup"><span data-stu-id="89de2-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="89de2-634">So fügen Sie den Ursprung in der Office 365 CLI hinzu:</span><span class="sxs-lookup"><span data-stu-id="89de2-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="89de2-635">Welche PowerShell-Module und CLI-Shells muss ich mit dem Office 365 CDN verwenden?</span><span class="sxs-lookup"><span data-stu-id="89de2-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="89de2-636">Sie können mit dem Office 365 CDN entweder mithilfe des PowerShell-Moduls von **SharePoint Online Verwaltungsshell** oder der **Office 365 CLI**arbeiten.</span><span class="sxs-lookup"><span data-stu-id="89de2-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="89de2-637">Erste Schritte mit der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="89de2-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="89de2-638">Installieren von Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="89de2-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="89de2-639">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89de2-639">See also</span></span>

[<span data-ttu-id="89de2-640">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="89de2-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="89de2-641">Netzwerkplanung und Leistungsoptimierung für Office 365</span><span class="sxs-lookup"><span data-stu-id="89de2-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="89de2-642">SharePoint-Leistungsreihe-Office 365 CDN-Videoreihe</span><span class="sxs-lookup"><span data-stu-id="89de2-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
