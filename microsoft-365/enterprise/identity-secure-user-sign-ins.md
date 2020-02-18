---
title: 'Schritt 3: Absichern und Verwalten von Benutzeranmeldungen'
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
description: Sie können die Benutzeranmeldungen auf Windows-Geräten und auf Microsoft 365 sicherer machen.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067292"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Schritt 3: Absichern und Verwalten von Benutzeranmeldungen

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Windows Hello for Business

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365*

Windows Hello for Business in Windows 10 Enterprise ersetzt Kennwörter durch eine starke zweistufige Authentifizierung, wenn sich jemand auf einem Windows-Gerät anmeldet. Beide Faktoren zählen zu neuen Arten von Benutzeranmeldeinformationen, die mit einem Gerät verknüpft sind und biometrische Daten oder eine PIN erfordern.

Weitere Informationen finden Sie unter [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Einrichten der mehrstufigen Azure-Authentifizierung

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365*

Im Rahmen dieses Schritts richten Sie die mehrstufige Azure-Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene zu Benutzeranmeldungen und -transaktionen hinzuzufügen. Die mehrstufige Authentifizierung erfordert eine zusätzliche Überprüfungsmethode, nachdem die Benutzer ihr Kennwort korrekt eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem bei Kennwörtern ist, dass viele von ihnen durch einen Angreifer leicht erraten oder unwissentlich mit nicht vertrauenswürdigen Parteien geteilt werden.

Die zweite Sicherheitsebene bei MFA kann Folgendes sein:

- Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.
- Ein biometrisches Attribut, z. B. ein Fingerabdruck.

Sie aktivieren die mehrstufige Authentifizierung und konfigurieren die zweite Authentifizierungsmethode mithilfe von [Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), die es Ihnen ermöglichen, Azure Active Directory-Gruppen (Azure AD) zum Rollout von MFA für bestimmte Gruppen von Benutzern, z. B. Pilotbenutzer, geografische Regionen oder Abteilungen zu verwenden. Teilen Sie Ihren Benutzern unbedingt mit, dass die mehrstufige Authentifizierung aktiviert wird, damit sie die Anforderungen, z. B. die obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können. 

Weitere Informationen finden Sie unter [Planen einer cloudbasierten Bereitstellung der mehrstufigen Azure-Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Mehrstufige Azure-Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Abschnitt ansehen.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Schutz vor Kompromittierung von Anmeldeinformationen

*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten. Azure AD Identity Protection bietet verschiedene Möglichkeiten um zu verhindern, dass ein Angreifer die Anmeldeinformationen eines Benutzerkontos kompromittiert.

Mit Azure AD Identity Protection können Sie Folgendes:

|||
|:---------|:---------|
|Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation|Azure AD verwendet das maschinelle Lernen, um Anomalien und verdächtige Aktivitäten wie Anmeldeaktivitäten und Aktivitäten nachdem Anmelden zu erkennen. Anhand dieser Daten generiert Azure AD Identity Protection Berichte und Warnungen, mit denen Sie die Probleme bewerten und entsprechende Maßnahmen ergreifen können.|
|Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese|Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Zusätzlich zu anderen Kontrollelementen für den bedingten Zugriff von Azure AD und Microsoft Intune können mithilfe dieser Richtlinien entweder Zugriffsversuche automatisch blockiert oder Korrekturmaßnahmen ergriffen werden. Hierzu gehören Kennwortzurücksetzungen und die Anforderung der mehrstufigen Azure-Authentifizierung für nachfolgende Anmeldeversuche.|
|Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben|Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.|

Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:

- Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen
- Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen
- Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Abschnitt ansehen.

|||
|:-------|:-----|
|![Schritt 4](../media/stepnumbers/Step4.png)| [Hinzufügen von Benutzerkonten](identity-add-user-accounts.md) |
