---
title: Aktivieren der Regeln zur Verringerung der Angriffsfläche
description: Aktivieren Sie Regeln zur Verringerung der Angriffsfläche (Attack Surface Reduction, ASR), um Ihre Geräte vor Angriffen zu schützen, die Makros, Skripts und allgemeine Einfügungstechniken verwenden.
keywords: Attack Surface Reduction, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsschutz, aktivieren, aktivieren, aktivieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: 65215d15e79ab03611bbf28c153d6882fd1c355d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229143"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="3626e-104">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3626e-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="3626e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3626e-105">**Applies to:**</span></span>

- [<span data-ttu-id="3626e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3626e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3626e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3626e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3626e-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="3626e-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="3626e-109">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="3626e-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="3626e-110">[Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md) (ATTACK Surface Reduction Rules, ASR-Regeln) tragen dazu bei, Aktionen zu verhindern, die schadsoftware häufig missbraucht, um Geräte und Netzwerke zu kompromittieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="3626e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3626e-111">Requirements</span></span>

<span data-ttu-id="3626e-112">Attack Surface Reduction-Features in Windows Versionen</span><span class="sxs-lookup"><span data-stu-id="3626e-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="3626e-113">Sie können Regeln zur Verringerung der Angriffsfläche für Geräte festlegen, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="3626e-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="3626e-114">Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="3626e-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3626e-115">Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="3626e-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3626e-116">Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="3626e-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3626e-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3626e-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3626e-118">Um den gesamten Featuresatz von Regeln zur Verringerung der Angriffsfläche zu verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3626e-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="3626e-119">Windows Defender Antivirus als primäre AV(Echtzeitschutz aktiviert)</span><span class="sxs-lookup"><span data-stu-id="3626e-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="3626e-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (einige Regeln erfordern dies)</span><span class="sxs-lookup"><span data-stu-id="3626e-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="3626e-121">Windows 10 Enterprise E5- oder E3-Lizenz oder Microsoft 365 Business-Lizenz</span><span class="sxs-lookup"><span data-stu-id="3626e-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="3626e-122">Obwohl die Regeln zur Verringerung der Angriffsfläche keine [Windows E5-Lizenz](/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie mit einer Windows E5-Lizenz erweiterte Verwaltungsfunktionen, einschließlich Überwachung, Analyse und Workflows, die in Defender für Endpunkt verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="3626e-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="3626e-123">Diese erweiterten Funktionen sind nicht mit einer E3-Lizenz verfügbar, sie können jedoch weiterhin die Ereignisanzeige verwenden, um Regelereignisse zur Verringerung der Angriffsfläche zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3626e-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="3626e-124">Jede ASR-Regel enthält eine von vier Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3626e-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="3626e-125">**Nicht konfiguriert:** Deaktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="3626e-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="3626e-126">**Blockieren:** Aktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="3626e-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="3626e-127">**Überwachung:** Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="3626e-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="3626e-128">**Warnen:** Aktivieren der ASR-Regel, aber Zulassen, dass der Endbenutzer den Block umgeht</span><span class="sxs-lookup"><span data-stu-id="3626e-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3626e-129">Derzeit wird der Warnmodus für drei ASR-Regeln nicht unterstützt, wenn Sie ASR-Regeln in Microsoft Endpoint Manager (MEM) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="3626e-130">Weitere Informationen finden Sie unter Fälle, in denen der [Warnmodus nicht unterstützt wird.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="3626e-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="3626e-131">Es wird dringend empfohlen, ASR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) zu verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen zu [nutzen,](microsoft-defender-endpoint.md) die in Microsoft Defender für Endpunkt (Defender für Endpunkt) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3626e-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="3626e-132">Wenn Sie jedoch über eine andere Lizenz verfügen, z. B. Windows Professional oder Windows E3, die keine erweiterten Überwachungs- und Berichtsfunktionen enthalten, können Sie ihre eigenen Überwachungs- und Berichterstellungstools zusätzlich zu den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignisweiterleitung).</span><span class="sxs-lookup"><span data-stu-id="3626e-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="3626e-133">Weitere Informationen zu Windows Lizenzierung finden Sie unter [Windows 10 Lizenzierung](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im [Volumenlizenzierungshandbuch für Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="3626e-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="3626e-134">Sie können Regeln zur Verringerung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3626e-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="3626e-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3626e-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="3626e-136">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="3626e-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="3626e-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3626e-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="3626e-138">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3626e-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="3626e-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3626e-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="3626e-140">Enterprise-Verwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3626e-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="3626e-141">die Verwaltung auf Enterprise Ebene überschreibt beim Start alle widersprüchlichen Gruppenrichtlinien oder PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3626e-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="3626e-142">Ausschließen von Dateien und Ordnern aus ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="3626e-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="3626e-143">Sie können Dateien und Ordner von der Auswertung durch die meisten Regeln zur Verringerung der Angriffsfläche ausschließen.</span><span class="sxs-lookup"><span data-stu-id="3626e-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="3626e-144">Dies bedeutet, dass selbst wenn eine ASR-Regel feststellt, dass die Datei oder der Ordner schädliches Verhalten enthält, die Ausführung der Datei nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="3626e-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="3626e-145">Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3626e-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="3626e-146">Sie können ASR-Regeln auch von der Auslösung basierend auf Zertifikat- und Dateihashes ausschließen, indem Sie angegebene Defender für Endpunkt-Datei- und Zertifikatindikatoren zulassen.</span><span class="sxs-lookup"><span data-stu-id="3626e-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="3626e-147">(Siehe ["Indikatoren](manage-indicators.md)verwalten".)</span><span class="sxs-lookup"><span data-stu-id="3626e-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3626e-148">Das Ausschließen von Dateien oder Ordnern kann den Schutz durch ASR-Regeln erheblich reduzieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="3626e-149">Ausgeschlossene Dateien dürfen ausgeführt werden, und es wird kein Bericht oder Ereignis aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3626e-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="3626e-150">Wenn ASR-Regeln Dateien erkennen, von denen Sie glauben, dass sie nicht erkannt werden sollten, sollten Sie [zuerst den Überwachungsmodus verwenden, um die Regel zu testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="3626e-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="3626e-151">Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), aber Sie können nicht angeben, für welche Regeln die Ausschlüsse gelten.</span><span class="sxs-lookup"><span data-stu-id="3626e-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="3626e-152">Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3626e-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="3626e-153">Wenn Sie beispielsweise einen Ausschluss für einen Updatedienst hinzufügen, der bereits ausgeführt wird, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3626e-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="3626e-154">ASR-Regeln unterstützen Umgebungsvariablen und Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="3626e-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="3626e-155">Informationen zur Verwendung von Platzhaltern finden Sie unter [Verwenden von Platzhaltern in den Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="3626e-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="3626e-156">Die folgenden Verfahren zum Aktivieren von ASR-Regeln umfassen Anweisungen zum Ausschließen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="3626e-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="3626e-157">Intune</span><span class="sxs-lookup"><span data-stu-id="3626e-157">Intune</span></span>

1. <span data-ttu-id="3626e-158">Wählen Sie **Gerätekonfigurationsprofile**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="3626e-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="3626e-159">Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues.</span><span class="sxs-lookup"><span data-stu-id="3626e-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="3626e-160">Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen** aus, und geben Sie Informationen für dieses Profil ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="3626e-161">Wählen Sie für **Profiltyp** **Endpunktschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="3626e-162">Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** und dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="3626e-163">Wählen Sie im **Endpunktschutzbereich** **Windows Defender Exploit Guard** und dann Attack Surface **Reduction** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="3626e-164">Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="3626e-165">Geben Sie unter **Attack Surface Reduction-Ausnahmen** einzelne Dateien und Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="3626e-166">Sie können auch **"Importieren"** auswählen, um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von ASR-Regeln ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3626e-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="3626e-167">Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:</span><span class="sxs-lookup"><span data-stu-id="3626e-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="3626e-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="3626e-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="3626e-169">Wählen Sie in den drei Konfigurationsbereichen **"OK"** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="3626e-170">Wählen Sie dann **"Erstellen"** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **"Speichern",** wenn Sie eine vorhandene bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3626e-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="3626e-171">Mem</span><span class="sxs-lookup"><span data-stu-id="3626e-171">MEM</span></span>

<span data-ttu-id="3626e-172">Sie können Microsoft Endpoint Manager (MEM)-OMA-URI verwenden, um benutzerdefinierte ASR-Regeln zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="3626e-173">Im folgenden Verfahren wird für das Beispiel die Regel ["Missbrauch von missbrauchten gefährdeten signierten Treibern blockieren"](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) verwendet.</span><span class="sxs-lookup"><span data-stu-id="3626e-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="3626e-174">Öffnen Sie das Microsoft Endpoint Manager (MEM) Admin Center.</span><span class="sxs-lookup"><span data-stu-id="3626e-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="3626e-175">Klicken Sie im Menü **"Start"** auf **"Geräte",** wählen Sie **"Konfigurationsprofil"** aus, und klicken Sie dann auf **"Profil erstellen".**</span><span class="sxs-lookup"><span data-stu-id="3626e-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-176">![MEM-Profil erstellen](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="3626e-177">Wählen Sie in **"Profil erstellen"** in den folgenden beiden Dropdownlisten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3626e-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="3626e-178">Wählen Sie **in** **"Plattform"** Windows 10 und höher aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="3626e-179">Wählen Sie **im Profiltyp** **"Vorlagen" aus.**</span><span class="sxs-lookup"><span data-stu-id="3626e-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="3626e-180">Wählen Sie **"Benutzerdefiniert"** aus, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="3626e-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-181">![MEM-Regelprofilattribute](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="3626e-182">Das Tool für benutzerdefinierte Vorlagen wird mit Schritt **1 Basics** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3626e-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="3626e-183">Geben Sie in **1 Basics** unter **Name** einen Namen für Ihre Vorlage ein, und in **"Beschreibung"** können Sie eine Beschreibung eingeben (optional).</span><span class="sxs-lookup"><span data-stu-id="3626e-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-184">![GRUNDLEGENDE MEM-Attribute](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="3626e-185">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3626e-185">Click **Next**.</span></span> <span data-ttu-id="3626e-186">Schritt **2: Konfigurationseinstellungen** werden geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3626e-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="3626e-187">Klicken Sie für OMA-URI-Einstellungen auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3626e-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="3626e-188">Jetzt werden zwei Optionen angezeigt: **Hinzufügen** und **Exportieren.**</span><span class="sxs-lookup"><span data-stu-id="3626e-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-189">![MEM-Konfigurationseinstellungen](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="3626e-190">Klicken Sie erneut auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3626e-190">Click **Add** again.</span></span> <span data-ttu-id="3626e-191">Das **Add Row OMA-URI Einstellungen** opens.</span><span class="sxs-lookup"><span data-stu-id="3626e-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="3626e-192">Führen Sie in **"Zeile hinzufügen"** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3626e-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="3626e-193">Geben Sie unter **"Name"** einen Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="3626e-194">Geben Sie in **Beschreibung** eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="3626e-195">Geben Sie in **OMA-URI** den spezifischen OMA-URI-Link für die Regel ein, die Sie hinzufügen, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="3626e-196">Wählen Sie **im Datentyp** **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="3626e-197">Geben Sie in **Wert** den GUID-Wert, das Vorzeichen und den Statuswert ohne Leerzeichen ein, oder fügen Sie ihn ein ( \= _GUID=StateValue_).</span><span class="sxs-lookup"><span data-stu-id="3626e-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="3626e-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="3626e-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-199">![MEM-OMA-URI-Konfiguration](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="3626e-200">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3626e-200">Click **Save**.</span></span> <span data-ttu-id="3626e-201">**Zeile hinzufügen** wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="3626e-201">**Add Row** closes.</span></span> <span data-ttu-id="3626e-202">Klicken Sie **in "Benutzerdefiniert"** auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3626e-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="3626e-203">In Schritt **3 sind Bereichstags** optional.</span><span class="sxs-lookup"><span data-stu-id="3626e-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="3626e-204">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3626e-204">Do one of the following:</span></span>

   - <span data-ttu-id="3626e-205">Klicken Sie auf **"Bereichstags auswählen",** wählen Sie das Bereichstag (optional) aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3626e-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="3626e-206">Oder klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3626e-206">Or click **Next**</span></span>

7. <span data-ttu-id="3626e-207">Wählen Sie in Schritt **4 "Zuordnungen"** in **"Enthaltene Gruppen"** – für die Gruppen, die diese Regel anwenden soll – aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3626e-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="3626e-208">**Hinzufügen von Gruppen**</span><span class="sxs-lookup"><span data-stu-id="3626e-208">**Add groups**</span></span>
   - <span data-ttu-id="3626e-209">**Hinzufügen aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="3626e-209">**Add all users**</span></span>
   - <span data-ttu-id="3626e-210">**Hinzufügen aller Geräte**</span><span class="sxs-lookup"><span data-stu-id="3626e-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-211">![MEM-Zuweisungen](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="3626e-212">Wählen Sie in **ausgeschlossenen Gruppen** alle Gruppen aus, die Sie von dieser Regel ausschließen möchten, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3626e-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="3626e-213">Führen Sie in Schritt **5 Anwendbarkeitsregeln** für die folgenden Einstellungen die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3626e-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="3626e-214">Wählen Sie in **"Regel"** entweder **"Profil zuweisen" oder** **"Profil nicht zuweisen"** aus, wenn</span><span class="sxs-lookup"><span data-stu-id="3626e-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="3626e-215">Wählen Sie in **"Eigenschaft"** die Eigenschaft aus, auf die diese Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3626e-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="3626e-216">Geben Sie in **Wert** den entsprechenden Wert oder Wertebereich ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3626e-217">![MEM-Anwendbarkeitsregeln](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="3626e-218">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3626e-218">Click **Next**.</span></span> <span data-ttu-id="3626e-219">Überprüfen und erstellen Sie in Schritt **6** die Einstellungen und Informationen, die Sie ausgewählt und eingegeben haben, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="3626e-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3626e-220">![MEM-Überprüfung und -Erstellung](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="3626e-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3626e-221">Regeln sind aktiv und sind innerhalb von Minuten aktiv.</span><span class="sxs-lookup"><span data-stu-id="3626e-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="3626e-222">Konfliktbehandlung:</span><span class="sxs-lookup"><span data-stu-id="3626e-222">Conflict handling:</span></span>
>
> <span data-ttu-id="3626e-223">Wenn Sie einem Gerät zwei unterschiedliche ASR-Richtlinien zuweisen, ist die Art und Weise, wie Konflikte behandelt werden, Regeln, denen unterschiedliche Zustände zugewiesen sind, keine Konfliktverwaltung vorhanden, und das Ergebnis ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="3626e-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="3626e-224">Regeln, die keine Konflikte verursachen, führen nicht zu einem Fehler, und die Regel wird ordnungsgemäß angewendet.</span><span class="sxs-lookup"><span data-stu-id="3626e-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="3626e-225">Das Ergebnis ist, dass die erste Regel angewendet wird und nachfolgende nicht miteinander in Konflikt stehende Regeln mit der Richtlinie zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3626e-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="3626e-226">Mdm</span><span class="sxs-lookup"><span data-stu-id="3626e-226">MDM</span></span>

<span data-ttu-id="3626e-227">Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP), um den Modus für jede Regel einzeln zu aktivieren und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3626e-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="3626e-228">Es folgt ein Referenzbeispiel mit [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="3626e-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="3626e-229">Die Werte zum Aktivieren (Blockieren), Deaktivieren, Warnen oder Aktivieren im Überwachungsmodus sind:</span><span class="sxs-lookup"><span data-stu-id="3626e-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="3626e-230">0 : Deaktivieren (Asr-Regel deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="3626e-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="3626e-231">1 : Blockieren (ASR-Regel aktivieren)</span><span class="sxs-lookup"><span data-stu-id="3626e-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="3626e-232">2 : Überwachung (Bewerten, wie sich die ASR-Regel bei Aktivierung auf Ihre Organisation auswirken würde)</span><span class="sxs-lookup"><span data-stu-id="3626e-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="3626e-233">6 : Warnen (Aktivieren sie die ASR-Regel, aber lassen Sie zu, dass der Endbenutzer den Block umgehen kann).</span><span class="sxs-lookup"><span data-stu-id="3626e-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="3626e-234">Der Warnmodus ist jetzt für die meisten ASR-Regeln verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3626e-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="3626e-235">Verwenden Sie [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3626e-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="3626e-236">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3626e-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="3626e-237">Achten Sie darauf, OMA-URI-Werte ohne Leerzeichen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="3626e-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3626e-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3626e-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="3626e-239">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="3626e-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="3626e-240">Wählen Sie **"Home**  >  **Create Exploit Guard Policy" aus.**</span><span class="sxs-lookup"><span data-stu-id="3626e-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="3626e-241">Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **Attack Surface Reduction** aus, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="3626e-242">Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="3626e-243">Überprüfen Sie die Einstellungen, und wählen Sie **"Weiter"** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3626e-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="3626e-244">Nachdem die Richtlinie erstellt wurde, **schließen Sie**.</span><span class="sxs-lookup"><span data-stu-id="3626e-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="3626e-245">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3626e-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="3626e-246">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle widersprüchlichen Gruppenrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3626e-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="3626e-247">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](https://technet.microsoft.com/library/cc731212.aspx), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3626e-248">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="3626e-249">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Microsoft Defender Exploit Guard**  >  **Attack Surface Reduction.**</span><span class="sxs-lookup"><span data-stu-id="3626e-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="3626e-250">Wählen Sie **"Attack Surface Reduction"-Regeln konfigurieren** und **"Aktiviert"** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="3626e-251">Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt "Optionen" festlegen.</span><span class="sxs-lookup"><span data-stu-id="3626e-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="3626e-252">Wählen Sie **"Anzeigen" aus,** und geben Sie die Regel-ID in der Spalte **"Wertname"** und den ausgewählten Status in der Spalte **"Wert"** wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3626e-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="3626e-253">0 : Deaktivieren (Asr-Regel deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="3626e-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="3626e-254">1 : Blockieren (ASR-Regel aktivieren)</span><span class="sxs-lookup"><span data-stu-id="3626e-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="3626e-255">2 : Überwachung (Bewerten, wie sich die ASR-Regel bei Aktivierung auf Ihre Organisation auswirken würde)</span><span class="sxs-lookup"><span data-stu-id="3626e-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="3626e-256">6 : Warnen (Aktivieren der ASR-Regel, aber Zulassen, dass der Endbenutzer den Block umgeht)</span><span class="sxs-lookup"><span data-stu-id="3626e-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-Regeln in Gruppenrichtlinien":::

5. <span data-ttu-id="3626e-258">Um Dateien und Ordner von ASR-Regeln auszuschließen, wählen Sie die Einstellung **"Dateien und Pfade aus Attack Surface Reduction"-Regeln ausschließen aus,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="3626e-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="3626e-259">Wählen Sie **"Anzeigen"** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **"Wertname"** ein.</span><span class="sxs-lookup"><span data-stu-id="3626e-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="3626e-260">Geben Sie 0 in die **Spalte Wert** für jedes Element ein. </span><span class="sxs-lookup"><span data-stu-id="3626e-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="3626e-261">Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte mit dem **Wertnamen** noch für die **Spalte Value** unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3626e-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="3626e-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3626e-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="3626e-263">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle widersprüchlichen PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3626e-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="3626e-264">Damit Benutzer den Wert mithilfe von PowerShell definieren können, verwenden Sie die Option "Benutzerdefiniert" für die Regel in der Verwaltungsplattform.</span><span class="sxs-lookup"><span data-stu-id="3626e-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="3626e-265">Geben Sie **powershell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="3626e-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3626e-266">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="3626e-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="3626e-267">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3626e-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="3626e-268">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Warnmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3626e-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="3626e-269">Verwenden Sie das folgende Cmdlet, um den ASR-Blockierungsfehler von gefährdeten signierten Treibern zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3626e-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="3626e-270">Verwenden Sie das folgende Cmdlet, um ASR-Regeln zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3626e-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="3626e-271">Sie müssen den Status für jede Regel einzeln angeben, aber Sie können Regeln und Zustände in einer durch Trennzeichen getrennten Liste kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="3626e-272">Im folgenden Beispiel werden die ersten beiden Regeln aktiviert, die dritte Regel deaktiviert, und die vierte Regel wird im Überwachungsmodus aktiviert:</span><span class="sxs-lookup"><span data-stu-id="3626e-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="3626e-273">Sie können auch das `Add-MpPreference` PowerShell-Verb verwenden, um der vorhandenen Liste neue Regeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3626e-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3626e-274">`Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln.</span><span class="sxs-lookup"><span data-stu-id="3626e-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="3626e-275">Wenn Sie dem vorhandenen Satz hinzufügen möchten, verwenden Sie `Add-MpPreference` stattdessen.</span><span class="sxs-lookup"><span data-stu-id="3626e-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="3626e-276">Sie können eine Liste der Regeln und deren aktuellen Status abrufen, indem Sie `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="3626e-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="3626e-277">Verwenden Sie das folgende Cmdlet, um Dateien und Ordner von ASR-Regeln auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="3626e-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="3626e-278">Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Dateien und Ordner hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3626e-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3626e-279">Dient `Add-MpPreference` zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="3626e-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="3626e-280">Mithilfe des `Set-MpPreference` Cmdlets wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3626e-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3626e-281">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3626e-281">Related articles</span></span>

- [<span data-ttu-id="3626e-282">Reduzieren von Angriffsflächen mit Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3626e-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="3626e-283">Auswerten der Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3626e-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="3626e-284">Häufig gestellte Fragen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3626e-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
