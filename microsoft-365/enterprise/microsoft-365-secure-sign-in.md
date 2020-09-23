---
title: Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Legen Sie fest, dass sich Ihre Benutzer über mehrstufige Authentifizierung (MFA) und andere Features sicher anmelden müssen.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132241"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten

So erhöhen Sie die Sicherheit von Benutzeranmeldungen:

- Verwenden des Azure Active Directory-Kennwortschutzes (Azure AD)
- Verwenden der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA)
- Bereitstellen von Identitäts- und Gerätezugriffsrichtlinien

## <a name="azure-ad-password-protection"></a>Azure AD-Kennwortschutz

Der Azure AD-Kennwortschutz erkennt und blockiert als schwach bekannte Kennwörter und deren Varianten und kann zusätzlich für Ihre Organisation spezifische schwache Ausdrücke blockieren. Listen standardmäßig global gesperrter Kennwörter werden automatisch auf alle Benutzer in einem Azure AD-Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter angeben. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese Listen gesperrter Kennwörter überprüft, um die Verwendung von sicheren Kennwörtern zu erzwingen.

Weitere Informationen finden Sie unter [Konfigurieren des Azure AD-Kennwortschutzes](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA (mehrstufige Authentifizierung)

MFA erfordert, dass Nutzeranmeldungen einer zusätzlichen Überprüfung unterzogen werden, die über das Kennwort des Nutzerkontos hinausgeht. Selbst wenn ein böswilliger Nutzer ein Nutzerkontokennwort ermittelt, muss er in der Lage sein, auf eine zusätzliche Überprüfung zu antworten, z. B. eine Textnachricht, die an ein Smartphone gesendet wird, bevor der Zugriff gewährt wird.

![Das richtige Kennwort und eine zusätzliche Überprüfungsergebnisse bei einer erfolgreichen Anmeldung](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Der erste Schritt bei der Verwendung von MFA besteht darin, sie ***für alle Administratorkonten als erforderlich festzulegen*** (diese Konten werden auch als privilegierte Konten bezeichnet).

Über diesen ersten Schritt hinaus empfiehlt Microsoft, die mehrstufige Authentifizierung unbedingt für alle Benutzer vorzugeben.

Basierend auf Ihrem Microsoft 365-Plan gibt es drei Möglichkeiten, von Ihren Administratoren oder Nutzern die Verwendung der mehrstufigen Authentifizierung zu verlangen.

| Plan | Empfehlung |
|---------|---------|
|Alle Microsoft 365-Pläne (ohne Azure AD Premium P1- oder P2-Lizenzen)     |[Aktivieren Sie die Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Zu den Sicherheitsstandards in Azure AD gehört MFA für Nutzer und Administratoren.   |
|Microsoft 365 E3 (einschließlich Azure AD Premium P1-Lizenzen)     | Verwenden Sie [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common), um die folgenden Richtlinien zu konfigurieren: <br>- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (einschließlich Azure AD Premium P2-Lizenzen)     | Nutzen Sie den Azure AD-Identity Protection, beginnen Sie mit der Implementierung des von Microsoft [empfohlenen Satzes von bedingtem Zugriff und zugehörigen Richtlinien](../enterprise/identity-access-policies.md), indem Sie die folgenden 2 Richtlinien nutzen:<br> - [MFA erforderlich, wenn das Anmelderisiko mittel oder hoch ist](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Nutzer mit hohem Risiko müssen das Kennwort ändern](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Sicherheitsstandards

Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden. Bei diesen Abonnements sind die Sicherheitsstandards aktiviert, sodass ***alle Nutzer MFA mit der Microsoft Authenticator-App verwenden müssen***.
 
Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden. Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.

Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist. Sie können Sicherheitsstandards für MFA mit Richtlinien für den bedingten Zugriff oder für einzelne Konten deaktivieren.

Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet werden und der Zugriff gewährt wird. Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:

- Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.

Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.

Sie können die Richtlinien für den bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. wenn die Anmeldung von einem kompatiblen Gerät aus erfolgen muss, z. B. von Ihrem Laptop unter Windows 10.

Für den bedingten Zugriff sind Azure AD Premium P1-Lizenzen erforderlich, die in Microsoft 365 E3 und E5 enthalten sind.

Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Diese Methoden zusammen verwenden

Denken Sie dabei an Folgendes:

- Sie können die Sicherheitsstandards nicht aktivieren, wenn Sie Richtlinien für den bedingten Zugriff aktiviert haben.
- Sie können keine Richtlinien für den bedingten Zugriff aktivieren, wenn Sie die Sicherheitsstandards aktiviert haben.

Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Nutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App aufgefordert. 

Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards und Richtlinien für bedingten Zugriff.

| Methode | Aktiviert | Deaktiviert | Zusätzliche Authentifizierungsmethode |
|:-------|:-----|:-------|:-------|
| **Sicherheitsstandards**  | Richtlinien für bedingten Zugriff können nicht verwendet werden | Richtlinien für den bedingten Zugriff können verwendet werden | Microsoft Authenticator-App |
| **Richtlinien für bedingten Zugriff** | Wenn welche aktiviert sind, können Sie die Sicherheitsstandards nicht aktivieren | Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren  | Werden vom Benutzer während der MFA-Registrierung festgelegt  |
||||

## <a name="identity-and-device-access-policies"></a>Identitäts- und Gerätezugriffsrichtlinien

Einstellungen und Richtlinien für den Identitäts- und Gerätezugriff sind empfohlene Voraussetzungen. Deren Einstellungen bestimmen in Kombination mit bedingtem Zugriff, Intune und Azure AD Identity Protection-Richtlinien für den Identitätsschutz, ob und unter welchen Bedingungen einer bestimmten Zugriffsanforderung zugestimmt werden soll. Diese Ermittlung basiert auf dem Benutzerkonto der Anmeldung, dem verwendeten Gerät, der vom Benutzer für die Anmeldung verwendeten App, dem Ort, an dem die Zugriffsanforderung erfolgt sowie einer Bewertung des Risikos der Anforderung. Diese Funktion trägt dazu bei, sicherzustellen, dass nur autorisierte Benutzer und Geräte auf Ihre kritischen Ressourcen zugreifen können.

>[!Note]
>Für Azure AD Identity Protection sind Azure AD Premium P2-Lizenzen erforderlich, die in Microsoft 365 E5 enthalten sind.
>

Identitäts- und Gerätezugriffsrichtlinien sind für die Verwendung auf drei Ebenen definiert: 

- Der grundlegende Schutz bietet ein Mindestmaß an Sicherheit für Ihre Identitäten und Geräte, die auf Ihre Apps und Daten zugreifen.
- Der Schutz vertraulicher Daten bietet zusätzliche Sicherheit für bestimmte Daten. Identitäten und Geräte müssen höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen.
- Der Schutz für Umgebungen mit strengen Datensicherheitsbestimmungen ist für in der Regel kleine Mengen von Daten bestimmt, die streng vertraulich sind, Geschäftsgeheimnisse enthalten oder Datenschutzbestimmungen unterliegen. Identitäten und Geräte müssen viel höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen. 

Diese Ebenen und die entsprechenden Konfigurationen bieten einheitliche Schutzniveaus für Ihre Daten, Identitäten und Geräte.

Microsoft empfiehlt dringend das Konfigurieren und Bereitstellen von Identitäts- und Gerätezugriffsrichtlinien in Ihrer Organisation, einschließlich spezifischer Einstellungen für Microsoft Teams, Exchange Online und SharePoint. Weitere Informationen finden Sie unter [Konfigurationen für den Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md).

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Technische Administratorressourcen für mehrstufige Authentifizierung (MFA) und sichere Anmeldungen

- [MFA für Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Identitäts-Roadmap für Microsoft 365](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-Schulungsvideos](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Konfigurieren Sie die Registrierungsrichtlinie für die Azure-Multi-Faktor-Authentifizierung](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Konfigurationen für den Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md)

