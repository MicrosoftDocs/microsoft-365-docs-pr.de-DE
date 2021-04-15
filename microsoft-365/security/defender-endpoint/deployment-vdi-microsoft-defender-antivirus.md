---
title: Bereitstellungshandbuch für die Bereitstellung von Microsoft Defender Antivirus Virtual Desktop Infrastructure
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus in einer virtuellen Desktopumgebung bereitstellen, um eine optimale Balance zwischen Schutz und Leistung zu erzielen.
keywords: vdi, hyper-v, vm, virtual machine, windows defender, antivirus, av, virtual desktop, rds, remote desktop
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: fed66586dc0607989e407ecd790d2af8c40e2939
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765731"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="f835b-104">Bereitstellungshandbuch für Microsoft Defender Antivirus in einer Virtuellen Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI)-Umgebung</span><span class="sxs-lookup"><span data-stu-id="f835b-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f835b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f835b-105">**Applies to:**</span></span>

- [<span data-ttu-id="f835b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f835b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f835b-107">Zusätzlich zu den standardmäßigen lokalen oder Hardwarekonfigurationen können Sie Microsoft Defender Antivirus auch in einer Remotedesktopumgebung (RDS) oder einer virtuellen Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f835b-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="f835b-108">Weitere Informationen zur Unterstützung von Microsoft Remote Desktop Services und VDI finden Sie in der Dokumentation zu Windows [Virtual Desktop.](/azure/virtual-desktop)</span><span class="sxs-lookup"><span data-stu-id="f835b-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="f835b-109">Informationen zu azurebasierten virtuellen Computern finden Sie unter [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="f835b-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="f835b-110">Mit der Möglichkeit, Updates auf VMs, die in VDIs ausgeführt werden, einfach bereitstellen zu können, haben wir dieses Handbuch verkürzt, um uns darauf zu konzentrieren, wie Sie Updates auf Ihren Computern schnell und einfach erhalten können.</span><span class="sxs-lookup"><span data-stu-id="f835b-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="f835b-111">Sie müssen keine goldenen Bilder mehr regelmäßig erstellen und versiegeln, da Updates in ihre Komponentenbits auf dem Hostserver erweitert und dann direkt auf den virtuellen Computer heruntergeladen werden, wenn er aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f835b-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="f835b-112">In diesem Handbuch wird beschrieben, wie Sie Ihre virtuellen Computer für optimalen Schutz und optimale Leistung konfigurieren. Dazu gehören u. a.:</span><span class="sxs-lookup"><span data-stu-id="f835b-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="f835b-113">Einrichten einer dedizierten VDI-Dateifreigabe für Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="f835b-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="f835b-114">Randomisieren geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="f835b-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="f835b-115">Verwenden von Schnellscans</span><span class="sxs-lookup"><span data-stu-id="f835b-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="f835b-116">Verhindern von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f835b-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="f835b-117">Deaktivieren von Scans nach jedem Update</span><span class="sxs-lookup"><span data-stu-id="f835b-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="f835b-118">Überprüfen veralteter Computer oder Computer, die eine Weile offline waren</span><span class="sxs-lookup"><span data-stu-id="f835b-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="f835b-119">Anwenden von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="f835b-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="f835b-120">Sie können auch das Whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)herunterladen, das sich mit dem neuen Feature für das Update der gemeinsamen Sicherheitsintelligenz sowie mit Leistungstests und Anleitungen zum Testen der Antivirusleistung in Ihrem eigenen VDI beschäftigt.</span><span class="sxs-lookup"><span data-stu-id="f835b-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f835b-121">Obwohl der VDI auf Windows Server 2012 oder Windows Server 2016 gehostet werden kann, sollten auf den virtuellen Computern (VMs) mindestens Windows 10, 1607, ausgeführt werden, da höhere Schutztechnologien und Features in früheren Versionen von Windows nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f835b-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="f835b-122">Es gibt Leistungs- und Funktionsverbesserungen bei der Art und Weise, wie Microsoft Defender AV auf virtuellen Computern in Windows 10 Insider Preview, Build 18323 (und höher) arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f835b-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="f835b-123">Wir identifizieren in diesem Handbuch, ob Sie einen Insider #A0 verwenden müssen. Wenn sie nicht angegeben ist, ist windows 10 1607 die mindestens erforderliche Version für den besten Schutz und die beste Leistung.</span><span class="sxs-lookup"><span data-stu-id="f835b-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="f835b-124">Einrichten einer dedizierten VDI-Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="f835b-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="f835b-125">In Windows 10, Version 1903, haben wir das Feature für gemeinsame Sicherheitsintelligenz eingeführt, das das Auspacken heruntergeladener Sicherheitsintelligenzupdates auf einen Hostcomputer auslädt, wodurch frühere CPU-, Datenträger- und Arbeitsspeicherressourcen auf einzelnen Computern gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="f835b-126">Dieses Feature wurde zurückportiert und funktioniert jetzt in Windows 10, Version 1703 und höher.</span><span class="sxs-lookup"><span data-stu-id="f835b-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="f835b-127">Sie können dieses Feature mit einer Gruppenrichtlinie oder PowerShell festlegen.</span><span class="sxs-lookup"><span data-stu-id="f835b-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="f835b-128">Verwenden Sie Gruppenrichtlinien, um das Feature für gemeinsame Sicherheit in der Sicherheitsintelligenz zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f835b-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="f835b-129">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die Gruppenrichtlinienverwaltungskonsole, klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f835b-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="f835b-130">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f835b-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="f835b-131">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="f835b-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="f835b-132">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="f835b-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="f835b-133">Doppelklicken Sie **auf Speicherort der Sicherheitsintelligenz für VDI-Clients definieren,** und legen Sie dann die Option auf **Aktiviert fest.**</span><span class="sxs-lookup"><span data-stu-id="f835b-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="f835b-134">Ein Feld wird automatisch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f835b-134">A field automatically appears.</span></span>

6. <span data-ttu-id="f835b-135">Geben `\\<sharedlocation\>\wdav-update` Sie ein (Hilfe zu diesem Wert finden Sie unter [Herunterladen und Auspacken](#download-and-unpackage-the-latest-updates)).</span><span class="sxs-lookup"><span data-stu-id="f835b-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="f835b-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f835b-136">Click **OK**.</span></span>

8. <span data-ttu-id="f835b-137">Stellen Sie das Gruppenrichtlinienobjekt auf den virtuellen Computer, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="f835b-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="f835b-138">Verwenden von PowerShell zum Aktivieren des Features für gemeinsame Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="f835b-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="f835b-139">Verwenden Sie das folgende Cmdlet, um das Feature zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f835b-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="f835b-140">Sie müssen dies dann pushen, da Sie normalerweise PowerShell-basierte Konfigurationsrichtlinien auf die virtuellen Computer pushen würden:</span><span class="sxs-lookup"><span data-stu-id="f835b-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="f835b-141">Informationen dazu [finden](#download-and-unpackage-the-latest-updates) Sie im Abschnitt Herunterladen und \<shared location\> Entpacken.</span><span class="sxs-lookup"><span data-stu-id="f835b-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="f835b-142">Herunterladen und Entpacken der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="f835b-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="f835b-143">Jetzt können Sie mit dem Herunterladen und Installieren neuer Updates beginnen.</span><span class="sxs-lookup"><span data-stu-id="f835b-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="f835b-144">Wir haben unten ein PowerShell-Beispielskript für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="f835b-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="f835b-145">Dieses Skript ist die einfachste Möglichkeit, neue Updates herunterzuladen und für Ihre virtuellen Computer zu bereiten.</span><span class="sxs-lookup"><span data-stu-id="f835b-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="f835b-146">Anschließend sollten Sie festlegen, dass das Skript zu einem bestimmten Zeitpunkt auf dem Verwaltungscomputer mithilfe einer geplanten Aufgabe ausgeführt wird (oder Wenn Sie mit der Verwendung von PowerShell-Skripts in Azure, Intune oder SCCM vertraut sind, können Sie diese Skripts auch verwenden).</span><span class="sxs-lookup"><span data-stu-id="f835b-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="f835b-147">Sie können festlegen, dass ein geplanter Vorgang einmal täglich ausgeführt wird, sodass die virtuellen Computer das neue Update erhalten, wenn das Paket heruntergeladen und entpackt wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="f835b-148">Wir empfehlen, einmal am Tag zu beginnen. Sie sollten jedoch mit dem Erhöhen oder Verringern der Häufigkeit experimentieren, um die Auswirkungen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="f835b-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="f835b-149">Security Intelligence-Pakete werden in der Regel alle drei bis vier Stunden veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f835b-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="f835b-150">Das Festlegen einer Häufigkeit von weniger als vier Stunden wird nicht empfohlen, da dadurch der Netzwerkaufwand auf Dem Verwaltungscomputer ohne Nutzen erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="f835b-151">Festlegen eines geplanten Vorgangs zum Ausführen des PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="f835b-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="f835b-152">Öffnen Sie auf dem Verwaltungscomputer das Menü Start, und geben Sie **Task Scheduler ein.**</span><span class="sxs-lookup"><span data-stu-id="f835b-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="f835b-153">Öffnen Sie sie, und wählen **Sie Aufgabe erstellen... aus.**</span><span class="sxs-lookup"><span data-stu-id="f835b-153">Open it and select **Create task…**</span></span> <span data-ttu-id="f835b-154">auf der Seitenleiste.</span><span class="sxs-lookup"><span data-stu-id="f835b-154">on the side panel.</span></span>

2. <span data-ttu-id="f835b-155">Geben Sie den Namen als **Security Intelligence Unpacker ein.**</span><span class="sxs-lookup"><span data-stu-id="f835b-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="f835b-156">Wechseln Sie zur **Registerkarte Trigger.** Wählen **Sie Neu aus...**</span><span class="sxs-lookup"><span data-stu-id="f835b-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="f835b-157"> > **Täglich**, und wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="f835b-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="f835b-158">Wechseln Sie zur **Registerkarte Aktionen.** Wählen **Sie Neu aus...**</span><span class="sxs-lookup"><span data-stu-id="f835b-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="f835b-159">Geben **Sie PowerShell** in das **Feld Programm/Skript** ein.</span><span class="sxs-lookup"><span data-stu-id="f835b-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="f835b-160">Geben `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` Sie in das Feld Argumente **hinzufügen** ein.</span><span class="sxs-lookup"><span data-stu-id="f835b-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="f835b-161">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-161">Select **OK**.</span></span>

4. <span data-ttu-id="f835b-162">Sie können bei Wunsch zusätzliche Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f835b-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="f835b-163">Wählen **Sie OK** aus, um den geplanten Vorgang zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f835b-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="f835b-164">Sie können das Update manuell initiieren, indem Sie mit der rechten Maustaste auf die Aufgabe klicken und auf **Ausführen klicken.**</span><span class="sxs-lookup"><span data-stu-id="f835b-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="f835b-165">Manuelles Herunterladen und Entpacken</span><span class="sxs-lookup"><span data-stu-id="f835b-165">Download and unpackage manually</span></span>

<span data-ttu-id="f835b-166">Wenn Sie es vorziehen, alles manuell auszuführen, müssen Sie das Verhalten des Skripts replizieren:</span><span class="sxs-lookup"><span data-stu-id="f835b-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="f835b-167">Erstellen Sie einen neuen Ordner im Systemstamm, der zum Speichern von Nachrichtenupdates aufgerufen wird, z. B. `wdav_update` erstellen Sie den Ordner `c:\wdav_update` .</span><span class="sxs-lookup"><span data-stu-id="f835b-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="f835b-168">Erstellen eines Unterordners *unter wdav_update* mit einem GUID-Namen, z. B. `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="f835b-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="f835b-169">Hier ein Beispiel: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="f835b-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="f835b-170">Im Skript legen wir es so fest, dass die letzten 12 Ziffern der GUID das Jahr, den Monat, den Tag und die Uhrzeit sind, zu der die Datei heruntergeladen wurde, sodass jedes Mal ein neuer Ordner erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="f835b-171">Sie können dies so ändern, dass die Datei jedes Mal in denselben Ordner heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="f835b-172">Laden Sie ein Security Intelligence-Paket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  aus in den GUID-Ordner herunter.</span><span class="sxs-lookup"><span data-stu-id="f835b-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="f835b-173">Die Datei sollte den Namen `mpam-fe.exe` haben.</span><span class="sxs-lookup"><span data-stu-id="f835b-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="f835b-174">Öffnen Sie ein Cmd-Eingabeaufforderungsfenster, und navigieren Sie zu dem erstellten GUID-Ordner.</span><span class="sxs-lookup"><span data-stu-id="f835b-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="f835b-175">Verwenden Sie den /X-Extraktionsbefehl, um die Dateien zu extrahieren, z. B.  `mpam-fe.exe /X` .</span><span class="sxs-lookup"><span data-stu-id="f835b-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f835b-176">Die virtuellen Computer nehmen das aktualisierte Paket auf, wenn ein neuer GUID-Ordner mit einem extrahierten Updatepaket erstellt wird oder wenn ein vorhandener Ordner mit einem neuen extrahierten Paket aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="f835b-177">Randomisieren geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="f835b-177">Randomize scheduled scans</span></span>

<span data-ttu-id="f835b-178">Geplante Scans werden zusätzlich zu [Echtzeitschutz und -überprüfung ausgeführt.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f835b-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="f835b-179">Die Startzeit des Scans selbst basiert weiterhin auf der geplanten Scanrichtlinie (**ScheduleDay**, **ScheduleTime** und **ScheduleQuickScanTime**).</span><span class="sxs-lookup"><span data-stu-id="f835b-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="f835b-180">Die Randomisierung verursacht, dass Microsoft Defender Antivirus eine Überprüfung auf jedem Computer innerhalb eines 4-Stunden-Fensters ab dem Für die geplante Überprüfung festgelegten Zeitraum startet.</span><span class="sxs-lookup"><span data-stu-id="f835b-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="f835b-181">Weitere [Konfigurationsoptionen für](scheduled-catch-up-scans-microsoft-defender-antivirus.md) geplante Scans finden Sie unter Planen von Scans.</span><span class="sxs-lookup"><span data-stu-id="f835b-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="f835b-182">Verwenden von Schnellscans</span><span class="sxs-lookup"><span data-stu-id="f835b-182">Use quick scans</span></span>

<span data-ttu-id="f835b-183">Sie können den Typ der Überprüfung angeben, die während einer geplanten Überprüfung durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f835b-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="f835b-184">Schnelle Scans sind der bevorzugte Ansatz, da sie so konzipiert sind, dass sie an allen Stellen aussehen, an denen Schadsoftware gespeichert werden muss, um aktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="f835b-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="f835b-185">Im folgenden Verfahren wird das Einrichten von Schnellscans mithilfe von Gruppenrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f835b-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="f835b-186">Wechseln Sie im Gruppenrichtlinien-Editor zu **Administrative Vorlagen**  >  **Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="f835b-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="f835b-187">Wählen **Sie Den Scantyp angeben aus, der für eine geplante** Überprüfung verwendet werden soll, und bearbeiten Sie dann die Richtlinieneinstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f835b-188">Legen Sie die Richtlinie auf **Aktiviert**, und wählen Sie dann unter **Optionen** die Option **Schnellscan aus.**</span><span class="sxs-lookup"><span data-stu-id="f835b-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="f835b-189">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-189">Select **OK**.</span></span> 

5. <span data-ttu-id="f835b-190">Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="f835b-191">Verhindern von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f835b-191">Prevent notifications</span></span>

<span data-ttu-id="f835b-192">Manchmal können Microsoft Defender Antivirus-Benachrichtigungen an mehrere Sitzungen gesendet oder beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="f835b-193">Um dieses Problem zu minimieren, können Sie die Benutzeroberfläche von Microsoft Defender Antivirus sperren.</span><span class="sxs-lookup"><span data-stu-id="f835b-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="f835b-194">Im folgenden Verfahren wird beschrieben, wie Benachrichtigungen mit Gruppenrichtlinien unterdrückt werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="f835b-195">Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows-Komponenten**  >  **Microsoft Defender**  >  **Antivirus-Clientschnittstelle**.</span><span class="sxs-lookup"><span data-stu-id="f835b-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="f835b-196">Wählen **Sie Alle Benachrichtigungen unterdrücken** aus, und bearbeiten Sie dann die Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f835b-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="f835b-197">Legen Sie die Richtlinie auf **Aktiviert**, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="f835b-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="f835b-198">Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="f835b-199">Das Unterdrücken von Benachrichtigungen verhindert, dass Benachrichtigungen von Microsoft Defender Antivirus im Action Center unter Windows 10 angezeigt werden, wenn Scans durchgeführt oder Korrekturaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="f835b-200">Ihr Sicherheitsbetriebsteam sieht jedoch die Ergebnisse der Überprüfung im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="f835b-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="f835b-201">Gehen Sie wie folgt vor, um das Action Center unter Windows 10 zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="f835b-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="f835b-202">Wählen Sie am rechten Ende der Taskleiste das Symbol Aktionscenter aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="f835b-203">Drücken Sie die Windows-Logotaste + A.</span><span class="sxs-lookup"><span data-stu-id="f835b-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="f835b-204">Wischen Sie auf einem Touchscreengerät vom rechten Rand des Bildschirms ein.</span><span class="sxs-lookup"><span data-stu-id="f835b-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="f835b-205">Deaktivieren von Scans nach einem Update</span><span class="sxs-lookup"><span data-stu-id="f835b-205">Disable scans after an update</span></span>

<span data-ttu-id="f835b-206">Durch deaktivieren eines Scans nach einem Update wird verhindert, dass nach dem Empfang eines Updates eine Überprüfung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="f835b-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="f835b-207">Sie können diese Einstellung beim Erstellen des Basisimages anwenden, wenn Sie auch einen Schnellscan ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f835b-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="f835b-208">Auf diese Weise können Sie verhindern, dass der neu aktualisierte virtuelle Computer erneut eine Überprüfung durchführen kann (wie Sie ihn bereits beim Erstellen des Basisimages überprüft haben).</span><span class="sxs-lookup"><span data-stu-id="f835b-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f835b-209">Das Ausführen von Scans nach einem Update hilft Ihnen, sicherzustellen, dass Ihre virtuellen Computer mit den neuesten Security Intelligence-Updates geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="f835b-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="f835b-210">Wenn Sie diese Option deaktivieren, wird die Schutzstufe Ihrer virtuellen Computer reduziert und sollte nur beim ersten Erstellen oder Bereitstellen des Basisimages verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="f835b-211">Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="f835b-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="f835b-212">Wählen **Sie Scan aktivieren nach dem Update der Sicherheitsintelligenz aus,** und bearbeiten Sie dann die Richtlinieneinstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f835b-213">Legen Sie die Richtlinie auf **Deaktiviert .**</span><span class="sxs-lookup"><span data-stu-id="f835b-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="f835b-214">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-214">Select **OK**.</span></span>

5. <span data-ttu-id="f835b-215">Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="f835b-216">Diese Richtlinie verhindert, dass eine Überprüfung unmittelbar nach einem Update ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f835b-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="f835b-217">Überprüfen von virtuellen Computer, die offline waren</span><span class="sxs-lookup"><span data-stu-id="f835b-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="f835b-218">Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="f835b-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="f835b-219">Wählen **Sie Nachhol-Schnellscan aktivieren aus,** und bearbeiten Sie dann die Richtlinieneinstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f835b-220">Legen Sie die Richtlinie auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="f835b-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="f835b-221">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-221">Select **OK**.</span></span>

5. <span data-ttu-id="f835b-222">Stellen Sie Ihr Gruppenrichtlinienobjekt wie gewöhnlich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="f835b-223">Diese Richtlinie erzwingt eine Überprüfung, wenn der virtuelle Computer zwei oder mehr aufeinander folgende geplante Scans verpasst hat.</span><span class="sxs-lookup"><span data-stu-id="f835b-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="f835b-224">Aktivieren des kopflosen Benutzeroberflächenmodus</span><span class="sxs-lookup"><span data-stu-id="f835b-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="f835b-225">Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows-Komponenten**  >  **Microsoft Defender**  >  **Antivirus-Clientschnittstelle**.</span><span class="sxs-lookup"><span data-stu-id="f835b-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="f835b-226">Wählen **Sie Kopflose Benutzeroberflächenmodus aktivieren aus,** und bearbeiten Sie die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f835b-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="f835b-227">Legen Sie die Richtlinie auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="f835b-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="f835b-228">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f835b-228">Click **OK**.</span></span>

5. <span data-ttu-id="f835b-229">Stellen Sie Ihr Gruppenrichtlinienobjekt wie gewöhnlich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f835b-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="f835b-230">Diese Richtlinie blendet die gesamte Microsoft Defender Antivirus-Benutzeroberfläche vor Endbenutzern in Ihrer Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="f835b-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="f835b-231">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f835b-231">Exclusions</span></span>

<span data-ttu-id="f835b-232">Ausschlüsse können ihren Anforderungen entsprechend hinzugefügt, entfernt oder angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="f835b-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="f835b-233">Weitere Informationen finden Sie unter [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="f835b-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f835b-234">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f835b-234">Additional resources</span></span>

- [<span data-ttu-id="f835b-235">Tech Community Blog: Konfigurieren von Microsoft Defender Antivirus für nicht persistente VDI-Computer</span><span class="sxs-lookup"><span data-stu-id="f835b-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="f835b-236">TechNet-Foren zu Remotedesktopdiensten und VDI</span><span class="sxs-lookup"><span data-stu-id="f835b-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="f835b-237">SignatureDownloadCustomTask PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="f835b-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)