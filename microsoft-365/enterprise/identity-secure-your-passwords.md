---
title: 'Schritt 2: Schützen von Kennwörtern'
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
description: Sie müssen für Ihre gesamte Organisation sichere Kennwörter verwenden, und die Kennwortverwaltung einfach gestalten.
ms.openlocfilehash: b4eb1861eb8d1c483972cf6a7c22a339dc1b0b36
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637048"
---
# <a name="step-2-secure-your-passwords"></a>Schritt 2: Schützen von Kennwörtern

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Verhindern unsicherer Kennwörter

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*

Alle Benutzer Ihrer Organisation sollten bei der Erstellung der Kennwörter für ihre Benutzerkonten die [Kennwortrichtlinien von Microsoft](https://www.microsoft.com/research/publication/password-guidance/) anwenden.

Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen. Hier können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B.:

- Markennamen
- Produktnamen
- Standorte (z. B. Firmenhauptsitz)
- Unternehmensspezifische interne Begriffe
- Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben

Sie können unsichere Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) sperren.

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-password-prot) für diesen Abschnitt ansehen.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Vereinfachen der Kennwortzurücksetzung

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*

In diesem Abschnitt können Sie mit der Self-Service-Kennwortzurücksetzung (SSPR) Benutzern erlauben, ihre Kennwörter oder Konten zurückzusetzen oder zu entsperren. Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird. Sie müssen das Rückschreiben des Kennworts aktivieren, bevor Sie das Zurücksetzen von Kennwörtern bereitstellen können.

Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Leitfaden für Testlabor: Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-reset) für diesen Abschnitt betrachten.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Vereinfachen der Benutzeranmeldung

*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt werden Sie das nahtlose einmalige Anmelden von Azure Active Directory einrichten, das mit der Kennworthashsynchronisierung (PHS) und der Passthrough-Authentifizierung (PTA) verwendet werden kann, damit sich Benutzer bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ohne ihre Benutzernamen angeben zu müssen. Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.

Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.

Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-sso) für diesen Abschnitt ansehen.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a>Anpassen der Anmeldeseite

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt werden Sie den Unternehmensnamen, das Logo und andere erkennbare Elemente zu der Anmeldeseite Ihrer Organisation hinzufügen, damit Benutzer diese als solche erkennen. 

Mit Microsoft 365 Enterprise können Sie die Darstellung der Anmeldeseite und der Zugriffsbereichsseiten anpassen, damit sie Unternehmenslogo, Farbschemas und angepasste Benutzerinformationen enthalten. 

Weitere Informationen finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite von Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Anweisungen zur Konfiguration finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite und zu Zugriffsbereichsseiten](https://aka.ms/aadpaddbranding).

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-custom-sign-in) für diesen Abschnitt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 3](../media/stepnumbers/Step3.png)| [Absichern und Verwalten von Benutzeranmeldungen](identity-secure-user-sign-ins.md) |
