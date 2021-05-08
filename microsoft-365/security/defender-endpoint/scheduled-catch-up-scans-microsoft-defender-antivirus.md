---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
keywords: Schnellscan, vollständiger Scan, Schnell- und Vollscan, Zeitplanscan, täglich, wöchentlich, Zeit, geplant, serienmäßig, normal
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274688"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="87e51-104">Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="87e51-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="87e51-105">**Applies to:**</span></span>

- [<span data-ttu-id="87e51-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="87e51-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="87e51-107">Standardmäßig wird Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans auf ein Update überprüft.</span><span class="sxs-lookup"><span data-stu-id="87e51-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="87e51-108">Sie können [den Zeitplan verwalten, wann](manage-protection-update-schedule-microsoft-defender-antivirus.md) Schutzupdates heruntergeladen und angewendet werden sollen, um diese Standardeinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="87e51-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="87e51-109">Neben dem immer-on-Echtzeitschutz und [Denkscans](run-scan-microsoft-defender-antivirus.md) bei Bedarf können Sie regelmäßige, geplante Scans einrichten.</span><span class="sxs-lookup"><span data-stu-id="87e51-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="87e51-110">Sie können den Typ der Überprüfung konfigurieren, wann die Überprüfung erfolgen [](manage-protection-updates-microsoft-defender-antivirus.md) soll und ob die Überprüfung nach einem Schutzupdate erfolgen soll oder ob der Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87e51-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="87e51-111">Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="87e51-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="87e51-112">In diesem Artikel wird beschrieben, wie Geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="87e51-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="87e51-113">Sie können auch Zeitplänescans mit [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) oder [Microsoft Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="87e51-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="87e51-114">So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="87e51-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="87e51-115">Wechseln Sie auf dem Computer für die Gruppenrichtlinienverwaltung im Gruppenrichtlinien-Editor zu Computerkonfiguration Administrative Vorlagen Windows  >    >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="87e51-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="87e51-116">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="87e51-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="87e51-117">Geben Sie Einstellungen für das Gruppenrichtlinienobjekt an, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="87e51-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="87e51-118">Wiederholen Sie die Schritte 1 bis 4 für jede Einstellung, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="87e51-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="87e51-119">Stellen Sie ihr Gruppenrichtlinienobjekt wie gewohnt zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="87e51-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="87e51-120">Wenn Sie Hilfe zu Gruppenrichtlinienobjekten benötigen, lesen [Sie Erstellen eines Gruppenrichtlinienobjekts](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span><span class="sxs-lookup"><span data-stu-id="87e51-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="87e51-121">Weitere Informationen finden Sie [unter Manage when protection updates should be download and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and Prevent or allow users to locally modify policy settings [topics.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="87e51-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="87e51-122">Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="87e51-123">Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um eine vollständige oder eine schnelle Überprüfung gehen soll.</span><span class="sxs-lookup"><span data-stu-id="87e51-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="87e51-124">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="87e51-124">Quick scan</span></span>  |<span data-ttu-id="87e51-125">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="87e51-125">Full scan</span></span>  | <span data-ttu-id="87e51-126">Benutzerdefinierte Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87e51-127">Eine schnelle Überprüfung sucht nach allen Speicherorten, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.</span><span class="sxs-lookup"><span data-stu-id="87e51-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="87e51-128">In den meisten Fällen ist eine schnelle Überprüfung ausreichend und wird für geplante Scans empfohlen.</span><span class="sxs-lookup"><span data-stu-id="87e51-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="87e51-129">Eine vollständige Überprüfung beginnt mit einer schnell ausgeführten Überprüfung und wird dann mit einer sequenziellen Dateiscan aller bereitgestellten Festplatten und Wechseldatenträger/Netzwerklaufwerke fortgesetzt (sofern die vollständige Überprüfung dafür konfiguriert ist).</span><span class="sxs-lookup"><span data-stu-id="87e51-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="87e51-130">Eine vollständige Überprüfung kann je nach Menge und Art der zu überprüfende Daten einige Stunden oder Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="87e51-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="87e51-131">Nach Abschluss der vollständigen Überprüfung ist neue Sicherheitsintelligenz verfügbar, und es ist eine neue Überprüfung erforderlich, um sicherzustellen, dass keine weiteren Bedrohungen mit der neuen Sicherheitsintelligenz erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="87e51-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="87e51-132">Bei einer benutzerdefinierten Überprüfung handelt es sich um eine Schnellscan, die für die angegebenen Dateien und Ordner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87e51-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="87e51-133">Sie können beispielsweise ein USB-Laufwerk oder einen bestimmten Ordner auf dem lokalen Laufwerk Ihres Geräts überprüfen.</span><span class="sxs-lookup"><span data-stu-id="87e51-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="87e51-134">Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="87e51-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="87e51-135">Wo finde ich den zu wählende Scantyp?</span><span class="sxs-lookup"><span data-stu-id="87e51-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="87e51-136">Verwenden Sie die folgende Tabelle, um einen Scantyp zu wählen.</span><span class="sxs-lookup"><span data-stu-id="87e51-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="87e51-137">Szenario</span><span class="sxs-lookup"><span data-stu-id="87e51-137">Scenario</span></span>  |<span data-ttu-id="87e51-138">Empfohlener Scantyp</span><span class="sxs-lookup"><span data-stu-id="87e51-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="87e51-139">Sie möchten regelmäßige, geplante Scans einrichten</span><span class="sxs-lookup"><span data-stu-id="87e51-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="87e51-140">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="87e51-140">Quick scan</span></span> <p><span data-ttu-id="87e51-141">Bei einer schnell durchgeführten Überprüfung werden die Prozesse, der Arbeitsspeicher, die Profile und bestimmte Speicherorte auf dem Gerät überprüft.</span><span class="sxs-lookup"><span data-stu-id="87e51-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="87e51-142">In Kombination [mit dem Immer-On-Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md)bietet eine schnelle Überprüfung eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene.</span><span class="sxs-lookup"><span data-stu-id="87e51-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="87e51-143">Der Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wann immer ein Benutzer zu einem Ordner navigiert.</span><span class="sxs-lookup"><span data-stu-id="87e51-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="87e51-144">Bedrohungen, z. B. Schadsoftware, werden auf einem Gerät erkannt</span><span class="sxs-lookup"><span data-stu-id="87e51-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="87e51-145">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="87e51-145">Full scan</span></span> <p><span data-ttu-id="87e51-146">Bei einer vollständigen Überprüfung kann ermittelt werden, ob es inaktive Komponenten gibt, für die eine gründlichere Bereinigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="87e51-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="87e51-147">Sie möchten eine [Anforderungsscan ausführen](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="87e51-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="87e51-148">Vollständiger Scan</span><span class="sxs-lookup"><span data-stu-id="87e51-148">Full scan</span></span>  <p><span data-ttu-id="87e51-149">Bei einer vollständigen Überprüfung werden alle Dateien auf dem Gerätedatenträger betrachtet, einschließlich veralteter, archivierter und nicht täglich zugänglicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="87e51-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="87e51-150">Sie möchten sicherstellen, dass ein tragbares Gerät, z. B. ein USB-Laufwerk, keine Schadsoftware enthält.</span><span class="sxs-lookup"><span data-stu-id="87e51-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="87e51-151">Benutzerdefinierte Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-151">Custom scan</span></span> <p><span data-ttu-id="87e51-152">Mit einer benutzerdefinierten Überprüfung können Sie bestimmte Speicherorte, Ordner oder Dateien auswählen und eine schnelle Überprüfung durchführen.</span><span class="sxs-lookup"><span data-stu-id="87e51-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="87e51-153">Was muss ich sonst noch über schnelle und vollständige Scans wissen?</span><span class="sxs-lookup"><span data-stu-id="87e51-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="87e51-154">Schädliche Dateien können an Speicherorten gespeichert werden, die nicht in einer Schnellscan enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="87e51-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="87e51-155">Der always-on-Echtzeitschutz überprüft jedoch alle geöffneten und geschlossenen Dateien sowie alle Dateien, die sich in Ordnern befinden, auf die von einem Benutzer zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="87e51-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="87e51-156">Die Kombination aus Echtzeitschutz und schneller Überprüfung hilft dabei, einen starken Schutz vor Schadsoftware zu bieten.</span><span class="sxs-lookup"><span data-stu-id="87e51-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="87e51-157">Der On-Access-Schutz mit cloudbasiertem Schutz trägt dazu bei, dass alle dateien, auf die auf das System zugegriffen wird, mit den neuesten Sicherheitsintelligenz- und Cloud Machine [Learning-Modellen](cloud-protection-microsoft-defender-antivirus.md) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="87e51-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="87e51-158">Wenn der Echtzeitschutz Schadsoftware erkennt und der Umfang der betroffenen Dateien zunächst nicht bestimmt wird, Microsoft Defender Antivirus im Rahmen des Korrekturprozesses eine vollständige Überprüfung initiiert.</span><span class="sxs-lookup"><span data-stu-id="87e51-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="87e51-159">Bei einer vollständigen Überprüfung können schädliche Dateien erkannt werden, die von anderen Scans nicht erkannt wurden, z. B. eine Schnellscan.</span><span class="sxs-lookup"><span data-stu-id="87e51-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="87e51-160">Eine vollständige Überprüfung kann jedoch eine Weile dauern und wertvolle Systemressourcen zum Abschließen verwenden.</span><span class="sxs-lookup"><span data-stu-id="87e51-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="87e51-161">Wenn ein Gerät über einen längeren Zeitraum offline ist, kann eine vollständige Überprüfung länger dauern.</span><span class="sxs-lookup"><span data-stu-id="87e51-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="87e51-162">Einrichten geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-162">Set up scheduled scans</span></span>

<span data-ttu-id="87e51-163">Geplante Scans werden an dem von Ihnen angegebenen Tag und der angegebenen Uhrzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="87e51-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="87e51-164">Sie können Gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="87e51-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="87e51-165">Wenn ein Gerät während einer geplanten vollständigen Überprüfung getrennt wird und während der geplanten vollständigen Überprüfung mit Akku ausgeführt wird, wird die geplante Überprüfung mit dem Ereignis 1002 beendet, das besagt, dass die Überprüfung vor Abschluss beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="87e51-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="87e51-166">Microsoft Defender Antivirus wird zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="87e51-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="87e51-167">Planen von Scans mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="87e51-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="87e51-168">Speicherort</span><span class="sxs-lookup"><span data-stu-id="87e51-168">Location</span></span> | <span data-ttu-id="87e51-169">Einstellung</span><span class="sxs-lookup"><span data-stu-id="87e51-169">Setting</span></span> | <span data-ttu-id="87e51-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e51-170">Description</span></span> | <span data-ttu-id="87e51-171">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="87e51-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="87e51-172">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-172">Scan</span></span> | <span data-ttu-id="87e51-173">Angeben des Scantyps, der für eine geplante Überprüfung verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="87e51-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="87e51-174">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="87e51-174">Quick scan</span></span> |
|<span data-ttu-id="87e51-175">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-175">Scan</span></span> | <span data-ttu-id="87e51-176">Angeben des Wochentags zum Ausführen einer geplanten Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="87e51-177">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="87e51-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="87e51-178">Nie</span><span class="sxs-lookup"><span data-stu-id="87e51-178">Never</span></span> |
|<span data-ttu-id="87e51-179">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-179">Scan</span></span> | <span data-ttu-id="87e51-180">Angeben der Uhrzeit für die Ausführung einer geplanten Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="87e51-181">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein).</span><span class="sxs-lookup"><span data-stu-id="87e51-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="87e51-182">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="87e51-182">2 a.m.</span></span> |
|<span data-ttu-id="87e51-183">Root</span><span class="sxs-lookup"><span data-stu-id="87e51-183">Root</span></span> | <span data-ttu-id="87e51-184">Randomisieren geplanter Vorgangszeiten</span><span class="sxs-lookup"><span data-stu-id="87e51-184">Randomize scheduled task times</span></span> |<span data-ttu-id="87e51-185">In Microsoft Defender Antivirus die Startzeit der Überprüfung auf ein Intervall von 0 bis 4 Stunden randomisieren.</span><span class="sxs-lookup"><span data-stu-id="87e51-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="87e51-186">In [SCEP,](/mem/intune/protect/certificates-scep-configure)randomize scans to any interval plus or minus 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="87e51-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="87e51-187">Dies kann bei virtuellen Computern oder VDI-Bereitstellungen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="87e51-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="87e51-188">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="87e51-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="87e51-189">Verwenden von PowerShell-Cmdlets zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="87e51-190">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="87e51-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="87e51-191">Weitere Informationen finden Sie unter [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="87e51-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="87e51-192">Verwenden Windows Management Instruction (WMI) zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="87e51-193">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="87e51-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="87e51-194">Weitere Informationen und zulässige Parameter finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="87e51-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="87e51-195">Geplante Scans nur starten, wenn der Endpunkt nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="87e51-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="87e51-196">Sie können festlegen, dass die geplante Überprüfung nur stattfindet, wenn der Endpunkt aktiviert ist, jedoch nicht mit Gruppenrichtlinien, PowerShell oder WMI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87e51-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="87e51-197">Bei diesen Überprüfungen wird die KONFIGURATION der CPU-Einschränkung nicht berücksichtigt und die verfügbaren Ressourcen genutzt, um den Scan so schnell wie möglich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="87e51-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="87e51-198">Planen von Scans mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="87e51-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="87e51-199">Speicherort</span><span class="sxs-lookup"><span data-stu-id="87e51-199">Location</span></span> | <span data-ttu-id="87e51-200">Einstellung</span><span class="sxs-lookup"><span data-stu-id="87e51-200">Setting</span></span> | <span data-ttu-id="87e51-201">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e51-201">Description</span></span> | <span data-ttu-id="87e51-202">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="87e51-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="87e51-203">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-203">Scan</span></span> | <span data-ttu-id="87e51-204">Starten der geplanten Überprüfung nur, wenn der Computer zwar installiert ist, aber nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="87e51-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="87e51-205">Geplante Scans werden nicht ausgeführt, es sei denn, der Computer ist in, aber nicht in Gebrauch.</span><span class="sxs-lookup"><span data-stu-id="87e51-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="87e51-206">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="87e51-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="87e51-207">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="87e51-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="87e51-208">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="87e51-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="87e51-209">Weitere Informationen finden Sie unter [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="87e51-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="87e51-210">Verwenden Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="87e51-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="87e51-211">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="87e51-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="87e51-212">Weitere Informationen zu APIs und zulässigen Parametern finden Sie [unter Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="87e51-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="87e51-213">Konfigurieren, wann vollständige Überprüfungen ausgeführt werden sollen, um die Korrektur durchzuführen</span><span class="sxs-lookup"><span data-stu-id="87e51-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="87e51-214">Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um ihre Entfernung und Behebung abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="87e51-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="87e51-215">Sie können angeben, wann diese Überprüfungen mit Gruppenrichtlinien, PowerShell oder WMI durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="87e51-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="87e51-216">Planen der erforderlichen Überprüfungen mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="87e51-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="87e51-217">Speicherort</span><span class="sxs-lookup"><span data-stu-id="87e51-217">Location</span></span> | <span data-ttu-id="87e51-218">Einstellung</span><span class="sxs-lookup"><span data-stu-id="87e51-218">Setting</span></span> | <span data-ttu-id="87e51-219">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e51-219">Description</span></span> | <span data-ttu-id="87e51-220">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="87e51-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="87e51-221">Korrektur</span><span class="sxs-lookup"><span data-stu-id="87e51-221">Remediation</span></span> | <span data-ttu-id="87e51-222">Angeben des Wochentags zum Ausführen einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur</span><span class="sxs-lookup"><span data-stu-id="87e51-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="87e51-223">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="87e51-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="87e51-224">Nie</span><span class="sxs-lookup"><span data-stu-id="87e51-224">Never</span></span> |
|<span data-ttu-id="87e51-225">Korrektur</span><span class="sxs-lookup"><span data-stu-id="87e51-225">Remediation</span></span> | <span data-ttu-id="87e51-226">Angeben der Uhrzeit für die Ausführung einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur</span><span class="sxs-lookup"><span data-stu-id="87e51-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="87e51-227">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="87e51-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="87e51-228">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="87e51-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="87e51-229">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="87e51-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="87e51-230">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="87e51-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="87e51-231">Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="87e51-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="87e51-232">Verwenden Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="87e51-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="87e51-233">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="87e51-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="87e51-234">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="87e51-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="87e51-235">Einrichten täglicher Schnellscans</span><span class="sxs-lookup"><span data-stu-id="87e51-235">Set up daily quick scans</span></span>

<span data-ttu-id="87e51-236">Sie können eine tägliche Schnellscan aktivieren, die zusätzlich zu ihren anderen geplanten Scans mit Gruppenrichtlinie, PowerShell oder WMI ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="87e51-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="87e51-237">Verwenden von Gruppenrichtlinien zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="87e51-238">Speicherort</span><span class="sxs-lookup"><span data-stu-id="87e51-238">Location</span></span> | <span data-ttu-id="87e51-239">Einstellung</span><span class="sxs-lookup"><span data-stu-id="87e51-239">Setting</span></span> | <span data-ttu-id="87e51-240">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e51-240">Description</span></span> | <span data-ttu-id="87e51-241">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="87e51-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="87e51-242">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-242">Scan</span></span> | <span data-ttu-id="87e51-243">Angeben des Intervalls zum Ausführen von Schnellscans pro Tag</span><span class="sxs-lookup"><span data-stu-id="87e51-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="87e51-244">Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstreichen sollen.</span><span class="sxs-lookup"><span data-stu-id="87e51-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="87e51-245">Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, und geben Sie einmal pro Tag **24 ein.**</span><span class="sxs-lookup"><span data-stu-id="87e51-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="87e51-246">Geben **Sie 0** ein, um nie einen täglichen Schnellscan ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="87e51-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="87e51-247">Nie</span><span class="sxs-lookup"><span data-stu-id="87e51-247">Never</span></span> |
|<span data-ttu-id="87e51-248">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="87e51-248">Scan</span></span> | <span data-ttu-id="87e51-249">Angeben der Uhrzeit für einen täglichen Schnellscan</span><span class="sxs-lookup"><span data-stu-id="87e51-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="87e51-250">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="87e51-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="87e51-251">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="87e51-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="87e51-252">Verwenden von PowerShell-Cmdlets zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="87e51-253">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="87e51-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="87e51-254">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="87e51-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="87e51-255">Verwenden Windows Management Instruction (WMI) zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="87e51-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="87e51-256">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="87e51-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="87e51-257">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="87e51-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="87e51-258">Aktivieren von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="87e51-258">Enable scans after protection updates</span></span>

<span data-ttu-id="87e51-259">Sie können erzwingen, dass eine Überprüfung nach jedem Schutzupdate [mit Gruppenrichtlinien](manage-protection-updates-microsoft-defender-antivirus.md) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="87e51-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="87e51-260">Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="87e51-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="87e51-261">Speicherort</span><span class="sxs-lookup"><span data-stu-id="87e51-261">Location</span></span> | <span data-ttu-id="87e51-262">Einstellung</span><span class="sxs-lookup"><span data-stu-id="87e51-262">Setting</span></span> | <span data-ttu-id="87e51-263">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87e51-263">Description</span></span> | <span data-ttu-id="87e51-264">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="87e51-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="87e51-265">Signaturupdates</span><span class="sxs-lookup"><span data-stu-id="87e51-265">Signature updates</span></span> | <span data-ttu-id="87e51-266">Aktivieren der Überprüfung nach dem Update der Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="87e51-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="87e51-267">Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates.</span><span class="sxs-lookup"><span data-stu-id="87e51-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="87e51-268">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="87e51-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="87e51-269">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87e51-269">See also</span></span>

- [<span data-ttu-id="87e51-270">Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern</span><span class="sxs-lookup"><span data-stu-id="87e51-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="87e51-271">Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="87e51-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="87e51-272">Konfigurieren der Scanoptionen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="87e51-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="87e51-273">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines</span><span class="sxs-lookup"><span data-stu-id="87e51-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="87e51-274">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="87e51-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="87e51-275">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="87e51-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)