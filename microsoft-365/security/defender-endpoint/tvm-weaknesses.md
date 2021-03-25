---
title: Sicherheitsrisiken in meiner Organisation – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Listet die häufigen Sicherheitsrisiken und Risikorisiken (CVE)-ID von Schwachstellen auf, die in der in Ihrer Organisation ausgeführten Software gefunden wurden. Entdeckt von der Microsoft Defender ATP-Bedrohungs- und Sicherheitsrisikoverwaltungsfunktion.
keywords: mdatp threat & vulnerability management, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b42e25c409ba19639e77e95fafc3d939514511ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068447"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="b7472-105">Sicherheitsrisiken in meiner Organisation – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="b7472-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7472-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b7472-106">**Applies to:**</span></span>
- [<span data-ttu-id="b7472-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b7472-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b7472-108">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="b7472-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b7472-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7472-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b7472-110">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b7472-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7472-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b7472-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b7472-112">Die Bedrohungs- und Sicherheitsrisikoverwaltung verwendet dieselben Signale im Endpunktschutz von Defender for Endpoint, um Sicherheitsrisiken zu überprüfen und zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="b7472-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="b7472-113">Auf **der Seite Schwächen** werden die Softwarerisiken aufgeführt, für die Ihre Geräte verfügbar sind, indem Sie die ID für häufige Sicherheitsrisiken und -risiken (Common Vulnerabilities and Exposures, CVE) auflisten.</span><span class="sxs-lookup"><span data-stu-id="b7472-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="b7472-114">Sie können auch den Schweregrad, die Bewertung des Allgemeinen Bewertungssystems für Sicherheitslücken (Common Vulnerability Scoring System, CVSS), die Verbreitung in Ihrer Organisation, die entsprechende Verletzung, Bedrohungseinblicke und vieles mehr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b7472-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="b7472-115">Wenn einer Sicherheitslücke keine offizielle CVE-ID zugewiesen ist, wird der Sicherheitsrisikoname von der Bedrohungs- und Sicherheitsrisikoverwaltung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b7472-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="b7472-116">Informationen zu E-Mails zu neuen Sicherheitsrisikoereignissen finden Sie unter [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="b7472-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="b7472-117">Navigieren Sie zur Seite Schwächen</span><span class="sxs-lookup"><span data-stu-id="b7472-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="b7472-118">Greifen Sie auf die Seite Schwächen auf verschiedene Arten zu:</span><span class="sxs-lookup"><span data-stu-id="b7472-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="b7472-119">Auswählen **von Schwächen** im Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung im Microsoft Defender Security [Center](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b7472-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="b7472-120">Globale Suche</span><span class="sxs-lookup"><span data-stu-id="b7472-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="b7472-121">Navigationsmenü</span><span class="sxs-lookup"><span data-stu-id="b7472-121">Navigation menu</span></span>

<span data-ttu-id="b7472-122">Wechseln Sie zum Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung, und wählen Sie **Schwächen** aus, um die Liste der CVEs zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b7472-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="b7472-123">Sicherheitsrisiken bei der globalen Suche</span><span class="sxs-lookup"><span data-stu-id="b7472-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="b7472-124">Wechseln Sie zum Dropdownmenü globale Suche.</span><span class="sxs-lookup"><span data-stu-id="b7472-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="b7472-125">Wählen **Sie Sicherheitsanfälligkeit** und Schlüssel in der ID für häufige Sicherheitsrisiken und Gefährdungen (Common Vulnerabilites and Exposures, CVE) aus, die Sie suchen, und wählen Sie dann das Suchsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="b7472-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="b7472-126">Die **Seite Schwächen** wird mit den von Ihnen gesuchten CVE-Informationen geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b7472-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="b7472-127">![Globales Suchfeld mit ausgewählter Dropdownoption "Sicherheitsrisiko" und beispiel CVE.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="b7472-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="b7472-128">Wählen Sie den CVE aus, um ein Flyoutpanel mit weiteren Informationen zu öffnen, einschließlich der Beschreibung der Sicherheitslücke, Details, Bedrohungseinblicke und verfügbar gemachten Geräten.</span><span class="sxs-lookup"><span data-stu-id="b7472-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="b7472-129">Um die restlichen Sicherheitsrisiken auf der Seite Schwächen zu **sehen,** geben Sie CVE ein, und wählen Sie dann Suche aus.</span><span class="sxs-lookup"><span data-stu-id="b7472-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="b7472-130">Übersicht über Schwächen</span><span class="sxs-lookup"><span data-stu-id="b7472-130">Weaknesses overview</span></span>

<span data-ttu-id="b7472-131">Behebung der Sicherheitsrisiken auf exponierten Geräten, um das Risiko für Ihre Ressourcen und Ihre Organisation zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="b7472-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="b7472-132">Wenn die **Spalte Verfügbar gemachte** Geräte 0 zeigt, bedeutet dies, dass Sie nicht gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="b7472-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Zielseite "Schwächen".](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="b7472-134">Einblicke in Sicherheitsverletzungen und Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="b7472-134">Breach and threat insights</span></span>

<span data-ttu-id="b7472-135">Sehen Sie sich in der Spalte Bedrohung alle informationen zu Sicherheitsverletzungen und Bedrohungen **an,** wenn die Symbole rot gefärbt sind.</span><span class="sxs-lookup"><span data-stu-id="b7472-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="b7472-136">Priorisieren Sie immer Empfehlungen, die laufenden Bedrohungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b7472-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="b7472-137">Diese Empfehlungen sind mit dem Symbol "Bedrohungserblick" ![ gekennzeichnet Einfaches Zeichnen eines roten Fehlers.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="b7472-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="b7472-138">and breach insight icon ![ Einfache Zeichnung eines Pfeils, der auf ein Ziel trifft. ](images/tvm_alert_icon.png)</span><span class="sxs-lookup"><span data-stu-id="b7472-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="b7472-139">Das Symbol für Sicherheitslückeneinblicke wird hervorgehoben, wenn in Ihrer Organisation eine Sicherheitslücke gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="b7472-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="b7472-140">![Beispiel für einen Text zu Sicherheitslückeneinblicken, der beim Zeigen auf das Symbol angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7472-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="b7472-141">In diesem wird "mögliche aktive Warnung dieser Empfehlung zugeordnet.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="b7472-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="b7472-142">Das Symbol für Bedrohungseinblicke wird hervorgehoben, wenn die in Ihrer Organisation gefundene Sicherheitslücke mit Exploits verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="b7472-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="b7472-143">Das Zeigen auf das Symbol zeigt, ob die Bedrohung Teil eines Exploitkits ist oder mit bestimmten erweiterten persistenten Kampagnen oder Aktivitätsgruppen verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b7472-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="b7472-144">Wenn verfügbar, gibt es einen Link zu einem Threat Analytics-Bericht mit Zero-Day-Nutzungsnachrichten, Enthüllungen oder zugehörigen Sicherheitsratgebern.</span><span class="sxs-lookup"><span data-stu-id="b7472-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Text zu Bedrohungseinblicken, der beim Zeigen auf das Symbol angezeigt werden könnte.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="b7472-147">Gewinnen von Erkenntnissen zu Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="b7472-147">Gain vulnerability insights</span></span>

<span data-ttu-id="b7472-148">Wenn Sie einen CVE auswählen, wird ein Flyoutpanel mit weiteren Informationen wie der Sicherheitsrisikobeschreibung, Details, Bedrohungseinblicken und verfügbar gemachten Geräten geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b7472-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="b7472-149">Die Kategorie "Betriebssystemfeature" wird in relevanten Szenarien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7472-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="b7472-150">Sie können zu der zugehörigen Sicherheitsempfehlung für jeden CVE mit verfügbar gemachten Geräten wechseln.</span><span class="sxs-lookup"><span data-stu-id="b7472-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Beispiel für ein Schwaches Flyout.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="b7472-152">Software, die nicht unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="b7472-152">Software that isn't supported</span></span>

<span data-ttu-id="b7472-153">CVEs für Software, die derzeit nicht von bedrohungsbedrohungen unterstützt & auf der Seite Schwächen weiterhin vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b7472-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="b7472-154">Da die Software nicht unterstützt wird, sind nur begrenzte Daten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7472-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="b7472-155">Verfügbar gemachte Geräteinformationen sind für CVEs mit nicht unterstützter Software nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7472-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="b7472-156">Filtern Sie nach nicht unterstützter Software, indem Sie im Abschnitt "Verfügbar gemachte Geräte" die Option "Nicht verfügbar" auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7472-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Filter für verfügbar gemachte Geräte.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="b7472-158">Anzeigen von Einträgen zu häufigen Sicherheitsrisiken und Gefährdungen (Common Vulnerabilities and Exposures, CVE) an anderen Orten</span><span class="sxs-lookup"><span data-stu-id="b7472-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="b7472-159">Besonders anfällige Software im Dashboard</span><span class="sxs-lookup"><span data-stu-id="b7472-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="b7472-160">Wechseln Sie zum [Dashboard für die Verwaltung](tvm-dashboard-insights.md) von Bedrohungen und Sicherheitslücken, und scrollen Sie zum Widget **"Besonders anfällige Software".**</span><span class="sxs-lookup"><span data-stu-id="b7472-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="b7472-161">Sie sehen die Anzahl der Sicherheitsrisiken, die in jeder Software gefunden werden, sowie Bedrohungsinformationen und eine hohe Ansicht der Geräteexposition im Laufe der Zeit.</span><span class="sxs-lookup"><span data-stu-id="b7472-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Top vulnerable software card with four columns: software, weaknesses, threats, exposed devices.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="b7472-163">Wählen Sie die Software aus, die Sie untersuchen möchten, um zu einer Drilldownseite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="b7472-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="b7472-164">Wählen Sie die **Registerkarte Gefundene Sicherheitsrisiken** aus.</span><span class="sxs-lookup"><span data-stu-id="b7472-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="b7472-165">Wählen Sie die Sicherheitslücke aus, die Sie untersuchen möchten, um weitere Informationen zu Sicherheitsrisikodetails zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b7472-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Übersicht über Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="b7472-167">Entdecken von Sicherheitsrisiken auf der Geräteseite</span><span class="sxs-lookup"><span data-stu-id="b7472-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="b7472-168">Anzeigen verwandter Schwachstelleninformationen auf der Geräteseite.</span><span class="sxs-lookup"><span data-stu-id="b7472-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="b7472-169">Wechseln Sie zur Navigationsleiste microsoft Defender Security Center, und wählen Sie dann das Gerätesymbol aus.</span><span class="sxs-lookup"><span data-stu-id="b7472-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="b7472-170">Die **Seite Geräteliste** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b7472-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="b7472-171">Wählen Sie **auf der Seite** Geräteliste den Gerätenamen aus, den Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7472-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Geräteliste mit ausgewähltem Gerät, das untersucht werden soll.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="b7472-173">Die Geräteseite wird mit Details und Antwortoptionen für das Gerät geöffnet, das Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7472-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="b7472-174">Wählen **Sie Gefundene Sicherheitsrisiken aus.**</span><span class="sxs-lookup"><span data-stu-id="b7472-174">Select **Discovered vulnerabilities**.</span></span>

    ![Geräteseite mit Details und Antwortoptionen.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="b7472-176">Wählen Sie die Sicherheitslücke aus, die Sie untersuchen möchten, um ein Flyoutpanel mit den CVE-Details zu öffnen, z. B.: Beschreibung von Sicherheitslücken, Einblicke in Bedrohungen und Erkennungslogik.</span><span class="sxs-lookup"><span data-stu-id="b7472-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="b7472-177">CVE-Erkennungslogik</span><span class="sxs-lookup"><span data-stu-id="b7472-177">CVE Detection logic</span></span>

<span data-ttu-id="b7472-178">Ähnlich wie der Softwarebeweis zeigen wir nun die Erkennungslogik an, die wir auf einem Gerät angewendet haben, um zu erkennen, dass es anfällig ist.</span><span class="sxs-lookup"><span data-stu-id="b7472-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="b7472-179">Der neue Abschnitt heißt "Erkennungslogik" (in allen erkannten Sicherheitslücken auf der Geräteseite) und zeigt die Erkennungslogik und -quelle.</span><span class="sxs-lookup"><span data-stu-id="b7472-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="b7472-180">Die Kategorie "Betriebssystemfeature" wird auch in relevanten Szenarien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7472-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="b7472-181">Ein CVE würde sich nur dann auf Geräte auswirken, auf die ein anfälliges Betriebssystem ausgeführt wird, wenn eine bestimmte Betriebssystemkomponente aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b7472-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="b7472-182">Angenommen, Windows Server 2019 hat eine Sicherheitslücke in seiner DNS-Komponente.</span><span class="sxs-lookup"><span data-stu-id="b7472-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="b7472-183">Mit dieser neuen Funktion fügen wir diesen CVE nur an die Windows Server 2019-Geräte an, deren DNS-Funktion im Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b7472-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Beispiel für die Erkennungslogik, in dem die auf dem Gerät und den KBs erkannte Software aufgeführt wird.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="b7472-185">Ungenauigkeit melden</span><span class="sxs-lookup"><span data-stu-id="b7472-185">Report inaccuracy</span></span>

<span data-ttu-id="b7472-186">Melden Sie ein falsch positives Ergebnis, wenn vage, ungenaue oder unvollständige Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b7472-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="b7472-187">Sie können auch über Sicherheitsempfehlungen berichten, die bereits behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="b7472-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="b7472-188">Öffnen Sie den CVE auf der Seite Schwächen.</span><span class="sxs-lookup"><span data-stu-id="b7472-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="b7472-189">Wählen **Sie Ungenauigkeit melden aus,** und ein Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b7472-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="b7472-190">Wählen Sie im Dropdownmenü die Kategorie Ungenauigkeit aus, und geben Sie Ihre E-Mail-Adresse und Ungenauigkeitsdetails ein.</span><span class="sxs-lookup"><span data-stu-id="b7472-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="b7472-191">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="b7472-191">Select **Submit**.</span></span> <span data-ttu-id="b7472-192">Ihr Feedback wird sofort an die Experten für die Bedrohungs- und Sicherheitsrisikoverwaltung gesendet.</span><span class="sxs-lookup"><span data-stu-id="b7472-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b7472-193">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b7472-193">Related articles</span></span>

- [<span data-ttu-id="b7472-194">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="b7472-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b7472-195">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="b7472-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b7472-196">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="b7472-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="b7472-197">Dashboard-Einblicke</span><span class="sxs-lookup"><span data-stu-id="b7472-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="b7472-198">Anzeigen und Organisieren der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="b7472-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
