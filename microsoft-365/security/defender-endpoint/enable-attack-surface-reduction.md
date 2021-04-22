---
title: Aktivieren der Regeln zur Verringerung der Angriffsfläche
description: Aktivieren Sie Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR), um Ihre Geräte vor Angriffen zu schützen, die Makros, Skripts und allgemeine Einspritztechniken verwenden.
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939242"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="3f613-104">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3f613-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f613-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3f613-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f613-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3f613-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3f613-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f613-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3f613-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="3f613-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3f613-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3f613-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="3f613-110">[Attack Surface Reduction Rules](attack-surface-reduction.md) (ASR-Regeln) helfen, Aktionen zu verhindern, die von Schadsoftware häufig missbraucht werden, um Geräte und Netzwerke zu gefährdeten.</span><span class="sxs-lookup"><span data-stu-id="3f613-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="3f613-111">Sie können ASR-Regeln für Geräte mit einer der folgenden Editionen und Versionen von Windows festlegen:</span><span class="sxs-lookup"><span data-stu-id="3f613-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="3f613-112">Windows 10 Pro, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f613-113">Windows 10 Enterprise, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f613-114">Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3f613-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f613-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f613-116">**Anforderungen** Sie können Regeln zur Reduzierung der Angriffsfläche für Geräte festlegen, auf der eine der folgenden Editionen und Versionen von Windows ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="3f613-116">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="3f613-117">Windows 10 Pro, Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-117">Windows 10 Pro, version 1709 or later</span></span>
- <span data-ttu-id="3f613-118">Windows 10 Enterprise, Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-118">Windows 10 Enterprise, version 1709 or later</span></span>
- <span data-ttu-id="3f613-119">Windows Server, Version 1803 (Halbjährskanal) oder höher</span><span class="sxs-lookup"><span data-stu-id="3f613-119">Windows Server, version 1803 (Semi-Annual Channel) or later</span></span>
- <span data-ttu-id="3f613-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f613-120">Windows Server 2019</span></span>

<span data-ttu-id="3f613-121">Obwohl Regeln zur Reduzierung der Angriffsfläche keine Windows E5-Lizenz erfordern, erhalten Sie bei Windows E5 erweiterte Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="3f613-121">Although attack surface reduction rules don't require a Windows E5 license, if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="3f613-122">Diese Funktionen, die nur in Windows E5 verfügbar sind, umfassen Überwachung, Analyse und Workflows, die in Defender for Endpoint verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="3f613-122">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="3f613-123">Diese erweiterten Funktionen sind nicht mit einer Windows Professional- oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige- und Microsoft Defender Antivirus-Protokolle verwenden, um Ihre Ereignisse der Regel zur Reduzierung der Angriffsfläche zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3f613-123">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="3f613-124">Jede ASR-Regel enthält eine von vier Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3f613-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="3f613-125">**Nicht konfiguriert:** Deaktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="3f613-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="3f613-126">**Block**: Aktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="3f613-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="3f613-127">**Überwachung**: Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre</span><span class="sxs-lookup"><span data-stu-id="3f613-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="3f613-128">**Warn**: Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="3f613-128">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f613-129">Derzeit wird der Warnmodus für drei ASR-Regeln nicht unterstützt, wenn Sie ASR-Regeln in Microsoft Endpoint Manager (MEM) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3f613-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="3f613-130">Weitere Informationen finden Sie unter [Fälle, in denen der Warnmodus nicht unterstützt wird.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="3f613-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="3f613-131">Es wird dringend empfohlen, dass Sie ASR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen zu nutzen, die in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3f613-131">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="3f613-132">Für andere Lizenzen wie Windows Professional oder E3, die keinen Zugriff auf erweiterte Überwachungs- und Berichtsfunktionen haben, können Sie jedoch eigene Überwachungs- und Berichterstellungstools neben den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignis forwarding).</span><span class="sxs-lookup"><span data-stu-id="3f613-132">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="3f613-133">Weitere Informationen zur Windows-Lizenzierung finden Sie unter [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im Handbuch zur [Volumenlizenzierung für Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="3f613-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="3f613-134">Sie können Regeln zur Reduzierung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3f613-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="3f613-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3f613-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="3f613-136">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="3f613-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="3f613-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f613-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="3f613-138">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3f613-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="3f613-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f613-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="3f613-140">Die Unternehmensverwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3f613-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="3f613-141">Die Unternehmensverwaltung überschreibt beim Start alle in Konflikt enden Gruppenrichtlinien oder PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f613-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="3f613-142">Ausschließen von Dateien und Ordnern aus ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="3f613-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="3f613-143">Sie können ausschließen, dass Dateien und Ordner von den meisten Regeln zur Reduzierung der Angriffsfläche ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="3f613-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="3f613-144">Dies bedeutet, dass selbst wenn eine ASR-Regel bestimmt, dass die Datei oder der Ordner schädliches Verhalten enthält, die Ausführung der Datei nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="3f613-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="3f613-145">Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infizieren.</span><span class="sxs-lookup"><span data-stu-id="3f613-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="3f613-146">Sie können #A0 auch von der Auslösung basierend auf Zertifikat- und Dateihashes ausschließen, indem Sie bestimmte Defender for Endpoint-Datei- und Zertifikatindikatoren zulassen.</span><span class="sxs-lookup"><span data-stu-id="3f613-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="3f613-147">(Siehe [Verwalten von Indikatoren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="3f613-147">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f613-148">Das Ausschließen von Dateien oder Ordnern kann den von den ASR-Regeln bereitgestellten Schutz erheblich verringern.</span><span class="sxs-lookup"><span data-stu-id="3f613-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="3f613-149">Ausgeschlossene Dateien können ausgeführt werden, und es werden keine Berichte oder Ereignisse aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3f613-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="3f613-150">Wenn ASR-Regeln Dateien erkennen, die Ihrer Meinung nach nicht erkannt werden sollten, sollten Sie zuerst den Überwachungsmodus verwenden, um die [Regel zu testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="3f613-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="3f613-151">Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), Sie können jedoch nicht angeben, für welche Regeln die Ausschlüsse gelten.</span><span class="sxs-lookup"><span data-stu-id="3f613-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="3f613-152">Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f613-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="3f613-153">Wenn Sie beispielsweise einen Ausschluss für einen bereits ausgeführten Updatedienst hinzufügen, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f613-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="3f613-154">ASR-Regeln unterstützen Umgebungsvariablen und Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="3f613-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="3f613-155">Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="3f613-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="3f613-156">Die folgenden Verfahren zum Aktivieren von ASR-Regeln enthalten Anweisungen zum Ausschließen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="3f613-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="3f613-157">Intune</span><span class="sxs-lookup"><span data-stu-id="3f613-157">Intune</span></span>

1. <span data-ttu-id="3f613-158">Wählen **Sie Gerätekonfigurationsprofile**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="3f613-159">Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues.</span><span class="sxs-lookup"><span data-stu-id="3f613-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="3f613-160">Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen aus,** und geben Sie Informationen für dieses Profil ein.</span><span class="sxs-lookup"><span data-stu-id="3f613-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="3f613-161">Wählen **Sie für Profiltyp** **Endpunktschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="3f613-162">Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** und dann **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="3f613-163">Wählen Sie **im Bereich** Endpunktschutz die option Windows Defender **Exploit Guard** aus, und wählen Sie dann Attack Surface **Reduction aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="3f613-164">Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.</span><span class="sxs-lookup"><span data-stu-id="3f613-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="3f613-165">Geben **Sie unter Attack Surface Reduction exceptions** einzelne Dateien und Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="3f613-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="3f613-166">Sie können auch **Importieren auswählen,** um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von DEN REGELN ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3f613-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="3f613-167">Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:</span><span class="sxs-lookup"><span data-stu-id="3f613-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="3f613-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="3f613-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="3f613-169">Wählen **Sie in** den drei Konfigurationsfenstern OK aus.</span><span class="sxs-lookup"><span data-stu-id="3f613-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="3f613-170">Wählen Sie dann **Erstellen** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **Speichern,** wenn Sie eine vorhandene Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3f613-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="3f613-171">MDM</span><span class="sxs-lookup"><span data-stu-id="3f613-171">MDM</span></span>

<span data-ttu-id="3f613-172">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) Configuration Service Provider (CSP), um den Modus für jede Regel einzeln zu aktivieren und festlegen.</span><span class="sxs-lookup"><span data-stu-id="3f613-172">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="3f613-173">Im Folgenden finden Sie ein Referenzbeispiel unter Verwendung von [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="3f613-173">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="3f613-174">Die Werte zum Aktivieren (Blockieren), Deaktivieren, Warnen oder Aktivieren im Überwachungsmodus sind:</span><span class="sxs-lookup"><span data-stu-id="3f613-174">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="3f613-175">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="3f613-175">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="3f613-176">1 : Block (Aktivieren der ASR-Regel)</span><span class="sxs-lookup"><span data-stu-id="3f613-176">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="3f613-177">2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)</span><span class="sxs-lookup"><span data-stu-id="3f613-177">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="3f613-178">6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen).</span><span class="sxs-lookup"><span data-stu-id="3f613-178">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="3f613-179">Der Warnmodus ist jetzt für die meisten ASR-Regeln verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3f613-179">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="3f613-180">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f613-180">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="3f613-181">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f613-181">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="3f613-182">Geben Sie unbedingt OMA-URI-Werte ohne Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="3f613-182">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3f613-183">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f613-183">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="3f613-184">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="3f613-184">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="3f613-185">Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-185">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="3f613-186">Geben Sie einen Namen und eine Beschreibung ein, wählen **Sie Attack Surface Reduction** aus, und wählen Sie Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-186">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="3f613-187">Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-187">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="3f613-188">Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f613-188">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="3f613-189">Nachdem die Richtlinie erstellt wurde, schließen **Sie**.</span><span class="sxs-lookup"><span data-stu-id="3f613-189">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="3f613-190">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3f613-190">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="3f613-191">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle In konflikt enden Gruppenrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f613-191">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="3f613-192">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-192">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3f613-193">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-193">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="3f613-194">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Microsoft Defender Exploit  >  **Guard** Attack  >  **Surface Reduction**.</span><span class="sxs-lookup"><span data-stu-id="3f613-194">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="3f613-195">Wählen **Sie Attack surface reduction rules konfigurieren aus,** und wählen Sie Aktiviert **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-195">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="3f613-196">Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="3f613-196">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="3f613-197">Wählen **Sie Anzeigen...** aus, und geben Sie die Regel-ID in der Spalte **Wertname** und den ausgewählten Status in der **Spalte Wert** wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3f613-197">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="3f613-198">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="3f613-198">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="3f613-199">1 : Block (Aktivieren der ASR-Regel)</span><span class="sxs-lookup"><span data-stu-id="3f613-199">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="3f613-200">2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)</span><span class="sxs-lookup"><span data-stu-id="3f613-200">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="3f613-201">6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen)</span><span class="sxs-lookup"><span data-stu-id="3f613-201">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-Regeln in Gruppenrichtlinien":::

5. <span data-ttu-id="3f613-203">Um Dateien und Ordner von ASR-Regeln auszuschließen, wählen Sie die Einstellung Dateien und Pfade von Attack **surface reduction rules** ausschließen aus, und legen Sie die Option auf Aktiviert **.**</span><span class="sxs-lookup"><span data-stu-id="3f613-203">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="3f613-204">Wählen **Sie Anzeigen** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **Wertname** ein.</span><span class="sxs-lookup"><span data-stu-id="3f613-204">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="3f613-205">Geben **Sie 0** in die **Spalte Wert** für jedes Element ein.</span><span class="sxs-lookup"><span data-stu-id="3f613-205">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="3f613-206">Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte **Wertname** noch für die **Spalte Wert unterstützt** werden.</span><span class="sxs-lookup"><span data-stu-id="3f613-206">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="3f613-207">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f613-207">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="3f613-208">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle in Konflikt enden PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f613-208">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="3f613-209">Um Benutzern das Definieren des Werts mithilfe von PowerShell zu ermöglichen, verwenden Sie die Option "Benutzerdefiniert" für die Regel in der Verwaltungsplattform.</span><span class="sxs-lookup"><span data-stu-id="3f613-209">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="3f613-210">Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **Maustaste auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="3f613-210">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3f613-211">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="3f613-211">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="3f613-212">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3f613-212">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="3f613-213">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Warnmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3f613-213">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="3f613-214">Verwenden Sie das folgende Cmdlet, um ASR-Regeln zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3f613-214">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="3f613-215">Sie müssen den Status für jede Regel einzeln angeben, aber Sie können Regeln und Zustände in einer durch Kommas getrennten Liste kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3f613-215">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="3f613-216">Im folgenden Beispiel werden die ersten beiden Regeln aktiviert, die dritte Regel deaktiviert, und die vierte Regel wird im Überwachungsmodus aktiviert:</span><span class="sxs-lookup"><span data-stu-id="3f613-216">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="3f613-217">Sie können auch das `Add-MpPreference` PowerShell-Verb verwenden, um der vorhandenen Liste neue Regeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f613-217">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3f613-218">`Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln.</span><span class="sxs-lookup"><span data-stu-id="3f613-218">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="3f613-219">Wenn Sie dem vorhandenen Satz hinzufügen möchten, verwenden Sie `Add-MpPreference` stattdessen.</span><span class="sxs-lookup"><span data-stu-id="3f613-219">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="3f613-220">Mithilfe von können Sie eine Liste der Regeln und deren aktuellen Status `Get-MpPreference` abrufen.</span><span class="sxs-lookup"><span data-stu-id="3f613-220">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="3f613-221">Verwenden Sie das folgende Cmdlet, um Dateien und Ordner von ASR-Regeln auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="3f613-221">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="3f613-222">Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Dateien und Ordner hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f613-222">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3f613-223">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="3f613-223">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="3f613-224">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3f613-224">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3f613-225">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3f613-225">Related articles</span></span>

- [<span data-ttu-id="3f613-226">Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3f613-226">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="3f613-227">Bewerten der Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3f613-227">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="3f613-228">FAQ zu Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3f613-228">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
