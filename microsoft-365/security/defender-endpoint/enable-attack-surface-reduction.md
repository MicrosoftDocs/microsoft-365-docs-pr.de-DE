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
ms.openlocfilehash: df77a3d6c1f66882600a200b83b3b2585473f42b
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995069"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="64212-104">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="64212-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64212-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64212-105">**Applies to:**</span></span>
- [<span data-ttu-id="64212-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64212-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64212-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64212-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="64212-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="64212-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64212-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64212-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="64212-110">[Attack Surface Reduction Rules](attack-surface-reduction.md) (ASR-Regeln) helfen, Aktionen zu verhindern, die von Schadsoftware häufig missbraucht werden, um Geräte und Netzwerke zu gefährdeten.</span><span class="sxs-lookup"><span data-stu-id="64212-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="64212-111">**Anforderungen** Sie können Regeln zur Reduzierung der Angriffsfläche für Geräte festlegen, auf der eine der folgenden Editionen und Versionen von Windows ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="64212-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="64212-112">Windows 10 Pro, [Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="64212-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="64212-113">Windows 10 Enterprise, [Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="64212-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="64212-114">Windows Server, [Version 1803 (Halbjährskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="64212-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="64212-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="64212-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="64212-116">Obwohl Regeln zur Reduzierung der Angriffsfläche keine [Windows E5-Lizenz](/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie bei Windows E5 erweiterte Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="64212-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="64212-117">Diese Funktionen, die nur in Windows E5 verfügbar sind, umfassen Überwachung, Analyse und Workflows, die in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft [365 Security Center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="64212-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="64212-118">Diese erweiterten Funktionen sind nicht mit einer Windows Professional- oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige- und Microsoft Defender Antivirus-Protokolle verwenden, um Ihre Ereignisse der Regel zur Reduzierung der Angriffsfläche zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="64212-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="64212-119">Jede ASR-Regel enthält eine von vier Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="64212-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="64212-120">**Nicht konfiguriert:** Deaktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="64212-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="64212-121">**Block**: Aktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="64212-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="64212-122">**Überwachung**: Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre</span><span class="sxs-lookup"><span data-stu-id="64212-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="64212-123">**Warn**: Aktivieren Sie die ASR-Regel, lassen Sie den Endbenutzer jedoch das Umgehen des Blocks zu.</span><span class="sxs-lookup"><span data-stu-id="64212-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64212-124">Derzeit wird der Warnmodus für drei ASR-Regeln nicht unterstützt, wenn Sie ASR-Regeln in Microsoft Endpoint Manager (MEM) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="64212-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="64212-125">Weitere Informationen finden Sie unter [Fälle, in denen der Warnmodus nicht unterstützt wird.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="64212-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="64212-126">Es wird dringend empfohlen, dass Sie ASR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen zu nutzen, die in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="64212-126">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="64212-127">Für andere Lizenzen wie Windows Professional oder E3, die keinen Zugriff auf erweiterte Überwachungs- und Berichtsfunktionen haben, können Sie jedoch eigene Überwachungs- und Berichterstellungstools neben den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignis forwarding).</span><span class="sxs-lookup"><span data-stu-id="64212-127">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="64212-128">Weitere Informationen zur Windows-Lizenzierung finden Sie unter [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im Handbuch zur [Volumenlizenzierung für Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="64212-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="64212-129">Sie können Regeln zur Reduzierung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="64212-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="64212-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="64212-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="64212-131">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="64212-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="64212-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64212-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="64212-133">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="64212-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="64212-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64212-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="64212-135">Die Unternehmensverwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="64212-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="64212-136">Die Unternehmensverwaltung überschreibt beim Start alle in Konflikt enden Gruppenrichtlinien oder PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="64212-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="64212-137">Ausschließen von Dateien und Ordnern aus ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="64212-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="64212-138">Sie können ausschließen, dass Dateien und Ordner von den meisten Regeln zur Reduzierung der Angriffsfläche ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="64212-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="64212-139">Dies bedeutet, dass selbst wenn eine ASR-Regel bestimmt, dass die Datei oder der Ordner schädliches Verhalten enthält, die Ausführung der Datei nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="64212-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="64212-140">Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infizieren.</span><span class="sxs-lookup"><span data-stu-id="64212-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="64212-141">Sie können #A0 auch von der Auslösung basierend auf Zertifikat- und Dateihashes ausschließen, indem Sie bestimmte Defender for Endpoint-Datei- und Zertifikatindikatoren zulassen.</span><span class="sxs-lookup"><span data-stu-id="64212-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="64212-142">(Siehe [Verwalten von Indikatoren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="64212-142">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64212-143">Das Ausschließen von Dateien oder Ordnern kann den von den ASR-Regeln bereitgestellten Schutz erheblich verringern.</span><span class="sxs-lookup"><span data-stu-id="64212-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="64212-144">Ausgeschlossene Dateien können ausgeführt werden, und es werden keine Berichte oder Ereignisse aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="64212-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="64212-145">Wenn ASR-Regeln Dateien erkennen, die Ihrer Meinung nach nicht erkannt werden sollten, sollten Sie zuerst den Überwachungsmodus verwenden, um die [Regel zu testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="64212-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="64212-146">Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), Sie können jedoch nicht angeben, für welche Regeln die Ausschlüsse gelten.</span><span class="sxs-lookup"><span data-stu-id="64212-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="64212-147">Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="64212-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="64212-148">Wenn Sie beispielsweise einen Ausschluss für einen bereits ausgeführten Updatedienst hinzufügen, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="64212-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="64212-149">ASR-Regeln unterstützen Umgebungsvariablen und Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="64212-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="64212-150">Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="64212-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="64212-151">Die folgenden Verfahren zum Aktivieren von ASR-Regeln enthalten Anweisungen zum Ausschließen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="64212-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="64212-152">Intune</span><span class="sxs-lookup"><span data-stu-id="64212-152">Intune</span></span>

1. <span data-ttu-id="64212-153">Wählen **Sie Gerätekonfigurationsprofile**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="64212-154">Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues.</span><span class="sxs-lookup"><span data-stu-id="64212-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="64212-155">Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen aus,** und geben Sie Informationen für dieses Profil ein.</span><span class="sxs-lookup"><span data-stu-id="64212-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="64212-156">Wählen **Sie für Profiltyp** **Endpunktschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="64212-157">Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** und dann **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="64212-158">Wählen Sie **im Bereich** Endpunktschutz die option Windows Defender **Exploit Guard** aus, und wählen Sie dann Attack Surface **Reduction aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="64212-159">Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.</span><span class="sxs-lookup"><span data-stu-id="64212-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="64212-160">Geben **Sie unter Attack Surface Reduction exceptions** einzelne Dateien und Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="64212-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="64212-161">Sie können auch **Importieren auswählen,** um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von DEN REGELN ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="64212-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="64212-162">Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:</span><span class="sxs-lookup"><span data-stu-id="64212-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="64212-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="64212-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="64212-164">Wählen **Sie in** den drei Konfigurationsfenstern OK aus.</span><span class="sxs-lookup"><span data-stu-id="64212-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="64212-165">Wählen Sie dann **Erstellen** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **Speichern,** wenn Sie eine vorhandene Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="64212-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="64212-166">MDM</span><span class="sxs-lookup"><span data-stu-id="64212-166">MDM</span></span>

<span data-ttu-id="64212-167">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) Configuration Service Provider (CSP), um den Modus für jede Regel einzeln zu aktivieren und festlegen.</span><span class="sxs-lookup"><span data-stu-id="64212-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="64212-168">Im Folgenden finden Sie ein Referenzbeispiel unter Verwendung von [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="64212-168">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="64212-169">Die Werte zum Aktivieren (Blockieren), Deaktivieren, Warnen oder Aktivieren im Überwachungsmodus sind:</span><span class="sxs-lookup"><span data-stu-id="64212-169">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="64212-170">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="64212-170">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="64212-171">1 : Block (Aktivieren der ASR-Regel)</span><span class="sxs-lookup"><span data-stu-id="64212-171">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="64212-172">2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)</span><span class="sxs-lookup"><span data-stu-id="64212-172">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="64212-173">6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen).</span><span class="sxs-lookup"><span data-stu-id="64212-173">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="64212-174">Der Warnmodus ist jetzt für die meisten ASR-Regeln verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64212-174">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="64212-175">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="64212-175">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="64212-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="64212-176">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="64212-177">Geben Sie unbedingt OMA-URI-Werte ohne Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="64212-177">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="64212-178">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64212-178">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="64212-179">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="64212-179">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="64212-180">Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-180">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="64212-181">Geben Sie einen Namen und eine Beschreibung ein, wählen **Sie Attack Surface Reduction** aus, und wählen Sie Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-181">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="64212-182">Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-182">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="64212-183">Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64212-183">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="64212-184">Nachdem die Richtlinie erstellt wurde, schließen **Sie**.</span><span class="sxs-lookup"><span data-stu-id="64212-184">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="64212-185">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="64212-185">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="64212-186">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle In konflikt enden Gruppenrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="64212-186">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="64212-187">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-187">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="64212-188">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-188">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="64212-189">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Microsoft Defender Exploit  >  **Guard** Attack  >  **Surface Reduction**.</span><span class="sxs-lookup"><span data-stu-id="64212-189">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="64212-190">Wählen **Sie Attack surface reduction rules konfigurieren aus,** und wählen Sie Aktiviert **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-190">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="64212-191">Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="64212-191">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="64212-192">Wählen **Sie Anzeigen...** aus, und geben Sie die Regel-ID in der Spalte **Wertname** und den ausgewählten Status in der **Spalte Wert** wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="64212-192">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="64212-193">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="64212-193">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="64212-194">1 : Block (Aktivieren der ASR-Regel)</span><span class="sxs-lookup"><span data-stu-id="64212-194">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="64212-195">2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)</span><span class="sxs-lookup"><span data-stu-id="64212-195">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="64212-196">6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen)</span><span class="sxs-lookup"><span data-stu-id="64212-196">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-Regeln in Gruppenrichtlinien":::

5. <span data-ttu-id="64212-198">Um Dateien und Ordner von ASR-Regeln auszuschließen, wählen Sie die Einstellung Dateien und Pfade von Attack **surface reduction rules** ausschließen aus, und legen Sie die Option auf Aktiviert **.**</span><span class="sxs-lookup"><span data-stu-id="64212-198">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="64212-199">Wählen **Sie Anzeigen** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **Wertname** ein.</span><span class="sxs-lookup"><span data-stu-id="64212-199">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="64212-200">Geben **Sie 0** in die **Spalte Wert** für jedes Element ein.</span><span class="sxs-lookup"><span data-stu-id="64212-200">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="64212-201">Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte **Wertname** noch für die **Spalte Wert unterstützt** werden.</span><span class="sxs-lookup"><span data-stu-id="64212-201">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="64212-202">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64212-202">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="64212-203">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle in Konflikt enden PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="64212-203">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="64212-204">Um Benutzern das Definieren des Werts mithilfe von PowerShell zu ermöglichen, verwenden Sie die Option "Benutzerdefiniert" für die Regel in der Verwaltungsplattform.</span><span class="sxs-lookup"><span data-stu-id="64212-204">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="64212-205">Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **Maustaste auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="64212-205">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="64212-206">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="64212-206">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="64212-207">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="64212-207">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="64212-208">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Warnmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="64212-208">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="64212-209">Verwenden Sie das folgende Cmdlet, um ASR-Regeln zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="64212-209">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="64212-210">Sie müssen den Status für jede Regel einzeln angeben, aber Sie können Regeln und Zustände in einer durch Kommas getrennten Liste kombinieren.</span><span class="sxs-lookup"><span data-stu-id="64212-210">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="64212-211">Im folgenden Beispiel werden die ersten beiden Regeln aktiviert, die dritte Regel deaktiviert, und die vierte Regel wird im Überwachungsmodus aktiviert:</span><span class="sxs-lookup"><span data-stu-id="64212-211">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="64212-212">Sie können auch das `Add-MpPreference` PowerShell-Verb verwenden, um der vorhandenen Liste neue Regeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="64212-212">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="64212-213">`Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln.</span><span class="sxs-lookup"><span data-stu-id="64212-213">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="64212-214">Wenn Sie dem vorhandenen Satz hinzufügen möchten, verwenden Sie `Add-MpPreference` stattdessen.</span><span class="sxs-lookup"><span data-stu-id="64212-214">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="64212-215">Mithilfe von können Sie eine Liste der Regeln und deren aktuellen Status `Get-MpPreference` abrufen.</span><span class="sxs-lookup"><span data-stu-id="64212-215">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="64212-216">Verwenden Sie das folgende Cmdlet, um Dateien und Ordner von ASR-Regeln auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="64212-216">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="64212-217">Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Dateien und Ordner hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="64212-217">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64212-218">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="64212-218">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="64212-219">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="64212-219">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="64212-220">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="64212-220">Related articles</span></span>

- [<span data-ttu-id="64212-221">Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="64212-221">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="64212-222">Bewerten der Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="64212-222">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="64212-223">FAQ zu Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="64212-223">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
