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
description: Melden Sie sich bei Ihrem Microsoft 365 Administratorkonto an, um festlegen, dass einige einzelne Benutzerkennwörter niemals mit Windows PowerShell ablaufen.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571925"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="7bb16-103">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="7bb16-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="7bb16-104">In diesem Artikel wird erläutert, wie Sie ein Kennwort festlegen, damit ein einzelner Benutzer nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="7bb16-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="7bb16-105">Sie müssen diese Schritte mit PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7bb16-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="7bb16-106">Before you begin</span></span>

<span data-ttu-id="7bb16-107">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7bb16-108">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="7bb16-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="7bb16-109">[Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7bb16-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="7bb16-110">Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7bb16-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7bb16-111">Ein globaler Administrator für einen Microsoft-Clouddienst kann die [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) verwenden, um Kennwörter festzulegen, die nicht für bestimmte Benutzer ablaufen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="7bb16-112">Sie können [azureAD-Cmdlets](/powershell/module/Azuread) auch verwenden, um die nicht ablaufende Konfiguration zu entfernen oder um zu sehen, welche Benutzerkennwörter nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="7bb16-113">Dieses Handbuch gilt für andere Anbieter, z. B. Intune und Microsoft 365, die sich für Identitäts- und Verzeichnisdienste auch auf Azure AD verlassen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="7bb16-114">Der Kennwortablauf ist der einzige Teil der Richtlinie, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7bb16-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb16-115">Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass sie nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="7bb16-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="7bb16-116">Weitere Informationen zur Verzeichnissynchronisierung finden Sie [unter Verbinden AD mit Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="7bb16-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="7bb16-117">So überprüfen Sie die Ablaufrichtlinie auf ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="7bb16-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="7bb16-118">Weitere Informationen zum Get-AzureADUser Befehl im AzureAD-Modul finden Sie im Referenzartikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="7bb16-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="7bb16-119">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="7bb16-119">Run one of the following commands:</span></span>

- <span data-ttu-id="7bb16-120">Um festzustellen, ob das Kennwort eines einzelnen Benutzers nie ablaufen soll, führen Sie das folgende Cmdlet mithilfe des UPN (z. B. *user@contoso.onmicrosoft.com*) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten:</span><span class="sxs-lookup"><span data-stu-id="7bb16-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="7bb16-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7bb16-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="7bb16-122">Um die Einstellung Kennwort nie für alle Benutzer **abläuft,** führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="7bb16-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="7bb16-123">Um einen Bericht aller Benutzer mit PasswordNeverExpires in Html auf dem Desktop des aktuellen Benutzers mit dem Namen  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="7bb16-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="7bb16-124">So erhalten Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="7bb16-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="7bb16-125">Führen Sie das folgende Cmdlet aus, um festzulegen, dass die Kennwörter aller Benutzer in einer Organisation nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="7bb16-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="7bb16-126">Benutzerkonten, die mit dem Parameter still age basierend auf dem Attribut konfiguriert `-PasswordPolicies DisablePasswordExpiration` `pwdLastSet` sind.</span><span class="sxs-lookup"><span data-stu-id="7bb16-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="7bb16-127">Wenn `pwdLastSet` Sie das Ablaufdatum in ändern, müssen alle Kennwörter mit einem pwdLastSet, die älter als 90 Tage sind, bei der nächsten Anmeldung geändert werden, wenn Sie das Ablaufdatum in `-PasswordPolicies None` ändern.</span><span class="sxs-lookup"><span data-stu-id="7bb16-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="7bb16-128">Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="7bb16-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="7bb16-129">Festlegen eines Kennworts für das Ablaufen</span><span class="sxs-lookup"><span data-stu-id="7bb16-129">Set a password to expire</span></span>

<span data-ttu-id="7bb16-130">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="7bb16-130">Run one of the following commands:</span></span>

- <span data-ttu-id="7bb16-131">Um das Kennwort eines Benutzers so festzulegen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="7bb16-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="7bb16-132">Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so festzulegen, dass sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="7bb16-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="7bb16-133">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="7bb16-133">Related content</span></span>

<span data-ttu-id="7bb16-134">[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="7bb16-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="7bb16-135">[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="7bb16-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>