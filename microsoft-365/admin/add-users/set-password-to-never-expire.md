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
# <a name="set-an-individual-users-password-to-never-expire"></a>Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft

In diesem Artikel wird erläutert, wie Sie ein Kennwort für einen einzelnen Benutzer festlegen, der nicht abläuft. Sie müssen diese Schritte mithilfe von PowerShell ausführen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md) 

Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.

Ein globaler Administrator für einen Microsoft-Clouddienst kann mithilfe der [Azure Active Directory PowerShell für](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) Graph festlegen, dass Kennwörter für bestimmte Benutzer nicht ablaufen. Sie können [](/powershell/module/Azuread) auch AzureAD-Cmdlets verwenden, um die nie abgelaufene Konfiguration zu entfernen oder um zu sehen, welche Benutzerkennwörter auf nie ablaufen festgelegt sind.

Dieses Handbuch gilt für andere Anbieter, z. B. Intune und Microsoft 365, die auch für Identitäts- und Verzeichnisdienste auf Azure AD angewiesen sind. Kennwortablauf ist der einzige Teil der Richtlinie, der geändert werden kann.

> [!NOTE]
> Nur Kennwörter für Benutzerkonten, die nicht über die Verzeichnissynchronisierung synchronisiert werden, können so konfiguriert werden, dass sie nicht ablaufen. Weitere Informationen zur Verzeichnissynchronisierung finden Sie [unter Verbinden AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Überprüfen der Ablaufrichtlinie für ein Kennwort

Weitere Informationen zum Befehl Get-AzureADUser im AzureAD-Modul finden Sie im Referenzartikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Führen Sie einen der folgenden Befehle aus:

- Führen Sie das folgende Cmdlet mit dem UPN (z. B. user@contoso.onmicrosoft.com ) oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten, um zu überprüfen, ob das Kennwort eines einzelnen Benutzers *auf* nie abläuft:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Beispiel:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Führen Sie das folgende **Cmdlet** aus, um die Einstellung Kennwort läuft nie ab für alle Benutzer zu sehen:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- So erhalten Sie einen Bericht aller Benutzer mit PasswordNeverExpires in Html auf dem Desktop des aktuellen Benutzers mitReportPasswordNeverExpires.htm **l**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- So erhalten Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit **ReportPasswordNeverExpires.csv**

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

- Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation auf niemals ablaufen zu lassen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Benutzerkonten, die mit dem Parameter `-PasswordPolicies DisablePasswordExpiration` konfiguriert sind, altern basierend auf dem `pwdLastSet` Attribut noch. Wenn Sie den Ablauf in ändern, müssen alle Kennwörter, deren pwdLastSet älter als 90 Tage ist, basierend auf dem Attribut vom Benutzer bei der nächsten Anmeldung geändert `pwdLastSet` `-PasswordPolicies None` werden. Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.

### <a name="set-a-password-to-expire"></a>Festlegen des Ablaufs eines Kennworts

Führen Sie einen der folgenden Befehle aus:

- Um das Kennwort eines Benutzers so festzusetzen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mit dem UPN oder der Benutzer-ID des Benutzers aus:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so fest zu legen, dass sie ablaufen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Verwandte Inhalte

[Benutzer können ihre eigenen Kennwörter](../add-users/let-users-reset-passwords.md) zurücksetzen (Artikel)\
[Zurücksetzen von Kennwörtern](../add-users/reset-passwords.md) (Artikel)\
[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md) (Artikel)