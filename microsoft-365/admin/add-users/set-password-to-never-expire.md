---
title: Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: In diesem Artikel erfahren Sie, wie Sie mit Windows PowerShell einzelne Benutzerkennwörter so festlegen, dass Sie nie ablaufen.
ms.openlocfilehash: 9497dfb5793ddbfc3d6845ec1efba91ad972ea38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646655"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="47c98-103">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="47c98-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="47c98-104">In diesem Artikel wird erklärt, wie Sie ein Kennwort für einen einzelnen Benutzer festlegen, der nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="47c98-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="47c98-105">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="47c98-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="47c98-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="47c98-106">Before you begin</span></span>

<span data-ttu-id="47c98-107">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="47c98-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="47c98-108">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="47c98-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="47c98-109">[Was ist ein Administratorkonto?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="47c98-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="47c98-110">Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="47c98-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="47c98-111">Ein globaler Administrator für einen Microsoft-clouddienst kann das [Azure Active Directory PowerShell für Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) verwenden, um Kennwörter festzulegen, die für bestimmte Benutzer nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="47c98-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="47c98-112">Sie können auch [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) -Cmdlets verwenden, um die nie ablaufende Konfiguration zu entfernen oder zu sehen, welche Benutzerkennwörter nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="47c98-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="47c98-113">Dieses Handbuch gilt für andere Anbieter wie InTune und Microsoft 365, die sich auch auf Azure AD für Identitäts-und Verzeichnisdienste stützen.</span><span class="sxs-lookup"><span data-stu-id="47c98-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="47c98-114">Das Kennwortablaufdatum ist der einzige Teil der Richtlinie, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="47c98-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="47c98-115">Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass Sie nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="47c98-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="47c98-116">Weitere Informationen zur Verzeichnissynchronisierung finden Sie unter [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="47c98-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="47c98-117">Überprüfen der Ablaufrichtlinie auf ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="47c98-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="47c98-118">Weitere Informationen zum Befehl Get-AzureADUser im AzureAD-Modul finden Sie im Referenzartikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="47c98-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="47c98-119">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="47c98-119">Run one of the following commands:</span></span>

- <span data-ttu-id="47c98-120">Um festzustellen, ob das Kennwort eines einzelnen Benutzers auf nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN (beispielsweise *user@contoso.onmicrosoft.com*) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten:</span><span class="sxs-lookup"><span data-stu-id="47c98-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="47c98-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47c98-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="47c98-122">Führen Sie das folgende Cmdlet aus, um die Einstellung **Kennwort läuft nie ab** für alle Benutzer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="47c98-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="47c98-123">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in HTML auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires.html** ab</span><span class="sxs-lookup"><span data-stu-id="47c98-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="47c98-124">So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit dem Namen ab **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="47c98-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="47c98-125">Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation so festzulegen, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="47c98-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="47c98-126">Festlegen eines Kennworts zum ablaufen</span><span class="sxs-lookup"><span data-stu-id="47c98-126">Set a password to expire</span></span>

<span data-ttu-id="47c98-127">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="47c98-127">Run one of the following commands:</span></span>

- <span data-ttu-id="47c98-128">Um das Kennwort eines Benutzers so festzulegen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="47c98-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="47c98-129">Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so festzulegen, dass Sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="47c98-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="47c98-130">Benutzerkonten, die mit dem `-PasswordPolicies DisablePasswordExpiration` Parameter "still Age" basierend auf dem `pwdLastSet` Benutzerkonto Attribut konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="47c98-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="47c98-131">Wenn Sie beispielsweise festlegen, dass Benutzerkennwörter nie ablaufen und dann 90 oder mehr Tage vergehen, verfallen die Kennwörter weiterhin.</span><span class="sxs-lookup"><span data-stu-id="47c98-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="47c98-132">Basierend auf dem `pwdLastSet` Benutzerkonto Attribut müssen bei Benutzerkonten, die mit dem Parameter konfiguriert sind `-PasswordPolicies None` , alle Kennwörter, die `pwdLastSet` älter als 90 Tage sind, vom Benutzer geändert werden, wenn Sie sich das nächste Mal anmelden. Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="47c98-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="47c98-133">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="47c98-133">Related content</span></span>

[<span data-ttu-id="47c98-134">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="47c98-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="47c98-135">Zurücksetzen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="47c98-135">Reset passwords</span></span>](../add-users/reset-passwords.md)