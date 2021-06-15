---
title: Microsoft Defender AV-Ereignis-IDs und Fehlercodes
description: Nachschlagen der Ursachen und Lösungen für Microsoft Defender Antivirus Ereignis-IDs und -Fehler
keywords: Ereignis, Fehlercode, Siem, Protokollierung, Problembehandlung, Wef, Windows-Ereignisweiterleitung
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cba7a9d6ed23ac1dc72ef6cbcecfdfc7a0f4c60b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926283"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="8f651-104">Überprüfen von Ereignisprotokollen und Fehlercodes zum Behandeln von Problemen mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8f651-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8f651-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f651-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8f651-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8f651-107">Wenn ein Problem mit Microsoft Defender Antivirus auftritt, können Sie in den Tabellen in diesem Thema nach einem übereinstimmenden Problem und einer potenziellen Lösung suchen.</span><span class="sxs-lookup"><span data-stu-id="8f651-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="8f651-108">Die Tabellenliste:</span><span class="sxs-lookup"><span data-stu-id="8f651-108">The tables list:</span></span>

- <span data-ttu-id="8f651-109">[Microsoft Defender Antivirus Ereignis-IDs](#windows-defender-av-ids) (diese gelten sowohl für Windows 10 als auch für Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="8f651-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="8f651-110">Microsoft Defender Antivirus Clientfehlercodes</span><span class="sxs-lookup"><span data-stu-id="8f651-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="8f651-111">Interne Microsoft Defender Antivirus Clientfehlercodes (von Microsoft während der Entwicklung und beim Testen verwendet)</span><span class="sxs-lookup"><span data-stu-id="8f651-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="8f651-112">Sie können auch die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die folgenden Features funktionieren:</span><span class="sxs-lookup"><span data-stu-id="8f651-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="8f651-113">Aus der Cloud gelieferter Schutz</span><span class="sxs-lookup"><span data-stu-id="8f651-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="8f651-114">Schnelles Lernen (einschließlich "Bei erster Anzeige blockieren")</span><span class="sxs-lookup"><span data-stu-id="8f651-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="8f651-115">Blockieren potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8f651-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="8f651-116">Microsoft Defender Antivirus-Ereignis-IDs</span><span class="sxs-lookup"><span data-stu-id="8f651-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="8f651-117">Microsoft Defender Antivirus zeichnet Ereignis-IDs im Windows-Ereignisprotokoll auf.</span><span class="sxs-lookup"><span data-stu-id="8f651-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="8f651-118">Sie können das Ereignisprotokoll direkt anzeigen, oder wenn Sie über ein SIEM-Tool (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch [Microsoft Defender Antivirus Clientereignis-IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) verwenden, um bestimmte Ereignisse und Fehler von Ihren Endpunkten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8f651-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="8f651-119">In der Tabelle in diesem Abschnitt sind die wichtigsten Microsoft Defender Antivirus Ereignis-IDs aufgeführt, und nach Möglichkeit werden Lösungsvorschläge zum Beheben oder Beheben des Fehlers bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8f651-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="8f651-120">So zeigen Sie ein Microsoft Defender Antivirus-Ereignis an</span><span class="sxs-lookup"><span data-stu-id="8f651-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="8f651-121">Öffnen **Sie die Ereignisanzeige.**</span><span class="sxs-lookup"><span data-stu-id="8f651-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="8f651-122">Erweitern Sie in der Konsolenstruktur **Anwendungs- und Dienstprotokolle,** dann **Microsoft**, dann **Windows** und **dann Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="8f651-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="8f651-123">Doppelklicken Sie auf **"Betriebsbereit".**</span><span class="sxs-lookup"><span data-stu-id="8f651-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="8f651-124">Zeigen Sie im Detailbereich die Liste der einzelnen Ereignisse an, um Ihr Ereignis zu finden.</span><span class="sxs-lookup"><span data-stu-id="8f651-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="8f651-125">Klicken Sie auf das Ereignis, um bestimmte Details zu einem Ereignis im unteren Bereich unter den Registerkarten **"Allgemein"** und **"Details"** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f651-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="8f651-126">Ereignis-ID: 1000</span><span class="sxs-lookup"><span data-stu-id="8f651-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-127">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="8f651-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-129">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-129">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-130">
<b>Ein Antischadsoftwarescan wurde gestartet. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="8f651-131">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-132">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-133">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-134">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-135">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-136">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-137">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-137">Full scan</span></span></li>
<li><span data-ttu-id="8f651-138">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-138">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-139">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-139">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-140">
</dt>
<dt>Scannen von Ressourcen: &lt; Ressourcen (z. B. Dateien/Verzeichnisse/BHO), &gt; die gescannt wurden.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-141">Ereignis-ID: 1001</span><span class="sxs-lookup"><span data-stu-id="8f651-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-142">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-144">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-144">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-145">
<b>Ein Antischadsoftwarescan wurde abgeschlossen.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-146">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-147">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-148">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-149">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-150">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-151">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-152">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-152">Full scan</span></span></li>
<li><span data-ttu-id="8f651-153">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-153">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-154">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-154">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-155">
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Scanzeit</dt>des
<dt>Benutzers: &lt; Die Dauer einer Überprüfung. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-156">Ereignis-ID: 1002</span><span class="sxs-lookup"><span data-stu-id="8f651-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-157">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-159">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-159">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-160">
<b>Ein Antischadsoftwarescan wurde beendet, bevor er abgeschlossen wurde. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-161">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-162">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-163">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-164">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-165">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-166">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-167">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-167">Full scan</span></span></li>
<li><span data-ttu-id="8f651-168">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-168">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-169">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-169">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-170">
</dt>
<dt>Benutzer: &lt; Domäne &gt; &amp; lt; &gt;Scanzeit</dt>des
<dt>Benutzers: &lt; Die Dauer einer Überprüfung. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-171">Ereignis-ID: 1003</span><span class="sxs-lookup"><span data-stu-id="8f651-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-172">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-174">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-174">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-175">
<b>Ein Antischadsoftwarescan wurde angehalten. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-176">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-177">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-178">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-179">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-180">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-181">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-182">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-182">Full scan</span></span></li>
<li><span data-ttu-id="8f651-183">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-183">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-184">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-184">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-185">
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-186">Ereignis-ID: 1004</span><span class="sxs-lookup"><span data-stu-id="8f651-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-187">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-189">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-189">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-190">
<b>Ein Antischadsoftwarescan wurde fortgesetzt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-191">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-192">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-193">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-194">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-195">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-196">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-197">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-197">Full scan</span></span></li>
<li><span data-ttu-id="8f651-198">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-198">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-199">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-199">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-200">
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-201">Ereignis-ID: 1005</span><span class="sxs-lookup"><span data-stu-id="8f651-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-202">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-204">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-204">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-205">
<b>Fehler bei einem Antischadsoftwarescan. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-206">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8f651-207">
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-208">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-209">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-210">Antimalware</span></span></li>
</ul><span data-ttu-id="8f651-211">
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-212">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="8f651-212">Full scan</span></span></li>
<li><span data-ttu-id="8f651-213">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="8f651-213">Quick scan</span></span></li>
<li><span data-ttu-id="8f651-214">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="8f651-214">Customer scan</span></span></li>
</ul><span data-ttu-id="8f651-215">
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-216">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-217">Der Antivirenclient ist auf einen Fehler gestoßen, und die aktuelle Überprüfung wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="8f651-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="8f651-218">Die Überprüfung schlägt möglicherweise aufgrund eines clientseitigen Problems fehl.</span><span class="sxs-lookup"><span data-stu-id="8f651-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="8f651-219">Dieser Ereignisdatensatz enthält die Scan-ID, den Scantyp (Microsoft Defender Antivirus, Antispyware, Antischadsoftware), Scanparameter, den Benutzer, der die Überprüfung gestartet hat, den Fehlercode und eine Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="8f651-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="8f651-220">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8f651-221">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="8f651-222">Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8f651-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8f651-223">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-224">Ereignis-ID: 1006</span><span class="sxs-lookup"><span data-stu-id="8f651-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-225">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-227">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-227">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-228">
<b>Das Antischadsoftwaremodul hat Schadsoftware oder andere potenziell unerwünschte Software gefunden. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-229">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-230">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-231">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-232">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-232">Low</span></span></li>
<li><span data-ttu-id="8f651-233">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-233">Moderate</span></span></li>
<li><span data-ttu-id="8f651-234">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-234">High</span></span></li>
<li><span data-ttu-id="8f651-235">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-235">Severe</span></span></li>
</ul><span data-ttu-id="8f651-236">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-237">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-237">Unknown</span></span></li>
<li><span data-ttu-id="8f651-238">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-238">Local computer</span></span></li>
<li><span data-ttu-id="8f651-239">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-239">Network share</span></span></li>
<li><span data-ttu-id="8f651-240">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-240">Internet</span></span></li>
<li><span data-ttu-id="8f651-241">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-242">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-243">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-244">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-244">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-245">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-245">Generic</span></span></li>
<li><span data-ttu-id="8f651-246">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-246">Concrete</span></span></li>
<li><span data-ttu-id="8f651-247">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-248">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-249">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-249">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-250">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-250">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-251">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-252">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-253">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-254">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-255">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-256">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-257">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-258">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-259">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-260"></dt>
<dt>UAC-Status: &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-261">Ereigniskennung: 1007</span><span class="sxs-lookup"><span data-stu-id="8f651-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-262">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-264">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-264">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-265">
<b>Die Antischadsoftwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-266">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-267">Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8f651-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="8f651-268">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-269">
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; Bedrohungs-ID: &gt; </dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-270">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-270">Low</span></span></li>
<li><span data-ttu-id="8f651-271">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-271">Moderate</span></span></li>
<li><span data-ttu-id="8f651-272">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-272">High</span></span></li>
<li><span data-ttu-id="8f651-273">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-273">Severe</span></span></li>
</ul><span data-ttu-id="8f651-274">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt> Aktion: &lt; &gt; Aktion, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-275">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="8f651-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8f651-276">Quarantäne: Die Ressource wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="8f651-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8f651-277">Entfernen: Die Ressource wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8f651-278">Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="8f651-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8f651-279">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="8f651-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8f651-280">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-280">No action: No action</span></span></li>
<li><span data-ttu-id="8f651-281">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8f651-282">
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-283">Ereigniskennung: 1008</span><span class="sxs-lookup"><span data-stu-id="8f651-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-284">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-286">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-286">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-287">
<b>Die Antischadsoftwareplattform hat versucht, eine Aktion auszuführen, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen, die Aktion ist jedoch fehlgeschlagen.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-288">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-289">Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="8f651-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="8f651-290">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-291">
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; Bedrohungs-ID: &gt; </dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-292">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-292">Low</span></span></li>
<li><span data-ttu-id="8f651-293">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-293">Moderate</span></span></li>
<li><span data-ttu-id="8f651-294">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-294">High</span></span></li>
<li><span data-ttu-id="8f651-295">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-295">Severe</span></span></li>
</ul><span data-ttu-id="8f651-296">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadaktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-297">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="8f651-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8f651-298">Quarantäne: Die Ressource wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="8f651-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8f651-299">Entfernen: Die Ressource wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8f651-300">Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="8f651-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8f651-301">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="8f651-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8f651-302">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-302">No action: No action</span></span></li>
<li><span data-ttu-id="8f651-303">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8f651-304">
</dt>
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-305">Ereigniskennung: 1009</span><span class="sxs-lookup"><span data-stu-id="8f651-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-306">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-308">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-308">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-309">
<b>Die Antischadsoftwareplattform hat ein Element aus der Quarantäne wiederhergestellt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-310">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-311">Microsoft Defender Antivirus ein Element aus der Quarantäne wiederhergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="8f651-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="8f651-312">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-313">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-314">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-314">Low</span></span></li>
<li><span data-ttu-id="8f651-315">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-315">Moderate</span></span></li>
<li><span data-ttu-id="8f651-316">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-316">High</span></span></li>
<li><span data-ttu-id="8f651-317">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-317">Severe</span></span></li>
</ul><span data-ttu-id="8f651-318">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-319">Ereigniskennung: 1010</span><span class="sxs-lookup"><span data-stu-id="8f651-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-320">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-322">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-322">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-323">
<b>Die Antischadsoftwareplattform konnte ein Element nicht aus der Quarantäne wiederherstellen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-324">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-325">Microsoft Defender Antivirus beim Versuch, ein Element aus der Quarantäne wiederherzustellen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="8f651-326">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-327">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-328">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-328">Low</span></span></li>
<li><span data-ttu-id="8f651-329">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-329">Moderate</span></span></li>
<li><span data-ttu-id="8f651-330">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-330">High</span></span></li>
<li><span data-ttu-id="8f651-331">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-331">Severe</span></span></li>
</ul><span data-ttu-id="8f651-332">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-333">Ereignis-ID: 1011</span><span class="sxs-lookup"><span data-stu-id="8f651-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-334">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-336">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-336">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-337">
<b>Die Antischadsoftwareplattform hat ein Element aus der Quarantäne gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-338">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-339">Microsoft Defender Antivirus ein Element aus der Quarantäne gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="8f651-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="8f651-340">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-341">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-342">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-342">Low</span></span></li>
<li><span data-ttu-id="8f651-343">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-343">Moderate</span></span></li>
<li><span data-ttu-id="8f651-344">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-344">High</span></span></li>
<li><span data-ttu-id="8f651-345">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-345">Severe</span></span></li>
</ul><span data-ttu-id="8f651-346">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-347">Ereigniskennung: 1012</span><span class="sxs-lookup"><span data-stu-id="8f651-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-348">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-350">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-350">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-351">
<b>Die Antischadsoftwareplattform konnte ein Element nicht aus der Quarantäne löschen.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-352">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-353">Microsoft Defender Antivirus beim Versuch, ein Element aus der Quarantäne zu löschen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="8f651-354">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-355">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-356">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-356">Low</span></span></li>
<li><span data-ttu-id="8f651-357">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-357">Moderate</span></span></li>
<li><span data-ttu-id="8f651-358">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-358">High</span></span></li>
<li><span data-ttu-id="8f651-359">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-359">Severe</span></span></li>
</ul><span data-ttu-id="8f651-360">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-361">Ereignis-ID: 1013</span><span class="sxs-lookup"><span data-stu-id="8f651-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-362">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-364">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-364">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-365">
<b>Die Antischadsoftwareplattform hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software gelöscht.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-366">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-367">Microsoft Defender Antivirus hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software entfernt.</span><span class="sxs-lookup"><span data-stu-id="8f651-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8f651-368">
<dt>Uhrzeit: Die Uhrzeit, zu der das Ereignis aufgetreten ist, z. B. wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um die Wiederherstellungszeit oder die Infektionszeit handelt. Für diese bezeichnen wir sie ausdrücklich als Aktionszeit oder Erkennungszeit.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-369">Ereignis-ID: 1014</span><span class="sxs-lookup"><span data-stu-id="8f651-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-370">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-372">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="8f651-373">Die Antischadsoftwareplattform konnte den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="8f651-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-374">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-375">Microsoft Defender Antivirus beim Versuch, den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software zu entfernen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8f651-376">
<dt>Uhrzeit: Die Uhrzeit, zu der das Ereignis aufgetreten ist, z. B. wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um die Wiederherstellungszeit oder die Infektionszeit handelt. Für diese bezeichnen wir sie ausdrücklich als Aktionszeit oder Erkennungszeit.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-377">Ereignis-ID: 1015</span><span class="sxs-lookup"><span data-stu-id="8f651-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-378">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-380">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-380">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-381">
<b>Die Antischadsoftwareplattform hat verdächtiges Verhalten erkannt.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-382">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-383">Microsoft Defender Antivirus hat ein verdächtiges Verhalten erkannt.</span><span class="sxs-lookup"><span data-stu-id="8f651-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="8f651-384">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-385">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-386">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-386">Low</span></span></li>
<li><span data-ttu-id="8f651-387">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-387">Moderate</span></span></li>
<li><span data-ttu-id="8f651-388">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-388">High</span></span></li>
<li><span data-ttu-id="8f651-389">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-389">Severe</span></span></li>
</ul><span data-ttu-id="8f651-390">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-391">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-391">Unknown</span></span></li>
<li><span data-ttu-id="8f651-392">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-392">Local computer</span></span></li>
<li><span data-ttu-id="8f651-393">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-393">Network share</span></span></li>
<li><span data-ttu-id="8f651-394">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-394">Internet</span></span></li>
<li><span data-ttu-id="8f651-395">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-396">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-397">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-398">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-398">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-399">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-399">Generic</span></span></li>
<li><span data-ttu-id="8f651-400">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-400">Concrete</span></span></li>
<li><span data-ttu-id="8f651-401">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-402">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-403">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-403">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-404">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-404">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-405">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-406">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-407">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-408">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-409">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-410">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-411">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-412">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-413">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-414"></dt>
<dt>UAC-Status: &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signatur-ID:</dt>
<dt>Aufzählungsabgleichsschweregrad.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; &gt; Version</dt>
<dt>Fidelity Label:</dt>
<dt>Zieldateiname: &lt; &gt; Dateinamename der Datei.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-415">Ereignis-ID: 1116</span><span class="sxs-lookup"><span data-stu-id="8f651-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-416">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-418">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-418">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-419">
<b>Die Antischadsoftwareplattform hat Schadsoftware oder andere potenziell unerwünschte Software erkannt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-420">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-421">Microsoft Defender Antivirus Schadsoftware oder andere potenziell unerwünschte Software erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="8f651-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8f651-422">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-423">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-424">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-424">Low</span></span></li>
<li><span data-ttu-id="8f651-425">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-425">Moderate</span></span></li>
<li><span data-ttu-id="8f651-426">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-426">High</span></span></li>
<li><span data-ttu-id="8f651-427">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-427">Severe</span></span></li>
</ul><span data-ttu-id="8f651-428">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-429">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-429">Unknown</span></span></li>
<li><span data-ttu-id="8f651-430">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-430">Local computer</span></span></li>
<li><span data-ttu-id="8f651-431">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-431">Network share</span></span></li>
<li><span data-ttu-id="8f651-432">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-432">Internet</span></span></li>
<li><span data-ttu-id="8f651-433">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-434">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-435">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-436">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-436">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-437">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-437">Generic</span></span></li>
<li><span data-ttu-id="8f651-438">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-438">Concrete</span></span></li>
<li><span data-ttu-id="8f651-439">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-440">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-441">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-441">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-442">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-442">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-443">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-444">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-445">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-446">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-447">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-448">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-449">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-450">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-451">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-452"></dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-453">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-454">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-454">No action is required.</span></span> <span data-ttu-id="8f651-455">Microsoft Defender Antivirus können diese Bedrohung anhalten und routinemäßig maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="8f651-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="8f651-456">Wenn Sie die Bedrohung manuell entfernen möchten, klicken Sie auf der Microsoft Defender Antivirus Benutzeroberfläche auf <b>"Computer bereinigen".</b></span><span class="sxs-lookup"><span data-stu-id="8f651-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-457">Ereignis-ID: 1117</span><span class="sxs-lookup"><span data-stu-id="8f651-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-458">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-460">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-460">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-461">
<b>Die Antischadsoftwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-462">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-463">Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8f651-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8f651-464">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-465">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-466">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-466">Low</span></span></li>
<li><span data-ttu-id="8f651-467">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-467">Moderate</span></span></li>
<li><span data-ttu-id="8f651-468">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-468">High</span></span></li>
<li><span data-ttu-id="8f651-469">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-469">Severe</span></span></li>
</ul><span data-ttu-id="8f651-470">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-471">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-471">Unknown</span></span></li>
<li><span data-ttu-id="8f651-472">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-472">Local computer</span></span></li>
<li><span data-ttu-id="8f651-473">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-473">Network share</span></span></li>
<li><span data-ttu-id="8f651-474">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-474">Internet</span></span></li>
<li><span data-ttu-id="8f651-475">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-476">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-477">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-478">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-478">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-479">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-479">Generic</span></span></li>
<li><span data-ttu-id="8f651-480">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-480">Concrete</span></span></li>
<li><span data-ttu-id="8f651-481">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-482">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-483">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-483">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-484">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-484">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-485">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-486">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-487">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-488">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-489">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-490">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-491">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-492">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-493">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-494"></dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-495">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="8f651-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8f651-496">Quarantäne: Die Ressource wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="8f651-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8f651-497">Entfernen: Die Ressource wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8f651-498">Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="8f651-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8f651-499">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="8f651-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8f651-500">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-500">No action: No action</span></span></li>
<li><span data-ttu-id="8f651-501">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8f651-502">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; Version &gt; </dt> HINWEIS: Wenn Microsoft Defender Antivirus, Microsoft Security Essentials, Tool zum Entfernen bösartiger Software oder System Center Endpoint Protection eine Schadsoftware erkennt, werden die folgenden Systemeinstellungen und Dienste wiederhergestellt, die die Schadsoftware möglicherweise geändert hat:</span><span class="sxs-lookup"><span data-stu-id="8f651-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="8f651-503">Standardeinstellung für Internet Explorer oder Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8f651-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="8f651-504">Einstellungen für die Benutzerzugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="8f651-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="8f651-505">Chrome-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="8f651-505">Chrome settings</span></span></li>
<li><span data-ttu-id="8f651-506">Startsteuerungsdaten</span><span class="sxs-lookup"><span data-stu-id="8f651-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="8f651-507">Registrierungseinstellungen für Regedit und Task-Manager</span><span class="sxs-lookup"><span data-stu-id="8f651-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="8f651-508">Windows Update-, Background Intelligent Transfer Service- und Remoteprozedur-Aufrufdienst</span><span class="sxs-lookup"><span data-stu-id="8f651-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="8f651-509">Windows Betriebssystemdateien</span><span class="sxs-lookup"><span data-stu-id="8f651-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="8f651-510">Der obige Kontext gilt für die folgenden Client- und Serverversionen:</span><span class="sxs-lookup"><span data-stu-id="8f651-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="8f651-511">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-511">Operating system</span></span></th>
<th><span data-ttu-id="8f651-512">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="8f651-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-513">Clientbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="8f651-514">Windows Vista (Service Pack 1 oder Service Pack 2), Windows 7 und höher</span><span class="sxs-lookup"><span data-stu-id="8f651-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-515">Serverbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="8f651-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 und Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8f651-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-517">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-518">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-518">No action is necessary.</span></span> <span data-ttu-id="8f651-519">Microsoft Defender Antivirus eine Bedrohung entfernt oder isoliert.</span><span class="sxs-lookup"><span data-stu-id="8f651-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-520">Ereignis-ID: 1118</span><span class="sxs-lookup"><span data-stu-id="8f651-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-521">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-523">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-523">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-524">
<b>Die Antischadsoftwareplattform hat versucht, eine Aktion auszuführen, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen, die Aktion ist jedoch fehlgeschlagen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-525">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-526">Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software ein nicht schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8f651-527">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-528">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-529">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-529">Low</span></span></li>
<li><span data-ttu-id="8f651-530">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-530">Moderate</span></span></li>
<li><span data-ttu-id="8f651-531">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-531">High</span></span></li>
<li><span data-ttu-id="8f651-532">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-532">Severe</span></span></li>
</ul><span data-ttu-id="8f651-533">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-534">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-534">Unknown</span></span></li>
<li><span data-ttu-id="8f651-535">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-535">Local computer</span></span></li>
<li><span data-ttu-id="8f651-536">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-536">Network share</span></span></li>
<li><span data-ttu-id="8f651-537">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-537">Internet</span></span></li>
<li><span data-ttu-id="8f651-538">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-539">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-540">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-541">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-541">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-542">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-542">Generic</span></span></li>
<li><span data-ttu-id="8f651-543">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-543">Concrete</span></span></li>
<li><span data-ttu-id="8f651-544">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-545">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-546">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-546">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-547">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-547">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-548">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-549">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-550">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-551">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-552">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-553">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-554">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-555">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-556">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-557"></dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-558">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="8f651-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8f651-559">Quarantäne: Die Ressource wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="8f651-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8f651-560">Entfernen: Die Ressource wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8f651-561">Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="8f651-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8f651-562">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="8f651-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8f651-563">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-563">No action: No action</span></span></li>
<li><span data-ttu-id="8f651-564">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8f651-565">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-566">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-567">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-567">No action is necessary.</span></span> <span data-ttu-id="8f651-568">Microsoft Defender Antivirus konnte eine Aufgabe im Zusammenhang mit der Schadsoftwarebehebung nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="8f651-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="8f651-569">Dies ist kein schwerwiegender Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f651-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-570">Ereignis-ID: 1119</span><span class="sxs-lookup"><span data-stu-id="8f651-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-571">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-573">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-573">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-574">
<b>Die Antischadsoftwareplattform ist beim Versuch, Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software zu ergreifen, auf einen kritischen Fehler gestoßen. Die Ereignisnachricht enthält weitere Details.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-575">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-576">Microsoft Defender Antivirus beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software einen kritischen Fehler festgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="8f651-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8f651-577">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8f651-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="8f651-578">
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-579">Niedrig</span><span class="sxs-lookup"><span data-stu-id="8f651-579">Low</span></span></li>
<li><span data-ttu-id="8f651-580">Mittel</span><span class="sxs-lookup"><span data-stu-id="8f651-580">Moderate</span></span></li>
<li><span data-ttu-id="8f651-581">Hoch</span><span class="sxs-lookup"><span data-stu-id="8f651-581">High</span></span></li>
<li><span data-ttu-id="8f651-582">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="8f651-582">Severe</span></span></li>
</ul><span data-ttu-id="8f651-583">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-584">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="8f651-584">Unknown</span></span></li>
<li><span data-ttu-id="8f651-585">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="8f651-585">Local computer</span></span></li>
<li><span data-ttu-id="8f651-586">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-586">Network share</span></span></li>
<li><span data-ttu-id="8f651-587">Internet</span><span class="sxs-lookup"><span data-stu-id="8f651-587">Internet</span></span></li>
<li><span data-ttu-id="8f651-588">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="8f651-589">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="8f651-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8f651-590">
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-591">Heuristik</span><span class="sxs-lookup"><span data-stu-id="8f651-591">Heuristics</span></span></li>
<li><span data-ttu-id="8f651-592">Generic</span><span class="sxs-lookup"><span data-stu-id="8f651-592">Generic</span></span></li>
<li><span data-ttu-id="8f651-593">Konkrete</span><span class="sxs-lookup"><span data-stu-id="8f651-593">Concrete</span></span></li>
<li><span data-ttu-id="8f651-594">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="8f651-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8f651-595">
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f651-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8f651-596">Benutzer: benutzerinitiierte</span><span class="sxs-lookup"><span data-stu-id="8f651-596">User: user initiated</span></span></li>
<li><span data-ttu-id="8f651-597">System: systeminitiiertes System</span><span class="sxs-lookup"><span data-stu-id="8f651-597">System: system initiated</span></span></li>
<li><span data-ttu-id="8f651-598">Echtzeit: In Echtzeit initiierte Komponente</span><span class="sxs-lookup"><span data-stu-id="8f651-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8f651-599">IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8f651-600">NIS: Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8f651-601">IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="8f651-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8f651-602">Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM).</span><span class="sxs-lookup"><span data-stu-id="8f651-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8f651-603">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8f651-604">Remotenachweis</span><span class="sxs-lookup"><span data-stu-id="8f651-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="8f651-605">Antischadsoftware-Scanschnittstelle (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8f651-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8f651-606">Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8f651-607"></dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8f651-608">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="8f651-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8f651-609">Quarantäne: Die Ressource wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="8f651-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8f651-610">Entfernen: Die Ressource wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8f651-611">Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="8f651-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8f651-612">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="8f651-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8f651-613">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-613">No action: No action</span></span></li>
<li><span data-ttu-id="8f651-614">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8f651-615">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-616">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-617">Der Microsoft Defender Antivirus-Client ist aufgrund kritischer Probleme auf diesen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="8f651-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="8f651-618">Der Endpunkt ist möglicherweise nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="8f651-618">The endpoint might not be protected.</span></span> <span data-ttu-id="8f651-619">Überprüfen Sie die Fehlerbeschreibung, und führen Sie dann die entsprechenden Schritte <b>für die Benutzeraktion</b> unten aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="8f651-620">Aktion</span><span class="sxs-lookup"><span data-stu-id="8f651-620">Action</span></span></th>
<th><span data-ttu-id="8f651-621">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8f651-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8f651-622">
<b>Entfernen</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="8f651-623">Aktualisieren Sie die Definitionen, und stellen Sie sicher, dass die Entfernung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8f651-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8f651-624">
<b>Sauber</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="8f651-625">Aktualisieren Sie die Definitionen, und überprüfen Sie dann, ob die Korrektur erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8f651-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8f651-626">
<b>Quarantäne</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="8f651-627">Aktualisieren Sie die Definitionen, und stellen Sie sicher, dass der Benutzer über die Berechtigung für den Zugriff auf die erforderlichen Ressourcen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f651-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8f651-628">
<b>Ermöglichen</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="8f651-629">Stellen Sie sicher, dass der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f651-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="8f651-630">Wenn dieses Ereignis weiterhin besteht:</span><span class="sxs-lookup"><span data-stu-id="8f651-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="8f651-631">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="8f651-632">Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8f651-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8f651-633">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-634">Ereignis-ID: 1120</span><span class="sxs-lookup"><span data-stu-id="8f651-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-635">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-637">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-637">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-638">
<b>Microsoft Defender Antivirus hat die Hashes für eine Bedrohungsressource abgeleitet.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-639">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-640">Microsoft Defender Antivirus Client ist in einem fehlerfreien Zustand ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8f651-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="8f651-641">
<dt>Aktuelle Plattformversion: &lt; Threat &gt; </dt>Resource Path der aktuellen
<dt>Plattformversion: &lt; &gt; Pfadhashes:</dt>
<dt> &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="8f651-642"><b>Hinweis: Dieses Ereignis wird nur protokolliert, wenn die folgende Richtlinie festgelegt ist: <b>ThreatFileHashLogging unsigned</b>.</span><span class="sxs-lookup"><span data-stu-id="8f651-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-643">Ereignis-ID: 1150</span><span class="sxs-lookup"><span data-stu-id="8f651-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-644">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-646">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-646">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-647">
<b>Wenn Ihre Antischadsoftwareplattform den Status an eine Überwachungsplattform meldet, gibt dieses Ereignis an, dass die Antischadsoftwareplattform ausgeführt wird und sich in einem fehlerfreien Zustand befindet. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-648">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-649">Microsoft Defender Antivirus Client ist in einem fehlerfreien Zustand ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8f651-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="8f651-650">
<dt>Plattformversion: &lt; Signaturversion &gt; der aktuellen Plattformversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-651">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-652">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-652">No action is necessary.</span></span> <span data-ttu-id="8f651-653">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="8f651-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8f651-654">Dieses Ereignis wird stündlich gemeldet.</span><span class="sxs-lookup"><span data-stu-id="8f651-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="8f651-655">Ereignis-ID: 1151</span><span class="sxs-lookup"><span data-stu-id="8f651-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-656">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-658">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-658">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-659">
<b>Endpoint Protection Clientintegritätsbericht (Uhrzeit in UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-660">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-661">Antivirus-Clientintegritätsbericht.</span><span class="sxs-lookup"><span data-stu-id="8f651-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="8f651-662">
<dt>Plattformversion: &lt; Aktuelle Version &gt; des Plattformversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; &gt; Version</dt>des Network Realtime Inspection-Moduls: Version der Antivirus-Signaturversion des
<dt> &lt; Network Realtime &gt; Inspection-Moduls:</dt>
<dt> &lt; &gt; Antivirensignaturversion</dt>
<dt>Antispyware-Signaturversion: &lt; Antispyware-Signaturversion &gt; </dt>der Network Realtime Inspection-Signaturversion: RTP-Status der
<dt> &lt; Netzwerk-Echtzeitüberprüfungssignaturversion: &gt; </dt>Echtzeit Protection State
<dt> &lt; &gt; (Enabled or Disabled)</dt>
<dt>OA &lt; state: On Access state &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt; IE Downloads and Outlook Express Attachments state &gt; (Enabled or Disabled)</dt>BM
<dt>state: Behavior Monitoring state &lt; &gt; (Enabled or Disabled)</dt>Antivirus signature
<dt>age: Antivirus signature &lt; age: Antivirus signature age &gt;(in Tagen)</dt>Alter der
<dt>Antispyware-Signatur: Alter der &lt; Antispyware-Signatur &gt; (in Tagen)</dt>
<dt>Letztes Schnelle &lt; scanalter: Letztes Schnelle scanalter &gt; (in Tagen)</dt>
<dt>Letztes vollständiges &lt; Scanalter: Letztes vollständiges Scanalter &gt; (in Tagen)</dt>
<dt>Erstellungszeit der Antivirus-Signatur: ? &lt; &gt;</dt>Zeit für die Erstellung von
<dt>Antispyware-Signaturen durch Antivirus: ? &lt; Erstellungszeit der &gt; Antispyware-Signatur</dt>
<dt>zum Zeitpunkt des letzten Schnellscanstarts: ? &lt; Startzeit des &gt; letzten Schnellscans</dt>
<dt>Letztes Ende des Schnellscans: ? &lt; Letzte &gt; Schnellscanendzeit</dt>
<dt>letzte Schnellscanquelle: Letzte &lt; Schnellscanquelle &gt; (0 = Scan wurde nicht ausgeführt&#39;, 1 = vom Benutzer initiiert, 2 = vom System initiiert)</dt>
<dt>Letzte Startzeit des vollständigen Scans: ? &lt; Startzeit &gt; des letzten vollständigen Scans</dt>
<dt>Letzte Vollständige Scan-Endzeit: ? &lt; Letzte vollständige &gt; Scanendzeit</dt>letzte vollständige
<dt>Scanquelle: Letzte Quelle des &lt; vollständigen Scans &gt; (0 = Scan wurde nicht ausgeführt&#39;, 1 = vom Benutzer initiiert, 2 = vom System initiiert)</dt> 
<dt> Produktstatus: Für interne Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8f651-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="8f651-663">
<th colspan="2">Ereignis-ID: 2000</span><span class="sxs-lookup"><span data-stu-id="8f651-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-664">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-666">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-666">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-667">
<b>Die Antischadsoftwaredefinitionen wurden erfolgreich aktualisiert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-668">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-669">Die Antivirensignaturversion wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="8f651-670">
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Vorherige Signaturversion: Signaturtyp der &lt; vorherigen &gt; Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8f651-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-671">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-672">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-673">Antimalware</span></span></li>
<li><span data-ttu-id="8f651-674">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-675">
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder "Full" oder "Delta".</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Aktuelle &gt; Modulversion</dt>
<dt>des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>Vorherige
<dt>Modulversion: &lt; Vorherige Modulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-676">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-677">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-677">No action is necessary.</span></span> <span data-ttu-id="8f651-678">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="8f651-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8f651-679">Dieses Ereignis wird gemeldet, wenn Signaturen erfolgreich aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-680">Ereignis-ID: 2001</span><span class="sxs-lookup"><span data-stu-id="8f651-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-681">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-683">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-683">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-684">
<b>Das Update zur Sicherheitsintelligenz ist fehlgeschlagen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-685">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-686">Microsoft Defender Antivirus beim Versuch, Signaturen zu aktualisieren, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="8f651-687">
<dt>Neue Security Intelligence-Version: &lt; Neue &gt; Versionsnummer</dt>
<dt>Frühere Security Intelligence-Version: &lt; Updatequelle der vorherigen &gt; Version:</dt> 
<dt> &lt; &gt; Updatequelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-688">Security Intelligence Update-Ordner</span><span class="sxs-lookup"><span data-stu-id="8f651-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="8f651-689">Interner Security Intelligence Update-Server</span><span class="sxs-lookup"><span data-stu-id="8f651-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="8f651-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="8f651-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="8f651-691">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="8f651-691">File share</span></span></li>
<li><span data-ttu-id="8f651-692">Microsoft Center zum Schutz vor Malware (MMPC)</span><span class="sxs-lookup"><span data-stu-id="8f651-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="8f651-693">
</dt>
<dt>Updatephase: &lt; &gt; Updatephase, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-694">Suche</span><span class="sxs-lookup"><span data-stu-id="8f651-694">Search</span></span></li>
<li><span data-ttu-id="8f651-695">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="8f651-695">Download</span></span></li>
<li><span data-ttu-id="8f651-696">Installieren</span><span class="sxs-lookup"><span data-stu-id="8f651-696">Install</span></span></li>
</ul><span data-ttu-id="8f651-697">
</dt>
<dt>Quellpfad: Dateifreigabename für Universal Naming Convention (UNC), Servername für Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8f651-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-698">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-699">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-700">Antimalware</span></span></li>
<li><span data-ttu-id="8f651-701">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-702">
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder "Full" oder "Delta".</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-703">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-704">Dieser Fehler tritt auf, wenn beim Aktualisieren von Definitionen ein Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="8f651-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="8f651-705">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8f651-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="8f651-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="8f651-707">Überprüfen Sie die Einträge in der Datei "%Windir%\WindowsUpdate.log", um weitere Informationen zu diesem Fehler zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="8f651-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="8f651-708">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-709">Ereignis-ID: 2002</span><span class="sxs-lookup"><span data-stu-id="8f651-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-710">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-712">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-712">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-713">
<b>Das Antischadsoftwaremodul wurde erfolgreich aktualisiert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-714">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-715">Microsoft Defender Antivirus Modulversion wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="8f651-716">
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt>
<dt>Vorherige Modulversion: Modultyp der &lt; vorherigen &gt; Modulversion:</dt>
<dt> &lt; &gt; Modultyp, entweder Antischadsoftwaremodul oder Netzwerküberprüfungssystemmodul.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-717">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-718">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-718">No action is necessary.</span></span> <span data-ttu-id="8f651-719">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="8f651-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8f651-720">Dieses Ereignis wird gemeldet, wenn das Antischadsoftwaremodul erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8f651-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-721">Ereignis-ID: 2003</span><span class="sxs-lookup"><span data-stu-id="8f651-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-722">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-724">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-724">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-725">
<b>Fehler beim Update des Antischadsoftwaremoduls. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-726">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-727">Microsoft Defender Antivirus beim Versuch, das Modul zu aktualisieren, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="8f651-728">
<dt>Neue Modulversion:</dt>
<dt>Frühere Modulversion: Modultyp der &lt; vorherigen &gt; Modulversion:</dt>
<dt> &lt; Modultyp, &gt; antischadsoftwaremodul oder Netzwerküberprüfungssystemmodul.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-729">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-730">Fehler bei der Microsoft Defender Antivirus Clientaktualisierung.</span><span class="sxs-lookup"><span data-stu-id="8f651-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="8f651-731">Dieses Ereignis tritt auf, wenn der Client sich selbst nicht aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="8f651-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="8f651-732">Dieses Ereignis ist in der Regel auf eine Unterbrechung der Netzwerkkonnektivität während eines Updates zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="8f651-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="8f651-733">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8f651-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="8f651-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="8f651-735">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-736">Ereignis-ID: 2004</span><span class="sxs-lookup"><span data-stu-id="8f651-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-737">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-739">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-739">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-740">
<b>Beim Laden von Antischadsoftwaredefinitionen ist ein Problem aufgetreten. Das Antischadsoftwaremodul versucht, den letzten bekannten ordnungsgemäßen Satz von Definitionen zu laden.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-741">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-742">Microsoft Defender Antivirus beim Versuch, Signaturen zu laden, einen Fehler aufgetreten ist, und versucht, einen bekannten Satz von Signaturen wiederhergestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="8f651-743">
<dt>Versuchte Signaturen:</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-744">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-745">Der Microsoft Defender Antivirus-Client hat versucht, die neueste Definitionsdatei herunterzuladen und zu installieren, und es ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="8f651-746">Dieser Fehler kann auftreten, wenn der Client beim Laden der Definitionen auf einen Fehler stößt oder wenn die Datei beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="8f651-747">Microsoft Defender Antivirus versuchen, zu einem bekannten Satz von Definitionen zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="8f651-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="8f651-748">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8f651-749">Starten Sie den Computer neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="8f651-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="8f651-750">Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence Website</a>herunter.</span><span class="sxs-lookup"><span data-stu-id="8f651-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="8f651-751">Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="8f651-752">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-753">Ereignis-ID: 2005</span><span class="sxs-lookup"><span data-stu-id="8f651-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-754">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-756">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-756">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-757">
<b>Das Antischadsoftwaremodul konnte nicht geladen werden, da die Antischadsoftwareplattform veraltet ist. Die Antischadsoftwareplattform lädt das zuletzt als gut bekannte Antischadsoftwaremodul und versucht, es zu aktualisieren.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-758">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-759">Microsoft Defender Antivirus konnte das Antischadsoftwaremodul nicht laden, da die aktuelle Plattformversion nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="8f651-760">Microsoft Defender Antivirus kehren zum letzten als gut bekannten Modul zurück, und es wird versucht, ein Plattformupdate auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8f651-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="8f651-761">
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-762">Ereignis-ID: 2006</span><span class="sxs-lookup"><span data-stu-id="8f651-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-763">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-765">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-765">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-766">
<b>Das Plattformupdate ist fehlgeschlagen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-767">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-768">Microsoft Defender Antivirus beim Versuch, die Plattform zu aktualisieren, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="8f651-769">
<dt>Aktuelle Plattformversion: &lt; Fehlercode &gt; der aktuellen Plattformversion:</dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-770">Ereignis-ID: 2007</span><span class="sxs-lookup"><span data-stu-id="8f651-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-771">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-773">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-773">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-774">
<b>Die Plattform ist in Kürze veraltet. Laden Sie die neueste Plattform herunter, um den Schutz auf dem neuesten Stand zu halten.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-775">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-776">Microsoft Defender Antivirus benötigen in Kürze eine neuere Plattformversion, um zukünftige Versionen des Antischadsoftwaremoduls zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8f651-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="8f651-777">Laden Sie die neueste Microsoft Defender Antivirus-Plattform herunter, um das beste verfügbare Schutzniveau aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="8f651-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="8f651-778">
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-779">Ereignis-ID: 2010</span><span class="sxs-lookup"><span data-stu-id="8f651-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-780">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-782">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-782">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-783">
<b>Das Antischadsoftwaremodul hat den Dienst für dynamische Signaturen verwendet, um zusätzliche Definitionen abzurufen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-784">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-785">Microsoft Defender Antivirus den <i>Dienst für dynamische Signaturen</i> verwendet, um zusätzliche Signaturen abzurufen, um Ihren Computer zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8f651-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="8f651-786">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8f651-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-787">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-788">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-789">Antimalware</span></span></li>
<li><span data-ttu-id="8f651-790">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-791">
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-792">Version</span><span class="sxs-lookup"><span data-stu-id="8f651-792">Version</span></span></li>
<li><span data-ttu-id="8f651-793">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-793">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-794">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-794">No limit</span></span></li>
<li><span data-ttu-id="8f651-795">Dauer</span><span class="sxs-lookup"><span data-stu-id="8f651-795">Duration</span></span></li>
</ul><span data-ttu-id="8f651-796">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:</span><span class="sxs-lookup"><span data-stu-id="8f651-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-797">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="8f651-797">VDM version</span></span></li>
<li><span data-ttu-id="8f651-798">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-798">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-799">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-799">No limit</span></span></li>
</ul><span data-ttu-id="8f651-800">
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-801">Ereigniskennung: 2011</span><span class="sxs-lookup"><span data-stu-id="8f651-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-802">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-804">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-804">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-805">
<b>Der Dienst für dynamische Signaturen hat die veralteten dynamischen Definitionen gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-806">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-807">Microsoft Defender Antivirus <i>den Dienst für dynamische Signaturen</i> verwendet, um veraltete Signaturen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8f651-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="8f651-808">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8f651-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-809">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-810">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-811">Antimalware</span></span></li>
<li><span data-ttu-id="8f651-812">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-813">
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp, &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-814">Version</span><span class="sxs-lookup"><span data-stu-id="8f651-814">Version</span></span></li>
<li><span data-ttu-id="8f651-815">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-815">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-816">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-816">No limit</span></span></li>
<li><span data-ttu-id="8f651-817">Dauer</span><span class="sxs-lookup"><span data-stu-id="8f651-817">Duration</span></span></li>
</ul><span data-ttu-id="8f651-818">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:</span><span class="sxs-lookup"><span data-stu-id="8f651-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-819">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="8f651-819">VDM version</span></span></li>
<li><span data-ttu-id="8f651-820">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-820">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-821">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-821">No limit</span></span></li>
</ul><span data-ttu-id="8f651-822">
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-823">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-824">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f651-824">No action is necessary.</span></span> <span data-ttu-id="8f651-825">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="8f651-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8f651-826">Dieses Ereignis wird gemeldet, wenn der Dienst für dynamische Signaturen veraltete dynamische Definitionen erfolgreich löscht.</span><span class="sxs-lookup"><span data-stu-id="8f651-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-827">Ereignis-ID: 2012</span><span class="sxs-lookup"><span data-stu-id="8f651-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-828">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-830">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-830">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-831">
<b>Beim Versuch, den Dienst für dynamische Signaturen zu verwenden, ist beim Antischadsoftwaremodul ein Fehler aufgetreten. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-832">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-833">Microsoft Defender Antivirus beim Versuch, den Dienst für <i>dynamische Signaturen</i>zu verwenden, ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="8f651-834">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8f651-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8f651-835">Antivirus</span></span></li>
<li><span data-ttu-id="8f651-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8f651-836">Antispyware</span></span></li>
<li><span data-ttu-id="8f651-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8f651-837">Antimalware</span></span></li>
<li><span data-ttu-id="8f651-838">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-839">
</dt>
<dt>Aktuelle Modulversion: &lt; Fehlercode &gt; der aktuellen Modulversion:</dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt> Dynamischer Signaturtyp: &lt; Dynamischer &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-840">Version</span><span class="sxs-lookup"><span data-stu-id="8f651-840">Version</span></span></li>
<li><span data-ttu-id="8f651-841">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-841">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-842">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-842">No limit</span></span></li>
<li><span data-ttu-id="8f651-843">Dauer</span><span class="sxs-lookup"><span data-stu-id="8f651-843">Duration</span></span></li>
</ul><span data-ttu-id="8f651-844">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:</span><span class="sxs-lookup"><span data-stu-id="8f651-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-845">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="8f651-845">VDM version</span></span></li>
<li><span data-ttu-id="8f651-846">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="8f651-846">Timestamp</span></span></li>
<li><span data-ttu-id="8f651-847">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="8f651-847">No limit</span></span></li>
</ul><span data-ttu-id="8f651-848">
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-849">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-850">Überprüfen Sie ihre Internetkonnektivitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="8f651-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-851">Ereignis-ID: 2013</span><span class="sxs-lookup"><span data-stu-id="8f651-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-852">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-854">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-854">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-855">
<b>Der Dienst für dynamische Signaturen hat alle dynamischen Definitionen gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-856">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-857">Microsoft Defender Antivirus alle Signaturen <i>des Diensts für dynamische Signaturen</i> verworfen.</span><span class="sxs-lookup"><span data-stu-id="8f651-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="8f651-858">
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-859">Ereignis-ID: 2020</span><span class="sxs-lookup"><span data-stu-id="8f651-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-860">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-862">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-862">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-863">
<b>Das Antischadsoftwaremodul hat eine fehlerfreie Datei heruntergeladen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-864">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-865">Microsoft Defender Antivirus eine bereinigte Datei heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="8f651-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="8f651-866">
<dt>Dateiname: &lt; Dateiname &gt; der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Aktuelle Modulversion: Aktuelle &lt; Modulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-867">Ereignis-ID: 2021</span><span class="sxs-lookup"><span data-stu-id="8f651-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-868">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-870">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-870">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-871">
<b>Das Antischadsoftwaremodul konnte keine fehlerfreie Datei herunterladen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-872">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-873">Microsoft Defender Antivirus beim Versuch, eine fehlerfreie Datei herunterzuladen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="8f651-874">
<dt>Dateiname: &lt; Dateiname &gt; der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle &gt; Signaturversion</dt>
<dt>Aktuelle Modulversion: Fehlercode der &lt; aktuellen Modulversion: &gt; </dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-875">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-876">Überprüfen Sie ihre Internetkonnektivitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="8f651-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="8f651-877">Beim Microsoft Defender Antivirus Client ist beim Verwenden des Diensts für dynamische Signaturen ein Fehler aufgetreten, um die neuesten Definitionen für eine bestimmte Bedrohung herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="8f651-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="8f651-878">Dieser Fehler wird wahrscheinlich durch ein Netzwerkverbindungsproblem verursacht.</span><span class="sxs-lookup"><span data-stu-id="8f651-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-879">Ereignis-ID: 2030</span><span class="sxs-lookup"><span data-stu-id="8f651-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-880">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-882">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-882">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-883">
<b>Das Antischadsoftwaremodul wurde heruntergeladen und ist so konfiguriert, dass es beim nächsten Systemneustart offline ausgeführt wird.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-884">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-885">Microsoft Defender Antivirus offline Antivirus heruntergeladen und konfiguriert, um beim nächsten Neustart ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-886">Ereignis-ID: 2031</span><span class="sxs-lookup"><span data-stu-id="8f651-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-887">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-889">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-889">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-890">
<b>Das Antischadsoftwaremodul konnte einen Offlinescan nicht herunterladen und konfigurieren.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-891">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-892">Microsoft Defender Antivirus beim Versuch, Offline-Antivirus herunterzuladen und zu konfigurieren, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f651-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="8f651-893">
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-894">Ereignis-ID: 2040</span><span class="sxs-lookup"><span data-stu-id="8f651-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-895">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-897">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-897">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-898">
<b>Die Antischadsoftwareunterstützung für diese Betriebssystemversion wird bald beendet. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-899">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-900">Die Unterstützung für Ihr Betriebssystem läuft in Kürze ab.</span><span class="sxs-lookup"><span data-stu-id="8f651-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="8f651-901">Das Ausführen von Microsoft Defender Antivirus auf einem nicht unterstützten Betriebssystem ist keine angemessene Lösung zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="8f651-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-902">Ereigniskennung: 2041</span><span class="sxs-lookup"><span data-stu-id="8f651-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-903">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-905">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-905">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-906">
<b>Die Antischadsoftwareunterstützung für dieses Betriebssystem wurde beendet. Sie müssen das Betriebssystem aktualisieren, um den Support fortzusetzen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-907">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-908">Die Unterstützung für Ihr Betriebssystem ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="8f651-908">The support for your operating system has expired.</span></span> <span data-ttu-id="8f651-909">Das Ausführen von Microsoft Defender Antivirus auf einem nicht unterstützten Betriebssystem ist keine angemessene Lösung zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="8f651-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-910">Ereignis-ID: 2042</span><span class="sxs-lookup"><span data-stu-id="8f651-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-911">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-913">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-913">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-914">
<b>Das Antischadsoftwaremodul unterstützt dieses Betriebssystem nicht mehr und schützt Ihr System nicht mehr vor Schadsoftware. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-915">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-916">Die Unterstützung für Ihr Betriebssystem ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="8f651-916">The support for your operating system has expired.</span></span> <span data-ttu-id="8f651-917">Microsoft Defender Antivirus wird auf Ihrem Betriebssystem nicht mehr unterstützt, funktioniert nicht mehr und schützt nicht mehr vor Schadsoftwarebedrohungen.</span><span class="sxs-lookup"><span data-stu-id="8f651-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-918">Ereignis-ID: 3002</span><span class="sxs-lookup"><span data-stu-id="8f651-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-919">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-921">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-921">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-922">
<b>Beim Echtzeitschutz ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-923">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-924">Microsoft Defender Antivirus Real-Time Protection-Feature ist ein Fehler aufgetreten und fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="8f651-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="8f651-925">
<dt>Feature: &lt; &gt; Feature, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-926">Bei Zugriff</span><span class="sxs-lookup"><span data-stu-id="8f651-926">On Access</span></span></li>
<li><span data-ttu-id="8f651-927">Internet Explorer-Downloads und Microsoft Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8f651-928">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="8f651-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8f651-929">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-930">
</dt>
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus Echtzeitschutz ein Feature neu gestartet hat.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-931">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-932">Starten Sie das System neu, und führen Sie dann einen vollständigen Scan durch, da es&#39;, dass das System für einige Zeit nicht geschützt war.</span><span class="sxs-lookup"><span data-stu-id="8f651-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="8f651-933">Das Echtzeitschutzfeature des Microsoft Defender Antivirus-Clients&#39;ist auf einen Fehler gestoßen, da einer der Dienste nicht gestartet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8f651-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="8f651-934">Wenn auf sie eine 3007-Ereignis-ID folgt, war der Fehler temporär, und der Antischadsoftwareclient wurde nach dem Fehler wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8f651-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-935">Ereignis-ID: 3007</span><span class="sxs-lookup"><span data-stu-id="8f651-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-936">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-938">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-938">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-939">
<b>Echtzeitschutz, der nach einem Fehler wiederhergestellt wurde. Es wird empfohlen, eine vollständige Systemüberprüfung auszuführen, wenn dieser Fehler angezeigt wird. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-940">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-941">Microsoft Defender Antivirus Der Echtzeitschutz hat ein Feature neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="8f651-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="8f651-942">Es wird empfohlen, dass Sie einen vollständigen Systemscan ausführen, um Elemente zu erkennen, die während des Ausfalls dieses Agents möglicherweise übersehen wurden.</span><span class="sxs-lookup"><span data-stu-id="8f651-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="8f651-943">
<dt>Feature: &lt; &gt; Feature, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-944">Bei Zugriff</span><span class="sxs-lookup"><span data-stu-id="8f651-944">On Access</span></span></li>
<li><span data-ttu-id="8f651-945">IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8f651-946">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="8f651-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8f651-947">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-948">
</dt>
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus Echtzeitschutz ein Feature neu gestartet hat.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-949">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-950">Das Echtzeitschutzfeature wurde neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="8f651-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="8f651-951">Wenn dieses Ereignis erneut auftritt, wenden Sie sich an <a href="https://go.microsoft.com/fwlink/?LinkId=215491">den technischen Support von Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="8f651-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-952">Ereignis-ID: 5000</span><span class="sxs-lookup"><span data-stu-id="8f651-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-953">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-955">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-955">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-956">
<b>Der Echtzeitschutz ist aktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-957">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-958">Microsoft Defender Antivirus Echtzeitschutzüberprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-959">Ereignis-ID: 5001</span><span class="sxs-lookup"><span data-stu-id="8f651-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-960">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-962">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-962">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-963">
<b>Der Echtzeitschutz ist deaktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-964">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-965">Microsoft Defender Antivirus Echtzeitschutzüberprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-966">Ereignis-ID: 5004</span><span class="sxs-lookup"><span data-stu-id="8f651-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-967">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-969">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-969">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-970">
<b>Die Echtzeitschutzkonfiguration wurde geändert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-971">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-972">Microsoft Defender Antivirus Konfiguration der Echtzeitschutzfunktion wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="8f651-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="8f651-973">
<dt>Feature: &lt; &gt; Feature, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f651-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8f651-974">Bei Zugriff</span><span class="sxs-lookup"><span data-stu-id="8f651-974">On Access</span></span></li>
<li><span data-ttu-id="8f651-975">IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="8f651-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8f651-976">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="8f651-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8f651-977">Netzwerküberprüfungssystem</span><span class="sxs-lookup"><span data-stu-id="8f651-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8f651-978">
</dt>
<dt>Konfiguration: </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-979">Ereignis-ID: 5007</span><span class="sxs-lookup"><span data-stu-id="8f651-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-980">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-982">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-982">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-983">
<b>Die Konfiguration der Antischadsoftwareplattform wurde geändert.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-984">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-985">Microsoft Defender Antivirus Konfiguration wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="8f651-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="8f651-986">Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.</span><span class="sxs-lookup"><span data-stu-id="8f651-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="8f651-987">
<dt>Alter Wert: &lt; Alter Wert Zahl &gt; Alter Antivirus-Konfigurationswert.</dt> 
<dt>Neuer Wert: &lt; New value number &gt; New antivirus configuration value.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-988">Ereignis-ID: 5008</span><span class="sxs-lookup"><span data-stu-id="8f651-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-989">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-991">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-991">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-992">
<b>Beim Antischadsoftwaremodul ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-993">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-994">Microsoft Defender Antivirus Modul wurde aufgrund eines unerwarteten Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="8f651-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="8f651-995">
<dt>Fehlertyp: &lt; &gt;Fehlertyp, z. B.: Crash or Hang</dt>Exception
<dt>Code: Error &lt; code &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-996">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-997">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="8f651-998">Versuchen Sie, den Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="8f651-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="8f651-999">Geben Sie für Antischadsoftware, Antivirus und Spyware an einer Eingabeaufforderung mit erhöhten Rechten <b>"net stop msmpsvc"</b>ein, und geben Sie dann <b>"net start msmpsvc"</b> ein, um das Antischadsoftwaremodul neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="8f651-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="8f651-1000">Geben Sie für das <i>Netzwerküberprüfungssystem</i>an einer Eingabeaufforderung mit erhöhten Rechten <b>"net start nissrv"</b>und dann <b>"net start nissrv"</b> ein, um das <i>Netzwerküberprüfungssystem-Modul</i> mithilfe der NiSSRV.exe-Datei neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="8f651-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="8f651-1001">Wenn auf die gleiche Weise ein Fehler auftritt, suchen Sie nach dem Fehlercode, indem Sie auf die <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite</a> zugreifen und die Fehlernummer in das <b>Suchfeld</b> eingeben, und wenden Sie sich an den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="8f651-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1002">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="8f651-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1003">Das Microsoft Defender Antivirus Clientmodul wurde aufgrund eines unerwarteten Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="8f651-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="8f651-1004">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="8f651-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8f651-1005">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="8f651-1006">Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8f651-1007">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="8f651-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1008">Ereignis-ID: 5009</span><span class="sxs-lookup"><span data-stu-id="8f651-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1009">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1011">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1012">
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist aktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1013">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1014">Microsoft Defender Antivirus Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1015">Ereignis-ID: 5010</span><span class="sxs-lookup"><span data-stu-id="8f651-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1016">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1018">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1019">
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1020">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1021">Microsoft Defender Antivirus Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1022">Ereignis-ID: 5011</span><span class="sxs-lookup"><span data-stu-id="8f651-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1023">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1025">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1026">
<b>Die Virenüberprüfung ist aktiviert.</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1027">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1028">Microsoft Defender Antivirus Virenüberprüfung wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1029">Ereignis-ID: 5012</span><span class="sxs-lookup"><span data-stu-id="8f651-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1030">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1032">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1033">
<b>Die Virenüberprüfung ist deaktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1034">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1035">Microsoft Defender Antivirus Virenüberprüfung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1036">Ereignis-ID: 5100</span><span class="sxs-lookup"><span data-stu-id="8f651-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1037">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1039">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1040">
<b>Die Antischadsoftwareplattform läuft in Kürze ab. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1041">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1042">Microsoft Defender Antivirus hat eine Nachfrist begonnen und läuft bald ab.</span><span class="sxs-lookup"><span data-stu-id="8f651-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="8f651-1043">Nach ablaufen deaktiviert dieses Programm den Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software.</span><span class="sxs-lookup"><span data-stu-id="8f651-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8f651-1044">
<dt>Ablaufgrund: Der Grund, warum Microsoft Defender Antivirus abläuft.</dt> 
<dt>Ablaufdatum: Das Datum Microsoft Defender Antivirus abläuft.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1045">Ereignis-ID: 5101</span><span class="sxs-lookup"><span data-stu-id="8f651-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8f651-1046">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="8f651-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8f651-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1048">Meldung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="8f651-1049">
<b>Die Antischadsoftwareplattform ist abgelaufen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1050">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="8f651-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="8f651-1051">Microsoft Defender Antivirus Karenzzeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="8f651-1052">Der Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="8f651-1053">
<dt>Ablaufgrund:</dt>
<dt>Ablaufdatum: </dt> 
<dt>Fehlercode: &lt; Fehlercode-Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="8f651-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivirus Clientfehlercodes Wenn Microsoft Defender Antivirus Probleme auftreten, erhalten Sie in der Regel einen Fehlercode, der Ihnen bei der Problembehandlung hilft.</span><span class="sxs-lookup"><span data-stu-id="8f651-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="8f651-1055">In den meisten Fällen bedeutet ein Fehler, dass beim Installieren eines Updates ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="8f651-1056">Dieser Abschnitt enthält die folgenden Informationen zu Microsoft Defender Antivirus Clientfehlern.</span><span class="sxs-lookup"><span data-stu-id="8f651-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="8f651-1057">-   Der Fehlercode -   Der mögliche Grund für den -   Fehler. Hinweise dazu, was jetzt zu tun ist</span><span class="sxs-lookup"><span data-stu-id="8f651-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="8f651-1058">Verwenden Sie die Informationen in diesen Tabellen zur Problembehandlung Microsoft Defender Antivirus Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="8f651-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="8f651-1059">Fehlercode: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="8f651-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8f651-1060">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1060">Message</span></span></td>
<td><span data-ttu-id="8f651-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1062">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="8f651-1063">Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="8f651-1064">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="8f651-1065">Überprüfen Sie den verfügbaren Arbeitsspeicher auf Ihrem Gerät.</span><span class="sxs-lookup"><span data-stu-id="8f651-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="8f651-1066">Schließen Sie alle nicht verwendeten Anwendungen, die ausgeführt werden, um Arbeitsspeicher auf Ihrem Gerät freizugeben.</span><span class="sxs-lookup"><span data-stu-id="8f651-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="8f651-1067">Starten Sie das Gerät neu, und führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1068">Fehlercode: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="8f651-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="8f651-1069">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1069">Message</span></span></td>
<td><span data-ttu-id="8f651-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1071">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1072">Dieser Fehler weist darauf hin, dass möglicherweise ein Problem mit Ihrem Sicherheitsprodukt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="8f651-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="8f651-1073">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="8f651-1074">Aktualisieren Sie die Definitionen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1074">Update the definitions.</span></span> <span data-ttu-id="8f651-1075">Entweder:</span><span class="sxs-lookup"><span data-stu-id="8f651-1075">Either:</span></span><ol>
<li><span data-ttu-id="8f651-1076">Klicken Sie auf der Registerkarte <b>"Aktualisieren"</b> in Microsoft Defender Antivirus auf die Schaltfläche <b>"Definitionen</b> aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="8f651-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="8f651-1077">Oder:</span><span class="sxs-lookup"><span data-stu-id="8f651-1077">Or,</span></span>
</li>
<li><span data-ttu-id="8f651-1078">Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence Website</a>herunter.</span><span class="sxs-lookup"><span data-stu-id="8f651-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="8f651-1079">Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f651-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="8f651-1080">Führen Sie einen vollständigen Scan aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="8f651-1081">Starten Sie das Gerät neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="8f651-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1082">Fehlercode: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="8f651-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="8f651-1083">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1083">Message</span></span></td>
<td><span data-ttu-id="8f651-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1085">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1086">Dieser Fehler weist darauf hin, dass möglicherweise ein Modulkonfigurationsfehler vorliegt. In der Regel bezieht sich dies auf Eingabedaten, die nicht zulassen, dass das Modul ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1087">Fehlercode: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="8f651-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1088">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1088">Message</span></span></td>
<td><span data-ttu-id="8f651-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1090">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1091">Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus eine Bedrohung nicht unter Quarantäne stellen konnten.</span><span class="sxs-lookup"><span data-stu-id="8f651-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1092">Fehlercode: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="8f651-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1093">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1093">Message</span></span></td>
<td><span data-ttu-id="8f651-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1095">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1096">Dieser Fehler weist darauf hin, dass ein Neustart erforderlich ist, um die Bedrohung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="8f651-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="8f651-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1098">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1098">Message</span></span></td>
<td><span data-ttu-id="8f651-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1100">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1101">Dieser Fehler weist darauf hin, dass die Bedrohung möglicherweise nicht mehr auf den Medien vorhanden ist, oder dass Schadsoftware Sie daran hindert, Ihr Gerät zu scannen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="8f651-1102">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="8f651-1103">Führen Sie die <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> aktualisieren Sie dann Ihre Sicherheitssoftware, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="8f651-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1104">Fehlercode: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="8f651-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="8f651-1105">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1105">Message</span></span></td>
<td><span data-ttu-id="8f651-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1107">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1108">Dieser Fehler weist darauf hin, dass möglicherweise eine vollständige Systemüberprüfung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="8f651-1109">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1109">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1110">Führen Sie eine vollständige Systemüberprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1111">Fehlercode: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="8f651-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1112">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1112">Message</span></span></td>
<td><span data-ttu-id="8f651-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1114">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1115">Dieser Fehler weist darauf hin, dass manuelle Schritte erforderlich sind, um die Bedrohungsentfernung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1116">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1116">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1117">Führen Sie die manuellen Korrekturschritte aus, die im <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection-Abschnitt</a>beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="8f651-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="8f651-1118">Sie finden einen bedrohungsspezifischen Link im Ereignisverlauf.</span><span class="sxs-lookup"><span data-stu-id="8f651-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1119">Fehlercode: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="8f651-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1120">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1120">Message</span></span></td>
<td><span data-ttu-id="8f651-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1122">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1123">Dieser Fehler weist darauf hin, dass das Entfernen innerhalb des Containertyps möglicherweise nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="8f651-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1124">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1124">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1125">Microsoft Defender Antivirus können im Archiv erkannte Bedrohungen nicht beheben.</span><span class="sxs-lookup"><span data-stu-id="8f651-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="8f651-1126">Erwägen Sie, die erkannten Ressourcen manuell zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1127">Fehlercode: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="8f651-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1128">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1128">Message</span></span></td>
<td><span data-ttu-id="8f651-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1130">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1131">Dieser Fehler weist darauf hin, dass das Entfernen von niedrigen und mittleren Bedrohungen möglicherweise deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1132">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1132">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1133">Überprüfen Sie die erkannten Bedrohungen, und beheben Sie sie nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="8f651-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1134">Fehlercode: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="8f651-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1135">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1135">Message</span></span></td>
<td><span data-ttu-id="8f651-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1137">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1138">Dieser Fehler weist darauf hin, dass eine erneute Überprüfung der Bedrohung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1139">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1139">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1140">Führen Sie eine vollständige Systemüberprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1141">Fehlercode: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="8f651-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1142">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1142">Message</span></span></td>
<td><span data-ttu-id="8f651-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8f651-1144">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1145">Dieser Fehler weist darauf hin, dass eine Offlineüberprüfung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1146">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1146">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1147">Führen Sie offline Microsoft Defender Antivirus aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="8f651-1148">Informationen dazu finden Sie im <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Artikel "Offline Microsoft Defender Antivirus".</a></span><span class="sxs-lookup"><span data-stu-id="8f651-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8f651-1149">Fehlercode: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="8f651-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="8f651-1150">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f651-1150">Message</span></span></td>
<td><span data-ttu-id="8f651-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="8f651-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="8f651-1152">Mögliche Ursache</span><span class="sxs-lookup"><span data-stu-id="8f651-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="8f651-1153">Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus die aktuelle Version der Plattform nicht unterstützt und eine neue Version der Plattform erfordert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="8f651-1154">Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1154">Resolution</span></span></td><td>
<span data-ttu-id="8f651-1155">Sie können Microsoft Defender Antivirus nur in Windows 10 verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f651-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="8f651-1156">Für Windows 8, Windows 7 und Windows Vista können Sie <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f651-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="8f651-1157">

<a id="internal-error-codes"></a>Die folgenden Fehlercodes werden bei internen Tests von Microsoft Defender Antivirus verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f651-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="8f651-1158">Wenn diese Fehler angezeigt werden, können Sie versuchen, [Definitionen](manage-updates-baselines-microsoft-defender-antivirus.md) zu aktualisieren und einen erneuten Scan direkt auf dem Endpunkt zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8f651-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="8f651-1159">Interne Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="8f651-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="8f651-1160"><b>Fehlercode</b></span><span class="sxs-lookup"><span data-stu-id="8f651-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="8f651-1161">Angezeigte Nachricht</span><span class="sxs-lookup"><span data-stu-id="8f651-1161">Message displayed</span></span></th>
<th><span data-ttu-id="8f651-1162">Mögliche Ursache für Fehler und Lösung</span><span class="sxs-lookup"><span data-stu-id="8f651-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="8f651-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="8f651-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="8f651-1165">Überprüfen Sie Ihre Internetverbindung, und führen Sie die Überprüfung dann erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8f651-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="8f651-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="8f651-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="8f651-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="8f651-1168">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f651-1168">This is an internal error.</span></span> <span data-ttu-id="8f651-1169">Die Ursache ist nicht eindeutig definiert.</span><span class="sxs-lookup"><span data-stu-id="8f651-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="8f651-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="8f651-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="8f651-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="8f651-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="8f651-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="8f651-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="8f651-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="8f651-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="8f651-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="8f651-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="8f651-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="8f651-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="8f651-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="8f651-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="8f651-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="8f651-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="8f651-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="8f651-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="8f651-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="8f651-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="8f651-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="8f651-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="8f651-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="8f651-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="8f651-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="8f651-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="8f651-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="8f651-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="8f651-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="8f651-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="8f651-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="8f651-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="8f651-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="8f651-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="8f651-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="8f651-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="8f651-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="8f651-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="8f651-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="8f651-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="8f651-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="8f651-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="8f651-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="8f651-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="8f651-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="8f651-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="8f651-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="8f651-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="8f651-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="8f651-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="8f651-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="8f651-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="8f651-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="8f651-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="8f651-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="8f651-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="8f651-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="8f651-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="8f651-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="8f651-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="8f651-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="8f651-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="8f651-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="8f651-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="8f651-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="8f651-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="8f651-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="8f651-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="8f651-1238">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f651-1238">This is an internal error.</span></span> <span data-ttu-id="8f651-1239">Er kann ausgelöst werden, wenn die Entfernung von Schadsoftware nicht erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8f651-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8f651-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="8f651-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="8f651-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8f651-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="8f651-1242">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f651-1242">This is an internal error.</span></span> <span data-ttu-id="8f651-1243">Er kann ausgelöst worden sein, wenn eine Überprüfung nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f651-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="8f651-1244">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8f651-1244">Related topics</span></span>

- [<span data-ttu-id="8f651-1245">Bericht über Microsoft Defender Antivirus Schutz</span><span class="sxs-lookup"><span data-stu-id="8f651-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f651-1246">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f651-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)