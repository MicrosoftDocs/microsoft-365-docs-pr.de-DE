---
title: Navigationsoptionen für SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: In diesem Artikel werden Navigations Options Websites mit aktivierter SharePoint-Veröffentlichung in SharePoint Online beschrieben.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695956"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="e5a28-103">Navigationsoptionen für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a28-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="e5a28-104">In diesem Artikel werden Navigations Options Websites mit aktivierter SharePoint-Veröffentlichung in SharePoint Online beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5a28-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="e5a28-105">Die Auswahl und Konfiguration der Navigation wirkt sich erheblich auf die Leistung und Skalierbarkeit von Websites in SharePoint Online aus.</span><span class="sxs-lookup"><span data-stu-id="e5a28-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="e5a28-106">Die Vorlage für die SharePoint-Veröffentlichungswebsite sollte nur bei Bedarf für ein zentralisiertes Portal verwendet werden, und das Veröffentlichungsfeature sollte nur auf bestimmten Websites aktiviert werden und nur, wenn es absolut erforderlich ist, da sich die Leistung bei falscher Verwendung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="e5a28-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="e5a28-107">Wenn Sie moderne SharePoint-Navigationsoptionen wie Mega-Menü, kaskadierende Navigation oder Hub-Navigation verwenden, gilt dieser Artikel nicht für Ihre Website.</span><span class="sxs-lookup"><span data-stu-id="e5a28-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="e5a28-108">Moderne SharePoint-Website Architekturen nutzen eine vereinfachte Websitehierarchie und ein Hub-and-Spoke-Modell.</span><span class="sxs-lookup"><span data-stu-id="e5a28-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="e5a28-109">Auf diese Weise können viele Szenarien erreicht werden, für die die Verwendung des SharePoint-Veröffentlichungsfeatures nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="e5a28-110">Übersicht über Navigationsoptionen</span><span class="sxs-lookup"><span data-stu-id="e5a28-110">Overview of navigation options</span></span>

<span data-ttu-id="e5a28-111">Die Konfiguration des Navigations Anbieters kann die Leistung für den gesamten Standort erheblich beeinträchtigen, und es ist sorgfältig darauf zu achten, dass Sie einen Navigationsanbieter und eine Konfiguration auswählen, die für die Anforderungen einer SharePoint-Website effektiv skaliert wird.</span><span class="sxs-lookup"><span data-stu-id="e5a28-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="e5a28-112">Es gibt zwei out-of-the-Box-Navigationsanbieter sowie benutzerdefinierte Navigations Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="e5a28-113">Die erste Option, die [**strukturelle Navigation**](#using-structural-navigation-in-sharepoint-online), ist die empfohlene Navigationsoption in SharePoint Online für klassische SharePoint-Websites, **Wenn Sie die Zwischenspeicherung der Struktur Navigation für Ihre Website aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e5a28-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="e5a28-114">Dieser Navigationsanbieter zeigt die Navigationselemente unter der aktuellen Website und optional die aktuelle Website und ihre Geschwister an.</span><span class="sxs-lookup"><span data-stu-id="e5a28-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="e5a28-115">Es bietet zusätzliche Funktionen wie Sicherheits Kürzung und Websitestruktur Aufzählung.</span><span class="sxs-lookup"><span data-stu-id="e5a28-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="e5a28-116">Wenn die Zwischenspeicherung deaktiviert ist, wirkt sich dies negativ auf die Leistung und Skalierbarkeit aus, und die Einschränkung ist möglicherweise eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="e5a28-117">Die zweite Option, [**verwaltete (Metadaten) Navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), stellt Navigationselemente mithilfe eines Ausdruckssatzes für verwaltete Metadaten dar.</span><span class="sxs-lookup"><span data-stu-id="e5a28-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="e5a28-118">Es wird empfohlen, die Sicherheits Kürzung nur dann zu deaktivieren, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="e5a28-119">Das Trimmen von Sicherheitsgründen ist als sichere Standardeinstellung für diesen Navigationsanbieter aktiviert. für viele Websites ist jedoch der Aufwand der Sicherheits Kürzung nicht erforderlich, da Navigationselemente häufig für alle Benutzer der Website konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="e5a28-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="e5a28-120">Mit der empfohlenen Konfiguration zum Deaktivieren der Einschränkung der Sicherheit erfordert dieser Navigationsanbieter keine Aufzählung der Websitestruktur und ist hochgradig skalierbar mit akzeptabler Leistungsbeeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="e5a28-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="e5a28-121">Neben den standardmäßigen Navigations Anbietern haben viele Kunden erfolgreich Alternative benutzerdefinierte Navigations Implementierungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="e5a28-122">Weitere Informationen finden Sie in diesem Artikel unter [Such gesteuerte clientseitige Skripts](#using-search-driven-client-side-scripting) .</span><span class="sxs-lookup"><span data-stu-id="e5a28-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="e5a28-123">Vorteile und Nachteile von SharePoint Online Navigationsoptionen</span><span class="sxs-lookup"><span data-stu-id="e5a28-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="e5a28-124">In der folgenden Tabelle sind die vor-und Nachteile der einzelnen Optionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e5a28-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="e5a28-125">Strukturelle Navigation</span><span class="sxs-lookup"><span data-stu-id="e5a28-125">Structural navigation</span></span>  |<span data-ttu-id="e5a28-126">Verwaltete Navigation</span><span class="sxs-lookup"><span data-stu-id="e5a28-126">Managed navigation</span></span>  |<span data-ttu-id="e5a28-127">Such gesteuerte Navigation</span><span class="sxs-lookup"><span data-stu-id="e5a28-127">Search-driven navigation</span></span>  |<span data-ttu-id="e5a28-128">Benutzerdefinierter Navigationsanbieter</span><span class="sxs-lookup"><span data-stu-id="e5a28-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e5a28-129">Experten</span><span class="sxs-lookup"><span data-stu-id="e5a28-129">Pros:</span></span><br/><br/><span data-ttu-id="e5a28-130">Einfache Wartung</span><span class="sxs-lookup"><span data-stu-id="e5a28-130">Easy to maintain</span></span><br/><span data-ttu-id="e5a28-131">Getrimmte Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e5a28-131">Security trimmed</span></span><br/><span data-ttu-id="e5a28-132">Wird automatisch innerhalb von 24 Stunden aktualisiert, wenn Inhalte geändert werden</span><span class="sxs-lookup"><span data-stu-id="e5a28-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="e5a28-133">Experten</span><span class="sxs-lookup"><span data-stu-id="e5a28-133">Pros:</span></span><br/><br/><span data-ttu-id="e5a28-134">Einfache Wartung</span><span class="sxs-lookup"><span data-stu-id="e5a28-134">Easy to maintain</span></span><br/>|<span data-ttu-id="e5a28-135">Experten</span><span class="sxs-lookup"><span data-stu-id="e5a28-135">Pros:</span></span><br/><br/><span data-ttu-id="e5a28-136">Getrimmte Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e5a28-136">Security trimmed</span></span><br/><span data-ttu-id="e5a28-137">Automatisch aktualisieren, wenn Websites hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="e5a28-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="e5a28-138">Schnelle Ladezeit und lokal zwischengespeicherte Navigationsstruktur</span><span class="sxs-lookup"><span data-stu-id="e5a28-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="e5a28-139">Experten</span><span class="sxs-lookup"><span data-stu-id="e5a28-139">Pros:</span></span><br/><br/><span data-ttu-id="e5a28-140">Breitere Auswahl von verfügbaren Optionen</span><span class="sxs-lookup"><span data-stu-id="e5a28-140">Wider choice of options available</span></span><br/><span data-ttu-id="e5a28-141">Schnelles Laden, wenn die Zwischenspeicherung ordnungsgemäß verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e5a28-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="e5a28-142">Viele Optionen funktionieren mit dem reaktionsschnellen Seitenentwurf gut</span><span class="sxs-lookup"><span data-stu-id="e5a28-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="e5a28-143">Nachteile</span><span class="sxs-lookup"><span data-stu-id="e5a28-143">Cons:</span></span><br/><br/><span data-ttu-id="e5a28-144">**Auswirkungen auf die Leistung, wenn die Zwischenspeicherung deaktiviert ist**</span><span class="sxs-lookup"><span data-stu-id="e5a28-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="e5a28-145">Einschränkungen unterliegen</span><span class="sxs-lookup"><span data-stu-id="e5a28-145">Subject to throttling</span></span><br/>|<span data-ttu-id="e5a28-146">Nachteile</span><span class="sxs-lookup"><span data-stu-id="e5a28-146">Cons:</span></span><br/><br/><span data-ttu-id="e5a28-147">Nicht automatisch aktualisiert, um die Websitestruktur widerzuspiegeln</span><span class="sxs-lookup"><span data-stu-id="e5a28-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="e5a28-148">**Auswirkungen auf die Leistung, wenn die Sicherheits Kürzung aktiviert ist** oder wenn die Navigationsstruktur Komplex ist</span><span class="sxs-lookup"><span data-stu-id="e5a28-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="e5a28-149">Nachteile</span><span class="sxs-lookup"><span data-stu-id="e5a28-149">Cons:</span></span><br/><br/><span data-ttu-id="e5a28-150">Keine Möglichkeit, Websites problemlos zu bestellen</span><span class="sxs-lookup"><span data-stu-id="e5a28-150">No ability to easily order sites</span></span><br/><span data-ttu-id="e5a28-151">Erfordert die Anpassung der Gestaltungsvorlage (erforderliche technische Kenntnisse)</span><span class="sxs-lookup"><span data-stu-id="e5a28-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="e5a28-152">Nachteile</span><span class="sxs-lookup"><span data-stu-id="e5a28-152">Cons:</span></span><br/><br/><span data-ttu-id="e5a28-153">Benutzerdefinierte Entwicklung ist erforderlich</span><span class="sxs-lookup"><span data-stu-id="e5a28-153">Custom development is required</span></span><br/><span data-ttu-id="e5a28-154">Externe Datenquelle/Cachespeicherung erforderlich, beispielsweise Azure</span><span class="sxs-lookup"><span data-stu-id="e5a28-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="e5a28-155">Die am besten geeignete Option für Ihre Website hängt von den Anforderungen Ihrer Website und ihrer technischen Leistungsfähigkeit ab.</span><span class="sxs-lookup"><span data-stu-id="e5a28-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="e5a28-156">Wenn Sie einen einfach zu konfigurierenden Navigationsanbieter wünschen, der automatisch aktualisiert wird, wenn Inhalt geändert wird, ist die strukturelle Navigation [mit aktivierter Zwischenspeicherung](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) eine gute Option.</span><span class="sxs-lookup"><span data-stu-id="e5a28-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="e5a28-157">Die Anwendung des gleichen Prinzips wie moderne SharePoint-Websites durch Vereinfachung der allgemeinen Websitestruktur in einer flacheren, nicht hierarchischen Struktur verbessert die Leistung und vereinfacht das Wechseln zu modernen SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="e5a28-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="e5a28-158">Dies bedeutet, dass statt einer einzelnen Websitesammlung mit Hunderten von Websites (Unterwebs) ein besserer Ansatz darin besteht, viele Websitesammlungen mit sehr wenigen Unterwebsites (Unterwebs) zu haben.</span><span class="sxs-lookup"><span data-stu-id="e5a28-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="e5a28-159">Analysieren der Navigationsleistung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a28-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="e5a28-160">Das [Seiten Diagnosetool für SharePoint](https://aka.ms/perftool) ist eine Browser Erweiterung für Microsoft Edge-und Chrome-Browser, die sowohl SharePoint Online moderne Portal-als auch klassische Veröffentlichungswebsite-Seiten analysiert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="e5a28-161">Dieses Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-System Seite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="e5a28-162">Das Tool generiert einen Bericht für jede analysierte Seite, die zeigt, wie die Seite mit einem vordefinierten Satz von Regeln ausgeführt wird, und zeigt ausführliche Informationen an, wenn Ergebnisse für einen Test außerhalb des Basiswerts liegen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="e5a28-163">SharePoint Online Administratoren und Designer können das Tool verwenden, um Leistungsprobleme zu beheben, um sicherzustellen, dass neue Seiten vor der Veröffentlichung optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="e5a28-164">**SPRequestDuration** ist insbesondere die Zeit, die SharePoint benötigt, um die Seite zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e5a28-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="e5a28-165">Die schwere Navigation (beispielsweise das Einschließen von Seiten in der Navigation), komplexe Websitehierarchien und andere Konfigurations-und Topologiefunktionen können einen erheblichen Beitrag zur längeren Dauer leisten.</span><span class="sxs-lookup"><span data-stu-id="e5a28-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="e5a28-166">Verwenden der Struktur Navigation in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a28-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="e5a28-167">Dies ist die standardmäßig verwendete Navigation, die die einfachste Lösung ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="e5a28-168">Es ist keine Anpassung erforderlich, und ein nicht technischer Benutzer kann auch auf einfache Weise Elemente hinzufügen, Elemente ausblenden und die Navigation auf der Seite "Einstellungen" verwalten.</span><span class="sxs-lookup"><span data-stu-id="e5a28-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="e5a28-169">Es wird empfohlen, die [Zwischenspeicherung zu aktivieren](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), da andernfalls ein teurer Leistungskompromiss vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="e5a28-170">Vorgehensweise implementieren der Zwischenspeicherung der Struktur Navigation</span><span class="sxs-lookup"><span data-stu-id="e5a28-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="e5a28-171">Unter **Websiteeinstellungen**  >  **sehen und fühlen**  >  **Navigation**können Sie überprüfen, ob die strukturelle Navigation für die globale Navigation oder aktuelle Navigation ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="e5a28-172">Das Auswählen von **Seiten anzeigen** wirkt sich negativ auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="e5a28-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Struktur Navigation mit ausgewählten Unterwebsites anzeigen](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="e5a28-174">Die Zwischenspeicherung kann auf Websitesammlungsebene und auf Websiteebene aktiviert oder deaktiviert werden und ist standardmäßig für beide aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="e5a28-175">Aktivieren **Site Settings**  >  **Site Collection Administration**  >  Sie das Kontrollkästchen zum **Aktivieren der Zwischenspeicherung**auf Websitesammlungsebene Unterwebsite Sammlungsverwaltung Website Sammlungs**Navigation**.</span><span class="sxs-lookup"><span data-stu-id="e5a28-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Aktivieren der Zwischenspeicherung auf Websiteebene](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="e5a28-177">Aktivieren **Site Settings**  >  Sie das Kontrollkästchen **Zwischenspeicherung aktivieren**, um auf Websiteebene Unterwebsite Einstellungen zu**Navigieren**.</span><span class="sxs-lookup"><span data-stu-id="e5a28-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Aktivieren der Zwischenspeicherung auf Websiteebene](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="e5a28-179">Verwenden der verwalteten Navigation und der Metadaten in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a28-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="e5a28-180">Die verwaltete Navigation ist eine weitere out-of-the-Box-Option, die Sie verwenden können, um die meisten der gleichen Funktionen wie die strukturelle Navigation neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="e5a28-181">Verwaltete Metadaten können so konfiguriert werden, dass die Sicherheits Kürzung aktiviert oder deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e5a28-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="e5a28-182">Bei deaktivierter Sicherheits Kürzung ist die verwaltete Navigation relativ effizient, da alle Navigationslinks mit einer Konstanten Anzahl von Server aufrufen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="e5a28-183">Durch das Aktivieren der Sicherheits Kürzung werden jedoch einige der Leistungsvorteile der verwalteten Navigation negiert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="e5a28-184">Wenn Sie das Kürzen von Sicherheitsgründen aktivieren müssen, empfehlen wir Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e5a28-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="e5a28-185">Aktualisieren aller benutzerfreundlichen URL-Links auf einfache Links</span><span class="sxs-lookup"><span data-stu-id="e5a28-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="e5a28-186">Hinzufügen erforderlicher Sicherheits Kürzungs Knoten als benutzerfreundliche URLs</span><span class="sxs-lookup"><span data-stu-id="e5a28-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="e5a28-187">Beschränken Sie die Anzahl der Navigationselemente auf nicht mehr als 100 und nicht mehr als 3 Ebenen tief</span><span class="sxs-lookup"><span data-stu-id="e5a28-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="e5a28-188">Für viele Websites ist keine Sicherheits Kürzung erforderlich, da die Navigationsstruktur häufig für alle Benutzer der Website konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="e5a28-189">Wenn die Sicherheits Kürzung deaktiviert ist und der Navigation ein Link hinzugefügt wird, auf den nicht alle Benutzer Zugriff haben, wird der Link weiterhin angezeigt, führt jedoch zu einer Meldung mit Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="e5a28-190">Es besteht keine Gefahr eines versehentlichen Zugriffs auf den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="e5a28-191">Implementieren der verwalteten Navigation und der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e5a28-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="e5a28-192">In docs.Microsoft.com finden Sie verschiedene Artikel zu den Details der verwalteten Navigation.</span><span class="sxs-lookup"><span data-stu-id="e5a28-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="e5a28-193">Beispiel: siehe [Übersicht über die verwaltete Navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span><span class="sxs-lookup"><span data-stu-id="e5a28-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="e5a28-194">Um die verwaltete Navigation zu implementieren, richten Sie Begriffe mit URLs ein, die der Navigationsstruktur der Website entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="e5a28-195">Die verwaltete Navigation kann sogar manuell kuratiert werden, um die Struktur Navigation in vielen Fällen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="e5a28-196">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5a28-196">For example:</span></span>

![SharePoint Online Websitestruktur](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="e5a28-198">)</span><span class="sxs-lookup"><span data-stu-id="e5a28-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="e5a28-199">Verwenden von Such gesteuerten clientseitigen Skripts</span><span class="sxs-lookup"><span data-stu-id="e5a28-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="e5a28-200">Eine allgemeine Klasse von Implementierungen für benutzerdefinierte Navigation umfasst Client gerenderte Entwurfsmuster, die einen lokalen Cache von Navigationsknoten speichern.</span><span class="sxs-lookup"><span data-stu-id="e5a28-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="e5a28-201">Diese Navigationsanbieter haben einige wichtige Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e5a28-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="e5a28-202">Sie funktionieren im Allgemeinen gut mit reaktionsschnellen Seitendesigns.</span><span class="sxs-lookup"><span data-stu-id="e5a28-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="e5a28-203">Sie sind extrem skalierbar und leistungsfähig, da Sie ohne Ressourcenkosten Rendern können (und nach einem Timeout im Hintergrund aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="e5a28-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="e5a28-204">Diese Navigationsanbieter können Navigationsdaten mithilfe verschiedener Strategien abrufen, von einfachen statischen Konfigurationen bis hin zu verschiedenen dynamischen Datenanbietern.</span><span class="sxs-lookup"><span data-stu-id="e5a28-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="e5a28-205">Ein Beispiel für einen Datenanbieter ist die Verwendung einer **Such gesteuerten Navigation**, die Flexibilität beim Aufzählen von Navigationsknoten und der effizienten Handhabung von Sicherheits Trimmungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e5a28-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="e5a28-206">Es gibt andere beliebte Optionen zum Erstellen **benutzerdefinierter Navigationsanbieter**.</span><span class="sxs-lookup"><span data-stu-id="e5a28-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="e5a28-207">Weitere Anleitungen zum Erstellen eines benutzerdefinierten Navigations Anbieters finden Sie unter [Navigationslösungen für SharePoint Online-Portale](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) .</span><span class="sxs-lookup"><span data-stu-id="e5a28-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="e5a28-208">Mithilfe der Suche können Sie die Indizes nutzen, die im Hintergrund mithilfe der kontinuierlichen Durchforstung aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="e5a28-209">Die Suchergebnisse werden aus dem Suchindex abgerufen, und die Ergebnisse werden Sicherheits getrimmt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="e5a28-210">Dies ist im Allgemeinen schneller als bei der vordefinierten Navigation, wenn Sicherheits Kürzung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="e5a28-211">Die Verwendung der Suche für die strukturelle Navigation, insbesondere wenn Sie über eine komplexe Websitestruktur verfügen, beschleunigt die Ladezeit der Seite erheblich.</span><span class="sxs-lookup"><span data-stu-id="e5a28-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="e5a28-212">Der Hauptvorteil dieser über die verwaltete Navigation ist, dass Sie von Sicherheit Trimmen profitieren.</span><span class="sxs-lookup"><span data-stu-id="e5a28-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="e5a28-213">Dieser Ansatz umfasst das Erstellen einer benutzerdefinierten Gestaltungsvorlage und das Ersetzen des vordefinierten Navigations Codes durch benutzerdefinierten HTML-Code.</span><span class="sxs-lookup"><span data-stu-id="e5a28-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="e5a28-214">Gehen Sie wie im folgenden Beispiel beschrieben vor, um den Navigationscode in der Datei zu ersetzen `seattle.html` .</span><span class="sxs-lookup"><span data-stu-id="e5a28-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="e5a28-215">In diesem Beispiel werden Sie die Datei öffnen `seattle.html` und das gesamte `id="DeltaTopNavigation"` -Element durch benutzerdefinierten HTML-Code ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="e5a28-216">Beispiel: Ersetzen des Standard Navigations Codes in einer Gestaltungsvorlage</span><span class="sxs-lookup"><span data-stu-id="e5a28-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="e5a28-217">Navigieren Sie zur Seite Websiteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="e5a28-218">Öffnen Sie den gestaltungsvorlagenkatalog, indem Sie auf **Masterseiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="e5a28-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="e5a28-219">Von hier aus können Sie durch die Bibliothek navigieren und die Datei herunterladen `seattle.master` .</span><span class="sxs-lookup"><span data-stu-id="e5a28-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="e5a28-220">Bearbeiten Sie den Code mit einem Text-Editor, und löschen Sie den Codeblock im folgenden Screenshot.</span><span class="sxs-lookup"><span data-stu-id="e5a28-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Löschen des angezeigten Codeblocks](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="e5a28-222">Entfernen Sie den Code zwischen den `<SharePoint:AjaxDelta id="DeltaTopNavigation">` und- `<\SharePoint:AjaxDelta>` Tags, und ersetzen Sie ihn durch den folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="e5a28-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="e5a28-223">Ersetzen Sie die URL im Tag Loading Image Anchor am Anfang durch einen Link zu einem Bild laden in Ihrer Websitesammlung.</span><span class="sxs-lookup"><span data-stu-id="e5a28-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="e5a28-224">Nachdem Sie die Änderungen vorgenommen haben, benennen Sie die Datei um, und laden Sie Sie dann in den gestaltungsvorlagenkatalog hoch.</span><span class="sxs-lookup"><span data-stu-id="e5a28-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="e5a28-225">Dadurch wird eine neue Masterdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="e5a28-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="e5a28-226">Dieser HTML-Code ist das grundlegende Markup, das von den Suchergebnissen aufgefüllt wird, die von JavaScript-Code zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="e5a28-227">Sie müssen den Code so bearbeiten, dass der Wert für var root = "Website Sammlungs-URL" geändert wird, wie im folgenden Codeausschnitt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e5a28-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="e5a28-228">Die Ergebnisse werden dem Self. Nodes-Array zugewiesen, und eine Hierarchie wird aus den Objekten mit linq.js zuweisen der Ausgabe zu einem Array Self. Hierarchy erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="e5a28-229">Dieses Array ist das Objekt, das an den HTML-Code gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="e5a28-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="e5a28-230">Dies erfolgt in der toggleView ()-Funktion, indem das Self-Objekt an die ko. applyBinding ()-Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5a28-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="e5a28-231">Dadurch wird das Hierarchie Array an den folgenden HTML-Code gebunden:</span><span class="sxs-lookup"><span data-stu-id="e5a28-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="e5a28-232">Die Ereignishandler für `mouseenter` und `mouseexit` werden zur Navigation auf oberster Ebene hinzugefügt, um die Unterwebsite-Dropdownmenüs zu verarbeiten, die in der-Funktion ausgeführt werden `addEventsToElements()` .</span><span class="sxs-lookup"><span data-stu-id="e5a28-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="e5a28-233">In unserem komplexen Navigations Beispiel zeigt eine neue Seitenauslastung ohne lokale Zwischenspeicherung, dass die Zeit, die auf dem Server aufgewendet wurde, aus der Benchmark-Struktur Navigation reduziert wurde, um ein ähnliches Ergebnis wie beim verwalteten Navigations Ansatz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e5a28-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="e5a28-234">Informationen zur JavaScript-Datei...</span><span class="sxs-lookup"><span data-stu-id="e5a28-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="e5a28-235">Wenn Sie benutzerdefiniertes JavaScript verwenden, stellen Sie sicher, dass das öffentliche CDN aktiviert ist und sich die Datei an einem CDN-Speicherort befindet.</span><span class="sxs-lookup"><span data-stu-id="e5a28-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="e5a28-236">Die gesamte JavaScript-Datei lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e5a28-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="e5a28-237">Um den oben gezeigten Code in der Funktion zusammenzufassen, `jQuery $(document).ready` gibt es eine `viewModel object` erstellte und dann die- `loadNavigationNodes()` Funktion für dieses Objekt wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="e5a28-238">Diese Funktion lädt entweder die zuvor erstellte Navigationshierarchie, die im lokalen HTML5-Speicher des Clientbrowsers gespeichert ist, oder Sie ruft die Funktion auf `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="e5a28-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="e5a28-239">`QueryRemoteInterface()` erstellt eine Anforderung mithilfe der `getRequest()` Funktion mit dem zuvor im Skript definierten Abfrageparameter und gibt dann Daten vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="e5a28-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="e5a28-240">Diese Daten sind im Wesentlichen ein Array aller Websites in der Websitesammlung, die als Daten Übertragungsobjekte mit verschiedenen Eigenschaften dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="e5a28-241">Diese Daten werden dann in die zuvor definierten Objekte analysiert, `SPO.Models.NavigationNode` die `Knockout.js` zum Erstellen beobachtbarer Eigenschaften für die Verwendung durch Datenbindung der Werte in den HTML-Code verwenden, den wir zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="e5a28-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="e5a28-242">Die Objekte werden dann in ein Ergebnisarray eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-242">The objects are then put into a results array.</span></span> <span data-ttu-id="e5a28-243">Dieses Array wird mithilfe von Knockout in JSON analysiert und im lokalen Browser Speicher gespeichert, um die Leistung bei zukünftigen Seitenlasten zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e5a28-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="e5a28-244">Vorteile dieses Ansatzes</span><span class="sxs-lookup"><span data-stu-id="e5a28-244">Benefits of this approach</span></span>

<span data-ttu-id="e5a28-245">Ein wesentlicher Vorteil [dieses Ansatzes](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) ist, dass die Navigation bei Verwendung des lokalen HTML5-Speichers lokal für den Benutzer gespeichert wird, wenn Sie das nächste Mal die Seite laden.</span><span class="sxs-lookup"><span data-stu-id="e5a28-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="e5a28-246">Bei der Verwendung der Such-API für die strukturelle Navigation erhalten wir deutliche Leistungsverbesserungen. Es erfordert jedoch einige technische Funktionen zum Ausführen und Anpassen dieser Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="e5a28-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="e5a28-247">In der [Beispielimplementierung](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)werden die Websites auf die gleiche Weise wie die standardmäßige Struktur Navigation sortiert. alphabetische Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e5a28-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="e5a28-248">Wenn Sie von dieser Reihenfolge abweichen möchten, wäre es komplizierter zu entwickeln und zu warten.</span><span class="sxs-lookup"><span data-stu-id="e5a28-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="e5a28-249">Bei dieser Vorgehensweise müssen Sie auch von den unterstützten Masterseiten abweichen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="e5a28-250">Wenn die benutzerdefinierte Gestaltungsvorlage nicht beibehalten wird, verpasst ihre Website Updates und Verbesserungen, die Microsoft an den Gestaltungsvorlagen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="e5a28-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="e5a28-251">Der [obige Code](#about-the-javascript-file) hat die folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="e5a28-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="e5a28-252">jQuery https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="e5a28-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="e5a28-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="e5a28-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="e5a28-254">Linq.js- https://linqjs.codeplex.com/ oder GitHub.com/neuecc/-linq.js</span><span class="sxs-lookup"><span data-stu-id="e5a28-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="e5a28-255">Die aktuelle Version von LinqJS enthält nicht die ByHierarchy-Methode, die im obigen Code verwendet wird, und der Navigationscode wird unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="e5a28-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="e5a28-256">Um dies zu beheben, fügen Sie die folgende Methode zur Linq.js Datei vor der-Verbindung hinzu `Flatten: function ()` .</span><span class="sxs-lookup"><span data-stu-id="e5a28-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="e5a28-257">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e5a28-257">Related topics</span></span>

[<span data-ttu-id="e5a28-258">Übersicht über die verwaltete Navigation in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="e5a28-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="e5a28-259">Zwischenspeicherung und Leistung der Struktur Navigation</span><span class="sxs-lookup"><span data-stu-id="e5a28-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
