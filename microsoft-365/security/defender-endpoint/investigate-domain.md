---
title: Untersuchen von Microsoft Defender for Endpoint-Domänen
description: Verwenden Sie die Untersuchungsoptionen, um zu sehen, ob Geräte und Server mit bösartigen Domänen kommuniziert haben.
keywords: Untersuchen von Domäne, Domäne, bösartiger Domäne, Microsoft Defender for Endpoint, Warnung, URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933469"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="51afb-104">Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="51afb-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="51afb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51afb-105">**Applies to:**</span></span>
- [<span data-ttu-id="51afb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51afb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51afb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51afb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51afb-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="51afb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51afb-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="51afb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="51afb-110">Untersuchen Sie eine Domäne, um zu ermitteln, ob Geräte und Server in Ihrem Unternehmensnetzwerk mit einer bekannten bösartigen Domäne kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="51afb-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="51afb-111">Sie können eine Domäne untersuchen, indem Sie das Suchfeature verwenden oder über die Gerätezeitachse auf einen Domänenlink **klicken.**</span><span class="sxs-lookup"><span data-stu-id="51afb-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="51afb-112">Informationen aus den folgenden Abschnitten finden Sie in der URL-Ansicht:</span><span class="sxs-lookup"><span data-stu-id="51afb-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="51afb-113">URL-Details, Kontakte, Nameserver</span><span class="sxs-lookup"><span data-stu-id="51afb-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="51afb-114">Warnungen im Zusammenhang mit dieser URL</span><span class="sxs-lookup"><span data-stu-id="51afb-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="51afb-115">URL in der Organisation</span><span class="sxs-lookup"><span data-stu-id="51afb-115">URL in organization</span></span>
- <span data-ttu-id="51afb-116">Zuletzt beobachtete Geräte mit URL</span><span class="sxs-lookup"><span data-stu-id="51afb-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="51afb-117">URL weltweit</span><span class="sxs-lookup"><span data-stu-id="51afb-117">URL worldwide</span></span>

<span data-ttu-id="51afb-118">Der **Abschnitt URL Worldwide** enthält die URL, einen Link zu weiteren Details unter Whois, die Anzahl der damit verbundenen offenen Vorfälle und die Anzahl der aktiven Warnungen.</span><span class="sxs-lookup"><span data-stu-id="51afb-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="51afb-119">Vorfall</span><span class="sxs-lookup"><span data-stu-id="51afb-119">Incident</span></span>

<span data-ttu-id="51afb-120">Die **Karte Vorfall** zeigt ein Balkendiagramm aller aktiven Warnungen bei Vorfällen in den letzten 180 Tagen an.</span><span class="sxs-lookup"><span data-stu-id="51afb-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="51afb-121">Prävalenz</span><span class="sxs-lookup"><span data-stu-id="51afb-121">Prevalence</span></span>

<span data-ttu-id="51afb-122">Die **Prävalenzkarte** enthält Details zur Verbreitung der URL innerhalb der Organisation über einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="51afb-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="51afb-123">Obwohl der Standardzeitraum die letzten 30 Tage ist, können Sie den Bereich anpassen, indem Sie den nach unten zeigenden Pfeil in der Ecke der Karte auswählen.</span><span class="sxs-lookup"><span data-stu-id="51afb-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="51afb-124">Der kürzeste verfügbare Bereich ist für die Verbreitung über den letzten Tag, während der längste Bereich über die letzten 6 Monate liegt.</span><span class="sxs-lookup"><span data-stu-id="51afb-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="51afb-125">Warnungen</span><span class="sxs-lookup"><span data-stu-id="51afb-125">Alerts</span></span>

<span data-ttu-id="51afb-126">Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die der URL zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="51afb-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="51afb-127">Die hier gezeigte Tabelle ist eine gefilterte Version der Warnungen, die auf dem Warteschleifenbildschirm angezeigt wird und nur Warnungen enthält, die der Domäne zugeordnet sind, ihren Schweregrad, status, den zugeordneten Vorfall, die Klassifizierung, den Untersuchungsstatus und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="51afb-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="51afb-128">Die Registerkarte Warnungen kann angepasst werden, um  mehr oder weniger Informationen anzuzeigen, indem Sie im Aktionsmenü oberhalb der Spaltenüberschriften Spalten anpassen auswählen.</span><span class="sxs-lookup"><span data-stu-id="51afb-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="51afb-129">Die Anzahl der angezeigten Elemente kann auch angepasst werden, indem Elemente pro **Seite im** gleichen Menü ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="51afb-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="51afb-130">Beobachtet in der Organisation</span><span class="sxs-lookup"><span data-stu-id="51afb-130">Observed in organization</span></span>

<span data-ttu-id="51afb-131">Die **Registerkarte Beobachtet in der** Organisation bietet eine chronologische Ansicht der Ereignisse und zugeordneten Warnungen, die in der URL beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="51afb-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="51afb-132">Diese Registerkarte enthält eine Zeitachse und eine anpassbare Tabelle, in der Ereignisdetails wie Uhrzeit, Gerät und eine kurze Beschreibung der Ereignisse aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="51afb-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="51afb-133">Sie können Ereignisse aus unterschiedlichen Zeiträumen anzeigen, indem Sie die Datumsangaben in die Textfelder oberhalb der Tabellenkopfzeilen eingeben.</span><span class="sxs-lookup"><span data-stu-id="51afb-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="51afb-134">Sie können den Zeitraum auch anpassen, indem Sie unterschiedliche Bereiche der Zeitachse auswählen.</span><span class="sxs-lookup"><span data-stu-id="51afb-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="51afb-135">**Untersuchen einer Domäne:**</span><span class="sxs-lookup"><span data-stu-id="51afb-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="51afb-136">Wählen **Sie url** im **Dropdownmenü Suchleiste** aus.</span><span class="sxs-lookup"><span data-stu-id="51afb-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="51afb-137">Geben Sie die URL in das Feld **Suche** ein.</span><span class="sxs-lookup"><span data-stu-id="51afb-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="51afb-138">Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="51afb-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="51afb-139">Details zur URL werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51afb-139">Details about the URL are displayed.</span></span> <span data-ttu-id="51afb-140">Hinweis: Suchergebnisse werden nur für URLs zurückgegeben, die in der Kommunikation von Geräten in der Organisation beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="51afb-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="51afb-141">Verwenden Sie die Suchfilter, um die Suchkriterien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="51afb-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="51afb-142">Sie können auch das Zeitachsensuchfeld verwenden, um die angezeigten Ergebnisse aller Geräte in der Organisation zu filtern, die bei der Kommunikation mit der URL, der der Kommunikation zugeordneten Datei und dem letzten beobachteten Datum beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="51afb-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="51afb-143">Wenn Sie auf einen der Gerätenamen klicken, werden Sie zur Ansicht dieses Geräts angezeigt, in der Sie gemeldete Warnungen, Verhaltensweisen und Ereignisse weiterhin untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="51afb-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51afb-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="51afb-144">Related topics</span></span>
- [<span data-ttu-id="51afb-145">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="51afb-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="51afb-146">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="51afb-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="51afb-147">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="51afb-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="51afb-148">Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="51afb-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="51afb-149">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="51afb-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="51afb-150">Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="51afb-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="51afb-151">Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51afb-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
