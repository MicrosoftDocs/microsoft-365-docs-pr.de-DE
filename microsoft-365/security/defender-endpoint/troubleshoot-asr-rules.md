---
title: Melden und Beheben von Problemen mit Microsoft Defender für Endpunkt-ASR-Regeln
description: In diesem Thema wird beschrieben, wie Microsoft Defender für Endpunkt-ASR-Regeln gemeldet und Problembehandlung ausgeführt wird.
keywords: Attack Surface Reduction-Regeln, Asr, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsverhinderung, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 65e3e8d1baef7ca4440824c9a262f0b5f696b657
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194745"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="b5319-104">Melden und Beheben von Problemen mit Microsoft Defender für ATP ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="b5319-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5319-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b5319-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5319-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b5319-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b5319-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5319-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b5319-108">Das Microsoft 365 Security Center ist die neue Schnittstelle für die Überwachung und Verwaltung der Sicherheit über Ihre Microsoft-Identitäten, Daten, Geräte, Apps und Infrastruktur hinweg.</span><span class="sxs-lookup"><span data-stu-id="b5319-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="b5319-109">Hier können Sie den Sicherheitsstatus Ihrer Organisation ganz einfach anzeigen, Geräte, Benutzer und Apps konfigurieren sowie Benachrichtigungen zu verdächtigen Aktivitäten erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5319-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="b5319-110">Das Microsoft 365 Security Center ist dazu bestimmt, Sicherheitsadministratoren und Sicherheitsteams zu ermöglichen, Verwaltung und Schutz Ihrer Organisation zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b5319-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="b5319-111">Besuchen Sie das Microsoft 365 Security Center unter https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="b5319-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="b5319-112">In Microsoft 365 Security Center bieten wir Ihnen einen vollständigen Überblick über die aktuelle KONFIGURATION und Ereignisse von ASR-Regeln in Ihrem Bestand.</span><span class="sxs-lookup"><span data-stu-id="b5319-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="b5319-113">Beachten Sie, dass Ihre Geräte in den Microsoft Defender für Endpunktdienst integriert werden müssen, damit diese Berichte ausgefüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="b5319-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="b5319-114">Hier ist ein Screenshot aus dem Microsoft 365 Security Center (unter **Attack** Surface Reduction für Berichte  >  **für Geräte).**  >  </span><span class="sxs-lookup"><span data-stu-id="b5319-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="b5319-115">Wählen Sie auf Geräteebene im Regelbereich zur Verringerung der **Angriffsfläche** die Option **"Konfiguration"** aus.</span><span class="sxs-lookup"><span data-stu-id="b5319-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="b5319-116">Der folgende Bildschirm wird angezeigt, auf dem Sie ein bestimmtes Gerät auswählen und dessen individuelle ASR-Regelkonfiguration überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="b5319-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR-Regelbildschirm":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="b5319-118">Microsoft Defender für Endpunkt – Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b5319-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="b5319-119">Eines der leistungsstärksten Features von Microsoft Defender für Endpunkt ist die erweiterte Suche.</span><span class="sxs-lookup"><span data-stu-id="b5319-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="b5319-120">Wenn Sie mit der erweiterten Suche nicht vertraut sind, suchen Sie [proaktiv nach Bedrohungen mit der erweiterten Suche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b5319-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="b5319-121">Die erweiterte Suche ist ein abfragebasiertes (Kusto Query Language) Bedrohungssuche-Tool, mit dem Sie bis zu 30 Tage der erfassten (unformatierten) Daten, die Defender für Endpunkt von Ihren Geräten erfasst.</span><span class="sxs-lookup"><span data-stu-id="b5319-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that Defender for Endpoint collects from your devices.</span></span> <span data-ttu-id="b5319-122">Durch die erweiterte Suche können Sie Ereignisse proaktiv untersuchen, um interessante Indikatoren und Entitäten zu finden.</span><span class="sxs-lookup"><span data-stu-id="b5319-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="b5319-123">Der flexible Zugriff auf Daten hilft bei der uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="b5319-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="b5319-124">Durch die erweiterte Suche ist es möglich, ASR-Regelinformationen zu extrahieren, Berichte zu erstellen und ausführliche Informationen zum Kontext einer bestimmten ASR-Regelüberwachung oder eines Bestimmten Blockereignisses abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5319-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="b5319-125">ASR-Regelereignisse können in der DeviceEvents-Tabelle im Abschnitt "Erweiterte Suche" des Microsoft Defender Security Center abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="b5319-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b5319-126">Beispielsweise kann eine einfache Abfrage wie die folgende alle Ereignisse melden, die ASR-Regeln als Datenquelle für die letzten 30 Tage aufweisen, und diese anhand der ActionType-Anzahl zusammenfassen, in diesem Fall ist dies der tatsächliche Codename der ASR-Regel.</span><span class="sxs-lookup"><span data-stu-id="b5319-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Erweiterte Suchabfrage":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Bildschirm &quot;Erweiterte Suche&quot;":::

<span data-ttu-id="b5319-129">Mit der erweiterten Suche können Sie die Abfragen nach Ihren Wünschen gestalten, damit Sie sehen können, was geschieht, unabhängig davon, ob Sie etwas auf einem einzelnen Computer anheften oder Einblicke aus Ihrer gesamten Umgebung extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b5319-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="b5319-130">Computerzeitachse von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b5319-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="b5319-131">Eine Alternative zur erweiterten Suche, jedoch mit einem schmaleren Bereich, ist die Microsoft Defender für Endpunkt-Computerzeitachse.</span><span class="sxs-lookup"><span data-stu-id="b5319-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="b5319-132">Sie können alle erfassten Ereignisse eines Geräts für die letzten sechs Monate im Microsoft Defender Security Center anzeigen, indem Sie zur Computerliste wechseln, einen bestimmten Computer auswählen und dann auf die Registerkarte Zeitachse klicken.</span><span class="sxs-lookup"><span data-stu-id="b5319-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="b5319-133">Unten ist ein Screenshot der Zeitachsenansicht dieser Ereignisse auf einem bestimmten Endpunkt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b5319-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="b5319-134">Aus dieser Ansicht können Sie die Ereignisliste basierend auf einer der Ereignisgruppen im rechten Bereich filtern.</span><span class="sxs-lookup"><span data-stu-id="b5319-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="b5319-135">Sie können auch gekennzeichnete und ausführliche Ereignisse aktivieren oder deaktivieren, während Sie Warnungen anzeigen und einen Bildlauf durch die verlaufsbezogene Zeitachse ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5319-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft Defender Security Center-Zeitachse":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="b5319-137">Problembehandlung bei ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="b5319-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="b5319-138">Die erste und direkteste Möglichkeit besteht darin, lokal auf einem Windows Gerät zu überprüfen, welche ASR-Regeln aktiviert sind (und deren Konfiguration) mithilfe der PowerShell-Cmdlets erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b5319-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="b5319-139">Hier sind einige weitere Informationsquellen, die Windows bietet, um die Auswirkungen und den Betrieb von ASR-Regeln zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b5319-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="b5319-140">Abfragen, welche Regeln aktiv sind</span><span class="sxs-lookup"><span data-stu-id="b5319-140">Querying which rules are active</span></span>
<span data-ttu-id="b5319-141">Eine der einfachsten Möglichkeiten, um festzustellen, ob ASR-Regeln bereits aktiviert sind, ist das PowerShell-Cmdlet "Get-MpPreference".</span><span class="sxs-lookup"><span data-stu-id="b5319-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="b5319-142">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b5319-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-Skript abrufen":::

<span data-ttu-id="b5319-144">Es sind mehrere ASR-Regeln mit unterschiedlichen konfigurierten Aktionen aktiv.</span><span class="sxs-lookup"><span data-stu-id="b5319-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="b5319-145">Um die oben genannten Informationen zu ASR-Regeln zu erweitern, können Sie die Eigenschaften **AttackSurfaceReductionRules_Ids** und/oder **AttackSurfaceReductionRules_Actions** verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5319-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="b5319-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b5319-146">Example:</span></span>

<span data-ttu-id="b5319-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*-AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="b5319-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="beispiel für &quot;get mpreference&quot;":::

<span data-ttu-id="b5319-149">Im obigen Beispiel werden alle IDs für ASR-Regeln angezeigt, deren Einstellung sich von 0 unterscheidet (nicht konfiguriert).</span><span class="sxs-lookup"><span data-stu-id="b5319-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="b5319-150">Im nächsten Schritt werden dann die tatsächlichen Aktionen (Blockieren oder Überwachen) aufgeführt, mit denen jede Regel konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b5319-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="b5319-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*-AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="b5319-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="b5319-153">Abfragen von Blockierungs- und Überwachungsereignissen</span><span class="sxs-lookup"><span data-stu-id="b5319-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="b5319-154">ASR-Regelereignisse können im Windows Defender-Protokoll angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5319-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="b5319-155">Um darauf zuzugreifen, öffnen Sie Windows Ereignisanzeige, und navigieren Sie zu **"Anwendungs- und Dienstprotokolle"**  >  **von Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="b5319-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="Ereignisanzeige scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="b5319-157">Microsoft Defender-Protokolle zum Schutz vor Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="b5319-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="b5319-158">Sie können Regelereignisse auch über das Microsoft Defender Antivirus dedizierte Befehlszeilentool anzeigen, das aufgerufen `*mpcmdrun.exe*` wird und zum Verwalten und Konfigurieren von Aufgaben verwendet werden kann, und Aufgaben bei Bedarf automatisieren.</span><span class="sxs-lookup"><span data-stu-id="b5319-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="b5319-159">Dieses Hilfsprogramm finden Sie unter *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="b5319-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="b5319-160">Sie müssen es über eine Eingabeaufforderung mit erhöhten Rechten ausführen (d. a. als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="b5319-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="b5319-161">Um die Supportinformationen zu generieren, geben *SieMpCmdRun.exe -getfiles* ein.</span><span class="sxs-lookup"><span data-stu-id="b5319-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="b5319-162">Nach einer Weile werden mehrere Protokolle in ein Archiv (MpSupportFiles.cab) gepackt und in *C:\ProgramData\Microsoft\Windows Defender\Support* zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="b5319-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Protokolle zum Schutz vor Schadsoftware":::

<span data-ttu-id="b5319-164">Extrahieren Sie dieses Archiv, und Sie haben viele Dateien zur Problembehandlung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b5319-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="b5319-165">Die relevantesten Dateien sind:</span><span class="sxs-lookup"><span data-stu-id="b5319-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="b5319-166">**MPOperationalEvents.txt:** Diese Datei enthält dieselbe Ebene von Informationen, die in der Ereignisanzeige für das Betriebsprotokoll Windows Defender zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="b5319-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="b5319-167">**MPRegistry.txt** – In dieser Datei können Sie alle aktuellen Windows Defender Konfigurationen analysieren, beginnend mit der Erfassung der Supportprotokolle.</span><span class="sxs-lookup"><span data-stu-id="b5319-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="b5319-168">**MPLog.txt** – Dieses Protokoll enthält ausführlichere Informationen zu allen Aktionen/Vorgängen des Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="b5319-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
