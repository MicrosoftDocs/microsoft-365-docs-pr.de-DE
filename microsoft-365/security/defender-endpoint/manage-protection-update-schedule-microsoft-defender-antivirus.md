---
title: Planen Microsoft Defender Antivirus Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Download von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Updates planen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: abb656586d6a7bd779b109fcad3c777016fef980
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926055"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="390a8-104">Verwalten des Zeitplans für Download und Anwendung von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="390a8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="390a8-105">**Applies to:**</span></span>

- [<span data-ttu-id="390a8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="390a8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="390a8-107">Microsoft Defender Antivirus können Sie bestimmen, wann updates gesucht und heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="390a8-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="390a8-108">Sie können Updates für Ihre Endpunkte planen, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="390a8-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="390a8-109">Angeben des Wochentags, an dem nach Schutzupdates gesucht werden soll</span><span class="sxs-lookup"><span data-stu-id="390a8-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="390a8-110">Angeben des zu überprüfenden Intervalls für Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="390a8-111">Angeben der Zeit für die Suche nach Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="390a8-112">Sie können auch zufällig festlegen, wann jeder Endpunkt Schutzupdates überprüft und herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="390a8-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="390a8-113">Weitere Informationen finden Sie im Thema ["Scans planen".](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="390a8-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="390a8-114">Verwenden von Configuration Manager zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="390a8-115">Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**</span><span class="sxs-lookup"><span data-stu-id="390a8-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="390a8-116">Wechseln Sie zum Abschnitt **"Security Intelligence Updates".**</span><span class="sxs-lookup"><span data-stu-id="390a8-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="390a8-117">So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:</span><span class="sxs-lookup"><span data-stu-id="390a8-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="390a8-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span><span class="sxs-lookup"><span data-stu-id="390a8-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="390a8-119">Legen **Sie Check for Endpoint Protection security intelligence updates daily** at... auf den Zeitpunkt fest, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="390a8-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="390a8-120">3</span><span class="sxs-lookup"><span data-stu-id="390a8-120">3</span></span>
4. <span data-ttu-id="390a8-121">Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen **Sie die Suche nach Endpoint Protection Sicherheitsupdates in einem bestimmten Intervall...** auf die Anzahl der Stunden fest, die zwischen Updates auftreten sollten.</span><span class="sxs-lookup"><span data-stu-id="390a8-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="390a8-122">[Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="390a8-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="390a8-123">Verwenden von Gruppenrichtlinien zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="390a8-124">Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update.</span><span class="sxs-lookup"><span data-stu-id="390a8-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="390a8-125">Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="390a8-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="390a8-126">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="390a8-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="390a8-127">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="390a8-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="390a8-128">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="390a8-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="390a8-129">Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signature Intelligence Updates,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="390a8-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="390a8-130">Doppelklicken Sie auf den Tag der Woche angeben, um nach der Einstellung **für Sicherheitsupdates zu suchen,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="390a8-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="390a8-131">Geben Sie den Wochentag ein, an dem nach Updates gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="390a8-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="390a8-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="390a8-132">Click **OK**.</span></span>
    2. <span data-ttu-id="390a8-133">Doppelklicken Sie auf die Einstellung **"Intervall zum Suchen** nach Sicherheitsupdates angeben", und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="390a8-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="390a8-134">Geben Sie die Anzahl der Stunden zwischen Updates ein.</span><span class="sxs-lookup"><span data-stu-id="390a8-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="390a8-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="390a8-135">Click **OK**.</span></span>
    3. <span data-ttu-id="390a8-136">Doppelklicken Sie auf die Einstellung **"Zeitpunkt für die Überprüfung auf Sicherheitsupdates angeben",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="390a8-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="390a8-137">Geben Sie den Zeitpunkt ein, zu dem Updates überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="390a8-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="390a8-138">Die Uhrzeit basiert auf der Ortszeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="390a8-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="390a8-139">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="390a8-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="390a8-140">Verwenden von PowerShell-Cmdlets zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="390a8-141">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="390a8-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="390a8-142">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="390a8-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="390a8-143">Verwenden Windows Management Instruction (WMI) zum Planen von Schutzupdates</span><span class="sxs-lookup"><span data-stu-id="390a8-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="390a8-144">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="390a8-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="390a8-145">Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="390a8-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="390a8-146">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="390a8-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="390a8-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="390a8-147">Related articles</span></span>

- [<span data-ttu-id="390a8-148">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="390a8-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="390a8-149">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="390a8-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="390a8-150">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="390a8-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="390a8-151">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="390a8-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="390a8-152">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="390a8-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="390a8-153">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="390a8-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)