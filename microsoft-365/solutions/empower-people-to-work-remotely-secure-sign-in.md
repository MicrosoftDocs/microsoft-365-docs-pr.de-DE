---
title: Schritt 1. Erhöhen Sie die Anmeldesicherheit für Remote-Mitarbeiter mit MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Fordern Sie Ihre Remote-Mitarbeiter auf, sich mit der Mehrstufigen Authentifizierung (MFA) anzumelden.
ms.openlocfilehash: a0350be5cf75024fbefadb21ae56017bf64ca0d8
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213472"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Schritt 1. Erhöhen Sie die Anmeldesicherheit für Remote-Mitarbeiter mit MFA

Verwenden Sie die Mehrstufige Authentifizierung (MFA), um die Sicherheit der Anmeldungen Ihrer Remote-Mitarbeiter zu erhöhen. MFA erfordert, dass Nutzeranmeldungen einer zusätzlichen Überprüfung unterzogen werden, die über das Kennwort des Nutzerkontos hinausgeht. Selbst wenn ein böswilliger Nutzer ein Nutzerkontokennwort ermittelt, muss er in der Lage sein, auf eine zusätzliche Überprüfung zu antworten, z. B. eine Textnachricht, die an ein Smartphone gesendet wird, bevor der Zugriff gewährt wird.

![Das richtige Kennwort und eine zusätzliche Überprüfungsergebnisse bei einer erfolgreichen Anmeldung](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Für alle Nutzer, einschließlich Remote-Mitarbeiter und insbesondere Administratoren, empfiehlt Microsoft dringend MFA.

Es gibt drei Möglichkeiten, von Ihren Nutzern die Verwendung von MFA basierend auf Ihrem Microsoft 365-Plan zu verlangen.

|Plan  |Empfehlung  |
|---------|---------|
|Microsoft 365-Pläne (ohne Azure AD Premium P1 oder P2)     |[Aktivieren Sie die Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Zu den Sicherheitsstandards in Azure AD gehört MFA für Nutzer und Administratoren.   |
|Microsoft 365 E3 (mit Azure AD Premium P1)     | Verwenden Sie [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common), um die folgenden Richtlinien zu konfigurieren: <br>- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (mit Azure AD Premium P2)     | Nutzen Sie den Azure AD-Identity Protection, beginnen Sie mit der Implementierung des von Microsoft [empfohlenen Satzes von bedingtem Zugriff und zugehörigen Richtlinien](../enterprise/identity-access-policies.md), indem Sie die folgenden 2 Richtlinien nutzen:<br> - [MFA erforderlich, wenn das Anmelderisiko mittel oder hoch ist](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Nutzer mit hohem Risiko müssen das Kennwort ändern](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Sicherheitsstandards

Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden. Bei diesen Abonnements sind die Sicherheitsstandards aktiviert, sodass ***alle Nutzer MFA mit der Microsoft Authenticator-App verwenden müssen***.
 
Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden. Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.

Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist. Sie können Sicherheitsstandards für MFA mit Richtlinien für den bedingten Zugriff oder für einzelne Konten deaktivieren.

Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet und zugelassen werden. Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:

- Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.

Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.

Sie können die Richtlinien für den bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. wenn die Anmeldung von einem kompatiblen Gerät aus erfolgen muss, z. B. von Ihrem Laptop unter Windows 10.

Für den bedingten Zugriff ist Azure AD Premium P1 erforderlich, das in Microsoft 365 E3 und E5 enthalten ist.

Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-support"></a>Support für Azure AD Identity Protection

Mit Azure AD Identity Protection können Sie eine zusätzliche Richtlinie für bedingten Zugriff erstellen, die festlegt:

- Wenn das Anmelderisiko als mittleres oder hohes Risiko eingestuft wird, ist MFA zu fordern.

Für Azure AD Identity Protection ist Azure AD Premium P2 erforderlich, das in Microsoft 365 E5 enthalten ist.

Weitere Informationen finden Sie unter [Risikoabhängiger bedingter Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).

## <a name="using-these-methods-together"></a>Diese Methoden zusammen verwenden

Beachten Sie Folgendes:

- Sie können die Sicherheitsstandards nicht aktivieren, wenn Sie Richtlinien für den bedingten Zugriff aktiviert haben.
- Sie können keine Richtlinien für den bedingten Zugriff aktivieren, wenn Sie die Sicherheitsstandards aktiviert haben.

Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Nutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App aufgefordert. 

Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards und Richtlinien für bedingten Zugriff.

|| Aktiviert | Deaktiviert | Zusätzliche Authentifizierungsmethode |
|:-------|:-----|:-------|:-------|
| **Sicherheitsstandards**  | Richtlinien für bedingten Zugriff können nicht verwendet werden | Richtlinien für den bedingten Zugriff können verwendet werden | Microsoft Authenticator-App |
| **Richtlinien für bedingten Zugriff** | Wenn welche aktiviert sind, können Sie die Sicherheitsstandards nicht aktivieren | Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren  | Werden vom Benutzer während der MFA-Registrierung festgelegt  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Administratorschulung und technische Ressourcen für MFA und Identität

- [MFA-Planung für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Die 5 wichtigsten Möglichkeiten, mit denen Azure AD die Remote-Arbeit aktivieren kann](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Planen und Bereitstellen Ihrer Microsoft 365-Identitätsinfrastruktur](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD-Schulungsvideos](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Konfigurieren Sie die Registrierungsrichtlinie für die Azure-Multi-Faktor-Authentifizierung](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Ergebnisse von Schritt 1

Nach der Bereitstellung von MFA haben Ihre Nutzer:

- Die Verpflichtung MFA für Anmeldungen verwenden.
- Den MFA-Registrierungsprozess abgeschlossen und verwenden MFA für alle Anmeldungen.

## <a name="next-step"></a>Nächster Schritt

Fahren Sie mit [Schritt 2](empower-people-to-work-remotely-remote-access.md) fort, um den Remotezugriff auf lokale Apps und Dienste bereitzustellen.
