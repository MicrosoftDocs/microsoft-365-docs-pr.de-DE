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
ms.openlocfilehash: ca3ec0ca6e9a2267c84549f26498b46479f74401
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032350"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="9bd0b-103">Vorgehensweise Office 365 Überprüfen der Absenderadresse zur Verhinderung von Phishing</span><span class="sxs-lookup"><span data-stu-id="9bd0b-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="9bd0b-104">Office 365-und Outlook.com-e-Mail-Konten erhalten eine immer größere Anzahl von Phishing-Angriffen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="9bd0b-105">Eine Methode, die Phisher verwendet, ist das Senden von Nachrichten mit Werten für die Absenderadresse, die nicht mit [RFC 5322](https://tools.ietf.org/html/rfc5322)kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="9bd0b-106">Die from:-Adresse wird auch als 5322. from-Adresse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="9bd0b-107">Um diese Art von Phishing zu verhindern, erfordern Office 365 und Outlook.com, dass Nachrichten, die vom Dienst empfangen werden, eine RFC-konforme von:-Adresse enthalten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9bd0b-108">Die Informationen in diesem Artikel erfordern ein grundlegendes Verständnis des allgemeinen Formats von e-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="9bd0b-109">Weitere Informationen finden Sie unter [RFC 5322](https://tools.ietf.org/html/rfc5322) (insbesondere Abschnitte 3.2.3, 3,4 und 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), sowie [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="9bd0b-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="9bd0b-110">In diesem Artikel geht es um die Richtlinienerzwingung für die 5322. from-Adresse.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="9bd0b-111">In diesem Artikel geht es nicht um die 5321. MailFrom-Adresse.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="9bd0b-112">Leider gibt es noch einige Legacy-e-Mail-Server im Internet, die weiterhin "legitime" e-Mail-Nachrichten senden, die eine fehlende oder fehlerhafte from:-Adresse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="9bd0b-113">Wenn Sie regelmäßig e-Mails von Organisationen erhalten, die diese Legacy Systeme verwenden, ermutigen Sie diese Organisationen, Ihre e-Mail-Server so zu aktualisieren, dass Sie den modernen Sicherheitsstandards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="9bd0b-114">Microsoft startet die Implementierung der in diesem Artikel beschriebenen Richtlinien am 9. November 2017.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="9bd0b-115">Wie Office 365 die Verwendung einer gültigen from:-Adresse zur Verhinderung von Phishing-Angriffen erzwingt</span><span class="sxs-lookup"><span data-stu-id="9bd0b-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="9bd0b-116">Office 365 ändert die Art und Weise, wie die Verwendung der from:-Adresse in empfangenen Nachrichten erzwungen wird, um Sie vor Phishing-Angriffen besser zu schützen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="9bd0b-117">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-117">In this article:</span></span>
  
- [<span data-ttu-id="9bd0b-118">Alle Nachrichten müssen eine gültige from:-Adresse enthalten.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="9bd0b-119">Format der from:-Adresse, wenn kein Anzeigename hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="9bd0b-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="9bd0b-120">Format der from:-Adresse, wenn Sie einen Anzeigenamen einschließen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="9bd0b-121">Weitere Beispiele für gültige und ungültige from:-Adressen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="9bd0b-122">Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken, ohne die von:-Richtlinie zu unterbrechen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="9bd0b-123">Überschreiben der Office 365 von: Address Enforcement Policy</span><span class="sxs-lookup"><span data-stu-id="9bd0b-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="9bd0b-124">Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Office 365</span><span class="sxs-lookup"><span data-stu-id="9bd0b-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="9bd0b-125">Das Senden im Auftrag eines anderen Benutzers ist von dieser Änderung nicht betroffen, weitere Informationen finden Sie unter Terry Zinks Blog "[Was verstehen wir, wenn wir auf den Absender einer e-Mail" Bezug nehmen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="9bd0b-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="9bd0b-126">Alle Nachrichten müssen eine gültige from:-Adresse enthalten.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="9bd0b-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-127"></span></span>

<span data-ttu-id="9bd0b-128">Einige automatisierte Nachrichten enthalten keine from:-Adresse, wenn Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="9bd0b-129">Wenn Office 365 oder Outlook.com in der Vergangenheit eine Nachricht ohne eine from:-Adresse empfangen hat, hat der Dienst die folgende Standardeinstellung von: address zur Nachricht hinzugefügt, um die Zustellung zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="9bd0b-130">Ab dem 9. November 2017 werden Office 365 Änderungen an den Rechenzentren und e-Mail-Servern durchführen, wodurch eine neue Regel erzwungen wird, bei der Nachrichten ohne Absenderadresse nicht mehr von Office 365 oder Outlook.com akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="9bd0b-131">Stattdessen müssen alle von Office 365 empfangenen Nachrichten bereits eine gültige from:-Adresse enthalten.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="9bd0b-132">Andernfalls wird die Nachricht entweder an die Ordner "Junk-e-Mail" oder "Gelöschte Elemente" in Outlook.com und Office 365 gesendet.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="9bd0b-133">Syntax Übersicht: gültiges Format für die from:-Adresse für Office 365</span><span class="sxs-lookup"><span data-stu-id="9bd0b-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="9bd0b-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-134"></span></span>

<span data-ttu-id="9bd0b-135">Das Format für den Wert der from:-Adresse wird über mehrere RFCs hinweg detailliert definiert.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="9bd0b-136">Es gibt viele Variationen bei der Adressierung und was als gültig oder ungültig angesehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="9bd0b-137">Um es einfach zu halten, empfiehlt Microsoft, dass Sie das folgende Format und die folgenden Definitionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="9bd0b-138">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-138">Where:</span></span>
  
- <span data-ttu-id="9bd0b-139">Optional  *DisplayName* ist ein Ausdruck, der den Besitzer der e-Mail-Adresse beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="9bd0b-140">Dies kann beispielsweise ein benutzerfreundlicherer Name sein, um den Absender als den Namen des Postfachs zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="9bd0b-141">Die Verwendung eines Anzeigenamens ist optional.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-141">Using a display name is optional.</span></span> <span data-ttu-id="9bd0b-142">Wenn Sie jedoch einen Anzeigenamen verwenden, empfiehlt Microsoft, dass Sie ihn immer in Anführungszeichen einschließen, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="9bd0b-143">Erforderlich  die e- *Email* -e-mailbesteht aus:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="9bd0b-144">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-144">Where:</span></span>
    
  - <span data-ttu-id="9bd0b-145">Erforderlich  *local-Part* ist eine Zeichenfolge, die das Postfach identifiziert, das der Adresse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="9bd0b-146">Dies ist innerhalb der Domäne eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-146">This is unique within the domain.</span></span> <span data-ttu-id="9bd0b-147">Der Benutzername oder die GUID des Postfachbesitzers wird häufig als Wert für das lokale Webpart verwendet.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="9bd0b-148">Erforderlich  *Domain* ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des e-Mail-Servers, der das Postfach hostet, das vom lokalen Teil der e-Mail-Adresse identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="9bd0b-149">Format der from:-Adresse, wenn kein Anzeigename hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="9bd0b-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="9bd0b-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-150"></span></span>

<span data-ttu-id="9bd0b-151">Eine ordnungsgemäß formatierte from:-Adresse, die keinen Anzeigenamen enthält, umfasst nur eine einzelne e-Mail-Adresse mit oder ohne spitzen Klammern.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="9bd0b-152">Microsoft empfiehlt, die spitzen Klammern nicht mit Leerzeichen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="9bd0b-153">Fügen Sie außerdem nichts nach der e-Mail-Adresse hinzu.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="9bd0b-154">Die folgenden Beispiele sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="9bd0b-155">Das folgende Beispiel ist gültig, wird jedoch nicht empfohlen, da es Leerzeichen zwischen den spitzen Klammern und der e-Mail-Adresse enthält:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="9bd0b-156">Das folgende Beispiel ist ungültig, da es Text nach der e-Mail-Adresse enthält:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="9bd0b-157">Format der from:-Adresse, wenn Sie einen Anzeigenamen einschließen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="9bd0b-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-158"></span></span>

<span data-ttu-id="9bd0b-159">Für from: addresses, die einen Wert für den Anzeigenamen enthalten, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="9bd0b-160">Wenn die Absenderadresse einen Anzeigenamen enthält und der Anzeigename ein Komma enthält, muss der Anzeigename in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="9bd0b-161">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-161">For example:</span></span>
    
    <span data-ttu-id="9bd0b-162">Das folgende Beispiel ist gültig:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="9bd0b-163">Das folgende Beispiel ist ungültig:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="9bd0b-164">Der Anzeigename wird nicht in Anführungszeichen gesetzt, wenn dieser Anzeigename ein Komma enthält, ist gemäß RFC 5322 ungültig.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="9bd0b-165">Es empfiehlt sich, Anführungszeichen um den Anzeigenamen zu setzen, unabhängig davon, ob ein Komma innerhalb des Anzeigenamens vorhanden ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="9bd0b-166">Wenn die Absenderadresse einen Anzeigenamen enthält, muss die e-Mail-Adresse in spitzen Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="9bd0b-167">Als bewährte Methode empfiehlt Microsoft dringend, ein Leerzeichen zwischen dem Anzeigenamen und der e-Mail-Adresse einzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="9bd0b-168">Weitere Beispiele für gültige und ungültige from:-Adressen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="9bd0b-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-169"></span></span>

- <span data-ttu-id="9bd0b-170">Gültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="9bd0b-171">Ungültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-171">Invalid.</span></span> <span data-ttu-id="9bd0b-172">Die e-Mail-Adresse ist nicht mit spitzen Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="9bd0b-173">Gültig, wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-173">Valid, but not recommended.</span></span> <span data-ttu-id="9bd0b-174">Der Anzeigename ist nicht in Anführungszeichen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-174">The display name is not in quotes.</span></span> <span data-ttu-id="9bd0b-175">Als bewährte Methode sollten Sie immer Anführungszeichen um den Anzeigenamen herum setzen:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="9bd0b-176">Ungültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-176">Invalid.</span></span> <span data-ttu-id="9bd0b-177">Alles ist in Anführungszeichen eingeschlossen, nicht nur der Anzeigename:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="9bd0b-178">Ungültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-178">Invalid.</span></span> <span data-ttu-id="9bd0b-179">Es gibt keine spitzen Klammern um die e-Mail-Adresse:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="9bd0b-180">Ungültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-180">Invalid.</span></span> <span data-ttu-id="9bd0b-181">Zwischen dem Anzeigenamen und der linken spitzen Klammer ist kein Leerzeichen vorhanden:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="9bd0b-182">Ungültig</span><span class="sxs-lookup"><span data-stu-id="9bd0b-182">Invalid.</span></span> <span data-ttu-id="9bd0b-183">Zwischen dem schließenden Anführungszeichen um den Anzeigenamen und der linken spitzen Klammer ist kein Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="9bd0b-184">Automatische Antworten auf Ihre benutzerdefinierte Domäne unterdrücken, ohne die von:-Richtlinie zu unterbrechen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="9bd0b-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-185"></span></span>

<span data-ttu-id="9bd0b-186">Mit dem neuen Absender: Richtlinienerzwingung können Sie von: \< \> nicht mehr verwenden, um automatische Antworten zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="9bd0b-187">Stattdessen müssen Sie einen NULL-MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="9bd0b-188">Der MX-Eintrag (Mail Exchanger) ist ein Ressourceneintrag in DNS, der den e-Mail-Server identifiziert, der e-Mails für Ihre Domäne empfängt.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="9bd0b-189">Automatische Antworten (und alle Antworten) werden natürlich unterdrückt, da keine veröffentlichte Adresse vorhanden ist, an die der antwortenden Server Nachrichten senden kann.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="9bd0b-190">Wenn Sie einen NULL MX-Eintrag für Ihre benutzerdefinierte Domäne einrichten:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="9bd0b-191">Wählen Sie eine Domäne aus, von der Nachrichten gesendet werden sollen, die keine e-Mails annehmen (empfangen).</span><span class="sxs-lookup"><span data-stu-id="9bd0b-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="9bd0b-192">Wenn Ihre primäre Domäne beispielsweise contoso.com ist, können Sie noreply.contoso.com auswählen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="9bd0b-193">Richten Sie den NULL-MX-Eintrag für Ihre Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="9bd0b-194">Ein NULL-MX-Eintrag besteht aus einem einzelnen Punkt, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="9bd0b-195">Weitere Informationen zum Veröffentlichen eines NULL MX finden Sie unter [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="9bd0b-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="9bd0b-196">Überschreiben der Office 365 von: Address Enforcement Policy</span><span class="sxs-lookup"><span data-stu-id="9bd0b-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="9bd0b-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-197"></span></span>

<span data-ttu-id="9bd0b-198">Wenn die Bereitstellung der neuen Richtlinie abgeschlossen ist, können Sie diese Richtlinie nur für eingehende e-Mails umgehen, die Sie von Office 365 erhalten, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="9bd0b-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="9bd0b-199">IP-Zulassungslisten</span><span class="sxs-lookup"><span data-stu-id="9bd0b-199">IP allow lists</span></span>
    
- <span data-ttu-id="9bd0b-200">Exchange Online von Nachrichtenfluss Regeln</span><span class="sxs-lookup"><span data-stu-id="9bd0b-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="9bd0b-201">Microsoft empfiehlt dringend, die Erzwingung der from:-Richtlinie außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="9bd0b-202">Durch das außer Kraft setzen dieser Richtlinie können Sie das Risiko Ihrer Organisation für Spam, Phishing und andere Internetkriminalität verbessern.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="9bd0b-203">Sie können diese Richtlinie nicht für ausgehende e-Mails außer Kraft setzen, die Sie in Office 365 senden.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="9bd0b-204">Darüber hinaus werden von Outlook.com keine Außerkraftsetzungen jeglicher Art zugelassen, auch über die Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="9bd0b-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="9bd0b-205">Weitere Möglichkeiten zum verhindern und schützen von Internetkriminalität in Office 365</span><span class="sxs-lookup"><span data-stu-id="9bd0b-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="9bd0b-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="9bd0b-206"></span></span>

<span data-ttu-id="9bd0b-207">Weitere Informationen darüber, wie Sie Ihre Organisation gegen Internetkriminalität wie Phishing, Spam, Datenschutzverletzungen und andere Bedrohungen stärken können, finden Sie unter [bewährte Methoden für die Sicherheit für Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span><span class="sxs-lookup"><span data-stu-id="9bd0b-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9bd0b-208">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9bd0b-208">Related Topics</span></span>

[<span data-ttu-id="9bd0b-209">Rückläufernachrichten und EOP</span><span class="sxs-lookup"><span data-stu-id="9bd0b-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  

