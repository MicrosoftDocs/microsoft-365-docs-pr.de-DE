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
description: Melden Sie sich bei Ihrem Microsoft 365 Administratorkonto an, um bestimmte Benutzerkennwörter so zu setzen, dass sie niemals ablaufen, indem Sie Windows PowerShell.
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635558"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="a1a3b-103">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="a1a3b-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="a1a3b-104">In diesem Artikel wird erläutert, wie Sie ein Kennwort für einen einzelnen Benutzer festlegen, der nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="a1a3b-105">Sie müssen diese Schritte mithilfe von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a1a3b-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-106">Before you begin</span></span>

<span data-ttu-id="a1a3b-107">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a1a3b-108">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="a1a3b-109">[Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a1a3b-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="a1a3b-110">Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a1a3b-111">Ein globaler Administrator für einen Microsoft-Clouddienst kann mithilfe der [Azure Active Directory PowerShell für](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) Graph festlegen, dass Kennwörter für bestimmte Benutzer nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="a1a3b-112">Sie können [](/powershell/module/Azuread) auch AzureAD-Cmdlets verwenden, um die nie abgelaufene Konfiguration zu entfernen oder um zu sehen, welche Benutzerkennwörter auf nie ablaufen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="a1a3b-113">Dieses Handbuch gilt für andere Anbieter, z. B. Intune und Microsoft 365, die auch für Identitäts- und Verzeichnisdienste auf Azure AD angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="a1a3b-114">Kennwortablauf ist der einzige Teil der Richtlinie, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="a1a3b-115">Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass sie nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="a1a3b-116">Weitere Informationen zur Verzeichnissynchronisierung finden Sie [unter Verbinden AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="a1a3b-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="a1a3b-117">Überprüfen der Ablaufrichtlinie für ein Kennwort</span><span class="sxs-lookup"><span data-stu-id="a1a3b-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="a1a3b-118">Weitere Informationen zum Befehl Get-AzureADUser im AzureAD-Modul finden Sie im Referenzartikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="a1a3b-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="a1a3b-119">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-119">Run one of the following commands:</span></span>

- <span data-ttu-id="a1a3b-120">Führen Sie das folgende Cmdlet mit dem UPN (z. B. user@contoso.onmicrosoft.com ) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten, um zu überprüfen, ob das Kennwort eines einzelnen Benutzers *auf* nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="a1a3b-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="a1a3b-122">Führen Sie das folgende **Cmdlet** aus, um die Einstellung Kennwort läuft nie ab für alle Benutzer zu sehen:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="a1a3b-123">So erhalten Sie einen Bericht aller Benutzer mit PasswordNeverExpires in Html auf dem Desktop des aktuellen Benutzers mitReportPasswordNeverExpires.htm **l**</span><span class="sxs-lookup"><span data-stu-id="a1a3b-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="a1a3b-124">So erhalten Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="a1a3b-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="a1a3b-125">Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation auf niemals ablaufen zu lassen:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="a1a3b-126">Benutzerkonten, die mit dem Parameter `-PasswordPolicies DisablePasswordExpiration` konfiguriert sind, altern basierend auf dem `pwdLastSet` Attribut noch.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="a1a3b-127">Wenn Sie den Ablauf in ändern, müssen alle Kennwörter, deren pwdLastSet älter als 90 Tage ist, basierend auf dem Attribut vom Benutzer bei der nächsten Anmeldung geändert `pwdLastSet` `-PasswordPolicies None` werden.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="a1a3b-128">Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="a1a3b-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="a1a3b-129">Festlegen des Ablaufs eines Kennworts</span><span class="sxs-lookup"><span data-stu-id="a1a3b-129">Set a password to expire</span></span>

<span data-ttu-id="a1a3b-130">Führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-130">Run one of the following commands:</span></span>

- <span data-ttu-id="a1a3b-131">Um das Kennwort eines Benutzers so festzusetzen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mit dem UPN oder der Benutzer-ID des Benutzers aus:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="a1a3b-132">Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so fest zu legen, dass sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="a1a3b-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="a1a3b-133">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a1a3b-133">Related content</span></span>

<span data-ttu-id="a1a3b-134">[Benutzer können ihre eigenen Kennwörter](../add-users/let-users-reset-passwords.md) zurücksetzen (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a1a3b-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="a1a3b-135">[Zurücksetzen von Kennwörtern](../add-users/reset-passwords.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a1a3b-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="a1a3b-136">[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a1a3b-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>