---
title: Office 365 Content Delivery Network (CDN) Schnellstart
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) Schnellstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921594"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="44821-103">Office 365 Content Delivery Network (CDN) Schnellstart</span><span class="sxs-lookup"><span data-stu-id="44821-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="44821-104">Mit dem integrierten **Office 365 Content Delivery Network (CDN)** können Sie statische Objekte (Bilder, JavaScript, Stylesheets, WOFF-Dateien) hosten, um eine bessere Leistung für Ihre SharePoint Onlineseiten zu bieten.</span><span class="sxs-lookup"><span data-stu-id="44821-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="44821-105">Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="44821-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="44821-106">Darüber hinaus verwendet Office 365 CDN http/2-Protokoll für verbesserte Komprimierung und HTTP-Pipelining.</span><span class="sxs-lookup"><span data-stu-id="44821-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="44821-107">Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.</span><span class="sxs-lookup"><span data-stu-id="44821-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="44821-108">Ausführlichere Informationen finden Sie unter [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="44821-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="44821-109">Die Office 365 CDN ist nur für Mandanten in der Produktions-Cloud (weltweit) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44821-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="44821-110">Mandanten in der US-Regierung, China und Deutschland unterstützen die Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="44821-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="44821-111">Verwenden Sie das Tool Seitendiagnose für SharePoint, um Elemente zu identifizieren, die nicht in CDN</span><span class="sxs-lookup"><span data-stu-id="44821-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="44821-112">Sie können  die Seitendiagnose für SharePoint-Browsererweiterung verwenden, um Objekte auf Ihren SharePoint Online-Seiten auflisten zu können, die einem CDN hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="44821-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="44821-113">Das **Tool Seitendiagnose für SharePoint** ist eine Browsererweiterung für die neuen browser Microsoft Edge ( und Chrome-Browser, die sowohl moderne SharePoint Online-Portal- als auch klassische https://www.microsoft.com/edge) Veröffentlichungswebsiteseiten analysiert.</span><span class="sxs-lookup"><span data-stu-id="44821-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="44821-114">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="44821-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="44821-115">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](./page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="44821-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="44821-116">Wenn Sie das Tool Seitendiagnose für SharePoint auf einer SharePoint Online-Seite ausführen, können Sie auf die Registerkarte Diagnosetests klicken, um eine Liste der Objekte zu sehen, die nicht von der Website gehostet CDN. </span><span class="sxs-lookup"><span data-stu-id="44821-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="44821-117">Diese Objekte werden unter der Überschrift Content Delivery Network **(CDN) aufgelistet,** wie im screenshot unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="44821-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Seitendiagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="44821-119">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44821-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="44821-120">CDN Übersicht</span><span class="sxs-lookup"><span data-stu-id="44821-120">CDN Overview</span></span>

<span data-ttu-id="44821-121">Das Office 365 CDN dient dazu, die Leistung für Benutzer zu optimieren, indem häufig verwendete Objekte wie Bilder und Javascriptdateien über ein globales Hochgeschwindigkeitsnetzwerk verteilt werden, die Ladezeit der Seite reduziert und der Zugriff auf gehostete Objekte so nah wie möglich für den Benutzer ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="44821-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="44821-122">Die CDN ruft Ihre Objekte von einem Speicherort ab, der als Ursprung _bezeichnet wird._</span><span class="sxs-lookup"><span data-stu-id="44821-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="44821-123">Ein Ursprung kann eine website SharePoint Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="44821-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="44821-124">Die Office 365 CDN ist in zwei grundlegende Typen getrennt:</span><span class="sxs-lookup"><span data-stu-id="44821-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="44821-125">**Public CDN** ist für JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) und nicht proprietäre Bilder wie Firmenlogos konzipiert.</span><span class="sxs-lookup"><span data-stu-id="44821-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="44821-126">**Private CDN** für Bilder (PNG, JPG, JPEG usw.) entwickelt.</span><span class="sxs-lookup"><span data-stu-id="44821-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="44821-127">Sie können sowohl öffentliche als auch private Ursprünge für Ihre Organisation auswählen.</span><span class="sxs-lookup"><span data-stu-id="44821-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="44821-128">Die meisten Organisationen entscheiden sich dafür, eine Kombination aus beiden zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="44821-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="44821-129">Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungsgewinne, aber jede bietet eindeutige Attribute und Vorteile.</span><span class="sxs-lookup"><span data-stu-id="44821-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="44821-130">Weitere Informationen zu öffentlichen und privaten CDN finden Sie unter [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="44821-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="44821-131">Aktivieren von öffentlichen und privaten CDN mit der Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="44821-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="44821-132">Bevor Sie Änderungen an den Mandanteneinstellungen CDN, sollten Sie überprüfen, ob sie den Compliance-, Sicherheits- und Datenschutzrichtlinien Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="44821-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="44821-133">Ausführlichere Konfigurationseinstellungen oder wenn Sie CDN bereits aktiviert haben und zusätzliche Speicherorte (Ursprünge) hinzufügen möchten, finden Sie im Abschnitt Einrichten und Konfigurieren der Office 365 CDN mithilfe der [SharePoint Online-Verwaltungsshell.](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="44821-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="44821-134">Verbinden sie mithilfe der SharePoint Online-Verwaltungsshell an Ihren Mandanten:</span><span class="sxs-lookup"><span data-stu-id="44821-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="44821-135">Geben Sie den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge mit der Standardkonfiguration verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="44821-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="44821-136">Die Ausgabe dieser Cmdlets sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="44821-136">Output of these cmdlets should look like the following:</span></span>

![Ausgabe von Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="44821-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44821-138">See also</span></span>

[<span data-ttu-id="44821-139">Verwenden des Tools "Seitendiagnose" für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44821-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="44821-140">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44821-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="44821-141">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="44821-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="44821-142">Netzwerkplanung und Leistungsoptimierung für Office 365</span><span class="sxs-lookup"><span data-stu-id="44821-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="44821-143">SharePoint Leistungsserie – Office 365 CDN Videoreihe</span><span class="sxs-lookup"><span data-stu-id="44821-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)