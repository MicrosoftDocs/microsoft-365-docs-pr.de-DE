---
title: Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: Legen Sie fest, dass sich Ihre Benutzer über mehrstufige Authentifizierung (MFA) und andere Features sicher anmelden müssen.
ms.openlocfilehash: 8426d902ff8be8541b5d770af6d34cdf71868047
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558526"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten

So erhöhen Sie die Sicherheit von Benutzeranmeldungen:

- Verwenden von Windows Hello for Business
- Verwenden des Azure Active Directory-Kennwortschutzes (Azure AD)
- Verwenden der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA)
- Bereitstellen von Konfigurationen für den Identitäts- und Gerätezugriff
- Schutz vor Gefährdung der Anmeldeinformationen mit Azure AD Identity Protection

## <a name="windows-hello-for-business"></a>Windows Hello for Business

Windows Hello for Business in Windows 10 Enterprise ersetzt Kennwörter durch eine starke zweistufige Authentifizierung, wenn sich jemand auf einem Windows-Gerät anmeldet. Beide Faktoren zählen zu neuen Arten von Benutzeranmeldeinformationen, die mit einem Gerät verknüpft sind und biometrische Daten oder eine PIN erfordern.

Weitere Informationen finden Sie unter [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


## <a name="azure-ad-password-protection"></a>Azure AD-Kennwortschutz

Der Azure AD-Kennwortschutz erkennt und blockiert als schwach bekannte Kennwörter und deren Varianten und kann zusätzlich für Ihre Organisation spezifische schwache Ausdrücke blockieren. Listen standardmäßig global gesperrter Kennwörter werden automatisch auf alle Benutzer in einem Azure AD-Mandanten angewendet. Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter angeben. Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese Listen gesperrter Kennwörter überprüft, um die Verwendung von sicheren Kennwörtern zu erzwingen.

Weitere Informationen finden Sie unter [Konfigurieren des Azure AD-Kennwortschutzes](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA (mehrstufige Authentifizierung)

MFA erfordert, dass Nutzeranmeldungen einer zusätzlichen Überprüfung unterzogen werden, die über das Kennwort des Nutzerkontos hinausgeht. Selbst wenn ein böswilliger Nutzer ein Nutzerkontokennwort ermittelt, muss er in der Lage sein, auf eine zusätzliche Überprüfung zu antworten, z. B. eine Textnachricht, die an ein Smartphone gesendet wird, bevor der Zugriff gewährt wird.

![Das richtige Kennwort und eine zusätzliche Überprüfungsergebnisse bei einer erfolgreichen Anmeldung](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Der erste Schritt bei der Verwendung von MFA besteht darin, sie ***für alle Administratorkonten als erforderlich festzulegen** _ (diese Konten werden auch als privilegierte Konten bezeichnet).

Über diesen ersten Schritt hinaus empfiehlt Microsoft, die mehrstufige Authentifizierung für alle Benutzer vorzugeben.

Basierend auf Ihrem Microsoft 365-Plan gibt es drei Möglichkeiten, von Ihren Administratoren oder Nutzern die Verwendung der mehrstufigen Authentifizierung zu verlangen.

| Plan | Empfehlung |
|---------|---------|
|Alle Microsoft 365-Pläne (ohne Azure AD Premium P1- oder P2-Lizenzen)     |[Aktivieren Sie die Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Zu den Sicherheitsstandards in Azure AD gehört MFA für Nutzer und Administratoren.   |
|Microsoft 365 E3 (einschließlich Azure AD Premium P1-Lizenzen)     | Verwenden Sie [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common), um die folgenden Richtlinien zu konfigurieren: <br>- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (einschließlich Azure AD Premium P2-Lizenzen)     | Nutzen Sie den Azure AD-Identity Protection, beginnen Sie mit der Implementierung des von Microsoft [empfohlenen Satzes von bedingtem Zugriff und zugehörigen Richtlinien](../security/office-365-security/identity-access-policies.md), indem Sie die folgenden 2 Richtlinien nutzen:<br> - [MFA erforderlich, wenn das Anmelderisiko mittel oder hoch ist](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Nutzer mit hohem Risiko müssen das Kennwort ändern](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Sicherheitsstandards

Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden. Bei diesen Abonnements sind die Sicherheitsstandards aktiviert, sodass _*_alle Nutzer MFA mit der Microsoft Authenticator-App verwenden müssen_*_.
 
Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden. Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.

Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist. Sie können Sicherheitsstandards für MFA mit Richtlinien für den bedingten Zugriff oder für einzelne Konten deaktivieren.

Weitere Informationen finden Sie in der [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet werden und der Zugriff gewährt wird. Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:

- Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.

Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.

Sie können die Richtlinien für den bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. wenn die Anmeldung von einem kompatiblen Gerät aus erfolgen muss, z. B. von Ihrem Laptop unter Windows 10.

Für den bedingten Zugriff sind Azure AD Premium P1-Lizenzen erforderlich, die in Microsoft 365 E3 und E5 enthalten sind.

Weitere Informationen finden Sie in der [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Diese Methoden zusammen verwenden

Denken Sie dabei an Folgendes:

- Sie können die Sicherheitsstandards nicht aktivieren, wenn Sie Richtlinien für den bedingten Zugriff aktiviert haben.
- Sie können keine Richtlinien für den bedingten Zugriff aktivieren, wenn Sie die Sicherheitsstandards aktiviert haben.

Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Nutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App aufgefordert. 

Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards und Richtlinien für bedingten Zugriff.

| Methode | Aktiviert | Deaktiviert | Zusätzliche Authentifizierungsmethode |
|:-------|:-----|:-------|:-------|
| _ *Sicherheitsstandards**  | Richtlinien für bedingten Zugriff können nicht verwendet werden | Richtlinien für den bedingten Zugriff können verwendet werden | Microsoft Authenticator-App |
| **Richtlinien für bedingten Zugriff** | Wenn welche aktiviert sind, können Sie die Sicherheitsstandards nicht aktivieren | Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren  | Werden vom Benutzer während der MFA-Registrierung festgelegt  |
||||

## <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

Einstellungen und Richtlinien für den Identitäts- und Gerätezugriff sind empfohlene Voraussetzungen. Deren Einstellungen bestimmen in Kombination mit bedingtem Zugriff, Intune und Azure AD Identity Protection-Richtlinien für den Identitätsschutz, ob und unter welchen Bedingungen einer bestimmten Zugriffsanforderung zugestimmt werden soll. Diese Ermittlung basiert auf dem Benutzerkonto der Anmeldung, dem verwendeten Gerät, der vom Benutzer für die Anmeldung verwendeten App, dem Ort, an dem die Zugriffsanforderung erfolgt sowie einer Bewertung des Risikos der Anforderung. Diese Funktion trägt dazu bei, sicherzustellen, dass nur autorisierte Benutzer und Geräte auf Ihre kritischen Ressourcen zugreifen können.

>[!Note]
>Für Azure AD Identity Protection sind Azure AD Premium P2-Lizenzen erforderlich, die in Microsoft 365 E5 enthalten sind.
>

Identitäts- und Gerätezugriffsrichtlinien sind für die Verwendung auf drei Ebenen definiert: 

- Der grundlegende Schutz bietet ein Mindestmaß an Sicherheit für Ihre Identitäten und Geräte, die auf Ihre Apps und Daten zugreifen.
- Der Schutz vertraulicher Daten bietet zusätzliche Sicherheit für bestimmte Daten. Identitäten und Geräte müssen höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen.
- Der Schutz für Umgebungen mit strengen Datensicherheitsbestimmungen ist für in der Regel kleine Mengen von Daten bestimmt, die streng vertraulich sind, Geschäftsgeheimnisse enthalten oder Datenschutzbestimmungen unterliegen. Identitäten und Geräte müssen viel höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen. 

Diese Ebenen und die entsprechenden Konfigurationen bieten einheitliche Schutzniveaus für Ihre Daten, Identitäten und Geräte.

Microsoft empfiehlt dringend das Konfigurieren und Bereitstellen von Identitäts- und Gerätezugriffsrichtlinien in Ihrer Organisation, einschließlich spezifischer Einstellungen für Microsoft Teams, Exchange Online und SharePoint. Weitere Informationen finden Sie unter [Konfigurationen für den Identitäts- und Gerätezugriff](../security/office-365-security/microsoft-365-policies-configurations.md).

## <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten. Azure AD Identity Protection bietet verschiedene Möglichkeiten um zu verhindern, dass ein Angreifer die Anmeldeinformationen eines Benutzerkontos kompromittiert.

Mit Azure AD Identity Protection können Sie Folgendes:

|Funktion|Beschreibung|
|:---------|:---------|
| Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation | Azure AD verwendet das maschinelle Lernen, um Anomalien und verdächtige Aktivitäten wie Anmeldeaktivitäten und Aktivitäten nachdem Anmelden zu erkennen. Anhand dieser Daten generiert Azure AD Identity Protection Berichte und Warnungen, mit denen Sie die Probleme bewerten und entsprechende Maßnahmen ergreifen können.|
|Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese|Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Zusätzlich zu anderen Kontrollelementen für den bedingten Zugriff von Azure AD und Microsoft Intune können mithilfe dieser Richtlinien entweder Zugriffsversuche automatisch blockiert oder Korrekturmaßnahmen ergriffen werden. Hierzu gehören Kennwortzurücksetzungen und die Anforderung von Azure AD Multi-Factor Authentication für nachfolgende Anmeldeversuche. |
| Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben | Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung. |
|||

Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Technische Administratorressourcen für mehrstufige Authentifizierung (MFA) und sichere Anmeldungen

- [MFA für Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Identitäts-Roadmap für Microsoft 365](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-Schulungsvideos](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Konfigurieren der Registrierungsrichtlinie für Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Konfigurationen für den Identitäts- und Gerätezugriff](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a>Nächster Schritt

[Verwalten von Benutzerkonten](manage-microsoft-365-accounts.md)