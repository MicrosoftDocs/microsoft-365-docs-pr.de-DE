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
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167515"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="cdc42-103">So überprüft EOP die "Von"-Adresse, um Phishing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="cdc42-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cdc42-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="cdc42-104">**Applies to**</span></span>
- [<span data-ttu-id="cdc42-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cdc42-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="cdc42-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="cdc42-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="cdc42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdc42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cdc42-108">Phishingangriffe sind eine konstante Bedrohung für jede E-Mail-Organisation.</span><span class="sxs-lookup"><span data-stu-id="cdc42-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="cdc42-109">Zusätzlich zur Verwendung gefälschter [(gefälschter)](anti-spoofing-protection.md)Absender-E-Mail-Adressen verwenden Angreifer häufig Werte in der Absenderadresse, die gegen Internetstandards verstoßen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="cdc42-110">Um diese Art von Phishing zu verhindern, erfordern Exchange Online Protection (EOP) und Outlook.com jetzt, dass eingehende Nachrichten eine RFC-kompatible "From"-Adresse enthalten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cdc42-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="cdc42-111">Diese Erzwingung wurde im November 2017 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cdc42-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="cdc42-112">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="cdc42-112">**Notes**:</span></span>

- <span data-ttu-id="cdc42-113">Wenn Sie regelmäßig E-Mails von Organisationen erhalten, die falsch formatierte "Von"-Adressen haben, wie in diesem Artikel beschrieben, sollten Sie diese Organisationen ermutigen, ihre E-Mail-Server zu aktualisieren, um moderne Sicherheitsstandards einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="cdc42-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="cdc42-114">Das zugehörige Feld "Absender" (verwendet von "Senden im Auftrag von" und "Mailinglisten") ist von diesen Anforderungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="cdc42-115">Weitere Informationen finden Sie im folgenden Blogbeitrag: Was meinen wir, wenn wir auf den ["Absender" einer E-Mail verweisen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="cdc42-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="cdc42-116">Übersicht über E-Mail-Nachrichtenstandards</span><span class="sxs-lookup"><span data-stu-id="cdc42-116">An overview of email message standards</span></span>

<span data-ttu-id="cdc42-117">Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt.</span><span class="sxs-lookup"><span data-stu-id="cdc42-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="cdc42-118">Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Übermittlung der Nachricht zwischen den SMTP-Servern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cdc42-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="cdc42-119">Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext.</span><span class="sxs-lookup"><span data-stu-id="cdc42-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="cdc42-120">Der Nachrichtenumschlag wird in [RFC 5321](https://tools.ietf.org/html/rfc5321)beschrieben, und der Nachrichtenkopf wird in [RFC 5322 beschrieben.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="cdc42-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="cdc42-121">Empfänger sehen den tatsächlichen Nachrichtenumschlag nie, da er vom Nachrichtenübermittlungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.</span><span class="sxs-lookup"><span data-stu-id="cdc42-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="cdc42-122">Die Adresse (auch als `5321.MailFrom` MAIL **FROM-Adresse,** Absender von E-Mails oder Umschlagsender bezeichnet) ist die E-Mail-Adresse, die bei der SMTP-Übermittlung der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cdc42-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="cdc42-123">Diese **E-Mail-Adresse** wird in der Regel im Kopfzeilenfeld "Return-Path" im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Absender-E-Mail-Adresse** festlegen kann).</span><span class="sxs-lookup"><span data-stu-id="cdc42-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="cdc42-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span><span class="sxs-lookup"><span data-stu-id="cdc42-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="cdc42-125">Die "Von"-Adresse ist der Schwerpunkt der Anforderungen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="cdc42-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="cdc42-126">Die "From"-Adresse wird in mehreren RFCs (z. B. RFC 5322, Abschnitte 3.2.3, 3.4 und 3.4.1 und [RFC 3696)](https://tools.ietf.org/html/rfc3696)ausführlich definiert.</span><span class="sxs-lookup"><span data-stu-id="cdc42-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="cdc42-127">Es gibt viele Variationen zur Adressierung und was als gültig oder ungültig betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="cdc42-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="cdc42-128">Um dies einfach zu halten, empfehlen wir das folgende Format und die folgenden Definitionen:</span><span class="sxs-lookup"><span data-stu-id="cdc42-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="cdc42-129">**Anzeigename:** Ein optionaler Ausdruck, der den Besitzer der E-Mail-Adresse beschreibt.</span><span class="sxs-lookup"><span data-stu-id="cdc42-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="cdc42-130">Es wird empfohlen, den Anzeigenamen wie dargestellt immer in doppelte Anführungszeichen (") zu setzen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="cdc42-131">Wenn der Anzeigename ein Komma enthält, müssen Sie die Zeichenfolge in doppelte Anführungszeichen nach RFC 5322 setzen. </span><span class="sxs-lookup"><span data-stu-id="cdc42-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="cdc42-132">Wenn die "Von"-Adresse einen Anzeigenamen enthält, muss der Wert "EmailAddress" in spitze Klammern (< >) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cdc42-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="cdc42-133">Microsoft empfiehlt dringend, dass Sie ein Leerzeichen zwischen dem Anzeigenamen und der E-Mail-Adresse einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="cdc42-134">**EmailAddress**: Eine E-Mail-Adresse verwendet das Format `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="cdc42-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="cdc42-135">**local-part**: Eine Zeichenfolge, die das postfach identifiziert, das der Adresse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cdc42-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="cdc42-136">Dieser Wert ist innerhalb der Domäne eindeutig.</span><span class="sxs-lookup"><span data-stu-id="cdc42-136">This value is unique within the domain.</span></span> <span data-ttu-id="cdc42-137">Häufig wird der Benutzername oder die GUID des Postfachbesitzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="cdc42-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="cdc42-138">**domäne:** Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des E-Mail-Servers, der das Postfach hostet, das durch den lokalen Teil der E-Mail-Adresse identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="cdc42-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="cdc42-139">Dies sind einige zusätzliche Überlegungen für den Wert "EmailAddress":</span><span class="sxs-lookup"><span data-stu-id="cdc42-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="cdc42-140">Nur eine E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="cdc42-140">Only one email address.</span></span>
  - <span data-ttu-id="cdc42-141">Es wird empfohlen, die spitzen Klammern nicht durch Leerzeichen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="cdc42-142">Fügen Sie nach der E-Mail-Adresse keinen zusätzlichen Text ein.</span><span class="sxs-lookup"><span data-stu-id="cdc42-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="cdc42-143">Beispiele für gültige und ungültige "From"-Adressen</span><span class="sxs-lookup"><span data-stu-id="cdc42-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="cdc42-144">Die folgenden "Von"-E-Mail-Adressen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cdc42-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="cdc42-145">`From: < sender@contoso.com >` (Nicht empfohlen, da es Leerzeichen zwischen den spitzen Klammern und der E-Mail-Adresse gibt.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="cdc42-146">`From: Microsoft 365 <sender@contoso.com>` (Nicht empfohlen, da der Anzeigename nicht in doppelte Anführungszeichen eingeschlossen ist.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="cdc42-147">Die folgenden "Von"-E-Mail-Adressen sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="cdc42-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="cdc42-148">**No From address:** Some automated messages don't include a From address.</span><span class="sxs-lookup"><span data-stu-id="cdc42-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="cdc42-149">In der Vergangenheit, als Microsoft 365 oder Outlook.com eine Nachricht ohne "Von"-Adresse empfangen hat, hat der Dienst die folgende standardmäßige "Von:"-Adresse hinzugefügt, damit die Nachricht zugestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="cdc42-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="cdc42-150">Jetzt werden Nachrichten mit einer leeren "Von"-Adresse nicht mehr akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="cdc42-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="cdc42-151">`From: Microsoft 365 sender@contoso.com` (Der Anzeigename ist vorhanden, aber die E-Mail-Adresse ist nicht in spitze Klammern eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="cdc42-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text hinter der E-Mail-Adresse.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="cdc42-153">`From: Sender, Example <sender.example@contoso.com>` (Der Anzeigename enthält ein Komma, ist jedoch nicht in doppelte Anführungszeichen eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="cdc42-154">`From: "Microsoft 365 <sender@contoso.com>"` (Der gesamte Wert ist fälschlicherweise in doppelte Anführungszeichen eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="cdc42-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Der Anzeigename ist vorhanden, aber die E-Mail-Adresse ist nicht in spitze Klammern eingeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="cdc42-156">`From: Microsoft 365<sender@contoso.com>` (Kein Leerzeichen zwischen dem Anzeigenamen und der linken spitzen Klammer.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="cdc42-157">`From: "Microsoft 365"<sender@contoso.com>` (Kein Abstand zwischen dem schließenden doppelten Anführungszeichen und der linken spitzen Klammer.)</span><span class="sxs-lookup"><span data-stu-id="cdc42-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="cdc42-158">Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken</span><span class="sxs-lookup"><span data-stu-id="cdc42-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="cdc42-159">Sie können den Wert nicht verwenden, `From: <>` um automatische Antworten zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cdc42-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="cdc42-160">Stattdessen müssen Sie einen Null-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten.</span><span class="sxs-lookup"><span data-stu-id="cdc42-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="cdc42-161">Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da es keine veröffentlichte Adresse gibt, an die der reagierende Server Nachrichten senden kann.</span><span class="sxs-lookup"><span data-stu-id="cdc42-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="cdc42-162">Wählen Sie eine E-Mail-Domäne aus, die keine E-Mails empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="cdc42-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="cdc42-163">Wenn Ihre primäre Domäne z. B. contoso.com ist, können Sie noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cdc42-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="cdc42-164">Der Null-MX-Eintrag für diese Domäne besteht aus einem einzelnen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="cdc42-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="cdc42-165">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cdc42-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="cdc42-166">Weitere Informationen zum Einrichten von MX-Einträgen finden Sie unter Erstellen von [DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="cdc42-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="cdc42-167">Weitere Informationen zum Veröffentlichen eines NULL-MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="cdc42-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="cdc42-168">Außerkraftsetzung von Adressersetzung</span><span class="sxs-lookup"><span data-stu-id="cdc42-168">Override From address enforcement</span></span>

<span data-ttu-id="cdc42-169">Um die Anforderungen der Absenderadresse für eingehende E-Mails zu umgehen, können Sie die IP-Allow List (Verbindungsfilterung) oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, wie unter Erstellen von Listen sicherer Absender [in Microsoft 365](create-safe-sender-lists-in-office-365.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cdc42-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="cdc42-170">Sie können die Von-Adressanforderungen für ausgehende E-Mails, die Sie von Microsoft 365 senden, nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="cdc42-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="cdc42-171">Darüber hinaus lässt Outlook.com keine Außerkraftsetzungen beliebiger Art zu, auch nicht über die Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="cdc42-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="cdc42-172">Andere Möglichkeiten zum Verhindern und Schutz vor Cyberkriminalität in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cdc42-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="cdc42-173">Weitere Informationen dazu, wie Sie Ihre Organisation gegen Phishing, Spam, Datenschutzverletzungen und andere Bedrohungen stärken können, finden Sie unter den 10 besten Methoden zum Sichern von [Microsoft 365 Business-Plänen.](../../admin/security-and-compliance/secure-your-business-data.md)</span><span class="sxs-lookup"><span data-stu-id="cdc42-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
