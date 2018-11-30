---
title: 'Schritt 2: Schützen von globalen Administratorkonten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie Ihre Administratorkonten für maximalen Schutz.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868196"
---
# <a name="step-2-protect-global-administrator-accounts"></a>Schritt 2: Schützen von globalen Administratorkonten

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. Dazu müssen Sie Folgendes tun:

- Erstellen Sie dedizierte globale Administratorkonten mit sehr [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.
- Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, zu Benutzerkonten von IT-Personal nach Bedarf zuweisen.

Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:

1. Testen Sie Einstellungen für Konto oder bedingte zugriffsbasierte Multi-Factor Authentication (MFA) pro Benutzer mit einem Testbenutzerkonto, um sicherzustellen, dass MFA korrekt und vorhersehbar arbeitet. Die MFA erfordert eine sekundäre Authentifizierung, wie einen an ein Smartphone gesendeten Verifizierungscode.
2. Konfigurieren Sie die MFA für jedes der dedizierten globalen Office 365-Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung, die in Ihrer Organisation verfügbar ist. Unter [Multi-Factor Authentication](identity-multi-factor-authentication.md) finden Sie weitere Informationen.
2. Verwenden Sie eine bedingte Zugriffsrichtlinie, damit MFA für globalen Administratorkonten erforderlich ist. Weitere Informationen finden Sie unter [Administratorkonten schützen](identity-access-prerequisites.md#protecting-administrator-accounts).
4. Verwenden Sie eine Office 365 Cloud App Security-Richtlinie, um die Aktivität globaler Administratorkonten zu überwachen. Unter [Erhöhte Sicherheit für Office 365 konfigurieren](infoprotect-configure-increased-security-office-365.md) finden Sie weitere Informationen.

Unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) finden Sie weitere Informationen zur Konfiguration.

> [!Note]
> Organisationen sollten reine Cloud-Identitäten verwenden, um privilegierte Konten, z. B. globale Administratoren, für Break-Glass-Szenarien in Notfällen (wie Cyberangriff) zu erstellen. Weitere Informationen finden Sie unter [Administrativen Konten für den Notfallzugriff in Azure AD verwalten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Die Ergebnisse dieses Schritts sind:

- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Rolle des globalen Administrators verfügen, sind der neue Satz der dedizierten globalen Administratorkonten. Überprüfen Sie dies mit dem folgenden Windows Azure AD V2 PowerShell-Befehl: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.

> [!Note]
> Anweisungen zum Installieren des Azure AD V2 PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Einrichten von globalen Administratoren bei Bedarf](identity-privileged-identity-management.md) |

