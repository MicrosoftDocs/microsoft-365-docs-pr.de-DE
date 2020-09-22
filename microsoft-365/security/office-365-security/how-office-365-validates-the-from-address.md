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
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196059"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="74b3b-103">Wie EoP die Absenderadresse überprüft, um Phishing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="74b3b-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="74b3b-104">Phishing-Angriffe stellen eine ständige Bedrohung für jede e-Mail-Organisation dar.</span><span class="sxs-lookup"><span data-stu-id="74b3b-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="74b3b-105">Zusätzlich zur Verwendung [gefälschter Absender-e-Mail-Adressen](anti-spoofing-protection.md)verwenden Angreifer häufig Werte in der von-Adresse, die Internetstandards verletzen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="74b3b-106">Um diese Art von Phishing zu verhindern, benötigen Exchange Online Protection (EoP) und Outlook.com nun eingehende Nachrichten, um eine RFC-konforme von-Adresse hinzuzufügen, wie in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74b3b-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="74b3b-107">Diese Erzwingung wurde im November 2017 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74b3b-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="74b3b-108">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="74b3b-108">**Notes**:</span></span>

- <span data-ttu-id="74b3b-109">Wenn Sie regelmäßig e-Mails von Organisationen erhalten, die wie in diesem Thema beschrieben aus Adressen falsch formatiert sind, sollten Sie diese Organisationen ermutigen, Ihre e-Mail-Server so zu aktualisieren, dass Sie den modernen Sicherheitsstandards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="74b3b-110">Das zugehörige Absenderfeld (von "Senden im Auftrag" und "Mailinglisten" verwendet) ist von diesen Anforderungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="74b3b-111">Weitere Informationen finden Sie im folgenden Blogbeitrag: [Was verstehen wir, wenn wir auf den Absender einer e-Mail Bezug nehmen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="74b3b-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="74b3b-112">Eine Übersicht über Standards für e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="74b3b-112">An overview of email message standards</span></span>

<span data-ttu-id="74b3b-113">Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt.</span><span class="sxs-lookup"><span data-stu-id="74b3b-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="74b3b-114">Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Zustellung der Nachricht zwischen SMTP-Servern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="74b3b-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="74b3b-115">Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext.</span><span class="sxs-lookup"><span data-stu-id="74b3b-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="74b3b-116">Der Nachrichtenumschlag wird in [RFC 5321](https://tools.ietf.org/html/rfc5321)beschrieben, und der Nachrichtenkopf wird in [RFC 5322](https://tools.ietf.org/html/rfc5322)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74b3b-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="74b3b-117">Empfänger sehen den tatsächlichen Nachrichtenumschlag nie, da er vom Nachrichtenübertragungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.</span><span class="sxs-lookup"><span data-stu-id="74b3b-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="74b3b-118">Die `5321.MailFrom` Adresse (auch bekannt als **Mail from** Address, P1 Sender oder Envelope Sender) ist die e-Mail-Adresse, die in der SMTP-Übertragung der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74b3b-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="74b3b-119">Diese e-Mail-Adresse wird in der Regel im Headerfeld **Return-Path** in der Nachrichtenkopfzeile aufgezeichnet (obwohl es möglich ist, dass der Absender eine andere e-Mail-Adresse für den **Rückgabepfad** festlegt).</span><span class="sxs-lookup"><span data-stu-id="74b3b-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="74b3b-120">Die `5322.From` (auch bekannt als von-Adresse oder P2-Absender bezeichnet) ist die e-Mail-Adresse im Feld **von** -Kopfzeile und die e-Mail-Adresse des Absenders, die in e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74b3b-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="74b3b-121">Die from-Adresse steht im Mittelpunkt der Anforderungen in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="74b3b-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="74b3b-122">Die from-Adresse ist in mehreren RFCs detailliert definiert (beispielsweise RFC 5322 Sections 3.2.3, 3,4, and 3.4.1 und [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="74b3b-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="74b3b-123">Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig erachtet wird.</span><span class="sxs-lookup"><span data-stu-id="74b3b-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="74b3b-124">Um es einfach zu halten, empfehlen wir das folgende Format und die folgenden Definitionen:</span><span class="sxs-lookup"><span data-stu-id="74b3b-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="74b3b-125">**Anzeige Name**: ein optionaler Ausdruck, der den Besitzer der e-Mail-Adresse beschreibt.</span><span class="sxs-lookup"><span data-stu-id="74b3b-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="74b3b-126">Es wird empfohlen, den Anzeigenamen immer in doppelte Anführungszeichen (") einzuschließen (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="74b3b-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="74b3b-127">Wenn der Anzeigename ein Komma enthält, _müssen_ Sie die Zeichenfolge in doppelte Anführungszeichen pro RFC 5322 einschließen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="74b3b-128">Wenn die von-Adresse einen Anzeigenamen enthält, muss der e-Post-Wert wie dargestellt in spitzen Klammern (< >) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="74b3b-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="74b3b-129">Microsoft empfiehlt dringend, ein Leerzeichen zwischen dem Anzeigenamen und der e-Mail-Adresse einzufügen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="74b3b-130">E-Mail- **Adresse: eine**e-Mail verwendet das folgende Format `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="74b3b-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="74b3b-131">**local-Part**: eine Zeichenfolge, die das Postfach identifiziert, das der Adresse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="74b3b-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="74b3b-132">Dieser Wert ist innerhalb der Domäne eindeutig.</span><span class="sxs-lookup"><span data-stu-id="74b3b-132">This value is unique within the domain.</span></span> <span data-ttu-id="74b3b-133">Häufig wird der Benutzername oder die GUID des Postfachbesitzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="74b3b-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="74b3b-134">**Domäne**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des e-Mail-Servers, der das Postfach hostet, das vom lokalen Teil der e-Mail-Adresse identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="74b3b-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="74b3b-135">Dies sind einige zusätzliche Überlegungen für den Wert der e-mailemail:</span><span class="sxs-lookup"><span data-stu-id="74b3b-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="74b3b-136">Nur eine e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="74b3b-136">Only one email address.</span></span>
  - <span data-ttu-id="74b3b-137">Es wird empfohlen, die spitzen Klammern nicht mit Leerzeichen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="74b3b-138">Fügen Sie nach der e-Mail-Adresse keinen zusätzlichen Text ein.</span><span class="sxs-lookup"><span data-stu-id="74b3b-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="74b3b-139">Beispiele für gültige und ungültige Adressen</span><span class="sxs-lookup"><span data-stu-id="74b3b-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="74b3b-140">Die folgenden e-Mail-Adressen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="74b3b-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="74b3b-141">`From: < sender@contoso.com >` (Nicht empfehlenswert, da zwischen den spitzen Klammern und der e-Mail-Adresse Leerzeichen vorhanden sind.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="74b3b-142">`From: Microsoft 365 <sender@contoso.com>` (Nicht empfohlen, da der Anzeigename nicht in doppelte Anführungszeichen eingeschlossen ist.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="74b3b-143">Die folgenden e-Mail-Adressen sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="74b3b-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="74b3b-144">**Keine Absender**Adresse: einige automatisierte Nachrichten enthalten keine Absenderadresse.</span><span class="sxs-lookup"><span data-stu-id="74b3b-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="74b3b-145">Wenn Microsoft 365 oder Outlook.com in der Vergangenheit eine Nachricht ohne Absenderadresse empfangen hat, hat der Dienst den folgenden Standardwert von: Address hinzugefügt, um die Nachricht zuzustellen:</span><span class="sxs-lookup"><span data-stu-id="74b3b-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="74b3b-146">Nachrichten mit leerer Absenderadresse werden nun nicht mehr akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="74b3b-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="74b3b-147">`From: Microsoft 365 sender@contoso.com` (Der Anzeigename ist vorhanden, aber die e-Mail-Adresse ist nicht in spitzen Klammern eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="74b3b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text nach der e-Mail-Adresse.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="74b3b-149">`From: Sender, Example <sender.example@contoso.com>` (Der Anzeigename enthält ein Komma, ist jedoch nicht in doppelte Anführungszeichen eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="74b3b-150">`From: "Microsoft 365 <sender@contoso.com>"` (Der gesamte Wert ist falsch in doppelte Anführungszeichen eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="74b3b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Der Anzeigename ist vorhanden, aber die e-Mail-Adresse ist nicht in spitzen Klammern eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="74b3b-152">`From: Microsoft 365<sender@contoso.com>` (Kein Leerzeichen zwischen dem Anzeigenamen und der linken spitzen Klammer.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="74b3b-153">`From: "Microsoft 365"<sender@contoso.com>` (Kein Leerzeichen zwischen dem schließenden doppelten Anführungszeichen und der linken spitzen Klammer.)</span><span class="sxs-lookup"><span data-stu-id="74b3b-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="74b3b-154">Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken</span><span class="sxs-lookup"><span data-stu-id="74b3b-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="74b3b-155">Sie können den Wert nicht verwenden `From: <>` , um automatische Antworten zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="74b3b-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="74b3b-156">Stattdessen müssen Sie einen NULL-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten.</span><span class="sxs-lookup"><span data-stu-id="74b3b-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="74b3b-157">Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da keine veröffentlichte Adresse vorhanden ist, an die der antwortenden Server Nachrichten senden kann.</span><span class="sxs-lookup"><span data-stu-id="74b3b-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="74b3b-158">Wählen Sie eine e-Mail-Domäne aus, die keine e-Mails empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="74b3b-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="74b3b-159">Wenn Ihre primäre Domäne beispielsweise contoso.com ist, können Sie noreply.contoso.com auswählen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="74b3b-160">Der NULL-MX-Eintrag für diese Domäne besteht aus einem einzelnen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="74b3b-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="74b3b-161">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74b3b-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="74b3b-162">Weitere Informationen zum Einrichten von MX-Einträgen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostanbieter für Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="74b3b-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="74b3b-163">Weitere Informationen zum Veröffentlichen eines NULL MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="74b3b-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="74b3b-164">Überschreiben von der Adress Erzwingung</span><span class="sxs-lookup"><span data-stu-id="74b3b-164">Override From address enforcement</span></span>

<span data-ttu-id="74b3b-165">Um die von den Adressanforderungen für eingehende e-Mails zu umgehen, können Sie die IP-Zulassungsliste (Verbindungsfilterung) oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden, wie unter [Create Safe Sender Lists in Microsoft 365](create-safe-sender-lists-in-office-365.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74b3b-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="74b3b-166">Sie können die von-Adresse-Anforderungen für ausgehende e-Mails, die Sie von Microsoft 365 senden, nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="74b3b-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="74b3b-167">Darüber hinaus werden von Outlook.com keine Außerkraftsetzungen jeglicher Art zugelassen, auch über die Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="74b3b-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="74b3b-168">Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74b3b-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="74b3b-169">Weitere Informationen darüber, wie Sie Ihre Organisation vor Phishing, Spam, Datenschutzverletzungen und anderen Bedrohungen stärken können, finden Sie auf [den zehn besten wegen zum Sichern von Microsoft 365 for Business-Plänen](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="74b3b-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
