---
title: Abrufen von Details zu von Basic Mobility and Security verwalteten Geräten
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
description: Verwenden Sie Windows PowerShell, um Details zu grundlegenden Mobilitäts- und Sicherheitsgeräten in Ihrer Organisation zu erhalten.
ms.openlocfilehash: 7cb2369c9a31210f26db12b0453e7a4228e1cccc
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782441"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="fdb6e-103">Abrufen von Details zu von Basic Mobility and Security verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="fdb6e-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="fdb6e-104">In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation zu erhalten, die Sie für Grundlegende Mobilität und Sicherheit eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="fdb6e-105">Hier ist eine Aufschlüsselung der verfügbaren Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="fdb6e-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="fdb6e-106">**Detail**</span></span>|<span data-ttu-id="fdb6e-107">**Suchen in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fdb6e-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="fdb6e-108">Das Gerät ist in Basic Mobility and Security registriert.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="fdb6e-109">Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="fdb6e-110">Der Wert des *isManaged-Parameters*   lautet:</span><span class="sxs-lookup"><span data-stu-id="fdb6e-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="fdb6e-111">**True**= Gerät ist registriert.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="fdb6e-112">**False**= Gerät ist nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="fdb6e-113">Das Gerät ist mit Ihren Gerätesicherheitsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="fdb6e-114">Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="fdb6e-115">Der Wert des *isCompliant-Parameters*   lautet:</span><span class="sxs-lookup"><span data-stu-id="fdb6e-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="fdb6e-116">**True**   = Das Gerät ist richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="fdb6e-117">**False**   = Das Gerät ist nicht richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende PowerShell-Parameter für Mobilität und Sicherheit":::

>[!NOTE]
><span data-ttu-id="fdb6e-119">Die Befehle und Skripts in diesem Artikel geben auch Details zu allen Geräten [zurück, die](https://www.microsoft.com/cloud-platform/microsoft-intune)von Microsoft Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fdb6e-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="fdb6e-120">Before you begin</span></span>

<span data-ttu-id="fdb6e-121">Es gibt einige Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fdb6e-122">Schritt 1: Herunterladen und Installieren des Azure Active Directory Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdb6e-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fdb6e-123">Weitere Informationen zu diesen Schritten finden Sie unter [Verbinden zum Microsoft 365 mit PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="fdb6e-124">Wechseln Sie zu [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl,](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)und wählen Sie    **"Download for Microsoft Online Services Sign-in Assistant" aus.**</span><span class="sxs-lookup"><span data-stu-id="fdb6e-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="fdb6e-125">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="fdb6e-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="fdb6e-126">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="fdb6e-127">Führen Sie den BefehlInstall-Module MSOnline aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="fdb6e-128">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="fdb6e-129">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="fdb6e-130">Schließen Sie nach der Installation das PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="fdb6e-131">Schritt 2: Verbinden zu Ihrem Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="fdb6e-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="fdb6e-132">Führen Sie im Windows Azure Active Directory Modul für Windows PowerShell den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="fdb6e-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="fdb6e-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="fdb6e-134">Geben Sie im Dialogfeld Windows PowerShell Anmeldeinformationsanforderung den Benutzernamen und das Kennwort für Ihr Microsoft 365 globale Administratorkonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="fdb6e-135">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-135">Run the following command.</span></span>

    <span data-ttu-id="fdb6e-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="fdb6e-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="fdb6e-137">Schritt 3: Stellen Sie sicher, dass Sie PowerShell-Skripts ausführen können</span><span class="sxs-lookup"><span data-stu-id="fdb6e-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="fdb6e-138">Sie können diesen Schritt überspringen, wenn Sie bereits für die Ausführung von PowerShell-Skripts eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="fdb6e-139">Um das skript Get-MsolUserDeviceComplianceStatus.ps1 ausführen zu können, müssen Sie die Ausführung von PowerShell-Skripts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="fdb6e-140">Wählen Sie im Windows Desktop die Option **"Start"** aus, und geben Sie dann Windows PowerShell ein.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="fdb6e-141">Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und wählen Sie dann **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="fdb6e-142">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-142">Run the following command.</span></span>

    <span data-ttu-id="fdb6e-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="fdb6e-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="fdb6e-144">Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="fdb6e-145">**Führen Sie das Cmdlet Get-MsolDevice aus, um Details für alle Geräte in Ihrer Organisation anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="fdb6e-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="fdb6e-146">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="fdb6e-147">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-147">Run the following command.</span></span>

    <span data-ttu-id="fdb6e-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="fdb6e-149">Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="fdb6e-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="fdb6e-150">Ausführen eines Skripts zum Abrufen von Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="fdb6e-150">Run a script to get device details</span></span>

<span data-ttu-id="fdb6e-151">Speichern Sie zunächst das Skript auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="fdb6e-152">Kopieren Sie den folgenden Text, und fügen Sie ihn in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="fdb6e-153">param (</span><span class="sxs-lookup"><span data-stu-id="fdb6e-153">param (</span></span>

3.  <span data-ttu-id="fdb6e-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="fdb6e-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="fdb6e-155">[Switch]$export,</span><span class="sxs-lookup"><span data-stu-id="fdb6e-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="fdb6e-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="fdb6e-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="fdb6e-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span><span class="sxs-lookup"><span data-stu-id="fdb6e-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="fdb6e-158">)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-158">)</span></span>

9.  <span data-ttu-id="fdb6e-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="fdb6e-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="fdb6e-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="fdb6e-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="fdb6e-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="fdb6e-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="fdb6e-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="fdb6e-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="fdb6e-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="fdb6e-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="fdb6e-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="fdb6e-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="fdb6e-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="fdb6e-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="fdb6e-172">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-172">}</span></span>
    

25.  <span data-ttu-id="fdb6e-173">function createResultObject</span><span class="sxs-lookup"><span data-stu-id="fdb6e-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="fdb6e-174">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-174">{</span></span>
    

28.  <span data-ttu-id="fdb6e-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span><span class="sxs-lookup"><span data-stu-id="fdb6e-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="fdb6e-176">return $resultObject</span><span class="sxs-lookup"><span data-stu-id="fdb6e-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="fdb6e-177">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-177">}</span></span>
    

33.  <span data-ttu-id="fdb6e-178">If ($users. Count -eq 0)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="fdb6e-179">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-179">{</span></span>
    

35.  <span data-ttu-id="fdb6e-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="fdb6e-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="fdb6e-181">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-181">}</span></span>
    

38.  <span data-ttu-id="fdb6e-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="fdb6e-183">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-183">{</span></span>
    

41.  <span data-ttu-id="fdb6e-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="fdb6e-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="fdb6e-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="fdb6e-186">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-186">{</span></span>
    

44.  <span data-ttu-id="fdb6e-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="fdb6e-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="fdb6e-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="fdb6e-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="fdb6e-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="fdb6e-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="fdb6e-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="fdb6e-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="fdb6e-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="fdb6e-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="fdb6e-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="fdb6e-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="fdb6e-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="fdb6e-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="fdb6e-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="fdb6e-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="fdb6e-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="fdb6e-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="fdb6e-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="fdb6e-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="fdb6e-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="fdb6e-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="fdb6e-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="fdb6e-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="fdb6e-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="fdb6e-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="fdb6e-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="fdb6e-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="fdb6e-201">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-201">}</span></span>
    

61.  <span data-ttu-id="fdb6e-202">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-202">}</span></span>
    

63.  <span data-ttu-id="fdb6e-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-203">If ($export)</span></span>
    

64.  <span data-ttu-id="fdb6e-204">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-204">{</span></span>
    

65.  <span data-ttu-id="fdb6e-205">$result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="fdb6e-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="fdb6e-206">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-206">}</span></span>
    

67.  <span data-ttu-id="fdb6e-207">Else</span><span class="sxs-lookup"><span data-stu-id="fdb6e-207">Else</span></span>
    

68.  <span data-ttu-id="fdb6e-208">{</span><span class="sxs-lookup"><span data-stu-id="fdb6e-208">{</span></span>
    

69.  <span data-ttu-id="fdb6e-209">$result</span><span class="sxs-lookup"><span data-stu-id="fdb6e-209">$result</span></span>
    

70.  <span data-ttu-id="fdb6e-210">}</span><span class="sxs-lookup"><span data-stu-id="fdb6e-210">}</span></span>
    

71.  <span data-ttu-id="fdb6e-211">Speichern Sie sie als Windows PowerShell Skriptdatei mithilfe der Dateierweiterung .ps1. Beispielsweise Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="fdb6e-212">Ausführen des Skripts zum Abrufen von Geräteinformationen für ein einzelnes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="fdb6e-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="fdb6e-213">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="fdb6e-214">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="fdb6e-215">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="fdb6e-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="fdb6e-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="fdb6e-217">Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Sie Gerätedetails abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="fdb6e-218">In diesem Beispiel werden Details für bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="fdb6e-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="fdb6e-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="fdb6e-220">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="fdb6e-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="fdb6e-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="fdb6e-222">Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="fdb6e-223">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="fdb6e-224">Ausführen des Skripts zum Abrufen von Geräteinformationen für eine Gruppe von Benutzern</span><span class="sxs-lookup"><span data-stu-id="fdb6e-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="fdb6e-225">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="fdb6e-226">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="fdb6e-227">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="fdb6e-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="fdb6e-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="fdb6e-229">Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Sie Gerätedetails abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="fdb6e-230">In diesem Beispiel werden Details für Benutzer in der Gruppe FinanceStaff angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="fdb6e-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="fdb6e-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="fdb6e-232">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="fdb6e-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="fdb6e-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="fdb6e-234">Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="fdb6e-235">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdb6e-236">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fdb6e-236">Related topics</span></span>

[<span data-ttu-id="fdb6e-237">Microsoft Verbinden wurde eingestellt</span><span class="sxs-lookup"><span data-stu-id="fdb6e-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="fdb6e-238">Übersicht von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fdb6e-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="fdb6e-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="fdb6e-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)