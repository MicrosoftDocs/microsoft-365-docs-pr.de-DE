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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Machen Sie Ihr Unternehmen sicherer gegen Kennwortangriffe, verbieten Sie gängige Kennwörter und aktivieren Sie die risikobasierte mehrstufige Authentifizierung.
ms.openlocfilehash: f2b9b9188a6f05bbcdae45dcc22d401e1eb6f1a8
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593909"
---
# <a name="password-policy-recommendations"></a>Empfehlungen für Kennwortrichtlinien

Als Administrator einer Organisation sind Sie für das Einrichten der Kennwortrichtlinie für Benutzer in Ihrer Organisation verantwortlich. das Festlegen der Kennwortrichtlinie kann kompliziert und verwirrend sein, und dieser Artikel enthält Empfehlungen, wie Sie Ihre Organisation besser vor Kennwortangriffen schützen können.
  
Um zu ermitteln, wie oft Microsoft 365-Kennwörter in Ihrer Organisation ablaufen, lesen Sie die Informationen unter [Festlegen der Kennwortablaufrichtlinie für Microsoft 365](../manage/set-password-expiration-policy.md).

Weitere Informationen über Microsoft 365-Kennwörter finden Sie unter:

[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](../add-users/set-password-to-never-expire.md) (Artikel)

[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)

[Erneutes Senden eines Benutzerkennworts – Administratorhilfe](../add-users/resend-user-password.md) (Artikel)
  
## <a name="understanding-password-recommendations"></a>Grundlegendes zu Kennwortempfehlungen

Empfohlene Kennwortpraktiken werden in einige allgemeine Kategorien unterteilt:
  
- **Schutz vor häufig vorkommenden Angriffen** Legen Sie fest, wo Benutzer Kennwörter eingeben können (bekannte und vertrauenswürdige Geräte mit guter Erkennung von Malware, überprüften Websites) und welche Kennwörter verwendet werden dürfen (Länge und Eindeutigkeit).

- **Eindämmung erfolgreicher Angriffe** Bei der Eindämmung erfolgreicher Hackerangriffe geht es darum, die Gefährdung auf einen bestimmten Dienst einzuschränken oder den Schaden komplett zu verhindern, wenn das Kennwort eines Benutzers gestohlen wird. So sollte beispielsweise sichergestellt werden, dass durch den Angriff auf Ihre Social Networking-Anmeldeinformationen Ihr Bankkonto nicht angreifbar wird oder dass ein schlecht bewachtes Konto keine Reset-Links für ein wichtiges Konto zulässt.

- **Die menschliche Natur verstehen** Viele gültige Kennwortpraktiken scheitern an natürlichen menschlichen Verhaltensweisen. Das Verständnis der menschlichen Natur ist von äußerster Bedeutung, denn Untersuchungen zeigen, dass fast jede Regel, die Sie Ihren Benutzern auferlegen, zu einer Schwächung der Kennwortqualität führt. Anforderungen an Länge, Sonderzeichen und Kennwortänderungen führen zu einer Normalisierung der Kennwörter, was es Angreifern erleichtert, Kennwörter zu erraten oder zu knacken.

## <a name="password-guidelines-for-administrators"></a>Kennwortrichtlinien für Administratoren

Das primäre Ziel eines sichereren Kennwortsystems ist die Vielfalt der Kennwörter. Sie möchten, dass Ihre Kennwortrichtlinie viele verschiedene und schwer zu erratende Kennwörter umfasst. Hier sind ein paar Empfehlungen, wie Sie Ihre Organisation am besten schützen können.
  
- Halten Sie eine Mindestlänge von 8 Zeichen ein (länger ist nicht unbedingt besser).

- Legen Sie keine Anforderungen an die Zeichenzusammensetzung fest. Zum Beispiel \*&amp;(^%$

- Fordern Sie kein obligatorisches periodisches Zurücksetzen der Kennwörter für Benutzerkonten.

- Verbieten Sie gängige Kennwörter, um die anfälligsten Kennwörter von Ihrem System fernzuhalten.

- Informieren Sie Ihre Benutzer, dass sie ihre Organisationskennwörter nicht für private Zwecke wiederverwenden dürfen.

- Erzwingen Sie die Registrierung für die [mehrstufige Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)

- Aktivieren Sie risikobasierte mehrstufige Authentifizierung

### <a name="password-guidance-for-your-users"></a>Kennwortratgeber für Benutzer

Hier finden Sie einige Kennwortanleitungen für Benutzer in Ihrer Organisation. Informieren Sie Ihre Benutzer über diese Empfehlungen und setzen Sie die empfohlenen Kennwortrichtlinien auf Organisationsebene durch.
  
- Verwenden Sie kein Kennwort, das einem auf anderen Websites verwendeten Kennwort entspricht oder ähnlich ist.

- Verwenden Sie kein einzelnes Wort, z. B. **Kennwort** und keinen häufig verwendeten Ausdruck, z. B. **Ichliebedich**

- Verwenden Sie Kennwörter, die selbst für Personen schwer zu erraten sind, die viel über Sie wissen (wie z. B. die Namen und Geburtstage Ihrer Freunde und Familie, Ihre Lieblingsbands und Phrasen, die Sie gerne verwenden).

## <a name="some-common-approaches-and-their-negative-impacts"></a>Einige allgemeine Ansätze sowie deren negative Auswirkungen

Dies sind einige der am häufigsten verwendeten Kennwortverwaltungspraktiken, aber Recherchen warnen vor deren negativen Auswirkungen.
  
### <a name="password-expiration-requirements-for-users"></a>Anforderungen für den Ablauf von Benutzerkennwörtern

Anforderungen für den Ablauf von Kennwörtern schaden mehr als dass sie nützen, da diese Anforderungen die Benutzer dazu veranlassen, vorhersagbare Passwörter zu wählen, die aus aufeinanderfolgenden Wörtern und Zahlen bestehen, die eng miteinander verwandt sind. In diesen Fällen kann das nächste Kennwort anhand des vorherigen Kennwortes vorhergesagt werden. Anforderungen für den Ablauf von Kennwörtern bieten keine Vorteile hinsichtlich der Abwehr von Angriffen, da Cyberkriminelle Anmeldeinformationen, sobald sie diese herausgefunden haben, fast immer sofort verwenden. Weitere Informationen finden Sie unter [Zeit zum Überdenken der obligatorischen Kennwortänderungen](https://go.microsoft.com/fwlink/p/?linkid=861018).
  
### <a name="requiring-long-passwords"></a>Anforderung an die Länge von Kennwörtern

Anforderung an die Länge von Kennwörtern (mehr als ca. 10 Zeichen) können zu einem vorhersehbaren und nicht wünschenswerten Benutzerverhalten führen. Benutzer, die gezwungen werden, ein Kennwort mit 16 Zeichen zu verwenden, neigen beispielsweise dazu, sich wiederholende Muster wie **viervierviervier** oder **KennwortKennwort** auszuwählen, die die Anforderung an die Zeichenlänge erfüllen, aber nicht schwer zu erraten sind. Darüber hinaus erhöhen Längenanforderungen die Wahrscheinlichkeit, dass Benutzer andere unsichere Methoden verwenden, wie z. B., ihre Kennwörter aufzuschreiben, wiederzuverwenden oder unverschlüsselt in ihren Dokumenten zu speichern. Um Benutzer zu ermutigen, eindeutige Kennwörter zu erstellen, empfehlen wir eine angemessene Mindestlängenanforderung von 8 Zeichen.
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Fordern der Verwendung von mehreren Zeichensätzen

Anforderungen an die Kennwortkomplexität reduzieren den Schlüsselraum und veranlassen Benutzer dazu, auf vorhersehbare Weise zu handeln, wodurch sie mehr Schaden als Nutzen anrichten. Die meisten Systeme erzwingen ein bestimmtes Maß an Anforderungen an die Kennwortkomplexität. Beispielsweise müssen Kennwörter Zeichen aus allen drei der folgenden Kategorien enthalten:
  
- Großbuchstaben

- Kleinbuchstaben

- Nicht alphanumerische Zeichen

Die meisten Benutzer verwenden ähnliche Muster, z. B. einen Großbuchstabe an der ersten Position, ein Symbol an der letzten Position und eine Zahl an den letzten 2 Stellen. Cyberkriminelle wissen dies, daher führen sie ihre Wörterbuchangriffe unter Verwendung der am häufigsten verwendeten Austauschzeichen durch, "$" für "s", "@" für "a", "1" für "l". Wenn Sie Ihre Benutzer zwingen, eine Kombination aus Groß- und Kleinbuchstaben, Ziffern und Sonderzeichen zu wählen, wirkt sich das negativ aus. Einige Komplexitätsanforderungen hindern Benutzer sogar daran, sichere und einprägsame Kennwörter zu verwenden, und zwingen sie dazu, weniger sichere und weniger einprägsame Kennwörter zu wählen.
  
## <a name="successful-patterns"></a>Erfolgreiche Muster

Im Gegensatz dazu finden Sie hier einige Empfehlungen zur Förderung der Kennwortvielfalt.
  
### <a name="ban-common-passwords"></a>Häufig verwendete Kennwörter sperren

Die wichtigste Kennwortanforderung, die Sie Ihren Benutzern bei der Erstellung von Kennwörtern auferlegen sollten, besteht darin, die Verwendung häufig verwendeter Kennwörter zu verbieten, um die Anfälligkeit Ihres Unternehmens für Brute-Force-Kennwortangriffe zu verringern. Häufig verwendete Benutzerkennwörter sind beispielsweise **abcdefg**, **Kennwort**, **123456**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Weisen Sie die Benutzer an, keine Kennwörter der Organisation an anderer Stelle wiederzuverwenden

Eine der wichtigsten Botschaften, die Sie den Benutzern in Ihrer Organisation vermitteln müssen, ist, dass Sie ihr Organisationskennwort nirgendwo anders wiederverwenden dürfen. Die Verwendung von Organisationskennwörtern auf externen Websites erhöht die Wahrscheinlichkeit erheblich, dass Cyberkriminelle diese Kennwörter knacken.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Erzwingen Sie die Registrierung für die mehrstufige Authentifizierung

Stellen Sie sicher, dass Ihre Benutzer Kontakt- und Sicherheitsinformationen aktualisieren (z. B. eine alternative E-Mail-Adresse, Telefonnummer oder ein Gerät, das für Pushbenachrichtigungen registriert ist), damit sie auf Sicherheitsherausforderungen reagieren und über Sicherheitsereignisse benachrichtigt werden können. Aktualisierte Kontakt- und Sicherheitsinformationen helfen Benutzern, ihre Identität zu verifizieren, wenn sie ihr Passwort vergessen haben oder wenn jemand anderes versucht, ihr Konto zu übernehmen. Zudem wird ein Out-of-Band-Benachrichtigungskanal für den Fall bereitgestellt, dass Sicherheitsereignisse wie Anmeldeversuche oder geänderte Kennwörter eintreten. 
  
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

## <a name="related-content"></a>Verwandte Inhalte

[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](../add-users/set-password-to-never-expire.md) (Artikel)

[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)

[Erneutes Senden eines Benutzerkennworts – Administratorhilfe](../add-users/resend-user-password.md) (Artikel)
