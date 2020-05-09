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
ms.openlocfilehash: 3d5d65f687a5ed02e0e20ff77482f7bef5b6b695
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173496"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="3a816-103">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="3a816-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="3a816-104">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="3a816-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="3a816-105">Wechseln Sie im Admin Center zur Seite **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Einstellungen.</a></span><span class="sxs-lookup"><span data-stu-id="3a816-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="3a816-106">Wählen Sie oben auf der Seite Einstellungen die Option **Sicherheit & Datenschutz**aus.</span><span class="sxs-lookup"><span data-stu-id="3a816-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="3a816-107">Wählen Sie **Kennwortablaufrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="3a816-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="3a816-108">Wenn Kennwörter auf nie ablaufen festgelegt sind, aktivieren Sie das Kontrollkästchen neben **Kennwort für Benutzer festlegen, um nach einer bestimmten Anzahl von Tagen zu verfallen**.</span><span class="sxs-lookup"><span data-stu-id="3a816-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="3a816-109">Sie erhalten die Option, die Anzahl der Tage anzugeben, bis Kennwörter ablaufen.</span><span class="sxs-lookup"><span data-stu-id="3a816-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="3a816-110">Festlegen der Kennwortablaufrichtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="3a816-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="3a816-111">Ein globaler Administrator für einen Microsoft-clouddienst kann das [Azure Active Directory PowerShell für Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) verwenden, um Kennwörter festzulegen, die für bestimmte Benutzer nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="3a816-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="3a816-112">Sie können auch [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) -Cmdlets verwenden, um die nie ablaufende Konfiguration zu entfernen oder zu sehen, welche Benutzerkennwörter nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="3a816-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="3a816-113">Dieses Handbuch gilt für andere Anbieter wie InTune und Microsoft 365, die sich auch auf Azure AD für Identitäts-und Verzeichnisdienste stützen.</span><span class="sxs-lookup"><span data-stu-id="3a816-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="3a816-114">Das Kennwortablaufdatum ist der einzige Teil der Richtlinie, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a816-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="3a816-115">Weitere Informationen zum Azure AD PowerShell für Graph finden Sie unter [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="3a816-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="3a816-116">Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass Sie nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="3a816-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="3a816-117">Weitere Informationen zur Verzeichnissynchronisierung finden Sie unter [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="3a816-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="3a816-118">Überprüfen der Ablaufrichtlinie auf ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="3a816-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="3a816-119">Weitere Informationen zum Befehl Get-AzureADUser im AzureAD-Modul finden Sie im Referenzartikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="3a816-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="3a816-120">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="3a816-120">Run one of the following commands:</span></span>

- <span data-ttu-id="3a816-121">Um festzustellen, ob das Kennwort eines einzelnen Benutzers auf nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN (beispielsweise *user@contoso.onmicrosoft.com*) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten:</span><span class="sxs-lookup"><span data-stu-id="3a816-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="3a816-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3a816-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="3a816-123">Führen Sie das folgende Cmdlet aus, um die Einstellung **Kennwort läuft nie ab** für alle Benutzer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3a816-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="3a816-124">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in HTML auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires. html** ab</span><span class="sxs-lookup"><span data-stu-id="3a816-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="3a816-125">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires. CSV** ab</span><span class="sxs-lookup"><span data-stu-id="3a816-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="3a816-126">Festlegen eines Kennworts zum ablaufen</span><span class="sxs-lookup"><span data-stu-id="3a816-126">Set a password to expire</span></span>

<span data-ttu-id="3a816-127">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="3a816-127">Run one of the following commands:</span></span>

- <span data-ttu-id="3a816-128">Um das Kennwort eines Benutzers so festzulegen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="3a816-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="3a816-129">Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so festzulegen, dass Sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="3a816-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="3a816-130">Festlegen eines Kennworts, das nie abläuft</span><span class="sxs-lookup"><span data-stu-id="3a816-130">Set a password to never expire</span></span>

<span data-ttu-id="3a816-131">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="3a816-131">Run one of the following commands:</span></span>

- <span data-ttu-id="3a816-132">Um das Kennwort eines Benutzers so festzulegen, dass es nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="3a816-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="3a816-133">Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation so festzulegen, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="3a816-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="3a816-134">Kennwörter, `-PasswordPolicies DisablePasswordExpiration` die auf dem Attribut basierend `pwdLastSet` auf "still Age" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3a816-134">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="3a816-135">Wenn Sie festlegen, dass die Benutzerkennwörter nie ablaufen und dann 90 + Tage vergehen, laufen die Kennwörter ab.</span><span class="sxs-lookup"><span data-stu-id="3a816-135">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="3a816-136">Wenn Sie den `pwdLastSet` Ablauf in `-PasswordPolicies None`ändern, müssen alle Kennwörter, die `pwdLastSet` älter als 90 Tage sind, basierend auf dem Attribut geändert werden, wenn Sie sich das nächste Mal anmelden.</span><span class="sxs-lookup"><span data-stu-id="3a816-136">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="3a816-137">Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="3a816-137">This change can affect a large number of users.</span></span>
