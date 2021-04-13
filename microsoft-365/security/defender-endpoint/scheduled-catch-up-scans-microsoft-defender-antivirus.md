---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
keywords: Schnellscan, vollständiger Scan, Schnell- und Vollscan, Zeitplanscan, täglich, wöchentlich, Zeit, geplant, serienmäßig, normal
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690628"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="acabe-104">Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="acabe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="acabe-105">**Applies to:**</span></span>

- [<span data-ttu-id="acabe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="acabe-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="acabe-107">Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update.</span><span class="sxs-lookup"><span data-stu-id="acabe-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="acabe-108">Sie können [den Zeitplan verwalten, wann](manage-protection-update-schedule-microsoft-defender-antivirus.md) Schutzupdates heruntergeladen und angewendet werden sollen, um diese Standardeinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="acabe-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="acabe-109">Neben dem immer-on-Echtzeitschutz und [Denkscans](run-scan-microsoft-defender-antivirus.md) bei Bedarf können Sie regelmäßige, geplante Scans einrichten.</span><span class="sxs-lookup"><span data-stu-id="acabe-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="acabe-110">Sie können den Typ der Überprüfung konfigurieren, wann die Überprüfung erfolgen [](manage-protection-updates-microsoft-defender-antivirus.md) soll und ob die Überprüfung nach einem Schutzupdate erfolgen soll oder ob der Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="acabe-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="acabe-111">Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="acabe-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="acabe-112">In diesem Artikel wird beschrieben, wie Geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="acabe-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="acabe-113">Sie können auch Zeitplänescans mit [Microsoft Endpoint Configuration Manager oder](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) Microsoft Intune [konfigurieren.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="acabe-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="acabe-114">So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="acabe-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="acabe-115">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="acabe-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="acabe-116">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="acabe-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="acabe-117">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="acabe-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="acabe-118">Erweitern Sie die Struktur auf **Windows-Komponenten >**  Microsoft Defender Antivirus und dann den in der folgenden Tabelle angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="acabe-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="acabe-119">Doppelklicken Sie auf die **Richtlinieneinstellung,** wie in der folgenden Tabelle angegeben, und legen Sie die Option auf die gewünschte Konfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="acabe-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="acabe-120">Klicken **Sie auf OK,** und wiederholen Sie dies für alle anderen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="acabe-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="acabe-121">Weitere Informationen finden Sie [unter Manage when protection updates should be download and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and Prevent or allow users to locally modify policy settings [topics.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="acabe-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="acabe-122">Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="acabe-123">Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um eine vollständige oder eine schnelle Überprüfung gehen soll.</span><span class="sxs-lookup"><span data-stu-id="acabe-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="acabe-124">Schnellscans sehen sich alle Speicherorte an, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows-Startordner.</span><span class="sxs-lookup"><span data-stu-id="acabe-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="acabe-125">In Kombination mit der [Immer-On-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md) , die Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, hilft ein Schnellscan, sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene eine starke Abdeckung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="acabe-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="acabe-126">In den meisten Fällen bedeutet dies, dass eine schnelle Überprüfung ausreichend ist, um Schadsoftware zu finden, die nicht vom Echtzeitschutz aufgegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="acabe-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="acabe-127">Eine vollständige Überprüfung kann für Endpunkte nützlich sein, die eine Schadsoftwarebedrohung festgestellt haben, um zu ermitteln, ob inaktive Komponenten enthalten sind, die eine gründlichere Bereinigung erfordern.</span><span class="sxs-lookup"><span data-stu-id="acabe-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="acabe-128">In dieser Instanz können Sie eine vollständige Überprüfung verwenden, wenn Sie eine [On-Demand-Überprüfung ausführen.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="acabe-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="acabe-129">Mit einer benutzerdefinierten Überprüfung können Sie die zu scannenden Dateien und Ordner angeben, z. B. ein USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="acabe-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="acabe-130">Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="acabe-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="acabe-131">Einrichten geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-131">Set up scheduled scans</span></span>

<span data-ttu-id="acabe-132">Geplante Scans werden zum angegebenen Tag und zur angegebenen Uhrzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="acabe-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="acabe-133">Sie können Gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="acabe-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="acabe-134">Wenn ein Computer während einer geplanten vollständigen Überprüfung getrennt wird und während der geplanten vollständigen Überprüfung mit dem Akku ausgeführt wird, wird die geplante Überprüfung mit dem Ereignis 1002 beendet, das besagt, dass die Überprüfung vor Abschluss beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="acabe-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="acabe-135">Microsoft Defender Antivirus wird zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="acabe-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="acabe-136">Planen von Scans mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="acabe-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="acabe-137">Speicherort</span><span class="sxs-lookup"><span data-stu-id="acabe-137">Location</span></span> | <span data-ttu-id="acabe-138">Einstellung</span><span class="sxs-lookup"><span data-stu-id="acabe-138">Setting</span></span> | <span data-ttu-id="acabe-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acabe-139">Description</span></span> | <span data-ttu-id="acabe-140">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="acabe-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="acabe-141">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-141">Scan</span></span> | <span data-ttu-id="acabe-142">Angeben des Scantyps, der für eine geplante Überprüfung verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="acabe-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="acabe-143">Schnellscan</span><span class="sxs-lookup"><span data-stu-id="acabe-143">Quick scan</span></span> |
|<span data-ttu-id="acabe-144">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-144">Scan</span></span> | <span data-ttu-id="acabe-145">Angeben des Wochentags zum Ausführen einer geplanten Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="acabe-146">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="acabe-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="acabe-147">Nie</span><span class="sxs-lookup"><span data-stu-id="acabe-147">Never</span></span> |
|<span data-ttu-id="acabe-148">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-148">Scan</span></span> | <span data-ttu-id="acabe-149">Angeben der Uhrzeit für die Ausführung einer geplanten Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="acabe-150">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein).</span><span class="sxs-lookup"><span data-stu-id="acabe-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="acabe-151">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="acabe-151">2 a.m.</span></span> |
|<span data-ttu-id="acabe-152">Root</span><span class="sxs-lookup"><span data-stu-id="acabe-152">Root</span></span> | <span data-ttu-id="acabe-153">Randomisieren geplanter Vorgangszeiten</span><span class="sxs-lookup"><span data-stu-id="acabe-153">Randomize scheduled task times</span></span> |<span data-ttu-id="acabe-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span><span class="sxs-lookup"><span data-stu-id="acabe-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="acabe-155">In FEP/SCEP: randomisieren Sie auf ein beliebiges Intervall plus oder minus 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="acabe-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="acabe-156">Dies kann in VM- oder VDI-Bereitstellungen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="acabe-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="acabe-157">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="acabe-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="acabe-158">Verwenden von PowerShell-Cmdlets zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="acabe-159">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="acabe-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="acabe-160">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="acabe-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="acabe-161">Verwenden von Windows Management Instruction (WMI) zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="acabe-162">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="acabe-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="acabe-163">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="acabe-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="acabe-164">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="acabe-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="acabe-165">Geplante Scans nur starten, wenn der Endpunkt nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="acabe-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="acabe-166">Sie können festlegen, dass die geplante Überprüfung nur stattfindet, wenn der Endpunkt aktiviert ist, jedoch nicht mit Gruppenrichtlinien, PowerShell oder WMI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="acabe-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="acabe-167">Bei diesen Überprüfungen wird die KONFIGURATION der CPU-Einschränkung nicht berücksichtigt und die verfügbaren Ressourcen genutzt, um den Scan so schnell wie möglich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="acabe-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="acabe-168">Planen von Scans mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="acabe-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="acabe-169">Speicherort</span><span class="sxs-lookup"><span data-stu-id="acabe-169">Location</span></span> | <span data-ttu-id="acabe-170">Einstellung</span><span class="sxs-lookup"><span data-stu-id="acabe-170">Setting</span></span> | <span data-ttu-id="acabe-171">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acabe-171">Description</span></span> | <span data-ttu-id="acabe-172">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="acabe-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="acabe-173">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-173">Scan</span></span> | <span data-ttu-id="acabe-174">Starten der geplanten Überprüfung nur, wenn der Computer zwar installiert ist, aber nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="acabe-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="acabe-175">Geplante Scans werden nicht ausgeführt, es sei denn, der Computer ist in, aber nicht in Gebrauch.</span><span class="sxs-lookup"><span data-stu-id="acabe-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="acabe-176">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="acabe-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="acabe-177">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="acabe-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="acabe-178">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="acabe-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="acabe-179">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="acabe-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="acabe-180">Verwenden von Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="acabe-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="acabe-181">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="acabe-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="acabe-182">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="acabe-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="acabe-183">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="acabe-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="acabe-184">Konfigurieren, wann vollständige Überprüfungen ausgeführt werden sollen, um die Korrektur durchzuführen</span><span class="sxs-lookup"><span data-stu-id="acabe-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="acabe-185">Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um ihre Entfernung und Behebung abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="acabe-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="acabe-186">Sie können planen, wann diese Überprüfungen mit Gruppenrichtlinien, PowerShell oder WMI durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acabe-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="acabe-187">Planen der erforderlichen Überprüfungen mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="acabe-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="acabe-188">Speicherort</span><span class="sxs-lookup"><span data-stu-id="acabe-188">Location</span></span> | <span data-ttu-id="acabe-189">Einstellung</span><span class="sxs-lookup"><span data-stu-id="acabe-189">Setting</span></span> | <span data-ttu-id="acabe-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acabe-190">Description</span></span> | <span data-ttu-id="acabe-191">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="acabe-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="acabe-192">Korrektur</span><span class="sxs-lookup"><span data-stu-id="acabe-192">Remediation</span></span> | <span data-ttu-id="acabe-193">Angeben des Wochentags zum Ausführen einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur</span><span class="sxs-lookup"><span data-stu-id="acabe-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="acabe-194">Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="acabe-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="acabe-195">Nie</span><span class="sxs-lookup"><span data-stu-id="acabe-195">Never</span></span> |
|<span data-ttu-id="acabe-196">Korrektur</span><span class="sxs-lookup"><span data-stu-id="acabe-196">Remediation</span></span> | <span data-ttu-id="acabe-197">Angeben der Uhrzeit für die Ausführung einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur</span><span class="sxs-lookup"><span data-stu-id="acabe-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="acabe-198">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="acabe-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="acabe-199">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="acabe-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="acabe-200">Verwenden von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="acabe-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="acabe-201">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="acabe-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="acabe-202">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="acabe-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="acabe-203">Verwenden von Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="acabe-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="acabe-204">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="acabe-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="acabe-205">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="acabe-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="acabe-206">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="acabe-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="acabe-207">Einrichten täglicher Schnellscans</span><span class="sxs-lookup"><span data-stu-id="acabe-207">Set up daily quick scans</span></span>

<span data-ttu-id="acabe-208">Sie können eine tägliche Schnellscan aktivieren, die zusätzlich zu ihren anderen geplanten Scans mit Gruppenrichtlinie, PowerShell oder WMI ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="acabe-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="acabe-209">Verwenden von Gruppenrichtlinien zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="acabe-210">Speicherort</span><span class="sxs-lookup"><span data-stu-id="acabe-210">Location</span></span> | <span data-ttu-id="acabe-211">Einstellung</span><span class="sxs-lookup"><span data-stu-id="acabe-211">Setting</span></span> | <span data-ttu-id="acabe-212">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acabe-212">Description</span></span> | <span data-ttu-id="acabe-213">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="acabe-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="acabe-214">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-214">Scan</span></span> | <span data-ttu-id="acabe-215">Angeben des Intervalls zum Ausführen von Schnellscans pro Tag</span><span class="sxs-lookup"><span data-stu-id="acabe-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="acabe-216">Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstreichen sollen.</span><span class="sxs-lookup"><span data-stu-id="acabe-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="acabe-217">Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, und geben Sie einmal pro Tag **24 ein.**</span><span class="sxs-lookup"><span data-stu-id="acabe-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="acabe-218">Geben **Sie 0** ein, um nie einen täglichen Schnellscan ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="acabe-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="acabe-219">Nie</span><span class="sxs-lookup"><span data-stu-id="acabe-219">Never</span></span> |
|<span data-ttu-id="acabe-220">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="acabe-220">Scan</span></span> | <span data-ttu-id="acabe-221">Angeben der Uhrzeit für einen täglichen Schnellscan</span><span class="sxs-lookup"><span data-stu-id="acabe-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="acabe-222">Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein)</span><span class="sxs-lookup"><span data-stu-id="acabe-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="acabe-223">2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="acabe-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="acabe-224">Verwenden von PowerShell-Cmdlets zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="acabe-225">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="acabe-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="acabe-226">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="acabe-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="acabe-227">Verwenden von Windows Management Instruction (WMI) zum Planen täglicher Scans</span><span class="sxs-lookup"><span data-stu-id="acabe-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="acabe-228">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="acabe-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="acabe-229">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="acabe-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="acabe-230">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="acabe-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="acabe-231">Aktivieren von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="acabe-231">Enable scans after protection updates</span></span>

<span data-ttu-id="acabe-232">Sie können erzwingen, dass eine Überprüfung nach jedem Schutzupdate [mit Gruppenrichtlinien](manage-protection-updates-microsoft-defender-antivirus.md) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="acabe-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="acabe-233">Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="acabe-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="acabe-234">Speicherort</span><span class="sxs-lookup"><span data-stu-id="acabe-234">Location</span></span> | <span data-ttu-id="acabe-235">Einstellung</span><span class="sxs-lookup"><span data-stu-id="acabe-235">Setting</span></span> | <span data-ttu-id="acabe-236">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acabe-236">Description</span></span> | <span data-ttu-id="acabe-237">Standardeinstellung (wenn nicht konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="acabe-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="acabe-238">Signaturupdates</span><span class="sxs-lookup"><span data-stu-id="acabe-238">Signature updates</span></span> | <span data-ttu-id="acabe-239">Aktivieren der Überprüfung nach dem Update der Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="acabe-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="acabe-240">Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates.</span><span class="sxs-lookup"><span data-stu-id="acabe-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="acabe-241">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="acabe-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="acabe-242">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acabe-242">See also</span></span>
- [<span data-ttu-id="acabe-243">Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern</span><span class="sxs-lookup"><span data-stu-id="acabe-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acabe-244">Konfigurieren und Ausführen von Bedarfsscans von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="acabe-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acabe-245">Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen</span><span class="sxs-lookup"><span data-stu-id="acabe-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acabe-246">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="acabe-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acabe-247">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="acabe-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="acabe-248">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="acabe-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)