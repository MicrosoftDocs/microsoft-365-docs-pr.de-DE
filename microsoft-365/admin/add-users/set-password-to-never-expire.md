---
title: Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: In diesem Artikel erfahren Sie, wie Sie mit Windows PowerShell einzelne Benutzerkennwörter so festlegen, dass Sie nie ablaufen.
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241569"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="bfdf4-103">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="bfdf4-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="bfdf4-104">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="bfdf4-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="bfdf4-105">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Privatsphäre</a> .</span><span class="sxs-lookup"><span data-stu-id="bfdf4-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="bfdf4-106">Wählen Sie neben **Kennwortrichtlinie** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="bfdf4-107">Wenn Kennwörter auf nie ablaufen festgelegt sind, legen Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="bfdf4-108">Sie erhalten die Option, die Anzahl der Tage anzugeben, bis Kennwörter ablaufen.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="bfdf4-109">Festlegen der Kennwortablaufrichtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="bfdf4-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="bfdf4-110">Ein globaler Administrator für einen Microsoft-clouddienst kann das Microsoft Azure AD-Modul für Windows PowerShell verwenden, um Kennwörter festzulegen, die für bestimmte Benutzer nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="bfdf4-111">Sie können auch Windows PowerShell-Cmdlets verwenden, um die nie ablaufende Konfiguration zu entfernen oder um festzustellen, welche Benutzerkennwörter nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="bfdf4-112">Dieses Handbuch gilt für andere Anbieter wie InTune und Office 365, die sich auch auf Azure AD für Identitäts-und Verzeichnisdienste stützen.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="bfdf4-113">Das Kennwortablaufdatum ist der einzige Teil der Richtlinie, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="bfdf4-114">Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass Sie nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="bfdf4-115">Weitere Informationen zur Verzeichnissynchronisierung finden Sie unter [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="bfdf4-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="bfdf4-116">Überprüfen der Ablaufrichtlinie auf ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="bfdf4-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="bfdf4-117">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="bfdf4-118">Um festzustellen, ob das Kennwort eines einzelnen Benutzers auf nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN (beispielsweise *user@contoso.onmicrosoft.com*) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="bfdf4-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="bfdf4-120">Führen Sie das folgende Cmdlet aus, um die Einstellung **Kennwort läuft nie ab** für alle Benutzer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="bfdf4-121">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in HTML auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires. html** ab</span><span class="sxs-lookup"><span data-stu-id="bfdf4-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="bfdf4-122">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires. CSV** ab</span><span class="sxs-lookup"><span data-stu-id="bfdf4-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="bfdf4-123">Festlegen eines Kennworts zum ablaufen</span><span class="sxs-lookup"><span data-stu-id="bfdf4-123">Set a password to expire</span></span>

<span data-ttu-id="bfdf4-124">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="bfdf4-125">Um das Kennwort eines Benutzers so festzulegen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="bfdf4-126">Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so festzulegen, dass Sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="bfdf4-127">Festlegen eines Kennworts, das nie abläuft</span><span class="sxs-lookup"><span data-stu-id="bfdf4-127">Set a password to never expire</span></span>

<span data-ttu-id="bfdf4-128">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="bfdf4-129">Um das Kennwort eines Benutzers so festzulegen, dass es nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="bfdf4-130">Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation so festzulegen, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="bfdf4-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="bfdf4-131">Kennwörter, `-PasswordPolicies DisablePasswordExpiration` die auf dem Attribut basierend `pwdLastSet` auf "still Age" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="bfdf4-132">Wenn Sie festlegen, dass die Benutzerkennwörter nie ablaufen und dann 90 + Tage vergehen, laufen die Kennwörter ab.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="bfdf4-133">Wenn Sie den `pwdLastSet` Ablauf in `-PasswordPolicies None`ändern, müssen alle Kennwörter, die `pwdLastSet` älter als 90 Tage sind, basierend auf dem Attribut geändert werden, wenn Sie sich das nächste Mal anmelden.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="bfdf4-134">Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="bfdf4-134">This change can affect a large number of users.</span></span> 
