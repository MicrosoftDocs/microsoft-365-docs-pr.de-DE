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
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228171"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="80564-103">Abrufen von Details zu von Basic Mobility and Security verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="80564-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="80564-104">In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation zu erhalten, die Sie für Grundlegende Mobilität und Sicherheit eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="80564-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="80564-105">Hier ist eine Aufschlüsselung der verfügbaren Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="80564-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="80564-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="80564-106">**Detail**</span></span>|<span data-ttu-id="80564-107">**Suchen in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="80564-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="80564-108">Das Gerät ist in Basic Mobility and Security registriert.</span><span class="sxs-lookup"><span data-stu-id="80564-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="80564-109">Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="80564-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="80564-110">Der Wert des *isManaged-Parameters*   lautet:</span><span class="sxs-lookup"><span data-stu-id="80564-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="80564-111">**True**= Gerät ist registriert.</span><span class="sxs-lookup"><span data-stu-id="80564-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="80564-112">**False**= Gerät ist nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="80564-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="80564-113">Das Gerät ist mit Ihren Gerätesicherheitsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="80564-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="80564-114">Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="80564-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="80564-115">Der Wert des *isCompliant-Parameters*   lautet:</span><span class="sxs-lookup"><span data-stu-id="80564-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="80564-116">**True**   = Das Gerät ist richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="80564-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="80564-117">**False**   = Das Gerät ist nicht richtlinienkonform.</span><span class="sxs-lookup"><span data-stu-id="80564-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende PowerShell-Parameter für Mobilität und Sicherheit":::

> [!NOTE]
> <span data-ttu-id="80564-119">Die Befehle und Skripts in diesem Artikel geben auch Details zu allen Geräten [zurück, die](https://www.microsoft.com/cloud-platform/microsoft-intune)von Microsoft Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="80564-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80564-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="80564-120">Before you begin</span></span>

<span data-ttu-id="80564-121">Es gibt einige Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="80564-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="80564-122">Schritt 1: Herunterladen und Installieren des Azure Active Directory Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80564-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="80564-123">Weitere Informationen zu diesen Schritten finden Sie unter [Verbinden zum Microsoft 365 mit PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="80564-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="80564-124">Wechseln Sie zu [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl,](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)und wählen Sie    **"Download for Microsoft Online Services Sign-in Assistant"** aus.</span><span class="sxs-lookup"><span data-stu-id="80564-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="80564-125">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="80564-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="80564-126">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="80564-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="80564-127">Führen Sie den Befehl `Install-Module MSOnline` aus.</span><span class="sxs-lookup"><span data-stu-id="80564-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="80564-128">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="80564-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="80564-129">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="80564-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="80564-130">Schließen Sie nach der Installation das PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="80564-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="80564-131">Schritt 2: Verbinden zu Ihrem Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="80564-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="80564-132">Führen Sie im Windows Azure Active Directory Modul für Windows PowerShell den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="80564-133">Geben Sie im Dialogfeld Windows PowerShell Anmeldeinformationsanforderung den Benutzernamen und das Kennwort für Ihr Microsoft 365 globale Administratorkonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="80564-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="80564-134">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="80564-135">Schritt 3: Stellen Sie sicher, dass Sie PowerShell-Skripts ausführen können</span><span class="sxs-lookup"><span data-stu-id="80564-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="80564-136">Sie können diesen Schritt überspringen, wenn Sie bereits für die Ausführung von PowerShell-Skripts eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="80564-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="80564-137">Zum Ausführen des Get-MsolUserDeviceComplianceStatus.ps1 Skripts müssen Sie die Ausführung von PowerShell-Skripts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80564-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="80564-138">Wählen Sie im Windows Desktop die Option **"Start"** aus, und geben Sie dann Windows PowerShell ein.</span><span class="sxs-lookup"><span data-stu-id="80564-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="80564-139">Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und wählen Sie dann **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="80564-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="80564-140">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="80564-141">Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="80564-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="80564-142">Führen Sie das Cmdlet Get-MsolDevice aus, um Details für alle Geräte in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="80564-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="80564-143">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80564-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="80564-144">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="80564-145">Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="80564-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="80564-146">Ausführen eines Skripts zum Abrufen von Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="80564-146">Run a script to get device details</span></span>

<span data-ttu-id="80564-147">Speichern Sie zunächst das Skript auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="80564-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="80564-148">Kopieren Sie den folgenden Text, und fügen Sie ihn in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="80564-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="80564-149">Speichern Sie sie als Windows PowerShell Skriptdatei, indem Sie die Dateierweiterung .ps1 verwenden. Beispielsweise Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="80564-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="80564-150">Ausführen des Skripts zum Abrufen von Geräteinformationen für ein einzelnes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="80564-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="80564-151">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80564-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="80564-152">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="80564-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="80564-153">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="80564-154">Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Sie Gerätedetails abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="80564-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="80564-155">In diesem Beispiel werden Details für bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="80564-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="80564-156">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="80564-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="80564-157">Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="80564-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="80564-158">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="80564-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="80564-159">Ausführen des Skripts zum Abrufen von Geräteinformationen für eine Gruppe von Benutzern</span><span class="sxs-lookup"><span data-stu-id="80564-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="80564-160">Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80564-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="80564-161">Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="80564-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="80564-162">Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80564-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="80564-163">Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Sie Gerätedetails abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="80564-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="80564-164">In diesem Beispiel werden Details für Benutzer in der Gruppe FinanceStaff angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80564-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="80564-165">Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="80564-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="80564-166">Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert.</span><span class="sxs-lookup"><span data-stu-id="80564-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="80564-167">Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="80564-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80564-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80564-168">Related topics</span></span>

[<span data-ttu-id="80564-169">Microsoft Verbinden wurde eingestellt</span><span class="sxs-lookup"><span data-stu-id="80564-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="80564-170">Übersicht von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="80564-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="80564-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="80564-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
