---
title: Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)
description: Stellen Sie das Konfigurationspaket auf dem VDI-Gerät (Virtual Desktop Infrastructure) bereit, damit es in den Microsoft Defender für Endpunktdienst integriert ist.
keywords: Virtual Desktop Infrastructure (VDI)-Gerät konfigurieren, vdi, Geräteverwaltung, Microsoft Defender für Endpunkt konfigurieren, Endpunkte
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
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843210"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="61f07-104">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="61f07-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61f07-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="61f07-105">**Applies to:**</span></span>
- [<span data-ttu-id="61f07-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="61f07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61f07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61f07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="61f07-108">VDI-Geräte (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="61f07-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="61f07-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="61f07-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="61f07-110">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="61f07-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61f07-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="61f07-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="61f07-112">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="61f07-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="61f07-113">Defender für Endpunkt unterstützt das Onboarding von nicht persistenten VDI-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="61f07-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="61f07-114">Beim Onboarding von VDIs können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="61f07-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="61f07-115">Nachfolgend sind typische Herausforderungen für dieses Szenario aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="61f07-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="61f07-116">Sofortiges frühes Onboarding einer kurzlebigen Sitzung, die vor der tatsächlichen Bereitstellung in Defender für Endpunkt integriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="61f07-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="61f07-117">Der Gerätename wird in der Regel für neue Sitzungen wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="61f07-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="61f07-118">VDI-Geräte können im Defender für Endpunkt-Portal als eine der folgenden Optionen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="61f07-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="61f07-119">Einzelner Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="61f07-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="61f07-120">In diesem Fall muss *derselbe* Gerätename konfiguriert werden, wenn die Sitzung erstellt wird, z. B. mithilfe einer unbeaufsichtigten Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="61f07-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="61f07-121">Mehrere Einträge für jedes Gerät – einer für jede Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61f07-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="61f07-122">Die folgenden Schritte führen Sie durch das Onboarding von VDI-Geräten und heben die Schritte für einzelne und mehrere Einträge hervor.</span><span class="sxs-lookup"><span data-stu-id="61f07-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="61f07-123">In Umgebungen mit geringen Ressourcenkonfigurationen kann das VDI-Startverfahren das Onboarding des Defender für Endpunkt-Sensors verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="61f07-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="61f07-124">For Windows 10 or Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="61f07-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="61f07-125">Öffnen Sie das VDI-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="61f07-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="61f07-126">Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:</span><span class="sxs-lookup"><span data-stu-id="61f07-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="61f07-127">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="61f07-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="61f07-128">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="61f07-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="61f07-129">Wählen Sie im Feld **"Bereitstellungsmethode"** **VDI-Onboardingskripts für nicht persistente Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="61f07-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="61f07-130">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="61f07-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="61f07-131">Kopieren Sie die Dateien aus dem Ordner "WindowsDefenderATPOnboardingPackage", die aus der .zip-Datei extrahiert wurden, in das `golden/master` Bild unter dem `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` Pfad.</span><span class="sxs-lookup"><span data-stu-id="61f07-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="61f07-132">Wenn Sie keinen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie "WindowsDefenderATPOnboardingScript.cmd".</span><span class="sxs-lookup"><span data-stu-id="61f07-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="61f07-133">Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie sowohl Onboard-NonPersistentMachine.ps1 als auch WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="61f07-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61f07-134">Wenn der Ordner nicht angezeigt `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` wird, ist er möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="61f07-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="61f07-135">Sie müssen die Option **"Ausgeblendete Dateien und Ordner anzeigen"** im Datei-Explorer auswählen.</span><span class="sxs-lookup"><span data-stu-id="61f07-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="61f07-136">Öffnen Sie ein Lokales Gruppenrichtlinien-Editor-Fenster, und navigieren Sie zum Start von **Computerkonfiguration**  >  **Windows Einstellungen**  >  **Skripts.**  >  </span><span class="sxs-lookup"><span data-stu-id="61f07-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="61f07-137">Domänengruppenrichtlinien können auch für das Onboarding nicht persistenter VDI-Geräte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61f07-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="61f07-138">Je nachdem, welche Methode Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="61f07-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="61f07-139">Für einen einzelnen Eintrag für jedes Gerät:</span><span class="sxs-lookup"><span data-stu-id="61f07-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="61f07-140">Wählen Sie die Registerkarte **"PowerShell-Skripts"** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="61f07-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="61f07-141">Navigieren Sie zum Onboarding des PowerShell-Skripts. `Onboard-NonPersistentMachine.ps1`</span><span class="sxs-lookup"><span data-stu-id="61f07-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="61f07-142">Es ist nicht erforderlich, die andere Datei anzugeben, da sie automatisch ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="61f07-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="61f07-143">Für mehrere Einträge für jedes Gerät:</span><span class="sxs-lookup"><span data-stu-id="61f07-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="61f07-144">Wählen Sie die Registerkarte **"Skripts"** aus, und klicken Sie dann auf **"Hinzufügen"** (Windows Explorer direkt in dem Pfad geöffnet wird, in den Sie das Onboardingskript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="61f07-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="61f07-145">Navigieren Sie zum Onboarding-Bash-Skript. `WindowsDefenderATPOnboardingScript.cmd`</span><span class="sxs-lookup"><span data-stu-id="61f07-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="61f07-146">Testen Sie Ihre Lösung:</span><span class="sxs-lookup"><span data-stu-id="61f07-146">Test your solution:</span></span>

   1. <span data-ttu-id="61f07-147">Erstellen Sie einen Pool mit einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="61f07-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="61f07-148">Melden Sie sich am Gerät an.</span><span class="sxs-lookup"><span data-stu-id="61f07-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="61f07-149">Abmelden vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="61f07-149">Logoff from device.</span></span>

   1. <span data-ttu-id="61f07-150">Melden Sie sich mit einem anderen Benutzer am Gerät an.</span><span class="sxs-lookup"><span data-stu-id="61f07-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="61f07-151">Je nachdem, welche Methode Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="61f07-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="61f07-152">Für einen einzelnen Eintrag für jedes Gerät:</span><span class="sxs-lookup"><span data-stu-id="61f07-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="61f07-153">Überprüfen Sie nur einen Eintrag in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="61f07-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="61f07-154">Für mehrere Einträge für jedes Gerät:</span><span class="sxs-lookup"><span data-stu-id="61f07-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="61f07-155">Überprüfen Sie mehrere Einträge in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="61f07-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="61f07-156">Klicken Sie im Navigationsbereich auf **"Geräteliste".**</span><span class="sxs-lookup"><span data-stu-id="61f07-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="61f07-157">Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und **"Gerät"** als Suchtyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="61f07-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="61f07-158">Für Vorgänger-SKUs</span><span class="sxs-lookup"><span data-stu-id="61f07-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="61f07-159">Die folgende Registrierung ist nur relevant, wenn das Ziel darin besteht, einen "einzelnen Eintrag für jedes Gerät" zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="61f07-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="61f07-160">Legen Sie den Registrierungswert auf:</span><span class="sxs-lookup"><span data-stu-id="61f07-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="61f07-161">oder mithilfe der Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="61f07-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="61f07-162">Folgen Sie dem [Server-Onboarding-Prozess.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="61f07-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="61f07-163">Aktualisieren von VDI-Images (Non-Persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="61f07-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="61f07-164">Als bewährte Methode empfehlen wir die Verwendung von Offlinewartungstools zum Patchen von goldenen/Master-Images.</span><span class="sxs-lookup"><span data-stu-id="61f07-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="61f07-165">Sie können z. B. die folgenden Befehle verwenden, um ein Update zu installieren, während das Bild offline bleibt:</span><span class="sxs-lookup"><span data-stu-id="61f07-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="61f07-166">Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="61f07-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="61f07-167">Ändern eines Windows-Images mithilfe von DISM</span><span class="sxs-lookup"><span data-stu-id="61f07-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="61f07-168">DISM-Imageverwaltung Command-Line Optionen</span><span class="sxs-lookup"><span data-stu-id="61f07-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="61f07-169">Verringern der Größe der Komponente Store in einem Offline-Windows-Image</span><span class="sxs-lookup"><span data-stu-id="61f07-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="61f07-170">Wenn die Offlinewartung für Ihre nicht persistente VDI-Umgebung keine geeignete Option ist, sollten die folgenden Schritte ausgeführt werden, um Konsistenz und Sensorintegrität sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="61f07-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="61f07-171">Führen Sie nach dem Start des Masterimages für online servicing or patching ein Offboarding-Skript aus, um den Defender für Endpunkt-Sensor zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="61f07-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="61f07-172">Weitere Informationen finden Sie unter [Offboarding von Geräten mithilfe eines lokalen Skripts.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="61f07-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="61f07-173">Stellen Sie sicher, dass der Sensor beendet wird, indem Sie den folgenden Befehl in einem CMD-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="61f07-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="61f07-174">Dienst das Image nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="61f07-174">Service the image as needed.</span></span>

4. <span data-ttu-id="61f07-175">Führen Sie die folgenden Befehle mit PsExec.exe aus (die heruntergeladen werden https://download.sysinternals.com/files/PSTools.zip) können, um die Inhalte des Cyberordners zu bereinigen, die der Sensor seit dem Start möglicherweise angesammelt hat:</span><span class="sxs-lookup"><span data-stu-id="61f07-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="61f07-176">Versiegeln Sie das Gold-Master-Bild erneut wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="61f07-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61f07-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="61f07-177">Related topics</span></span>
- [<span data-ttu-id="61f07-178">Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="61f07-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="61f07-179">Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="61f07-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="61f07-180">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="61f07-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="61f07-181">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="61f07-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="61f07-182">Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten</span><span class="sxs-lookup"><span data-stu-id="61f07-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
