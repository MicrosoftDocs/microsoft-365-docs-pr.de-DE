---
title: Softwareinventar in der Bedrohungs- und Sicherheitsrisikoverwaltung
description: Die Seite "Softwareinventar" für die Bedrohungs- und Sicherheitsrisikoverwaltung von Microsoft Defender for Endpoint zeigt, wie viele Schwachstellen und Sicherheitsrisiken in Der Software erkannt wurden.
keywords: Bedrohungs- und Sicherheitsrisikoverwaltung, Microsoft Defender for Endpoint, Microsoft Defender for Endpoint Software inventory, Microsoft Defender for Endpoint Threat & Vulnerability Management, Microsoft Defender for Endpoint Threat & Vulnerability Management Software Inventory, Microsoft Defender for Endpoint tvm software inventory, tvm software inventory
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0d270760cfed965c8190668afcdb1cc25223d2b1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933721"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="56906-104">Softwareinventar – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="56906-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56906-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="56906-105">**Applies to:**</span></span>
- [<span data-ttu-id="56906-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="56906-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="56906-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="56906-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="56906-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56906-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="56906-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="56906-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="56906-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="56906-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="56906-111">Das Softwareinventar im Bedrohungs- und Sicherheitsrisikomanagement ist eine Liste bekannter Software in Ihrer Organisation mit offiziellen [Common Platform Enumerations (CPE).](https://nvd.nist.gov/products/cpe)</span><span class="sxs-lookup"><span data-stu-id="56906-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="56906-112">Softwareprodukte ohne offizielle CPE haben keine Sicherheitsrisiken veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="56906-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="56906-113">Sie enthält auch Details wie den Namen des Anbieters, die Anzahl der Schwächen, Bedrohungen und die Anzahl der verfügbar gemachten Geräte.</span><span class="sxs-lookup"><span data-stu-id="56906-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="56906-114">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="56906-114">How it works</span></span>

<span data-ttu-id="56906-115">Im Bereich der Ermittlung nutzen wir den gleichen Satz von Signalen, der für die Erkennung und Bewertung von Sicherheitslücken in Microsoft Defender for Endpoint Erkennungs- und Reaktionsfunktionen [verantwortlich ist.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="56906-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="56906-116">Da es in Echtzeit ist, werden in wenigen Minuten Informationen zu Sicherheitslücken erkannt.</span><span class="sxs-lookup"><span data-stu-id="56906-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="56906-117">Das Modul greift automatisch Informationen aus mehreren Sicherheitsfeeds auf.</span><span class="sxs-lookup"><span data-stu-id="56906-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="56906-118">Tatsächlich sehen Sie, ob eine bestimmte Software mit einer Livebedrohungskampagne verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="56906-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="56906-119">Sie stellt außerdem einen Link zu einem Threat Analytics-Bericht bereit, sobald er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="56906-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="56906-120">Navigieren zur Seite Softwareinventar</span><span class="sxs-lookup"><span data-stu-id="56906-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="56906-121">Greifen Sie auf die Seite Softwarebestand zu, indem Sie **im** Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung im [Microsoft Defender Security Center softwareinventar auswählen.](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="56906-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="56906-122">Anzeigen von Software auf bestimmten Geräten auf den einzelnen Geräteseiten in der [Geräteliste](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56906-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="56906-123">Wenn Sie mithilfe der globalen Microsoft Defender for Endpoint-Suche nach Software suchen, stellen Sie sicher, dass Sie einen Unterstrich anstelle eines Leerzeichens setzen.</span><span class="sxs-lookup"><span data-stu-id="56906-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="56906-124">Für die besten Suchergebnisse würden Sie z. B. "windows_10" anstelle von "Windows 10" schreiben.</span><span class="sxs-lookup"><span data-stu-id="56906-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="56906-125">Übersicht über das Softwareinventar</span><span class="sxs-lookup"><span data-stu-id="56906-125">Software inventory overview</span></span>

<span data-ttu-id="56906-126">Die **Seite Softwareinventar** wird mit einer Liste der in Ihrem Netzwerk installierten Software geöffnet, einschließlich des Herstellernamens, gefundener Schwachstellen, damit verbundener Bedrohungen, verfügbar gemachter Geräte, Auswirkungen auf die Belichtungsbewertung und Tags.</span><span class="sxs-lookup"><span data-stu-id="56906-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="56906-127">Sie können die Listenansicht basierend auf Denkschwächen in der Software, den damit verbundenen Bedrohungen und Tags filtern, z. B. ob die Software das Ende des Support erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="56906-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Beispiel für die Angebotsseite für softwareinventar.](images/tvm-software-inventory.png)

<span data-ttu-id="56906-129">Wählen Sie die Software aus, die Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="56906-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="56906-130">Ein Flyoutpanel wird mit einer kompakteren Ansicht der Informationen auf der Seite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="56906-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="56906-131">Sie können entweder tiefer in die Untersuchung eintauchen und Softwareseite öffnen auswählen **oder** technische Inkonsistenzen kennzeichnen, indem Sie Ungenauigkeit melden **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="56906-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="56906-132">Software, die nicht unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="56906-132">Software that isn't supported</span></span>

<span data-ttu-id="56906-133">Software, die derzeit nicht von der Bedrohungsverwaltung & unterstützt wird, kann auf der Seite Softwareinventar vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="56906-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="56906-134">Da sie nicht unterstützt wird, sind nur begrenzte Daten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="56906-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="56906-135">Filtern Sie nach nicht unterstützter Software mit der Option "Nicht verfügbar" im Abschnitt "Schwachstelle".</span><span class="sxs-lookup"><span data-stu-id="56906-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Nicht unterstützter Softwarefilter.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="56906-137">Im Folgenden wird angegeben, dass eine Software nicht unterstützt wird:</span><span class="sxs-lookup"><span data-stu-id="56906-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="56906-138">Das Feld "Schwächen" zeigt "Nicht verfügbar" an.</span><span class="sxs-lookup"><span data-stu-id="56906-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="56906-139">Feld "Verfügbar gemachte Geräte" zeigt einen Strich an</span><span class="sxs-lookup"><span data-stu-id="56906-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="56906-140">Im Seitenbereich und auf der Softwareseite hinzugefügter Informationstext</span><span class="sxs-lookup"><span data-stu-id="56906-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="56906-141">Die Softwareseite enthält keine Sicherheitsempfehlungen, entdeckten Sicherheitsrisiken oder Abschnitte der Ereigniszeitachse.</span><span class="sxs-lookup"><span data-stu-id="56906-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="56906-142">Derzeit werden Produkte ohne CPE nicht auf der Seite Softwareinventar angezeigt, sondern nur im Softwareinventar auf Geräteebene.</span><span class="sxs-lookup"><span data-stu-id="56906-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="56906-143">Softwareinventar auf Geräten</span><span class="sxs-lookup"><span data-stu-id="56906-143">Software inventory on devices</span></span>

<span data-ttu-id="56906-144">Wechseln Sie im Microsoft Defender Security Center-Navigationsbereich zur **[Liste Geräte](machines-view-overview.md)**.</span><span class="sxs-lookup"><span data-stu-id="56906-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="56906-145">Wählen Sie den Namen eines Geräts aus, um die Geräteseite zu öffnen (z. B. Computer1), und wählen Sie dann die Registerkarte **Softwarebestand** aus, um eine Liste aller auf dem Gerät vorhandenen bekannten Software zu sehen.</span><span class="sxs-lookup"><span data-stu-id="56906-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="56906-146">Wählen Sie einen bestimmten Softwareeintrag aus, um das Flyout mit weiteren Informationen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="56906-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="56906-147">Software kann auf Geräteebene sichtbar sein, auch wenn sie derzeit nicht von der Bedrohungs- und Sicherheitsrisikoverwaltung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="56906-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="56906-148">Es sind jedoch nur begrenzte Daten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="56906-148">However, only limited data will be available.</span></span> <span data-ttu-id="56906-149">Sie wissen, ob Software nicht unterstützt wird, da sie in der Spalte "Schwäche" "Nicht verfügbar" sagen wird.</span><span class="sxs-lookup"><span data-stu-id="56906-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="56906-150">Software ohne CPE kann auch unter diesem gerätespezifischen Softwarebestand angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56906-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="56906-151">Softwarebeweis</span><span class="sxs-lookup"><span data-stu-id="56906-151">Software evidence</span></span>

<span data-ttu-id="56906-152">Sehen Sie sich an, wo wir eine bestimmte Software auf einem Gerät aus der Registrierung, dem Datenträger oder beiden erkannt haben. Sie finden sie auf jedem Gerät im Gerätesoftwarebestand.</span><span class="sxs-lookup"><span data-stu-id="56906-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="56906-153">Wählen Sie einen Softwarenamen aus, um das Flyout zu öffnen, und suchen Sie nach dem Abschnitt "Software Evidence".</span><span class="sxs-lookup"><span data-stu-id="56906-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Software evidence example of Windows 10 from the devices list, showing software evidence registry path.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="56906-155">Softwareseiten</span><span class="sxs-lookup"><span data-stu-id="56906-155">Software pages</span></span>

<span data-ttu-id="56906-156">Sie können Softwareseiten auf verschiedene Weise anzeigen:</span><span class="sxs-lookup"><span data-stu-id="56906-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="56906-157">Seite "Softwareinventar" > Wählen Sie einen Softwarenamen > **Wählen** Sie im Flyout Softwareseite öffnen aus.</span><span class="sxs-lookup"><span data-stu-id="56906-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="56906-158">[Seite "Sicherheitsempfehlungen"](tvm-security-recommendation.md) > Wählen Sie eine Empfehlung > **Wählen** Sie im Flyout Die Seite Software öffnen aus.</span><span class="sxs-lookup"><span data-stu-id="56906-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="56906-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span><span class="sxs-lookup"><span data-stu-id="56906-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="56906-160">Eine vollständige Seite mit allen Details einer bestimmten Software und den folgenden Informationen wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="56906-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="56906-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span><span class="sxs-lookup"><span data-stu-id="56906-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="56906-162">Datenvisualisierungen, die die Anzahl und den Schweregrad von Sicherheitsrisiken und Falschkonfigurationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="56906-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="56906-163">Außerdem werden Diagramme mit der Anzahl der verfügbar gemachten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56906-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="56906-164">Registerkarten mit Informationen wie:</span><span class="sxs-lookup"><span data-stu-id="56906-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="56906-165">Entsprechende Sicherheitsempfehlungen für die identifizierten Schwachstellen und Schwachstellen.</span><span class="sxs-lookup"><span data-stu-id="56906-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="56906-166">Benannte CVEs von entdeckten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="56906-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="56906-167">Geräte, auf die die Software installiert ist (zusammen mit Gerätename, Domäne, Betriebssystem und mehr).</span><span class="sxs-lookup"><span data-stu-id="56906-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="56906-168">Liste der Softwareversion (einschließlich der Anzahl der Geräte, auf denen die Version installiert ist, die Anzahl der erkannten Sicherheitsrisiken und die Namen der installierten Geräte).</span><span class="sxs-lookup"><span data-stu-id="56906-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Softwarebeispielseite für Visual Studio 2017 mit den Softwaredetails, Schwächen, verfügbar gemachten Geräten und mehr.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="56906-170">Ungenauigkeit melden</span><span class="sxs-lookup"><span data-stu-id="56906-170">Report inaccuracy</span></span>

<span data-ttu-id="56906-171">Melden Sie ein falsch positives Ergebnis, wenn vage, ungenaue oder unvollständige Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56906-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="56906-172">Sie können auch über Sicherheitsempfehlungen berichten, die bereits behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="56906-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="56906-173">Öffnen Sie das Softwaref flyout auf der Seite Softwareinventar.</span><span class="sxs-lookup"><span data-stu-id="56906-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="56906-174">Wählen **Sie Ungenauigkeit melden aus.**</span><span class="sxs-lookup"><span data-stu-id="56906-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="56906-175">Wählen Sie im Flyoutbereich im Dropdownmenü die Kategorie Ungenauigkeit aus, geben Sie Ihre E-Mail-Adresse ein und geben Sie Details zur Ungenauigkeit an.</span><span class="sxs-lookup"><span data-stu-id="56906-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="56906-176">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="56906-176">Select **Submit**.</span></span> <span data-ttu-id="56906-177">Ihr Feedback wird sofort an die Experten für die Bedrohungs- und Sicherheitsrisikoverwaltung gesendet.</span><span class="sxs-lookup"><span data-stu-id="56906-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="56906-178">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="56906-178">Related articles</span></span>

- [<span data-ttu-id="56906-179">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="56906-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="56906-180">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="56906-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="56906-181">Ablauf der Veranstaltung</span><span class="sxs-lookup"><span data-stu-id="56906-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="56906-182">Anzeigen und Organisieren der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="56906-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
