---
title: Selbstregistrieren vorhandener Geräte
description: Registrieren sie wiederverwendete Geräte, die Sie möglicherweise bereits selbst haben, damit sie von Microsoft Managed Desktop verwaltet werden können.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445566"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="e41c3-104">Selbstregistrieren vorhandener Geräte</span><span class="sxs-lookup"><span data-stu-id="e41c3-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="e41c3-105">In diesem Thema werden die Schritte beschrieben, wie Sie bereits vorhandene Geräte wiederverwenden und in Microsoft Managed Desktop registrieren können.</span><span class="sxs-lookup"><span data-stu-id="e41c3-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="e41c3-106">Wenn Sie mit brandneuen Geräten arbeiten, führen Sie stattdessen die Schritte unter Registrieren neuer Geräte [in Microsoft Managed Desktop selbst](register-devices-self.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e41c3-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="e41c3-107">Der Prozess für Partner ist unter Schritte für Partner zum Registrieren [von Geräten dokumentiert.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="e41c3-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="e41c3-108">Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können bereits vorhandene Geräte wiederverwenden (dies erfordert, dass Sie sie neu abbilden).</span><span class="sxs-lookup"><span data-stu-id="e41c3-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="e41c3-109">Sie können Geräte bei Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.</span><span class="sxs-lookup"><span data-stu-id="e41c3-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="e41c3-110">Vorbereiten der Registrierung vorhandener Geräte</span><span class="sxs-lookup"><span data-stu-id="e41c3-110">Prepare to register existing devices</span></span>


<span data-ttu-id="e41c3-111">Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="e41c3-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="e41c3-112">Rufen Sie den Hardwarehash für jedes Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="e41c3-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="e41c3-113">Zusammenführen der Hashdaten</span><span class="sxs-lookup"><span data-stu-id="e41c3-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="e41c3-114">[Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="e41c3-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="e41c3-115">Überprüfen Sie, ob das Bild richtig ist.</span><span class="sxs-lookup"><span data-stu-id="e41c3-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="e41c3-116">Bereitstellen des Geräts</span><span class="sxs-lookup"><span data-stu-id="e41c3-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="e41c3-117">Abrufen des Hardwarehashs</span><span class="sxs-lookup"><span data-stu-id="e41c3-117">Obtain the hardware hash</span></span>

<span data-ttu-id="e41c3-118">Microsoft Managed Desktop identifiziert jedes Gerät durch Verweisen auf den Hardwarehash eindeutig.</span><span class="sxs-lookup"><span data-stu-id="e41c3-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="e41c3-119">Sie haben vier Optionen, um diese Informationen von Geräten zu erhalten, die Sie bereits verwenden:</span><span class="sxs-lookup"><span data-stu-id="e41c3-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="e41c3-120">Fragen Sie Ihren OEM-Lieferanten nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.</span><span class="sxs-lookup"><span data-stu-id="e41c3-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="e41c3-121">Sammeln von Informationen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="e41c3-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="e41c3-122">Führen Sie Windows PowerShell -- entweder mithilfe von [](#manual-powershell-script-method) [Active Directory](#active-directory-powershell-script-method) oder manuell auf jedem Gerät - aus, und sammeln Sie die Ergebnisse in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="e41c3-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="e41c3-123">Starten Sie jedes Gerät , aber schließen Sie die #A0 nicht ab, und sammeln Sie die Hashes auf einem [Wechseldatenträger.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="e41c3-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e41c3-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e41c3-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="e41c3-125">Sie können Microsoft Endpoint Configuration Manager verwenden, um die Hardwarehashes von vorhandenen Geräten zu erfassen, die Sie bei Microsoft Managed Desktop registrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e41c3-126">Alle Geräte, für die Sie diese Informationen erhalten möchten, müssen Windows 10, Version 1703 oder höher, ausführen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="e41c3-127">Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen sammeln, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e41c3-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="e41c3-128">Wählen Sie in der Configuration Manager-Konsole Überwachung **aus.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="e41c3-129">Erweitern Sie im Arbeitsbereich Überwachung den Knoten **Berichterstellung,** erweitern Sie **Berichte,** und wählen Sie **den Knoten Hardware – Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="e41c3-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="e41c3-130">Führen Sie den Bericht Windows **Autopilot Device Information aus,** und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="e41c3-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="e41c3-131">Wählen Sie in der Berichtsanzeige das Symbol **Exportieren** aus, und wählen Sie die **Option CSV (durch** Trennzeichen getrennt) aus.</span><span class="sxs-lookup"><span data-stu-id="e41c3-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="e41c3-132">Nach dem Speichern der Datei müssen Sie die Ergebnisse nur auf die Geräte filtern, die Sie bei Microsoft Managed Desktop registrieren und die Daten auf Microsoft Managed Desktop hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="e41c3-133">Öffnen Sie Microsoft Endpoint Manager, navigieren Sie zum Menü **Geräte,** suchen Sie dann nach Microsoft Managed Desktop, und wählen Sie **Geräte aus.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="e41c3-134">Wählen **Sie + Geräte registrieren** aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e41c3-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="e41c3-135">Weitere Informationen finden Sie unter Registrieren [von Geräten mithilfe des Administratorportals.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="e41c3-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="e41c3-136">Active Directory -PowerShell-Skriptmethode</span><span class="sxs-lookup"><span data-stu-id="e41c3-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="e41c3-137">In einer Active Directory-Umgebung können Sie das PowerShell-Cmdlet verwenden, um die Informationen von Geräten in Active Directory-Gruppen mithilfe von `Get-WindowsAutoPilotInfo` WinRM remote zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="e41c3-138">Sie können auch das Cmdlet verwenden und gefilterte Ergebnisse für einen bestimmten Hardwaremodellnamen im `Get-AD Computer` Katalog erhalten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="e41c3-139">Bevor Sie fortfahren, bestätigen Sie zunächst diese Voraussetzungen, und fahren Sie dann mit den Schritten fort:</span><span class="sxs-lookup"><span data-stu-id="e41c3-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="e41c3-140">WinRM ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e41c3-140">WinRM is enabled.</span></span>
- <span data-ttu-id="e41c3-141">Die Geräte, die Sie registrieren möchten, sind im Netzwerk aktiv (d. h., sie werden nicht getrennt oder deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="e41c3-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="e41c3-142">Stellen Sie sicher, dass Sie über einen Domänenanmeldeinformationsparameter verfügen, der über die Berechtigung zum Remote ausführen auf den Geräten verfügt.</span><span class="sxs-lookup"><span data-stu-id="e41c3-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="e41c3-143">Stellen Sie sicher, dass die Windows-Firewall den Zugriff auf WMI zulässt.</span><span class="sxs-lookup"><span data-stu-id="e41c3-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="e41c3-144">Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e41c3-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="e41c3-145">Öffnen Sie Windows Defender Firewall-Systemsteuerung, und wählen Sie App oder Feature über die **Firewall Windows Defender zulassen aus.** </span><span class="sxs-lookup"><span data-stu-id="e41c3-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="e41c3-146">Suchen **Sie die Windows-Verwaltungsinstrumentierung (WMI)** in der Liste, aktivieren Sie **private** und öffentliche Geräte, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="e41c3-147">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="e41c3-148">Führen *Sie eines der* folgenden Skripts aus:</span><span class="sxs-lookup"><span data-stu-id="e41c3-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="e41c3-149">Greifen Sie auf verzeichnisse zu, in denen Einträge für die Geräte enthalten sein können.</span><span class="sxs-lookup"><span data-stu-id="e41c3-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="e41c3-150">Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory Domain Services und Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e41c3-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="e41c3-151">Beachten Sie, dass das Entfernen einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="e41c3-152">Zugriff auf Verwaltungsdienste, bei denen Einträge für die Geräte enthalten sein können.</span><span class="sxs-lookup"><span data-stu-id="e41c3-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="e41c3-153">Entfernen Sie Einträge für jedes Gerät aus *allen Verwaltungsdiensten,* einschließlich Microsoft Endpoint Configuration Manager, Microsoft Intune und Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e41c3-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="e41c3-154">Beachten Sie, dass das Entfernen einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="e41c3-155">Jetzt können Sie mit der [Registrierung von Geräten fortfahren.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="e41c3-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="e41c3-156">Manuelle PowerShell-Skriptmethode</span><span class="sxs-lookup"><span data-stu-id="e41c3-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="e41c3-157">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="e41c3-158">Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="e41c3-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="e41c3-159">Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e41c3-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="e41c3-160">Zusammenführen der Hashdaten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="e41c3-161">Flash drive-Methode</span><span class="sxs-lookup"><span data-stu-id="e41c3-161">Flash drive method</span></span>

1. <span data-ttu-id="e41c3-162">Fügen Sie auf einem anderen Gerät als dem, das Sie registrieren, ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="e41c3-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="e41c3-163">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="e41c3-164">Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="e41c3-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="e41c3-165">Aktivieren Sie das Gerät, das Sie registrieren, *starten Sie jedoch nicht die Einrichtungserfahrung*.</span><span class="sxs-lookup"><span data-stu-id="e41c3-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="e41c3-166">Wenn Sie die Einrichtung versehentlich starten, müssen Sie das Gerät zurücksetzen oder neu abbilden.</span><span class="sxs-lookup"><span data-stu-id="e41c3-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="e41c3-167">Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.</span><span class="sxs-lookup"><span data-stu-id="e41c3-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="e41c3-168">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann `cd <pathToUsb>` aus.</span><span class="sxs-lookup"><span data-stu-id="e41c3-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="e41c3-169">Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="e41c3-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="e41c3-170">Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e41c3-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="e41c3-171">Entfernen Sie das USB-Laufwerk, und fahren Sie das Gerät herunter, indem Sie `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="e41c3-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="e41c3-172">Zusammenführen der Hashdaten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="e41c3-173">Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, wenn Sie die Registrierung für das Gerät abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e41c3-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="e41c3-174">Zusammenführen von Hashdaten</span><span class="sxs-lookup"><span data-stu-id="e41c3-174">Merge hash data</span></span>

<span data-ttu-id="e41c3-175">Wenn Sie die Hardwarehashdaten mithilfe der manuellen PowerShell- oder Flashlaufwerkmethoden gesammelt haben, müssen Sie die Daten in den #A0 nun in einer einzigen Datei kombinieren, um die Registrierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="e41c3-176">Im Folgenden finden Sie ein PowerShell-Beispielskript, um es einfach zu machen:</span><span class="sxs-lookup"><span data-stu-id="e41c3-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="e41c3-177">Nachdem die Hashdaten in einer #A0 zusammengeführt wurden, können Sie nun mit der [Registrierung der Geräte fortfahren.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="e41c3-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="e41c3-178">Registrieren von Geräten mithilfe des Administratorportals</span><span class="sxs-lookup"><span data-stu-id="e41c3-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="e41c3-179">Wählen [Sie im Microsoft Endpoint Manager](https://endpoint.microsoft.com/) **geräte** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="e41c3-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="e41c3-180">Suchen Sie im Menü nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Geräte aus.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="e41c3-181">Wählen Sie im Arbeitsbereich Microsoft Managed Desktop Devices die Option **+ Geräte registrieren** aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e41c3-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="e41c3-182">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e41c3-182">Follow these steps:</span></span>

1. <span data-ttu-id="e41c3-183">Geben **Sie unter Dateiupload** einen Pfad zur zuvor erstellten CSV-Datei an.</span><span class="sxs-lookup"><span data-stu-id="e41c3-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="e41c3-184">Wählen **Sie Geräte registrieren aus.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-184">Select **Register devices**.</span></span> <span data-ttu-id="e41c3-185">Das System fügt die Geräte ihrer Liste der Geräte auf dem **Blatt Geräte** hinzu, das als **Registrierung ausstehend gekennzeichnet ist.**</span><span class="sxs-lookup"><span data-stu-id="e41c3-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="e41c3-186">Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Verwendung wird das Gerät als **Bereit** für Benutzer angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.</span><span class="sxs-lookup"><span data-stu-id="e41c3-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="e41c3-187">Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="e41c3-188">Mögliche gemeldete Zustände sind:</span><span class="sxs-lookup"><span data-stu-id="e41c3-188">Possible states reported there include:</span></span>

| <span data-ttu-id="e41c3-189">Status</span><span class="sxs-lookup"><span data-stu-id="e41c3-189">State</span></span> | <span data-ttu-id="e41c3-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e41c3-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="e41c3-191">Registrierung ausstehend</span><span class="sxs-lookup"><span data-stu-id="e41c3-191">Registration Pending</span></span> | <span data-ttu-id="e41c3-192">Die Registrierung ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-192">Registration is not done yet.</span></span> <span data-ttu-id="e41c3-193">Überprüfen Sie später.</span><span class="sxs-lookup"><span data-stu-id="e41c3-193">Check back later.</span></span> |
| <span data-ttu-id="e41c3-194">Fehler bei der Registrierung</span><span class="sxs-lookup"><span data-stu-id="e41c3-194">Registration failed</span></span> | <span data-ttu-id="e41c3-195">Die Registrierung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e41c3-195">Registration could not be completed.</span></span> <span data-ttu-id="e41c3-196">Weitere Informationen [finden Sie unter Problembehandlung](#troubleshooting-device-registration) bei der Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="e41c3-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="e41c3-197">Bereit für Benutzer</span><span class="sxs-lookup"><span data-stu-id="e41c3-197">Ready for user</span></span> | <span data-ttu-id="e41c3-198">Die Registrierung ist erfolgreich, und das Gerät kann jetzt an den Benutzer zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e41c3-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="e41c3-199">Microsoft Managed Desktop führt sie durch das erste Einrichten, sodass Sie keine weiteren Vorbereitungen machen müssen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="e41c3-200">Aktiv</span><span class="sxs-lookup"><span data-stu-id="e41c3-200">Active</span></span> | <span data-ttu-id="e41c3-201">Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="e41c3-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="e41c3-202">Dies bedeutet auch, dass sie das Gerät regelmäßig verwenden.</span><span class="sxs-lookup"><span data-stu-id="e41c3-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="e41c3-203">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="e41c3-203">Inactive</span></span> | <span data-ttu-id="e41c3-204">Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="e41c3-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="e41c3-205">Sie haben das Gerät jedoch in letzter Zeit (in den letzten 7 Tagen) nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e41c3-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="e41c3-206">Problembehandlung bei der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="e41c3-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="e41c3-207">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="e41c3-207">Error message</span></span> | <span data-ttu-id="e41c3-208">Details</span><span class="sxs-lookup"><span data-stu-id="e41c3-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="e41c3-209">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e41c3-209">Device not found</span></span> | <span data-ttu-id="e41c3-210">Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer finden konnten.</span><span class="sxs-lookup"><span data-stu-id="e41c3-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="e41c3-211">Bestätigen Sie diese Werte mit Ihrem Geräteanbieter.</span><span class="sxs-lookup"><span data-stu-id="e41c3-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="e41c3-212">Hardwarehash ungültig</span><span class="sxs-lookup"><span data-stu-id="e41c3-212">Hardware hash not valid</span></span> | <span data-ttu-id="e41c3-213">Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="e41c3-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="e41c3-214">Überprüfen Sie den Hardwarehash, und übermitteln Sie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="e41c3-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="e41c3-215">Gerät bereits registriert</span><span class="sxs-lookup"><span data-stu-id="e41c3-215">Device already registered</span></span> | <span data-ttu-id="e41c3-216">Dieses Gerät ist bereits in Ihrer Organisation registriert.</span><span class="sxs-lookup"><span data-stu-id="e41c3-216">This device is already registered to your organization.</span></span> <span data-ttu-id="e41c3-217">Keine weiteren Aktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e41c3-217">No further action required.</span></span> |
| <span data-ttu-id="e41c3-218">Von einer anderen Organisation beanspruchtes Gerät</span><span class="sxs-lookup"><span data-stu-id="e41c3-218">Device claimed by another organization</span></span> | <span data-ttu-id="e41c3-219">Dieses Gerät wurde bereits von einer anderen Organisation beansprucht.</span><span class="sxs-lookup"><span data-stu-id="e41c3-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="e41c3-220">Informieren Sie sich bei Ihrem Geräteanbieter.</span><span class="sxs-lookup"><span data-stu-id="e41c3-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="e41c3-221">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="e41c3-221">Unexpected error</span></span> | <span data-ttu-id="e41c3-222">Ihre Anforderung konnte nicht automatisch verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e41c3-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="e41c3-223">Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId></span><span class="sxs-lookup"><span data-stu-id="e41c3-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="e41c3-224">Überprüfen des Bilds</span><span class="sxs-lookup"><span data-stu-id="e41c3-224">Check the image</span></span>

<span data-ttu-id="e41c3-225">Wenn Ihr Gerät von einem Microsoft Managed Desktop-Partneranbieter stammen, sollte das Bild korrekt sein.</span><span class="sxs-lookup"><span data-stu-id="e41c3-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="e41c3-226">Sie können das Bild auch selbst anwenden, wenn Sie es bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="e41c3-227">Um zu beginnen, wenden Sie sich an den Microsoft-Vertreter, mit dem Sie arbeiten, und er stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e41c3-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="e41c3-228">Bereitstellen des Geräts</span><span class="sxs-lookup"><span data-stu-id="e41c3-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e41c3-229">Bevor Sie das Gerät an Ihren Benutzer senden, stellen Sie sicher, dass Sie die entsprechenden [Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erhalten und angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="e41c3-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="e41c3-230">Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von Geräten bereit [machen,](get-started-devices.md)und dann kann Der Benutzer das Gerät starten und die Windows-Setuperfahrung durchmachen.</span><span class="sxs-lookup"><span data-stu-id="e41c3-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









