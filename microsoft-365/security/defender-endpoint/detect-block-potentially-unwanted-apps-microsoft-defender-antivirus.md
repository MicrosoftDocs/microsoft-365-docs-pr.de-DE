---
title: Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender Antivirus
description: Aktivieren Sie das Antivirus-Feature für potentiell unerwünschte Anwendungen (PUA), um unerwünschte Software wie z. B. Adware zu blockieren.
keywords: PUA, aktivieren, unerwünschte Software, unerwünschte Apps, Adware, Browser-Symbolleiste, erkennen, blockieren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275240"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="a6a87-104">Erkennen und Blockieren potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a6a87-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6a87-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a6a87-105">**Applies to:**</span></span>

- [<span data-ttu-id="a6a87-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a6a87-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="a6a87-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6a87-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="a6a87-108">Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die Ihren Computer verlangsamen, unerwartete Werbung anzeigen oder schlimmstenfalls andere Software installieren kann, die unerwartet oder unerwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="a6a87-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="a6a87-109">PUA werden nicht als Virus, Schadsoftware oder eine andere Art von Bedrohung angesehen, aber sie können Aktionen auf Endgeräten durchführen, welche die Leistung oder Nutzung von Endgeräten beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="a6a87-110">Der Ausdruck *PUA* kann sich auch auf eine Anwendung beziehen, die aufgrund bestimmter unerwünschten Verhaltensweisen einen schlechten Ruf hat (gemäß Bewertung von Microsoft Defender für Endpunkt).</span><span class="sxs-lookup"><span data-stu-id="a6a87-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="a6a87-111">Hier sind einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a6a87-111">Here are some examples:</span></span>

- <span data-ttu-id="a6a87-112">**Werbe-Software**, welche Werbung oder Aktionen anzeigt, einschließlich Software, die Werbung in Webseiten einfügt.</span><span class="sxs-lookup"><span data-stu-id="a6a87-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="a6a87-113">**Bündelung-Software**, die anbietet, andere Software zu installieren, die nicht von der gleichen Entität digital signiert ist.</span><span class="sxs-lookup"><span data-stu-id="a6a87-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="a6a87-114">Ebenfalls Software, die anbietet, andere Software zu installieren, die als PUA eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="a6a87-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="a6a87-115">**Umgehungssoftware**, die aktiv versucht, sich der Erkennung durch Sicherheitsprodukte zu entziehen, einschließlich Software, die sich bei Vorhandensein von Sicherheitsprodukten anders verhält.</span><span class="sxs-lookup"><span data-stu-id="a6a87-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="a6a87-116">Weitere Beispiele und eine Diskussion der Kriterien, die wir verwenden, um Anwendungen für die besondere Aufmerksamkeit von Sicherheitsfeatures zu kennzeichnen, finden Sie unter [Wie Microsoft Schadsoftware und potenziell unerwünschte Anwendungen identifiziert](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="a6a87-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="a6a87-117">Potenziell unerwünschte Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk durch echte Schadsoftware infiziert wird, gestalten die Identifizierung von Schadsoftware-Infektionen schwieriger oder verschwenden IT-Ressourcen für deren Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="a6a87-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="a6a87-118">PUA-Schutz wird in Windows 10, Windows Server 2019 und Windows Server 2016 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a6a87-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="a6a87-119">In Windows 10 (Version 2004 oder höher) blockiert Microsoft Defender Antivirus standardmäßig Apps, die für Geräte von Unternehmen (E5) als PUA angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="a6a87-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="a6a87-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6a87-120">Microsoft Edge</span></span>

<span data-ttu-id="a6a87-121">Der [neue Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), der Chromium-basiert ist, blockiert das Herunterladen von potenziell unerwünschten Anwendungen und zugehöriger Ressourcen-URLs.</span><span class="sxs-lookup"><span data-stu-id="a6a87-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="a6a87-122">Dieses Feature wird über [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="a6a87-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="a6a87-123">PUA-Schutz im Chromium-basierten Microsoft Edge aktivieren</span><span class="sxs-lookup"><span data-stu-id="a6a87-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="a6a87-124">Obwohl der Schutz vor potentiell unerwünschten Anwendungen in Microsoft Edge (Chromium-basiert, Version 80.0.361.50) standardmäßig deaktiviert ist, kann er einfach aus dem Browser heraus aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a6a87-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="a6a87-125">Wählen Sie in Ihrem Microsoft Edge-Browser die Ellipsen aus und dann **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a6a87-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="a6a87-126">Wählen Sie **Datenschutz, Suche und Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="a6a87-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="a6a87-127">Aktivieren Sie unter dem Abschnitt **Sicherheit** die Option **Blockieren potenziell unerwünschter Apps**.</span><span class="sxs-lookup"><span data-stu-id="a6a87-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="a6a87-128">Wenn Sie Microsoft Edge (Chromium-basiert) verwenden, können Sie die URL-Blockierungsfunktion des PUA-Schutzes sicher erkunden, indem Sie diese auf einer unserer [Microsoft Defender SmartScreen-Demoseiten ausprobieren](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="a6a87-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="a6a87-129">URLs blockieren mit Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="a6a87-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="a6a87-130">Im Chromium-basierten Microsoft Edge mit aktiviertem PUA-Schutz schützt Microsoft Defender SmartScreen Sie vor mit PUA assoziierten URLs.</span><span class="sxs-lookup"><span data-stu-id="a6a87-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="a6a87-131">Sicherheitsadministratoren können [konfigurieren](/DeployEdge/configure-microsoft-edge), wie Microsoft Edge und Microsoft Defender SmartScreen zusammenarbeiten, um Gruppen von Benutzern vor mit PUA assoziierten URLs zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="a6a87-132">Für Microsoft Defender SmartScreen sind mehrere [Gruppenrichtlinieneinstellungen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explizit verfügbar, einschließlich [eine zum Blockieren von PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="a6a87-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="a6a87-133">Zusätzlich können Administratoren [Microsoft Defender SmartScreen als Ganzes konfigurieren](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen), indem Sie Gruppenrichtlinieneinstellungen verwenden, um Microsoft Defender SmartScreen zu aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="a6a87-134">Obwohl Microsoft Defender für Endpunkt über eine eigene Sperrliste verfügt, die auf einem von Microsoft verwalteten Dataset basiert, können Sie diese Liste basierend auf Ihren eigenen Bedrohungsinformationen anpassen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="a6a87-135">Wenn Sie im Microsoft Defender für Endpunkt-Portal [Indikatoren erstellen und verwalten](manage-indicators.md), berücksichtigt Microsoft Defender SmartScreen die neuen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="a6a87-136">Microsoft Defender Antivirus und PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="a6a87-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="a6a87-137">Die Schutzfunktion gegen potentiell unerwünschte Anwendungen (PUA) in Microsoft Defender Antivirus kann PUA auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a87-138">Dieses Feature ist verfügbar in Windows 10, Windows Server 2019 und Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a6a87-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="a6a87-139">Microsoft Defender Antivirus blockiert erkannte PUA-Dateien und jeden Versuch, diese herunterzuladen, zu verschieben, auszuführen oder zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="a6a87-140">Blockierte PUA-Dateien werden dann unter Quarantäne gestellt.</span><span class="sxs-lookup"><span data-stu-id="a6a87-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="a6a87-141">Wenn eine PUA-Datei auf einem Endpunkt erkannt wird, sendet Microsoft Defender Antivirus eine Benachrichtigung an den Benutzer ([außer wenn Benachrichtigungen deaktiviert wurden](configure-notifications-microsoft-defender-antivirus.md)), im gleichen Format wir für andere Bedrohungserkennungen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="a6a87-142">Der Benachrichtigung wird `PUA:` vorangestellt, um ihren Inhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="a6a87-143">Die Benachrichtigung erscheint in der üblichen [Quarantäneliste innerhalb der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a6a87-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="a6a87-144">Konfigurieren des PUA-Schutzes in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a6a87-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a6a87-145">Sie können den PUA-Schutz mit [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), einer [Gruppenrichtlinie](/azure/active-directory-domain-services/manage-group-policy) oder mittels [PowerShell-Cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="a6a87-146">Sie können den PUA-Schutz ebenfalls im Überwachungsmodus verwenden, um potenziell unerwünschte Anwendungen zu erkennen, ohne sie zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="a6a87-147">Die Erkennungen werden im Windows-Ereignisprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6a87-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="a6a87-148">Besuchen Sie die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep), um zu bestätigen, dass das Feature funktioniert, und es bei der Arbeit zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="a6a87-149">Der PUA-Schutz im Überwachungsmodus ist nützlich, wenn Ihr Unternehmen eine interne Software-Sicherheitsüberprüfung durchführt und Sie Fehlalarme vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="a6a87-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="a6a87-150">Verwenden von Intune zum Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="a6a87-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="a6a87-151">Für mehr Details lesen Sie [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure) und [Einstellungen für Microsoft Defender Antivirus-Geräteeinschränkungen für Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="a6a87-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="a6a87-152">Verwenden des Configuration Manager zum Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="a6a87-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="a6a87-153">Der PUA-Schutz ist standardmäßig im Microsoft Endpoint Manager (Aktueller Branch) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6a87-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a6a87-154">Für Details zur Konfiguration des Microsoft Endpoint Manager (Aktueller Branch) lesen Sie [Erstellen und Bereitstellen von Antimalware-Richtlinien: Einstellungen für geplante Scans](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).</span><span class="sxs-lookup"><span data-stu-id="a6a87-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a6a87-155">Für den Configuration Manager des System Center 2012 lesen Sie [Bereitstellen einer Schutzrichtlinie für potenziell unerwünschte Anwendungen für den Endpunktschutz im Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="a6a87-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="a6a87-156">Von Microsoft Defender Antivirus blockierte PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet und nicht im Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a6a87-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="a6a87-157">Verwenden einer Gruppenrichtlinie zum Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="a6a87-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="a6a87-158">Herunterladen und Installieren der [Administrativen Vorlagen (.admx) für Windows 10, Oktober 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="a6a87-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="a6a87-159">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="a6a87-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="a6a87-160">Wählen Sie das Gruppenrichtlinien-Objekt aus, das Sie konfigurieren wollen, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="a6a87-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="a6a87-161">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="a6a87-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="a6a87-162">Erweitern Sie die Struktur bis zu **Windows-Komponenten > \*\*\*\*Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="a6a87-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="a6a87-163">Doppelklicken Sie auf **Erkennung für potentiell unerwünschte Anwendungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="a6a87-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="a6a87-164">Wählen Sie **Aktiviert** aus, um den PUA-Schutz zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="a6a87-165">Wählen Sie unter **Optionen** die Option **Blockieren** aus, um potentiell unerwünschte Anwendungen zu blockieren, oder wählen Sie **Überwachungsmodus** aus, um zu testen, wie sich die Einstellung in Ihrer Umgebung auswirken.</span><span class="sxs-lookup"><span data-stu-id="a6a87-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="a6a87-166">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a6a87-166">Select **OK**.</span></span>

9. <span data-ttu-id="a6a87-167">Stellen Sie Ihr Gruppenrichtlinien-Objekt bereit, so wie Sie dies normalerweise tun.</span><span class="sxs-lookup"><span data-stu-id="a6a87-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="a6a87-168">Verwenden von PowerShell-Cmdlets zum Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="a6a87-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="a6a87-169">So aktivieren Sie den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="a6a87-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="a6a87-170">Wenn der Wert für dieses Cmdlet auf `Enabled` eingestellt wird, aktiviert dies das Feature, wenn es deaktiviert war.</span><span class="sxs-lookup"><span data-stu-id="a6a87-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="a6a87-171">So stellen Sie den PUA-Schutz auf den Überwachungsmodus ein</span><span class="sxs-lookup"><span data-stu-id="a6a87-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="a6a87-172">Die Einstellung `AuditMode` erkennt PUAs, ohne sie zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="a6a87-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="a6a87-173">So deaktivieren Sie den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="a6a87-173">To disable PUA protection</span></span>

<span data-ttu-id="a6a87-174">Wir empfehlen, den PUA-Schutz aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="a6a87-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="a6a87-175">Sie können ihn jedoch mit dem folgenden Cmdlet deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a6a87-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="a6a87-176">Wenn der Wert für dieses Cmdlet auf `Disabled` eingestellt wird, deaktiviert dies das Feature, wenn es aktiviert war.</span><span class="sxs-lookup"><span data-stu-id="a6a87-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="a6a87-177">Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="a6a87-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="a6a87-178">PUA-Ereignisse mittels PowerShell anzeigen</span><span class="sxs-lookup"><span data-stu-id="a6a87-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="a6a87-179">PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet, aber nicht in Microsoft Endpoint Manager oder Intune.</span><span class="sxs-lookup"><span data-stu-id="a6a87-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="a6a87-180">Sie können auch das `Get-MpThreat`-Cmdlet verwenden, um Bedrohungen anzuzeigen, die Microsoft Defender Antivirus behandelt hat.</span><span class="sxs-lookup"><span data-stu-id="a6a87-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="a6a87-181">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6a87-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="a6a87-182">E-Mail-Benachrichtigungen über PUA-Erkennungen erhalten</span><span class="sxs-lookup"><span data-stu-id="a6a87-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="a6a87-183">Sie können E-Mail-Benachrichtigungen aktivieren, um E-Mails über PUA-Erkennungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a6a87-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="a6a87-184">Weitere Details zum Anzeigen von Microsoft Defender Antivirus-Ereignissen finden Sie unter [Problembehandlung von Ereignis-IDs](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a6a87-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="a6a87-185">PUA-Ereignisse werden mit der Ereignis-ID **1160** aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6a87-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="a6a87-186">PUA-Ereignisse mittels der erweiterte Bedrohungssuche anzeigen</span><span class="sxs-lookup"><span data-stu-id="a6a87-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="a6a87-187">Wenn Sie [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) verwenden, können Sie eine Abfrage zur erweiterten Bedrohungssuche verwenden, um PUA-Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="a6a87-188">Hier ist eine Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="a6a87-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="a6a87-189">Weiter Informationen über die erweiterte Bedrohungssuche finden Sie unter [Proaktive Suche nach Bedrohungen mit der erweiterten Bedrohungssuche](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a6a87-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="a6a87-190">Dateien vom PUA-Schutz ausschließen</span><span class="sxs-lookup"><span data-stu-id="a6a87-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="a6a87-191">Manchmal wird eine Datei fälschlicherweise vom PUA-Schutz blockiert, oder ein Feature einer PUA wird benötigt, um eine Aufgabe zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="a6a87-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="a6a87-192">In diesen Fällen kann eine Datei zur Ausschlussliste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a6a87-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="a6a87-193">Weitere Informationen finden Sie unter [Konfigurieren und Validieren von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherorten](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a6a87-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6a87-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6a87-194">See also</span></span>

- [<span data-ttu-id="a6a87-195">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="a6a87-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a6a87-196">Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeit-Schutz</span><span class="sxs-lookup"><span data-stu-id="a6a87-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)