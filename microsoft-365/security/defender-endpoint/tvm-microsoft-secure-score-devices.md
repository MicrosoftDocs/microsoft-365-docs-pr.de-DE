---
title: Microsoft-Sicherheitsbewertung für Geräte
description: Ihre Bewertung für Geräte zeigt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte über Anwendung, Betriebssystem, Netzwerk, Konten und Sicherheitskontrollen hinweg.
keywords: Microsoft-Sicherheitsbewertung für Geräte, Microsoft Defender für Endpunkt Microsoft-Sicherheitsbewertung für Geräte, Sicherheitsbewertung, Konfigurationsbewertung, Bedrohungs- und Sicherheitsrisikomanagement, Sicherheitskontrollen, Verbesserungsmöglichkeiten, Sicherheitskonfigurationsbewertung im Laufe der Zeit, Sicherheitsstatus, Baseline
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
ms.openlocfilehash: 13307d3205818d41e7b2219b4e3a4ed6e9f2d5bb
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454774"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="c6319-104">Microsoft-Sicherheitsbewertung für Geräte</span><span class="sxs-lookup"><span data-stu-id="c6319-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6319-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c6319-105">**Applies to:**</span></span>

- [<span data-ttu-id="c6319-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c6319-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c6319-107">Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="c6319-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="c6319-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6319-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6319-109">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="c6319-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6319-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="c6319-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="c6319-111">Die Konfigurationsbewertung ist jetzt Teil Bedrohungs- und Sicherheitsrisikomanagement als Microsoft-Sicherheitsbewertung für Geräte.</span><span class="sxs-lookup"><span data-stu-id="c6319-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="c6319-112">Ihre Bewertung für Geräte ist im [Bedrohungs- und Sicherheitsrisikomanagement-Dashboard](tvm-dashboard-insights.md) des Microsoft 365 Defender-Portals sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c6319-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c6319-113">Eine höhere Microsoft-Sicherheitsbewertung für Geräte bedeutet, dass Ihre Endpunkte stabiler vor Angriffen auf Cybersicherheitsbedrohungen sind.</span><span class="sxs-lookup"><span data-stu-id="c6319-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="c6319-114">Es spiegelt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte in den folgenden Kategorien wider:</span><span class="sxs-lookup"><span data-stu-id="c6319-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="c6319-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c6319-115">Application</span></span>
- <span data-ttu-id="c6319-116">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="c6319-116">Operating system</span></span>
- <span data-ttu-id="c6319-117">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="c6319-117">Network</span></span>
- <span data-ttu-id="c6319-118">Konten</span><span class="sxs-lookup"><span data-stu-id="c6319-118">Accounts</span></span>
- <span data-ttu-id="c6319-119">Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="c6319-119">Security controls</span></span>

<span data-ttu-id="c6319-120">Wählen Sie eine Kategorie aus, um zur Seite [**"Sicherheitsempfehlungen"**](tvm-security-recommendation.md) zu wechseln und die entsprechenden Empfehlungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6319-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="c6319-121">Aktivieren des Microsoft Secure Score-Connectors</span><span class="sxs-lookup"><span data-stu-id="c6319-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="c6319-122">Leiten Sie Microsoft Defender für Endpunkt-Signale weiter, sodass Die Microsoft-Sicherheitsbewertung einen Einblick in den Sicherheitsstatus des Geräts erhält.</span><span class="sxs-lookup"><span data-stu-id="c6319-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="c6319-123">Weitergeleitete Daten werden am selben Speicherort wie Ihre Microsoft-Sicherheitsbewertungsdaten gespeichert und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c6319-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="c6319-124">Es kann bis zu ein paar Stunden dauern, bis Änderungen im Dashboard angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6319-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="c6319-125">Wechseln Sie im Navigationsbereich zu **Einstellungen** Allgemeine erweiterte  >    >    >  **Endpunktfeatures**</span><span class="sxs-lookup"><span data-stu-id="c6319-125">In the navigation pane, go to **Settings** > **Endpoints** > **General** > **Advanced features**</span></span> 

2. <span data-ttu-id="c6319-126">Scrollen Sie nach unten zur **Microsoft-Sicherheitsbewertung,** und setzen Sie die Einstellung auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="c6319-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="c6319-127">Wählen Sie **"Einstellungen speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="c6319-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="c6319-128">So funktioniert's</span><span class="sxs-lookup"><span data-stu-id="c6319-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="c6319-129">Die Microsoft-Sicherheitsbewertung für Geräte unterstützt derzeit Konfigurationen, die über Gruppenrichtlinien festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="c6319-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="c6319-130">Aufgrund der aktuellen teilweisen Intune-Unterstützung werden Konfigurationen, die möglicherweise über Intune festgelegt wurden, als falsch konfiguriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c6319-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="c6319-131">Wenden Sie sich an Ihren IT-Administrator, um den tatsächlichen Konfigurationsstatus für den Fall zu überprüfen, dass Ihre Organisation Intune für die sichere Konfigurationsverwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6319-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="c6319-132">Die Daten in der Microsoft-Karte "Sicherheitsbewertung für Geräte" sind das Produkt eines laufenden Prozesses zur Ermittlung von Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="c6319-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="c6319-133">Es wird mit Konfigurationsermittlungsbewertungen aggregiert, die fortlaufend:</span><span class="sxs-lookup"><span data-stu-id="c6319-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="c6319-134">Vergleichen sie gesammelte Konfigurationen mit den erfassten Benchmarks, um falsch konfigurierte Ressourcen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c6319-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="c6319-135">Zuordnen von Konfigurationen zu Sicherheitsrisiken, die behoben oder teilweise behoben werden können (Risikominderung)</span><span class="sxs-lookup"><span data-stu-id="c6319-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="c6319-136">Sammeln und Verwalten von Konfigurationsbenchmarks für bewährte Methoden (Anbieter, Sicherheitsfeeds, interne Forschungsteams)</span><span class="sxs-lookup"><span data-stu-id="c6319-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="c6319-137">Erfassen und Überwachen von Änderungen des Konfigurationsstatus der Sicherheitssteuerung aus allen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c6319-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="c6319-138">Verbessern der Sicherheitskonfiguration</span><span class="sxs-lookup"><span data-stu-id="c6319-138">Improve your security configuration</span></span>

<span data-ttu-id="c6319-139">Verbessern Sie Ihre Sicherheitskonfiguration, indem Sie Probleme aus der Liste der Sicherheitsempfehlungen beheben.</span><span class="sxs-lookup"><span data-stu-id="c6319-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="c6319-140">Dadurch wird Ihre Microsoft-Sicherheitsbewertung für Geräte verbessert, und Ihre Organisation wird stabiler gegen Cybersicherheitsbedrohungen und Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="c6319-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="c6319-141">Wählen Sie auf der Karte "Microsoft-Sicherheitsbewertung für Geräte" im Bedrohungs- und Sicherheitsrisikomanagement-Dashboard eine der Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="c6319-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select one of the categories.</span></span> <span data-ttu-id="c6319-142">Sie werden die Liste der Empfehlungen im Zusammenhang mit dieser Kategorie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6319-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="c6319-143">Sie gelangen dann zur Seite [**"Sicherheitsempfehlungen".**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="c6319-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="c6319-144">Wenn Sie alle Sicherheitsempfehlungen anzeigen möchten, löschen Sie das Suchfeld, sobald Sie zur Seite "Sicherheitsempfehlungen" gelangen.</span><span class="sxs-lookup"><span data-stu-id="c6319-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="c6319-145">Wählen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c6319-145">Select an item on the list.</span></span> <span data-ttu-id="c6319-146">Das Flyout-Panel wird mit Details im Zusammenhang mit der Empfehlung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c6319-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="c6319-147">Wählen Sie **Korrekturoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="c6319-147">Select **Remediation options**.</span></span>

   :::image type="content" alt-text="Sicherheitskontrollen im Zusammenhang mit Sicherheitsempfehlungen." source="images/security-controls.png":::

3. <span data-ttu-id="c6319-149">Lesen Sie die Beschreibung, um den Kontext des Problems und die nächsten Aktionen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="c6319-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="c6319-150">Wählen Sie ein Fälligkeitsdatum aus, fügen Sie Notizen hinzu, und wählen Sie **"Alle Korrekturaktivitätsdaten in CSV exportieren"** aus, damit Sie sie zur Nachverfolgung an eine E-Mail anfügen können.</span><span class="sxs-lookup"><span data-stu-id="c6319-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="c6319-151">**Anforderung senden**.</span><span class="sxs-lookup"><span data-stu-id="c6319-151">**Submit request**.</span></span> <span data-ttu-id="c6319-152">Es wird eine Bestätigungsmeldung angezeigt, dass die Korrekturaufgabe erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6319-152">You'll see a confirmation message that the remediation task has been created.</span></span>

   :::image type="content" alt-text="Bestätigung der Erstellung von Korrekturaufgaben." source="images/remediation-task-created.png":::

5. <span data-ttu-id="c6319-154">Speichern Sie Ihre CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="c6319-154">Save your CSV file.</span></span>

   :::image type="content" alt-text="Speichern Sie die CSV-Datei." source="images/tvm_save_csv_file.png":::

6. <span data-ttu-id="c6319-156">Senden Sie eine Nachverfolgungs-E-Mail an Ihren IT-Administrator, und lassen Sie zu, dass die Zeit, die Sie für die Korrektur zugewiesen haben, im System verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="c6319-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="c6319-157">Überprüfen Sie die **Microsoft-Karte "Sicherheitsbewertung für Geräte"** erneut auf dem Dashboard.</span><span class="sxs-lookup"><span data-stu-id="c6319-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="c6319-158">Die Anzahl der Empfehlungen für Sicherheitskontrollen nimmt ab.</span><span class="sxs-lookup"><span data-stu-id="c6319-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="c6319-159">Wenn Sie **Sicherheitssteuerelemente** auswählen, um zur Seite **"Sicherheitsempfehlungen"** zurückzukehren, wird das element, das Sie adressiert haben, dort nicht mehr aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6319-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="c6319-160">Ihre Microsoft-Sicherheitsbewertung für Geräte sollte erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="c6319-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c6319-161">Laden Sie die folgenden obligatorischen Sicherheitsupdates herunter, und stellen Sie sie in Ihrem Netzwerk bereit, um die Erkennungsraten ihrer Schwachstellen zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="c6319-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="c6319-162">19H1-Kunden | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="c6319-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="c6319-163">RS5-Kunden | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="c6319-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="c6319-164">RS4-Kunden | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="c6319-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="c6319-165">RS3-Kunden | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="c6319-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="c6319-166">So laden Sie die Sicherheitsupdates herunter:</span><span class="sxs-lookup"><span data-stu-id="c6319-166">To download the security updates:</span></span>
>1. <span data-ttu-id="c6319-167">Wechseln Sie zum [Microsoft Update-Katalog.](https://www.catalog.update.microsoft.com/home.aspx)</span><span class="sxs-lookup"><span data-stu-id="c6319-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="c6319-168">Geben Sie die KB-Nummer des Sicherheitsupdates ein, die Sie herunterladen müssen, und klicken Sie dann auf **"Suchen".**</span><span class="sxs-lookup"><span data-stu-id="c6319-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="c6319-169">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c6319-169">Related topics</span></span>

- [<span data-ttu-id="c6319-170">Übersicht über Bedrohungen und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="c6319-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="c6319-171">Dashboard</span><span class="sxs-lookup"><span data-stu-id="c6319-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="c6319-172">Gefährdungsscore</span><span class="sxs-lookup"><span data-stu-id="c6319-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="c6319-173">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="c6319-173">Security recommendations</span></span>](tvm-security-recommendation.md)
