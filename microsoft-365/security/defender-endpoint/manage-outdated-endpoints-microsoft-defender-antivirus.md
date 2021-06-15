---
title: Anwenden von Microsoft Defender AV-Schutzupdates auf veraltete Endpunkte
description: Legen Sie fest, wann und wie Updates für Endpunkte angewendet werden sollen, die seit einer Weile nicht aktualisiert wurden.
keywords: Updates, Schutz, veraltet, veraltet, alt, Nachholbedarf
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
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b141c9b745e560b3c2236a9d073a7b2f3500623c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926043"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="dbfa6-104">Verwalten von Updates und Scans von Microsoft Defender Antivirus für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="dbfa6-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dbfa6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-105">**Applies to:**</span></span>

- [<span data-ttu-id="dbfa6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dbfa6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dbfa6-107">Microsoft Defender Antivirus können Sie definieren, wie lange ein Endpunkt ein Update vermeiden kann oder wie viele Scans es verpassen kann, bevor er sich aktualisieren und scannen muss.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="dbfa6-108">Dies ist besonders nützlich in Umgebungen, in denen Geräte häufig nicht mit einem Unternehmensnetzwerk oder externen Netzwerk verbunden sind oder nicht täglich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="dbfa6-109">Beispielsweise befindet sich ein Mitarbeiter, der einen bestimmten PC verwendet, drei Tage in der Pause und meldet sich während dieser Zeit nicht an ihrem PC an.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="dbfa6-110">Wenn der Benutzer zur Arbeit zurückkehrt und sich auf dem PC anmeldet, werden Microsoft Defender Antivirus sofort die neuesten Schutzupdates überprüfen und herunterladen und eine Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="dbfa6-111">Einrichten von Nachholschutzupdates für Endpunkte, die eine Weile nicht aktualisiert wurden</span><span class="sxs-lookup"><span data-stu-id="dbfa6-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="dbfa6-112">Wenn Microsoft Defender Antivirus für einen bestimmten Zeitraum keine Schutzupdates heruntergeladen haben, können Sie es so einrichten, dass das neueste Update bei der nächsten Anmeldung automatisch überprüft und heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="dbfa6-113">Dies ist nützlich, wenn Sie automatische [Updatedownloads beim Start global deaktiviert](manage-event-based-updates-microsoft-defender-antivirus.md)haben.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="dbfa6-114">Verwenden von Configuration Manager zum Konfigurieren von Nachholschutzupdates</span><span class="sxs-lookup"><span data-stu-id="dbfa6-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="dbfa6-115">Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="dbfa6-116">Wechseln Sie zum Abschnitt **"Security Intelligence Updates",** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="dbfa6-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="dbfa6-118">Geben Sie für den  **If Configuration Manager als Quelle für Sicherheitsupdates an...** die Stunden, vor denen die von Configuration Manager bereitgestellten Schutzupdates als veraltet betrachtet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="dbfa6-119">Dadurch wird der nächste Updatespeicherort basierend auf der definierten [Fallbackquellreihenfolge](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="dbfa6-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-120">Click **OK**.</span></span>

4.  <span data-ttu-id="dbfa6-121">[Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="dbfa6-122">Verwenden von Gruppenrichtlinien zum Aktivieren und Konfigurieren des Nachholupdatefeatures</span><span class="sxs-lookup"><span data-stu-id="dbfa6-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="dbfa6-123">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dbfa6-124">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="dbfa6-125">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="dbfa6-126">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Signaturupdates.**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="dbfa6-127">Doppelklicken Sie auf die Einstellung **"Anzahl der Tage definieren", nach denen ein Update zur Nachholaktualisierung erforderlich ist,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="dbfa6-128">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV das neueste Schutzupdate suchen und herunterladen soll.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="dbfa6-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="dbfa6-130">Verwenden von PowerShell-Cmdlets zum Konfigurieren von Nachholschutzupdates</span><span class="sxs-lookup"><span data-stu-id="dbfa6-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="dbfa6-131">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="dbfa6-132">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="dbfa6-133">Verwenden Windows Management Instruction (WMI) zum Konfigurieren von Nachholschutzupdates</span><span class="sxs-lookup"><span data-stu-id="dbfa6-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="dbfa6-134">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="dbfa6-135">Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="dbfa6-136">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="dbfa6-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="dbfa6-137">Festlegen der Anzahl von Tagen, bevor der Schutz als veraltet gemeldet wird</span><span class="sxs-lookup"><span data-stu-id="dbfa6-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="dbfa6-138">Sie können auch die Anzahl der Tage angeben, nach denen Microsoft Defender Antivirus Schutz als veraltet oder veraltet betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="dbfa6-139">Nach der angegebenen Anzahl von Tagen meldet sich der Client selbst als veraltet und zeigt dem Benutzer des PCs einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="dbfa6-140">Es kann auch dazu führen, dass Microsoft Defender Antivirus versuchen, ein Update aus anderen Quellen herunterzuladen (basierend auf der definierten [Fallbackquellreihenfolge), z.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)B. wenn MMPC als sekundäre Quelle verwendet wird, nachdem WSUS oder Microsoft Update als erste Quelle festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="dbfa6-141">Verwenden von Gruppenrichtlinien zum Angeben der Anzahl von Tagen, bevor der Schutz als veraltet eingestuft wird</span><span class="sxs-lookup"><span data-stu-id="dbfa6-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="dbfa6-142">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="dbfa6-143">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="dbfa6-144">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="dbfa6-145">Erweitern Sie die Struktur bis **Windows Komponenten > Microsoft Defender Antivirus > Signaturupdates,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="dbfa6-146">Doppelklicken Sie auf **"Anzahl der Tage definieren", bevor Spywaredefinitionen als veraltet gelten,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="dbfa6-147">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV die Spyware Security Intelligence als veraltet betrachten soll.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="dbfa6-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="dbfa6-149">Doppelklicken Sie auf **"Anzahl der Tage definieren", bevor Virendefinitionen als veraltet gelten,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="dbfa6-150">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV die Virensicherheitserkennung als veraltet betrachten soll.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="dbfa6-151">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="dbfa6-152">Einrichten von Nachholscans für Endpunkte, die eine Weile nicht gescannt wurden</span><span class="sxs-lookup"><span data-stu-id="dbfa6-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="dbfa6-153">Sie können die Anzahl der aufeinanderfolgenden geplanten Scans festlegen, die verpasst werden können, bevor Microsoft Defender Antivirus eine Überprüfung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="dbfa6-154">Der Prozess zum Aktivieren dieses Features lautet:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="dbfa6-155">Richten Sie mindestens einen geplanten Scan ein (siehe Das Thema ["Scans planen").](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="dbfa6-156">Aktivieren Sie die Funktion für den Nachholscan.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="dbfa6-157">Definieren Sie die Anzahl der Scans, die übersprungen werden können, bevor ein Nachholscan durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="dbfa6-158">Dieses Feature kann sowohl für vollständige als auch für schnelle Scans aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="dbfa6-159">Verwenden von Gruppenrichtlinien zum Aktivieren und Konfigurieren des Nachholscanfeatures</span><span class="sxs-lookup"><span data-stu-id="dbfa6-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="dbfa6-160">Stellen Sie sicher, dass Sie mindestens einen geplanten Scan eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="dbfa6-161">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="dbfa6-162">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="dbfa6-163">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="dbfa6-164">Erweitern Sie die Struktur, um komponenten > Microsoft Defender Antivirus > Scan zu **Windows,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="dbfa6-165">Wenn Sie geplante Schnellscans eingerichtet haben, doppelklicken Sie auf die Einstellung **"Nachholscan aktivieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="dbfa6-166">Wenn Sie geplante vollständige Scans eingerichtet haben, doppelklicken Sie auf die Einstellung **"Nachholvorgang für vollständige Überprüfung** aktivieren", und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="dbfa6-167">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-167">Click **OK**.</span></span>
    3. <span data-ttu-id="dbfa6-168">Doppelklicken Sie auf **die Anzahl der Tage definieren, nach denen eine Nachholüberprüfung erzwungen wird,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="dbfa6-169">Geben Sie die Anzahl der Scans ein, die übersehen werden können, bevor ein Scan automatisch ausgeführt wird, wenn sich der Benutzer das nächste Mal am PC anmeldet.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="dbfa6-170">Der Typ des ausgeführten Scans wird durch die **Angabe des Scantyps bestimmt, der für eine geplante Überprüfung verwendet werden soll** (siehe Das Thema ["Scans planen").](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="dbfa6-171">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbfa6-172">Der Titel der Gruppenrichtlinieneinstellung bezieht sich auf die Anzahl der Tage.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="dbfa6-173">Die Einstellung wird jedoch auf die Anzahl der Scans (nicht Tage) angewendet, bevor der Nachholscan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="dbfa6-174">Verwenden von PowerShell-Cmdlets zum Konfigurieren von Nachholscans</span><span class="sxs-lookup"><span data-stu-id="dbfa6-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="dbfa6-175">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="dbfa6-176">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Verwalten von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="dbfa6-177">Verwenden Windows Management Instruction (WMI) zum Konfigurieren von Nachholscans</span><span class="sxs-lookup"><span data-stu-id="dbfa6-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="dbfa6-178">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="dbfa6-179">Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="dbfa6-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="dbfa6-180">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="dbfa6-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="dbfa6-181">Verwenden von Configuration Manager zum Konfigurieren von Nachholscans</span><span class="sxs-lookup"><span data-stu-id="dbfa6-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="dbfa6-182">Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="dbfa6-183">Wechseln Sie zum Abschnitt **"Geplante Scans",** und **erzwingen Sie eine Überprüfung des ausgewählten Scantyps, wenn der Clientcomputer offline ist...** auf **"Ja".**</span><span class="sxs-lookup"><span data-stu-id="dbfa6-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="dbfa6-184">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa6-184">Click **OK**.</span></span>

4.  <span data-ttu-id="dbfa6-185">[Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="dbfa6-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="dbfa6-186">Related articles</span></span>

- [<span data-ttu-id="dbfa6-187">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="dbfa6-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbfa6-188">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="dbfa6-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbfa6-189">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="dbfa6-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbfa6-190">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="dbfa6-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbfa6-191">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="dbfa6-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbfa6-192">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="dbfa6-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)