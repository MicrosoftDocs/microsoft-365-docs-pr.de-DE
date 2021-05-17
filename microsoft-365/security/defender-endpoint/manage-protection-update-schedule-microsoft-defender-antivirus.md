---
title: Planen Microsoft Defender Antivirus Von Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Zeitpunkt des Herunterladens von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Zeitplanupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275036"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="703ae-104">Verwalten des Zeitplans für Download und Anwendung von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="703ae-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="703ae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="703ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="703ae-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="703ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="703ae-107">Microsoft Defender Antivirus können Sie bestimmen, wann updates suchen und heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="703ae-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="703ae-108">Sie können Updates für Ihre Endpunkte planen, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="703ae-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="703ae-109">Angeben des Wochentags, der auf Schutzupdates überprüft werden soll</span><span class="sxs-lookup"><span data-stu-id="703ae-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="703ae-110">Angeben des Intervalls, das auf Schutzupdates überprüft werden soll</span><span class="sxs-lookup"><span data-stu-id="703ae-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="703ae-111">Angeben der Zeit für die Überprüfung auf Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="703ae-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="703ae-112">Sie können auch die Zeiten randomisieren, zu denen jeder Endpunkt Schutzupdates überprüft und herunterlässt.</span><span class="sxs-lookup"><span data-stu-id="703ae-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="703ae-113">Weitere Informationen [finden](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Sie im Thema Zeitplanscans.</span><span class="sxs-lookup"><span data-stu-id="703ae-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="703ae-114">Planen von Schutzupdates mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="703ae-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="703ae-115">Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)</span><span class="sxs-lookup"><span data-stu-id="703ae-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="703ae-116">Wechseln Sie zum Abschnitt **Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="703ae-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="703ae-117">So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:</span><span class="sxs-lookup"><span data-stu-id="703ae-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="703ae-118">Legen **Sie überprüfen Endpoint Protection Sicherheitsintelligenzupdates in einem bestimmten** Intervall fest... auf **0**.</span><span class="sxs-lookup"><span data-stu-id="703ae-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="703ae-119">Legen **Sie check for Endpoint Protection security intelligence updates daily at...** auf den Zeitpunkt, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="703ae-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="703ae-120">3</span><span class="sxs-lookup"><span data-stu-id="703ae-120">3</span></span>
4. <span data-ttu-id="703ae-121">Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen Sie die Überprüfung auf Endpoint Protection Sicherheitsintelligenzupdates in einem bestimmten Intervall **fest...** auf die Anzahl der Stunden, die zwischen Updates auftreten sollten.</span><span class="sxs-lookup"><span data-stu-id="703ae-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="703ae-122">[Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="703ae-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="703ae-123">Planen von Schutzupdates mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="703ae-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="703ae-124">Standardmäßig wird Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans auf ein Update überprüft.</span><span class="sxs-lookup"><span data-stu-id="703ae-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="703ae-125">Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="703ae-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="703ae-126">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="703ae-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="703ae-127">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="703ae-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="703ae-128">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="703ae-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="703ae-129">Erweitern Sie die **Struktur, Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Signature Intelligence Updates** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="703ae-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="703ae-130">Doppelklicken Sie auf die Einstellung Tag **der** Woche angeben, um nach Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="703ae-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="703ae-131">Geben Sie den Wochentag ein, um nach Updates zu suchen.</span><span class="sxs-lookup"><span data-stu-id="703ae-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="703ae-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="703ae-132">Click **OK**.</span></span>
    2. <span data-ttu-id="703ae-133">Doppelklicken Sie auf die Einstellung Intervall **angeben, um nach** Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="703ae-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="703ae-134">Geben Sie die Anzahl der Stunden zwischen Updates ein.</span><span class="sxs-lookup"><span data-stu-id="703ae-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="703ae-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="703ae-135">Click **OK**.</span></span>
    3. <span data-ttu-id="703ae-136">Doppelklicken Sie auf die Einstellung Zeit **zum Überprüfen** von Sicherheitsintelligenzupdates angeben, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="703ae-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="703ae-137">Geben Sie den Zeitpunkt ein, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="703ae-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="703ae-138">Die Uhrzeit basiert auf der Ortszeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="703ae-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="703ae-139">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="703ae-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="703ae-140">Verwenden von PowerShell-Cmdlets zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="703ae-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="703ae-141">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="703ae-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="703ae-142">Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="703ae-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="703ae-143">Verwenden Windows Management Instruction (WMI) zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="703ae-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="703ae-144">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="703ae-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="703ae-145">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="703ae-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="703ae-146">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="703ae-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="703ae-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="703ae-147">Related articles</span></span>

- [<span data-ttu-id="703ae-148">Bereitstellen Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="703ae-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="703ae-149">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines</span><span class="sxs-lookup"><span data-stu-id="703ae-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="703ae-150">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="703ae-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="703ae-151">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="703ae-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="703ae-152">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="703ae-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="703ae-153">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="703ae-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)