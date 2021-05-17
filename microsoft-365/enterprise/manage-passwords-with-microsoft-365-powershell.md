---
title: Verwalten von Kennwörtern mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Erfahren Sie, wie Sie PowerShell zum Verwalten von Kennwörtern verwenden.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073212"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="93521-103">Verwalten von Kennwörtern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="93521-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="93521-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="93521-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="93521-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center zum Verwalten von Kennwörtern in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93521-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="93521-106">Wenn für einen Befehlsblock in diesem Artikel variablen Werte angegeben werden müssen, verwenden Sie die folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="93521-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="93521-107">Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Editor oder die integrierte PowerShell Script Environment (ISE) ein.</span><span class="sxs-lookup"><span data-stu-id="93521-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="93521-108">Füllen Sie die Variablenwerte aus, und entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="93521-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="93521-109">Führen Sie die Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="93521-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="93521-110">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="93521-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="93521-111">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="93521-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="93521-112">Festlegen eines Kennworts</span><span class="sxs-lookup"><span data-stu-id="93521-112">Set a password</span></span>

<span data-ttu-id="93521-113">Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.</span><span class="sxs-lookup"><span data-stu-id="93521-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="93521-114">Erzwingen, dass ein Benutzer sein Kennwort ändert</span><span class="sxs-lookup"><span data-stu-id="93521-114">Force a user to change their password</span></span>

<span data-ttu-id="93521-115">Verwenden Sie diese Befehle, um ein Kennwort zu setzen und einen Benutzer zum Ändern des neuen Kennworts zu zwingen.</span><span class="sxs-lookup"><span data-stu-id="93521-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="93521-116">Verwenden Sie diese Befehle, um ein Kennwort festlegen und einen Benutzer zwingen, sein neues Kennwort bei der nächsten Anmeldung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="93521-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="93521-117">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93521-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="93521-118">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="93521-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="93521-119">Festlegen eines Kennworts</span><span class="sxs-lookup"><span data-stu-id="93521-119">Set a password</span></span>

<span data-ttu-id="93521-120">Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.</span><span class="sxs-lookup"><span data-stu-id="93521-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="93521-121">Erzwingen, dass ein Benutzer sein Kennwort ändert</span><span class="sxs-lookup"><span data-stu-id="93521-121">Force a user to change their password</span></span>

<span data-ttu-id="93521-122">Verwenden Sie diese Befehle, um einen Benutzer zum Ändern des Kennworts zu zwingen.</span><span class="sxs-lookup"><span data-stu-id="93521-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="93521-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93521-123">See also</span></span>

[<span data-ttu-id="93521-124">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="93521-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="93521-125">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="93521-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="93521-126">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93521-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

