---
title: Deaktivieren starker Kennwortanforderungen für Benutzer
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
description: Erfahren Sie, wie Sie starke Kennwortanforderungen für Ihre Benutzer mithilfe von Windows PowerShell.
ms.openlocfilehash: e2300e3c94de53cd04d0c1726538fdb8a86a1ccf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903536"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Deaktivieren starker Kennwortanforderungen für Benutzer

In diesem Artikel wird erläutert, wie Sie starke Kennwortanforderungen für Ihre Benutzer deaktivieren. Starke Kennwortanforderungen sind in Ihrer Microsoft 365 Business-Organisation standardmäßig aktiviert. Ihre Organisation muss möglicherweise sichere Kennwörter deaktivieren. Führen Sie die folgenden Schritte aus, um starke Kennwortanforderungen zu deaktivieren. Sie müssen diese Schritte mithilfe von PowerShell ausführen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Dieser Artikel ist für Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder gemeinnützige Organisation verwalten. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../admin-overview/admin-overview.md) Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.

Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.

## <a name="set-strong-passwords"></a>Festlegen von starken Kennwörtern

1. [Verbinden Sie sich mit Microsoft 365 mit PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Mit PowerShell können Sie starke Kennwortanforderungen für alle Benutzer mit dem folgenden Befehl deaktivieren:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> Der userPrincipalName muss im Anmeldeformat im Internetformat vorliegen, in dem auf den Benutzernamen das At-Zeichen (@) und ein Domänenname folgen. Beispiel: user@contoso.com.

## <a name="related-content"></a>Verwandte Inhalte

[Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Weitere Informationen zu PowerShell-MsolUser-Befehlen](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Weitere Informationen zur Kennwortrichtlinie](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)