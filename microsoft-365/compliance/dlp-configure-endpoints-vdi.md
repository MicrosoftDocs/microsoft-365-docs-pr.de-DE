---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Stellen Sie das Konfigurationspaket auf einem Virtuellen Desktopinfrastrukturgerät (Virtual Desktop Infrastructure, VDI) so sicher, dass es in den Microsoft 365 Endpoint Data Loss Prevention Service (Verhinderung von Datenverlust) onboardiert wird.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917951"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e5670-103">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="e5670-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="e5670-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e5670-104">**Applies to:**</span></span>
- [<span data-ttu-id="e5670-105">Microsoft 365 Endpoint Data Loss Prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="e5670-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="e5670-106">Virtual Desktop Infrastructure (VDI)-Geräte</span><span class="sxs-lookup"><span data-stu-id="e5670-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="e5670-107">Microsoft 365 Endpoint-Unterstützung zur Verhinderung von Datenverlust für Windows Virtual Desktop unterstützt Einzelne Sitzungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="e5670-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="e5670-108">Szenarien mit mehreren Sitzungen auf Windows Virtual Desktop werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5670-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="e5670-109">Onboarding von VDI-Geräten</span><span class="sxs-lookup"><span data-stu-id="e5670-109">Onboard VDI devices</span></span>

<span data-ttu-id="e5670-110">Microsoft 365 Endpoint Data Loss Prevention unterstützt nicht persistentes VDI-Sitzungs-Onboarding.</span><span class="sxs-lookup"><span data-stu-id="e5670-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="e5670-111">Um nicht persistente VDI-Sitzungen zu integrieren, müssen sich VDI-Geräte unter Windows 10 1809 oder höher benennen.</span><span class="sxs-lookup"><span data-stu-id="e5670-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="e5670-112">Beim Onboarding von VDIs kann es zu herausforderungen kommen.</span><span class="sxs-lookup"><span data-stu-id="e5670-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="e5670-113">Es folgen typische Herausforderungen für dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="e5670-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="e5670-114">Sofortiges frühzeitiges Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Microsoft 365 Endpoint Data Loss Prevention (Verhinderung von Datenverlust) onboardiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e5670-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="e5670-115">Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="e5670-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="e5670-116">VDI-Geräte können im Microsoft 365 Compliance Center wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e5670-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="e5670-117">Einzelner Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="e5670-117">Single entry for each device.</span></span>  
<span data-ttu-id="e5670-118">Beachten Sie, dass  in diesem Fall derselbe Gerätename beim Erstellen der Sitzung konfiguriert werden muss, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="e5670-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="e5670-119">Mehrere Einträge für jedes Gerät – einer für jede Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e5670-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="e5670-120">Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und zeigen Schritte für einzelne und mehrere Einträge an.</span><span class="sxs-lookup"><span data-stu-id="e5670-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="e5670-121">In Umgebungen mit geringen Ressourcenkonfigurationen kann das Onboarding der Verhinderung von Datenverlust in Microsoft 365 Endpoint durch die VDI-Startprozedur verlangsamt werden.</span><span class="sxs-lookup"><span data-stu-id="e5670-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="e5670-122">Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets (*DeviceCompliancePackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="e5670-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="e5670-123">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte onboarding**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="e5670-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="e5670-124">Wählen Sie **im Feld Bereitstellungsmethode** die Option **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="e5670-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="e5670-125">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5670-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="e5670-126">Kopieren Sie die Dateien aus dem Ordner DeviceCompliancePackage aus der ZIP-Datei in das Bild `golden/master` unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="e5670-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="e5670-127">Wenn Sie keinen einzigen Eintrag für jedes Gerät implementieren, kopieren Sie DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e5670-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="e5670-128">Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie Onboard-NonPersistentMachine.ps1 deviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e5670-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5670-129">Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, wird er möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="e5670-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="e5670-130">Sie müssen die Option  Ausgeblendete Dateien und Ordner anzeigen im Datei-Explorer auswählen.</span><span class="sxs-lookup"><span data-stu-id="e5670-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="e5670-131">Öffnen Sie ein Fenster des Editors für lokale Gruppenrichtlinien, und navigieren Sie zu **Computerkonfiguration**  >  **Windows-Einstellungen**  >  **Skripts**  >  **starten**.</span><span class="sxs-lookup"><span data-stu-id="e5670-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5670-132">Domänengruppenrichtlinien können auch zum Onboarding nicht persistenter VDI-Geräte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5670-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="e5670-133">Führen Sie in Abhängigkeit von der Methode, die Sie implementieren möchten, die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e5670-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="e5670-134">**Für einzelnen Eintrag für jedes Gerät**</span><span class="sxs-lookup"><span data-stu-id="e5670-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="e5670-135">Wählen Sie **die Registerkarte PowerShell-Skripts** aus, und klicken Sie dann auf Hinzufügen **(Windows** Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="e5670-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e5670-136">Navigieren Sie zum Onboarding des PowerShell-Skripts `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e5670-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="e5670-137">**Für mehrere Einträge für jedes Gerät:**</span><span class="sxs-lookup"><span data-stu-id="e5670-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="e5670-138">Wählen Sie **die Registerkarte Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt im Pfad geöffnet, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="e5670-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e5670-139">Navigieren Sie zum Onboarding-Bash-Skript `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="e5670-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="e5670-140">Testen Sie Ihre Lösung:</span><span class="sxs-lookup"><span data-stu-id="e5670-140">Test your solution:</span></span>

   1. <span data-ttu-id="e5670-141">Erstellen Sie einen Pool mit einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="e5670-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="e5670-142">Bei Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="e5670-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="e5670-143">Abmelden vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="e5670-143">Logoff from device.</span></span>

   1. <span data-ttu-id="e5670-144">Bei einem anderen Benutzer am Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="e5670-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="e5670-145">**Für einen einzelnen Eintrag für jedes Gerät:** Überprüfen Sie nur einen Eintrag im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="e5670-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="e5670-146">**Für mehrere Einträge für jedes Gerät:** Überprüfen Sie mehrere Einträge im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="e5670-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="e5670-147">Klicken **Sie im** Navigationsbereich auf Geräteliste.</span><span class="sxs-lookup"><span data-stu-id="e5670-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="e5670-148">Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **Gerät als** Suchtyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="e5670-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="e5670-149">Aktualisieren von nicht persistenten VDI-Images (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e5670-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="e5670-150">Als bewährte Methode wird die Verwendung von Offlinewartungstools zum Patchen von Golden/Master-Images empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e5670-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="e5670-151">Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Image offline bleibt:</span><span class="sxs-lookup"><span data-stu-id="e5670-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="e5670-152">Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="e5670-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="e5670-153">Ändern eines Windows-Images mithilfe von DISM</span><span class="sxs-lookup"><span data-stu-id="e5670-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="e5670-154">DISM Image Management Command-Line Optionen</span><span class="sxs-lookup"><span data-stu-id="e5670-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="e5670-155">Verringern der Größe des Komponentenspeichers in einem Offline-Windows-Image</span><span class="sxs-lookup"><span data-stu-id="e5670-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="e5670-156">Wenn die Offlinewartung keine praktikable Option für Ihre nicht persistente VDI-Umgebung ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintehigkeit sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="e5670-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="e5670-157">Führen Sie nach dem Start des Masterimages für die Onlinewartung oder das Patchen ein offboarding-Skript aus, um den Microsoft 365 Endpoint-Sensor zur Verhinderung von Datenverlust zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5670-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="e5670-158">Weitere Informationen finden Sie unter [Offboardgeräte mit einem lokalen Skript](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="e5670-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="e5670-159">Stellen Sie sicher, dass der Sensor angehalten wird, indem Sie den folgenden Befehl in einem CMD-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="e5670-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="e5670-160">Service des Images nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="e5670-160">Service the image as needed.</span></span>

4. <span data-ttu-id="e5670-161">Führen Sie die folgenden Befehle mit PsExec.exe (die heruntergeladen werden können, um die Inhalte des Cyberordners zu bereinigen, die der Sensor seit dem Start möglicherweise angesammelt https://download.sysinternals.com/files/PSTools.zip) hat:</span><span class="sxs-lookup"><span data-stu-id="e5670-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="e5670-162">Versiegeln Sie das Golden/Master-Bild wie gewohnt erneut.</span><span class="sxs-lookup"><span data-stu-id="e5670-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5670-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e5670-163">Related topics</span></span>
- [<span data-ttu-id="e5670-164">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e5670-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="e5670-165">Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e5670-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="e5670-166">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="e5670-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="e5670-167">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="e5670-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="e5670-168">Behandeln von Problemen mit dem Microsoft Defender Advanced Threat Protection-Onboarding</span><span class="sxs-lookup"><span data-stu-id="e5670-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)