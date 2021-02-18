---
title: So überprüft EOP die "Von"-Adresse, um Phishing zu verhindern
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die Typen von E-Mail-Adressen informieren, die von Exchange Online Protection (EOP) und EOP akzeptiert oder abgelehnt werden, Outlook.com, um Phishing zu verhindern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ced200c2e521533c1dec8a9d0917add7ca058f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287819"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>So überprüft EOP die "Von"-Adresse, um Phishing zu verhindern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Phishingangriffe sind eine konstante Bedrohung für jede E-Mail-Organisation. Zusätzlich zur Verwendung gefälschter [(gefälschter)](anti-spoofing-protection.md)Absender-E-Mail-Adressen verwenden Angreifer häufig Werte in der Absenderadresse, die gegen Internetstandards verstoßen. Um diese Art von Phishing zu verhindern, erfordern Exchange Online Protection (EOP) und Outlook.com jetzt, dass eingehende Nachrichten eine RFC-kompatible "From"-Adresse enthalten, wie in diesem Artikel beschrieben. Diese Erzwingung wurde im November 2017 aktiviert.

**Hinweise**:

- Wenn Sie regelmäßig E-Mails von Organisationen erhalten, die falsch formatierte "Von"-Adressen haben, wie in diesem Artikel beschrieben, sollten Sie diese Organisationen ermutigen, ihre E-Mail-Server so zu aktualisieren, dass sie modernen Sicherheitsstandards entsprechen.

- Das zugehörige Feld "Absender" (verwendet von "Senden im Auftrag von" und "Mailinglisten") ist von diesen Anforderungen nicht betroffen. Weitere Informationen finden Sie im folgenden Blogbeitrag: Was meinen wir, wenn wir auf den ["Absender" einer E-Mail verweisen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)

## <a name="an-overview-of-email-message-standards"></a>Übersicht über E-Mail-Nachrichtenstandards

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Übermittlung der Nachricht zwischen den SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in [RFC 5321](https://tools.ietf.org/html/rfc5321)beschrieben, und der Nachrichtenkopf wird in [RFC 5322 beschrieben.](https://tools.ietf.org/html/rfc5322) Empfänger sehen den tatsächlichen Nachrichtenumschlag nie, da er vom Nachrichtenübermittlungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.

- Die Adresse (auch als `5321.MailFrom` MAIL **FROM-Adresse,** Absender von E-Mails oder Umschlagsender bezeichnet) ist die E-Mail-Adresse, die bei der SMTP-Übermittlung der Nachricht verwendet wird. Diese E-Mail-Adresse wird in der Regel im Kopfzeilenfeld **"Return-Path"** im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Absender-E-Mail-Adresse** festlegen kann).

- The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients. Die "Von"-Adresse ist der Schwerpunkt der Anforderungen in diesem Artikel.

Die "From"-Adresse wird in mehreren RFCs (z. B. RFC 5322, Abschnitte 3.2.3, 3.4 und 3.4.1 und [RFC 3696)](https://tools.ietf.org/html/rfc3696)ausführlich definiert. Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig betrachtet wird. Um dies einfach zu halten, empfehlen wir das folgende Format und die folgenden Definitionen:

`From: "Display Name" <EmailAddress>`

- **Anzeigename:** Ein optionaler Ausdruck, der den Besitzer der E-Mail-Adresse beschreibt.

  - Es wird empfohlen, den Anzeigenamen wie dargestellt immer in doppelte Anführungszeichen (") zu setzen. Wenn der Anzeigename ein Komma enthält, _müssen_ Sie die Zeichenfolge in doppelte Anführungszeichen nach RFC 5322 setzen.
  - Wenn die "Von"-Adresse einen Anzeigenamen enthält, muss der Wert "EmailAddress" wie dargestellt in spitze klammern (< >) eingeschlossen werden.
  - Microsoft empfiehlt dringend, dass Sie ein Leerzeichen zwischen dem Anzeigenamen und der E-Mail-Adresse einfügen.

- **EmailAddress**: Eine E-Mail-Adresse verwendet das Format `local-part@domain` :

  - **local-part**: Eine Zeichenfolge, die das postfach identifiziert, das der Adresse zugeordnet ist. Dieser Wert ist innerhalb der Domäne eindeutig. Häufig wird der Benutzername oder die GUID des Postfachbesitzers verwendet.
  - **domäne:** Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des E-Mail-Servers, der das Postfach hostet, das durch den lokalen Teil der E-Mail-Adresse identifiziert wird.

  Dies sind einige zusätzliche Überlegungen für den Wert "EmailAddress":

  - Nur eine E-Mail-Adresse.
  - Es wird empfohlen, die spitzen Klammern nicht durch Leerzeichen zu trennen.
  - Fügen Sie nach der E-Mail-Adresse keinen zusätzlichen Text ein.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Beispiele für gültige und ungültige "From"-Adressen

Die folgenden "Von"-E-Mail-Adressen sind gültig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Nicht empfohlen, da es Leerzeichen zwischen den spitzen Klammern und der E-Mail-Adresse gibt.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Nicht empfohlen, da der Anzeigename nicht in doppelte Anführungszeichen eingeschlossen ist.)

Die folgenden "Von"-E-Mail-Adressen sind ungültig:

- **No From address:** Some automated messages don't include a From address. In der Vergangenheit, als Microsoft 365 oder Outlook.com eine Nachricht ohne "Von"-Adresse empfangen hat, hat der Dienst die folgende standardmäßige "Von:"-Adresse hinzugefügt, um die Nachricht zu liefern:

  `From: <>`

  Jetzt werden Nachrichten mit einer leeren "Von"-Adresse nicht mehr akzeptiert.

- `From: Microsoft 365 sender@contoso.com` (Der Anzeigename ist vorhanden, aber die E-Mail-Adresse ist nicht in spitze Klammern eingeschlossen.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text hinter der E-Mail-Adresse.)

- `From: Sender, Example <sender.example@contoso.com>` (Der Anzeigename enthält ein Komma, ist jedoch nicht in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Der gesamte Wert ist fälschlicherweise in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Der Anzeigename ist vorhanden, aber die E-Mail-Adresse ist nicht in spitze Klammern eingeschlossen.)

- `From: Microsoft 365<sender@contoso.com>` (Kein Leerzeichen zwischen dem Anzeigenamen und der linken spitzen Klammer.)

- `From: "Microsoft 365"<sender@contoso.com>` (Kein Abstand zwischen dem schließenden doppelten Anführungszeichen und der linken spitzen Klammer.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken

Sie können den Wert nicht verwenden, `From: <>` um automatische Antworten zu unterdrücken. Stattdessen müssen Sie einen Null-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten. Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da es keine veröffentlichte Adresse gibt, an die der reagierende Server Nachrichten senden kann.

- Wählen Sie eine E-Mail-Domäne aus, die keine E-Mails empfangen kann. Wenn Ihre primäre Domäne z. B. contoso.com ist, können Sie noreply.contoso.com.

- Der Null-MX-Eintrag für diese Domäne besteht aus einem einzelnen Zeitraum.

Zum Beispiel:

```text
noreply.contoso.com IN MX .
```

Weitere Informationen zum Einrichten von MX-Einträgen finden Sie unter Erstellen von [DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

Weitere Informationen zum Veröffentlichen eines NULL-MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Außerkraftsetzung von Adressersetzung

Um die Anforderungen der Absenderadresse für eingehende E-Mails zu umgehen, können Sie die IP-Allow List (Verbindungsfilterung) oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, wie unter Erstellen von Listen sicherer Absender [in Microsoft 365](create-safe-sender-lists-in-office-365.md)beschrieben.

Sie können die Von-Adressanforderungen für ausgehende E-Mails, die Sie von Microsoft 365 senden, nicht außer Kraft setzen. Darüber hinaus lässt Outlook.com keine Außerkraftsetzungen beliebiger Art zu, auch nicht durch Unterstützung.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere Möglichkeiten zum Verhindern und Schutz vor Cyberkriminalität in Microsoft 365

Weitere Informationen dazu, wie Sie Ihre Organisation gegen Phishing, Spam, Datenschutzverletzungen und andere Bedrohungen stärken können, finden Sie unter den 10 besten Methoden zum Sichern von [Microsoft 365 Business-Plänen.](../../admin/security-and-compliance/secure-your-business-data.md)
