---
title: Abrufen von Details zu grundlegenden Mobilitäts-und Sicherheits verwalteten Geräten
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Verwenden Sie Windows PowerShell, um Details zu grundlegenden Mobilitäts-und Sicherheitsgeräten in Ihrer Organisation zu erhalten.
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430187"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="3cf1c-103">Abrufen von Details zu grundlegenden Mobilitäts-und Sicherheits verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="3cf1c-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="3cf1c-104">In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation abzurufen, die Sie für einfache Mobilität und Sicherheit eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="3cf1c-105">Im folgenden finden Sie eine Aufschlüsselung der Gerätedetails, die Ihnen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="3cf1c-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="3cf1c-106">**Detail**</span></span>|<span data-ttu-id="3cf1c-107">**Worauf Sie in PowerShell achten sollten**</span><span class="sxs-lookup"><span data-stu-id="3cf1c-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="3cf1c-108">Das Gerät ist in Basic Mobility and Security eingeschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="3cf1c-109">Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="3cf1c-110">Der Wert des *IsManaged*-   Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="3cf1c-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="3cf1c-111">**True**= Gerät ist registriert.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="3cf1c-112">**False**= Gerät ist nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="3cf1c-113">Gerät ist mit ihren Gerätesicherheitsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="3cf1c-114">Weitere Informationen finden Sie unter [Create Device Security Policies](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="3cf1c-115">Der Wert des *isCompliant*-   Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="3cf1c-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="3cf1c-116">**True**   = Gerät ist mit Richtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="3cf1c-117">**False**   = Gerät ist nicht konform mit Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende Mobilitäts-und Sicherheits-PowerShell-Parameter":::

>[!NOTE]
><span data-ttu-id="3cf1c-119">Die Befehle und Skripts in diesem Artikel geben auch Details zu Geräten zurück, die von [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune)verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3cf1c-120">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="3cf1c-120">Before you begin</span></span>

<span data-ttu-id="3cf1c-121">Es gibt ein paar Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3cf1c-122">Schritt 1: herunterladen und Installieren des Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cf1c-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3cf1c-123">Weitere Informationen zu diesen Schritten finden Sie unter [Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3cf1c-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="3cf1c-124">Wechseln Sie zu [Microsoft Online Services-Anmeldeassistent für IT-Experten RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   , und wählen Sie  **Download für den Microsoft Online Services-Anmelde-Assistenten**aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="3cf1c-125">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="3cf1c-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="3cf1c-126">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="3cf1c-127">Führen Sie den BefehlInstall-Module MSOnline aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="3cf1c-128">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="3cf1c-129">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="3cf1c-130">Schließen Sie nach der Installation das PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="3cf1c-131">Schritt 2: Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="3cf1c-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="3cf1c-132">Führen Sie im Windows Azure Active Directory-Modul für Windows PowerShell den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="3cf1c-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="3cf1c-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="3cf1c-134">Geben Sie im Dialogfeld Windows PowerShell Anmeldeinformationen den Benutzernamen und das Kennwort für das globale Administratorkonto von Microsoft 365 ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="3cf1c-135">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-135">Run the following command.</span></span>
    
    <span data-ttu-id="3cf1c-136">Connect-MsolService – Anmeldeinformationen $UserCredential</span><span class="sxs-lookup"><span data-stu-id="3cf1c-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="3cf1c-137">Schritt 3: sicherstellen, dass PowerShell-Skripts ausgeführt werden können</span><span class="sxs-lookup"><span data-stu-id="3cf1c-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="3cf1c-138">Sie können diesen Schritt überspringen, wenn Sie bereits für die Ausführung von PowerShell-Skripts eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="3cf1c-139">Zum Ausführen des Get-MsolUserDeviceComplianceStatus.ps1 Skripts müssen Sie die Ausführung von PowerShell-Skripts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="3cf1c-140">Wählen Sie auf dem Windows-Desktop **Start**aus, und geben Sie dann Windows PowerShell ein.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="3cf1c-141">Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="3cf1c-142">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-142">Run the following command.</span></span>
    
    <span data-ttu-id="3cf1c-143">Gruppe-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="3cf1c-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="3cf1c-144">Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="3cf1c-145">**Ausführen des Cmdlets Get-MsolDevice zum Anzeigen von Details für alle Geräte in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="3cf1c-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="3cf1c-146">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="3cf1c-147">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-147">Run the following command.</span></span>
    
    <span data-ttu-id="3cf1c-148">Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="3cf1c-149">Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="3cf1c-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="3cf1c-150">Ausführen eines Skripts zum Abrufen von Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="3cf1c-150">Run a script to get device details</span></span>

<span data-ttu-id="3cf1c-151">Speichern Sie zunächst das Skript auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="3cf1c-152">Kopieren Sie den folgenden Text, und fügen Sie ihn in Notepad ein.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="3cf1c-153">param</span><span class="sxs-lookup"><span data-stu-id="3cf1c-153">param (</span></span>
    

3.  <span data-ttu-id="3cf1c-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="3cf1c-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="3cf1c-155">[Switch] $Export,</span><span class="sxs-lookup"><span data-stu-id="3cf1c-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="3cf1c-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="3cf1c-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="3cf1c-157">[String] $exportPath = [Environment]:: GetFolderPath ("Desktop")</span><span class="sxs-lookup"><span data-stu-id="3cf1c-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="3cf1c-158">)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-158">)</span></span>
    

9.  <span data-ttu-id="3cf1c-159">[System. Collections. IDictionary] $Script: Schema = @ {</span><span class="sxs-lookup"><span data-stu-id="3cf1c-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="3cf1c-160">Geräte-Nr = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="3cf1c-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="3cf1c-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="3cf1c-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="3cf1c-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="3cf1c-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="3cf1c-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="3cf1c-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="3cf1c-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="3cf1c-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="3cf1c-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="3cf1c-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="3cf1c-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="3cf1c-172">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-172">}</span></span>
    

25.  <span data-ttu-id="3cf1c-173">Funktion createresultobject</span><span class="sxs-lookup"><span data-stu-id="3cf1c-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="3cf1c-174">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-174">{</span></span>
    

28.  <span data-ttu-id="3cf1c-175">[PSObject] $resultObject = New-Object-typeName PSObject-Property $Script: Schema</span><span class="sxs-lookup"><span data-stu-id="3cf1c-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="3cf1c-176">zurück $resultObject</span><span class="sxs-lookup"><span data-stu-id="3cf1c-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="3cf1c-177">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-177">}</span></span>
    

33.  <span data-ttu-id="3cf1c-178">If ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="3cf1c-179">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-179">{</span></span>
    

35.  <span data-ttu-id="3cf1c-180">$Users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="3cf1c-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="3cf1c-181">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-181">}</span></span>
    

38.  <span data-ttu-id="3cf1c-182">[PSObject []] $result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="3cf1c-183">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-183">{</span></span>
    

41.  <span data-ttu-id="3cf1c-184">[PSObject] $Devices = Get-msoldevice-RegisteredOwnerUpn $u. userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3cf1c-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="3cf1c-185">foreach ($d in $Devices)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="3cf1c-186">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-186">{</span></span>
    

44.  <span data-ttu-id="3cf1c-187">[PSObject] $deviceResult = createresultobject</span><span class="sxs-lookup"><span data-stu-id="3cf1c-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="3cf1c-188">$deviceResult. Device-Nr = $d. Device-Nr</span><span class="sxs-lookup"><span data-stu-id="3cf1c-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="3cf1c-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="3cf1c-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="3cf1c-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="3cf1c-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="3cf1c-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="3cf1c-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="3cf1c-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cf1c-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="3cf1c-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="3cf1c-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="3cf1c-194">$deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged</span><span class="sxs-lookup"><span data-stu-id="3cf1c-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="3cf1c-195">$deviceResult. DeviceObjectId = $d. ObjectID</span><span class="sxs-lookup"><span data-stu-id="3cf1c-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="3cf1c-196">$deviceResult. RegisteredOwnerUpn = $u. userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3cf1c-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="3cf1c-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectID</span><span class="sxs-lookup"><span data-stu-id="3cf1c-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="3cf1c-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cf1c-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="3cf1c-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="3cf1c-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="3cf1c-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="3cf1c-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="3cf1c-201">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-201">}</span></span>
    

61.  <span data-ttu-id="3cf1c-202">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-202">}</span></span>
    

63.  <span data-ttu-id="3cf1c-203">If ($Export)</span><span class="sxs-lookup"><span data-stu-id="3cf1c-203">If ($export)</span></span>
    

64.  <span data-ttu-id="3cf1c-204">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-204">{</span></span>
    

65.  <span data-ttu-id="3cf1c-205">$result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="3cf1c-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="3cf1c-206">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-206">}</span></span>
    

67.  <span data-ttu-id="3cf1c-207">Else</span><span class="sxs-lookup"><span data-stu-id="3cf1c-207">Else</span></span>
    

68.  <span data-ttu-id="3cf1c-208">{</span><span class="sxs-lookup"><span data-stu-id="3cf1c-208">{</span></span>
    

69.  <span data-ttu-id="3cf1c-209">$result</span><span class="sxs-lookup"><span data-stu-id="3cf1c-209">$result</span></span>
    

70.  <span data-ttu-id="3cf1c-210">}</span><span class="sxs-lookup"><span data-stu-id="3cf1c-210">}</span></span>
    

71.  <span data-ttu-id="3cf1c-211">Speichern Sie es als Windows PowerShell Skriptdatei mit der Dateierweiterung. ps1; Beispiel: Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="3cf1c-212">Ausführen des Skripts zum Abrufen von Geräteinformationen für ein einzelnes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="3cf1c-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="3cf1c-213">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3cf1c-214">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="3cf1c-215">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="3cf1c-216">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="3cf1c-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="3cf1c-217">Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Gerätedetails abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="3cf1c-218">In diesem Beispiel werden Details für Bar@example.com abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="3cf1c-219">$u = get-MsolUser-userPrincipalName Bar@example.com</span><span class="sxs-lookup"><span data-stu-id="3cf1c-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="3cf1c-220">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="3cf1c-221">.\Get-MsolUserDeviceComplianceStatus.ps1-Benutzer $u-Export</span><span class="sxs-lookup"><span data-stu-id="3cf1c-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="3cf1c-222">Die Informationen werden als CSV-Datei auf Ihren Windows-Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="3cf1c-223">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="3cf1c-224">Ausführen des Skripts zum Abrufen von Geräteinformationen für eine Gruppe von Benutzern</span><span class="sxs-lookup"><span data-stu-id="3cf1c-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="3cf1c-225">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3cf1c-226">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="3cf1c-227">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="3cf1c-228">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="3cf1c-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="3cf1c-229">Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Gerätedetails abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="3cf1c-230">In diesem Beispiel werden Details für Benutzer in der FinanceStaff-Gruppe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="3cf1c-231">$u = get-MsolGroupMember-suchbare "FinanceStaff" | % {Get-MsolUser-ObjectID $ _. ObjectID</span><span class="sxs-lookup"><span data-stu-id="3cf1c-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="3cf1c-232">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="3cf1c-233">.\Get-MsolUserDeviceComplianceStatus.ps1-Benutzer $u-Export</span><span class="sxs-lookup"><span data-stu-id="3cf1c-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="3cf1c-234">Die Informationen werden als CSV-Datei auf Ihren Windows-Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="3cf1c-235">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3cf1c-236">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3cf1c-236">Related topics</span></span>

[<span data-ttu-id="3cf1c-237">Microsoft Connect wurde zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="3cf1c-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="3cf1c-238">Übersicht über grundlegende Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3cf1c-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="3cf1c-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="3cf1c-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)