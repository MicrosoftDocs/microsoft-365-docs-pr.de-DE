---
title: Anzeigen von lizenzierten und nicht lizenzierten Microsoft 365-Benutzern mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: In diesem Artikel wird die Verwendung von PowerShell zum Anzeigen von lizenzierten und nicht lizenzierten Microsoft 365-Benutzerkonten erläutert.
ms.openlocfilehash: 8a99ba2a80f1d814ec5268c4f8f479837eb54dc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690462"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Anzeigen von lizenzierten und nicht lizenzierten Microsoft 365-Benutzern mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Benutzerkonten in Ihrer Microsoft 365-Organisation haben möglicherweise einige, alle oder keine der verfügbaren Lizenzen, die Ihnen aus den in Ihrer Organisation verfügbaren Lizenzierungs Plänen zugewiesen sind. Sie können PowerShell für Microsoft 365 verwenden, um die lizenzierten und nicht lizenzierten Benutzer in Ihrer Organisation schnell zu finden.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Führen Sie den folgenden Befehl aus, um die Liste aller Benutzerkonten in Ihrer Organisation anzuzeigen, denen keine Ihrer Lizenzierungs Pläne zugewiesen wurden (nicht lizenzierte Benutzer):
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Führen Sie den folgenden Befehl aus, um die Liste aller Benutzerkonten in Ihrer Organisation anzuzeigen, denen Ihre Lizenzierungs Pläne zugewiesen wurden (lizenzierte Benutzer):
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Wenn Sie alle Benutzer in Ihrem Abonnement auflisten möchten, verwenden Sie den `Get-AzureAdUser -All $true` Befehl.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Um die Liste aller Benutzerkonten und deren Lizenzierungsstatus in Ihrer Organisation anzuzeigen, führen Sie den folgenden Befehl in PowerShell aus:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Führen Sie den folgenden Befehl aus, um die Liste aller nicht lizenzierten Benutzerkonten in Ihrer Organisation anzuzeigen:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Führen Sie den folgenden Befehl aus, um die Liste aller lizenzierten Benutzerkonten in Ihrer Organisation anzuzeigen:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
