---
title: Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)
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
description: Stellen Sie das Konfigurationspaket auf dem VDI-Gerät (Virtual Desktop Infrastructure) so bereit, dass es auf dem Microsoft 365 Endpoint Data Loss Prevention-Dienst implementiert ist.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769416"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="7c6a5-103">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="7c6a5-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="7c6a5-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7c6a5-104">**Applies to:**</span></span>
- [<span data-ttu-id="7c6a5-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="7c6a5-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="7c6a5-106">VDI-Geräte (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="7c6a5-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="7c6a5-107">Microsoft 365 Endpoint Data Loss Prevention-Unterstützung für Windows Virtual Desktop unterstützt Szenarien für einzelne Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="7c6a5-108">Szenarien mit mehreren Sitzungen auf dem virtuellen Windows-Desktop werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="7c6a5-109">Onboard-VDI-Geräte</span><span class="sxs-lookup"><span data-stu-id="7c6a5-109">Onboard VDI devices</span></span>

<span data-ttu-id="7c6a5-110">Microsoft 365 Endpoint Data Loss Prevention unterstützt das Onboarding von nicht persistenten VDI-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="7c6a5-111">Um nicht persistente VDI-Sitzungen an Bord zu können, müssen sich VDI-Geräte auf Windows 10 1809 oder höher befinden.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="7c6a5-112">Beim Onboarding von VDIs kann es zu Problemen kommen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="7c6a5-113">Im folgenden werden typische Herausforderungen für dieses Szenario dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="7c6a5-114">Sofortiges frühes Onboarding einer kurzlebigen Sitzung, die vor der eigentlichen Einrichtung auf Microsoft 365-Endpunkt Verhinderung von Datenverlust onboarded sein muss.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="7c6a5-115">Der Gerätename wird normalerweise für neue Sitzungen wieder verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="7c6a5-116">VDI-Geräte können im Microsoft 365 Compliance Center als Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="7c6a5-117">Einzelner Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-117">Single entry for each device.</span></span>  
<span data-ttu-id="7c6a5-118">Beachten Sie, dass in diesem Fall *derselbe* Gerätename beim Erstellen der Sitzung konfiguriert werden muss, beispielsweise mithilfe einer unbeaufsichtigten Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="7c6a5-119">Mehrere Einträge für jedes Gerät – eins für jede Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="7c6a5-120">Die folgenden Schritte werden Sie durch das Onboarding von VDI-Geräten führen und die Schritte für einzelne und mehrere Einträge hervorheben.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="7c6a5-121">Bei Umgebungen mit niedrigen Ressourcen Konfigurationen kann das VDI-Startverfahren das Onboarding von Microsoft 365-Endpunkt Datenverlust verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="7c6a5-122">Öffnen Sie die ZIP-Datei des VDI-Konfigurationspakets ( *DeviceCompliancePackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="7c6a5-123">Wählen Sie im Navigationsbereich die Option **Einstellungen** für das  >  **Onboarding von Geräten** aus  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="7c6a5-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="7c6a5-124">Wählen Sie im Feld **Bereitstellungsmethode** die Option **VDI-Onboarding-Skripts für nicht persistente Endpunkte** aus.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="7c6a5-125">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="7c6a5-126">Kopieren Sie die Dateien aus dem DeviceCompliancePackage-Ordner, der aus der ZIP-Datei extrahiert wurde, in das `golden/master` Bild unter dem Pfad `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="7c6a5-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="7c6a5-127">Wenn Sie keinen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="7c6a5-128">Wenn Sie einen einzelnen Eintrag für jedes Gerät implementieren, kopieren Sie sowohl Onboard-NonPersistentMachine.ps1 als auch DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c6a5-129">Wenn der Ordner nicht angezeigt wird `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , ist er möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="7c6a5-130">Sie müssen im Datei-Explorer die Option **Ausgeblendete Dateien und Ordner anzeigen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="7c6a5-131">Öffnen Sie ein lokales Gruppenrichtlinien-Editor Fenster, und navigieren Sie zu **Computer Konfiguration**  >  **Windows-Einstellungs**  >  **Skripts**  >  **Startup** .</span><span class="sxs-lookup"><span data-stu-id="7c6a5-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="7c6a5-132">Domänengruppenrichtlinien können auch für das Onboarding nicht persistenter VDI-Geräte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="7c6a5-133">Je nach der Methode, die Sie implementieren möchten, führen Sie die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="7c6a5-134">**Für einzelne Einträge für jedes Gerät**</span><span class="sxs-lookup"><span data-stu-id="7c6a5-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="7c6a5-135">Wählen Sie die Registerkarte **PowerShell-Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt in dem Pfad geöffnet, in dem Sie das Onboarding-Skript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="7c6a5-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="7c6a5-136">Navigieren Sie zum Onboarding PowerShell `Onboard-NonPersistentMachine.ps1` -Skript.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="7c6a5-137">**Für mehrere Einträge für jedes Gerät** :</span><span class="sxs-lookup"><span data-stu-id="7c6a5-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="7c6a5-138">Wählen Sie die Registerkarte **Skripts** aus, und klicken Sie dann auf **Hinzufügen** (Windows Explorer wird direkt im Pfad geöffnet, in dem Sie das Onboarding-Skript zuvor kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="7c6a5-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="7c6a5-139">Navigieren Sie zum Onboarding bash `DeviceComplianceOnboardingScript.cmd` -Skript.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="7c6a5-140">Testen Sie Ihre Lösung:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-140">Test your solution:</span></span>

   1. <span data-ttu-id="7c6a5-141">Erstellen Sie einen Pool mit einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="7c6a5-142">Bei Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="7c6a5-143">Abmelden vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-143">Logoff from device.</span></span>

   1. <span data-ttu-id="7c6a5-144">Melden Sie sich mit einem anderen Benutzer an einem Gerät an.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="7c6a5-145">**Für einzelne Einträge für jedes Gerät** : Überprüfen Sie nur einen Eintrag im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="7c6a5-146">**Für mehrere Einträge für jedes Gerät** : Überprüfen Sie mehrere Einträge im Sicherheits Center von Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="7c6a5-147">Klicken Sie im Navigationsbereich auf **Geräteliste** .</span><span class="sxs-lookup"><span data-stu-id="7c6a5-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="7c6a5-148">Verwenden Sie die Suchfunktion, indem Sie den Gerätenamen eingeben und als Suchtyp **Gerät** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="7c6a5-149">Aktualisieren von VDI-Images (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="7c6a5-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="7c6a5-150">Als bewährte Methode wird empfohlen, Offline-Wartungstools zu verwenden, um Golden/Master-Images zu patchen.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="7c6a5-151">Beispielsweise können Sie die folgenden Befehle verwenden, um ein Update zu installieren, während das Bild offline bleibt:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="7c6a5-152">Weitere Informationen zu DISM-Befehlen und zur Offlinewartung finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="7c6a5-153">Ändern eines Windows-Abbilds mithilfe von DISM</span><span class="sxs-lookup"><span data-stu-id="7c6a5-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="7c6a5-154">Command-Line Optionen für DISM-Bildverwaltung</span><span class="sxs-lookup"><span data-stu-id="7c6a5-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="7c6a5-155">Verringern der Größe des Komponenten Speichers in einem Windows-Offline Abbild</span><span class="sxs-lookup"><span data-stu-id="7c6a5-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="7c6a5-156">Wenn die Offlinewartung keine geeignete Option für Ihre nicht persistente VDI-Umgebung ist, müssen die folgenden Schritte ausgeführt werden, um die Konsistenz und die Integrität des Sensors sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="7c6a5-157">Nachdem Sie das Masterabbild für Onlinewartung oder Patching gestartet haben, führen Sie ein offboarding-Skript aus, um den Microsoft 365-Endpunkt für die Datenverlust-Verhinderung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="7c6a5-158">Weitere Informationen finden Sie unter [extern-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="7c6a5-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="7c6a5-159">Stellen Sie sicher, dass der Sensor angehalten wird, indem Sie den folgenden Befehl in einem cmd-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="7c6a5-160">Dienst das Bild nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-160">Service the image as needed.</span></span>

4. <span data-ttu-id="7c6a5-161">Führen Sie die folgenden Befehle mit PsExec.exe aus https://download.sysinternals.com/files/PSTools.zip) , um die Inhalte des Cyber-Ordners, die der Sensor seit dem Start möglicherweise angesammelt hat, zu bereinigen:</span><span class="sxs-lookup"><span data-stu-id="7c6a5-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="7c6a5-162">Schließen Sie das Goldene/Master-Bild wie gewohnt erneut an.</span><span class="sxs-lookup"><span data-stu-id="7c6a5-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c6a5-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7c6a5-163">Related topics</span></span>
- [<span data-ttu-id="7c6a5-164">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7c6a5-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="7c6a5-165">Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7c6a5-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="7c6a5-166">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="7c6a5-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="7c6a5-167">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="7c6a5-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="7c6a5-168">Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7c6a5-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
