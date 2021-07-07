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
description: Melden Sie sich bei Ihrem Microsoft 365 Administratorkonto an, um mithilfe von Windows PowerShell festzulegen, dass einzelne Benutzerpasswörter nie ablaufen.
ms.openlocfilehash: c9f0c245aca0e028183c42f6a257068d74aa563d
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326723"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft

In diesem Artikel wird erläutert, wie Sie ein Kennwort für einen einzelnen Benutzer festlegen, damit es nicht abläuft. Sie müssen diese Schritte mithilfe von PowerShell ausführen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)

Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

Ein globaler Administrator für einen Microsoft-Clouddienst kann die [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2) verwenden, um festzulegen, dass Kennwörter für bestimmte Benutzer nicht ablaufen. Sie können [auch AzureAD-Cmdlets](/powershell/module/Azuread) verwenden, um die Konfiguration "Nie abläuft" zu entfernen oder um zu sehen, welche Benutzerkennwörter so festgelegt sind, dass sie nie ablaufen.

Dieser Leitfaden gilt für andere Anbieter, z. B. Intune und Microsoft 365, die auch für Identitäts- und Verzeichnisdienste auf Azure AD angewiesen sind. Der Kennwortablauf ist der einzige Teil der Richtlinie, der geändert werden kann.


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>So überprüfen Sie die Ablaufrichtlinie für ein Kennwort

Weitere Informationen zum Get-AzureADUser Befehl im AzureAD-Modul finden Sie im Referenzartikel ["Get-AzureADUser".](/powershell/module/Azuread/Get-AzureADUser)

Führen Sie einen der folgenden Befehle aus:

- Um festzustellen, ob das Kennwort eines einzelnen Benutzers so festgelegt ist, dass es nie abläuft, führen Sie das folgende Cmdlet mithilfe des UPN (z. *B. user@contoso.onmicrosoft.com)* oder der Benutzer-ID des Benutzers aus, den Sie überprüfen möchten:

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

- Um die Einstellung **"Kennwort läuft nie ab"** für alle Benutzer anzuzeigen, führen Sie das folgende Cmdlet aus:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in Html auf dem Desktop des aktuellen Benutzers mit dem Namen  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- So rufen Sie einen Bericht aller Benutzer mit PasswordNeverExpires in CSV auf dem Desktop des aktuellen Benutzers mit dem Namen **ReportPasswordNeverExpires.csv**

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

- Führen Sie das folgende Cmdlet aus, um die Kennwörter aller Benutzer in einer Organisation so festzulegen, dass sie nie ablaufen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Benutzerkonten, die mit dem Parameter konfiguriert `-PasswordPolicies DisablePasswordExpiration` sind, altern basierend auf dem `pwdLastSet` Attribut noch. Wenn Sie den Ablauf basierend auf dem Attribut ändern, muss der `pwdLastSet` Benutzer bei allen Kennwörtern mit einem `-PasswordPolicies None` pwdLastSet, die älter als 90 Tage sind, diese bei der nächsten Anmeldung ändern. Diese Änderung kann sich auf eine große Anzahl von Benutzern auswirken.

### <a name="set-a-password-to-expire"></a>Festlegen des Ablaufs eines Kennworts

Führen Sie einen der folgenden Befehle aus:

- Um das Kennwort eines Benutzers so festzulegen, dass das Kennwort abläuft, führen Sie das folgende Cmdlet mithilfe des UPN oder der Benutzer-ID des Benutzers aus:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Verwenden Sie das folgende Cmdlet, um die Kennwörter aller Benutzer in der Organisation so festzulegen, dass sie ablaufen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Verwandte Inhalte

[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)\
[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)\
[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md) (Artikel)
