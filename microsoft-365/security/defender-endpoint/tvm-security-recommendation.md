---
title: Sicherheitsempfehlungen nach Bedrohungs- und Sicherheitsrisikoverwaltung
description: Erhalten Sie handlungsfähige Sicherheitsempfehlungen, die durch Bedrohung, wahrscheinliche Verletzung und Nutzen im Bedrohungs- und Sicherheitsrisikomanagement priorisiert werden.
keywords: Bedrohungs- und Sicherheitsrisikoverwaltung, mdatp tvm-Sicherheitsempfehlung, Cybersicherheitsempfehlung, Empfehlung zur Sicherheit mit Aktionen
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
ms.openlocfilehash: 97d496271c1ef7185419f7d39956da0429f070aa
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500488"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="8eff5-104">Sicherheitsempfehlungen – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="8eff5-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8eff5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8eff5-105">**Applies to:**</span></span>

- [<span data-ttu-id="8eff5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8eff5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8eff5-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="8eff5-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8eff5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eff5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8eff5-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8eff5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8eff5-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8eff5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="8eff5-111">Cybersicherheitsschwächen, die in Ihrer Organisation identifiziert werden, werden aktionsrelevanten Sicherheitsempfehlungen zugeordnet und durch ihre Auswirkungen priorisiert.</span><span class="sxs-lookup"><span data-stu-id="8eff5-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="8eff5-112">Mit priorisierten Empfehlungen können Sie die Zeit zur Behebung oder Behebung von Sicherheitsrisiken und zur Verbesserung der Compliance kürzen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="8eff5-113">Jede Sicherheitsempfehlung enthält Maßnahmen zur Behebung.</span><span class="sxs-lookup"><span data-stu-id="8eff5-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="8eff5-114">Zur Unterstützung der Aufgabenverwaltung kann die Empfehlung auch mit Microsoft Intune und Microsoft Endpoint Configuration Manager gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8eff5-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="8eff5-115">Wenn sich die Bedrohungslandschaft ändert, ändert sich auch die Empfehlung, da sie kontinuierlich Informationen aus Ihrer Umgebung sammelt.</span><span class="sxs-lookup"><span data-stu-id="8eff5-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="8eff5-116">Informationen zu E-Mails zu neuen Sicherheitsrisikoereignissen finden Sie unter [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="8eff5-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="8eff5-117">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="8eff5-117">How it works</span></span>

<span data-ttu-id="8eff5-118">Jedes Gerät in der Organisation wird basierend auf drei wichtigen Faktoren erzielt, mit deren Hilfe Kunden sich zum richtigen Zeitpunkt auf die richtigen Dinge konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="8eff5-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="8eff5-119">**Bedrohung** – Merkmale der Sicherheitsrisiken und Exploits in den Geräten Ihrer Organisation und des Verletzungsverlaufs.</span><span class="sxs-lookup"><span data-stu-id="8eff5-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="8eff5-120">Basierend auf diesen Faktoren zeigen die Sicherheitsempfehlungen die entsprechenden Links zu aktiven Warnungen, laufenden Bedrohungskampagnen und den entsprechenden Bedrohungsanalyseberichten an.</span><span class="sxs-lookup"><span data-stu-id="8eff5-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="8eff5-121">**Wahrscheinlichkeit von** Sicherheitsverletzungen – Sicherheitslage und Ausfallsicherheit Ihrer Organisation gegen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="8eff5-122">**Geschäftswert** – Die Ressourcen, kritischen Prozesse und geistigen Eigenschaften Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="8eff5-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="8eff5-123">Navigieren Sie zur Seite Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="8eff5-124">Greifen Sie auf die Seite Sicherheitsempfehlungen auf verschiedene Arten zu:</span><span class="sxs-lookup"><span data-stu-id="8eff5-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="8eff5-125">Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung im [Microsoft Defender Security Center](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8eff5-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="8eff5-126">Die besten Sicherheitsempfehlungen im Dashboard zur Verwaltung von Bedrohungen [und Sicherheitsrisiken](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="8eff5-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="8eff5-127">Zeigen Sie verwandte Sicherheitsempfehlungen an den folgenden Stellen an:</span><span class="sxs-lookup"><span data-stu-id="8eff5-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="8eff5-128">Softwareseite</span><span class="sxs-lookup"><span data-stu-id="8eff5-128">Software page</span></span>
- <span data-ttu-id="8eff5-129">Geräteseite</span><span class="sxs-lookup"><span data-stu-id="8eff5-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="8eff5-130">Navigationsmenü</span><span class="sxs-lookup"><span data-stu-id="8eff5-130">Navigation menu</span></span>

<span data-ttu-id="8eff5-131">Wechseln Sie zum Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung, und wählen Sie **Sicherheitsempfehlungen aus.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="8eff5-132">Die Seite enthält eine Liste der Sicherheitsempfehlungen für die Bedrohungen und Sicherheitsrisiken in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8eff5-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="8eff5-133">Die besten Sicherheitsempfehlungen im Dashboard zur Verwaltung von Bedrohungen und Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8eff5-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="8eff5-134">An einem bestimmten Tag als Sicherheitsadministrator können [](tvm-dashboard-insights.md) Sie sich das Dashboard für [](tvm-exposure-score.md) die Verwaltung von Bedrohungen und Sicherheitsrisiken anschauen, um Ihre Belichtungsergebnisseite neben Ihrer [Microsoft Secure Score for Devices anzuzeigen.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="8eff5-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="8eff5-135">Das Ziel ist **es,** die Gefährdung Ihrer  Organisation durch Sicherheitsrisiken zu verringern und die Gerätesicherheit Ihrer Organisation zu erhöhen, um widerstandsfähiger gegen Cybersicherheitsangriffe zu sein.</span><span class="sxs-lookup"><span data-stu-id="8eff5-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="8eff5-136">Die Liste der besten Sicherheitsempfehlungen kann Ihnen dabei helfen, dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-136">The top security recommendations list can help you achieve that goal.</span></span>

![Beispiel für die Top Security Recommendations Card mit vier Sicherheitsempfehlungen.](images/top-security-recommendations350.png)

<span data-ttu-id="8eff5-138">In den wichtigsten Sicherheitsempfehlungen werden die Verbesserungsmöglichkeiten aufgeführt, die basierend auf den im vorherigen Abschnitt erwähnten wichtigen Faktoren – Bedrohung, Wahrscheinlichkeit, dass eine Verletzung besteht, und Wert – priorisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8eff5-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="8eff5-139">Wenn Sie eine Empfehlung auswählen, gelangen Sie zur Seite mit den Sicherheitsempfehlungen mit weiteren Details.</span><span class="sxs-lookup"><span data-stu-id="8eff5-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="8eff5-140">Übersicht über Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-140">Security recommendations overview</span></span>

<span data-ttu-id="8eff5-141">Anzeigen von Empfehlungen, anzahl gefundener Schwachstellen, zugehöriger Komponenten, Bedrohungseinblicke, Anzahl der verfügbar gemachten Geräte, Status, Behebungstyp, Korrekturaktivitäten, Auswirkungen auf Ihre Belichtungsergebnis und Microsoft Secure Score für Geräte und zugehörige Tags.</span><span class="sxs-lookup"><span data-stu-id="8eff5-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="8eff5-142">Die Farbe des **Diagramms "Verfügbar gemachte Geräte"** ändert sich, wenn sich der Trend ändert.</span><span class="sxs-lookup"><span data-stu-id="8eff5-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="8eff5-143">Wenn die Anzahl der verfügbar gemachten Geräte steigt, ändert sich die Farbe in Rot.</span><span class="sxs-lookup"><span data-stu-id="8eff5-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="8eff5-144">Wenn die Anzahl der verfügbar gemachten Geräte sinkt, ändert sich die Farbe des Diagramms in Grün.</span><span class="sxs-lookup"><span data-stu-id="8eff5-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="8eff5-145">Das Bedrohungs- und Sicherheitsrisikomanagement zeigt Geräte an, die bis vor **30 Tagen verwendet wurden.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="8eff5-146">Dies ist anders als der Rest von Microsoft Defender for Endpoint. Wenn ein Gerät seit mehr als 7 Tagen nicht verwendet wird, hat es den Status "Inaktiv".</span><span class="sxs-lookup"><span data-stu-id="8eff5-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Beispiel für die Angebotsseite für Sicherheitsempfehlungen.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="8eff5-148">Symbole</span><span class="sxs-lookup"><span data-stu-id="8eff5-148">Icons</span></span>

<span data-ttu-id="8eff5-149">Nützliche Symbole machen Sie auch schnell auf:</span><span class="sxs-lookup"><span data-stu-id="8eff5-149">Useful icons also quickly call your attention to:</span></span>
- ![Pfeil, der auf ein Ziel trifft](images/tvm_alert_icon.png) <span data-ttu-id="8eff5-151">mögliche aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-151">possible active alerts</span></span>
- ![roter Fehler](images/tvm_bug_icon.png) <span data-ttu-id="8eff5-153">zugeordnete öffentliche Exploits</span><span class="sxs-lookup"><span data-stu-id="8eff5-153">associated public exploits</span></span>
- ![Glühbirne](images/tvm_insight_icon.png) <span data-ttu-id="8eff5-155">Empfehlungseinblicke</span><span class="sxs-lookup"><span data-stu-id="8eff5-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="8eff5-156">Erkunden von Optionen für Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-156">Explore security recommendation options</span></span>

<span data-ttu-id="8eff5-157">Wählen Sie die Sicherheitsempfehlung aus, die Sie untersuchen oder verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="8eff5-157">Select the security recommendation that you want to investigate or process.</span></span>

![Beispiel für eine Flyoutseite für Sicherheitsempfehlungen.](images/secrec-flyouteolsw.png)

<span data-ttu-id="8eff5-159">Im Flyout können Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="8eff5-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="8eff5-160">**Seite "Software öffnen"** – Öffnen Sie die Softwareseite, um mehr Kontext zur Software und deren Verteilung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8eff5-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="8eff5-161">Die Informationen können Bedrohungskontext, zugehörige Empfehlungen, ermittelte Schwachstellen, die Anzahl der verfügbar gemachten Geräte, ermittelte Sicherheitsrisiken, Namen und detaillierte Geräte mit der installierten Software sowie die Versionsverteilung umfassen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="8eff5-162">[**Korrekturoptionen –**](tvm-remediation.md) Übermitteln Sie eine Korrekturanforderung, um ein Ticket in Microsoft Intune zu öffnen, damit Ihr IT-Administrator es abberaten und adressieren kann.</span><span class="sxs-lookup"><span data-stu-id="8eff5-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="8eff5-163">Verfolgen Sie die Korrekturaktivität auf der Seite Korrektur.</span><span class="sxs-lookup"><span data-stu-id="8eff5-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="8eff5-164">[**Ausnahmeoptionen**](tvm-exception.md) – Senden Sie eine Ausnahme, geben Sie eine Begründung an, und legen Sie die Ausnahmedauer fest, wenn Sie das Problem noch nicht beheben können.</span><span class="sxs-lookup"><span data-stu-id="8eff5-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="8eff5-165">Wenn eine Softwareänderung auf einem Gerät vorgenommen wird, dauert es in der Regel 2 Stunden, bis die Daten im Sicherheitsportal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8eff5-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="8eff5-166">Es kann jedoch manchmal länger dauern.</span><span class="sxs-lookup"><span data-stu-id="8eff5-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="8eff5-167">Konfigurationsänderungen können zwischen 4 und 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="8eff5-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="8eff5-168">Untersuchen von Änderungen bei der Gerätebelichtung oder -auswirkung</span><span class="sxs-lookup"><span data-stu-id="8eff5-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="8eff5-169">Wenn die Anzahl der verfügbar gemachten Geräte stark anspringt oder die Auswirkungen auf die Belichtungszahl Ihrer Organisation und die Microsoft Secure Score für Geräte stark steigen, ist diese Sicherheitsempfehlung eine Untersuchung wert.</span><span class="sxs-lookup"><span data-stu-id="8eff5-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="8eff5-170">Wählen Sie die Empfehlung und **Die Seite Software öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="8eff5-171">Wählen Sie **die Registerkarte Ereigniszeitachse** aus, um alle auswirkungenreichen Ereignisse im Zusammenhang mit dieser Software anzuzeigen, z. B. neue Sicherheitsrisiken oder neue öffentliche Exploits.</span><span class="sxs-lookup"><span data-stu-id="8eff5-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="8eff5-172">Weitere Informationen zur Ereigniszeitachse</span><span class="sxs-lookup"><span data-stu-id="8eff5-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="8eff5-173">Entscheiden Sie, wie Sie die Erhöhung oder das Risiko Ihrer Organisation, z. B. das Einreichen einer Korrekturanforderung, adressieren.</span><span class="sxs-lookup"><span data-stu-id="8eff5-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="8eff5-174">Anforderungsbehebung</span><span class="sxs-lookup"><span data-stu-id="8eff5-174">Request remediation</span></span>

<span data-ttu-id="8eff5-175">Die Bereinigungsfunktion für die Bedrohungs- und Sicherheitsrisikoverwaltung überbrückt die Lücke zwischen Sicherheits- und IT-Administratoren über den Workflow zur Behebungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="8eff5-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="8eff5-176">Sicherheitsadministratoren wie Sie können den IT-Administrator bitten, eine  Sicherheitslücke von der Seite Sicherheitsempfehlung zu Intune zu be behebung.</span><span class="sxs-lookup"><span data-stu-id="8eff5-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="8eff5-177">Weitere Informationen zu Korrekturoptionen</span><span class="sxs-lookup"><span data-stu-id="8eff5-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="8eff5-178">Anfordern einer Korrektur</span><span class="sxs-lookup"><span data-stu-id="8eff5-178">How to request remediation</span></span>

<span data-ttu-id="8eff5-179">Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Korrektur anfordern möchten, und wählen Sie dann **Korrekturoptionen aus.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="8eff5-180">Füllen Sie das Formular aus, und wählen Sie **Anforderung senden aus.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="8eff5-181">Wechseln Sie zur [**Seite Korrektur,**](tvm-remediation.md) um den Status Ihrer Behebungsanforderung zu sehen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="8eff5-182">Weitere Informationen zum Anfordern von Korrekturen</span><span class="sxs-lookup"><span data-stu-id="8eff5-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="8eff5-183">Datei zur Ausnahme</span><span class="sxs-lookup"><span data-stu-id="8eff5-183">File for exception</span></span>

<span data-ttu-id="8eff5-184">Als Alternative zu einer Korrekturanforderung, wenn eine Empfehlung derzeit nicht relevant ist, können Sie Ausnahmen für Empfehlungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="8eff5-185">Weitere Informationen zu Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="8eff5-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="8eff5-186">Ausnahme können nur Benutzer mit Denkberechtigungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8eff5-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="8eff5-187">[Erfahren Sie mehr über RBAC-Rollen](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8eff5-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="8eff5-188">Wenn eine Ausnahme für eine Empfehlung erstellt wird, ist die Empfehlung nicht mehr aktiv.</span><span class="sxs-lookup"><span data-stu-id="8eff5-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="8eff5-189">Der Empfehlungsstatus wird in **Vollständige Ausnahme** oder **Teilausnahme** (nach Gerätegruppe) geändert.</span><span class="sxs-lookup"><span data-stu-id="8eff5-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="8eff5-190">Erstellen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="8eff5-190">How to create an exception</span></span>

<span data-ttu-id="8eff5-191">Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Ausnahme erstellen möchten, und wählen Sie dann **Ausnahmeoptionen aus.**</span><span class="sxs-lookup"><span data-stu-id="8eff5-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Zeigt an, wo sich die Schaltfläche für "Ausnahmeoptionen" in einem Flyout für Sicherheitsempfehlungen befindet.](images/tvm-exception-options.png)

<span data-ttu-id="8eff5-193">Füllen Sie das Formular aus, und übermitteln Sie es.</span><span class="sxs-lookup"><span data-stu-id="8eff5-193">Fill out the form and submit.</span></span> <span data-ttu-id="8eff5-194">Navigieren Sie zum Anzeigen aller Ausnahmen (aktuell und früher) zur Seite Problembehebung unter  dem Menü Bedrohung **&** Sicherheitsrisikoverwaltung, und wählen Sie die Registerkarte Ausnahmen aus. Erfahren Sie mehr über das Erstellen einer [Ausnahme.](tvm-exception.md#create-an-exception) [](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="8eff5-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="8eff5-195">Ungenauigkeit melden</span><span class="sxs-lookup"><span data-stu-id="8eff5-195">Report inaccuracy</span></span>

<span data-ttu-id="8eff5-196">Sie können ein falsch positives Ergebnis melden, wenn vage, ungenaue, unvollständige oder bereits behobene Sicherheitsempfehlungsinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8eff5-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="8eff5-197">Öffnen Sie die Sicherheitsempfehlung.</span><span class="sxs-lookup"><span data-stu-id="8eff5-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="8eff5-198">Wählen Sie die drei Punkte neben der Sicherheitsempfehlung aus, die Sie melden möchten, und wählen Sie **dann Ungenauigkeit** melden aus.</span><span class="sxs-lookup"><span data-stu-id="8eff5-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Zeigt an, wo sich die Schaltfläche "Ungenauigkeit melden" in einem Flyout für Sicherheitsempfehlungen befindet.](images/report-inaccuracy500.png)

3. <span data-ttu-id="8eff5-200">Wählen Sie im Flyoutbereich im Dropdownmenü die Kategorie Ungenauigkeit aus, geben Sie Ihre E-Mail-Adresse ein, und geben Sie Details zur Ungenauigkeit an.</span><span class="sxs-lookup"><span data-stu-id="8eff5-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="8eff5-201">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="8eff5-201">Select **Submit**.</span></span> <span data-ttu-id="8eff5-202">Ihr Feedback wird sofort an die Experten für die Bedrohungs- und Sicherheitsrisikoverwaltung gesendet.</span><span class="sxs-lookup"><span data-stu-id="8eff5-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8eff5-203">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8eff5-203">Related articles</span></span>

- [<span data-ttu-id="8eff5-204">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="8eff5-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8eff5-205">Dashboard</span><span class="sxs-lookup"><span data-stu-id="8eff5-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="8eff5-206">Gefährdungsscore</span><span class="sxs-lookup"><span data-stu-id="8eff5-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="8eff5-207">Microsoft-Sicherheitsbewertung für Geräte</span><span class="sxs-lookup"><span data-stu-id="8eff5-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="8eff5-208">Sicherheitsrisiken korrigieren</span><span class="sxs-lookup"><span data-stu-id="8eff5-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="8eff5-209">Erstellen und Anzeigen von Ausnahmen für Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="8eff5-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="8eff5-210">Ablauf der Veranstaltung</span><span class="sxs-lookup"><span data-stu-id="8eff5-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
