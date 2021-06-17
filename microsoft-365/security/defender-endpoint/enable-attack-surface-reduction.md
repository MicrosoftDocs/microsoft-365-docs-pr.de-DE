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
ms.openlocfilehash: b4040a60e59f3256b69f90d33af6f7543e50784e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984796"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="08cc1-104">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="08cc1-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="08cc1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="08cc1-105">**Applies to:**</span></span>

- [<span data-ttu-id="08cc1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="08cc1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08cc1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08cc1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="08cc1-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="08cc1-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="08cc1-109">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="08cc1-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="08cc1-110">[Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md) (ATTACK Surface Reduction Rules, ASR-Regeln) tragen dazu bei, Aktionen zu verhindern, die schadsoftware häufig missbraucht, um Geräte und Netzwerke zu kompromittieren.</span><span class="sxs-lookup"><span data-stu-id="08cc1-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="08cc1-111">**Anforderungen** Sie können Regeln zur Verringerung der Angriffsfläche für Geräte festlegen, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="08cc1-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="08cc1-112">Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="08cc1-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="08cc1-113">Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="08cc1-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="08cc1-114">Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="08cc1-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="08cc1-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="08cc1-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="08cc1-116">Obwohl die Regeln zur Verringerung der Angriffsfläche keine [Windows E5-Lizenz](/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie, wenn Sie über Windows E5 verfügen, erweiterte Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="08cc1-117">Zu diesen Funktionen, die nur in Windows E5 verfügbar sind, gehören Überwachung, Analysen und Workflows, die in [Defender für Endpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft 365 Security [Center.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="08cc1-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="08cc1-118">Diese erweiterten Funktionen sind nicht mit einer Windows Professional- oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige und Microsoft Defender Antivirus Protokolle verwenden, um ihre Regelereignisse zur Verringerung der Angriffsfläche zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="08cc1-119">Jede ASR-Regel enthält eine von vier Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="08cc1-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="08cc1-120">**Nicht konfiguriert:** Deaktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="08cc1-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="08cc1-121">**Blockieren:** Aktivieren der ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="08cc1-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="08cc1-122">**Überwachung:** Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="08cc1-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="08cc1-123">**Warnen:** Aktivieren der ASR-Regel, aber Zulassen, dass der Endbenutzer den Block umgeht</span><span class="sxs-lookup"><span data-stu-id="08cc1-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08cc1-124">Derzeit wird der Warnmodus für drei ASR-Regeln nicht unterstützt, wenn Sie ASR-Regeln in Microsoft Endpoint Manager (MEM) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08cc1-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="08cc1-125">Weitere Informationen finden Sie unter Fälle, in denen der [Warnmodus nicht unterstützt wird.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="08cc1-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="08cc1-126">Es wird dringend empfohlen, ASR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) zu verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen in [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) (Defender für Endpunkt) zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-126">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="08cc1-127">Wenn Sie jedoch über eine andere Lizenz verfügen, z. B. Windows Professional oder Windows E3, die keine erweiterten Überwachungs- und Berichtsfunktionen umfassen, können Sie ihre eigenen Überwachungs- und Berichterstellungstools zusätzlich zu den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignisweiterleitung).</span><span class="sxs-lookup"><span data-stu-id="08cc1-127">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="08cc1-128">Weitere Informationen zu Windows Lizenzierung finden Sie unter [Windows 10 Lizenzierung](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im [Volumenlizenzierungshandbuch für Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="08cc1-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="08cc1-129">Sie können Regeln zur Verringerung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cc1-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="08cc1-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="08cc1-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="08cc1-131">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="08cc1-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="08cc1-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="08cc1-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="08cc1-133">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="08cc1-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="08cc1-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="08cc1-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="08cc1-135">Enterprise-Verwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="08cc1-136">die Verwaltung auf Enterprise Ebene überschreibt beim Start alle widersprüchlichen Gruppenrichtlinien oder PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="08cc1-137">Ausschließen von Dateien und Ordnern aus ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="08cc1-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="08cc1-138">Sie können Dateien und Ordner von der Auswertung durch die meisten Regeln zur Verringerung der Angriffsfläche ausschließen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="08cc1-139">Dies bedeutet, dass selbst wenn eine ASR-Regel feststellt, dass die Datei oder der Ordner schädliches Verhalten enthält, die Ausführung der Datei nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="08cc1-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="08cc1-140">Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infiziert werden.</span><span class="sxs-lookup"><span data-stu-id="08cc1-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="08cc1-141">Sie können ASR-Regeln auch von der Auslösung basierend auf Zertifikat- und Dateihashes ausschließen, indem Sie angegebene Defender für Endpunkt-Datei- und Zertifikatindikatoren zulassen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="08cc1-142">(Siehe ["Indikatoren](manage-indicators.md)verwalten".)</span><span class="sxs-lookup"><span data-stu-id="08cc1-142">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08cc1-143">Das Ausschließen von Dateien oder Ordnern kann den Schutz durch ASR-Regeln erheblich reduzieren.</span><span class="sxs-lookup"><span data-stu-id="08cc1-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="08cc1-144">Ausgeschlossene Dateien dürfen ausgeführt werden, und es wird kein Bericht oder Ereignis aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="08cc1-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="08cc1-145">Wenn ASR-Regeln Dateien erkennen, von denen Sie glauben, dass sie nicht erkannt werden sollten, sollten Sie [zuerst den Überwachungsmodus verwenden, um die Regel zu testen.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="08cc1-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="08cc1-146">Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), aber Sie können nicht angeben, für welche Regeln die Ausschlüsse gelten.</span><span class="sxs-lookup"><span data-stu-id="08cc1-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="08cc1-147">Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="08cc1-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="08cc1-148">Wenn Sie beispielsweise einen Ausschluss für einen Updatedienst hinzufügen, der bereits ausgeführt wird, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="08cc1-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="08cc1-149">ASR-Regeln unterstützen Umgebungsvariablen und Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="08cc1-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="08cc1-150">Informationen zur Verwendung von Platzhaltern finden Sie unter [Verwenden von Platzhaltern in den Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="08cc1-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="08cc1-151">Die folgenden Verfahren zum Aktivieren von ASR-Regeln umfassen Anweisungen zum Ausschließen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="08cc1-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="08cc1-152">Intune</span><span class="sxs-lookup"><span data-stu-id="08cc1-152">Intune</span></span>

1. <span data-ttu-id="08cc1-153">Wählen Sie **Gerätekonfigurationsprofile**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="08cc1-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="08cc1-154">Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues.</span><span class="sxs-lookup"><span data-stu-id="08cc1-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="08cc1-155">Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen** aus, und geben Sie Informationen für dieses Profil ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="08cc1-156">Wählen Sie für **Profiltyp** **Endpunktschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="08cc1-157">Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** und dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="08cc1-158">Wählen Sie im **Endpunktschutzbereich** **Windows Defender Exploit Guard** und dann Attack Surface **Reduction** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="08cc1-159">Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="08cc1-160">Geben Sie unter **Attack Surface Reduction-Ausnahmen** einzelne Dateien und Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="08cc1-161">Sie können auch **"Importieren"** auswählen, um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von ASR-Regeln ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="08cc1-162">Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:</span><span class="sxs-lookup"><span data-stu-id="08cc1-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="08cc1-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="08cc1-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="08cc1-164">Wählen Sie in den drei Konfigurationsbereichen **"OK"** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="08cc1-165">Wählen Sie dann **"Erstellen"** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **"Speichern",** wenn Sie eine vorhandene bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="08cc1-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="08cc1-166">Mem</span><span class="sxs-lookup"><span data-stu-id="08cc1-166">MEM</span></span>

<span data-ttu-id="08cc1-167">Sie können Microsoft Endpoint Manager (MEM)-OMA-URI verwenden, um benutzerdefinierte ASR-Regeln zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08cc1-167">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="08cc1-168">Im folgenden Verfahren wird für das Beispiel die Regel ["Missbrauch von missbrauchten gefährdeten signierten Treibern blockieren"](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) verwendet.</span><span class="sxs-lookup"><span data-stu-id="08cc1-168">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="08cc1-169">Öffnen Sie das Microsoft Endpoint Manager (MEM) Admin Center.</span><span class="sxs-lookup"><span data-stu-id="08cc1-169">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="08cc1-170">Klicken Sie im Menü **"Start"** auf **"Geräte",** wählen Sie **"Konfigurationsprofil"** aus, und klicken Sie dann auf **"Profil erstellen".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-170">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-171">![MEM-Profil erstellen](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-171">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="08cc1-172">Wählen Sie in **"Profil erstellen"** in den folgenden beiden Dropdownlisten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="08cc1-172">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="08cc1-173">Wählen Sie **in** **"Plattform"** Windows 10 und höher aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-173">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="08cc1-174">Wählen Sie **im Profiltyp** **"Vorlagen" aus.**</span><span class="sxs-lookup"><span data-stu-id="08cc1-174">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="08cc1-175">Wählen Sie **"Benutzerdefiniert"** aus, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-175">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-176">![MEM-Regelprofilattribute](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-176">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="08cc1-177">Das Tool für benutzerdefinierte Vorlagen wird mit Schritt **1 Basics** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08cc1-177">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="08cc1-178">Geben Sie in **1 Basics** unter **Name** einen Namen für Ihre Vorlage ein, und in **"Beschreibung"** können Sie eine Beschreibung eingeben (optional).</span><span class="sxs-lookup"><span data-stu-id="08cc1-178">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-179">![GRUNDLEGENDE MEM-Attribute](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-179">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="08cc1-180">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="08cc1-180">Click **Next**.</span></span> <span data-ttu-id="08cc1-181">Schritt **2: Konfigurationseinstellungen** werden geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08cc1-181">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="08cc1-182">Klicken Sie für OMA-URI-Einstellungen auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-182">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="08cc1-183">Jetzt werden zwei Optionen angezeigt: **Hinzufügen** und **Exportieren.**</span><span class="sxs-lookup"><span data-stu-id="08cc1-183">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-184">![MEM-Konfigurationseinstellungen](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-184">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="08cc1-185">Klicken Sie erneut auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-185">Click **Add** again.</span></span> <span data-ttu-id="08cc1-186">Das **Add Row OMA-URI Einstellungen** opens.</span><span class="sxs-lookup"><span data-stu-id="08cc1-186">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="08cc1-187">Führen Sie in **"Zeile hinzufügen"** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="08cc1-187">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="08cc1-188">Geben Sie unter **"Name"** einen Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-188">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="08cc1-189">Geben Sie in **Beschreibung** eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-189">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="08cc1-190">Geben Sie in **OMA-URI** den spezifischen OMA-URI-Link für die Regel ein, die Sie hinzufügen, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-190">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="08cc1-191">Wählen Sie **im Datentyp** **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-191">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="08cc1-192">Geben Sie in **Wert** den GUID-Wert, das Vorzeichen und den Statuswert ohne Leerzeichen ein, oder fügen Sie ihn ein ( \= _GUID=StateValue_).</span><span class="sxs-lookup"><span data-stu-id="08cc1-192">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="08cc1-193">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="08cc1-193">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-194">![MEM-OMA-URI-Konfiguration](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-194">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="08cc1-195">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="08cc1-195">Click **Save**.</span></span> <span data-ttu-id="08cc1-196">**Zeile hinzufügen** wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-196">**Add Row** closes.</span></span> <span data-ttu-id="08cc1-197">Klicken Sie **in "Benutzerdefiniert"** auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-197">In **Custom**, click **Next**.</span></span> <span data-ttu-id="08cc1-198">In Schritt **3 sind Bereichstags** optional.</span><span class="sxs-lookup"><span data-stu-id="08cc1-198">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="08cc1-199">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="08cc1-199">Do one of the following:</span></span>

   - <span data-ttu-id="08cc1-200">Klicken Sie auf **"Bereichstags auswählen",** wählen Sie das Bereichstag (optional) aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-200">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="08cc1-201">Oder klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-201">Or click **Next**</span></span>

7. <span data-ttu-id="08cc1-202">Wählen Sie in Schritt **4 "Zuordnungen"** in **"Enthaltene Gruppen"** – für die Gruppen, die diese Regel anwenden soll – aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="08cc1-202">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="08cc1-203">**Hinzufügen von Gruppen**</span><span class="sxs-lookup"><span data-stu-id="08cc1-203">**Add groups**</span></span>
   - <span data-ttu-id="08cc1-204">**Hinzufügen aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="08cc1-204">**Add all users**</span></span>
   - <span data-ttu-id="08cc1-205">**Hinzufügen aller Geräte**</span><span class="sxs-lookup"><span data-stu-id="08cc1-205">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-206">![MEM-Zuweisungen](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-206">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="08cc1-207">Wählen Sie in **ausgeschlossenen Gruppen** alle Gruppen aus, die Sie von dieser Regel ausschließen möchten, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-207">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="08cc1-208">Führen Sie in Schritt **5 Anwendbarkeitsregeln** für die folgenden Einstellungen die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="08cc1-208">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="08cc1-209">Wählen Sie in **"Regel"** entweder **"Profil zuweisen" oder** **"Profil nicht zuweisen"** aus, wenn</span><span class="sxs-lookup"><span data-stu-id="08cc1-209">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="08cc1-210">Wählen Sie in **"Eigenschaft"** die Eigenschaft aus, auf die diese Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08cc1-210">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="08cc1-211">Geben Sie in **Wert** den entsprechenden Wert oder Wertebereich ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-211">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08cc1-212">![MEM-Anwendbarkeitsregeln](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-212">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="08cc1-213">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="08cc1-213">Click **Next**.</span></span> <span data-ttu-id="08cc1-214">Überprüfen und erstellen Sie in Schritt **6** die Einstellungen und Informationen, die Sie ausgewählt und eingegeben haben, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="08cc1-214">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08cc1-215">![MEM-Überprüfung und -Erstellung](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="08cc1-215">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="08cc1-216">Regeln sind aktiv und sind innerhalb von Minuten aktiv.</span><span class="sxs-lookup"><span data-stu-id="08cc1-216">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="08cc1-217">Konfliktbehandlung:</span><span class="sxs-lookup"><span data-stu-id="08cc1-217">Conflict handling:</span></span>
>
> <span data-ttu-id="08cc1-218">Wenn Sie einem Gerät zwei unterschiedliche ASR-Richtlinien zuweisen, ist die Art und Weise, wie Konflikte behandelt werden, Regeln, denen unterschiedliche Zustände zugewiesen sind, keine Konfliktverwaltung vorhanden, und das Ergebnis ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="08cc1-218">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="08cc1-219">Regeln, die keine Konflikte verursachen, führen nicht zu einem Fehler, und die Regel wird ordnungsgemäß angewendet.</span><span class="sxs-lookup"><span data-stu-id="08cc1-219">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="08cc1-220">Das Ergebnis ist, dass die erste Regel angewendet wird und nachfolgende nicht miteinander in Konflikt stehende Regeln mit der Richtlinie zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08cc1-220">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="08cc1-221">Mdm</span><span class="sxs-lookup"><span data-stu-id="08cc1-221">MDM</span></span>

<span data-ttu-id="08cc1-222">Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP), um den Modus für jede Regel einzeln zu aktivieren und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-222">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="08cc1-223">Es folgt ein Referenzbeispiel mit [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="08cc1-223">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="08cc1-224">Die Werte zum Aktivieren (Blockieren), Deaktivieren, Warnen oder Aktivieren im Überwachungsmodus sind:</span><span class="sxs-lookup"><span data-stu-id="08cc1-224">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="08cc1-225">0 : Deaktivieren (Asr-Regel deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="08cc1-225">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="08cc1-226">1 : Blockieren (ASR-Regel aktivieren)</span><span class="sxs-lookup"><span data-stu-id="08cc1-226">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="08cc1-227">2 : Überwachung (Bewerten, wie sich die ASR-Regel bei Aktivierung auf Ihre Organisation auswirken würde)</span><span class="sxs-lookup"><span data-stu-id="08cc1-227">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="08cc1-228">6 : Warnen (Aktivieren Sie die ASR-Regel, aber lassen Sie zu, dass der Endbenutzer den Block umgehen kann).</span><span class="sxs-lookup"><span data-stu-id="08cc1-228">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="08cc1-229">Der Warnmodus ist jetzt für die meisten ASR-Regeln verfügbar.</span><span class="sxs-lookup"><span data-stu-id="08cc1-229">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="08cc1-230">Verwenden Sie [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-230">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="08cc1-231">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08cc1-231">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="08cc1-232">Achten Sie darauf, OMA-URI-Werte ohne Leerzeichen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="08cc1-232">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="08cc1-233">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="08cc1-233">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="08cc1-234">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="08cc1-234">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="08cc1-235">Wählen Sie **"Home**  >  **Create Exploit Guard Policy" aus.**</span><span class="sxs-lookup"><span data-stu-id="08cc1-235">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="08cc1-236">Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **Attack Surface Reduction** aus, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-236">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="08cc1-237">Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-237">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="08cc1-238">Überprüfen Sie die Einstellungen, und wählen Sie **"Weiter"** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-238">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="08cc1-239">Nachdem die Richtlinie erstellt wurde, **schließen Sie**.</span><span class="sxs-lookup"><span data-stu-id="08cc1-239">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="08cc1-240">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="08cc1-240">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="08cc1-241">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle widersprüchlichen Gruppenrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-241">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="08cc1-242">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](https://technet.microsoft.com/library/cc731212.aspx), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-242">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="08cc1-243">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-243">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="08cc1-244">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Microsoft Defender Exploit Guard**  >  **Attack Surface Reduction.**</span><span class="sxs-lookup"><span data-stu-id="08cc1-244">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="08cc1-245">Wählen Sie **"Attack Surface Reduction"-Regeln konfigurieren** und **"Aktiviert"** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-245">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="08cc1-246">Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt "Optionen" festlegen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-246">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="08cc1-247">Wählen Sie **"Anzeigen" aus,** und geben Sie die Regel-ID in der Spalte **"Wertname"** und den ausgewählten Status in der Spalte **"Wert"** wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="08cc1-247">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="08cc1-248">0 : Deaktivieren (Asr-Regel deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="08cc1-248">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="08cc1-249">1 : Blockieren (ASR-Regel aktivieren)</span><span class="sxs-lookup"><span data-stu-id="08cc1-249">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="08cc1-250">2 : Überwachung (Bewerten, wie sich die ASR-Regel bei Aktivierung auf Ihre Organisation auswirken würde)</span><span class="sxs-lookup"><span data-stu-id="08cc1-250">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="08cc1-251">6 : Warnen (Aktivieren der ASR-Regel, aber Zulassen, dass der Endbenutzer den Block umgeht)</span><span class="sxs-lookup"><span data-stu-id="08cc1-251">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-Regeln in Gruppenrichtlinien":::

5. <span data-ttu-id="08cc1-253">Um Dateien und Ordner von ASR-Regeln auszuschließen, wählen Sie die Einstellung **"Dateien und Pfade aus Attack Surface Reduction"-Regeln ausschließen aus,** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="08cc1-253">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="08cc1-254">Wählen Sie **"Anzeigen"** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **"Wertname"** ein.</span><span class="sxs-lookup"><span data-stu-id="08cc1-254">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="08cc1-255">Geben Sie 0 in die **Spalte Wert** für jedes Element ein. </span><span class="sxs-lookup"><span data-stu-id="08cc1-255">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="08cc1-256">Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte mit dem **Wertnamen** noch für die **Spalte Value** unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="08cc1-256">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="08cc1-257">PowerShell</span><span class="sxs-lookup"><span data-stu-id="08cc1-257">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="08cc1-258">Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle widersprüchlichen PowerShell-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-258">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="08cc1-259">Damit Benutzer den Wert mithilfe von PowerShell definieren können, verwenden Sie die Option "Benutzerdefiniert" für die Regel in der Verwaltungsplattform.</span><span class="sxs-lookup"><span data-stu-id="08cc1-259">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="08cc1-260">Geben Sie **powershell** in die Menü "Start" ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **"Als Administrator ausführen"** aus.</span><span class="sxs-lookup"><span data-stu-id="08cc1-260">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="08cc1-261">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="08cc1-261">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="08cc1-262">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cc1-262">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="08cc1-263">Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Warnmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cc1-263">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="08cc1-264">Verwenden Sie das folgende Cmdlet, um den ASR-Blockierungsfehler von gefährdeten signierten Treibern zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cc1-264">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="08cc1-265">Verwenden Sie das folgende Cmdlet, um ASR-Regeln zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cc1-265">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="08cc1-266">Sie müssen den Status für jede Regel einzeln angeben, aber Sie können Regeln und Zustände in einer durch Trennzeichen getrennten Liste kombinieren.</span><span class="sxs-lookup"><span data-stu-id="08cc1-266">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="08cc1-267">Im folgenden Beispiel werden die ersten beiden Regeln aktiviert, die dritte Regel deaktiviert, und die vierte Regel wird im Überwachungsmodus aktiviert:</span><span class="sxs-lookup"><span data-stu-id="08cc1-267">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="08cc1-268">Sie können auch das `Add-MpPreference` PowerShell-Verb verwenden, um der vorhandenen Liste neue Regeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-268">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="08cc1-269">`Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln.</span><span class="sxs-lookup"><span data-stu-id="08cc1-269">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="08cc1-270">Wenn Sie dem vorhandenen Satz hinzufügen möchten, verwenden Sie `Add-MpPreference` stattdessen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-270">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="08cc1-271">Sie können eine Liste der Regeln und deren aktuellen Status abrufen, indem Sie `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="08cc1-271">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="08cc1-272">Verwenden Sie das folgende Cmdlet, um Dateien und Ordner von ASR-Regeln auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="08cc1-272">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="08cc1-273">Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Dateien und Ordner hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="08cc1-273">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="08cc1-274">Dient `Add-MpPreference` zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="08cc1-274">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="08cc1-275">Mithilfe des `Set-MpPreference` Cmdlets wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="08cc1-275">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="08cc1-276">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="08cc1-276">Related articles</span></span>

- [<span data-ttu-id="08cc1-277">Reduzieren von Angriffsflächen mit Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="08cc1-277">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="08cc1-278">Auswerten der Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="08cc1-278">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="08cc1-279">Häufig gestellte Fragen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="08cc1-279">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
