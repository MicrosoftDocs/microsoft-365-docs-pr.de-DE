---
title: Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender Antivirus
description: Aktivieren Sie das Antivirusfeature für potenziell unerwünschte Anwendungen (PUA), um unerwünschte Software wie z. B. Adware zu blockieren.
keywords: pua, enable, unerwünschte Software, unerwünschte Apps, Adware, Browsersymbolleiste, erkennen, blockieren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904010"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="f53b8-104">Erkennen und Blockieren potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f53b8-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f53b8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f53b8-105">**Applies to:**</span></span>

- [<span data-ttu-id="f53b8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f53b8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="f53b8-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f53b8-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="f53b8-108">Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die dazu führen kann, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigen oder im schlechtesten Fall andere Software installieren kann, die unerwartet oder unerwünscht sein kann.</span><span class="sxs-lookup"><span data-stu-id="f53b8-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="f53b8-109">PUA wird nicht als Virus, Schadsoftware oder eine andere Art von Bedrohung betrachtet, kann jedoch Aktionen für Endpunkte ausführen, die sich negativ auf die Leistung oder Verwendung von Endpunkten auswirken.</span><span class="sxs-lookup"><span data-stu-id="f53b8-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="f53b8-110">Der Begriff *PUA* kann sich auch auf eine Anwendung beziehen, die aufgrund bestimmter Arten von unerwünschtem Verhalten einen schlechten Ruf hat, wie von Microsoft Defender for Endpoint bewertet.</span><span class="sxs-lookup"><span data-stu-id="f53b8-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="f53b8-111">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="f53b8-111">Here are some examples:</span></span>

- <span data-ttu-id="f53b8-112">**Werbesoftware,** die Werbung oder Werbeaktionen anzeigt, einschließlich Software, die Werbung auf Webseiten einfüge.</span><span class="sxs-lookup"><span data-stu-id="f53b8-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="f53b8-113">**Bündelungssoftware,** die die Installation anderer Software anbietet, die nicht digital von derselben Entität signiert ist.</span><span class="sxs-lookup"><span data-stu-id="f53b8-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="f53b8-114">Außerdem software that offers to install other software that qualifies as PUA.</span><span class="sxs-lookup"><span data-stu-id="f53b8-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="f53b8-115">**Software zum** Ausweichen, die aktiv versucht, der Erkennung durch Sicherheitsprodukte zu entweichen, einschließlich Software, die sich bei Vorhandensein von Sicherheitsprodukten anders verhält.</span><span class="sxs-lookup"><span data-stu-id="f53b8-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="f53b8-116">Weitere Beispiele und eine Beschreibung der Kriterien, die wir zum Beschriften von Anwendungen für besondere Aufmerksamkeit von Sicherheitsfeatures verwenden, finden Sie unter [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="f53b8-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="f53b8-117">Potenziell unerwünschte Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit tatsächlicher Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren oder IT-Ressourcen beim Bereinigen zu verschwenden.</span><span class="sxs-lookup"><span data-stu-id="f53b8-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="f53b8-118">Der PUA-Schutz wird unter Windows 10, Windows Server 2019 und Windows Server 2016 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f53b8-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="f53b8-119">In Windows 10 (Version 2004 und höher) blockiert Microsoft Defender Antivirus Standardmäßig Apps, die als PUA for Enterprise (E5)-Geräte gelten.</span><span class="sxs-lookup"><span data-stu-id="f53b8-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="f53b8-120">Aktuelle Version von Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f53b8-120">Microsoft Edge</span></span>

<span data-ttu-id="f53b8-121">Das [neue Auf Chromium-basierte Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)blockiert potenziell unerwünschte Anwendungsdownloads und zugeordnete Ressourcen-URLs.</span><span class="sxs-lookup"><span data-stu-id="f53b8-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="f53b8-122">Dieses Feature wird über [Microsoft Defender SmartScreen bereitgestellt.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="f53b8-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="f53b8-123">Aktivieren des PUA-Schutzes in Chromium-basiertem Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f53b8-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="f53b8-124">Obwohl der potenziell unerwünschte Anwendungsschutz in Microsoft Edge (Chromium-basiert, Version 80.0.361.50) standardmäßig deaktiviert ist, kann er problemlos über den Browser aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f53b8-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="f53b8-125">Wählen Sie im Edgebrowser die Ellipsen aus, und wählen Sie dann **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="f53b8-126">Wählen **Sie Datenschutz, Suche und Dienste aus.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="f53b8-127">Aktivieren Sie **im Abschnitt Sicherheit** potenziell unerwünschte Apps **blockieren.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="f53b8-128">Wenn Sie Microsoft Edge (chromium-basiert) ausführen, können Sie das Feature zum Blockieren von URLs des PUA-Schutzes sicher erkunden, indem Sie es auf einer unserer [Microsoft Defender SmartScreen-Demoseiten testen.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="f53b8-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="f53b8-129">Blockieren von URLs mit Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="f53b8-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="f53b8-130">In Chromium-basiertem Edge mit aktiviertem PUA-Schutz schützt Microsoft Defender SmartScreen Sie vor PUA-zugeordneten URLs.</span><span class="sxs-lookup"><span data-stu-id="f53b8-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="f53b8-131">Sicherheitsadministratoren können [konfigurieren,](/DeployEdge/configure-microsoft-edge) wie Microsoft Edge und Microsoft Defender SmartScreen zusammenarbeiten, um Benutzergruppen vor PUA-zugeordneten URLs zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="f53b8-132">Es sind mehrere [Gruppenrichtlinieneinstellungen explizit](/DeployEdge/microsoft-edge-policies#smartscreen-settings) für Microsoft Defender SmartScreen verfügbar, einschließlich einer für das Blockieren [von PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="f53b8-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="f53b8-133">Darüber hinaus können Administratoren [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) als Ganzes konfigurieren, indem Sie Gruppenrichtlinieneinstellungen verwenden, um Microsoft Defender SmartScreen ein- oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="f53b8-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="f53b8-134">Obwohl Microsoft Defender for Endpoint über eine eigene Blockliste basierend auf einem von Microsoft verwalteten Datensatz verfügt, können Sie diese Liste basierend auf Ihrer eigenen Bedrohungsintelligenz anpassen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="f53b8-135">Wenn Sie [Indikatoren im](manage-indicators.md) Microsoft Defender for Endpoint-Portal erstellen und verwalten, respektiert Microsoft Defender SmartScreen die neuen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="f53b8-136">Microsoft Defender Antivirus- und PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="f53b8-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="f53b8-137">Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Microsoft Defender Antivirus kann PUA auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="f53b8-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="f53b8-138">Dieses Feature ist unter Windows 10, Windows Server 2019 und Windows Server 2016 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f53b8-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="f53b8-139">Microsoft Defender Antivirus blockiert erkannte PUA-Dateien und alle Versuche, sie herunterzuladen, zu verschieben, ausführen oder zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f53b8-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="f53b8-140">Blockierte PUA-Dateien werden dann in quarantäne verschoben.</span><span class="sxs-lookup"><span data-stu-id="f53b8-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="f53b8-141">Wenn eine PUA-Datei auf einem Endpunkt erkannt wird, sendet Microsoft Defender Antivirus eine Benachrichtigung[an](configure-notifications-microsoft-defender-antivirus.md)den Benutzer ( es sei denn, Benachrichtigungen wurden deaktiviert ) im gleichen Format wie andere Bedrohungserkennungen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="f53b8-142">Die Benachrichtigung ist mit vorkonfaced, `PUA:` um den Inhalt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f53b8-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="f53b8-143">Die Benachrichtigung wird in der üblichen [Quarantäneliste in der Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f53b8-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="f53b8-144">Konfigurieren des PUA-Schutzes in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f53b8-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f53b8-145">Sie können den PUA-Schutz mit [Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Gruppenrichtlinien](/azure/active-directory-domain-services/manage-group-policy)oder [über PowerShell-Cmdlets aktivieren.](/powershell/module/defender/?preserve-view=true&view=win10-ps)</span><span class="sxs-lookup"><span data-stu-id="f53b8-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="f53b8-146">Sie können den PUA-Schutz auch im Überwachungsmodus verwenden, um potenziell unerwünschte Anwendungen zu erkennen, ohne sie zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f53b8-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="f53b8-147">Die Erkennungen werden im Windows-Ereignisprotokoll erfasst.</span><span class="sxs-lookup"><span data-stu-id="f53b8-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="f53b8-148">Besuchen Sie die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com/Page/UrlRep) um zu bestätigen, dass das Feature funktioniert, und sehen Sie es in Aktion.</span><span class="sxs-lookup"><span data-stu-id="f53b8-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="f53b8-149">PuA-Schutz im Überwachungsmodus ist nützlich, wenn Ihr Unternehmen eine interne Überprüfung der Softwaresicherheit durchführt und Sie falsch positive Ergebnisse vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="f53b8-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="f53b8-150">Konfigurieren des PUA-Schutzes mithilfe von Intune</span><span class="sxs-lookup"><span data-stu-id="f53b8-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="f53b8-151">Weitere Informationen finden Sie [unter Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender Antivirus device restriction settings for Windows [10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="f53b8-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="f53b8-152">Konfigurieren des PUA-Schutzes mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f53b8-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="f53b8-153">Der PUA-Schutz ist standardmäßig im Microsoft Endpoint Manager (Current Branch) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f53b8-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f53b8-154">Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (Current Branch) finden Sie unter How [to create and deploy anmalware policies: Scheduled scans settings.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)</span><span class="sxs-lookup"><span data-stu-id="f53b8-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f53b8-155">Informationen zu System Center 2012 Configuration Manager finden Sie unter Bereitstellen potenziell unerwünschter Anwendungsschutzrichtlinien [für Endpunktschutz in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="f53b8-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="f53b8-156">Von Microsoft Defender Antivirus blockierte PUA-Ereignisse werden in der Windows-Ereignisanzeige und nicht in Microsoft Endpoint Configuration Manager gemeldet.</span><span class="sxs-lookup"><span data-stu-id="f53b8-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="f53b8-157">Konfigurieren des PUA-Schutzes mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f53b8-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="f53b8-158">Herunterladen und Installieren [von administrativen Vorlagen (ADMX) für Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="f53b8-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="f53b8-159">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="f53b8-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="f53b8-160">Wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="f53b8-161">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="f53b8-162">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="f53b8-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="f53b8-163">Doppelklicken Sie **auf Erkennung für potenziell unerwünschte Anwendungen konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="f53b8-164">Wählen **Sie Aktiviert** aus, um den PUA-Schutz zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f53b8-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="f53b8-165">Wählen **Sie unter Optionen** die Option **Blockieren** aus, um potenziell unerwünschte Anwendungen zu blockieren, oder wählen Sie Überwachungsmodus aus, um zu testen, wie die Einstellung in Ihrer Umgebung funktioniert. </span><span class="sxs-lookup"><span data-stu-id="f53b8-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="f53b8-166">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f53b8-166">Select **OK**.</span></span>

9. <span data-ttu-id="f53b8-167">Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f53b8-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="f53b8-168">Konfigurieren des PUA-Schutzes mithilfe von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f53b8-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="f53b8-169">So aktivieren Sie den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="f53b8-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="f53b8-170">Festlegen des Werts für dieses Cmdlet, um das Feature zu `Enabled` aktivieren, wenn es deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="f53b8-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="f53b8-171">So legen Sie den PUA-Schutz auf den Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="f53b8-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="f53b8-172">Die `AuditMode` Einstellung erkennt PUAs, ohne sie zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f53b8-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="f53b8-173">So deaktivieren Sie den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="f53b8-173">To disable PUA protection</span></span>

<span data-ttu-id="f53b8-174">Es wird empfohlen, den PUA-Schutz aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="f53b8-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="f53b8-175">Sie können sie jedoch mit dem folgenden Cmdlet deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f53b8-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="f53b8-176">Wenn Sie den Wert für dieses Cmdlet festlegen, wird das Feature `Disabled` deaktiviert, wenn es aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="f53b8-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="f53b8-177">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="f53b8-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="f53b8-178">Anzeigen von PUA-Ereignissen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f53b8-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="f53b8-179">PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet, jedoch nicht im Microsoft Endpoint Manager oder in Intune.</span><span class="sxs-lookup"><span data-stu-id="f53b8-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="f53b8-180">Sie können das Cmdlet auch zum Anzeigen von `Get-MpThreat` Bedrohungen verwenden, die von Microsoft Defender Antivirus behandelt wurden.</span><span class="sxs-lookup"><span data-stu-id="f53b8-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="f53b8-181">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f53b8-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="f53b8-182">Erhalten von E-Mail-Benachrichtigungen zu PUA-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="f53b8-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="f53b8-183">Sie können E-Mail-Benachrichtigungen aktivieren, um E-Mails zu PUA-Erkennungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="f53b8-184">Weitere Informationen zum Anzeigen von Microsoft Defender Antivirus-Ereignissen finden Sie unter [Troubleshoot event IDs.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f53b8-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="f53b8-185">PUA-Ereignisse werden unter ereignis-ID **1160 aufgezeichnet.**</span><span class="sxs-lookup"><span data-stu-id="f53b8-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="f53b8-186">Anzeigen von PUA-Ereignissen mithilfe der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="f53b8-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="f53b8-187">Wenn Sie [Microsoft Defender for Endpoint verwenden,](microsoft-defender-endpoint.md)können Sie eine erweiterte Suchabfrage zum Anzeigen von PUA-Ereignissen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f53b8-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="f53b8-188">Hier ist eine Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="f53b8-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="f53b8-189">Weitere Informationen zur erweiterten Suche finden Sie unter Proaktive Suche [nach Bedrohungen mit erweiterter Suche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f53b8-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="f53b8-190">Ausschließen von Dateien aus dem PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="f53b8-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="f53b8-191">Manchmal wird eine Datei fälschlicherweise durch den PUA-Schutz blockiert, oder ein Feature einer PUA ist erforderlich, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f53b8-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="f53b8-192">In diesen Fällen kann einer Ausschlussliste eine Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f53b8-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="f53b8-193">Weitere Informationen finden Sie unter [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="f53b8-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f53b8-194">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="f53b8-194">See also</span></span>

- [<span data-ttu-id="f53b8-195">Schutzlösungen der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="f53b8-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f53b8-196">Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="f53b8-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)