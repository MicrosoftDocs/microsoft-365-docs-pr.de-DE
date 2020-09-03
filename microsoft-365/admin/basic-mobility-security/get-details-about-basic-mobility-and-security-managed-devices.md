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
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336889"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Abrufen von Details zu grundlegenden Mobilitäts-und Sicherheits verwalteten Geräten

In diesem Artikel erfahren Sie, wie Sie Windows PowerShell verwenden, um Details zu den Geräten in Ihrer Organisation abzurufen, die Sie für einfache Mobilität und Sicherheit eingerichtet haben.

Im folgenden finden Sie eine Aufschlüsselung der Gerätedetails, die Ihnen zur Verfügung stehen.

|**Detail**|**Worauf Sie in PowerShell achten sollten**|
|:----------------|:------------------------------------------------------------------------------|
|Das Gerät ist in Basic Mobility and Security eingeschrieben. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)|Der Wert des *IsManaged*-   Parameters lautet:<br/>**True**= Gerät ist registriert.<br/>**False**= Gerät ist nicht registriert. |
|Gerät ist mit ihren Gerätesicherheitsrichtlinien kompatibel. Weitere Informationen finden Sie unter [Create Device Security Policies](create-device-security-policies-in-basic-mmobility-and-security.md)|Der Wert des *isCompliant*-   Parameters lautet:<br/>**True**   = Gerät ist mit Richtlinien kompatibel.<br/>**False**   = Gerät ist nicht konform mit Richtlinien.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundlegende Mobilitäts-und Sicherheits-PowerShell-Parameter":::

>[!NOTE]
>Die Befehle und Skripts in diesem Artikel geben auch Details zu Geräten zurück, die von [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune)verwaltet werden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Es gibt ein paar Dinge, die Sie einrichten müssen, um die in diesem Artikel beschriebenen Befehle und Skripts auszuführen.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Schritt 1: herunterladen und Installieren des Azure Active Directory-Moduls für Windows PowerShell

Weitere Informationen zu diesen Schritten finden Sie unter [Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Wechseln Sie zu [Microsoft Online Services-Anmeldeassistent für IT-Experten RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   , und wählen Sie  **Download für den Microsoft Online Services-Anmelde-Assistenten**aus.   

2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:   

    1. Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene.  

    2. Führen Sie den BefehlInstall-Module MSOnline aus.
    
    3. Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.   

    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie Y ein, und drücken Sie die EINGABETASTE.   

    5. Schließen Sie nach der Installation das PowerShell-Befehlsfenster.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Schritt 2: Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement

1. Führen Sie im Windows Azure Active Directory-Modul für Windows PowerShell den folgenden Befehl aus.  

    $UserCredential = Get-Credential

2. Geben Sie im Dialogfeld Windows PowerShell Anmeldeinformationen den Benutzernamen und das Kennwort für das globale Administratorkonto von Microsoft 365 ein, und wählen Sie dann **OK**aus.
    
3. Führen Sie den folgenden Befehl aus.
    
    Connect-MsolService – Anmeldeinformationen $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Schritt 3: sicherstellen, dass PowerShell-Skripts ausgeführt werden können

>[!NOTE]
>Sie können diesen Schritt überspringen, wenn Sie bereits für die Ausführung von PowerShell-Skripts eingerichtet sind.

Zum Ausführen des Get-MsolUserDeviceComplianceStatus.ps1 Skripts müssen Sie die Ausführung von PowerShell-Skripts aktivieren.

1. Wählen Sie auf dem Windows-Desktop **Start**aus, und geben Sie dann Windows PowerShell ein. Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und wählen Sie dann **als Administrator ausführen**aus.

2. Führen Sie den folgenden Befehl aus.
    
    Gruppe-ExecutionPolicy RemoteSigned

3. Wenn Sie dazu aufgefordert werden, geben Sie Y ein, und drücken Sie die EINGABETASTE.
    
**Ausführen des Cmdlets Get-MsolDevice zum Anzeigen von Details für alle Geräte in Ihrer Organisation**

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.  

2. Führen Sie den folgenden Befehl aus.
    
    Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}

Weitere Beispiele finden Sie unter  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Ausführen eines Skripts zum Abrufen von Gerätedetails

Speichern Sie zunächst das Skript auf Ihrem Computer.

1. Kopieren Sie den folgenden Text, und fügen Sie ihn in Notepad ein.  

2.  param
    

3.  [PSObject []] $users = @ (),
    

4.  [Switch] $Export,
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",
    

6.  [String] $exportPath = [Environment]:: GetFolderPath ("Desktop")
    

7.  )
    

9.  [System. Collections. IDictionary] $Script: Schema = @ {
    

11.  Geräte-Nr = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  Funktion createresultobject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-typeName PSObject-Property $Script: Schema
    

30.  zurück $resultObject
    

31.  }
    

33.  If ($users. Count-EQ 0)
    

34.  {
    

35.  $Users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject] $Devices = Get-msoldevice-RegisteredOwnerUpn $u. userPrincipalName
    

42.  foreach ($d in $Devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createresultobject
    

45.  $deviceResult. Device-Nr = $d. Device-Nr
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged
    

52.  $deviceResult. DeviceObjectId = $d. ObjectID
    

53.  $deviceResult. RegisteredOwnerUpn = $u. userPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectID
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($Export)
    

64.  {
    

65.  $result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Speichern Sie es als Windows PowerShell Skriptdatei mit der Dateierweiterung. ps1; Beispiel: Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ausführen des Skripts zum Abrufen von Geräteinformationen für ein einzelnes Benutzerkonto

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.
    
2. Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben. Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.
    
    CD-C:\PS-Scripts

3. Führen Sie den folgenden Befehl aus, um den Benutzer zu identifizieren, für den Gerätedetails abgerufen werden sollen. In diesem Beispiel werden Details für Bar@example.com abgerufen.
    
    $u = get-MsolUser-userPrincipalName Bar@example.com

4. Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.

    .\Get-MsolUserDeviceComplianceStatus.ps1-Benutzer $u-Export

Die Informationen werden als CSV-Datei auf Ihren Windows-Desktop exportiert. Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV anzugeben.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ausführen des Skripts zum Abrufen von Geräteinformationen für eine Gruppe von Benutzern

1. Öffnen Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell.
    
2. Wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben. Wenn Sie es beispielsweise in C:\PS-Scripts gespeichert haben, führen Sie den folgenden Befehl aus.   

    CD-C:\PS-Scripts

3. Führen Sie den folgenden Befehl aus, um die Gruppe zu identifizieren, für die Gerätedetails abgerufen werden sollen. In diesem Beispiel werden Details für Benutzer in der FinanceStaff-Gruppe abgerufen. 

    $u = get-MsolGroupMember-suchbare "FinanceStaff" | % {Get-MsolUser-ObjectID $ _. ObjectID

4. Führen Sie den folgenden Befehl aus, um das Skript zu initiieren.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-Benutzer $u-Export

Die Informationen werden als CSV-Datei auf Ihren Windows-Desktop exportiert. Sie können zusätzliche Parameter verwenden, um den Dateinamen und den Pfad der CSV anzugeben.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft Connect wurde zurückgezogen.](https://docs.microsoft.com/collaborate/connect-redirect)

[Übersicht über grundlegende Mobilität und Sicherheit](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)