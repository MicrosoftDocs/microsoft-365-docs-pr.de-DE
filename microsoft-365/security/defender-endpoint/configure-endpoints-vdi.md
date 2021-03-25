---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
description: Stellen Sie das Konfigurationspaket auf einem Virtuellen Desktopinfrastrukturgerät (Virtual Desktop Infrastructure, VDI) so sicher, dass es in Microsoft Defender ATP den Dienst integrierte.
keywords: Konfigurieren von Virtual Desktop Infrastructure (VDI)-Geräten, vdi, Geräteverwaltung, Konfigurieren von Windows ATP-Endpunkten, Konfigurieren von Microsoft Defender für Endpunkte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 167db9b5da841528e95f167b3af6a840b6c71eb4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165561"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="40b11-104">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="40b11-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40b11-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="40b11-105">**Applies to:**</span></span>
- [<span data-ttu-id="40b11-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="40b11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40b11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40b11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="40b11-108">Virtual Desktop Infrastructure (VDI)-Geräte</span><span class="sxs-lookup"><span data-stu-id="40b11-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="40b11-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="40b11-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="40b11-110">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="40b11-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="40b11-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="40b11-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="40b11-112">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="40b11-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="40b11-113">Defender for Endpoint unterstützt das nicht persistente Onboarding von VDI-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="40b11-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="40b11-114">Beim Onboarding von VDIs kann es zu herausforderungen kommen.</span><span class="sxs-lookup"><span data-stu-id="40b11-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="40b11-115">Es folgen typische Herausforderungen für dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="40b11-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="40b11-116">Sofortiges frühzeitiges Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Defender for Endpoint onboardiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="40b11-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="40b11-117">Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="40b11-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="40b11-118">VDI-Geräte können im Defender for Endpoint-Portal wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="40b11-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="40b11-119">Einzelner Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="40b11-119">Single entry for each device.</span></span>  
<span data-ttu-id="40b11-120">Beachten Sie, dass  in diesem Fall derselbe Gerätename beim Erstellen der Sitzung konfiguriert werden muss, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="40b11-120">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="40b11-121">Mehrere Einträge für jedes Gerät – einer für jede Sitzung.</span><span class="sxs-lookup"><span data-stu-id="40b11-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="40b11-122">Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und zeigen Schritte für einzelne und mehrere Einträge an.</span><span class="sxs-lookup"><span data-stu-id="40b11-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="40b11-123">In Umgebungen mit geringen Ressourcenkonfigurationen kann das Onboarding des Defender for Endpoint-Sensors durch die VDI-Startprozedur verlangsamt werden.</span><span class="sxs-lookup"><span data-stu-id="40b11-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="40b11-124">Für Windows 10 oder Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="40b11-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="40b11-125">Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="40b11-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="40b11-126">Sie können das Paket auch über [das Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="40b11-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="40b11-127">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="40b11-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="40b11-128">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="40b11-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="40b11-129">Wählen Sie **im Feld Bereitstellungsmethode** die Option **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="40b11-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="40b11-130">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="40b11-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="40b11-131">Kopieren Sie die Dateien aus dem Ordner WindowsDefenderATPOnboardingPackage aus der ZIP-Datei in das Bild `golden/master` unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="40b11-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="40b11-132">Wenn Sie keinen einzigen Eintrag für jedes Gerät implementieren, kopieren Sie WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="40b11-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="40b11-133">Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie Onboard-NonPersistentMachine.ps1 windowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="40b11-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40b11-134">Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, wird er möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="40b11-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="40b11-135">Sie müssen die Option  Ausgeblendete Dateien und Ordner anzeigen im Datei-Explorer auswählen.</span><span class="sxs-lookup"><span data-stu-id="40b11-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="40b11-136">Öffnen Sie ein Fenster des Editors für lokale Gruppenrichtlinien, und navigieren Sie zu **Computerkonfiguration**  >  **Windows-Einstellungen**  >  **Skripts**  >  **starten**.</span><span class="sxs-lookup"><span data-stu-id="40b11-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40b11-137">Domänengruppenrichtlinien können auch zum Onboarding nicht persistenter VDI-Geräte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40b11-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="40b11-138">Führen Sie in Abhängigkeit von der Methode, die Sie implementieren möchten, die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="40b11-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span> <br>
   <span data-ttu-id="40b11-139">**Für einen einzelnen Eintrag für jedes Gerät:**</span><span class="sxs-lookup"><span data-stu-id="40b11-139">**For single entry for each device**:</span></span><br>
   
   <span data-ttu-id="40b11-140">Wählen Sie **die Registerkarte PowerShell-Skripts** aus, und klicken Sie dann auf Hinzufügen **(Windows** Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="40b11-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="40b11-141">Navigieren Sie zum Onboarding des PowerShell-Skripts `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="40b11-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="40b11-142">**Für mehrere Einträge für jedes Gerät:**</span><span class="sxs-lookup"><span data-stu-id="40b11-142">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="40b11-143">Wählen Sie **die Registerkarte Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="40b11-143">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="40b11-144">Navigieren Sie zum Onboarding-Bash-Skript `WindowsDefenderATPOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="40b11-144">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="40b11-145">Testen Sie Ihre Lösung:</span><span class="sxs-lookup"><span data-stu-id="40b11-145">Test your solution:</span></span>

   1. <span data-ttu-id="40b11-146">Erstellen Sie einen Pool mit einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="40b11-146">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="40b11-147">Bei Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="40b11-147">Logon to device.</span></span>
      
   1. <span data-ttu-id="40b11-148">Abmelden vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="40b11-148">Logoff from device.</span></span>

   1. <span data-ttu-id="40b11-149">Bei einem anderen Benutzer am Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="40b11-149">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="40b11-150">**Für einen einzelnen Eintrag für jedes Gerät:** Überprüfen Sie nur einen Eintrag im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="40b11-150">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="40b11-151">**Für mehrere Einträge für jedes Gerät:** Überprüfen Sie mehrere Einträge im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="40b11-151">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="40b11-152">Klicken **Sie im** Navigationsbereich auf Geräteliste.</span><span class="sxs-lookup"><span data-stu-id="40b11-152">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="40b11-153">Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **Gerät als** Suchtyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="40b11-153">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="40b11-154">Für skUs auf Abwärtsebene</span><span class="sxs-lookup"><span data-stu-id="40b11-154">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="40b11-155">Die folgende Registrierung ist nur relevant, wenn es darum geht, einen "einzelnen Eintrag für jedes Gerät" zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="40b11-155">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="40b11-156">Legen Sie den Registrierungswert auf:</span><span class="sxs-lookup"><span data-stu-id="40b11-156">Set registry value to:</span></span>

    ```reg
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="40b11-157">oder verwenden Sie die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="40b11-157">or using command line:</span></span>

    ```
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="40b11-158">Folgen Sie [dem Server-Onboarding-Prozess.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="40b11-158">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="40b11-159">Aktualisieren von nicht persistenten VDI-Images (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="40b11-159">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="40b11-160">Als bewährte Methode wird die Verwendung von Offlinewartungstools zum Patchen von Golden/Master-Images empfohlen.</span><span class="sxs-lookup"><span data-stu-id="40b11-160">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="40b11-161">Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Image offline bleibt:</span><span class="sxs-lookup"><span data-stu-id="40b11-161">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="40b11-162">Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="40b11-162">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="40b11-163">Ändern eines Windows-Images mithilfe von DISM</span><span class="sxs-lookup"><span data-stu-id="40b11-163">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="40b11-164">DISM Image Management Command-Line Optionen</span><span class="sxs-lookup"><span data-stu-id="40b11-164">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="40b11-165">Verringern der Größe des Komponentenspeichers in einem Offline-Windows-Image</span><span class="sxs-lookup"><span data-stu-id="40b11-165">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="40b11-166">Wenn die Offlinewartung keine praktikable Option für Ihre nicht persistente VDI-Umgebung ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintehigkeit sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="40b11-166">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="40b11-167">Führen Sie nach dem Start des Masterimages für die Onlinewartung oder das Patchen ein offboarding-Skript aus, um den Defender for Endpoint-Sensor zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="40b11-167">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="40b11-168">Weitere Informationen finden Sie unter [Offboardgeräte mit einem lokalen Skript](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="40b11-168">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="40b11-169">Stellen Sie sicher, dass der Sensor angehalten wird, indem Sie den folgenden Befehl in einem CMD-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="40b11-169">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="40b11-170">Service des Images nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="40b11-170">Service the image as needed.</span></span>

4. <span data-ttu-id="40b11-171">Führen Sie die folgenden Befehle mit PsExec.exe (die heruntergeladen werden können, um die Inhalte des Cyberordners zu bereinigen, die der Sensor seit dem Start möglicherweise angesammelt https://download.sysinternals.com/files/PSTools.zip) hat:</span><span class="sxs-lookup"><span data-stu-id="40b11-171">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="40b11-172">Versiegeln Sie das Golden/Master-Bild wie gewohnt erneut.</span><span class="sxs-lookup"><span data-stu-id="40b11-172">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40b11-173">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="40b11-173">Related topics</span></span>
- [<span data-ttu-id="40b11-174">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="40b11-174">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="40b11-175">Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40b11-175">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="40b11-176">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="40b11-176">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="40b11-177">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="40b11-177">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="40b11-178">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="40b11-178">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
