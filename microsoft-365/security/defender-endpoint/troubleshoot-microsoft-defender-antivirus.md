---
title: Microsoft Defender AV-Ereignis-IDs und Fehlercodes
description: Suchen der Ursachen und Lösungen für Microsoft Defender Antivirus-Ereignis-IDs und -Fehler
keywords: Ereignis, Fehlercode, Siem, Protokollierung, Problembehandlung, Wef, Windows-Ereignis-Weiterleitung
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765815"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="1b184-104">Überprüfen von Ereignisprotokollen und Fehlercodes zur Problembehandlung bei Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1b184-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1b184-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b184-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1b184-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1b184-107">Wenn sie ein Problem mit Microsoft Defender Antivirus haben, können Sie in den Tabellen in diesem Thema nach einem übereinstimmenden Problem und einer potenziellen Lösung suchen.</span><span class="sxs-lookup"><span data-stu-id="1b184-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="1b184-108">Die Tabellenliste:</span><span class="sxs-lookup"><span data-stu-id="1b184-108">The tables list:</span></span>

- <span data-ttu-id="1b184-109">[Microsoft Defender Antivirus-Ereignis-IDs](#windows-defender-av-ids) (diese gelten für Windows 10 und Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="1b184-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="1b184-110">Microsoft Defender Antivirus-Clientfehlercodes</span><span class="sxs-lookup"><span data-stu-id="1b184-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="1b184-111">Interne Microsoft Defender Antivirus-Clientfehlercodes (die von Microsoft während der Entwicklung und beim Testen verwendet werden)</span><span class="sxs-lookup"><span data-stu-id="1b184-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="1b184-112">Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren:</span><span class="sxs-lookup"><span data-stu-id="1b184-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="1b184-113">In der Cloud zugestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="1b184-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="1b184-114">Schnelles Lernen (einschließlich "Bei erster Sicht blockieren")</span><span class="sxs-lookup"><span data-stu-id="1b184-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="1b184-115">Potenziell unerwünschte Anwendungsblockierung</span><span class="sxs-lookup"><span data-stu-id="1b184-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="1b184-116">Microsoft Defender Antivirus-Ereignis-IDs</span><span class="sxs-lookup"><span data-stu-id="1b184-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="1b184-117">Microsoft Defender Antivirus zeichnet Ereignis-IDs im Windows-Ereignisprotokoll auf.</span><span class="sxs-lookup"><span data-stu-id="1b184-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="1b184-118">Sie können das Ereignisprotokoll direkt anzeigen, oder wenn Sie über ein Tool für die Sicherheitsinformationen und Ereignisverwaltung (SIEM) eines Drittanbieters verfügen, können Sie auch [Microsoft Defender Antivirus-Clientereignis-IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) verwenden, um bestimmte Ereignisse und Fehler von Ihren Endpunkten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1b184-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="1b184-119">In der Tabelle in diesem Abschnitt sind die wichtigsten Microsoft Defender Antivirus-Ereignis-IDs aufgeführt und, sofern möglich, Lösungsvorschläge zum Beheben oder Beheben des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="1b184-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="1b184-120">So zeigen Sie ein Microsoft Defender Antivirus-Ereignis an</span><span class="sxs-lookup"><span data-stu-id="1b184-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="1b184-121">Öffnen **Sie die Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="1b184-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="1b184-122">Erweitern Sie in der Konsolenstruktur **Anwendungen- und Dienstprotokolle,** dann **Microsoft**, dann **Windows** und **dann Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="1b184-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="1b184-123">Doppelklicken Sie auf **Betriebs .**</span><span class="sxs-lookup"><span data-stu-id="1b184-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="1b184-124">Zeigen Sie im Detailbereich die Liste der einzelnen Ereignisse an, um Ihr Ereignis zu finden.</span><span class="sxs-lookup"><span data-stu-id="1b184-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="1b184-125">Klicken Sie auf das Ereignis, um bestimmte Details zu einem Ereignis im unteren Bereich unter den Registerkarten **Allgemein** und **Details** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b184-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="1b184-126">Ereignis-ID: 1000</span><span class="sxs-lookup"><span data-stu-id="1b184-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-127">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="1b184-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-129">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-129">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-130">
<b>Eine Antischalwarescan wurde gestartet. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="1b184-131">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-132">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-133">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-134">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-134">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-135">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-135">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-136">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-137">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-137">Full scan</span></span></li>
<li><span data-ttu-id="1b184-138">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-138">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-139">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-139">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-140">
</dt>
<dt>Scannen von Ressourcen: &lt; Gescannte Ressourcen (z. B. Dateien/Verzeichnisse/BHO). &gt; </dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-141">Ereignis-ID: 1001</span><span class="sxs-lookup"><span data-stu-id="1b184-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-142">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-144">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-144">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-145">
<b>Eine Antischalwarescan wurde abgeschlossen.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-146">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-147">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-148">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-149">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-149">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-150">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-150">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-151">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-152">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-152">Full scan</span></span></li>
<li><span data-ttu-id="1b184-153">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-153">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-154">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-154">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-155">
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerscanzeit: &lt; Die Dauer eines &gt; Scans.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-156">Ereignis-ID: 1002</span><span class="sxs-lookup"><span data-stu-id="1b184-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-157">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-159">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-159">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-160">
<b>Eine Antischalwarescan wurde beendet, bevor sie abgeschlossen wurde. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-161">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-162">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-163">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-164">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-164">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-165">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-165">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-166">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-167">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-167">Full scan</span></span></li>
<li><span data-ttu-id="1b184-168">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-168">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-169">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-169">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-170">
</dt>
<dt>Benutzer: &lt; Domain &gt; &amp; lt; &gt;</dt>
<dt>Benutzerscanzeit: &lt; Die Dauer eines &gt; Scans.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-171">Ereignis-ID: 1003</span><span class="sxs-lookup"><span data-stu-id="1b184-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-172">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-174">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-174">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-175">
<b>Eine Antischalwarescan wurde angehalten. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-176">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-177">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-178">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-179">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-179">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-180">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-180">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-181">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-182">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-182">Full scan</span></span></li>
<li><span data-ttu-id="1b184-183">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-183">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-184">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-184">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-185">
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; User&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-186">Ereignis-ID: 1004</span><span class="sxs-lookup"><span data-stu-id="1b184-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-187">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-189">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-189">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-190">
<b>Eine Antischalwarescan wurde fortgesetzt. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-191">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-192">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-193">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-194">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-194">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-195">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-195">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-196">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-197">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-197">Full scan</span></span></li>
<li><span data-ttu-id="1b184-198">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-198">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-199">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-199">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-200">
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; User&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-201">Ereignis-ID: 1005</span><span class="sxs-lookup"><span data-stu-id="1b184-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-202">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-204">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-204">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-205">
<b>Fehler bei einer Antischalwarescan. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-206">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="1b184-207">
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-208">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-209">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-209">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-210">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-210">Antimalware</span></span></li>
</ul><span data-ttu-id="1b184-211">
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-212">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="1b184-212">Full scan</span></span></li>
<li><span data-ttu-id="1b184-213">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="1b184-213">Quick scan</span></span></li>
<li><span data-ttu-id="1b184-214">Kundenscan</span><span class="sxs-lookup"><span data-stu-id="1b184-214">Customer scan</span></span></li>
</ul><span data-ttu-id="1b184-215">
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-216">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-217">Beim Antivirusclient ist ein Fehler aufgetreten, und die aktuelle Überprüfung wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="1b184-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="1b184-218">Die Überprüfung kann aufgrund eines clientseitigen Problems fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="1b184-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="1b184-219">Dieser Ereignisdatensatz enthält die Scan-ID, den Scantyp (Microsoft Defender Antivirus, Antischa spyware, Antischansoftware), Scanparameter, den Benutzer, der die Überprüfung gestartet hat, den Fehlercode und eine Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="1b184-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="1b184-220">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="1b184-221">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="1b184-222">Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1b184-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="1b184-223">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-224">Ereignis-ID: 1006</span><span class="sxs-lookup"><span data-stu-id="1b184-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-225">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-227">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-227">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-228">
<b>Das Antischalwaremodul hat Schadsoftware oder andere potenziell unerwünschte Software gefunden. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-229">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-230">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-231">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-232">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-232">Low</span></span></li>
<li><span data-ttu-id="1b184-233">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-233">Moderate</span></span></li>
<li><span data-ttu-id="1b184-234">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-234">High</span></span></li>
<li><span data-ttu-id="1b184-235">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-235">Severe</span></span></li>
</ul><span data-ttu-id="1b184-236">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-237">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-237">Unknown</span></span></li>
<li><span data-ttu-id="1b184-238">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-238">Local computer</span></span></li>
<li><span data-ttu-id="1b184-239">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-239">Network share</span></span></li>
<li><span data-ttu-id="1b184-240">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-240">Internet</span></span></li>
<li><span data-ttu-id="1b184-241">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-242">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-243">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-244">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-245">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-245">Generic</span></span></li>
<li><span data-ttu-id="1b184-246">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-246">Concrete</span></span></li>
<li><span data-ttu-id="1b184-247">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-248">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-249">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-249">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-250">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-250">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-251">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-252">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-253">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-254">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-255">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-256">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-257">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-258">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-259">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-260"></dt>
<dt>#A0 : &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>
<dt> &lt; &gt; Version</dt>des Definitionsmoduls:
<dt> &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-261">Ereigniskennung: 1007</span><span class="sxs-lookup"><span data-stu-id="1b184-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-262">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-264">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-264">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-265">
<b>Die Antischalwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-266">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-267">Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1b184-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="1b184-268">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-269">
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; Schweregrad , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-270">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-270">Low</span></span></li>
<li><span data-ttu-id="1b184-271">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-271">Moderate</span></span></li>
<li><span data-ttu-id="1b184-272">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-272">High</span></span></li>
<li><span data-ttu-id="1b184-273">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-273">Severe</span></span></li>
</ul><span data-ttu-id="1b184-274">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt> Aktion: &lt; Aktion &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-275">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="1b184-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="1b184-276">Quarantäne: Die Ressource wurde isoliert</span><span class="sxs-lookup"><span data-stu-id="1b184-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="1b184-277">Remove: Die Ressource wurde gelöscht</span><span class="sxs-lookup"><span data-stu-id="1b184-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="1b184-278">Allow: Die Ressource konnte ausgeführt/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="1b184-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="1b184-279">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="1b184-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="1b184-280">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-280">No action: No action</span></span></li>
<li><span data-ttu-id="1b184-281">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="1b184-282">
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-283">Ereigniskennung: 1008</span><span class="sxs-lookup"><span data-stu-id="1b184-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-284">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-286">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-286">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-287">
<b>Die Antischalwareplattform hat versucht, eine Aktion zum Schutz Ihres Systems vor Schadsoftware oder anderer potenziell unerwünschter Software durchzuführen, die Aktion ist jedoch fehlgeschlagen.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-288">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-289">Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="1b184-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="1b184-290">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-291">
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; Schweregrad , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-292">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-292">Low</span></span></li>
<li><span data-ttu-id="1b184-293">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-293">Moderate</span></span></li>
<li><span data-ttu-id="1b184-294">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-294">High</span></span></li>
<li><span data-ttu-id="1b184-295">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-295">Severe</span></span></li>
</ul><span data-ttu-id="1b184-296">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfadaktion: &gt; </dt> 
<dt> Aktion , &lt; &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-297">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="1b184-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="1b184-298">Quarantäne: Die Ressource wurde isoliert</span><span class="sxs-lookup"><span data-stu-id="1b184-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="1b184-299">Remove: Die Ressource wurde gelöscht</span><span class="sxs-lookup"><span data-stu-id="1b184-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="1b184-300">Allow: Die Ressource konnte ausgeführt/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="1b184-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="1b184-301">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="1b184-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="1b184-302">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-302">No action: No action</span></span></li>
<li><span data-ttu-id="1b184-303">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="1b184-304">
</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-304">
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
<th colspan="2"><span data-ttu-id="1b184-305">Ereigniskennung: 1009</span><span class="sxs-lookup"><span data-stu-id="1b184-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-306">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-308">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-308">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-309">
<b>Die Antischalwareplattform hat ein Element aus der Quarantäne wiederhergestellt. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-310">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-311">Microsoft Defender Antivirus hat ein Element aus der Quarantäne wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1b184-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="1b184-312">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-313">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-314">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-314">Low</span></span></li>
<li><span data-ttu-id="1b184-315">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-315">Moderate</span></span></li>
<li><span data-ttu-id="1b184-316">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-316">High</span></span></li>
<li><span data-ttu-id="1b184-317">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-317">Severe</span></span></li>
</ul><span data-ttu-id="1b184-318">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-318">
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
<th colspan="2"><span data-ttu-id="1b184-319">Ereigniskennung: 1010</span><span class="sxs-lookup"><span data-stu-id="1b184-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-320">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-322">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-322">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-323">
<b>Die Antischalwareplattform konnte ein Element nicht aus der Quarantäne wiederherstellen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-324">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-325">Beim Versuch, ein Element aus der Quarantäne wiederherzustellen, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="1b184-326">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-327">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-328">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-328">Low</span></span></li>
<li><span data-ttu-id="1b184-329">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-329">Moderate</span></span></li>
<li><span data-ttu-id="1b184-330">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-330">High</span></span></li>
<li><span data-ttu-id="1b184-331">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-331">Severe</span></span></li>
</ul><span data-ttu-id="1b184-332">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-332">
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
<th colspan="2"><span data-ttu-id="1b184-333">Ereignis-ID: 1011</span><span class="sxs-lookup"><span data-stu-id="1b184-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-334">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-336">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-336">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-337">
<b>Die Antischalwareplattform hat ein Element aus der Quarantäne gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-338">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-339">Microsoft Defender Antivirus hat ein Element aus der Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1b184-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="1b184-340">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-341">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-342">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-342">Low</span></span></li>
<li><span data-ttu-id="1b184-343">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-343">Moderate</span></span></li>
<li><span data-ttu-id="1b184-344">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-344">High</span></span></li>
<li><span data-ttu-id="1b184-345">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-345">Severe</span></span></li>
</ul><span data-ttu-id="1b184-346">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-346">
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
<th colspan="2"><span data-ttu-id="1b184-347">Ereigniskennung: 1012</span><span class="sxs-lookup"><span data-stu-id="1b184-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-348">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-350">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-350">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-351">
<b>Die Antischalwareplattform konnte ein Element nicht aus der Quarantäne löschen.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-352">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-353">Beim Versuch, ein Element aus der Quarantäne zu löschen, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="1b184-354">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-355">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-356">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-356">Low</span></span></li>
<li><span data-ttu-id="1b184-357">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-357">Moderate</span></span></li>
<li><span data-ttu-id="1b184-358">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-358">High</span></span></li>
<li><span data-ttu-id="1b184-359">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-359">Severe</span></span></li>
</ul><span data-ttu-id="1b184-360">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-360">
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
<th colspan="2"><span data-ttu-id="1b184-361">Ereignis-ID: 1013</span><span class="sxs-lookup"><span data-stu-id="1b184-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-362">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-364">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-364">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-365">
<b>Die Antischalwareplattform hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software gelöscht.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-366">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-367">Microsoft Defender Antivirus hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software entfernt.</span><span class="sxs-lookup"><span data-stu-id="1b184-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="1b184-368">Zeit: Der Zeitpunkt, zu dem das Ereignis aufgetreten ist, z. B. 
<dt>wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um Korrekturzeit oder Infektionszeit handelt. Für diese werden sie speziell als Aktionszeit oder Erkennungszeit bezeichnet.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-369">Ereignis-ID: 1014</span><span class="sxs-lookup"><span data-stu-id="1b184-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-370">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-372">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="1b184-373">Die Antischalwareplattform konnte den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="1b184-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-374">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-375">Microsoft Defender Antivirus hat einen Fehler beim Entfernen des Verlaufs von Schadsoftware und anderer potenziell unerwünschter Software festgestellt.</span><span class="sxs-lookup"><span data-stu-id="1b184-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="1b184-376">Zeit: Der Zeitpunkt, zu dem das Ereignis aufgetreten ist, z. B. 
<dt>wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um Korrekturzeit oder Infektionszeit handelt. Für diese werden sie speziell als Aktionszeit oder Erkennungszeit bezeichnet.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-377">Ereignis-ID: 1015</span><span class="sxs-lookup"><span data-stu-id="1b184-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-378">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-380">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-380">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-381">
<b>Die Antischalwareplattform hat verdächtiges Verhalten erkannt.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-382">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-383">Microsoft Defender Antivirus hat ein verdächtiges Verhalten erkannt.</span><span class="sxs-lookup"><span data-stu-id="1b184-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="1b184-384">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-385">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-386">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-386">Low</span></span></li>
<li><span data-ttu-id="1b184-387">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-387">Moderate</span></span></li>
<li><span data-ttu-id="1b184-388">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-388">High</span></span></li>
<li><span data-ttu-id="1b184-389">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-389">Severe</span></span></li>
</ul><span data-ttu-id="1b184-390">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-391">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-391">Unknown</span></span></li>
<li><span data-ttu-id="1b184-392">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-392">Local computer</span></span></li>
<li><span data-ttu-id="1b184-393">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-393">Network share</span></span></li>
<li><span data-ttu-id="1b184-394">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-394">Internet</span></span></li>
<li><span data-ttu-id="1b184-395">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-396">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-397">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-398">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-399">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-399">Generic</span></span></li>
<li><span data-ttu-id="1b184-400">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-400">Concrete</span></span></li>
<li><span data-ttu-id="1b184-401">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-402">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-403">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-403">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-404">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-404">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-405">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-406">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-407">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-408">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-409">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-410">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-411">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-412">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-413">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-414"></dt>
<dt>#A0 : &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signatur-ID:</dt>
<dt>Aufzählungsvergleichsschweregrad.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; &gt; Antischalwaremodulversion</dt>
<dt>Fidelity Label:</dt>
<dt>Zieldateiname: &lt; Dateiname Name der &gt; Datei.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="1b184-415">Ereignis-ID: 1116</span><span class="sxs-lookup"><span data-stu-id="1b184-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-416">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-418">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-418">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-419">
<b>Die Antischalwareplattform hat Schadsoftware oder andere potenziell unerwünschte Software erkannt. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-420">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-421">Microsoft Defender Antivirus hat Schadsoftware oder andere potenziell unerwünschte Software erkannt.</span><span class="sxs-lookup"><span data-stu-id="1b184-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="1b184-422">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-423">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-424">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-424">Low</span></span></li>
<li><span data-ttu-id="1b184-425">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-425">Moderate</span></span></li>
<li><span data-ttu-id="1b184-426">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-426">High</span></span></li>
<li><span data-ttu-id="1b184-427">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-427">Severe</span></span></li>
</ul><span data-ttu-id="1b184-428">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-429">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-429">Unknown</span></span></li>
<li><span data-ttu-id="1b184-430">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-430">Local computer</span></span></li>
<li><span data-ttu-id="1b184-431">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-431">Network share</span></span></li>
<li><span data-ttu-id="1b184-432">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-432">Internet</span></span></li>
<li><span data-ttu-id="1b184-433">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-434">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-435">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-436">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-437">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-437">Generic</span></span></li>
<li><span data-ttu-id="1b184-438">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-438">Concrete</span></span></li>
<li><span data-ttu-id="1b184-439">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-440">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-441">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-441">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-442">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-442">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-443">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-444">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-445">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-446">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-447">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-448">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-449">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-450">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-451">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-452"></dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>
<dt> &lt; &gt; Version</dt>des Definitionsmoduls:
<dt> &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-453">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-454">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-454">No action is required.</span></span> <span data-ttu-id="1b184-455">Microsoft Defender Antivirus kann diese Bedrohung anhalten und Routinemaßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="1b184-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="1b184-456">Wenn Sie die Bedrohung manuell entfernen möchten, klicken Sie auf der Microsoft Defender Antivirus-Schnittstelle auf <b>Clean Computer</b>.</span><span class="sxs-lookup"><span data-stu-id="1b184-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-457">Ereignis-ID: 1117</span><span class="sxs-lookup"><span data-stu-id="1b184-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-458">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-460">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-460">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-461">
<b>Die Antischalwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-462">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-463">Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1b184-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="1b184-464">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-465">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-466">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-466">Low</span></span></li>
<li><span data-ttu-id="1b184-467">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-467">Moderate</span></span></li>
<li><span data-ttu-id="1b184-468">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-468">High</span></span></li>
<li><span data-ttu-id="1b184-469">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-469">Severe</span></span></li>
</ul><span data-ttu-id="1b184-470">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-471">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-471">Unknown</span></span></li>
<li><span data-ttu-id="1b184-472">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-472">Local computer</span></span></li>
<li><span data-ttu-id="1b184-473">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-473">Network share</span></span></li>
<li><span data-ttu-id="1b184-474">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-474">Internet</span></span></li>
<li><span data-ttu-id="1b184-475">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-476">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-477">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-478">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-479">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-479">Generic</span></span></li>
<li><span data-ttu-id="1b184-480">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-480">Concrete</span></span></li>
<li><span data-ttu-id="1b184-481">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-482">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-483">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-483">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-484">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-484">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-485">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-486">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-487">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-488">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-489">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-490">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-491">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-492">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-493">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-494"></dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-495">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="1b184-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="1b184-496">Quarantäne: Die Ressource wurde isoliert</span><span class="sxs-lookup"><span data-stu-id="1b184-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="1b184-497">Remove: Die Ressource wurde gelöscht</span><span class="sxs-lookup"><span data-stu-id="1b184-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="1b184-498">Allow: Die Ressource konnte ausgeführt/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="1b184-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="1b184-499">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="1b184-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="1b184-500">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-500">No action: No action</span></span></li>
<li><span data-ttu-id="1b184-501">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="1b184-502">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>Definitionsmoduls:
<dt> &lt; &gt; AntischalwaremodulVersion</dt> HINWEIS: Wenn Microsoft Defender Antivirus, Microsoft Security Essentials, Tool zum Entfernen bösartiger Software oder System Center Endpoint Protection eine Schadsoftware erkennt, werden die folgenden Systemeinstellungen und Dienste wiederhergestellt, die die Schadsoftware möglicherweise geändert hat:</span><span class="sxs-lookup"><span data-stu-id="1b184-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="1b184-503">Standardeinstellung für Internet Explorer oder Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1b184-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="1b184-504">Einstellungen für die Benutzerzugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="1b184-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="1b184-505">Chrome-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1b184-505">Chrome settings</span></span></li>
<li><span data-ttu-id="1b184-506">Startsteuerungsdaten</span><span class="sxs-lookup"><span data-stu-id="1b184-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="1b184-507">Registrierungseinstellungen für Regedit und Task Manager</span><span class="sxs-lookup"><span data-stu-id="1b184-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="1b184-508">Windows Update-, Background Intelligent Transfer Service- und Remoteprozedur-Anrufdienst</span><span class="sxs-lookup"><span data-stu-id="1b184-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="1b184-509">Windows-Betriebssystemdateien</span><span class="sxs-lookup"><span data-stu-id="1b184-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="1b184-510">Der obige Kontext gilt für die folgenden Client- und Serverversionen:</span><span class="sxs-lookup"><span data-stu-id="1b184-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="1b184-511">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-511">Operating system</span></span></th>
<th><span data-ttu-id="1b184-512">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="1b184-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-513">Clientbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="1b184-514">Windows Vista (Service Pack 1 oder Service Pack 2), Windows 7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b184-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-515">Serverbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="1b184-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 und Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1b184-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-517">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-518">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-518">No action is necessary.</span></span> <span data-ttu-id="1b184-519">Microsoft Defender Antivirus hat eine Bedrohung entfernt oder isoliert.</span><span class="sxs-lookup"><span data-stu-id="1b184-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-520">Ereignis-ID: 1118</span><span class="sxs-lookup"><span data-stu-id="1b184-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-521">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-523">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-523">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-524">
<b>Die Antischalwareplattform hat versucht, eine Aktion zum Schutz Ihres Systems vor Schadsoftware oder anderer potenziell unerwünschter Software durchzuführen, die Aktion ist jedoch fehlgeschlagen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-525">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-526">Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen nicht kritischen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="1b184-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="1b184-527">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-528">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-529">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-529">Low</span></span></li>
<li><span data-ttu-id="1b184-530">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-530">Moderate</span></span></li>
<li><span data-ttu-id="1b184-531">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-531">High</span></span></li>
<li><span data-ttu-id="1b184-532">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-532">Severe</span></span></li>
</ul><span data-ttu-id="1b184-533">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-534">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-534">Unknown</span></span></li>
<li><span data-ttu-id="1b184-535">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-535">Local computer</span></span></li>
<li><span data-ttu-id="1b184-536">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-536">Network share</span></span></li>
<li><span data-ttu-id="1b184-537">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-537">Internet</span></span></li>
<li><span data-ttu-id="1b184-538">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-539">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-540">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-541">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-542">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-542">Generic</span></span></li>
<li><span data-ttu-id="1b184-543">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-543">Concrete</span></span></li>
<li><span data-ttu-id="1b184-544">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-545">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-546">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-546">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-547">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-547">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-548">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-549">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-550">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-551">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-552">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-553">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-554">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-555">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-556">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-557"></dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-558">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="1b184-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="1b184-559">Quarantäne: Die Ressource wurde isoliert</span><span class="sxs-lookup"><span data-stu-id="1b184-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="1b184-560">Remove: Die Ressource wurde gelöscht</span><span class="sxs-lookup"><span data-stu-id="1b184-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="1b184-561">Allow: Die Ressource konnte ausgeführt/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="1b184-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="1b184-562">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="1b184-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="1b184-563">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-563">No action: No action</span></span></li>
<li><span data-ttu-id="1b184-564">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="1b184-565">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-565">
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
<span data-ttu-id="1b184-566">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-567">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-567">No action is necessary.</span></span> <span data-ttu-id="1b184-568">Microsoft Defender Antivirus konnte eine Aufgabe im Zusammenhang mit der Schadsoftwarebehebung nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="1b184-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="1b184-569">Dies ist kein kritischer Fehler.</span><span class="sxs-lookup"><span data-stu-id="1b184-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-570">Ereignis-ID: 1119</span><span class="sxs-lookup"><span data-stu-id="1b184-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-571">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-573">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-573">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-574">
<b>Die Antischantischungsplattform ist beim Versuch, Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software zu ergreifen, auf einen kritischen Fehler gestoßen. Die Ereignisnachricht enthält weitere Details.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-575">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-576">Microsoft Defender Antivirus hat einen kritischen Fehler beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software festgestellt.</span><span class="sxs-lookup"><span data-stu-id="1b184-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="1b184-577">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b184-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="1b184-578">
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-579">Niedrig</span><span class="sxs-lookup"><span data-stu-id="1b184-579">Low</span></span></li>
<li><span data-ttu-id="1b184-580">Mittel</span><span class="sxs-lookup"><span data-stu-id="1b184-580">Moderate</span></span></li>
<li><span data-ttu-id="1b184-581">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b184-581">High</span></span></li>
<li><span data-ttu-id="1b184-582">Schwerwiegend</span><span class="sxs-lookup"><span data-stu-id="1b184-582">Severe</span></span></li>
</ul><span data-ttu-id="1b184-583">
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-584">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b184-584">Unknown</span></span></li>
<li><span data-ttu-id="1b184-585">Lokaler Computer</span><span class="sxs-lookup"><span data-stu-id="1b184-585">Local computer</span></span></li>
<li><span data-ttu-id="1b184-586">Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-586">Network share</span></span></li>
<li><span data-ttu-id="1b184-587">Internet</span><span class="sxs-lookup"><span data-stu-id="1b184-587">Internet</span></span></li>
<li><span data-ttu-id="1b184-588">Eingehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="1b184-589">Ausgehender Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1b184-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="1b184-590">
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="1b184-591">Heuristics</span></span></li>
<li><span data-ttu-id="1b184-592">Generic</span><span class="sxs-lookup"><span data-stu-id="1b184-592">Generic</span></span></li>
<li><span data-ttu-id="1b184-593">Concrete</span><span class="sxs-lookup"><span data-stu-id="1b184-593">Concrete</span></span></li>
<li><span data-ttu-id="1b184-594">Dynamische Signatur</span><span class="sxs-lookup"><span data-stu-id="1b184-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="1b184-595">
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="1b184-596">Benutzer: Vom Benutzer initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-596">User: user initiated</span></span></li>
<li><span data-ttu-id="1b184-597">System: System initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-597">System: system initiated</span></span></li>
<li><span data-ttu-id="1b184-598">Echtzeit: In Echtzeit initiierte Echtzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="1b184-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="1b184-599">IOAV: IE Downloads und Outlook Express Attachments initiiert</span><span class="sxs-lookup"><span data-stu-id="1b184-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="1b184-600">NIS: Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="1b184-601">IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b184-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="1b184-602">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="1b184-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="1b184-603">Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="1b184-604">Remote-Nachweis</span><span class="sxs-lookup"><span data-stu-id="1b184-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="1b184-605">Antischalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="1b184-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="1b184-606">Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="1b184-607"></dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="1b184-608">Clean: Die Ressource wurde bereinigt</span><span class="sxs-lookup"><span data-stu-id="1b184-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="1b184-609">Quarantäne: Die Ressource wurde isoliert</span><span class="sxs-lookup"><span data-stu-id="1b184-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="1b184-610">Remove: Die Ressource wurde gelöscht</span><span class="sxs-lookup"><span data-stu-id="1b184-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="1b184-611">Allow: Die Ressource konnte ausgeführt/vorhanden sein</span><span class="sxs-lookup"><span data-stu-id="1b184-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="1b184-612">Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</span><span class="sxs-lookup"><span data-stu-id="1b184-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="1b184-613">Keine Aktion: Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-613">No action: No action</span></span></li>
<li><span data-ttu-id="1b184-614">Block: Die Ausführung der Ressource wurde blockiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="1b184-615">
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-615">
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
<span data-ttu-id="1b184-616">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-617">Der Microsoft Defender Antivirus-Client ist aufgrund kritischer Probleme auf diesen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="1b184-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="1b184-618">Der Endpunkt ist möglicherweise nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="1b184-618">The endpoint might not be protected.</span></span> <span data-ttu-id="1b184-619">Überprüfen Sie die Fehlerbeschreibung, und führen Sie dann die unten aufgeführten Schritte <b>für die Benutzeraktion</b> aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="1b184-620">Aktion</span><span class="sxs-lookup"><span data-stu-id="1b184-620">Action</span></span></th>
<th><span data-ttu-id="1b184-621">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1b184-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="1b184-622">
<b>Entfernen</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="1b184-623">Aktualisieren Sie die Definitionen, und vergewissern Sie sich, dass die Entfernung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="1b184-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b184-624">
<b>Clean</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="1b184-625">Aktualisieren Sie die Definitionen, und vergewissern Sie sich, dass die Korrektur erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="1b184-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b184-626">
<b>Quarantäne</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="1b184-627">Aktualisieren Sie die Definitionen, und überprüfen Sie, ob der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b184-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b184-628">
<b>Zulassen</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="1b184-629">Stellen Sie sicher, dass der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b184-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="1b184-630">Wenn dieses Ereignis weiterhin besteht:</span><span class="sxs-lookup"><span data-stu-id="1b184-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="1b184-631">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="1b184-632">Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1b184-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="1b184-633">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-634">Ereignis-ID: 1120</span><span class="sxs-lookup"><span data-stu-id="1b184-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-635">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-637">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-637">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-638">
<b>Microsoft Defender Antivirus hat die Hashes für eine Bedrohungsressource abgeleitet.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-639">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-640">Der Microsoft Defender Antivirus-Client ist in einem fehlerfreien Zustand ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b184-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="1b184-641">
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion &gt; </dt>
<dt>Bedrohungsressourcenpfad: &lt; &gt; Pfadhashes:</dt>
<dt> &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="1b184-642"><b>Hinweis: Dieses Ereignis wird nur protokolliert, wenn die folgende Richtlinie festgelegt ist: <b>ThreatFileHashLogging unsigned</b>.</span><span class="sxs-lookup"><span data-stu-id="1b184-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-643">Ereignis-ID: 1150</span><span class="sxs-lookup"><span data-stu-id="1b184-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-644">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-646">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-646">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-647">
<b>Wenn Die Antischalwareplattform den Status einer Überwachungsplattform meldet, weist dieses Ereignis darauf hin, dass die Antischalwareplattform ausgeführt wird und sich in einem fehlerfreien Zustand befindet. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-648">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-649">Der Microsoft Defender Antivirus-Client ist in einem fehlerfreien Zustand ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b184-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="1b184-650">
<dt>Plattformversion: &lt; Signaturversion &gt; der aktuellen</dt>
<dt>Plattformversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt> &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-651">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-652">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-652">No action is necessary.</span></span> <span data-ttu-id="1b184-653">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="1b184-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="1b184-654">Dieses Ereignis wird stündlich gemeldet.</span><span class="sxs-lookup"><span data-stu-id="1b184-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="1b184-655">Ereignis-ID: 1151</span><span class="sxs-lookup"><span data-stu-id="1b184-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-656">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-658">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-658">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-659">
<b>Endpoint Protection-Clientinte health report (Time in UTC) </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-660">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-661">Antivirusclientinte health report.</span><span class="sxs-lookup"><span data-stu-id="1b184-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="1b184-662">
<dt>Plattformversion: &lt; &gt;</dt>Aktuelle Plattformversion
<dt>Modulversion: &lt; &gt; </dt>Antischalwaremodulversion Netzwerk Echtzeitprüfungsmodulversion: Version des
<dt> &lt; Netzwerk-Realtime-Inspektionsmoduls &gt; </dt>Antivirussignaturversion:
<dt> &lt; &gt; Antivirussignaturversion</dt>
<dt>Anspoywaresignaturversion Netzwerk &lt; &gt; </dt>Echtzeitprüfung Signaturversion: Network
<dt> &lt; Realtime Inspection &gt; </dt>Signature Version
<dt>RTP state: &lt; Realtime protection state &gt; (Enabled or Disabled)</dt>
<dt>OA state: On Access state &lt; &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: Status "IE Downloads and Outlook Express &lt; Attachments" (Aktiviert oder &gt; Deaktiviert):</dt>Status der Verhaltensüberwachung (Aktiviert oder
<dt> &lt; &gt; Deaktiviert)</dt>Antivirussignaturalter: Alter der Antivirussignatur
<dt> &lt; &gt; (in Tagen)</dt>
<dt>Antisywaresignaturalter: Alter der Ansywaresignatur &lt; &gt; (in Tagen)</dt>Alter der letzten Schnellscan: Alter der letzten Schnellscan
<dt> &lt; &gt; (in Tagen)</dt>Alter der letzten vollständigen Überprüfung: Alter der letzten vollständigen Überprüfung
<dt> &lt; &gt; (in Tagen)</dt>Erstellungszeit der Antivirussignatur:
<dt>? &lt; Erstellungszeit für &gt; AntivirensignaturEntschmieren</dt>
<dt>der Signatur antispyware: ? &lt; Erstellungszeit der &gt; Ansywaresignatur</dt>letzte
<dt>Schnellscanstartzeit: ? &lt; Startzeit der &gt; letzten Schnellscans</dt>
<dt>Letzte Endzeit des Schnellscans: ? &lt; &gt;Endzeit</dt>der letzten Schnellscans Letzte Schnellscanquelle: Quelle der letzten Schnellscans (0 = Scan&#39;wurde nicht
<dt> &lt; ausgeführt, 1 = Benutzer &gt; initiiert, 2 = System initiiert)</dt>Letzte vollständige Scanstartzeit:
<dt>? &lt; Startzeit der &gt; letzten vollständigen Überprüfung</dt>
<dt>Letzte vollständige Scanendezeit: ? &lt; &gt;Endzeit</dt>der letzten vollständigen Überprüfung Letzte vollständige Scanquelle: Letzte vollständige Scanquelle
<dt> &lt; (0 = Scan wurde&#39;nicht &gt; ausgeführt, 1 = Benutzer initiiert, 2 = System initiiert)</dt> 
<dt> Produktstatus: Zur internen Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1b184-662">
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

<tr><span data-ttu-id="1b184-663">
<th colspan="2">Ereignis-ID: 2000</span><span class="sxs-lookup"><span data-stu-id="1b184-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-664">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-666">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-666">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-667">
<b>Die Antischalwaredefinitionen wurden erfolgreich aktualisiert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-668">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-669">Die Antivirussignaturversion wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="1b184-670">
<dt>Aktuelle Signaturversion: &lt; Aktuelle &gt; Signaturversion</dt>
<dt>Vorherige Signaturversion: &lt; &gt; Signaturtyp</dt>der vorherigen 
<dt> Signaturversion: &lt; Signaturtyp , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="1b184-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-671">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-672">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-672">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-673">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-673">Antimalware</span></span></li>
<li><span data-ttu-id="1b184-674">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-675">
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder Vollständig oder Delta.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; Aktuelle &gt; </dt>
<dt>Modulversion des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>Vorherige
<dt>Modulversion: &lt; Frühere Modulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-675">
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
<span data-ttu-id="1b184-676">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-677">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-677">No action is necessary.</span></span> <span data-ttu-id="1b184-678">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="1b184-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="1b184-679">Dieses Ereignis wird gemeldet, wenn Signaturen erfolgreich aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-680">Ereignis-ID: 2001</span><span class="sxs-lookup"><span data-stu-id="1b184-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-681">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-683">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-683">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-684">
<b>Fehler beim Sicherheitsintelligenzupdate. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-685">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-686">Bei Microsoft Defender Antivirus ist ein Fehler beim Aktualisieren von Signaturen aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="1b184-687">
<dt>Neue Security Intelligence-Version: &lt; Neue Versionsnummer &gt; </dt>
<dt>Frühere Sicherheitsintelligenzversion: &lt; Vorherige &gt; </dt>Version 
<dt> Updatequelle: &lt; Updatequelle , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-688">Ordner für Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="1b184-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="1b184-689">Interner Updateserver für Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="1b184-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="1b184-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="1b184-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="1b184-691">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="1b184-691">File share</span></span></li>
<li><span data-ttu-id="1b184-692">Microsoft Center zum Schutz vor Malware (MMPC)</span><span class="sxs-lookup"><span data-stu-id="1b184-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="1b184-693">
</dt>
<dt>Updatephase: &lt; Updatephase &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-694">Suchen</span><span class="sxs-lookup"><span data-stu-id="1b184-694">Search</span></span></li>
<li><span data-ttu-id="1b184-695">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="1b184-695">Download</span></span></li>
<li><span data-ttu-id="1b184-696">Installieren</span><span class="sxs-lookup"><span data-stu-id="1b184-696">Install</span></span></li>
</ul><span data-ttu-id="1b184-697">
</dt>
<dt>Quellpfad: Dateifreigabename für universelle Benennungskonvention (Universal Naming Convention, UNC), Servername für Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; Signaturtyp &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="1b184-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-698">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-699">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-699">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-700">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-700">Antimalware</span></span></li>
<li><span data-ttu-id="1b184-701">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-702">
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder Vollständig oder Delta.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; Aktuelle &gt; </dt>
<dt>Modulversion des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>
<dt>Vorherige &lt; &gt; Modulversion:</dt>Frühere Modulversion
<dt>Fehlercode: &lt; Fehlercode Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-702">
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
<span data-ttu-id="1b184-703">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-704">Dieser Fehler tritt auf, wenn bei der Aktualisierung von Definitionen ein Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="1b184-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="1b184-705">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="1b184-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="1b184-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="1b184-707">Weitere Informationen zu diesem Fehler finden Sie in den Einträgen in der Datei %Windir%\WindowsUpdate.log.</span><span class="sxs-lookup"><span data-stu-id="1b184-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="1b184-708">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-709">Ereignis-ID: 2002</span><span class="sxs-lookup"><span data-stu-id="1b184-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-710">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-712">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-712">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-713">
<b>Das Antischalwaremodul wurde erfolgreich aktualisiert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-714">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-715">Die Version des Microsoft Defender Antivirus-Moduls wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="1b184-716">
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt>
<dt>Vorherige Modulversion: &lt; &gt; Modultyp</dt>der vorherigen Modulversion: Modultyp , entweder Antischalwaremodul oder
<dt> &lt; &gt; Netzwerkinspektionssystemmodul.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-717">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-718">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-718">No action is necessary.</span></span> <span data-ttu-id="1b184-719">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="1b184-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="1b184-720">Dieses Ereignis wird gemeldet, wenn das Antischalwaremodul erfolgreich aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-721">Ereignis-ID: 2003</span><span class="sxs-lookup"><span data-stu-id="1b184-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-722">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-724">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-724">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-725">
<b>Fehler beim Update des Antischalwaremoduls. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-726">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-727">Beim Versuch, das Modul zu aktualisieren, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="1b184-728">
<dt>Neue Modulversion:</dt>
<dt>Frühere Modulversion: &lt; &gt; Modultyp</dt>der vorherigen Modulversion: Modultyp , entweder Antischalwaremodul
<dt>oder &lt; &gt; Netzwerkinspektionssystemmodul.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-728">
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
<span data-ttu-id="1b184-729">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-730">Fehler beim Microsoft Defender Antivirus-Clientupdate.</span><span class="sxs-lookup"><span data-stu-id="1b184-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="1b184-731">Dieses Ereignis tritt auf, wenn der Client sich selbst nicht aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="1b184-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="1b184-732">Dieses Ereignis ist in der Regel auf eine Unterbrechung der Netzwerkverbindung während eines Updates bedingt.</span><span class="sxs-lookup"><span data-stu-id="1b184-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="1b184-733">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="1b184-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="1b184-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="1b184-735">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-736">Ereignis-ID: 2004</span><span class="sxs-lookup"><span data-stu-id="1b184-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-737">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-739">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-739">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-740">
<b>Beim Laden von Antischalwaredefinitionen ist ein Problem vorhanden. Das Antischalwaremodul versucht, den zuletzt bekannten guten Satz von Definitionen zu laden.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-741">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-742">Microsoft Defender Antivirus hat einen Fehler beim Laden von Signaturen festgestellt und versucht, zu einem bekannten Satz von Signaturen zurück zu kehren.</span><span class="sxs-lookup"><span data-stu-id="1b184-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="1b184-743">
<dt>Signaturen versucht:</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-743">
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
<span data-ttu-id="1b184-744">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-745">Der Microsoft Defender Antivirus-Client hat versucht, die neueste Definitionsdatei herunterzuladen und zu installieren, und es ist ein Fehler fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="1b184-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="1b184-746">Dieser Fehler kann auftreten, wenn auf dem Client beim Laden der Definitionen ein Fehler auftritt oder wenn die Datei beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="1b184-747">Microsoft Defender Antivirus versucht, zu einem bekannten Satz von Definitionen zurück zu kehren.</span><span class="sxs-lookup"><span data-stu-id="1b184-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="1b184-748">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="1b184-749">Starten Sie den Computer neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="1b184-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="1b184-750">Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-Website herunter.</a></span><span class="sxs-lookup"><span data-stu-id="1b184-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="1b184-751">Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="1b184-752">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-753">Ereignis-ID: 2005</span><span class="sxs-lookup"><span data-stu-id="1b184-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-754">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-756">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-756">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-757">
<b>Das Antischalwaremodul konnte nicht geladen werden, da die Antischalwareplattform veraltet ist. Die Antischalwareplattform wird das zuletzt bekannte gute Antischalwaremodul laden und versuchen, es zu aktualisieren.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-758">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-759">Microsoft Defender Antivirus konnte das Antischalwaremodul nicht laden, da die aktuelle Plattformversion nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="1b184-760">Microsoft Defender Antivirus kehrt zum letzten bekannten Modul zurück, und es wird versucht, ein Plattformupdate zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1b184-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="1b184-761">
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-762">Ereignis-ID: 2006</span><span class="sxs-lookup"><span data-stu-id="1b184-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-763">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-765">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-765">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-766">
<b>Fehler beim Plattformupdate. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-767">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-768">Beim Versuch, die Plattform zu aktualisieren, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="1b184-769">
<dt>Aktuelle Plattformversion: &lt; Fehlercode &gt; der aktuellen</dt>
<dt>Plattformversion: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-770">Ereignis-ID: 2007</span><span class="sxs-lookup"><span data-stu-id="1b184-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-771">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-773">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-773">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-774">
<b>Die Plattform ist bald veraltet. Laden Sie die neueste Plattform herunter, um den aktuellen Schutz auf dem neuesten Stand zu halten.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-775">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-776">Microsoft Defender Antivirus benötigt in Kürze eine neuere Plattformversion, um zukünftige Versionen des Antischammungsmoduls zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1b184-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="1b184-777">Laden Sie die neueste Microsoft Defender Antivirus-Plattform herunter, um den bestmöglichen Schutz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="1b184-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="1b184-778">
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-779">Ereignis-ID: 2010</span><span class="sxs-lookup"><span data-stu-id="1b184-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-780">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-782">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-782">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-783">
<b>Das Antischalwaremodul verwendet den dynamischen Signaturdienst, um zusätzliche Definitionen zu erhalten. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-784">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-785">Microsoft Defender Antivirus hat <i>den Dynamischen Signaturdienst verwendet,</i> um zusätzliche Signaturen abzurufen, um Ihren Computer zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1b184-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="1b184-786">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="1b184-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-787">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-788">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-788">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-789">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-789">Antimalware</span></span></li>
<li><span data-ttu-id="1b184-790">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-791">
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-792">Version</span><span class="sxs-lookup"><span data-stu-id="1b184-792">Version</span></span></li>
<li><span data-ttu-id="1b184-793">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-793">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-794">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-794">No limit</span></span></li>
<li><span data-ttu-id="1b184-795">Dauer</span><span class="sxs-lookup"><span data-stu-id="1b184-795">Duration</span></span></li>
</ul><span data-ttu-id="1b184-796">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Versionsnummer &gt; </dt>Dynamic Signature Compilation
<dt> &lt; Timestamp: Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-797">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="1b184-797">VDM version</span></span></li>
<li><span data-ttu-id="1b184-798">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-798">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-799">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-799">No limit</span></span></li>
</ul><span data-ttu-id="1b184-800">
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-801">Ereigniskennung: 2011</span><span class="sxs-lookup"><span data-stu-id="1b184-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-802">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-804">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-804">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-805">
<b>Der dynamische Signaturdienst hat die veralteten dynamischen Definitionen gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-806">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-807">Microsoft Defender Antivirus hat <i>den dynamischen Signaturdienst verwendet,</i> um veraltete Signaturen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="1b184-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="1b184-808">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="1b184-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-809">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-810">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-810">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-811">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-811">Antimalware</span></span></li>
<li><span data-ttu-id="1b184-812">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-813">
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-814">Version</span><span class="sxs-lookup"><span data-stu-id="1b184-814">Version</span></span></li>
<li><span data-ttu-id="1b184-815">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-815">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-816">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-816">No limit</span></span></li>
<li><span data-ttu-id="1b184-817">Dauer</span><span class="sxs-lookup"><span data-stu-id="1b184-817">Duration</span></span></li>
</ul><span data-ttu-id="1b184-818">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="1b184-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-819">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="1b184-819">VDM version</span></span></li>
<li><span data-ttu-id="1b184-820">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-820">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-821">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-821">No limit</span></span></li>
</ul><span data-ttu-id="1b184-822">
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-823">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-824">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b184-824">No action is necessary.</span></span> <span data-ttu-id="1b184-825">Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand.</span><span class="sxs-lookup"><span data-stu-id="1b184-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="1b184-826">Dieses Ereignis wird gemeldet, wenn der dynamische Signaturdienst veraltete dynamische Definitionen erfolgreich löscht.</span><span class="sxs-lookup"><span data-stu-id="1b184-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-827">Ereignis-ID: 2012</span><span class="sxs-lookup"><span data-stu-id="1b184-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-828">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-830">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-830">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-831">
<b>Das Antischantischungsmodul ist beim Versuch, den dynamischen Signaturdienst zu verwenden, auf einen Fehler gestoßen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-832">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-833">Microsoft Defender Antivirus hat einen Fehler beim Verwenden des <i>Dynamischen Signaturdiensts festgestellt.</i></span><span class="sxs-lookup"><span data-stu-id="1b184-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="1b184-834">
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="1b184-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-835">Antivirus</span></span></li>
<li><span data-ttu-id="1b184-836">Ansyware</span><span class="sxs-lookup"><span data-stu-id="1b184-836">Antispyware</span></span></li>
<li><span data-ttu-id="1b184-837">Antischalware</span><span class="sxs-lookup"><span data-stu-id="1b184-837">Antimalware</span></span></li>
<li><span data-ttu-id="1b184-838">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-839">
</dt>
<dt>Aktuelle Modulversion: &lt; Fehlercode &gt; der aktuellen</dt>
<dt>Modulversion: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt> Dynamischer Signaturtyp: &lt; Dynamischer &gt; Signaturtyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-840">Version</span><span class="sxs-lookup"><span data-stu-id="1b184-840">Version</span></span></li>
<li><span data-ttu-id="1b184-841">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-841">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-842">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-842">No limit</span></span></li>
<li><span data-ttu-id="1b184-843">Dauer</span><span class="sxs-lookup"><span data-stu-id="1b184-843">Duration</span></span></li>
</ul><span data-ttu-id="1b184-844">
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Versionsnummer &gt; </dt>Dynamic Signature Compilation
<dt> &lt; Timestamp: Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-845">VDM-Version</span><span class="sxs-lookup"><span data-stu-id="1b184-845">VDM version</span></span></li>
<li><span data-ttu-id="1b184-846">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="1b184-846">Timestamp</span></span></li>
<li><span data-ttu-id="1b184-847">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="1b184-847">No limit</span></span></li>
</ul><span data-ttu-id="1b184-848">
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-849">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-850">Überprüfen Sie ihre Internetverbindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1b184-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-851">Ereignis-ID: 2013</span><span class="sxs-lookup"><span data-stu-id="1b184-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-852">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-854">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-854">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-855">
<b>Der dynamische Signaturdienst hat alle dynamischen Definitionen gelöscht. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-856">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-857">Microsoft Defender Antivirus hat alle <i>Signaturen des dynamischen Signaturdiensts</i> verworfen.</span><span class="sxs-lookup"><span data-stu-id="1b184-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="1b184-858">
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-859">Ereignis-ID: 2020</span><span class="sxs-lookup"><span data-stu-id="1b184-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-860">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-862">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-862">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-863">
<b>Das Antischalwaremodul hat eine clean-Datei heruntergeladen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-864">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-865">Microsoft Defender Antivirus hat eine neue Datei heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="1b184-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="1b184-866">
<dt>Dateiname: &lt; Dateiname &gt; Name der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Aktuelle Modulversion: Aktuelle &lt; Modulversion &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-867">Ereignis-ID: 2021</span><span class="sxs-lookup"><span data-stu-id="1b184-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-868">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-870">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-870">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-871">
<b>Fehler beim Herunterladen einer sauberen Datei durch das Antischalwaremodul. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-872">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-873">Bei Microsoft Defender Antivirus ist ein Fehler beim Herunterladen einer sauberen Datei aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="1b184-874">
<dt>Dateiname: &lt; Dateiname &gt; Name der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Aktuelle Modulversion: Aktuelle &lt; Modulversion &gt; </dt>
<dt>Fehlercode: &lt; Fehlercode Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-874">
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
<span data-ttu-id="1b184-875">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-876">Überprüfen Sie ihre Internetverbindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1b184-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="1b184-877">Beim Microsoft Defender Antivirus-Client ist ein Fehler aufgetreten, wenn er den dynamischen Signaturdienst zum Herunterladen der neuesten Definitionen für eine bestimmte Bedrohung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b184-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="1b184-878">Dieser Fehler wird wahrscheinlich durch ein Netzwerkverbindungsproblem verursacht.</span><span class="sxs-lookup"><span data-stu-id="1b184-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-879">Ereignis-ID: 2030</span><span class="sxs-lookup"><span data-stu-id="1b184-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-880">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-882">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-882">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-883">
<b>Das Antischadwaremodul wurde heruntergeladen und ist so konfiguriert, dass es beim nächsten Systemneustart offline ausgeführt wird.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-884">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-885">Microsoft Defender Antivirus hat den Offline antivirus heruntergeladen und so konfiguriert, dass er beim nächsten Neustart ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-886">Ereignis-ID: 2031</span><span class="sxs-lookup"><span data-stu-id="1b184-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-887">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-889">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-889">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-890">
<b>Das Antischadwaremodul konnte einen Offlinescan nicht herunterladen und konfigurieren.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-891">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-892">Bei Microsoft Defender Antivirus ist ein Fehler beim Herunterladen und Konfigurieren von Offline antivirus aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b184-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="1b184-893">
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-894">Ereignis-ID: 2040</span><span class="sxs-lookup"><span data-stu-id="1b184-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-895">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-897">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-897">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-898">
<b>Die Antischalwareunterstützung für diese Betriebssystemversion wird bald beendet. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-899">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-900">Die Unterstützung für Ihr Betriebssystem läuft in Kürze ab.</span><span class="sxs-lookup"><span data-stu-id="1b184-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="1b184-901">Das Ausführen von Microsoft Defender Antivirus auf einem Betriebssystem ohne Support ist keine geeignete Lösung zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="1b184-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-902">Ereigniskennung: 2041</span><span class="sxs-lookup"><span data-stu-id="1b184-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-903">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-905">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-905">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-906">
<b>Die Antischalwareunterstützung für dieses Betriebssystem wurde beendet. Sie müssen das Betriebssystem aktualisieren, damit die Unterstützung fortgesetzt wird. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-907">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-908">Die Unterstützung für Ihr Betriebssystem ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="1b184-908">The support for your operating system has expired.</span></span> <span data-ttu-id="1b184-909">Das Ausführen von Microsoft Defender Antivirus auf einem Betriebssystem ohne Support ist keine geeignete Lösung zum Schutz vor Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="1b184-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-910">Ereignis-ID: 2042</span><span class="sxs-lookup"><span data-stu-id="1b184-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-911">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-913">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-913">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-914">
<b>Das Antischalwaremodul unterstützt dieses Betriebssystem nicht mehr und schützt Ihr System nicht mehr vor Schadsoftware. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-915">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-916">Die Unterstützung für Ihr Betriebssystem ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="1b184-916">The support for your operating system has expired.</span></span> <span data-ttu-id="1b184-917">Microsoft Defender Antivirus wird auf Ihrem Betriebssystem nicht mehr unterstützt, funktioniert nicht mehr und schützt nicht vor Schadsoftwarebedrohungen.</span><span class="sxs-lookup"><span data-stu-id="1b184-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-918">Ereignis-ID: 3002</span><span class="sxs-lookup"><span data-stu-id="1b184-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-919">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-921">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-921">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-922">
<b>Beim Echtzeitschutz ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-923">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-924">Microsoft Defender Antivirus Real-Time Protection-Funktion ist auf einen Fehler und einen Fehler gestoßen.</span><span class="sxs-lookup"><span data-stu-id="1b184-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="1b184-925">
<dt>Feature: &lt; Feature &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-926">On Access</span><span class="sxs-lookup"><span data-stu-id="1b184-926">On Access</span></span></li>
<li><span data-ttu-id="1b184-927">Internet Explorer-Downloads und Microsoft Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="1b184-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="1b184-928">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="1b184-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="1b184-929">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-930">
</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus echtzeitschutz ein Feature neu gestartet hat.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-931">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-932">Starten Sie das System neu, und führen Sie dann einen vollständigen Scan aus,&#39;das System möglicherweise einige Zeit nicht geschützt war.</span><span class="sxs-lookup"><span data-stu-id="1b184-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="1b184-933">Der Microsoft Defender Antivirus-Client&#39;Echtzeitschutzfunktion auf einen Fehler gestoßen, da einer der Dienste nicht gestartet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1b184-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="1b184-934">Wenn darauf eine 3007-Ereignis-ID folgt, war der Fehler temporär, und der Antischalwareclient wurde nach dem Fehler wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1b184-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-935">Ereignis-ID: 3007</span><span class="sxs-lookup"><span data-stu-id="1b184-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-936">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-938">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-938">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-939">
<b>Echtzeitschutz nach einem Fehler wiederhergestellt. Es wird empfohlen, eine vollständige Systemscan ausführen, wenn dieser Fehler angezeigt wird. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-940">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-941">Microsoft Defender Antivirus Real-time Protection hat ein Feature neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b184-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="1b184-942">Es wird empfohlen, dass Sie eine vollständige Systemscan ausführen, um Elemente zu erkennen, die während des Herunters dieses Agents möglicherweise verpasst wurden.</span><span class="sxs-lookup"><span data-stu-id="1b184-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="1b184-943">
<dt>Feature: &lt; Feature &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-944">On Access</span><span class="sxs-lookup"><span data-stu-id="1b184-944">On Access</span></span></li>
<li><span data-ttu-id="1b184-945">IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="1b184-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="1b184-946">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="1b184-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="1b184-947">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-948">
</dt>
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus echtzeitschutz ein Feature neu gestartet hat.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-949">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-950">Das Echtzeitschutzfeature wurde neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b184-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="1b184-951">Wenn dieses Ereignis erneut eintritt, wenden Sie sich <a href="https://go.microsoft.com/fwlink/?LinkId=215491">an den technischen Support von Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="1b184-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-952">Ereignis-ID: 5000</span><span class="sxs-lookup"><span data-stu-id="1b184-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-953">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-955">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-955">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-956">
<b>Echtzeitschutz ist aktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-957">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-958">Die Echtzeitschutzprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-959">Ereignis-ID: 5001</span><span class="sxs-lookup"><span data-stu-id="1b184-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-960">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-962">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-962">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-963">
<b>Der Echtzeitschutz ist deaktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-964">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-965">Die Echtzeitschutzprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-966">Ereignis-ID: 5004</span><span class="sxs-lookup"><span data-stu-id="1b184-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-967">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-969">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-969">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-970">
<b>Die Echtzeitschutzkonfiguration wurde geändert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-971">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-972">Die Konfiguration von Microsoft Defender Antivirus-Echtzeitschutzfeatures hat sich geändert.</span><span class="sxs-lookup"><span data-stu-id="1b184-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="1b184-973">
<dt>Feature: &lt; Feature &gt; , z. B.:</span><span class="sxs-lookup"><span data-stu-id="1b184-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="1b184-974">On Access</span><span class="sxs-lookup"><span data-stu-id="1b184-974">On Access</span></span></li>
<li><span data-ttu-id="1b184-975">IE-Downloads und Outlook Express-Anlagen</span><span class="sxs-lookup"><span data-stu-id="1b184-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="1b184-976">Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="1b184-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="1b184-977">Netzwerkinspektionssystem</span><span class="sxs-lookup"><span data-stu-id="1b184-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="1b184-978">
</dt>
<dt>Konfiguration: </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-979">Ereignis-ID: 5007</span><span class="sxs-lookup"><span data-stu-id="1b184-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-980">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-982">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-982">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-983">
<b>Die Konfiguration der Antischalwareplattform wurde geändert.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-984">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-985">Die Microsoft Defender Antivirus-Konfiguration hat sich geändert.</span><span class="sxs-lookup"><span data-stu-id="1b184-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="1b184-986">Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.</span><span class="sxs-lookup"><span data-stu-id="1b184-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="1b184-987">
<dt>Alter Wert: &lt; Alter Wert Zahl &gt; Alter Antiviruskonfigurationswert.</dt> 
<dt>Neuer Wert: &lt; Neue Wertnummer &gt; Neuer Antiviruskonfigurationswert.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-988">Ereignis-ID: 5008</span><span class="sxs-lookup"><span data-stu-id="1b184-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-989">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-991">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-991">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-992">
<b>Beim Antischantischungsmodul ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-993">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-994">Das Microsoft Defender Antivirus-Modul wurde aufgrund eines unerwarteten Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="1b184-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="1b184-995">
<dt>Fehlertyp: &lt; Fehlertyp &gt; , z. B.: Crash or Hang</dt>Exception
<dt>Code: Error &lt; code &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-996">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-997">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="1b184-998">Versuchen Sie, den Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1b184-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="1b184-999">Geben Sie für Antischansoftware, Antivirensoftware und Spyware an einer Eingabeaufforderung mit erhöhten Rechten <b>net stop msmpsvc</b>ein, und geben Sie dann <b>net start msmpsvc</b> ein, um das Antischantischungsmodul neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1b184-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="1b184-1000">Geben <i></i>Sie für das Netzwerkinspektionssystem an einer Eingabeaufforderung mit erhöhten Rechten net <b>start nissrv</b>ein, und geben Sie dann <b>net start nissrv</b> ein, um das <i>Netzwerkinspektionssystemmodul</i> mithilfe der NiSSRV.exe neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1b184-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="1b184-1001">Wenn es auf dieselbe Weise fehlschlägt, suchen Sie den Fehlercode, indem Sie <b></b> auf die <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-Website</a> zugreifen und die Fehlernummer im Feld Suchen eingeben, und wenden Sie sich an <a href="https://go.microsoft.com/fwlink/?LinkId=215491">den technischen Support</a>von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b184-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1002">Benutzeraktion:</span><span class="sxs-lookup"><span data-stu-id="1b184-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1003">Das Microsoft Defender Antivirus-Clientmodul wurde aufgrund eines unerwarteten Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="1b184-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="1b184-1004">So behandeln Sie dieses Ereignis:</span><span class="sxs-lookup"><span data-stu-id="1b184-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="1b184-1005">Führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="1b184-1006">Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="1b184-1007">Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1008">Ereignis-ID: 5009</span><span class="sxs-lookup"><span data-stu-id="1b184-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1009">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1011">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1012">
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist aktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1013">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1014">Die Überprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1015">Ereignis-ID: 5010</span><span class="sxs-lookup"><span data-stu-id="1b184-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1016">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1018">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1019">
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1020">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1021">Die Überprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1022">Ereignis-ID: 5011</span><span class="sxs-lookup"><span data-stu-id="1b184-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1023">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1025">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1026">
<b>Die Überprüfung auf Viren ist aktiviert.</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1027">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1028">Die Überprüfung von Microsoft Defender Antivirus auf Viren wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1029">Ereignis-ID: 5012</span><span class="sxs-lookup"><span data-stu-id="1b184-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1030">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1032">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1033">
<b>Die Überprüfung auf Viren ist deaktiviert. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1034">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1035">Die Überprüfung von Microsoft Defender Antivirus auf Viren ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1036">Ereignis-ID: 5100</span><span class="sxs-lookup"><span data-stu-id="1b184-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1037">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1039">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1040">
<b>Die Antischalwareplattform läuft bald ab. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1041">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1042">Microsoft Defender Antivirus hat eine Nachfrist eingegeben und läuft bald ab.</span><span class="sxs-lookup"><span data-stu-id="1b184-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="1b184-1043">Nach ablaufen deaktiviert dieses Programm den Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software.</span><span class="sxs-lookup"><span data-stu-id="1b184-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="1b184-1044">
<dt>Ablaufgrund: Der Grund, warum Microsoft Defender Antivirus abläuft.</dt> 
<dt>Ablaufdatum: Das Datum, an dem Microsoft Defender Antivirus abläuft.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1045">Ereignis-ID: 5101</span><span class="sxs-lookup"><span data-stu-id="1b184-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="1b184-1046">Symbolischer Name:</span><span class="sxs-lookup"><span data-stu-id="1b184-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="1b184-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1048">Meldung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="1b184-1049">
<b>Die Antischalwareplattform ist abgelaufen. </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1050">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="1b184-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="1b184-1051">Die Kulanzfrist für Microsoft Defender Antivirus ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="1b184-1052">Der Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="1b184-1053">
<dt>Ablaufgrund:</dt>
<dt>Ablaufdatum: </dt> 
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="1b184-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus-Clientfehlercodes Wenn Microsoft Defender Antivirus Probleme hat, erhalten Sie in der Regel einen Fehlercode, der Ihnen bei der Problembehandlung hilft.</span><span class="sxs-lookup"><span data-stu-id="1b184-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="1b184-1055">Meistens bedeutet ein Fehler, dass beim Installieren eines Updates ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="1b184-1056">Dieser Abschnitt enthält die folgenden Informationen zu Microsoft Defender Antivirus-Clientfehlern.</span><span class="sxs-lookup"><span data-stu-id="1b184-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="1b184-1057">-   Der Fehlercode -   Der mögliche Grund für den Fehler Hinweise zu den jetzt zu -   tunen</span><span class="sxs-lookup"><span data-stu-id="1b184-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="1b184-1058">Verwenden Sie die Informationen in diesen Tabellen, um Bei der Problembehandlung von Microsoft Defender Antivirus-Fehlercodes zu helfen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="1b184-1059">Fehlercode: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="1b184-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="1b184-1060">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1060">Message</span></span></td>
<td><span data-ttu-id="1b184-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1062">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="1b184-1063">Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="1b184-1064">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="1b184-1065">Überprüfen Sie den verfügbaren Speicher auf Ihrem Gerät.</span><span class="sxs-lookup"><span data-stu-id="1b184-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="1b184-1066">Schließen Sie alle nicht verwendeten Anwendungen, die ausgeführt werden, um Speicherplatz auf Ihrem Gerät frei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b184-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="1b184-1067">Starten Sie das Gerät neu, und führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1068">Fehlercode: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="1b184-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="1b184-1069">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1069">Message</span></span></td>
<td><span data-ttu-id="1b184-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1071">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1072">Dieser Fehler gibt an, dass möglicherweise ein Problem mit Ihrem Sicherheitsprodukt vor liegt.</span><span class="sxs-lookup"><span data-stu-id="1b184-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="1b184-1073">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="1b184-1074">Aktualisieren Sie die Definitionen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1074">Update the definitions.</span></span> <span data-ttu-id="1b184-1075">Eine der beiden:</span><span class="sxs-lookup"><span data-stu-id="1b184-1075">Either:</span></span><ol>
<li><span data-ttu-id="1b184-1076">Klicken Sie <b>auf der</b> Registerkarte <b>Update</b> in Microsoft Defender Antivirus auf die Schaltfläche Definitionen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1b184-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="1b184-1077">Oder:</span><span class="sxs-lookup"><span data-stu-id="1b184-1077">Or,</span></span>
</li>
<li><span data-ttu-id="1b184-1078">Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-Website herunter.</a></span><span class="sxs-lookup"><span data-stu-id="1b184-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="1b184-1079">Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b184-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="1b184-1080">Führen Sie einen vollständigen Scan aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="1b184-1081">Starten Sie das Gerät neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="1b184-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1082">Fehlercode: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="1b184-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="1b184-1083">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1083">Message</span></span></td>
<td><span data-ttu-id="1b184-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1085">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1086">Dieser Fehler weist darauf hin, dass möglicherweise ein Modulkonfigurationsfehler aufgetreten ist. Häufig ist dies mit Eingabedaten verbunden, die eine einwandfreie Funktionsweise des Moduls nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1087">Fehlercode: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="1b184-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1088">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1088">Message</span></span></td>
<td><span data-ttu-id="1b184-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1090">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1091">Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus eine Bedrohung nicht unter Quarantäne stellen konnte.</span><span class="sxs-lookup"><span data-stu-id="1b184-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1092">Fehlercode: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="1b184-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1093">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1093">Message</span></span></td>
<td><span data-ttu-id="1b184-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1095">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1096">Dieser Fehler gibt an, dass ein Neustart erforderlich ist, um die Bedrohungsentfernung abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="1b184-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="1b184-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="1b184-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1098">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1098">Message</span></span></td>
<td><span data-ttu-id="1b184-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1100">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1101">Dieser Fehler weist darauf hin, dass die Bedrohung möglicherweise nicht mehr auf den Medien vorhanden ist, oder Schadsoftware hält Sie möglicherweise am Scannen Ihres Geräts ab.</span><span class="sxs-lookup"><span data-stu-id="1b184-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="1b184-1102">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="1b184-1103">Führen Sie <a href="https://www.microsoft.com/security/scanner/default.aspx">den Microsoft Safety Scanner</a> aus, und aktualisieren Sie die Sicherheitssoftware, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="1b184-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1104">Fehlercode: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="1b184-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="1b184-1105">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1105">Message</span></span></td>
<td><span data-ttu-id="1b184-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1107">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1108">Dieser Fehler gibt an, dass möglicherweise eine vollständige Systemscan erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="1b184-1109">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1109">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1110">Führen Sie eine vollständige Systemscan aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1111">Fehlercode: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="1b184-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1112">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1112">Message</span></span></td>
<td><span data-ttu-id="1b184-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1114">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1115">Dieser Fehler gibt an, dass manuelle Schritte erforderlich sind, um die Bedrohungsentfernung abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="1b184-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1116">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1116">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1117">Führen Sie die manuellen Korrekturschritte aus, die in <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">der Microsoft Malware Protection-Enzyklopädie beschrieben sind.</a></span><span class="sxs-lookup"><span data-stu-id="1b184-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="1b184-1118">Sie finden einen bedrohungsspezifischen Link im Ereignisverlauf.</span><span class="sxs-lookup"><span data-stu-id="1b184-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1119">Fehlercode: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="1b184-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1120">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1120">Message</span></span></td>
<td><span data-ttu-id="1b184-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1122">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1123">Dieser Fehler gibt an, dass das Entfernen innerhalb des Containertyps möglicherweise nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1b184-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1124">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1124">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1125">Microsoft Defender Antivirus ist nicht in der Lage, im Archiv erkannte Bedrohungen zu beabwehren.</span><span class="sxs-lookup"><span data-stu-id="1b184-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="1b184-1126">Erwägen Sie, die erkannten Ressourcen manuell zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1127">Fehlercode: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="1b184-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1128">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1128">Message</span></span></td>
<td><span data-ttu-id="1b184-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1130">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1131">Dieser Fehler weist darauf hin, dass das Entfernen niedriger und mittlerer Bedrohungen möglicherweise deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1132">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1132">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1133">Überprüfen Sie die erkannten Bedrohungen, und beheben Sie sie nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="1b184-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1134">Fehlercode: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="1b184-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1135">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1135">Message</span></span></td>
<td><span data-ttu-id="1b184-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1137">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1138">Dieser Fehler gibt an, dass ein erneutes Scannen der Bedrohung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1139">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1139">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1140">Führen Sie eine vollständige Systemscan aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1141">Fehlercode: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="1b184-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1142">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1142">Message</span></span></td>
<td><span data-ttu-id="1b184-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="1b184-1144">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1145">Dieser Fehler gibt an, dass eine Offlinescan erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1146">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1146">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1147">Führen Sie Microsoft Defender Antivirus offline aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1b184-1148">Informationen dazu finden Sie im <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Microsoft Defender Antivirus-Offlineartikel</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="1b184-1149">Fehlercode: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="1b184-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="1b184-1150">Message</span><span class="sxs-lookup"><span data-stu-id="1b184-1150">Message</span></span></td>
<td><span data-ttu-id="1b184-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="1b184-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="1b184-1152">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="1b184-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="1b184-1153">Dieser Fehler gibt an, dass Microsoft Defender Antivirus die aktuelle Version der Plattform nicht unterstützt und eine neue Version der Plattform erfordert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="1b184-1154">Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1154">Resolution</span></span></td><td>
<span data-ttu-id="1b184-1155">Sie können Microsoft Defender Antivirus nur unter Windows 10 verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b184-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="1b184-1156">Für Windows 8 Windows 7 und Windows Vista können Sie <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection verwenden.</a></span><span class="sxs-lookup"><span data-stu-id="1b184-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="1b184-1157">

<a id="internal-error-codes"></a> Die folgenden Fehlercodes werden bei internen Tests von Microsoft Defender Antivirus verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b184-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="1b184-1158">Wenn diese Fehler angezeigt werden, können Sie versuchen, Definitionen [zu](manage-updates-baselines-microsoft-defender-antivirus.md) aktualisieren und einen erneuten Scan direkt auf dem Endpunkt zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1b184-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="1b184-1159">Interne Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="1b184-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="1b184-1160"><b>Fehlercode</b></span><span class="sxs-lookup"><span data-stu-id="1b184-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="1b184-1161">Angezeigte Nachricht</span><span class="sxs-lookup"><span data-stu-id="1b184-1161">Message displayed</span></span></th>
<th><span data-ttu-id="1b184-1162">Mögliche Ursache für Fehler und Lösung</span><span class="sxs-lookup"><span data-stu-id="1b184-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="1b184-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="1b184-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="1b184-1165">Überprüfen Sie Ihre Internetverbindung, und führen Sie den Scan erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1b184-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="1b184-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="1b184-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="1b184-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="1b184-1168">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="1b184-1168">This is an internal error.</span></span> <span data-ttu-id="1b184-1169">Die Ursache ist nicht klar definiert.</span><span class="sxs-lookup"><span data-stu-id="1b184-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="1b184-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="1b184-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="1b184-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="1b184-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="1b184-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="1b184-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="1b184-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="1b184-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="1b184-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="1b184-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="1b184-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="1b184-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="1b184-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="1b184-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="1b184-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="1b184-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="1b184-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="1b184-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="1b184-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="1b184-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="1b184-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="1b184-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="1b184-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="1b184-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="1b184-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="1b184-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="1b184-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="1b184-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="1b184-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="1b184-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="1b184-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="1b184-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="1b184-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="1b184-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="1b184-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="1b184-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="1b184-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="1b184-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="1b184-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="1b184-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="1b184-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="1b184-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="1b184-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="1b184-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="1b184-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="1b184-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="1b184-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="1b184-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="1b184-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="1b184-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="1b184-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="1b184-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="1b184-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="1b184-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="1b184-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="1b184-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="1b184-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="1b184-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="1b184-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="1b184-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="1b184-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="1b184-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="1b184-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="1b184-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="1b184-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="1b184-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="1b184-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="1b184-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="1b184-1238">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="1b184-1238">This is an internal error.</span></span> <span data-ttu-id="1b184-1239">Es kann ausgelöst werden, wenn die Schadsoftwareentfernung nicht erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="1b184-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="1b184-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="1b184-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="1b184-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="1b184-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="1b184-1242">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="1b184-1242">This is an internal error.</span></span> <span data-ttu-id="1b184-1243">Es kann ausgelöst worden sein, wenn eine Überprüfung nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1b184-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="1b184-1244">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1b184-1244">Related topics</span></span>

- [<span data-ttu-id="1b184-1245">Bericht zum Schutz von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1b184-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1b184-1246">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b184-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)