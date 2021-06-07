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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Abrufen von Details zu von Basic Mobility and Security verwalteten Geräten

In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation zu erhalten, die Sie für Grundlegende Mobilität und Sicherheit eingerichtet haben.

Hier ist eine Aufschlüsselung der verfügbaren Gerätedetails.

|**Detail**|**Suchen in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Das Gerät ist in Basic Mobility and Security registriert. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security](enroll-your-mobile-device.md)|Der Wert des *isManaged-Parameters*   lautet:<br/>**True**= Gerät ist registriert.<br/>**False**= Gerät ist nicht registriert. |
|Das Gerät ist mit Ihren Gerätesicherheitsrichtlinien kompatibel. Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien](create-device-security-policies.md)|Der Wert des *isCompliant-Parameters*   lautet:<br/>**True**   = Das Gerät ist richtlinienkonform.<br/>**False**   = Das Gerät ist nicht richtlinienkonform.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende PowerShell-Parameter für Mobilität und Sicherheit":::

>[!NOTE]
>Die Befehle und Skripts in diesem Artikel geben auch Details zu allen Geräten [zurück, die](https://www.microsoft.com/cloud-platform/microsoft-intune)von Microsoft Intune verwaltet werden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Es gibt einige Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Schritt 1: Herunterladen und Installieren des Azure Active Directory Moduls für Windows PowerShell

Weitere Informationen zu diesen Schritten finden Sie unter [Verbinden zum Microsoft 365 mit PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Wechseln Sie zu [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl,](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)und wählen Sie    **"Download for Microsoft Online Services Sign-in Assistant" aus.**

2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:

    1. Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.  

    2. Führen Sie den BefehlInstall-Module MSOnline aus.

    3. Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.

    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.

    5. Schließen Sie nach der Installation das PowerShell-Befehlsfenster.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Schritt 2: Verbinden zu Ihrem Microsoft 365-Abonnement

1. Führen Sie im Windows Azure Active Directory Modul für Windows PowerShell den folgenden Befehl aus.  

    $UserCredential = Get-Credential

2. Geben Sie im Dialogfeld Windows PowerShell Anmeldeinformationsanforderung den Benutzernamen und das Kennwort für Ihr Microsoft 365 globale Administratorkonto ein, und wählen Sie dann **OK** aus.

3. Führen Sie den folgenden Befehl aus.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Schritt 3: Stellen Sie sicher, dass Sie PowerShell-Skripts ausführen können

>[!NOTE]
>Sie können diesen Schritt überspringen, wenn Sie bereits für die Ausführung von PowerShell-Skripts eingerichtet sind.

Um das skript Get-MsolUserDeviceComplianceStatus.ps1 ausführen zu können, müssen Sie die Ausführung von PowerShell-Skripts aktivieren.

1. Wählen Sie im Windows Desktop die Option **"Start"** aus, und geben Sie dann Windows PowerShell ein. Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und wählen Sie dann **als Administrator ausführen** aus.

2. Führen Sie den folgenden Befehl aus.

    Set-ExecutionPolicy RemoteSigned

3. Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie dann die EINGABETASTE.

**Führen Sie das Cmdlet Get-MsolDevice aus, um Details für alle Geräte in Ihrer Organisation anzuzeigen.**

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.  

2. Führen Sie den folgenden Befehl aus.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

## <a name="run-a-script-to-get-device-details"></a>Ausführen eines Skripts zum Abrufen von Gerätedetails

Speichern Sie zunächst das Skript auf Ihrem Computer.

1. Kopieren Sie den folgenden Text, und fügen Sie ihn in Editor ein.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  return $resultObject
    

31.  }
    

33.  If ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Speichern Sie sie als Windows PowerShell Skriptdatei mithilfe der Dateierweiterung .ps1. Beispielsweise Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ausführen des Skripts zum Abrufen von Geräteinformationen für ein einzelnes Benutzerkonto

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.
    
2. Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben. Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.
    
    cd C:\PS-Scripts

3. Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Sie Gerätedetails abrufen möchten. In diesem Beispiel werden Details für bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert. Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ausführen des Skripts zum Abrufen von Geräteinformationen für eine Gruppe von Benutzern

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.
    
2. Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben. Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.   

    cd C:\PS-Scripts

3. Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Sie Gerätedetails abrufen möchten. In diesem Beispiel werden Details für Benutzer in der Gruppe FinanceStaff angezeigt. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Die Informationen werden als CSV-Datei in Ihre Windows Desktop exportiert. Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV-Datei anzugeben.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft Verbinden wurde eingestellt](/collaborate/connect-redirect)

[Übersicht von grundlegender Mobilität und Sicherheit](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)