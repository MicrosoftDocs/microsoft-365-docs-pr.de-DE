---
title: Deaktivieren der Anforderungen für sichere Kennwörter für Benutzer
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
description: Erfahren Sie, wie Sie mithilfe von Windows PowerShell sichere Kennwortanforderungen für Ihre Benutzer festlegen.
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286267"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Deaktivieren der Anforderungen für sichere Kennwörter für Benutzer

In diesem Artikel wird erläutert, wie Sie sichere Kennwortanforderungen für Ihre Benutzer deaktivieren. Sichere Kennwortanforderungen sind in Ihrer Microsoft 365 für Unternehmen standardmäßig aktiviert. Ihre Organisation hat möglicherweise Anforderungen, um sichere Kennwörter zu deaktivieren. Führen Sie die folgenden Schritte aus, um sichere Kennwortanforderungen zu deaktivieren. Sie müssen diese Schritte mithilfe von PowerShell ausführen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Dieser Artikel richtet sich an Personen, die die Kennwortrichtlinie für ein Unternehmen, eine Schule oder eine gemeinnützige Organisation verwalten. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](/microsoft-365/business-video/admin-center-overview) Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

Sie müssen auch eine Verbindung mit Microsoft 365 mit PowerShell herstellen.

## <a name="set-strong-passwords"></a>Festlegen sicherer Kennwörter

1. [Verbinden mit PowerShell zum Microsoft 365.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Mithilfe von PowerShell können Sie die Anforderungen für sichere Kennwörter für alle Benutzer mit dem folgenden Befehl deaktivieren:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> "userPrincipalName" muss im Anmeldeformat im Internetformat vorliegen, auf das der Benutzername folgt, gefolgt von "at sign" (@) und einem Domänennamen. Beispiel: user@contoso.com.

## <a name="related-content"></a>Verwandte Inhalte

[Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Weitere Informationen zu PowerShell-MsolUser-Befehlen](/powershell/azure/active-directory/install-adv2)

[Weitere Informationen zur Kennwortrichtlinie](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
