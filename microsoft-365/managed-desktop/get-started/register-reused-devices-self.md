---
title: Selbstregistrieren vorhandener Geräte
description: Wiederverwendete Geräte registrieren, die Sie möglicherweise bereits haben, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289139"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="2cb83-103">Selbstregistrieren vorhandener Geräte</span><span class="sxs-lookup"><span data-stu-id="2cb83-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="2cb83-104">In diesem Thema werden die Schritte beschrieben, mit denen Sie bereits verwendete Geräte wieder verwenden und in Microsoft Managed Desktop registrieren können.</span><span class="sxs-lookup"><span data-stu-id="2cb83-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="2cb83-105">Wenn Sie mit brandneuen Geräten arbeiten, befolgen Sie stattdessen die Schritte unter [Registrieren neuer Geräte in Microsoft Managed Desktop](register-devices-self.md) .</span><span class="sxs-lookup"><span data-stu-id="2cb83-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="2cb83-106">Der Prozess für Partner ist in [Schritten für Partner zum Registrieren von Geräten](register-devices-partner.md)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="2cb83-107">Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild).</span><span class="sxs-lookup"><span data-stu-id="2cb83-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="2cb83-108">Sie können Geräte über das Verwaltungs Portal von Microsoft Managed Desktop registrieren.</span><span class="sxs-lookup"><span data-stu-id="2cb83-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="2cb83-109">Vorbereiten der Registrierung vorhandener Geräte</span><span class="sxs-lookup"><span data-stu-id="2cb83-109">Prepare to register existing devices</span></span>


<span data-ttu-id="2cb83-110">Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="2cb83-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="2cb83-111">Rufen Sie den Hardwarehash für jedes Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="2cb83-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="2cb83-112">Zusammenführen der Hash Daten</span><span class="sxs-lookup"><span data-stu-id="2cb83-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="2cb83-113">[Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="2cb83-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="2cb83-114">Stellen Sie sicher, dass das Bild korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="2cb83-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="2cb83-115">Verteilen des Geräts</span><span class="sxs-lookup"><span data-stu-id="2cb83-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="2cb83-116">Abrufen des Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="2cb83-116">Obtain the hardware hash</span></span>

<span data-ttu-id="2cb83-117">Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem es auf seinen Hardwarehash verweist.</span><span class="sxs-lookup"><span data-stu-id="2cb83-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="2cb83-118">Sie haben vier Optionen, um diese Informationen von Geräten abzurufen, die Sie bereits verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cb83-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="2cb83-119">Fragen Sie Ihren OEM-Lieferanten nach der Autopilot-Registrierungsdatei, die die Hardware-Hashes enthält.</span><span class="sxs-lookup"><span data-stu-id="2cb83-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="2cb83-120">Sammeln von Informationen im [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="2cb83-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="2cb83-121">Führen Sie ein Windows PowerShell-Skript aus, indem Sie entweder [Active Directory](#active-directory-powershell-script-method) oder [manuell](#manual-powershell-script-method) auf jedem Gerät verwenden und die Ergebnisse in einer Datei sammeln.</span><span class="sxs-lookup"><span data-stu-id="2cb83-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="2cb83-122">Starten Sie jedes Gerät, aber schließen Sie nicht die Windows Setup-Umgebung ab – und [sammeln Sie die Hashes auf einem wechselbaren Flashlaufwerk](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="2cb83-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2cb83-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2cb83-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="2cb83-124">Sie können den Microsoft Endpoint Configuration Manager verwenden, um die Hardware Hashes von vorhandenen Geräten zu erfassen, die Sie bei Microsoft Managed Desktop registrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cb83-125">Für alle Geräte, für die Sie diese Informationen abrufen möchten, muss Windows 10, Version 1703 oder höher, installiert sein.</span><span class="sxs-lookup"><span data-stu-id="2cb83-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="2cb83-126">Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen mit den folgenden Schritten erfassen:</span><span class="sxs-lookup"><span data-stu-id="2cb83-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="2cb83-127">Wählen Sie in der Configuration Manager-Konsole **Überwachung**aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="2cb83-128">Erweitern Sie im Überwachungs Arbeitsbereich den Knoten **Berichterstellung** , erweitern Sie **Berichte**, und wählen Sie den Knoten **Hardware-allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="2cb83-129">Führen Sie den Bericht, **Windows Autopilot-Geräteinformationen**aus, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="2cb83-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="2cb83-130">Wählen Sie im Berichts-Viewer das **Export** Symbol aus, und wählen Sie die **CSV-Option (durch Trennzeichen-getrennt)** aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="2cb83-131">Nachdem Sie die Datei gespeichert haben, müssen Sie die Ergebnisse nur auf die Gerätefiltern, die Sie bei Microsoft Managed Desktop registrieren möchten, und die Daten in das [Verwaltungs Portal](https://aka.ms/mmdportal)von Microsoft Managed Desktop hochladen, indem Sie im linken Navigationsbereich **Geräte** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="2cb83-132">Select **+ Register Devices**; das Einfliegen wird geöffnet:</span><span class="sxs-lookup"><span data-stu-id="2cb83-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="2cb83-133">Weitere Informationen hierzu erhalten Sie unter [Registrieren von Geräten mithilfe des Verwaltungsportals](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="2cb83-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="2cb83-134">Active Directory PowerShell-Skriptmethode</span><span class="sxs-lookup"><span data-stu-id="2cb83-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="2cb83-135">In einer Active Directory Umgebung können Sie das PowerShell- `Get-WindowsAutoPilotInfo` Cmdlet verwenden, um die Informationen von Geräten in Active Directory Gruppen mithilfe von WinRM Remote zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="2cb83-136">Sie können auch das `Get-AD Computer` Cmdlet verwenden und gefilterte Ergebnisse für bestimmte Hardwaremodell Namen abrufen, die im Katalog enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2cb83-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="2cb83-137">Bestätigen Sie dazu zunächst diese Voraussetzungen, und fahren Sie mit den folgenden Schritten fort:</span><span class="sxs-lookup"><span data-stu-id="2cb83-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="2cb83-138">WinRM ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-138">WinRM is enabled.</span></span>
- <span data-ttu-id="2cb83-139">Die zu registrierenden Geräte sind im Netzwerk aktiv (Sie sind nicht getrennt oder ausgeschaltet).</span><span class="sxs-lookup"><span data-stu-id="2cb83-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="2cb83-140">Stellen Sie sicher, dass Sie über einen Domänenanmelde Parameter verfügen, der die Berechtigung hat, Remote auf den Geräten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="2cb83-141">Stellen Sie sicher, dass der Windows-Firewall Zugriff auf WMI zulässt.</span><span class="sxs-lookup"><span data-stu-id="2cb83-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="2cb83-142">Führen Sie dazu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2cb83-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="2cb83-143">Öffnen Sie die **Windows Defender-Firewall** -Systemsteuerung, und wählen Sie **app oder Feature über die Windows Defender-Firewall zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="2cb83-144">Suchen Sie in der Liste nach **Windows-Verwaltungsinstrumentation (WMI)** , aktivieren Sie für **Privat und öffentlich**, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="2cb83-145">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="2cb83-146">Führen Sie *eines* der folgenden Skripts aus:</span><span class="sxs-lookup"><span data-stu-id="2cb83-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="2cb83-147">Greifen Sie auf alle Verzeichnisse zu, in denen Einträge für die Geräte vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="2cb83-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="2cb83-148">Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory-Domänendienste und Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2cb83-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="2cb83-149">Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="2cb83-150">Access Management Services, bei denen Einträge für die Geräte vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="2cb83-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="2cb83-151">Entfernen Sie Einträge für jedes Gerät aus *allen* Verwaltungsdiensten, einschließlich Microsoft Endpoint Configuration Manager, Microsoft InTune und Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2cb83-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="2cb83-152">Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="2cb83-153">Jetzt können Sie mit dem [Registrieren von Geräten](#register-devices-by-using-the-admin-portal)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2cb83-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="2cb83-154">Manuelle PowerShell-Skriptmethode</span><span class="sxs-lookup"><span data-stu-id="2cb83-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="2cb83-155">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="2cb83-156">Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="2cb83-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="2cb83-157">Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2cb83-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="2cb83-158">Führen Sie die Hash Daten zusammen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="2cb83-159">Flash Drive-Methode</span><span class="sxs-lookup"><span data-stu-id="2cb83-159">Flash drive method</span></span>

1. <span data-ttu-id="2cb83-160">Legen Sie auf einem anderen Gerät als dem, das Sie gerade registrieren, ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="2cb83-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="2cb83-161">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="2cb83-162">Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="2cb83-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="2cb83-163">Aktivieren Sie das Gerät, das Sie registrieren, aber *beginnen Sie nicht mit der Setup-Umgebung*.</span><span class="sxs-lookup"><span data-stu-id="2cb83-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="2cb83-164">Wenn Sie das Setupprogramm versehentlich gestartet haben, müssen Sie das Gerät zurücksetzen oder neu abbilden.</span><span class="sxs-lookup"><span data-stu-id="2cb83-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="2cb83-165">Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.</span><span class="sxs-lookup"><span data-stu-id="2cb83-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="2cb83-166">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann aus `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="2cb83-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="2cb83-167">Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="2cb83-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="2cb83-168">Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2cb83-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="2cb83-169">Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="2cb83-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="2cb83-170">Führen Sie die Hash Daten zusammen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="2cb83-171">Schalten Sie das Gerät, das Sie erneut registrieren, erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="2cb83-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="2cb83-172">Zusammenführen von Hash Daten</span><span class="sxs-lookup"><span data-stu-id="2cb83-172">Merge hash data</span></span>

<span data-ttu-id="2cb83-173">Wenn Sie die Hardwarehash Daten nach den manuellen PowerShell-oder Flash Drive-Methoden gesammelt haben, müssen Sie nun die Daten in den CSV-Dateien in einer einzigen Datei zusammenfassen, um die Registrierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="2cb83-174">Hier ist ein Beispiel für PowerShell-Skripts, um dies zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="2cb83-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="2cb83-175">Nachdem die Hashdaten in einer CSV-Datei zusammengeführt wurden, können Sie nun mit [dem Registrieren der Geräte](#register-devices-by-using-the-admin-portal)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2cb83-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="2cb83-176">Registrieren von Geräten mithilfe des Verwaltungsportals</span><span class="sxs-lookup"><span data-stu-id="2cb83-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="2cb83-177">Wählen Sie im [Verwaltungs Portal](https://aka.ms/mmdportal)von Microsoft Managed Desktop die Option **Geräte** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="2cb83-178">Select **+ Register Devices**; das Einfliegen wird geöffnet:</span><span class="sxs-lookup"><span data-stu-id="2cb83-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="2cb83-179">[![Einfliegen nach Auswahl von Register Geräten, Auflisten von Geräten mit Spalten für zugewiesene Benutzer, Seriennummer, Status, zuletzt gesehenes Datum und Alter](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="2cb83-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="2cb83-180">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2cb83-180">Follow these steps:</span></span>

1. <span data-ttu-id="2cb83-181">Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2cb83-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="2cb83-182">Wählen Sie **Geräte registrieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2cb83-182">Select **Register devices**.</span></span> <span data-ttu-id="2cb83-183">Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als **AutopilotRegistrationRequested**gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="2cb83-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="2cb83-184">Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.</span><span class="sxs-lookup"><span data-stu-id="2cb83-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="2cb83-185">Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="2cb83-186">Mögliche Zustände, die dort gemeldet werden, umfassen:</span><span class="sxs-lookup"><span data-stu-id="2cb83-186">Possible states reported there include:</span></span>

| <span data-ttu-id="2cb83-187">Status</span><span class="sxs-lookup"><span data-stu-id="2cb83-187">State</span></span> | <span data-ttu-id="2cb83-188">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cb83-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="2cb83-189">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="2cb83-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="2cb83-190">Die Registrierung ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-190">Registration is not done yet.</span></span> <span data-ttu-id="2cb83-191">Überprüfen Sie später erneut.</span><span class="sxs-lookup"><span data-stu-id="2cb83-191">Check back later.</span></span> |
| <span data-ttu-id="2cb83-192">Registrierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="2cb83-192">Registration failed</span></span> | <span data-ttu-id="2cb83-193">Die Registrierung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2cb83-193">Registration could not be completed.</span></span> <span data-ttu-id="2cb83-194">Weitere Informationen erhalten Sie unter [Problembehandlung bei der Geräteregistrierung](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="2cb83-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="2cb83-195">Benutzer einsatzfähig</span><span class="sxs-lookup"><span data-stu-id="2cb83-195">Ready for user</span></span> | <span data-ttu-id="2cb83-196">Die Registrierung wurde erfolgreich ausgeführt, und das Gerät kann nun für den Benutzer bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2cb83-196">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="2cb83-197">Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="2cb83-198">Aktiv</span><span class="sxs-lookup"><span data-stu-id="2cb83-198">Active</span></span> | <span data-ttu-id="2cb83-199">Das Gerät wurde dem Benutzer zugestellt und Sie haben sich bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-199">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="2cb83-200">Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cb83-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="2cb83-201">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="2cb83-201">Inactive</span></span> | <span data-ttu-id="2cb83-202">Das Gerät wurde dem Benutzer zugestellt und Sie haben sich bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="2cb83-203">Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).</span><span class="sxs-lookup"><span data-stu-id="2cb83-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="2cb83-204">Problembehandlung bei der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="2cb83-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="2cb83-205">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="2cb83-205">Error message</span></span> | <span data-ttu-id="2cb83-206">Details</span><span class="sxs-lookup"><span data-stu-id="2cb83-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="2cb83-207">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="2cb83-207">Device not found</span></span> | <span data-ttu-id="2cb83-208">Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="2cb83-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="2cb83-209">Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="2cb83-210">Hardware Hash ungültig</span><span class="sxs-lookup"><span data-stu-id="2cb83-210">Hardware hash not valid</span></span> | <span data-ttu-id="2cb83-211">Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="2cb83-212">Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2cb83-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="2cb83-213">Gerät ist bereits registriert</span><span class="sxs-lookup"><span data-stu-id="2cb83-213">Device already registered</span></span> | <span data-ttu-id="2cb83-214">Dieses Gerät ist bereits für Ihre Organisation registriert.</span><span class="sxs-lookup"><span data-stu-id="2cb83-214">This device is already registered to your organization.</span></span> <span data-ttu-id="2cb83-215">Keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2cb83-215">No further action required.</span></span> |
| <span data-ttu-id="2cb83-216">Von einer anderen Organisation beanspruchtes Gerät</span><span class="sxs-lookup"><span data-stu-id="2cb83-216">Device claimed by another organization</span></span> | <span data-ttu-id="2cb83-217">Dieses Gerät wurde bereits von einer anderen Organisation beansprucht.</span><span class="sxs-lookup"><span data-stu-id="2cb83-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="2cb83-218">Erkundigen Sie sich bei Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="2cb83-219">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="2cb83-219">Unexpected error</span></span> | <span data-ttu-id="2cb83-220">Ihre Anforderung konnte nicht automatisch verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2cb83-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="2cb83-221">Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an: <requestId></span><span class="sxs-lookup"><span data-stu-id="2cb83-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="2cb83-222">Überprüfen des Bilds</span><span class="sxs-lookup"><span data-stu-id="2cb83-222">Check the image</span></span>

<span data-ttu-id="2cb83-223">Wenn Ihr Gerät von einem Microsoft Managed Desktop Partner-Anbieter stammt, sollte das Bild korrekt sein.</span><span class="sxs-lookup"><span data-stu-id="2cb83-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="2cb83-224">Sie können das Bild auch auf eigene Faust anwenden, wenn Sie es vorziehen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="2cb83-225">Um zu beginnen, wenden Sie sich an den Microsoft-Mitarbeiter, mit dem Sie zusammenarbeiten, und Sie werden den Speicherort und die Schritte zum Anwenden des Abbilds erhalten.</span><span class="sxs-lookup"><span data-stu-id="2cb83-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="2cb83-226">Verteilen des Geräts</span><span class="sxs-lookup"><span data-stu-id="2cb83-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cb83-227">Bevor Sie das Gerät an Ihren Benutzer übergeben, müssen Sie sicherstellen, dass Sie die [entsprechenden Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erworben und angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="2cb83-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="2cb83-228">Wenn alle Lizenzen angewendet werden, können Sie [Ihre Benutzer zur Verwendung von Geräten verwenden](get-started-devices.md), und dann kann Ihr Benutzer das Gerät starten und die Windows Setup-Umgebung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="2cb83-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









