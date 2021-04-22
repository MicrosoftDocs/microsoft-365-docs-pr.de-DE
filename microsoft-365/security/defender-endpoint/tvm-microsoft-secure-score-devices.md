---
title: Microsoft-Sicherheitsbewertung für Geräte
description: Ihre Bewertung für Geräte zeigt den gemeinsamen Sicherheitskonfigurationsstatus Ihrer Geräte über Anwendungs-, Betriebssystem-, Netzwerk-, Konten- und Sicherheitssteuerelemente hinweg an.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, threat and vulnerability management, security controls, improvement opportunities, security configuration score over time, security posture, baseline
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
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934081"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="d6a69-104">Microsoft-Sicherheitsbewertung für Geräte</span><span class="sxs-lookup"><span data-stu-id="d6a69-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d6a69-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d6a69-105">**Applies to:**</span></span>

- [<span data-ttu-id="d6a69-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d6a69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d6a69-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="d6a69-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d6a69-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6a69-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d6a69-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d6a69-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d6a69-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d6a69-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="d6a69-111">Die Konfigurationsnote ist jetzt Teil der Bedrohungs- und Sicherheitsrisikoverwaltung als Microsoft Secure Score für Geräte.</span><span class="sxs-lookup"><span data-stu-id="d6a69-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="d6a69-112">Ihre Bewertung für Geräte wird im [Dashboard](tvm-dashboard-insights.md) zur Verwaltung von Bedrohungen und Sicherheitsrisiken im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a69-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="d6a69-113">Eine höhere Microsoft Secure Score für Geräte bedeutet, dass Ihre Endpunkte widerstandsfähiger gegen Cybersicherheitsangriffe sind.</span><span class="sxs-lookup"><span data-stu-id="d6a69-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="d6a69-114">Dies spiegelt den Konfigurationsstatus für die gemeinsame Sicherheit Ihrer Geräte in den folgenden Kategorien wider:</span><span class="sxs-lookup"><span data-stu-id="d6a69-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="d6a69-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="d6a69-115">Application</span></span>
- <span data-ttu-id="d6a69-116">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d6a69-116">Operating system</span></span>
- <span data-ttu-id="d6a69-117">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d6a69-117">Network</span></span>
- <span data-ttu-id="d6a69-118">Konten</span><span class="sxs-lookup"><span data-stu-id="d6a69-118">Accounts</span></span>
- <span data-ttu-id="d6a69-119">Sicherheitssteuerelemente</span><span class="sxs-lookup"><span data-stu-id="d6a69-119">Security controls</span></span>

<span data-ttu-id="d6a69-120">Wählen Sie eine Kategorie aus, um zur Seite [**Sicherheitsempfehlungen zu**](tvm-security-recommendation.md) wechseln, und zeigen Sie die entsprechenden Empfehlungen an.</span><span class="sxs-lookup"><span data-stu-id="d6a69-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="d6a69-121">Aktivieren des Microsoft Secure Score-Connectors</span><span class="sxs-lookup"><span data-stu-id="d6a69-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="d6a69-122">Weiterleiten von Microsoft Defender for Endpoint-Signalen, was Microsoft Secure Score Sichtbarkeit in der Gerätesicherheitshaltung bietet.</span><span class="sxs-lookup"><span data-stu-id="d6a69-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="d6a69-123">Weitergeleitete Daten werden am gleichen Speicherort wie Ihre Microsoft Secure Score-Daten gespeichert und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d6a69-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="d6a69-124">Es kann bis zu ein paar Stunden dauern, bis Änderungen im Dashboard angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6a69-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="d6a69-125">Wechseln Sie im Navigationsbereich zu **Einstellungen**  >  **Erweiterte Features**</span><span class="sxs-lookup"><span data-stu-id="d6a69-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="d6a69-126">Scrollen Sie nach unten **zu Microsoft Secure Score,** und schalten Sie die Einstellung auf **Ein um.**</span><span class="sxs-lookup"><span data-stu-id="d6a69-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="d6a69-127">Wählen **Sie Einstellungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="d6a69-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d6a69-128">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="d6a69-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="d6a69-129">Microsoft Secure Score für Geräte unterstützt derzeit Konfigurationen, die über Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d6a69-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="d6a69-130">Aufgrund der aktuellen teilweisen Intune-Unterstützung werden Konfigurationen, die möglicherweise über Intune festgelegt wurden, möglicherweise als falsch konfiguriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a69-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="d6a69-131">Wenden Sie sich an Ihren IT-Administrator, um den tatsächlichen Konfigurationsstatus zu überprüfen, falls Ihre Organisation Intune für die sichere Konfigurationsverwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6a69-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="d6a69-132">Die Daten auf der Microsoft Secure Score for Devices-Karte sind das Produkt einer sorgfältigen und fortlaufenden Ermittlung von Sicherheitslücken.</span><span class="sxs-lookup"><span data-stu-id="d6a69-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="d6a69-133">Es wird mit Konfigurationsermittlungsbewertungen aggregiert, die kontinuierlich:</span><span class="sxs-lookup"><span data-stu-id="d6a69-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="d6a69-134">Vergleichen erfasster Konfigurationen mit den gesammelten Benchmarks zum Ermitteln falsch konfigurierter Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d6a69-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="d6a69-135">Zuordnung von Konfigurationen zu Sicherheitsrisiken, die behoben oder teilweise behoben werden können (Risikominderung)</span><span class="sxs-lookup"><span data-stu-id="d6a69-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="d6a69-136">Sammeln und Verwalten bewährter Konfigurations benchmarks (Anbieter, Sicherheitsfeeds, interne Forschungsteams)</span><span class="sxs-lookup"><span data-stu-id="d6a69-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="d6a69-137">Erfassen und Überwachen von Änderungen des Konfigurationsstatus der Sicherheitssteuerung aus allen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d6a69-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="d6a69-138">Verbessern Der Sicherheitskonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6a69-138">Improve your security configuration</span></span>

<span data-ttu-id="d6a69-139">Verbessern Sie Ihre Sicherheitskonfiguration, indem Sie Probleme aus der Liste der Sicherheitsempfehlungen beheben.</span><span class="sxs-lookup"><span data-stu-id="d6a69-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="d6a69-140">Dabei verbessert sich Ihre Microsoft Secure Score for Devices, und Ihre Organisation wird widerstandsfähiger gegen Cybersicherheitsbedrohungen und Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="d6a69-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="d6a69-141">Wählen Sie auf der Microsoft Secure Score for Devices-Karte im Dashboard für die Bedrohungs- und Sicherheitsrisikoverwaltung eine der Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="d6a69-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="d6a69-142">Sie sehen die Liste der Empfehlungen im Zusammenhang mit dieser Kategorie.</span><span class="sxs-lookup"><span data-stu-id="d6a69-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="d6a69-143">Sie gelangen zur Seite [**Sicherheitsempfehlungen.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="d6a69-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="d6a69-144">Wenn Sie alle Sicherheitsempfehlungen anzeigen möchten, löschen Sie das Suchfeld, sobald Sie zur Seite Sicherheitsempfehlungen gelangen.</span><span class="sxs-lookup"><span data-stu-id="d6a69-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="d6a69-145">Wählen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="d6a69-145">Select an item on the list.</span></span> <span data-ttu-id="d6a69-146">Das Flyoutpanel wird mit Details zur Empfehlung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d6a69-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="d6a69-147">Wählen **Sie Korrekturoptionen aus.**</span><span class="sxs-lookup"><span data-stu-id="d6a69-147">Select **Remediation options**.</span></span>

   ![Sicherheitskontrollen im Zusammenhang mit Sicherheitsempfehlungen](images/tvm_security_controls.png)

3. <span data-ttu-id="d6a69-149">Lesen Sie die Beschreibung, um den Kontext des Problems und die nächsten Schritte zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="d6a69-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="d6a69-150">Wählen Sie ein Fälligkeitsdatum aus, fügen Sie Notizen hinzu, und wählen Sie Alle Berichtsberichtsaktivitätsdaten in **CSV** exportieren aus, damit Sie sie an eine E-Mail für die Nachbereinigung anfügen können.</span><span class="sxs-lookup"><span data-stu-id="d6a69-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="d6a69-151">**Senden der Anforderung**.</span><span class="sxs-lookup"><span data-stu-id="d6a69-151">**Submit request**.</span></span> <span data-ttu-id="d6a69-152">Es wird eine Bestätigungsmeldung angezeigt, dass die Problembehebungsaufgabe erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6a69-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="d6a69-153">![Bestätigung der Erstellung von Korrekturaufgabe](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="d6a69-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="d6a69-154">Speichern Sie Ihre CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="d6a69-154">Save your CSV file.</span></span>
   <span data-ttu-id="d6a69-155">![Speichern der CSV-Datei](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="d6a69-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="d6a69-156">Senden Sie eine Follow-up-E-Mail an Ihren IT-Administrator, und lassen Sie die Zeit zu, die Sie für die Behebung zur Vermehrung im System zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="d6a69-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="d6a69-157">Überprüfen Sie **die Microsoft Secure Score for Devices-Karte** erneut auf dem Dashboard.</span><span class="sxs-lookup"><span data-stu-id="d6a69-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="d6a69-158">Die Anzahl der Empfehlungen für Sicherheitskontrollen nimmt ab.</span><span class="sxs-lookup"><span data-stu-id="d6a69-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="d6a69-159">Wenn Sie **Sicherheitssteuerelemente auswählen,** um zur Seite Sicherheitsempfehlungen zurück zu wechseln, wird das von Ihnen adressierte Element dort nicht mehr aufgeführt. </span><span class="sxs-lookup"><span data-stu-id="d6a69-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="d6a69-160">Ihre Microsoft Secure Score für Geräte sollte erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="d6a69-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d6a69-161">Laden Sie die folgenden obligatorischen Sicherheitsupdates herunter, und stellen Sie sie in Ihrem Netzwerk bereit, um die Erkennungsraten für Sicherheitsrisiken zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="d6a69-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="d6a69-162">19H1-Kunden | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="d6a69-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="d6a69-163">RS5-Kunden | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="d6a69-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="d6a69-164">RS4-Kunden | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="d6a69-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="d6a69-165">RS3-Kunden | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="d6a69-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="d6a69-166">So laden Sie die Sicherheitsupdates herunter:</span><span class="sxs-lookup"><span data-stu-id="d6a69-166">To download the security updates:</span></span>
>1. <span data-ttu-id="d6a69-167">Wechseln Sie zu [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6a69-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="d6a69-168">Wählen Sie die KB-Nummer des Sicherheitsupdates ein, die Sie herunterladen müssen, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d6a69-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="d6a69-169">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d6a69-169">Related topics</span></span>

- [<span data-ttu-id="d6a69-170">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="d6a69-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d6a69-171">Dashboard</span><span class="sxs-lookup"><span data-stu-id="d6a69-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="d6a69-172">Gefährdungsscore</span><span class="sxs-lookup"><span data-stu-id="d6a69-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="d6a69-173">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="d6a69-173">Security recommendations</span></span>](tvm-security-recommendation.md)
