---
title: Untersuchen einer einer Warnung zugeordneten IP-Adresse
description: Verwenden Sie die Untersuchungsoptionen, um die mögliche Kommunikation zwischen Geräten und externen IP-Adressen zu untersuchen.
keywords: Untersuchen, Untersuchen, IP-Adresse, Warnung, Microsoft Defender for Endpoint, externe IP
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933829"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="8e940-104">Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="8e940-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8e940-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8e940-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e940-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8e940-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e940-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e940-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8e940-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8e940-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e940-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8e940-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8e940-110">Untersuchen Sie die mögliche Kommunikation zwischen Ihren Geräten und externen Ip-Adressen (Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="8e940-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="8e940-111">Das Identifizieren aller Geräte in der Organisation, die mit einer verdächtigen oder bekannten schädlichen #A0 kommuniziert haben, z. B. Command and Control (C2)-Server, trägt dazu bei, den potenziellen Umfang von Sicherheitsverletzungen, zugeordneten Dateien und infizierten Geräten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8e940-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="8e940-112">Informationen finden Sie in den folgenden Abschnitten in der IP-Adressansicht:</span><span class="sxs-lookup"><span data-stu-id="8e940-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="8e940-113">IP weltweit</span><span class="sxs-lookup"><span data-stu-id="8e940-113">IP worldwide</span></span>
- <span data-ttu-id="8e940-114">Reverse-DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="8e940-114">Reverse DNS names</span></span>
- <span data-ttu-id="8e940-115">Warnungen im Zusammenhang mit dieser IP</span><span class="sxs-lookup"><span data-stu-id="8e940-115">Alerts related to this IP</span></span>
- <span data-ttu-id="8e940-116">IP in der Organisation</span><span class="sxs-lookup"><span data-stu-id="8e940-116">IP in organization</span></span>
- <span data-ttu-id="8e940-117">Prävalenz</span><span class="sxs-lookup"><span data-stu-id="8e940-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="8e940-118">IP Weltweit und Reverse-DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="8e940-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="8e940-119">Der Abschnitt "IP-Adressdetails" zeigt Attribute der IP-Adresse, z. B. den ASN und die Reverse-DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="8e940-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="8e940-120">Warnungen im Zusammenhang mit dieser IP</span><span class="sxs-lookup"><span data-stu-id="8e940-120">Alerts related to this IP</span></span>

<span data-ttu-id="8e940-121">Der **Abschnitt Warnungen im Zusammenhang** mit diesem IP enthält eine Liste der Warnungen, die der IP zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8e940-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="8e940-122">IP in der Organisation</span><span class="sxs-lookup"><span data-stu-id="8e940-122">IP in organization</span></span>

<span data-ttu-id="8e940-123">Der **Abschnitt IP in Organization** enthält Details zur Verbreitung der IP-Adresse in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="8e940-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="8e940-124">Prävalenz</span><span class="sxs-lookup"><span data-stu-id="8e940-124">Prevalence</span></span>

<span data-ttu-id="8e940-125">Im **Abschnitt Verbreitung** wird angezeigt, wie viele Geräte mit dieser IP-Adresse verbunden sind und wann die IP zuerst und zuletzt gesehen wurde.</span><span class="sxs-lookup"><span data-stu-id="8e940-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="8e940-126">Sie können die Ergebnisse dieses Abschnitts nach Zeitraum filtern. Der Standardzeitraum beträgt 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="8e940-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="8e940-127">Zuletzt beobachtete Geräte mit IP</span><span class="sxs-lookup"><span data-stu-id="8e940-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="8e940-128">Der **Abschnitt Zuletzt beobachtete** Geräte mit IP bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die an der IP-Adresse beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="8e940-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="8e940-129">**Untersuchen einer externen IP:**</span><span class="sxs-lookup"><span data-stu-id="8e940-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="8e940-130">Wählen **Sie im** Dropdownmenü **Suchleiste** IP aus.</span><span class="sxs-lookup"><span data-stu-id="8e940-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="8e940-131">Geben Sie die IP-Adresse in das Feld **Suche** ein.</span><span class="sxs-lookup"><span data-stu-id="8e940-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="8e940-132">Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="8e940-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="8e940-133">Details zur IP-Adresse werden angezeigt, darunter: Registrierungsdetails (sofern verfügbar), Reverse-IPs (z. B. Domänen), Verbreitung von Geräten in der Organisation, die mit dieser IP-Adresse kommuniziert haben (während eines auswählbaren Zeitraums) und die Geräte in der Organisation, die beobachtet wurden, wie sie mit dieser IP-Adresse kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8e940-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="8e940-134">Suchergebnisse werden nur für IP-Adressen zurückgegeben, die in der Kommunikation mit Geräten in der Organisation beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8e940-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="8e940-135">Verwenden Sie die Suchfilter, um die Suchkriterien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8e940-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="8e940-136">Sie können auch das Zeitachsensuchfeld verwenden, um die angezeigten Ergebnisse aller Geräte in der Organisation zu filtern, die die Kommunikation mit der IP-Adresse, der der Kommunikation zugeordneten Datei und dem letzten beobachteten Datum beobachtet haben.</span><span class="sxs-lookup"><span data-stu-id="8e940-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="8e940-137">Wenn Sie auf einen der Gerätenamen klicken, werden Sie zur Ansicht dieses Geräts angezeigt, in der Sie gemeldete Warnungen, Verhaltensweisen und Ereignisse weiterhin untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="8e940-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e940-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8e940-138">Related topics</span></span>

- [<span data-ttu-id="8e940-139">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="8e940-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8e940-140">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="8e940-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8e940-141">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="8e940-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8e940-142">Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8e940-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8e940-143">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="8e940-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8e940-144">Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8e940-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="8e940-145">Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e940-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
