---
title: 'Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der mehrstufigen Authentifizierung für Benutzerkonten.
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981846"
---
# <a name="step-4-configure-secure-user-authentication"></a>Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Schritt richten Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzuzufügen. MFA erfordert eine zusätzliche Überprüfungsmethode, nachdem Benutzer ihr Kennwort richtig eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem mit Kennwörtern ist, dass sie häufig von einem Angreifer leicht zu erraten sind oder unbewusst für nicht vertrauenswürdige Parteien freigegeben werden.

Die zweite Sicherheitsebene bei MFA kann Folgendes sein:

- Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.
- Ein biometrisches Attribut, z. B. ein Fingerabdruck.

Sie aktivieren MFA und konfigurieren die sekundäre Authentifizierungsmethode mit [bedingten Zugriffsrichtlinien](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), die es Ihnen ermöglichen, Azure Active Directory-Gruppen (Azure AD) zum Rollout von MFA für bestimmte Gruppen von Benutzern, z. B. Pilotbenutzer, geografische Regionen oder Abteilungen zu verwenden. Teilen Sie Ihren Benutzern unbedingt mit, dass MFA aktiviert ist, damit sie die Anforderungen, z. B. obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können. 

Weitere Informationen finden Sie unter [Planen der mehrstufigen Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

>[!Note]
>In einigen Clientanwendungen, z. B. Microsoft Office 2010 oder früher und Apple Mail, können Sie MFA nicht verwenden. Um diese Apps zu nutzen, müssen Sie „App-Kennwörter“ anstelle Ihres herkömmlichen Kennworts verwenden. Das App-Kennwort ermöglicht der App, MFA zu umgehen und die Arbeit fortzusetzen. Weitere Informationen zu App-Kennwörtern finden Sie unter [Erstellen eines App-Kennworts für Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Abschnitt ansehen.

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Verhindern unsicherer Kennwörter

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen. So können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B. "

- Markennamen
- Produktnamen
- Standorte (z. B. Firmenhauptsitz)
- Unternehmensspezifische interne Begriffe
- Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben.

Sie können unsichere Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory-Domänendienste (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) sperren.

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-password-prot) für diesen Abschnitt betrachten.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Schutz vor Kompromittierung von Anmeldeinformationen

*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten. Azure AD Identity Protection bietet eine Reihe von Methoden, mit denen verhindert werden kann, dass sich ein Angreifer seitwärts durch Konten und Gruppen und folglich Ihre wertvollsten Daten bewegt.

Mit Azure AD Identity Protection können Sie Folgendes:

|||
|:---------|:---------|
|Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation|Azure AD verwendet das maschinelle Lernen, um Anomalien und verdächtige Aktivitäten wie Anmeldeaktivitäten und Aktivitäten nachdem Anmelden zu erkennen. Anhand dieser Daten generiert Azure AD Identity Protection Berichte und Warnungen, mit denen Sie die Probleme bewerten und entsprechende Maßnahmen ergreifen können.|
|Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese|Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Mit diesen Richtlinien in Verbindung mit anderen Kontrollelementen für den bedingten Zugriff von Azure AD und Microsoft Intune können entweder Zugriffsversuche automatisch blockiert oder Korrekturmaßnahmen ergriffen werden. Hierzu gehören Kennwortzurücksetzungen und die Durchsetzung der Multi-Factor Authentication für nachfolgende Anmeldeversuche.|
|Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben|Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.|

Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:

- Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen
- Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen
- Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Abschnitt betrachten.

## <a name="monitor-tenant-and-sign-in-activity"></a>Überwachen der Mandanten- und Anmeldeaktivität

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Schritt überprüfen Sie Überwachungsprotokolle und Anmeldeaktivitäten mithilfe von Azure AD-Berichten. Es stehen zwei Arten von Berichten zur Verfügung.

Der **Aktivitätsbericht „Überwachungsprotokolle“** verzeichnet den Verlauf jeder in Ihrem Azure AD-Mandanten ausgeführten Aufgabe. In diesem Bericht finden Sie Antworten auf Fragen wie:

- Wer hat eine Person zu einer Administratorengruppe hinzugefügt?
- Welche Benutzer melden sich bei einer bestimmten App an?
- Wie viele Kennwortzurücksetzungen werden ausgeführt?

Der **Aktivitätsbericht „Anmeldungen“** verzeichnet, wer die im Überwachungsprotokollbericht gemeldeten Aufgaben ausgeführt hat. In diesem Bericht finden Sie Antworten auf Fragen wie:

- Welches Anmeldemuster gilt für einen bestimmten untersuchten Benutzer?
- Wie groß ist das Volumen von Anmeldungen über einen Tag, eine Woche oder einen Monat?
- Wie viele dieser Anmeldeversuche waren nicht erfolgreich und für welche Konten?

Weitere Informationen zu den Berichten und den Zugriffsmöglichkeiten auf diese finden Sie unter [Azure Active Directory-Berichterstellung](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

In diesem Schritt lernen Sie die Berichte kennen und erfahren, wie Sie sie verwenden können, um zu Planungs- und Sicherheitszwecken Informationen über Azure AD-Ereignisse und -Aktivitäten zu erhalten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [Vereinfachen des Zugriffs für Benutzer](identity-password-reset.md) |

