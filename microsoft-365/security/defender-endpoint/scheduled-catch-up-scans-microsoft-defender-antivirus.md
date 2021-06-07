---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, z. B. wann sie ausgeführt werden sollen und ob sie als vollständige oder schnelle Scans ausgeführt werden sollen
keywords: Schnellscan, vollständiger Scan, schnell und vollständig, Scan planen, täglich, wöchentlich, Zeit, geplant, serieell, regelmäßig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789268"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="e1c09-104">Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="e1c09-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e1c09-105">**Applies to:**</span></span>

- [<span data-ttu-id="e1c09-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e1c09-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="e1c09-107">Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Überprüfungen nach einem Update.</span><span class="sxs-lookup"><span data-stu-id="e1c09-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="e1c09-108">Sie können den Zeitplan für das Herunterladen und Anwenden von [Schutzupdates verwalten,](manage-protection-update-schedule-microsoft-defender-antivirus.md) um diese Standardeinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="e1c09-109">Zusätzlich zu always-on-Echtzeitschutz und [On-Demand-Scans](run-scan-microsoft-defender-antivirus.md) können Sie regelmäßige, geplante Scans einrichten.</span><span class="sxs-lookup"><span data-stu-id="e1c09-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="e1c09-110">Sie können den Scantyp konfigurieren, wann der Scan durchgeführt werden soll und ob der Scan nach einem [Schutzupdate](manage-protection-updates-microsoft-defender-antivirus.md) durchgeführt werden soll oder ob der Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1c09-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="e1c09-111">Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="e1c09-112">In diesem Artikel wird beschrieben, wie Sie geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1c09-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="e1c09-113">Sie können auch Zeitpläneüberprüfungen mit [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) oder [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1c09-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="e1c09-114">So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="e1c09-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="e1c09-115">Wechseln Sie auf dem Computer für die Gruppenrichtlinienverwaltung im Gruppenrichtlinien-Editor zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Überprüfung.**</span><span class="sxs-lookup"><span data-stu-id="e1c09-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="e1c09-116">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e1c09-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="e1c09-117">Geben Sie Einstellungen für das Gruppenrichtlinienobjekt an, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e1c09-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="e1c09-118">Wiederholen Sie die Schritte 1 bis 4 für jede Einstellung, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e1c09-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="e1c09-119">Stellen Sie Das Gruppenrichtlinienobjekt wie gewohnt bereit.</span><span class="sxs-lookup"><span data-stu-id="e1c09-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="e1c09-120">Wenn Sie Hilfe zu Gruppenrichtlinienobjekten benötigen, lesen [Sie Erstellen eines Gruppenrichtlinienobjekts .](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="e1c09-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="e1c09-121">Weitere Informationen finden Sie unter ["Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen"](manage-protection-update-schedule-microsoft-defender-antivirus.md) und ["Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern".](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e1c09-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="e1c09-122">Schnellscan im Vergleich zum vollständigen Scan und benutzerdefinierter Scan</span><span class="sxs-lookup"><span data-stu-id="e1c09-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="e1c09-123">Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um einen vollständigen oder einen Schnellscan handeln soll.</span><span class="sxs-lookup"><span data-stu-id="e1c09-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="e1c09-124">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-124">Quick scan</span></span>  |<span data-ttu-id="e1c09-125">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="e1c09-125">Full scan</span></span>  | <span data-ttu-id="e1c09-126">Benutzerdefinierter Scan</span><span class="sxs-lookup"><span data-stu-id="e1c09-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="e1c09-127">Ein Schnellscan untersucht alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.</span><span class="sxs-lookup"><span data-stu-id="e1c09-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="e1c09-128">In den meisten Fällen ist ein Schnellscan ausreichend und wird für geplante Scans empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="e1c09-129">Eine vollständige Überprüfung beginnt mit einer Schnellüberprüfung und wird dann mit einer sequenziellen Dateiüberprüfung aller bereitgestellten Festplatten und Wechseldatenträger/Netzlaufwerke fortgesetzt (wenn der vollständige Scan dafür konfiguriert ist).</span><span class="sxs-lookup"><span data-stu-id="e1c09-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="e1c09-130">Ein vollständiger Scan kann einige Stunden oder Tage dauern, abhängig von der Menge und dem Typ der Daten, die gescannt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="e1c09-131">Wenn der vollständige Scan abgeschlossen ist, sind neue Sicherheitsinformationen verfügbar, und es ist ein neuer Scan erforderlich, um sicherzustellen, dass keine anderen Bedrohungen mit der neuen Sicherheitsintelligenz erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="e1c09-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="e1c09-132">Ein benutzerdefinierter Scan ist ein Schnellscan, der für die von Ihnen angegebenen Dateien und Ordner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1c09-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="e1c09-133">Sie können z. B. ein USB-Laufwerk oder einen bestimmten Ordner auf dem lokalen Laufwerk Ihres Geräts scannen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="e1c09-134">Standardmäßig werden Schnellscans auf bereitgestellten Wechselmedien wie USB-Laufwerken ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1c09-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="e1c09-135">Woher weiß ich, welcher Scantyp ausgewählt werden soll?</span><span class="sxs-lookup"><span data-stu-id="e1c09-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="e1c09-136">Verwenden Sie die folgende Tabelle, um einen Scantyp auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="e1c09-137">Szenario</span><span class="sxs-lookup"><span data-stu-id="e1c09-137">Scenario</span></span>  |<span data-ttu-id="e1c09-138">Empfohlener Scantyp</span><span class="sxs-lookup"><span data-stu-id="e1c09-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="e1c09-139">Sie möchten regelmäßige, geplante Scans einrichten.</span><span class="sxs-lookup"><span data-stu-id="e1c09-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="e1c09-140">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-140">Quick scan</span></span> <p><span data-ttu-id="e1c09-141">Ein Schnellscan überprüft die Prozesse, den Arbeitsspeicher, die Profile und bestimmten Speicherorte auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="e1c09-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="e1c09-142">In Kombination mit [einem immer aktivierten Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md)bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene.</span><span class="sxs-lookup"><span data-stu-id="e1c09-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="e1c09-143">Der Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wenn ein Benutzer zu einem Ordner navigiert.</span><span class="sxs-lookup"><span data-stu-id="e1c09-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="e1c09-144">Bedrohungen wie Schadsoftware werden auf einem einzelnen Gerät erkannt.</span><span class="sxs-lookup"><span data-stu-id="e1c09-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="e1c09-145">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-145">Quick scan</span></span> <p><span data-ttu-id="e1c09-146">In den meisten Fällen erfasst und bereinigt ein Schnellscan erkannte Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="e1c09-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="e1c09-147">Sie möchten eine [Überprüfung nach Bedarf](run-scan-microsoft-defender-antivirus.md) ausführen</span><span class="sxs-lookup"><span data-stu-id="e1c09-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="e1c09-148">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-148">Quick scan</span></span>       |
| <span data-ttu-id="e1c09-149">Sie möchten sicherstellen, dass ein tragbares Gerät, z. B. ein USB-Laufwerk, keine Schadsoftware enthält.</span><span class="sxs-lookup"><span data-stu-id="e1c09-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="e1c09-150">Benutzerdefinierter Scan</span><span class="sxs-lookup"><span data-stu-id="e1c09-150">Custom scan</span></span> <p><span data-ttu-id="e1c09-151">Mit einer benutzerdefinierten Überprüfung können Sie bestimmte Speicherorte, Ordner oder Dateien auswählen und einen Schnellscan ausführen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="e1c09-152">Was muss ich sonst noch über schnelle und vollständige Scans wissen?</span><span class="sxs-lookup"><span data-stu-id="e1c09-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="e1c09-153">Schädliche Dateien können an Speicherorten gespeichert werden, die nicht in einem Schnellscan enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e1c09-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="e1c09-154">Der immer aktivierte Echtzeitschutz überprüft jedoch alle Dateien, die geöffnet und geschlossen werden, sowie alle Dateien, die sich in Ordnern befinden, auf die ein Benutzer zugegriffen hat.</span><span class="sxs-lookup"><span data-stu-id="e1c09-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="e1c09-155">Die Kombination aus Echtzeitschutz und schnellem Scan bietet starken Schutz vor Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="e1c09-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="e1c09-156">Der Schutz beim Zugriff mit über die [Cloud bereitgestellten Schutz](cloud-protection-microsoft-defender-antivirus.md) trägt dazu bei, sicherzustellen, dass alle Dateien, auf die auf dem System zugegriffen wird, mit den neuesten Sicherheitsintelligenz- und Cloud Machine Learning-Modellen gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="e1c09-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="e1c09-157">Wenn der Echtzeitschutz Schadsoftware erkennt und das Ausmaß der betroffenen Dateien zunächst nicht bestimmt wird, initiiert Microsoft Defender Antivirus im Rahmen des Korrekturprozesses eine vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="e1c09-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="e1c09-158">Ein vollständiger Scan kann schädliche Dateien erkennen, die von anderen Scans nicht erkannt wurden, z. B. ein Schnellscan.</span><span class="sxs-lookup"><span data-stu-id="e1c09-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="e1c09-159">Eine vollständige Überprüfung kann jedoch einige Zeit in Anspruch nehmen und wertvolle Systemressourcen nutzen, um diesen Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="e1c09-160">Wenn ein Gerät über einen längeren Zeitraum offline ist, kann ein vollständiger Scan länger dauern.</span><span class="sxs-lookup"><span data-stu-id="e1c09-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="e1c09-161">Einrichten von geplanten Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-161">Set up scheduled scans</span></span>

<span data-ttu-id="e1c09-162">Geplante Scans werden an dem von Ihnen angegebenen Tag und der angegebenen Uhrzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1c09-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="e1c09-163">Sie können gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1c09-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="e1c09-164">Wenn ein Gerät während eines geplanten vollständigen Scans angeschlossen wird und mit Akku betrieben wird, wird der geplante Scan mit Dem Ereignis 1002 beendet, das besagt, dass der Scan vor Abschluss beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e1c09-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="e1c09-165">Microsoft Defender Antivirus führt zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="e1c09-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="e1c09-166">Verwenden von Gruppenrichtlinien zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="e1c09-167">Standort</span><span class="sxs-lookup"><span data-stu-id="e1c09-167">Location</span></span> | <span data-ttu-id="e1c09-168">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e1c09-168">Setting</span></span> | <span data-ttu-id="e1c09-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1c09-169">Description</span></span> | <span data-ttu-id="e1c09-170">Standardeinstellung (falls nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e1c09-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e1c09-171">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-171">Scan</span></span> | <span data-ttu-id="e1c09-172">Angeben des Für einen geplanten Scan zu verwendenden Scantyps</span><span class="sxs-lookup"><span data-stu-id="e1c09-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="e1c09-173">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-173">Quick scan</span></span> |
|<span data-ttu-id="e1c09-174">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-174">Scan</span></span> | <span data-ttu-id="e1c09-175">Angeben des Wochentags, an dem eine geplante Überprüfung ausgeführt werden soll</span><span class="sxs-lookup"><span data-stu-id="e1c09-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="e1c09-176">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1c09-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="e1c09-177">Nie</span><span class="sxs-lookup"><span data-stu-id="e1c09-177">Never</span></span> |
|<span data-ttu-id="e1c09-178">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-178">Scan</span></span> | <span data-ttu-id="e1c09-179">Angeben der Tageszeit zum Ausführen eines geplanten Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="e1c09-180">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein).</span><span class="sxs-lookup"><span data-stu-id="e1c09-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="e1c09-181">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="e1c09-181">2 a.m.</span></span> |
|<span data-ttu-id="e1c09-182">wurzel</span><span class="sxs-lookup"><span data-stu-id="e1c09-182">Root</span></span> | <span data-ttu-id="e1c09-183">Zufällige Zeitplanung für geplante Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e1c09-183">Randomize scheduled task times</span></span> |<span data-ttu-id="e1c09-184">In Microsoft Defender Antivirus die Startzeit des Scans in ein beliebiges Intervall zwischen 0 und 4 Stunden zufällig festlegen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="e1c09-185">In [SCEP](/mem/intune/protect/certificates-scep-configure)randomisieren Sie Scans in ein beliebiges Intervall plus oder minus 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e1c09-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="e1c09-186">Dies kann bei virtuellen Computern oder VDI-Bereitstellungen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="e1c09-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="e1c09-187">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="e1c09-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="e1c09-188">Verwenden von PowerShell-Cmdlets zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="e1c09-189">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1c09-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="e1c09-190">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/) Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="e1c09-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="e1c09-191">Verwenden Windows Management Instruction (WMI) zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="e1c09-192">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e1c09-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="e1c09-193">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e1c09-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="e1c09-194">Starten von geplanten Scans nur, wenn der Endpunkt nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e1c09-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="e1c09-195">Sie können festlegen, dass der geplante Scan nur ausgeführt wird, wenn der Endpunkt aktiviert ist, aber nicht mit Gruppenrichtlinien, PowerShell oder WMI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1c09-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="e1c09-196">Diese Überprüfungen berücksichtigen nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="e1c09-197">Verwenden von Gruppenrichtlinien zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="e1c09-198">Standort</span><span class="sxs-lookup"><span data-stu-id="e1c09-198">Location</span></span> | <span data-ttu-id="e1c09-199">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e1c09-199">Setting</span></span> | <span data-ttu-id="e1c09-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1c09-200">Description</span></span> | <span data-ttu-id="e1c09-201">Standardeinstellung (falls nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e1c09-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e1c09-202">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-202">Scan</span></span> | <span data-ttu-id="e1c09-203">Starten Sie den geplanten Scan nur, wenn der Computer aktiviert ist, aber nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e1c09-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="e1c09-204">Geplante Scans werden nur ausgeführt, wenn der Computer aktiviert ist, aber nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1c09-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="e1c09-205">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="e1c09-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="e1c09-206">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e1c09-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="e1c09-207">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1c09-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="e1c09-208">Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="e1c09-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="e1c09-209">Verwenden Windows-Verwaltungsanweisung (WMI)</span><span class="sxs-lookup"><span data-stu-id="e1c09-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="e1c09-210">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e1c09-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="e1c09-211">Weitere Informationen zu APIs und zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e1c09-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="e1c09-212">Konfigurieren, wann vollständige Scans ausgeführt werden sollen, um die Korrektur abzuschließen</span><span class="sxs-lookup"><span data-stu-id="e1c09-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="e1c09-213">Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um deren Entfernung und Behebung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="e1c09-214">Sie können angeben, wann diese Überprüfungen mit der Gruppenrichtlinie, PowerShell oder WMI durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="e1c09-215">Verwenden von Gruppenrichtlinien zum Planen von Überprüfungen, die für die Wartung erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="e1c09-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="e1c09-216">Standort</span><span class="sxs-lookup"><span data-stu-id="e1c09-216">Location</span></span> | <span data-ttu-id="e1c09-217">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e1c09-217">Setting</span></span> | <span data-ttu-id="e1c09-218">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1c09-218">Description</span></span> | <span data-ttu-id="e1c09-219">Standardeinstellung (falls nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e1c09-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="e1c09-220">Sanierung</span><span class="sxs-lookup"><span data-stu-id="e1c09-220">Remediation</span></span> | <span data-ttu-id="e1c09-221">Geben Sie den Wochentag an, an dem ein geplanter vollständiger Scan ausgeführt werden soll, um die Korrektur abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="e1c09-222">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1c09-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="e1c09-223">Nie</span><span class="sxs-lookup"><span data-stu-id="e1c09-223">Never</span></span> |
|<span data-ttu-id="e1c09-224">Sanierung</span><span class="sxs-lookup"><span data-stu-id="e1c09-224">Remediation</span></span> | <span data-ttu-id="e1c09-225">Geben Sie die Tageszeit an, zu der ein geplanter vollständiger Scan ausgeführt werden soll, um die Wartung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="e1c09-226">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="e1c09-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="e1c09-227">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="e1c09-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="e1c09-228">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e1c09-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="e1c09-229">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1c09-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="e1c09-230">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="e1c09-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="e1c09-231">Verwenden Windows-Verwaltungsanweisung (WMI)</span><span class="sxs-lookup"><span data-stu-id="e1c09-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="e1c09-232">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e1c09-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="e1c09-233">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e1c09-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="e1c09-234">Einrichten täglicher Schnellscans</span><span class="sxs-lookup"><span data-stu-id="e1c09-234">Set up daily quick scans</span></span>

<span data-ttu-id="e1c09-235">Sie können einen täglichen Schnellscan aktivieren, der zusätzlich zu Ihren anderen geplanten Scans mithilfe von Gruppenrichtlinien, PowerShell oder WMI ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1c09-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="e1c09-236">Verwenden von Gruppenrichtlinien zum Planen von täglichen Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="e1c09-237">Standort</span><span class="sxs-lookup"><span data-stu-id="e1c09-237">Location</span></span> | <span data-ttu-id="e1c09-238">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e1c09-238">Setting</span></span> | <span data-ttu-id="e1c09-239">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1c09-239">Description</span></span> | <span data-ttu-id="e1c09-240">Standardeinstellung (falls nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e1c09-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e1c09-241">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-241">Scan</span></span> | <span data-ttu-id="e1c09-242">Angeben des Intervalls zum Ausführen von Schnellscans pro Tag</span><span class="sxs-lookup"><span data-stu-id="e1c09-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="e1c09-243">Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstrichen sein sollen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="e1c09-244">Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, geben Sie einmal täglich **24** ein.</span><span class="sxs-lookup"><span data-stu-id="e1c09-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="e1c09-245">Geben Sie **0** ein, um nie einen täglichen Schnellscan auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e1c09-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="e1c09-246">Nie</span><span class="sxs-lookup"><span data-stu-id="e1c09-246">Never</span></span> |
|<span data-ttu-id="e1c09-247">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1c09-247">Scan</span></span> | <span data-ttu-id="e1c09-248">Angeben der Zeit für einen täglichen Schnellscan</span><span class="sxs-lookup"><span data-stu-id="e1c09-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="e1c09-249">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="e1c09-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="e1c09-250">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="e1c09-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="e1c09-251">Verwenden von PowerShell-Cmdlets zum Planen von täglichen Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="e1c09-252">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1c09-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="e1c09-253">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="e1c09-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="e1c09-254">Verwenden von Windows Management Instruction (WMI) zum Planen von täglichen Scans</span><span class="sxs-lookup"><span data-stu-id="e1c09-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="e1c09-255">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e1c09-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="e1c09-256">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e1c09-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="e1c09-257">Aktivieren von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="e1c09-257">Enable scans after protection updates</span></span>

<span data-ttu-id="e1c09-258">Sie können erzwingen, dass nach jedem [Schutzupdate](manage-protection-updates-microsoft-defender-antivirus.md) mithilfe von Gruppenrichtlinien eine Überprüfung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1c09-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="e1c09-259">Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="e1c09-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="e1c09-260">Standort</span><span class="sxs-lookup"><span data-stu-id="e1c09-260">Location</span></span> | <span data-ttu-id="e1c09-261">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e1c09-261">Setting</span></span> | <span data-ttu-id="e1c09-262">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1c09-262">Description</span></span> | <span data-ttu-id="e1c09-263">Standardeinstellung (falls nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e1c09-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="e1c09-264">Signaturupdates</span><span class="sxs-lookup"><span data-stu-id="e1c09-264">Signature updates</span></span> | <span data-ttu-id="e1c09-265">Aktivieren des Scans nach dem Security Intelligence-Update</span><span class="sxs-lookup"><span data-stu-id="e1c09-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="e1c09-266">Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates.</span><span class="sxs-lookup"><span data-stu-id="e1c09-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="e1c09-267">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="e1c09-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="e1c09-268">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1c09-268">See also</span></span>

- [<span data-ttu-id="e1c09-269">Verhindern oder Zulassen der lokalen Änderung von Richtlinieneinstellungen durch Benutzer</span><span class="sxs-lookup"><span data-stu-id="e1c09-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e1c09-270">Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e1c09-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e1c09-271">Konfigurieren der Scanoptionen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e1c09-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e1c09-272">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="e1c09-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e1c09-273">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="e1c09-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="e1c09-274">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e1c09-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)