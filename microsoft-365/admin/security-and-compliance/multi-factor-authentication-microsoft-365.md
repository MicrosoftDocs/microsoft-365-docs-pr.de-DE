---
title: Mehrstufige Authentifizierung für Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über die mehrstufige Authentifizierung in Microsoft 365.
ms.openlocfilehash: 7d62d88acb5137bd0674de7a42b44103bc9fc5f0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926546"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Mehrstufige Authentifizierung für Microsoft 365

Kennwörter sind die am häufigsten verwendeten Methoden zum Authentifizieren einer Anmeldung bei einem Computer oder Onlinedienst, sind aber auch die anfälligste Methode. Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen bei verschiedenen Computern und Diensten verwenden.

Um eine zusätzliche Sicherheitsstufe für Anmeldungen zu bieten, müssen Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) verwenden, die sowohl ein Kennwort verwendet, das sicher sein sollte, als auch eine zusätzliche Überprüfungsmethode basierend auf:

- Etwas, das Sie bei sich haben, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.
- Etwas, über das Sie einzigartig und ohne Besonderes verfügen, z. B. Ihre Fingerabdrücke, Ihr Gesicht oder ein anderes biometrisches Attribut.

Die zusätzliche Überprüfungsmethode wird erst nach der Überprüfung des Kennworts des Benutzers verwendet. Bei MFA verfügt der Angreifer auch dann nicht über Ihr Smartphone oder Ihren Fingerabdruck, wenn ein starkes Benutzerkennwort gefährdet ist, um die Anmeldung zu vervollständigen.

## <a name="mfa-support-in-microsoft-365"></a>Unterstützung von MFA in Microsoft 365

Standardmäßig unterstützen sowohl Microsoft 365 als auch Office 365 MFA für Benutzerkonten mit:

- Eine an ein Telefon gesendete Textnachricht, für die der Benutzer einen Überprüfungscode eingeben muss.
- Ein Telefonanruf.
- Die Microsoft Authenticator-Smartphone-App.

In beiden Fällen verwendet die MFA-Anmeldung die Methode "Etwas, das Sie bei Ihnen haben, das nicht einfach dupliziert werden kann" für die zusätzliche Überprüfung. Es gibt mehrere Möglichkeiten, MFA für Microsoft 365 und Office 365 zu aktivieren:

- Mit Sicherheitseinstellungen
- Mit Richtlinien für bedingten Zugriff
- Für jedes einzelne Benutzerkonto (nicht empfohlen)

Diese Methoden basieren auf Ihrem Microsoft 365-Plan.

|Plan|Empfehlung|Typ des Kunden|
|---|---|---|
|Alle Microsoft 365-Pläne|Verwenden Sie Sicherheitseinstellungen, die MFA für alle Benutzerkonten erfordern. <p> Sie können MFA pro Benutzer auch für einzelne Benutzerkonten konfigurieren, dies wird jedoch nicht empfohlen.|Kleinunternehmen|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) Premium -P1-Lizenzen|Verwenden Sie Richtlinien für bedingten Zugriff, um MFA für Benutzerkonten basierend auf Gruppenmitgliedschaft, Apps oder anderen Kriterien zu verlangen.|Small Business to Enterprise|
|Microsoft 365 E5 <p> Azure AD Premium -P2-Lizenzen|Verwenden Sie Azure AD Identity Protection, um MFA basierend auf anmeldebezogenen Risikokriterien zu verlangen.|Unternehmen|
||||

### <a name="security-defaults"></a>Sicherheitsstandards

Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden. Für diese Abonnements sind die Sicherheitseinstellungen aktiviert, die:

- Erfordert, dass alle Benutzer MFA mit der Microsoft Authenticator-App verwenden.
- Blockiert die Legacyauthentifizierung.

Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden. Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.

Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist. Sie können Sicherheitseinstellungen für MFA mit Richtlinien für bedingten Zugriff deaktivieren.

Sie aktivieren oder deaktivieren Sicherheitseinstellungen im **Eigenschaftenbereich** für Azure AD im Azure-Portal.

![Bild der Seite "Verzeichniseigenschaften".](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Sie können Sicherheitseinstellungen mit einem beliebigen Microsoft 365-Plan verwenden.

Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet und zugelassen werden. Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:

- Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.

Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.

Sie können richtlinien für bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. die Anforderung von MFA für bestimmte Apps oder die Anmeldung über ein kompatibles Gerät, z. B. Ihren Laptop unter Windows 10.

Sie konfigurieren Richtlinien für bedingten Zugriff **im** Sicherheitsbereich für Azure AD im Azure-Portal.

![Abbildung der Menüoption für bedingten Zugriff](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Sie können Richtlinien für bedingten Zugriff mit:

- Microsoft 365 Business Premium
- Microsoft 365 E3 und E5
- Azure AD Premium P1- und Azure AD Premium P2-Lizenzen

Für kleine Unternehmen mit Microsoft 365 Business Premium können Sie richtlinien für bedingten Zugriff ganz einfach mit den folgenden Schritten verwenden:

1. Erstellen Sie eine Gruppe, die die Benutzerkonten enthält, für die MFA erforderlich ist.
2. Aktivieren Sie die **Richtlinie "MFA für globale Administratoren erforderlich".**
3. Erstellen Sie eine gruppenbasierte Richtlinie für bedingten Zugriff mit den folgenden Einstellungen:
    - Zuordnungen > Benutzer und Gruppen: Der Name Ihrer Gruppe aus Schritt 1 oben.
    - Zuweisungen > Cloud-Apps oder -Aktionen: Alle Cloud-Apps.
    - Zugriffssteuerungen > Gewähren > gewähren > mehrstufige Authentifizierung erforderlich.
4. Aktivieren Sie die Richtlinie.
5. Fügen Sie der in Schritt 1 erstellten Gruppe ein Benutzerkonto hinzu, und testen Sie es.
6. Wenn Sie MFA für zusätzliche Benutzerkonten benötigen möchten, fügen Sie sie der in Schritt 1 erstellten Gruppe hinzu.

Mit dieser Richtlinie für bedingten Zugriff können Sie die MFA-Anforderung in Ihrem eigenen Tempo für Ihre Benutzer rollouten.

Unternehmen sollten allgemeine [Richtlinien für bedingten Zugriff verwenden,](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) um die folgenden Richtlinien zu konfigurieren:

- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Mit Azure AD Identity Protection können Sie eine zusätzliche Richtlinie für bedingten Zugriff erstellen, um MFA zu verlangen, wenn das Anmelderisiko [mittel oder hoch ist.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)

Sie können Azure AD Identity Protection und risikobasierte Richtlinien für bedingten Zugriff mit:

- Microsoft 365 E5
- Azure AD Premium -P2-Lizenzen

Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>Legacy-MFA pro Benutzer (nicht empfohlen)

Sie sollten entweder Sicherheitseinstellungen oder Richtlinien für bedingten Zugriff verwenden, um MFA für Ihre Benutzerkonto-Anmeldungen zu verlangen. Wenn eine dieser Konten jedoch nicht verwendet werden kann, empfiehlt Microsoft dringend MFA für Benutzerkonten mit Administratorrollen, insbesondere der globalen Administratorrolle, für Abonnements beliebiger Größe.

Sie aktivieren MFA für einzelne Benutzerkonten im **Bereich "Aktive** Benutzer" im Microsoft 365 Admin Center.

![Bild der Mehrstufigen Authentifizierungsoption auf der Seite "Aktive Benutzer"](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Nach der Aktivierung wird der Benutzer bei der nächsten Anmeldung aufgefordert, sich für MFA zu registrieren und die zusätzliche Überprüfungsmethode zu wählen und zu testen.

### <a name="using-these-methods-together"></a>Diese Methoden zusammen verwenden

Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards, Richtlinien für bedingten Zugriff und Nutzerkonteneinstellungen.

||Aktiviert|Deaktiviert|Sekundäre Authentifizierungsmethode|
|---|---|---|---|
|**Sicherheitsstandards**|Richtlinien für bedingten Zugriff können nicht verwendet werden|Richtlinien für den bedingten Zugriff können verwendet werden|Microsoft Authenticator-App|
|**Richtlinien für bedingten Zugriff**|Falls aktiviert, können Sie keine Sicherheitseinstellungen aktivieren.|Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren|Nutzerdefiniert bei der MFA-Registrierung|
|**Legacy-MFA pro Benutzer (nicht empfohlen)**|Setzt Sicherheitseinstellungen und Richtlinien für bedingten Zugriff außer Kraft, die MFA bei jeder Anmeldung erfordern|Außer Kraft gesetzt durch Sicherheitseinstellungen und Richtlinien für bedingten Zugriff|Nutzerdefiniert bei der MFA-Registrierung|
||||

Wenn Sicherheitseinstellungen aktiviert sind, werden alle neuen Benutzer bei der nächsten Anmeldung zur Registrierung der MFA und zur Verwendung der Microsoft Authenticator-App aufgefordert.

## <a name="ways-to-manage-mfa-settings"></a>Möglichkeiten zum Verwalten von MFA-Einstellungen

Es gibt zwei Möglichkeiten zum Verwalten von MFA-Einstellungen.

Im Azure Portal können Sie:

- Aktivieren und Deaktivieren von Sicherheitseinstellungen
- Konfigurieren von Richtlinien für bedingten Zugriff

Im Microsoft 365 Admin Center können Sie benutzer- und Dienst-MFA-Einstellungen konfigurieren.

## <a name="your-next-step"></a>Nächster Schritt

[Einrichten von MFA für Microsoft 365](set-up-multi-factor-authentication.md)
