---
title: Anwenden Microsoft Defender Antivirus Updates nach bestimmten Ereignissen
description: Verwalten Sie, wie Microsoft Defender Antivirus Updates zur Sicherheitsintelligenz nach dem Starten oder Empfangen von über die Cloud bereitgestellten Erkennungsberichten anwendet.
keywords: Updates, Schutz, Updates erzwingen, Ereignisse, Starten, nach neuesten suchen, Benachrichtigungen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926079"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="ab152-104">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="ab152-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab152-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ab152-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab152-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ab152-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ab152-107">mit Microsoft Defender Antivirus können Sie ermitteln, ob Updates nach bestimmten Ereignissen erfolgen sollen (oder nicht), z. B. beim Start oder nach Erhalt bestimmter Berichte vom über die Cloud bereitgestellten Schutzdienst.</span><span class="sxs-lookup"><span data-stu-id="ab152-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="ab152-108">Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ab152-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="ab152-109">Sie können Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets und WMI verwenden, um Microsoft Defender Antivirus zu erzwingen, Schutzupdates zu überprüfen und herunterzuladen, bevor Sie eine geplante Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab152-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="ab152-110">Verwenden von Configuration Manager zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ab152-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="ab152-111">Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**</span><span class="sxs-lookup"><span data-stu-id="ab152-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="ab152-112">Wechseln Sie zum Abschnitt **"Geplante Scans",** und legen **Sie "Überprüfen auf die neuesten Sicherheitsupdates"** fest, bevor Sie eine Überprüfung auf **"Ja"** ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab152-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="ab152-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-113">Click **OK**.</span></span>

4. <span data-ttu-id="ab152-114">[Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="ab152-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="ab152-115">Verwenden von Gruppenrichtlinien zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ab152-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="ab152-116">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="ab152-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ab152-117">Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ab152-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ab152-118">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="ab152-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ab152-119">Erweitern Sie die Struktur, um **komponenten Microsoft Defender Antivirus**  >  Scan **Windows.**  >  </span><span class="sxs-lookup"><span data-stu-id="ab152-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="ab152-120">Doppelklicken Sie auf **"Nach den neuesten Viren- und Spywaredefinitionen suchen", bevor Sie einen geplanten Scan ausführen,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="ab152-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="ab152-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="ab152-122">Verwenden von PowerShell-Cmdlets zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ab152-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="ab152-123">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ab152-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="ab152-124">Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="ab152-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="ab152-125">Verwenden Windows Management Instruction (WMI) zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ab152-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="ab152-126">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab152-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="ab152-127">Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="ab152-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="ab152-128">Suchen nach Schutzupdates beim Start</span><span class="sxs-lookup"><span data-stu-id="ab152-128">Check for protection updates on startup</span></span>

<span data-ttu-id="ab152-129">Mithilfe von Gruppenrichtlinien können Sie erzwingen, dass Microsoft Defender Antivirus Schutzupdates beim Starten des Computers überprüfen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ab152-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="ab152-130">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="ab152-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ab152-131">Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ab152-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ab152-132">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="ab152-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ab152-133">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="ab152-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="ab152-134">Doppelklicken **Sie beim Start auf "Nach den neuesten Viren- und Spywaredefinitionen suchen",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="ab152-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="ab152-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-135">Click **OK**.</span></span>

<span data-ttu-id="ab152-136">Sie können auch Gruppenrichtlinien, PowerShell oder WMI verwenden, um Microsoft Defender Antivirus zu konfigurieren, um beim Start nach Updates zu suchen, auch wenn sie nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab152-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="ab152-137">Verwenden von Gruppenrichtlinien zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="ab152-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="ab152-138">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="ab152-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ab152-139">Wechseln Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ab152-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ab152-140">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="ab152-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ab152-141">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="ab152-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="ab152-142">Doppelklicken Sie **beim Start auf "Security Intelligence Update initiieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="ab152-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="ab152-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="ab152-144">Verwenden von PowerShell-Cmdlets zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="ab152-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="ab152-145">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ab152-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="ab152-146">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets](/powershell/module/defender/index) für weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="ab152-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="ab152-147">Verwenden Windows Management Instruction (WMI) zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="ab152-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="ab152-148">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab152-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="ab152-149">Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="ab152-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="ab152-150">Zulassen von Ad-hoc-Änderungen am Schutz basierend auf dem über die Cloud bereitgestellten Schutz</span><span class="sxs-lookup"><span data-stu-id="ab152-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="ab152-151">Microsoft Defender AV kann Änderungen an seinem Schutz basierend auf dem über die Cloud bereitgestellten Schutz vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ab152-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="ab152-152">Solche Änderungen können außerhalb von normalen oder geplanten Schutzupdates auftreten.</span><span class="sxs-lookup"><span data-stu-id="ab152-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="ab152-153">Wenn Sie den über die Cloud bereitgestellten Schutz aktiviert haben, sendet Microsoft Defender AV Dateien, die verdächtig sind, an die Windows Defender Cloud.</span><span class="sxs-lookup"><span data-stu-id="ab152-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="ab152-154">Wenn der Clouddienst meldet, dass die Datei bösartig ist und die Datei in einem kürzlichen Schutzupdate erkannt wird, können Sie Mithilfe von Gruppenrichtlinien Microsoft Defender AV so konfigurieren, dass dieses Schutzupdate automatisch empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="ab152-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="ab152-155">Es können auch andere wichtige Schutzupdates angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab152-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="ab152-156">Verwenden von Gruppenrichtlinien zum automatischen Herunterladen der neuesten Updates basierend auf dem über die Cloud bereitgestellten Schutz</span><span class="sxs-lookup"><span data-stu-id="ab152-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="ab152-157">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="ab152-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ab152-158">Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ab152-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ab152-159">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="ab152-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ab152-160">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="ab152-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="ab152-161">Doppelklicken Sie auf Updates zur **Echtzeitsicherheitserkennung basierend auf Berichten an Microsoft MAPS zulassen,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="ab152-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="ab152-162">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-162">Then click **OK**.</span></span>

6. <span data-ttu-id="ab152-163">**Zulassen, dass Benachrichtigungen definitionsbasierte Berichte an Microsoft MAPS deaktivieren** und die Option auf **"Aktiviert"** festlegen.</span><span class="sxs-lookup"><span data-stu-id="ab152-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="ab152-164">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab152-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab152-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span><span class="sxs-lookup"><span data-stu-id="ab152-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="ab152-166">Sie müssen Ihren Computer so konfigurieren, dass er Microsoft MAPS beitritt, damit diese Funktion funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ab152-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab152-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab152-167">See also</span></span>

- [<span data-ttu-id="ab152-168">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ab152-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab152-169">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="ab152-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab152-170">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="ab152-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab152-171">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="ab152-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab152-172">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="ab152-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab152-173">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab152-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)