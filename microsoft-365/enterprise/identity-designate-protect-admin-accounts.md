---
title: 'Schritt 2: Sichern Ihrer privilegierten Identitäten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie Ihre Administratorkonten für maximalen Schutz.
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074055"
---
# <a name="step-2-secure-your-privileged-identities"></a>Schritt 2: Sichern Ihrer privilegierten Identitäten

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Schützen von globalen Administratorkonten

*Dies ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. Dazu müssen Sie Folgendes tun:

- Erstellen Sie dedizierte globale Administratorkonten mit sehr [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.
- Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, zu Benutzerkonten von IT-Personal nach Bedarf zuweisen.

Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:

1. Testen Sie Einstellungen für Konto oder bedingte zugriffsbasierte Multi-Factor Authentication (MFA) pro Benutzer mit einem Testbenutzerkonto, um sicherzustellen, dass MFA korrekt und vorhersehbar arbeitet. Die MFA erfordert eine sekundäre Authentifizierung, wie einen an ein Smartphone gesendeten Verifizierungscode.
2. Konfigurieren Sie die MFA für jedes der dedizierten globalen Office 365-Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung, die in Ihrer Organisation verfügbar ist. Unter [Multi-Factor Authentication](identity-multi-factor-authentication.md#identity-mfa) finden Sie weitere Informationen.
2. Verwenden Sie eine bedingte Zugriffsrichtlinie, damit MFA für globalen Administratorkonten erforderlich ist. Weitere Informationen finden Sie unter [Administratorkonten schützen](identity-access-prerequisites.md#protecting-administrator-accounts).

Unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) finden Sie weitere Informationen zur Konfiguration.

> [!Note]
> Organisationen sollten reine Cloud-Identitäten verwenden, um privilegierte Konten, z. B. globale Administratoren, für Break-Glass-Szenarien in Notfällen (wie Cyberangriff) zu erstellen. Weitere Informationen finden Sie unter [Administrativen Konten für den Notfallzugriff in Azure AD verwalten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Die Ergebnisse dieses Abschnitts sind:

- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich im neuen Satz der dedizierten Konten für globale Administratoren. Verifizieren Sie dies mit dem folgenden Azure Active Directory PowerShell für Graph-Befehl: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.

> [!Note]
> Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Abschnitt betrachten.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>Einrichten von globalen Administratoren bei Bedarf

*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt richten Sie Azure AD Privileged Identity Management (PIM) ein, um die Zeitspanne zu verringern, in der Ihre globalen Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind. PIM bietet bei Bedarf eine zeitnahe Zuweisung der globalen Administratorrolle.  

Ihre globalen Administratorkonten werden zu berechtigten Administratoren anstelle von dauerhaften Administratoren. Die globale Administratorrolle ist inaktiv, bis eine Person sie benötigt. Sie durchlaufen dann einen Aktivierungsprozess, bei dem die globale Administratorrolle für eine bestimmte Zeitspanne zum globalen Administratorkonto hinzugefügt wird. Wenn der Zeitraum abgelaufen ist, entfernt PIM die globale Administratorrolle vom globalen Administratorkonto.

PIM ist zusammen mit Azure Active Directory Premium P2 erhältlich, das in Microsoft 365 Enterprise E5 enthalten ist. Alternativ können Sie für Ihre globalen Administratorkonten einzelne Azure Active Directory Premium P2-Lizenzen erwerben.

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für globale Administratorkonten finden Sie unter der [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Abschnitt betrachten.


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Konfigurieren der Hybrididentität](identity-azure-ad-connect.md) |

