---
title: So überprüft EOP die Von-Adresse, um Phishing zu verhindern
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
description: Administratoren können sich über die Typen von E-Mail-Adressen informieren, die von Exchange Online Protection (EOP) und Outlook.com akzeptiert oder abgelehnt werden, um Phishing zu verhindern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204185"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>So überprüft EOP die Von-Adresse, um Phishing zu verhindern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Phishingangriffe sind eine ständige Bedrohung für jede E-Mail-Organisation. Zusätzlich zur Verwendung [gefälschter (gefälschter)](anti-spoofing-protection.md)Absender-E-Mail-Adressen verwenden Angreifer häufig Werte in der Absenderadresse, die gegen Internetstandards verstoßen. Um diese Art von Phishing zu verhindern, benötigen Exchange Online Protection (EOP) und Outlook.com jetzt eingehende Nachrichten, um eine RFC-kompatible From-Adresse wie in diesem Artikel beschrieben zu enthalten. Diese Erzwingung wurde im November 2017 aktiviert.

**Hinweise**:

- Wenn Sie regelmäßig E-Mails von Organisationen erhalten, die eine falsch formatierte From-Adresse erhalten, wie in diesem Artikel beschrieben, ermutigen Sie diese Organisationen, ihre E-Mail-Server so zu aktualisieren, dass sie modernen Sicherheitsstandards entsprechen.

- Das zugehörige Feld "Sender" (wird von "Senden im Auftrag" und "Mailinglisten") wird von diesen Anforderungen nicht beeinflusst. Weitere Informationen finden Sie im folgenden Blogbeitrag: Was meinen wir, wenn wir auf den ["Absender" einer E-Mail verweisen?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).

## <a name="an-overview-of-email-message-standards"></a>Eine Übersicht über E-Mail-Nachrichtenstandards

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übertragung und Übermittlung der Nachricht zwischen SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in [RFC 5321](https://tools.ietf.org/html/rfc5321)beschrieben, und der Nachrichtenheader wird in [RFC 5322 beschrieben.](https://tools.ietf.org/html/rfc5322) Empfänger sehen nie den tatsächlichen Nachrichtenumschlag, da er durch den Nachrichtenübermittlungsprozess generiert wird und nicht teil der Nachricht ist.

- Die Adresse (auch bekannt `5321.MailFrom` als MAIL **FROM-Adresse,** P1-Absender oder Umschlagsender) ist die E-Mail-Adresse, die bei der SMTP-Übertragung der Nachricht verwendet wird. Diese **E-Mail-Adresse** wird in der Regel im Kopfzeilenfeld Return-Path im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Return-Path-E-Mail-Adresse** festlegen kann).

- The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients. Die From-Adresse steht im Mittelpunkt der Anforderungen in diesem Artikel.

Die From-Adresse wird in mehreren RFCs (z. B. RFC 5322-Abschnitte 3.2.3, 3.4 und 3.4.1 und [RFC 3696](https://tools.ietf.org/html/rfc3696)) detailliert definiert. Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig betrachtet wird. Um dies einfach zu halten, wird das folgende Format und die folgenden Definitionen empfohlen:

`From: "Display Name" <EmailAddress>`

- **Anzeigename**: Ein optionaler Ausdruck, der den Besitzer der E-Mail-Adresse beschreibt.

  - Es wird empfohlen, den Anzeigenamen wie dargestellt immer in doppelte Anführungszeichen (") zu setzen. Wenn der Anzeigename ein Komma enthält, _müssen_ Sie die Zeichenfolge in doppelte Anführungszeichen pro RFC 5322 setzen.
  - Wenn die From-Adresse einen Anzeigenamen enthält, muss der EmailAddress-Wert wie gezeigt in eckige Klammern (< >) eingeschlossen werden.
  - Microsoft empfiehlt dringend, ein Leerzeichen zwischen dem Anzeigenamen und der E-Mail-Adresse zu setzen.

- **EmailAddress**: Eine E-Mail-Adresse verwendet das Format `local-part@domain` :

  - **local-part**: Eine Zeichenfolge, die das postfach identifiziert, das der Adresse zugeordnet ist. Dieser Wert ist innerhalb der Domäne eindeutig. Häufig wird der Benutzername oder die GUID des Postfachbesitzers verwendet.
  - **domäne**: Der vollqualifizierte Domänenname (FQDN) des E-Mail-Servers, der das postfach hostet, das durch den lokalen Teil der E-Mail-Adresse identifiziert wird.

  Dies sind einige zusätzliche Überlegungen für den EmailAddress-Wert:

  - Nur eine E-Mail-Adresse.
  - Es wird empfohlen, die eckigen Klammern nicht durch Leerzeichen zu trennen.
  - Fügen Sie nach der E-Mail-Adresse keinen zusätzlichen Text hinzu.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Beispiele für gültige und ungültige From-Adressen

Die folgenden From-E-Mail-Adressen sind gültig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Nicht empfohlen, da zwischen den eckigen Klammern und der E-Mail-Adresse Leerzeichen enthalten sind.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Wird nicht empfohlen, da der Anzeigename nicht in doppelte Anführungszeichen eingeschlossen ist.)

Die folgenden From-E-Mail-Adressen sind ungültig:

- **No From address**: Einige automatisierte Nachrichten enthalten keine From-Adresse. In der Vergangenheit, wenn Microsoft 365 oder Outlook.com eine Nachricht ohne Eine Von-Adresse empfangen hat, hat der Dienst die folgende Standardmäßige Von: Adresse hinzugefügt, um die Nachricht zu liefern:

  `From: <>`

  Jetzt werden Nachrichten mit einer leeren Von-Adresse nicht mehr akzeptiert.

- `From: Microsoft 365 sender@contoso.com` (Der Anzeigename ist vorhanden, die E-Mail-Adresse ist jedoch nicht in eckige Klammern eingeschlossen.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text hinter der E-Mail-Adresse.)

- `From: Sender, Example <sender.example@contoso.com>` (Der Anzeigename enthält ein Komma, ist jedoch nicht in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Der gesamte Wert ist fälschlicherweise in doppelte Anführungszeichen eingeschlossen.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Der Anzeigename ist vorhanden, die E-Mail-Adresse ist jedoch nicht in eckige Klammern eingeschlossen.)

- `From: Microsoft 365<sender@contoso.com>` (Kein Abstand zwischen dem Anzeigenamen und der linken eckigen Klammer.)

- `From: "Microsoft 365"<sender@contoso.com>` (Kein Abstand zwischen dem schließenden doppelten Anführungszeichen und der linken winkeligen Klammer.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken

Sie können den Wert nicht verwenden, `From: <>` um automatische Antworten zu unterdrücken. Stattdessen müssen Sie einen Null-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten. Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da es keine veröffentlichte Adresse gibt, an die der antwortende Server Nachrichten senden kann.

- Wählen Sie eine E-Mail-Domäne aus, die keine E-Mails empfangen kann. Wenn Ihre primäre Domäne z. B. contoso.com ist, können Sie noreply.contoso.com.

- Der Null-MX-Eintrag für diese Domäne besteht aus einem einzelnen Zeitraum.

Beispiel:

```text
noreply.contoso.com IN MX .
```

Weitere Informationen zum Einrichten von MX-Einträgen finden Sie unter [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Weitere Informationen zum Veröffentlichen eines Null-MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Außerkraftsetzung von der Adressersetzung

Um die Anforderungen von Adressanforderungen für eingehende E-Mails zu umgehen, können Sie die IP-Zulässige Liste (Verbindungsfilterung) oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, wie unter Erstellen von Listen sicherer Absender [in Microsoft 365](create-safe-sender-lists-in-office-365.md).

Sie können die Von-Adressanforderungen für ausgehende E-Mails, die Sie von einem E-Mail-Microsoft 365. Darüber hinaus Outlook.com keine Außerkraftsetzungen jeglicher Art zulassen, auch nicht über die Unterstützung.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere Möglichkeiten zum Verhindern und Schutz vor Cyberkriminellen in Microsoft 365

Weitere Informationen dazu, wie Sie Ihre Organisation gegen Phishing, Spam, Datenschutzverletzungen und andere Bedrohungen stärken können, finden Sie unter [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).