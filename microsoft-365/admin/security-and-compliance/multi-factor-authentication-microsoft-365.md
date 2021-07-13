---
title: Mehrstufige Authentifizierung für Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) verwendet sowohl ein Kennwort, das stark sein sollte, als auch eine zusätzliche Überprüfungsmethode.
ms.openlocfilehash: 9b3347f1a8e7b1f62c9bbfe77a7f14c221ef28b5
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393643"
---
# <a name="multifactor-authentication-for-microsoft-365"></a>Mehrstufige Authentifizierung für Microsoft 365

Kennwörter sind die am häufigsten verwendete Methode zum Authentifizieren einer Anmeldung bei einem Computer oder Onlinedienst, sind aber auch am anfälligsten. Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen bei verschiedenen Computern und Diensten verwenden.

Um eine zusätzliche Sicherheitsstufe für Anmeldungen bereitzustellen, müssen Sie die mehrstufige Authentifizierung (MFA) verwenden, die sowohl ein Kennwort verwendet, das stark sein sollte, als auch eine zusätzliche Überprüfungsmethode basierend auf:

- Etwas, das Sie haben, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.
- Etwas, das Sie eindeutig und in besonderer Weise besitzen, z. B. Ihre Fingerabdrücke, Ihr Gesicht oder ein anderes biometrisches Attribut.

Die zusätzliche Überprüfungsmethode wird erst verwendet, nachdem das Kennwort des Benutzers überprüft wurde. Bei der MFA verfügt der Angreifer selbst dann nicht über Ihr Smartphone oder Ihren Fingerabdruck, wenn ein sicheres Benutzerkennwort kompromittiert wurde, um die Anmeldung abzuschließen.

## <a name="mfa-support-in-microsoft-365"></a>MFA-Unterstützung in Microsoft 365

Standardmäßig unterstützen sowohl Microsoft 365 als auch Office 365 MFA für Benutzerkonten mithilfe von:

- Eine an ein Telefon gesendete Textnachricht, die erfordert, dass der Benutzer einen Überprüfungscode eingibt.
- Ein Telefonanruf.
- Die Microsoft Authenticator Smartphone-App.

In beiden Fällen verwendet die MFA-Anmeldung die Methode "Etwas, das Sie bei Ihnen haben, das nicht einfach dupliziert werden kann" für die zusätzliche Überprüfung. Es gibt mehrere Möglichkeiten, MFA für Microsoft 365 und Office 365 zu aktivieren:

- Mit Sicherheitsstandards
- Mit Richtlinien für bedingten Zugriff
- Für jedes einzelne Benutzerkonto (nicht empfohlen)

Diese Methoden basieren auf Ihrem Microsoft 365 Plan.

|Plan|Empfehlung|Typ des Kunden|
|---|---|---|
|Alle pläne Microsoft 365|Verwenden Sie Sicherheitsstandards, die MFA für alle Benutzerkonten erfordern. <p> Sie können auch MFA pro Benutzer für einzelne Benutzerkonten konfigurieren, dies wird jedoch nicht empfohlen.|Kleinunternehmen|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) Premium P1-Lizenzen|Verwenden Sie Richtlinien für bedingten Zugriff, um MFA für Benutzerkonten basierend auf der Gruppenmitgliedschaft, Apps oder anderen Kriterien anzufordern.|Kleinunternehmen zu Unternehmen|
|Microsoft 365 E5 <p> Azure AD Premium P2 Lizenzen|Verwenden Sie Azure AD Identity Protection, um MFA basierend auf Anmelderisikokriterien anzufordern.|Enterprise|
||||

### <a name="security-defaults"></a>Sicherheitsstandards

Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden. Für diese Abonnements sind die Sicherheitsstandards aktiviert, die:

- Erfordert, dass alle Ihre Benutzer MFA mit der Microsoft Authenticator-App verwenden.
- Blockiert die Legacyauthentifizierung.

Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden. Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.

Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist. Sie können Sicherheitsstandards für MFA mit Richtlinien für bedingten Zugriff deaktivieren.

Sie aktivieren oder deaktivieren Die Sicherheitsstandards im **Eigenschaftenbereich** für Azure AD im Azure-Portal.

![Abbildung der Seite "Verzeichniseigenschaften".](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Sie können Sicherheitsstandards mit jedem Microsoft 365 Plan verwenden.

Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet und zugelassen werden. Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:

- Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.

Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.

Sie können richtlinien für bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. das Anfordern von MFA für bestimmte Apps oder das Anmelden über ein kompatibles Gerät, z. B. ihren Laptop, auf dem Windows 10 ausgeführt wird.

Sie konfigurieren Richtlinien für bedingten Zugriff im **Sicherheitsbereich** für Azure AD im Azure-Portal.

![Bild der Menüoption für bedingten Zugriff](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Sie können Richtlinien für bedingten Zugriff mit folgenden Aktionen verwenden:

- Microsoft 365 Business Premium
- Microsoft 365 E3 und E5
- lizenzen für Azure AD Premium P1 und Azure AD Premium P2

Für kleine Unternehmen mit Microsoft 365 Business Premium können Sie richtlinien für bedingten Zugriff ganz einfach mit den folgenden Schritten verwenden:

1. Erstellen Sie eine Gruppe, die die Benutzerkonten enthält, die MFA erfordern.
2. Aktivieren Sie die Richtlinie **"MFA für globale Administratoren anfordern".**
3. Erstellen Sie eine gruppenbasierte Richtlinie für bedingten Zugriff mit den folgenden Einstellungen:
    - Aufgaben > Benutzer und Gruppen: Der Name Ihrer Gruppe aus Schritt 1 oben.
    - Aufgaben > Cloud-Apps oder -Aktionen: alle Cloud-Apps.
    - Zugriffssteuerungen > gewähren > Zugriff gewähren > mehrstufige Authentifizierung erforderlich.
4. Aktivieren Sie die Richtlinie.
5. Fügen Sie der in Schritt 1 oben erstellten Gruppe ein Benutzerkonto hinzu, und testen Sie.
6. Um MFA für zusätzliche Benutzerkonten zu benötigen, fügen Sie sie der in Schritt 1 erstellten Gruppe hinzu.

Mit dieser Richtlinie für bedingten Zugriff können Sie die MFA-Anforderung für Ihre Benutzer in Ihrem eigenen Tempo bereitstellen.

Unternehmen sollten [allgemeine Richtlinien für bedingten Zugriff](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) verwenden, um die folgenden Richtlinien zu konfigurieren:

- [MFA für Administratoren erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [MFA für alle Nutzer erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Blockieren von Legacy-Authentifizierung](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Mit Azure AD Identity Protection können Sie eine zusätzliche Richtlinie für bedingten Zugriff erstellen, um [MFA zu erfordern, wenn das Anmelderisiko mittel oder hoch ist.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)

Sie können Azure AD Identity Protection und risikobasierte Richtlinien für bedingten Zugriff verwenden mit:

- Microsoft 365 E5
- Azure AD Premium P2 Lizenzen

Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>Legacy-MFA pro Benutzer (nicht empfohlen)

Sie sollten entweder Sicherheitsstandards oder Richtlinien für bedingten Zugriff verwenden, um MFA für Ihre Benutzerkontoanmeldungen zu erfordern. Wenn jedoch eine davon nicht verwendet werden kann, empfiehlt Microsoft dringend MFA für Benutzerkonten mit Administratorrollen, insbesondere der globalen Administratorrolle, für Abonnements jeder Größe.

Sie aktivieren MFA für einzelne Benutzerkonten im **aktiven Benutzerbereich** des Microsoft 365 Admin Center.

![Abbildung der Option "Mehrstufige Authentifizierung" auf der Seite "Aktive Benutzer"](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Nach der Aktivierung wird der Benutzer bei der nächsten Anmeldung aufgefordert, sich für MFA zu registrieren und die zusätzliche Überprüfungsmethode auszuwählen und zu testen.

### <a name="using-these-methods-together"></a>Diese Methoden zusammen verwenden

Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards, Richtlinien für bedingten Zugriff und Nutzerkonteneinstellungen.

|*Element*|Aktiviert|Deaktiviert|Sekundäre Authentifizierungsmethode|
|---|---|---|---|
|**Sicherheitsstandards**|Richtlinien für bedingten Zugriff können nicht verwendet werden|Richtlinien für den bedingten Zugriff können verwendet werden|Microsoft Authenticator-App|
|**Richtlinien für bedingten Zugriff**|Wenn eines aktiviert ist, können Sie die Sicherheitsstandards nicht aktivieren.|Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren|Nutzerdefiniert bei der MFA-Registrierung|
|**Legacy-MFA pro Benutzer (nicht empfohlen)**|Außerkraftsetzung von Sicherheitsstandards und Richtlinien für bedingten Zugriff, die MFA bei jeder Anmeldung erfordern|Außer Kraft gesetzt durch Sicherheitsstandards und Richtlinien für bedingten Zugriff|Nutzerdefiniert bei der MFA-Registrierung|
||||

Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Benutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App bei der nächsten Anmeldung aufgefordert.

## <a name="ways-to-manage-mfa-settings"></a>Möglichkeiten zum Verwalten von MFA-Einstellungen

Es gibt zwei Möglichkeiten zum Verwalten von MFA-Einstellungen.

Im Azure-Portal haben Sie folgende Möglichkeiten:

- Aktivieren und Deaktivieren von Sicherheitsstandards
- Konfigurieren von Richtlinien für bedingten Zugriff

Im Microsoft 365 Admin Center können Sie MFA-Einstellungen pro Benutzer und Dienst konfigurieren.

## <a name="next-steps"></a>Nächste Schritte

[Einrichten der MFA für Microsoft 365](set-up-multi-factor-authentication.md)

## <a name="related-content"></a>Verwandte Inhalte

[Aktivieren der mehrstufigen Authentifizierung](../../business-video/turn-on-mfa.md) (Video)\
[Aktivieren der mehrstufigen Authentifizierung für Ihr Telefon](../../business-video/set-up-mfa.md) (Video)