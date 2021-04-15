---
title: Anwenden von Microsoft Defender Antivirus-Updates nach bestimmten Ereignissen
description: Verwalten, wie Microsoft Defender Antivirus Sicherheitsintelligenzupdates nach dem Start oder dem Empfangen von in der Cloud übermittelten Erkennungsberichten verwendet.
keywords: updates, protection, force updates, events, startup, check for latest, notifications
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 78a04105fce0a3a1f9f7ea3f9ee993dd53750f3f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764555"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="708df-104">Verwalten ereignisbasierter erzwungener Updates</span><span class="sxs-lookup"><span data-stu-id="708df-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="708df-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="708df-105">**Applies to:**</span></span>

- [<span data-ttu-id="708df-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="708df-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="708df-107">Mit Microsoft Defender Antivirus können Sie ermitteln, ob Updates nach bestimmten Ereignissen auftreten sollten (oder nicht), z. B. nach dem Start oder nach dem Empfangen bestimmter Berichte vom in der Cloud übermittelten Schutzdienst.</span><span class="sxs-lookup"><span data-stu-id="708df-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="708df-108">Überprüfen sie vor dem Ausführen einer Überprüfung auf Schutzupdates.</span><span class="sxs-lookup"><span data-stu-id="708df-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="708df-109">Sie können Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets und WMI verwenden, um Microsoft Defender Antivirus zu zwingen, Schutzupdates zu überprüfen und herunterzuladen, bevor Sie eine geplante Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="708df-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="708df-110">Verwenden von Configuration Manager zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="708df-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="708df-111">Öffnen Sie in der Microsoft Endpoint Manager-Konsole die Richtlinie  für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur zu **Übersicht**  >  **Endpoint Protection**  >  **Anmalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="708df-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="708df-112">Wechseln Sie zum **Abschnitt Geplante Scans,** und legen Sie Auf die neuesten Sicherheitsintelligenzupdates **überprüfen fest,** bevor Sie eine Überprüfung auf **Ja ausführen.**</span><span class="sxs-lookup"><span data-stu-id="708df-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="708df-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-113">Click **OK**.</span></span>

4. <span data-ttu-id="708df-114">[Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="708df-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="708df-115">Verwenden von Gruppenrichtlinien zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="708df-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="708df-116">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="708df-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="708df-117">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="708df-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="708df-118">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="708df-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="708df-119">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="708df-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="708df-120">Doppelklicken Sie auf **Die neuesten Viren-** und Spywaredefinitionen überprüfen, bevor Sie einen geplanten Scan ausführen, und legen Sie die Option auf Aktiviert **fest.**</span><span class="sxs-lookup"><span data-stu-id="708df-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="708df-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="708df-122">Verwenden von PowerShell-Cmdlets zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="708df-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="708df-123">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="708df-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="708df-124">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="708df-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="708df-125">Verwenden der Windows-Verwaltungsanweisung (WMI), um vor dem Ausführen einer Überprüfung nach Schutzupdates zu suchen</span><span class="sxs-lookup"><span data-stu-id="708df-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="708df-126">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="708df-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="708df-127">Weitere Informationen finden Sie unter [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="708df-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="708df-128">Überprüfen auf Schutzupdates beim Start</span><span class="sxs-lookup"><span data-stu-id="708df-128">Check for protection updates on startup</span></span>

<span data-ttu-id="708df-129">Mithilfe von Gruppenrichtlinien können Sie Microsoft Defender Antivirus zwingen, Schutzupdates zu überprüfen und herunterzuladen, wenn der Computer gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="708df-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="708df-130">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="708df-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="708df-131">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="708df-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="708df-132">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="708df-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="708df-133">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="708df-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="708df-134">Doppelklicken Sie **auf Die neuesten Viren-** und Spywaredefinitionen beim Start überprüfen, und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="708df-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="708df-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-135">Click **OK**.</span></span>

<span data-ttu-id="708df-136">Sie können auch Gruppenrichtlinien, PowerShell oder WMI verwenden, um Microsoft Defender Antivirus so zu konfigurieren, dass updates beim Start überprüft werden, auch wenn es nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="708df-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="708df-137">Verwenden von Gruppenrichtlinien zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="708df-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="708df-138">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="708df-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="708df-139">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="708df-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="708df-140">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="708df-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="708df-141">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="708df-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="708df-142">Doppelklicken Sie beim **Start auf Sicherheitsintelligenzupdate initiieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="708df-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="708df-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="708df-144">Verwenden von PowerShell-Cmdlets zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="708df-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="708df-145">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="708df-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="708df-146">Weitere Informationen finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Verwalten von Microsoft Defender Antivirus- und [Defender-Cmdlets,](/powershell/module/defender/index) um weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="708df-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="708df-147">Verwenden von Windows Management Instruction (WMI) zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="708df-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="708df-148">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="708df-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="708df-149">Weitere Informationen finden Sie unter [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="708df-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="708df-150">Zulassen von Ad-hoc-Änderungen am Schutz basierend auf cloudbasiertem Schutz</span><span class="sxs-lookup"><span data-stu-id="708df-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="708df-151">Microsoft Defender AV kann änderungen an seinem Schutz basierend auf cloudbasiertem Schutz vornehmen.</span><span class="sxs-lookup"><span data-stu-id="708df-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="708df-152">Solche Änderungen können außerhalb normaler oder geplanter Schutzupdates auftreten.</span><span class="sxs-lookup"><span data-stu-id="708df-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="708df-153">Wenn Sie den in der Cloud übermittelten Schutz aktiviert haben, sendet Microsoft Defender AV Dateien, die verdächtig sind, an die Windows Defender cloud.</span><span class="sxs-lookup"><span data-stu-id="708df-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="708df-154">Wenn der Clouddienst meldet, dass die Datei schädlich ist und die Datei in einem aktuellen Schutzupdate erkannt wird, können Sie mithilfe von Gruppenrichtlinien Microsoft Defender AV so konfigurieren, dass dieses Schutzupdate automatisch empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="708df-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="708df-155">Es können auch andere wichtige Schutzupdates angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="708df-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="708df-156">Verwenden von Gruppenrichtlinien zum automatischen Herunterladen aktueller Updates basierend auf cloudbasiertem Schutz</span><span class="sxs-lookup"><span data-stu-id="708df-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="708df-157">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="708df-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="708df-158">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="708df-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="708df-159">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="708df-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="708df-160">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="708df-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="708df-161">Doppelklicken Sie **auf Echtzeit-Sicherheitsintelligenzupdates** basierend auf Berichten an Microsoft MAPS zulassen, und legen Sie die Option auf Aktiviert **.**</span><span class="sxs-lookup"><span data-stu-id="708df-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="708df-162">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-162">Then click **OK**.</span></span>

6. <span data-ttu-id="708df-163">**Zulassen, dass Benachrichtigungen definitionsbasierte Berichte für Microsoft MAPS** deaktivieren und die Option auf Aktiviert **festlegen.**</span><span class="sxs-lookup"><span data-stu-id="708df-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="708df-164">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="708df-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="708df-165">**Wenn Sie Benachrichtigungen zum Deaktivieren definitionsbasierter Berichte** zulassen, können sie von Microsoft MAPS deaktiviert werden, wenn bekannt ist, dass falsch positive Berichte verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="708df-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="708df-166">Sie müssen Ihren Computer so konfigurieren, dass er Microsoft MAPS beitritt, damit diese Funktion funktioniert.</span><span class="sxs-lookup"><span data-stu-id="708df-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="708df-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="708df-167">See also</span></span>

- [<span data-ttu-id="708df-168">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="708df-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="708df-169">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="708df-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="708df-170">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="708df-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="708df-171">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="708df-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="708df-172">Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="708df-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="708df-173">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="708df-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)