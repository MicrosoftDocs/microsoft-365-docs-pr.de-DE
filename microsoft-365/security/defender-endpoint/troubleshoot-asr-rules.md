---
title: Melden und Behandeln von Microsoft Defender for Endpoint-ASR-Regeln
description: In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint -ASR-Regeln melden und Behandeln von Problemen behandeln.
keywords: Attack Surface Reduction Rules, Asr, Hips, Host Intrusion Prevention System, Protection Rules, Anti-Exploit, Antiexploit, Exploit, Infection Prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246143"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="a729c-104">Melden und Behandeln von Microsoft Defender für ATP-ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="a729c-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a729c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a729c-105">**Applies to:**</span></span>

- [<span data-ttu-id="a729c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a729c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a729c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a729c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a729c-108">Das Microsoft 365 Security Center ist die neue Schnittstelle für die Überwachung und Verwaltung der Sicherheit in Ihren Microsoft-Identitäten, Daten, Geräten, Apps und Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="a729c-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="a729c-109">Hier können Sie den Sicherheitsstatus Ihrer Organisation ganz einfach anzeigen, Geräte, Benutzer und Apps konfigurieren sowie Benachrichtigungen zu verdächtigen Aktivitäten erhalten.</span><span class="sxs-lookup"><span data-stu-id="a729c-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="a729c-110">Das Microsoft 365 Security Center ist dazu bestimmt, Sicherheitsadministratoren und Sicherheitsteams zu ermöglichen, Verwaltung und Schutz Ihrer Organisation zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a729c-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="a729c-111">Besuchen Sie Microsoft 365 Security Center unter https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="a729c-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="a729c-112">In Microsoft 365 Security Center bieten wir Ihnen einen vollständigen Blick auf die aktuelle Konfiguration und Ereignisse von ASR-Regeln in Ihrem Nachlass.</span><span class="sxs-lookup"><span data-stu-id="a729c-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="a729c-113">Beachten Sie, dass Ihre Geräte in den Microsoft Defender for Endpoint-Dienst integrierte werden müssen, damit diese Berichte aufgefüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="a729c-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="a729c-114">Hier ist ein Screenshot der Microsoft 365 Security Center (unter **Berichte**  >  **Geräte**  >  **Attack surface reduction**).</span><span class="sxs-lookup"><span data-stu-id="a729c-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="a729c-115">Wählen Sie auf Geräteebene **im** Bereich Attack **surface reduction** rules die Option Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="a729c-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="a729c-116">Der folgende Bildschirm wird angezeigt, auf dem Sie ein bestimmtes Gerät auswählen und die konfiguration der einzelnen ASR-Regel überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="a729c-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Bildschirm &quot;ASR-Regeln&quot;":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="a729c-118">Microsoft Defender for Endpoint – Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="a729c-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="a729c-119">Eines der leistungsstärksten Features von Microsoft Defender for Endpoint ist die erweiterte Suche.</span><span class="sxs-lookup"><span data-stu-id="a729c-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="a729c-120">Wenn Sie mit der erweiterten Suche nicht vertraut sind, verweisen Sie proaktiv auf Bedrohungen mit [erweiterter Suche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a729c-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="a729c-121">Bei der erweiterten Suche handelt es sich um ein abfragebasiertes (Kusto Query Language)-Tool zur Bedrohungssuche, mit dem Sie bis zu 30 Tage der erfassten (unformatierten) Daten erkunden können, die MDE Endpoint Detection and Response (EDR) von allen Computern sammelt.</span><span class="sxs-lookup"><span data-stu-id="a729c-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="a729c-122">Durch die erweiterte Suche können Sie Ereignisse proaktiv überprüfen, um nach interessanten Indikatoren und Entitäten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a729c-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="a729c-123">Der flexible Zugriff auf Daten hilft bei der ungesübten Suche nach bekannten und potenziellen Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="a729c-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="a729c-124">Durch die erweiterte Suche ist es möglich, Informationen zu ASR-Regeln zu extrahieren, Berichte zu erstellen und detaillierte Informationen zum Kontext eines bestimmten ASR-Regel-Audit- oder -Blockereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a729c-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="a729c-125">ASR-Regelereignisse können in der DeviceEvents-Tabelle im Abschnitt erweiterte Suche des Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a729c-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a729c-126">Eine einfache Abfrage wie die folgende kann beispielsweise alle Ereignisse melden, die über ASR-Regeln als Datenquelle verfügen, für die letzten 30 Tage und fasst sie durch die ActionType-Anzahl zusammen, dass es sich in diesem Fall um den tatsächlichen Codenamen der ASR-Regel handeln wird.</span><span class="sxs-lookup"><span data-stu-id="a729c-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Erweiterte Suchabfrage":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Erweiterter Jagdbildschirm":::

<span data-ttu-id="a729c-129">Mit der erweiterten Suche können Sie die Abfragen nach Ihren Wünschen gestalten, sodass Sie sehen können, was geschieht, unabhängig davon, ob Sie auf einem einzelnen Computer etwas bestimmen oder Einblicke aus Ihrer gesamten Umgebung extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a729c-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="a729c-130">Microsoft Defender for Endpoint-Computerzeitachse</span><span class="sxs-lookup"><span data-stu-id="a729c-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="a729c-131">Eine Alternative zur erweiterten Suche, jedoch mit einem schmaleren Bereich, ist die Microsoft Defender for Endpoint-Computerzeitachse.</span><span class="sxs-lookup"><span data-stu-id="a729c-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="a729c-132">Sie können alle erfassten Ereignisse eines Geräts in den letzten sechs Monaten im Microsoft Defender Security Center anzeigen, indem Sie zur Liste Computer einen bestimmten Computer auswählen und dann auf die Registerkarte Zeitachse klicken.</span><span class="sxs-lookup"><span data-stu-id="a729c-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="a729c-133">Nachfolgend sehen Sie einen Screenshot der Zeitachsenansicht dieser Ereignisse auf einem bestimmten Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="a729c-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="a729c-134">In dieser Ansicht können Sie die Ereignisliste basierend auf allen Ereignisgruppen im rechten Bereich filtern.</span><span class="sxs-lookup"><span data-stu-id="a729c-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="a729c-135">Sie können auch gekennzeichnete und ausführliche Ereignisse aktivieren oder deaktivieren, während Sie Warnungen anzeigen und einen Bildlauf durch die verlaufshistorische Zeitachse durchführen.</span><span class="sxs-lookup"><span data-stu-id="a729c-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft Defender Security Center-Zeitachse":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="a729c-137">How to troubleshoot ASR rules?</span><span class="sxs-lookup"><span data-stu-id="a729c-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="a729c-138">Die erste und unmittelbarste Möglichkeit besteht in der lokalen Überprüfung auf einem Windows-Gerät, welche ASR-Regeln mit den PowerShell-Cmdlets aktiviert sind (und deren Konfiguration).</span><span class="sxs-lookup"><span data-stu-id="a729c-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="a729c-139">Hier sind einige weitere Informationsquellen, die Windows, um die Auswirkungen und den Betrieb von ASR-Regeln zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a729c-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="a729c-140">Abfragen der aktiven Regeln</span><span class="sxs-lookup"><span data-stu-id="a729c-140">Querying which rules are active</span></span>
<span data-ttu-id="a729c-141">Eine der einfachsten Methoden, um zu ermitteln, ob DIE-Regeln bereits aktiviert sind – und, über ein PowerShell-Cmdlet, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="a729c-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="a729c-142">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a729c-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-Skript erhalten":::

<span data-ttu-id="a729c-144">Es sind mehrere ASR-Regeln mit unterschiedlichen konfigurierten Aktionen aktiv.</span><span class="sxs-lookup"><span data-stu-id="a729c-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="a729c-145">Zum Erweitern der obigen Informationen zu ASR-Regeln können Sie die Eigenschaften AttackSurfaceReductionRules_Ids **und/oder** **AttackSurfaceReductionRules_Actions.**</span><span class="sxs-lookup"><span data-stu-id="a729c-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="a729c-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a729c-146">Example:</span></span>

<span data-ttu-id="a729c-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="a729c-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference-Beispiel erhalten":::

<span data-ttu-id="a729c-149">Im obigen Beispiel werden alle IDs für ASR-Regeln mit einer anderen Einstellung als 0 (Nicht konfiguriert) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a729c-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="a729c-150">Im nächsten Schritt werden dann die tatsächlichen Aktionen (Blockieren oder Überwachen) aufgeführt, mit der jede Regel konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a729c-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="a729c-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="a729c-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference-Beispiel2 erhalten":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="a729c-153">Abfragen von Blockieren und Überwachen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a729c-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="a729c-154">ASR-Regelereignisse können im Windows Defender angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a729c-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="a729c-155">Öffnen Sie zum Zugriff Windows Ereignisanzeige, und navigieren Sie zu Anwendungen und **Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="a729c-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="event viewer scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="a729c-157">Microsoft Defender Malware Protection Logs</span><span class="sxs-lookup"><span data-stu-id="a729c-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="a729c-158">Sie können Regelereignisse auch über das dedizierte Befehlszeilentool Microsoft Defender Antivirus, das zum Verwalten und Konfigurieren und Automatisieren von Aufgaben bei Bedarf verwendet werden `*mpcmdrun.exe*` kann, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a729c-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="a729c-159">Dieses Hilfsprogramm finden Sie unter *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="a729c-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="a729c-160">Sie müssen ihn über eine Eingabeaufforderung mit erhöhten Rechten ausführen (d. h. als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="a729c-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="a729c-161">Geben Sie zum Generieren der Supportinformationen *MpCmdRun.exe -getfiles ein.*</span><span class="sxs-lookup"><span data-stu-id="a729c-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="a729c-162">Nach einer Weile werden mehrere Protokolle in einem Archiv (MpSupportFiles.cab) verpackt und in *C:\ProgramData\Microsoft\Windows Defender\Support verfügbar gemacht.*</span><span class="sxs-lookup"><span data-stu-id="a729c-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Malwareschutzprotokolle":::

<span data-ttu-id="a729c-164">Extrahieren Sie dieses Archiv, und Sie haben viele Dateien zur Problembehandlung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a729c-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="a729c-165">Die relevantesten Dateien sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a729c-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="a729c-166">**MPOperationalEvents.txt** – Diese Datei enthält die gleiche Informationsebene, die in der Ereignisanzeige für Windows Defender Betriebsprotokoll gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="a729c-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="a729c-167">**MPRegistry.txt** – In dieser Datei können Sie alle aktuellen konfigurationen Windows Defender analysieren, ab dem Zeitpunkt, zu dem die Supportprotokolle erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="a729c-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="a729c-168">**MPLog.txt** – Dieses Protokoll enthält ausführlichere Informationen zu allen Aktionen/Vorgängen der Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="a729c-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
