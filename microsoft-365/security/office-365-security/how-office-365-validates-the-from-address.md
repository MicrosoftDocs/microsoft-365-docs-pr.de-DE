---
title: Vorgehensweise Office 365 Überprüfen der Absenderadresse zur Verhinderung von Phishing
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'Um Phishing zu verhindern, benötigen Office 365 und Outlook.com jetzt die RFC-Compliance für from: addresses.'
ms.openlocfilehash: 5805ca41243603ef4f58bbf39c8ddb38e5a9aa01
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871831"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Vorgehensweise Office 365 Überprüfen der Absenderadresse zur Verhinderung von Phishing

Office 365-und Outlook.com-e-Mail-Konten erhalten eine immer größere Anzahl von Phishing-Angriffen. Eine Methode, die Phisher verwendet, ist das Senden von Nachrichten mit Werten für die Absenderadresse, die nicht mit [RFC 5322](https://tools.ietf.org/html/rfc5322)kompatibel sind. Die from:-Adresse wird auch als 5322. from-Adresse bezeichnet. Um diese Art von Phishing zu verhindern, erfordern Office 365 und Outlook.com, dass Nachrichten, die vom Dienst empfangen werden, eine RFC-konforme von:-Adresse enthalten, wie in diesem Artikel beschrieben.

> [!NOTE]
> Die Informationen in diesem Artikel erfordern ein grundlegendes Verständnis des allgemeinen Formats von e-Mail-Adressen. Weitere Informationen finden Sie unter [RFC 5322](https://tools.ietf.org/html/rfc5322) (insbesondere Abschnitte 3.2.3, 3,4 und 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), sowie [RFC 3696](https://tools.ietf.org/html/rfc3696). In diesem Artikel geht es um die Richtlinienerzwingung für die 5322. from-Adresse. In diesem Artikel geht es nicht um die 5321. MailFrom-Adresse.

Leider gibt es noch einige Legacy-e-Mail-Server im Internet, die weiterhin "legitime" e-Mail-Nachrichten senden, die eine fehlende oder fehlerhafte from:-Adresse aufweisen. Wenn Sie regelmäßig e-Mails von Organisationen erhalten, die diese Legacy Systeme verwenden, ermutigen Sie diese Organisationen, Ihre e-Mail-Server so zu aktualisieren, dass Sie den modernen Sicherheitsstandards entsprechen.

Microsoft startet die Implementierung der in diesem Artikel beschriebenen Richtlinien am 9. November 2017.

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Wie Office 365 die Verwendung einer gültigen from:-Adresse zur Verhinderung von Phishing-Angriffen erzwingt

Office 365 ändert die Art und Weise, wie die Verwendung der from:-Adresse in empfangenen Nachrichten erzwungen wird, um Sie vor Phishing-Angriffen besser zu schützen. Inhalt dieses Artikels:

- [Alle Nachrichten müssen eine gültige from:-Adresse enthalten.](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [Format der from:-Adresse, wenn kein Anzeigename hinzugefügt wird](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [Format der from:-Adresse, wenn Sie einen Anzeigenamen einschließen](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [Weitere Beispiele für gültige und ungültige from:-Adressen](how-office-365-validates-the-from-address.md#Examples)

- [Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken, ohne die von:-Richtlinie zu unterbrechen](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [Überschreiben der Office 365 von: Address Enforcement Policy](how-office-365-validates-the-from-address.md#Override)

- [Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Office 365](how-office-365-validates-the-from-address.md#OtherProtection)

Das Senden im Auftrag eines anderen Benutzers ist von dieser Änderung nicht betroffen, weitere Informationen finden Sie unter Terry Zinks Blog "[Was verstehen wir, wenn wir auf den Absender einer e-Mail" Bezug nehmen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".

### <a name="all-messages-must-include-a-valid-from-address"></a>Alle Nachrichten müssen eine gültige from:-Adresse enthalten.
<a name="MustIncludeFromAddress"> </a>

Einige automatisierte Nachrichten enthalten keine from:-Adresse, wenn Sie gesendet werden. Wenn Office 365 oder Outlook.com in der Vergangenheit eine Nachricht ohne eine from:-Adresse empfangen hat, hat der Dienst die folgende Standardeinstellung von: address zur Nachricht hinzugefügt, um die Zustellung zu ermöglichen:

```
From: <>
```

Ab dem 9. November 2017 werden Office 365 Änderungen an den Rechenzentren und e-Mail-Servern durchführen, wodurch eine neue Regel erzwungen wird, bei der Nachrichten ohne Absenderadresse nicht mehr von Office 365 oder Outlook.com akzeptiert werden. Stattdessen müssen alle von Office 365 empfangenen Nachrichten bereits eine gültige from:-Adresse enthalten. Andernfalls wird die Nachricht entweder an die Ordner "Junk-e-Mail" oder "Gelöschte Elemente" in Outlook.com und Office 365 gesendet.

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Syntax Übersicht: gültiges Format für die from:-Adresse für Office 365
<a name="SyntaxOverviewFromAddress"> </a>

Das Format für den Wert der from:-Adresse wird über mehrere RFCs hinweg detailliert definiert. Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig angesehen werden kann. Um es einfach zu halten, empfiehlt Microsoft, dass Sie das folgende Format und die folgenden Definitionen verwenden:

```
From: "displayname " <emailaddress >
```

Dabei gilt:

- Optional  *DisplayName* ist ein Ausdruck, der den Besitzer der e-Mail-Adresse beschreibt. Dies kann beispielsweise ein benutzerfreundlicherer Name sein, um den Absender als den Namen des Postfachs zu beschreiben. Die Verwendung eines Anzeigenamens ist optional. Wenn Sie jedoch einen Anzeigenamen verwenden, empfiehlt Microsoft, dass Sie ihn immer in Anführungszeichen einschließen, wie in der Abbildung dargestellt.

- Erforderlich  die e- *Email* -e-mailbesteht aus:

  ```
  local-part @domain
  ```

    Dabei gilt:

  - Erforderlich  *local-Part* ist eine Zeichenfolge, die das Postfach identifiziert, das der Adresse zugeordnet ist. Dies ist innerhalb der Domäne eindeutig. Der Benutzername oder die GUID des Postfachbesitzers wird häufig als Wert für das lokale Webpart verwendet.

  - Erforderlich  *Domain* ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des e-Mail-Servers, der das Postfach hostet, das vom lokalen Teil der e-Mail-Adresse identifiziert wird.

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Format der from:-Adresse, wenn kein Anzeigename hinzugefügt wird
<a name="FormatNoDisplayName"> </a>

Eine ordnungsgemäß formatierte from:-Adresse, die keinen Anzeigenamen enthält, umfasst nur eine einzelne e-Mail-Adresse mit oder ohne spitzen Klammern. Microsoft empfiehlt, die spitzen Klammern nicht mit Leerzeichen zu trennen. Fügen Sie außerdem nichts nach der e-Mail-Adresse hinzu.

Die folgenden Beispiele sind gültig:

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

Das folgende Beispiel ist gültig, wird jedoch nicht empfohlen, da es Leerzeichen zwischen den spitzen Klammern und der e-Mail-Adresse enthält:

```
From: < sender@contoso.com >
```

Das folgende Beispiel ist ungültig, da es Text nach der e-Mail-Adresse enthält:

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Format der from:-Adresse, wenn Sie einen Anzeigenamen einschließen
<a name="FormatDisplayName"> </a>

Für from: addresses, die einen Wert für den Anzeigenamen enthalten, gelten die folgenden Regeln:

- Wenn die Absenderadresse einen Anzeigenamen enthält und der Anzeigename ein Komma enthält, muss der Anzeigename in Anführungszeichen eingeschlossen werden. Zum Beispiel:

    Das folgende Beispiel ist gültig:

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    Das folgende Beispiel ist ungültig:

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    Der Anzeigename wird nicht in Anführungszeichen gesetzt, wenn dieser Anzeigename ein Komma enthält, ist gemäß RFC 5322 ungültig.

    Es empfiehlt sich, Anführungszeichen um den Anzeigenamen zu setzen, unabhängig davon, ob ein Komma innerhalb des Anzeigenamens vorhanden ist oder nicht.

- Wenn die Absenderadresse einen Anzeigenamen enthält, muss die e-Mail-Adresse in spitzen Klammern eingeschlossen werden.

    Als bewährte Methode empfiehlt Microsoft dringend, ein Leerzeichen zwischen dem Anzeigenamen und der e-Mail-Adresse einzufügen.

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Weitere Beispiele für gültige und ungültige from:-Adressen
<a name="Examples"> </a>

- Gültig

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Ungültig Die e-Mail-Adresse ist nicht mit spitzen Klammern eingeschlossen:

  ```
  From: Office 365 sender@contoso.com
  ```

- Gültig, wird jedoch nicht empfohlen. Der Anzeigename ist nicht in Anführungszeichen gesetzt. Als bewährte Methode sollten Sie immer Anführungszeichen um den Anzeigenamen herum setzen:

  ```
  From: Office 365 <sender@contoso.com>
  ```

- Ungültig Alles ist in Anführungszeichen eingeschlossen, nicht nur der Anzeigename:

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Ungültig Es gibt keine spitzen Klammern um die e-Mail-Adresse:

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Ungültig Zwischen dem Anzeigenamen und der linken spitzen Klammer ist kein Leerzeichen vorhanden:

  ```
  From: Office 365<sender@contoso.com>
  ```

- Ungültig Zwischen dem schließenden Anführungszeichen um den Anzeigenamen und der linken spitzen Klammer ist kein Leerzeichen.

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken, ohne die von:-Richtlinie zu unterbrechen
<a name="SuppressAutoReply"> </a>

Mit dem neuen Absender: Richtlinienerzwingung können Sie von: \< \> nicht mehr verwenden, um automatische Antworten zu unterdrücken. Stattdessen müssen Sie einen NULL-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten.

Der MX-Eintrag (Mail Exchanger) ist ein Ressourceneintrag in DNS, der den e-Mail-Server identifiziert, der e-Mails für Ihre Domäne empfängt. Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da keine veröffentlichte Adresse vorhanden ist, an die der antwortenden Server Nachrichten senden kann.

Wenn Sie einen NULL MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten:

- Wählen Sie eine Domäne aus, von der Nachrichten gesendet werden sollen, die keine e-Mails annehmen (empfangen). Wenn Ihre primäre Domäne beispielsweise contoso.com ist, können Sie noreply.contoso.com auswählen.

- Richten Sie den NULL-MX-Eintrag für Ihre Domäne ein. Ein NULL-MX-Eintrag besteht aus einem einzelnen Punkt, beispielsweise:

  ```
  noreply.contoso.com IN MX .
  ```

Weitere Informationen zum Veröffentlichen eines NULL MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Überschreiben der Office 365 von: Address Enforcement Policy
<a name="Override"> </a>

Wenn die Bereitstellung der neuen Richtlinie abgeschlossen ist, können Sie diese Richtlinie nur für eingehende e-Mails umgehen, die Sie von Office 365 erhalten, indem Sie eine der folgenden Methoden verwenden:

- IP-Zulassungslisten

- Exchange Online von Nachrichtenfluss Regeln

Microsoft empfiehlt dringend, die Erzwingung der from:-Richtlinie außer Kraft zu setzen. Durch das außer Kraft setzen dieser Richtlinie können Sie das Risiko Ihrer Organisation für Spam, Phishing und andere Internetkriminalität verbessern.

Sie können diese Richtlinie nicht für ausgehende e-Mails außer Kraft setzen, die Sie in Office 365 senden. Darüber hinaus werden von Outlook.com keine Außerkraftsetzungen jeglicher Art zugelassen, auch über die Unterstützung.

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Office 365
<a name="OtherProtection"> </a>

Weitere Informationen darüber, wie Sie Ihre Organisation gegen Internetkriminalität wie Phishing, Spam, Datenschutzverletzungen und andere Bedrohungen stärken können, finden Sie unter [bewährte Methoden für die Sicherheit für Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).

## <a name="related-topics"></a>Verwandte Themen

[Rückläufernachrichten und EOP](backscatter-messages-and-eop.md)
