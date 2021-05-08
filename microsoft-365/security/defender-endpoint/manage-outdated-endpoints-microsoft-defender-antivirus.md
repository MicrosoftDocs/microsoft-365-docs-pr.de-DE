---
title: Anwenden von Microsoft Defender AV-Schutzupdates auf veraltete Endpunkte
description: Definieren Sie, wann und wie Updates für Endpunkte angewendet werden sollen, die in einer Weile nicht aktualisiert wurden.
keywords: updates, protection, out-of-date, outdated, old, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275060"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="8e502-104">Verwalten von Updates und Scans von Microsoft Defender Antivirus für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="8e502-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8e502-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8e502-105">**Applies to:**</span></span>

- [<span data-ttu-id="8e502-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8e502-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8e502-107">Microsoft Defender Antivirus können Sie definieren, wie lange ein Endpunkt ein Update vermeiden kann oder wie viele Scans er verpassen kann, bevor er selbst aktualisiert und überprüft werden muss.</span><span class="sxs-lookup"><span data-stu-id="8e502-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="8e502-108">Dies ist besonders in Umgebungen hilfreich, in denen Geräte nicht häufig mit einem Unternehmens- oder externen Netzwerk verbunden sind oder geräte, die nicht täglich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e502-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="8e502-109">Beispielsweise ist ein Mitarbeiter, der einen bestimmten PC verwendet, drei Tage in Der Pause und loggt sich während dieser Zeit nicht bei ihrem PC an.</span><span class="sxs-lookup"><span data-stu-id="8e502-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="8e502-110">Wenn der Benutzer zur Arbeit zurückkehrt und sich am PC anmeldet, Microsoft Defender Antivirus sofort die neuesten Schutzupdates überprüfen und herunterladen und eine Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="8e502-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="8e502-111">Einrichten von Nachholschutzupdates für Endpunkte, die eine Weile nicht aktualisiert wurden</span><span class="sxs-lookup"><span data-stu-id="8e502-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="8e502-112">Wenn Microsoft Defender Antivirus schutzupdates für einen bestimmten Zeitraum nicht heruntergeladen haben, können Sie es so einrichten, dass das neueste Update bei der nächsten Anmeldung automatisch überprüft und heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="8e502-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="8e502-113">Dies ist nützlich, wenn Sie beim Start [die Downloads automatischer Updates global deaktiviert haben.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8e502-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8e502-114">Konfigurieren von Nachholschutzupdates mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e502-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="8e502-115">Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)</span><span class="sxs-lookup"><span data-stu-id="8e502-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8e502-116">Wechseln Sie zum Abschnitt **Sicherheitsintelligenzupdates,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="8e502-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="8e502-117">Legen **Sie Force a security intelligence update fest, wenn der Clientcomputer für** mehr als zwei aufeinander folgende geplante Updates offline ist, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8e502-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="8e502-118">Geben Sie  **für if Configuration Manager als** Quelle für Sicherheitsintelligenzupdates... die Stunden an, bevor die von Configuration Manager übermittelten Schutzupdates als veraltet betrachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="8e502-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="8e502-119">Dadurch wird der nächste Aktualisierungsspeicherort basierend auf der definierten [Fallbackquellenreihenfolge verwendet.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="8e502-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="8e502-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-120">Click **OK**.</span></span>

4.  <span data-ttu-id="8e502-121">[Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="8e502-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="8e502-122">Aktivieren und Konfigurieren des Nachholupdatefeatures mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8e502-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="8e502-123">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8e502-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8e502-124">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8e502-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8e502-125">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="8e502-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="8e502-126">Erweitern Sie die Struktur, **Windows komponenten > Microsoft Defender Antivirus > Signaturupdates .**</span><span class="sxs-lookup"><span data-stu-id="8e502-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="8e502-127">Doppelklicken Sie auf Die Anzahl **der** Tage definieren, nach denen ein Nachholupdate für die Sicherheitsintelligenz erforderlich ist, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="8e502-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8e502-128">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV das neueste Schutzupdate überprüfen und herunterladen soll.</span><span class="sxs-lookup"><span data-stu-id="8e502-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="8e502-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8e502-130">Konfigurieren von Nachholschutzupdates mithilfe von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8e502-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="8e502-131">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8e502-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="8e502-132">Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8e502-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="8e502-133">Konfigurieren von Nachholschutzupdates mithilfe Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="8e502-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="8e502-134">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8e502-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="8e502-135">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="8e502-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8e502-136">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="8e502-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="8e502-137">Festlegen der Anzahl von Tagen, bevor der Schutz als veraltet gemeldet wird</span><span class="sxs-lookup"><span data-stu-id="8e502-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="8e502-138">Sie können auch die Anzahl der Tage angeben, nach denen Microsoft Defender Antivirus schutz als alt oder veraltet betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="8e502-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="8e502-139">Nach der angegebenen Anzahl von Tagen wird der Client sich selbst als veraltet melden und dem Benutzer des PCs einen Fehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e502-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="8e502-140">Es kann auch dazu führen, dass Microsoft Defender Antivirus versuchen, ein Update [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)aus anderen Quellen herunterzuladen (basierend auf der definierten Fallback-Quellreihenfolge), z. B. wenn MMPC als sekundäre Quelle verwendet wird, nachdem WSUS oder Microsoft Update als erste Quelle festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="8e502-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="8e502-141">Verwenden von Gruppenrichtlinien zum Angeben der Anzahl von Tagen, bevor der Schutz als veraltet angesehen wird</span><span class="sxs-lookup"><span data-stu-id="8e502-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="8e502-142">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8e502-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8e502-143">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8e502-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8e502-144">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="8e502-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8e502-145">Erweitern Sie die **Struktur, Windows Komponenten > Microsoft Defender Antivirus > Signaturupdates** hinzufügen und die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8e502-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8e502-146">Doppelklicken Sie auf Die Anzahl der Tage **definieren,** bevor Spywaredefinitionen als veraltet angesehen werden, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="8e502-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8e502-147">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV spyware Security Intelligence als veraltet betrachten soll.</span><span class="sxs-lookup"><span data-stu-id="8e502-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="8e502-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="8e502-149">Doppelklicken Sie auf Die Anzahl der Tage **definieren,** bevor Virendefinitionen als veraltet angesehen werden, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="8e502-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="8e502-150">Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV Virensicherheitsintelligenz als veraltet betrachten soll.</span><span class="sxs-lookup"><span data-stu-id="8e502-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="8e502-151">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="8e502-152">Einrichten von Nachholscans für Endpunkte, die eine Weile nicht überprüft wurden</span><span class="sxs-lookup"><span data-stu-id="8e502-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="8e502-153">Sie können die Anzahl der aufeinander folgenden geplanten Scans festlegen, die verpasst werden können, Microsoft Defender Antivirus eine Überprüfung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8e502-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="8e502-154">Der Vorgang zum Aktivieren dieses Features ist:</span><span class="sxs-lookup"><span data-stu-id="8e502-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="8e502-155">Richten Sie mindestens einen geplanten Scan ein (siehe [thema Schedule scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8e502-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="8e502-156">Aktivieren Sie das Nachholscanfeature.</span><span class="sxs-lookup"><span data-stu-id="8e502-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="8e502-157">Definieren Sie die Anzahl der Scans, die übersprungen werden können, bevor eine Nachholscan durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8e502-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="8e502-158">Dieses Feature kann sowohl für vollständige als auch für schnelle Scans aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8e502-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="8e502-159">Aktivieren und Konfigurieren des Nachholscanfeatures mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8e502-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="8e502-160">Stellen Sie sicher, dass Sie mindestens einen geplanten Scan eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="8e502-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="8e502-161">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8e502-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8e502-162">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8e502-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8e502-163">Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**</span><span class="sxs-lookup"><span data-stu-id="8e502-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8e502-164">Erweitern Sie die Struktur, **Windows komponenten > Microsoft Defender Antivirus > überprüfen** und die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8e502-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="8e502-165">Wenn Sie geplante Schnellscans eingerichtet haben, doppelklicken Sie auf die Einstellung Nachhol-Schnellscan aktivieren, und legen Sie die Option auf **Aktiviert fest.** </span><span class="sxs-lookup"><span data-stu-id="8e502-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="8e502-166">Wenn Sie geplante vollständige Scans eingerichtet haben, doppelklicken Sie auf die Einstellung Vollständige Nachholvorgang aktivieren, und legen Sie die Option auf **Aktiviert fest.** </span><span class="sxs-lookup"><span data-stu-id="8e502-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8e502-167">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-167">Click **OK**.</span></span>
    3. <span data-ttu-id="8e502-168">Doppelklicken Sie auf Die Anzahl **der** Tage definieren, nach denen eine Nachholscan erzwungen wird, und legen Sie die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="8e502-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="8e502-169">Geben Sie die Anzahl der Scans ein, die verpasst werden können, bevor eine Überprüfung automatisch ausgeführt wird, wenn sich der Benutzer das nächste Mal am PC anmeldet.</span><span class="sxs-lookup"><span data-stu-id="8e502-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="8e502-170">Der ausgeführte Scantyp wird durch das Angeben des Scantyps bestimmt, der für einen geplanten Scan verwendet werden soll **(siehe** Thema [Schedule scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8e502-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="8e502-171">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8e502-172">Der Titel der Gruppenrichtlinieneinstellung bezieht sich auf die Anzahl der Tage.</span><span class="sxs-lookup"><span data-stu-id="8e502-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="8e502-173">Die Einstellung wird jedoch auf die Anzahl der Scans (keine Tage) angewendet, bevor die Nachholscan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8e502-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="8e502-174">Konfigurieren von Nachholscans mithilfe von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8e502-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="8e502-175">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8e502-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="8e502-176">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus und [Defender-Cmdlets](/powershell/module/defender/) finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8e502-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="8e502-177">Konfigurieren von Nachholscans mithilfe Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="8e502-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="8e502-178">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8e502-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="8e502-179">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="8e502-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8e502-180">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="8e502-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="8e502-181">Konfigurieren von Nachholscans mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e502-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="8e502-182">Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)</span><span class="sxs-lookup"><span data-stu-id="8e502-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8e502-183">Wechseln Sie zum **Abschnitt Geplante Scans,** und erzwingen Sie eine Überprüfung des ausgewählten Scantyps, wenn **der Clientcomputer offline ist...** zu **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8e502-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="8e502-184">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e502-184">Click **OK**.</span></span>

4.  <span data-ttu-id="8e502-185">[Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="8e502-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="8e502-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8e502-186">Related articles</span></span>

- [<span data-ttu-id="8e502-187">Bereitstellen Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8e502-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e502-188">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines</span><span class="sxs-lookup"><span data-stu-id="8e502-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e502-189">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="8e502-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e502-190">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="8e502-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e502-191">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="8e502-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8e502-192">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8e502-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)