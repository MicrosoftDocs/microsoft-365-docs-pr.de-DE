---
title: Planen von Microsoft Defender Antivirus-Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Zeitpunkt des Herunterladens von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Zeitplanupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690425"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="acb15-104">Verwalten des Zeitplans für den Download und die Anwendung von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="acb15-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="acb15-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="acb15-105">**Applies to:**</span></span>

- [<span data-ttu-id="acb15-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="acb15-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="acb15-107">Mit Microsoft Defender Antivirus können Sie bestimmen, wann Updates suchen und heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acb15-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="acb15-108">Sie können Updates für Ihre Endpunkte planen, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="acb15-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="acb15-109">Angeben des Wochentags, der auf Schutzupdates überprüft werden soll</span><span class="sxs-lookup"><span data-stu-id="acb15-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="acb15-110">Angeben des Intervalls, das auf Schutzupdates überprüft werden soll</span><span class="sxs-lookup"><span data-stu-id="acb15-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="acb15-111">Angeben der Zeit für die Überprüfung auf Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="acb15-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="acb15-112">Sie können auch die Zeiten randomisieren, zu denen jeder Endpunkt Schutzupdates überprüft und herunterlässt.</span><span class="sxs-lookup"><span data-stu-id="acb15-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="acb15-113">Weitere Informationen [finden](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Sie im Thema Zeitplanscans.</span><span class="sxs-lookup"><span data-stu-id="acb15-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="acb15-114">Planen von Schutzupdates mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="acb15-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="acb15-115">Öffnen Sie in der Microsoft Endpoint Manager-Konsole die Richtlinie  für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur zu **Übersicht**  >  **Endpoint Protection**  >  **Anmalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="acb15-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="acb15-116">Wechseln Sie zum Abschnitt **Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="acb15-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="acb15-117">So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:</span><span class="sxs-lookup"><span data-stu-id="acb15-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="acb15-118">Legen **Sie die Überprüfung auf Endpoint Protection Security Intelligence-Updates in einem bestimmten Intervall... auf** **0 fest.**</span><span class="sxs-lookup"><span data-stu-id="acb15-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="acb15-119">Legen **Sie täglich check for Endpoint Protection security intelligence updates at...** auf den Zeitpunkt, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acb15-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="acb15-120">3</span><span class="sxs-lookup"><span data-stu-id="acb15-120">3</span></span>
4. <span data-ttu-id="acb15-121">Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen Sie Die Überprüfung auf Endpoint Protection-Sicherheitsintelligenzupdates in einem bestimmten Intervall **fest...** auf die Anzahl der Stunden, die zwischen Updates auftreten sollten.</span><span class="sxs-lookup"><span data-stu-id="acb15-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="acb15-122">[Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="acb15-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="acb15-123">Planen von Schutzupdates mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="acb15-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acb15-124">Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update.</span><span class="sxs-lookup"><span data-stu-id="acb15-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="acb15-125">Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="acb15-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="acb15-126">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="acb15-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="acb15-127">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="acb15-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="acb15-128">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="acb15-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="acb15-129">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature Intelligence  >  **Updates,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="acb15-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="acb15-130">Doppelklicken Sie auf die Einstellung Tag **der** Woche angeben, um nach Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="acb15-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="acb15-131">Geben Sie den Wochentag ein, um nach Updates zu suchen.</span><span class="sxs-lookup"><span data-stu-id="acb15-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="acb15-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="acb15-132">Click **OK**.</span></span>
    2. <span data-ttu-id="acb15-133">Doppelklicken Sie auf die Einstellung Intervall **angeben, um nach** Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="acb15-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="acb15-134">Geben Sie die Anzahl der Stunden zwischen Updates ein.</span><span class="sxs-lookup"><span data-stu-id="acb15-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="acb15-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="acb15-135">Click **OK**.</span></span>
    3. <span data-ttu-id="acb15-136">Doppelklicken Sie auf die Einstellung Zeit **zum Überprüfen** von Sicherheitsintelligenzupdates angeben, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="acb15-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="acb15-137">Geben Sie den Zeitpunkt ein, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acb15-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="acb15-138">Die Uhrzeit basiert auf der Ortszeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="acb15-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="acb15-139">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="acb15-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="acb15-140">Verwenden von PowerShell-Cmdlets zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="acb15-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="acb15-141">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="acb15-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="acb15-142">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="acb15-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="acb15-143">Planen von Schutzupdates mithilfe von Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="acb15-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="acb15-144">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="acb15-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="acb15-145">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="acb15-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="acb15-146">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="acb15-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="acb15-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="acb15-147">Related articles</span></span>

- [<span data-ttu-id="acb15-148">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="acb15-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acb15-149">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="acb15-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acb15-150">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="acb15-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acb15-151">Verwalten ereignisbasierter erzwungener Updates</span><span class="sxs-lookup"><span data-stu-id="acb15-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acb15-152">Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="acb15-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="acb15-153">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="acb15-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)