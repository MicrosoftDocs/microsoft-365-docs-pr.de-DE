---
title: Empfehlungen für Kennwortrichtlinien
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Erfahren Sie, wie Sie Ihre Organisation vor Kennwortangriffen schützen und warum Sie häufig verwendete Kennwörter verbieten und die risikobasierte mehrstufige Authentifizierung aktivieren sollten.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015923"
---
# <a name="password-policy-recommendations"></a>Empfehlungen für Kennwortrichtlinien
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
Um zu ermitteln, wie oft Microsoft 365-Kennwörter in Ihrer Organisation ablaufen, lesen Sie die Informationen unter [Festlegen der Kennwortablaufrichtlinie für Microsoft 365](../manage/set-password-expiration-policy.md).

Weitere Informationen über Microsoft 365-Kennwörter finden Sie in diesen [verwandten Artikeln](#related-articles).
  
## <a name="understanding-password-recommendations"></a>Grundlegendes zu Kennwortempfehlungen

Empfohlene Kennwortpraktiken werden in einige allgemeine Kategorien unterteilt:
  
- **Schutz vor häufig vorkommenden Angriffen** Legen Sie fest, wo Benutzer Kennwörter eingeben können (bekannte und vertrauenswürdige Geräte mit guter Erkennung von Malware, überprüften Websites) und welche Kennwörter verwendet werden dürfen (Länge und Eindeutigkeit).

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>Kennwortrichtlinien für Administratoren

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- Halten Sie eine Mindestlänge von 8 Zeichen ein (länger ist nicht unbedingt besser).

- Don't require character composition requirements. For example, \*&amp;(^%$

- Fordern Sie kein obligatorisches periodisches Zurücksetzen der Kennwörter für Benutzerkonten.

- Verbieten Sie gängige Kennwörter, um die anfälligsten Kennwörter von Ihrem System fernzuhalten.

- Informieren Sie Ihre Benutzer, dass sie ihre Organisationskennwörter nicht für private Zwecke wiederverwenden dürfen.

- Erzwingen Sie die Registrierung für die [mehrstufige Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)

- Aktivieren Sie risikobasierte mehrstufige Authentifizierung

### <a name="password-guidance-for-your-users"></a>Kennwortratgeber für Benutzer

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- Verwenden Sie kein Kennwort, das einem auf anderen Websites verwendeten Kennwort entspricht oder ähnlich ist.

- Verwenden Sie kein einzelnes Wort, z. B. **Kennwort** und keinen häufig verwendeten Ausdruck, z. B. **Ichliebedich**

- Verwenden Sie Kennwörter, die selbst für Personen schwer zu erraten sind, die viel über Sie wissen (wie z. B. die Namen und Geburtstage Ihrer Freunde und Familie, Ihre Lieblingsbands und Phrasen, die Sie gerne verwenden).

## <a name="some-common-approaches-and-their-negative-impacts"></a>Einige allgemeine Ansätze sowie deren negative Auswirkungen

Dies sind einige der am häufigsten verwendeten Kennwortverwaltungspraktiken, aber Recherchen warnen vor deren negativen Auswirkungen.
  
### <a name="password-expiration-requirements-for-users"></a>Anforderungen für den Ablauf von Benutzerkennwörtern

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>Anforderung an die Länge von Kennwörtern

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Fordern der Verwendung von mehreren Zeichensätzen

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- Großbuchstaben

- Kleinbuchstaben

- Nicht alphanumerische Zeichen

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>Erfolgreiche Muster

Im Gegensatz dazu finden Sie hier einige Empfehlungen zur Förderung der Kennwortvielfalt.
  
### <a name="ban-common-passwords"></a>Häufig verwendete Kennwörter sperren

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Weisen Sie die Benutzer an, keine Kennwörter der Organisation an anderer Stelle wiederzuverwenden

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Erzwingen Sie die Registrierung für die mehrstufige Authentifizierung

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
Weitere Informationen finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Aktivieren Sie die risikobasierte mehrstufige Authentifizierung

Durch die risikobasierte mehrstufige Authentifizierung wird sichergestellt, dass sich der Benutzer nachweisen kann, dass er der rechtmäßige Kontoinhaber ist, falls unser System verdächtige Aktivitäten erkennt. 
  
## <a name="want-to-know-more-recommended-reading"></a>Möchten Sie mehr darüber wissen? Empfohlene Literatur

- [Können starke Webkennwörter etwas bewirken?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Kennwortportfolios und der "Finite-Effort"-Benutzer](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Verhindern unsicherer Kennwörter, indem man die Gedanken der Benutzer liest](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Auswählen sicherer Kennwörter](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Zeit zum Überdenken der obligatorischen Kennwortänderungen](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Liste der schlechtesten Kennwörter 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Herunterladen von Dateien aus dem Internet](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>Verwandte Artikel

[Zurücksetzen von Kennwörtern](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[Erneutes Senden eines Benutzerkennworts – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
