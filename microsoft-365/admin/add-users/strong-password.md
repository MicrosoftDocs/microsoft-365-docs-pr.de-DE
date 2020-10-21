---
title: Festlegen einer strengen Kennwortanforderung für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von Windows PowerShell sichere Kennwortanforderungen für Ihre Benutzer festlegen können.
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626143"
---
# <a name="set-strong-password-requirement-for-users"></a>Festlegen einer strengen Kennwortanforderung für Benutzer

In diesem Artikel wird erklärt, wie Sie sichere Kennwortanforderungen für Ihre Benutzer festlegen. Sie müssen diese Schritte mithilfe von PowerShell ausführen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Dieser Artikel richtet sich an Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder eine gemeinnützige Organisation verwalten. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../admin-overview/admin-overview.md) Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.

## <a name="set-strong-passwords"></a>Festlegen sicherer Kennwörter

1. Stellen [Sie eine Verbindung mit Microsoft 365 mit PowerShell her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Mithilfe von PowerShell können Sie mit dem folgenden Befehl sichere Kennwortanforderungen für alle Benutzer aktivieren:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> Das userPrincipalName muss sich im Internet-Format für die Anmeldedatei befinden, wobei dem Benutzernamen das @-Zeichen und ein Domänenname folgen. Beispiel: user@contoso.com.

## <a name="related-content"></a>Verwandte Inhalte

[Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Weitere Informationen zu PowerShell-MsolUser-Befehlen](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Weitere Informationen zur Kennwortrichtlinie](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)