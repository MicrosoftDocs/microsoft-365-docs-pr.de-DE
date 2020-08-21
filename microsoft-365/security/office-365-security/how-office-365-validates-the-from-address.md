---
title: Wie EoP die Absenderadresse überprüft, um Phishing zu verhindern
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die Arten von e-Mail-Adressen informieren, die von Exchange Online Protection (EoP) und Outlook.com akzeptiert oder abgelehnt werden, um Phishing zu verhindern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827421"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Wie EoP die Absenderadresse überprüft, um Phishing zu verhindern

Phishing-Angriffe stellen eine ständige Bedrohung für jede e-Mail-Organisation dar. Zusätzlich zur Verwendung [gefälschter Absender-e-Mail-Adressen](anti-spoofing-protection.md)verwenden Angreifer häufig Werte in der von-Adresse, die Internetstandards verletzen. Um diese Art von Phishing zu verhindern, benötigen Exchange Online Protection (EoP) und Outlook.com nun eingehende Nachrichten, um eine RFC-konforme von-Adresse hinzuzufügen, wie in diesem Thema beschrieben. Diese Erzwingung wurde im November 2017 aktiviert.

**Hinweise**:

- Wenn Sie regelmäßig e-Mails von Organisationen erhalten, die wie in diesem Thema beschrieben aus Adressen falsch formatiert sind, sollten Sie diese Organisationen ermutigen, Ihre e-Mail-Server so zu aktualisieren, dass Sie den modernen Sicherheitsstandards entsprechen.

- Das zugehörige Absenderfeld (von "Senden im Auftrag" und "Mailinglisten" verwendet) ist von diesen Anforderungen nicht betroffen. Weitere Informationen finden Sie im folgenden Blogbeitrag: [Was verstehen wir, wenn wir auf den Absender einer e-Mail Bezug nehmen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Eine Übersicht über Standards für e-Mail-Nachrichten

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Zustellung der Nachricht zwischen SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in [RFC 5321](https://tools.ietf.org/html/rfc5321)beschrieben, und der Nachrichtenkopf wird in [RFC 5322](https://tools.ietf.org/html/rfc5322)beschrieben. Empfänger sehen den tatsächlichen Nachrichtenumschlag nie, da er vom Nachrichtenübertragungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.

- Die `5321.MailFrom` Adresse (auch bekannt als **Mail from** Address, P1 Sender oder Envelope Sender) ist die e-Mail-Adresse, die in der SMTP-Übertragung der Nachricht verwendet wird. Diese e-Mail-Adresse wird in der Regel im Headerfeld **Return-Path** in der Nachrichtenkopfzeile aufgezeichnet (obwohl es möglich ist, dass der Absender eine andere e-Mail-Adresse für den **Rückgabepfad** festlegt).

- Die `5322.From` (auch bekannt als von-Adresse oder P2-Absender bezeichnet) ist die e-Mail-Adresse im Feld **von** -Kopfzeile und die e-Mail-Adresse des Absenders, die in e-Mail-Clients angezeigt wird. Die from-Adresse steht im Mittelpunkt der Anforderungen in diesem Thema.

Die from-Adresse ist in mehreren RFCs detailliert definiert (beispielsweise RFC 5322 Sections 3.2.3, 3,4, and 3.4.1 und [RFC 3696](https://tools.ietf.org/html/rfc3696)). Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig erachtet wird. Um es einfach zu halten, empfehlen wir das folgende Format und die folgenden Definitionen:

`From: "Display Name" <EmailAddress>`

- **Anzeige Name**: ein optionaler Ausdruck, der den Besitzer der e-Mail-Adresse beschreibt.

  - Es wird empfohlen, den Anzeigenamen immer in doppelte Anführungszeichen (") einzuschließen (siehe Abbildung). Wenn der Anzeigename ein Komma enthält, _müssen_ Sie die Zeichenfolge in doppelte Anführungszeichen pro RFC 5322 einschließen.
  - Wenn die von-Adresse einen Anzeigenamen enthält, muss der e-Post-Wert wie dargestellt in spitzen Klammern (< >) eingeschlossen werden.
  - Microsoft empfiehlt dringend, ein Leerzeichen zwischen dem Anzeigenamen und der e-Mail-Adresse einzufügen.

- E-Mail- **Adresse: eine**e-Mail verwendet das folgende Format `local-part@domain` :

  - **local-Part**: eine Zeichenfolge, die das Postfach identifiziert, das der Adresse zugeordnet ist. Dieser Wert ist innerhalb der Domäne eindeutig. Häufig wird der Benutzername oder die GUID des Postfachbesitzers verwendet.
  - **Domäne**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des e-Mail-Servers, der das Postfach hostet, das vom lokalen Teil der e-Mail-Adresse identifiziert wird.

  Dies sind einige zusätzliche Überlegungen für den Wert der e-mailemail:

  - Nur eine e-Mail-Adresse.
  - Es wird empfohlen, die spitzen Klammern nicht mit Leerzeichen zu trennen.
  - Fügen Sie nach der e-Mail-Adresse keinen zusätzlichen Text ein.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Beispiele für gültige und ungültige Adressen

Die folgenden e-Mail-Adressen sind gültig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Nicht empfehlenswert, da zwischen den spitzen Klammern und der e-Mail-Adresse Leerzeichen vorhanden sind.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Nicht empfohlen, da der Anzeigename nicht in doppelte Anführungszeichen eingeschlossen ist.)

Die folgenden e-Mail-Adressen sind ungültig:

- **Keine Absender**Adresse: einige automatisierte Nachrichten enthalten keine Absenderadresse. Wenn Microsoft 365 oder Outlook.com in der Vergangenheit eine Nachricht ohne Absenderadresse empfangen hat, hat der Dienst den folgenden Standardwert von: Address hinzugefügt, um die Nachricht zuzustellen:

  `From: <>`

  Nachrichten mit leerer Absenderadresse werden nun nicht mehr akzeptiert.

- `From: Microsoft 365 sender@contoso.com` (Der Anzeigename ist vorhanden, aber die e-Mail-Adresse ist nicht in spitzen Klammern eingeschlossen.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text nach der e-Mail-Adresse.)

- `From: Sender, Example <sender.example@contoso.com>` (Der Anzeigename enthält ein Komma, ist jedoch nicht in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Der gesamte Wert ist falsch in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Der Anzeigename ist vorhanden, aber die e-Mail-Adresse ist nicht in spitzen Klammern eingeschlossen.)

- `From: Microsoft 365<sender@contoso.com>` (Kein Leerzeichen zwischen dem Anzeigenamen und der linken spitzen Klammer.)

- `From: "Microsoft 365"<sender@contoso.com>` (Kein Leerzeichen zwischen dem schließenden doppelten Anführungszeichen und der linken spitzen Klammer.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken

Sie können den Wert nicht verwenden `From: <>` , um automatische Antworten zu unterdrücken. Stattdessen müssen Sie einen NULL-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten. Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da keine veröffentlichte Adresse vorhanden ist, an die der antwortenden Server Nachrichten senden kann.

- Wählen Sie eine e-Mail-Domäne aus, die keine e-Mails empfangen kann. Wenn Ihre primäre Domäne beispielsweise contoso.com ist, können Sie noreply.contoso.com auswählen.

- Der NULL-MX-Eintrag für diese Domäne besteht aus einem einzelnen Zeitraum.

Beispiel:

```text
noreply.contoso.com IN MX .
```

Weitere Informationen zum Einrichten von MX-Einträgen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostanbieter für Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Weitere Informationen zum Veröffentlichen eines NULL MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Überschreiben von der Adress Erzwingung

Um die von den Adressanforderungen für eingehende e-Mails zu umgehen, können Sie die IP-Zulassungsliste (Verbindungsfilterung) oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden, wie unter [Create Safe Sender Lists in Microsoft 365](create-safe-sender-lists-in-office-365.md)beschrieben.

Sie können die von-Adresse-Anforderungen für ausgehende e-Mails, die Sie von Microsoft 365 senden, nicht außer Kraft setzen. Darüber hinaus werden von Outlook.com keine Außerkraftsetzungen jeglicher Art zugelassen, auch über die Unterstützung.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Microsoft 365

Weitere Informationen darüber, wie Sie Ihre Organisation vor Phishing, Spam, Datenschutzverletzungen und anderen Bedrohungen stärken können, finden Sie auf [den zehn besten wegen zum Sichern von Microsoft 365 for Business-Plänen](../../admin/security-and-compliance/secure-your-business-data.md).
