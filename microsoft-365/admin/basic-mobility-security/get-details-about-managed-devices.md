---
title: Erhalten von Details zu verwalteten Basic Mobility and Security-Geräten
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
description: Verwenden Windows PowerShell, um Details zu Grundlegenden Mobilitäts- und Sicherheitsgeräten in Ihrer Organisation zu erhalten.
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904252"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="6be9d-103">Erhalten von Details zu verwalteten Basic Mobility and Security-Geräten</span><span class="sxs-lookup"><span data-stu-id="6be9d-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="6be9d-104">In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation zu erhalten, die Sie für Grundlegende Mobilität und Sicherheit eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="6be9d-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="6be9d-105">Hier finden Sie eine Aufschlüsselung der verfügbaren Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="6be9d-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="6be9d-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="6be9d-106">**Detail**</span></span>|<span data-ttu-id="6be9d-107">**Suchen in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6be9d-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="6be9d-108">Das Gerät ist in Basic Mobility and Security registriert.</span><span class="sxs-lookup"><span data-stu-id="6be9d-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="6be9d-109">Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="6be9d-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="6be9d-110">Der Wert des *isManaged-Parameters*   ist:</span><span class="sxs-lookup"><span data-stu-id="6be9d-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="6be9d-111">**True**= Gerät wird registriert.</span><span class="sxs-lookup"><span data-stu-id="6be9d-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="6be9d-112">**False**= Gerät ist nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="6be9d-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="6be9d-113">Das Gerät ist mit den Gerätesicherheitsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="6be9d-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="6be9d-114">Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6be9d-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="6be9d-115">Der Wert des *isCompliant-Parameters*   ist:</span><span class="sxs-lookup"><span data-stu-id="6be9d-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="6be9d-116">**True**   = Das Gerät ist richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="6be9d-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="6be9d-117">**False**   = Das Gerät ist nicht richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="6be9d-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende PowerShell-Parameter für Mobilität und Sicherheit":::

>[!NOTE]
><span data-ttu-id="6be9d-119">Die Befehle und Skripts in diesem Artikel geben auch Details zu allen von Microsoft Intune verwalteten [Geräten zurück.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="6be9d-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6be9d-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="6be9d-120">Before you begin</span></span>

<span data-ttu-id="6be9d-121">Es gibt einige Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6be9d-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6be9d-122">Schritt 1: Herunterladen und Installieren des Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be9d-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6be9d-123">Weitere Informationen zu diesen Schritten finden Sie unter [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="6be9d-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="6be9d-124">Wechseln Sie [zu Microsoft Online Services Sign-In Assistant for IT Professionals RTWl,](https://www.microsoft.com/download/details.aspx?id=41950)und wählen Sie Download for Microsoft Online Services    **Sign-in Assistant aus.**</span><span class="sxs-lookup"><span data-stu-id="6be9d-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="6be9d-125">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="6be9d-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="6be9d-126">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="6be9d-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="6be9d-127">Führen Sie den BefehlInstall-Module MSOnline aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="6be9d-128">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6be9d-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="6be9d-129">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6be9d-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="6be9d-130">Schließen Sie nach der Installation das PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="6be9d-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="6be9d-131">Schritt 2: Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="6be9d-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="6be9d-132">Führen Sie im Windows Azure Active Directory Module for Windows PowerShell den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="6be9d-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="6be9d-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="6be9d-134">Geben Sie Windows PowerShell Benutzernamen und Kennwort für Ihr globales Microsoft 365-Administratorkonto ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="6be9d-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="6be9d-135">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-135">Run the following command.</span></span>

    <span data-ttu-id="6be9d-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="6be9d-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="6be9d-137">Schritt 3: Stellen Sie sicher, dass Sie PowerShell-Skripts ausführen können</span><span class="sxs-lookup"><span data-stu-id="6be9d-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="6be9d-138">Sie können diesen Schritt überspringen, wenn Sie bereits zum Ausführen von PowerShell-Skripts eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="6be9d-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="6be9d-139">Zum Ausführen des Get-MsolUserDeviceComplianceStatus.ps1 müssen Sie die Ausführung von PowerShell-Skripts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6be9d-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="6be9d-140">Wählen Sie auf Ihrem Windows Desktop **Start** aus, und geben Sie dann Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be9d-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="6be9d-141">Klicken Sie mit der rechten Windows PowerShell, und wählen Sie **dann Als Administrator ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="6be9d-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="6be9d-142">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-142">Run the following command.</span></span>

    <span data-ttu-id="6be9d-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="6be9d-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="6be9d-144">Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6be9d-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="6be9d-145">**Führen Sie Get-MsolDevice cmdlet aus, um Details für alle Geräte in Ihrer Organisation anzuzeigen**</span><span class="sxs-lookup"><span data-stu-id="6be9d-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="6be9d-146">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be9d-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="6be9d-147">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-147">Run the following command.</span></span>

    <span data-ttu-id="6be9d-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="6be9d-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="6be9d-149">Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="6be9d-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="6be9d-150">Ausführen eines Skripts zum Anzeigen von Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="6be9d-150">Run a script to get device details</span></span>

<span data-ttu-id="6be9d-151">Speichern Sie zunächst das Skript auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="6be9d-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="6be9d-152">Kopieren Sie den folgenden Text, und fügen Sie ihn in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="6be9d-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="6be9d-153">Param (</span><span class="sxs-lookup"><span data-stu-id="6be9d-153">param (</span></span>

3.  <span data-ttu-id="6be9d-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="6be9d-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="6be9d-155">[Switch]$export,</span><span class="sxs-lookup"><span data-stu-id="6be9d-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="6be9d-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="6be9d-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="6be9d-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span><span class="sxs-lookup"><span data-stu-id="6be9d-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="6be9d-158">)</span><span class="sxs-lookup"><span data-stu-id="6be9d-158">)</span></span>

9.  <span data-ttu-id="6be9d-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="6be9d-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="6be9d-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="6be9d-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="6be9d-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="6be9d-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="6be9d-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="6be9d-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="6be9d-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="6be9d-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="6be9d-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="6be9d-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="6be9d-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="6be9d-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="6be9d-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="6be9d-172">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-172">}</span></span>
    

25.  <span data-ttu-id="6be9d-173">funktion createResultObject</span><span class="sxs-lookup"><span data-stu-id="6be9d-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="6be9d-174">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-174">{</span></span>
    

28.  <span data-ttu-id="6be9d-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span><span class="sxs-lookup"><span data-stu-id="6be9d-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="6be9d-176">Rückgabe $resultObject</span><span class="sxs-lookup"><span data-stu-id="6be9d-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="6be9d-177">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-177">}</span></span>
    

33.  <span data-ttu-id="6be9d-178">If ($users. Count -eq 0)</span><span class="sxs-lookup"><span data-stu-id="6be9d-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="6be9d-179">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-179">{</span></span>
    

35.  <span data-ttu-id="6be9d-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="6be9d-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="6be9d-181">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-181">}</span></span>
    

38.  <span data-ttu-id="6be9d-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="6be9d-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="6be9d-183">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-183">{</span></span>
    

41.  <span data-ttu-id="6be9d-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6be9d-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="6be9d-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="6be9d-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="6be9d-186">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-186">{</span></span>
    

44.  <span data-ttu-id="6be9d-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="6be9d-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="6be9d-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="6be9d-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="6be9d-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="6be9d-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="6be9d-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="6be9d-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="6be9d-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="6be9d-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="6be9d-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="6be9d-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="6be9d-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="6be9d-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="6be9d-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="6be9d-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="6be9d-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="6be9d-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="6be9d-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6be9d-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="6be9d-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="6be9d-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="6be9d-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="6be9d-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="6be9d-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="6be9d-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="6be9d-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="6be9d-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="6be9d-201">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-201">}</span></span>
    

61.  <span data-ttu-id="6be9d-202">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-202">}</span></span>
    

63.  <span data-ttu-id="6be9d-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="6be9d-203">If ($export)</span></span>
    

64.  <span data-ttu-id="6be9d-204">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-204">{</span></span>
    

65.  <span data-ttu-id="6be9d-205">$result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="6be9d-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="6be9d-206">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-206">}</span></span>
    

67.  <span data-ttu-id="6be9d-207">Else</span><span class="sxs-lookup"><span data-stu-id="6be9d-207">Else</span></span>
    

68.  <span data-ttu-id="6be9d-208">{</span><span class="sxs-lookup"><span data-stu-id="6be9d-208">{</span></span>
    

69.  <span data-ttu-id="6be9d-209">$result</span><span class="sxs-lookup"><span data-stu-id="6be9d-209">$result</span></span>
    

70.  <span data-ttu-id="6be9d-210">}</span><span class="sxs-lookup"><span data-stu-id="6be9d-210">}</span></span>
    

71.  <span data-ttu-id="6be9d-211">Speichern Sie sie als Windows PowerShell skriptdatei mithilfe der Dateierweiterung .ps1; Beispiel: Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="6be9d-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="6be9d-212">Ausführen des Skripts zum Erhalten von Geräteinformationen für ein einzelnes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="6be9d-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="6be9d-213">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be9d-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6be9d-214">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="6be9d-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="6be9d-215">Wenn Sie sie beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="6be9d-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="6be9d-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="6be9d-217">Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Sie Gerätedetails erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6be9d-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="6be9d-218">In diesem Beispiel werden Details für bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="6be9d-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="6be9d-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="6be9d-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="6be9d-220">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="6be9d-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="6be9d-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="6be9d-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="6be9d-222">Die Informationen werden als CSV-Datei in Ihren Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="6be9d-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="6be9d-223">Sie können zusätzliche Parameter verwenden, um den Dateinamen und pfad der CSV anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6be9d-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="6be9d-224">Ausführen des Skripts zum Erhalten von Geräteinformationen für eine Gruppe von Benutzern</span><span class="sxs-lookup"><span data-stu-id="6be9d-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="6be9d-225">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be9d-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6be9d-226">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="6be9d-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="6be9d-227">Wenn Sie sie beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6be9d-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="6be9d-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="6be9d-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="6be9d-229">Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Sie Gerätedetails erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6be9d-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="6be9d-230">In diesem Beispiel werden Details für Benutzer in der Gruppe "FinanceStaff" abfragt.</span><span class="sxs-lookup"><span data-stu-id="6be9d-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="6be9d-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="6be9d-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="6be9d-232">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="6be9d-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="6be9d-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="6be9d-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="6be9d-234">Die Informationen werden als CSV-Datei in Ihren Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="6be9d-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="6be9d-235">Sie können zusätzliche Parameter verwenden, um den Dateinamen und pfad der CSV anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6be9d-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6be9d-236">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6be9d-236">Related topics</span></span>

[<span data-ttu-id="6be9d-237">Microsoft Connect wurde eingestellt</span><span class="sxs-lookup"><span data-stu-id="6be9d-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="6be9d-238">Übersicht von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6be9d-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="6be9d-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="6be9d-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)