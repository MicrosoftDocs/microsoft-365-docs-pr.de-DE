---
title: 'Schritt 1: Erstellen und Schützen Ihrer globalen Administratorkonten'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ihre globalen Administratorkonten benötigen eine spezielle Behandlung, um sie vor der Kompromittierung von Anmeldeinformationen zu schützen.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621306"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Schritt 1: Erstellen und Schützen Ihrer globalen Administratorkonten

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Schützen von globalen Administratorkonten

*Dies ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. Dazu müssen Sie Folgendes tun:

- Erstellen Sie mehr als ein dediziertes globales Administratorkonto mit [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.
- Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, anderen dedizierten Konten für diese Rollen oder Benutzerkonten von IT-Personal nach Bedarf zuweisen.

Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:

1. Testen Sie Einstellungen für Benutzerkonto oder bedingte zugriffsbasierte mehrstufige Azure-Authentifizierung (MFA) mit einem Testbenutzerkonto, um sicherzustellen, dass die MFA korrekt und vorhersehbarer funktioniert. Die MFA erfordert eine sekundäre Authentifizierungsform wie etwa einen an ein Smartphone gesendeten Verifizierungscode.
2. Erstellen und aktivieren Sie eine Richtlinie für den bedingten Zugriff für Ihre globalen Administratorkonten, die MFA erfordert und die stärkste in Ihrer Organisation verfügbare Form der sekundären Authentifizierung verwendet. Weitere Informationen finden Sie unter [Mehrstufige Azure-Authentifizierung](identity-access-prerequisites.md#protecting-administrator-accounts).

Näheres zu weiteren Schutzmaßnahmen finden Sie unter [Schützen Ihrer globalen Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> Notfallzugriffs-Konten für Notfälle wie etwa einen Cyberangriff sollten nur cloudbasiert sein. Sie können außerdem über globale Administratorkonten (berechtigt oder permanent) verfügen, die nicht rein cloudbasiert sind. Weitere Informationen finden Sie unter [Verwalten von Administratorkonten für den Notfallzugriff in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Die Ergebnisse dieses Abschnitts sind:

- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich in den dedizierten Konten für globale Administratoren. Verifizieren Sie dies mit dem folgenden Azure Active Directory PowerShell für Graph-Befehl: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Alle anderen Benutzerkonten für die Verwaltung Ihrer Abonnementdienste verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.

> [!Note]
> Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Abschnitt ansehen.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Einrichten von Administratoren bei Bedarf

*Dies ist optional und gilt nur für die Version E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt richten Sie Azure AD Privileged Identity Management (PIM) ein, um die Zeitspanne zu verringern, in der Ihre Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind. PIM bietet bei Bedarf eine zeitnahe Zuweisung von Administratorrollen.  

Statt dass Ihre Administratorkonten permanente Administratoren sind, werden sie zu berechtigten Administratoren. Die Administratorrolle ist so lange inaktiv, bis sie von jemandem benötigt wird. Dann wird ein Aktivierungsvorgang ausgeführt, um dem Administratorkonto die Administratorrolle für einen bestimmten Zeitraum hinzuzufügen. Wenn die Zeit abgelaufen ist, entfernt PIM die Administratorrolle aus dem Administratorkonto.

PIM ist im Lieferumfang von Azure Active Directory Premium P2 verfügbar, das im Lieferumfang von Microsoft 365 E5 enthalten ist. Alternativ hierzu können Sie einzelne Azure Active Directory Premium P2-Lizenzen für Ihre Administratorkonten erwerben.

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für Administratorkonten finden Sie unter [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Abschnitt ansehen.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Mandanten benötigt.

In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Organisation zu beginnen:

- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.

Weitere Informationen zum Aktivieren von Privileged Access Management finden Sie im Thema [Konfigurieren von Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Weitere Informationen finden Sie im Thema [Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Privileged Access Management](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pam) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 2](../media/stepnumbers/Step2.png)| [Schützen von Kennwörtern](identity-secure-your-passwords.md) |

