---
title: 'Schritt 5: Vereinfachen des Zugriffs für Benutzer'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie die Self-Service-Kennwortzurücksetzung (Self-Service Password Reset, SSPR) für Azure AD.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287058"
---
# <a name="step-5-simplify-access-for-users"></a>Schritt 5: Vereinfachen des Zugriffs für Benutzer

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Vereinfachen der Kennwortaktualisierungen

*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt können Sie können Sie festlegen, dass Benutzer ihre Kennwörter über Azure Active Directory (Azure AD) zurücksetzen können, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird. Dieser Vorgang wird als Rückschreiben des Kennworts bezeichnet. Dank dem Rückschreiben des Kennworts müssen Benutzer ihre Kennwörter nicht über das lokale Active Directory Domain Services (AD DS) aktualisieren, wo ihre ursprünglichen Benutzerkonten und Attribute gespeichert sind. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.

Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.

Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Rückschreiben des Kennworts](password-writeback-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-writeback) für diesen Abschnitt betrachten.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Vereinfachen der Kennwortzurücksetzung

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt können Sie mit der Self-Service-Kennwortzurücksetzung (SSPR) Benutzern erlauben, ihre Kennwörter oder Konten zurückzusetzen oder zu entsperren. Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird. Sie müssen das Rückschreiben des Kennworts aktivieren, bevor Sie das Zurücksetzen von Kennwörtern bereitstellen können.

Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Leitfaden für Testlabor: Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-reset) für diesen Abschnitt betrachten.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Vereinfachen der Benutzeranmeldung

*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt werden Sie das nahtlose einmalige Anmelden von Azure Active Directory einrichten, damit sich Benutzer bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ohne ihre Benutzernamen angeben zu müssen. Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.

Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.

Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sso) für diesen Abschnitt betrachten.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Anpassen der Office 365-Anmeldeseite

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt werden Sie den Unternehmensnamen, das Logo und andere erkennbare Elemente zu der Anmeldeseite Ihrer Organisation hinzufügen, damit Benutzer diese als solche erkennen. 

Mit Microsoft 365 Enterprise können Sie die Darstellung der Anmeldeseite und der Zugriffsbereichsseiten anpassen, damit sie Unternehmenslogo, Farbschemas und angepasste Benutzerinformationen enthalten. 

Wenn Benutzer versuchen, sich auf einem Gerät anzumelden, wird eine Seite angezeigt, die in etwa wie im folgenden Beispiel für eine Office 365-Anmeldeseite *vor der Anpassung* aussieht.

![Beispiel für die Office 365-Anmeldeseite vor der Anpassung](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

So würde die Seite für denselben Benutzer von Contoso Corporation *nach der Anpassung* aussehen.

![Beispiel für die Office 365-Anmeldeseite nach der Anpassung](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

Weitere Informationen finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite von Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Anweisungen zur Konfiguration finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite und zu Zugriffsbereichsseiten](http://aka.ms/aadpaddbranding).

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-custom-sign-in) für diesen Abschnitt betrachten.


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Verwenden von Gruppen zur einfacheren Verwaltung](identity-self-service-group-management.md) |


