---
title: E-Mail-Authentifizierung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Erfahren Sie, wie Exchange Online und Exchange Online Protection (EOP) in Microsoft 365 E-Mail-Authentifizierung (SPF, DKIM und DMARC) verwenden, um Spoofing, Phishing und Spam zu verhindern.
ms.openlocfilehash: f3a3ea902cb0c4fede4fcfd919f0969765bc4a96
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637556"
---
# <a name="email-authentication-in-microsoft-365"></a><span data-ttu-id="bb47a-103">E-Mail-Authentifizierung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb47a-103">Email authentication in Microsoft 365</span></span>

<span data-ttu-id="bb47a-104">E-Mail-Authentifizierung (auch als E-Mail-Validierung bezeichnet) ist eine Gruppe von Standards, die versucht, Spoofing (E-Mail-Nachrichten von gefälschten Absendern) entgegen zu wirken.</span><span class="sxs-lookup"><span data-stu-id="bb47a-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="bb47a-105">In Microsoft 365-Organisationen mit Exchange Online-Postfächern und in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer nutzt EOP die Standards, um eingehende E-Mails zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="bb47a-105">In Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP useses the standards to verify inbound email:</span></span>

- [<span data-ttu-id="bb47a-106">SPF</span><span class="sxs-lookup"><span data-stu-id="bb47a-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="bb47a-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="bb47a-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="bb47a-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="bb47a-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="bb47a-109">Die E-Mail-Authentifizierung überprüft, ob E-Mail-Nachrichten eines Absenders (z.B. laura@contoso.com) seriös sind und aus den erwarteten Quellen für diese E-Mail-Domäne stammen (z.B. contoso.com.)</span><span class="sxs-lookup"><span data-stu-id="bb47a-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="bb47a-110">Der Rest dieses Artikels erläutert, wie diese Technologien funktionieren und wie EOP sie verwendet, um eingehende E-Mails zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="bb47a-111">Verwenden von E-Mail-Authentifizierung, um Spoofing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="bb47a-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="bb47a-112">DMARC verhindert Spoofing, indem die **Von**-Adresse in Nachrichten untersucht wird (die Absender-E-Mail-Adresse, die Benutzer in ihren E-Mail-Clients sehen).</span><span class="sxs-lookup"><span data-stu-id="bb47a-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="bb47a-113">Ziel-E-Mail-Organisationen könne auch überprüfen, ob die E-Mail-Domäne SPF oder DKIM durchlaufen hat. Dies würde darauf hin deuten, dass die Domäne authentifiziert wurde und daher kein Spoofing erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="bb47a-114">Allerdings ist das Problem, dass SPF-, DKIM- und DMARC-Einträge im DNS für die E-Mail-Authentifizierung (gemeinsam unter der Bezeichnung „E-Mail-Authentifizierungsrichtlinien“ bekannt) vollständig optional sind.</span><span class="sxs-lookup"><span data-stu-id="bb47a-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="bb47a-115">Während Domänen mit Richtlinien für sichere E-Mail-Authentifizierung wie microsoft.com und skype.com vor Spoofing geschützt sind, werden Domänen mit schwächeren oder ohne E-Mail-Authentifizierungsrichtlinien zu einem hervorragenden Ziel für Spoofing.</span><span class="sxs-lookup"><span data-stu-id="bb47a-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="bb47a-116">Im März 2018 verfügen nur 9 % der Domänen der Fortune 500-Unternehmen über Richtlinien für sichere E-Mail-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bb47a-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="bb47a-117">Die verbleibenden 91% der Unternehmen können möglicherweise von einem Angreifer gefälscht werden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="bb47a-118">Falls kein anderer E-Mail-Filtermechanismus aktiviert ist, werden E-Mails von gefälschten Absendern in diesen Domänen möglicherweise an die Benutzer übermittelt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![DMARC-Richtlinien von Fortune 500-Unternehmen](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="bb47a-120">Der Anteil kleiner und mittelständischer Unternehmen, die keine Fortune 500-Unternehmen sind und Richtlinien für sichere E-Mail-Authentifizierung veröffentlichen, ist kleiner und noch kleiner für E-Mail-Domänen außerhalb von Nordamerika und Westeuropa.</span><span class="sxs-lookup"><span data-stu-id="bb47a-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="bb47a-121">Dies ist ein großes Problem, denn während Unternehmen möglicherweise nicht wissen, wie die E-Mail-Authentifizierung funktioniert, wissen Angreifer den Mangel auszunutzen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="bb47a-122">Da Phishing und ein solches Problem darstellt und die Einführung von Richtlinien für sichere E-Mail-Authentifizierung begrenzt ist, verwendet Microsoft *implizite E-Mail-Authentifizierung*, um eingehende E-Mails zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="bb47a-123">Die implizite E-Mail-Authentifizierung basiert auf zahlreichen Erweiterungen zu regulären E-Mail-Authentifizierungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="bb47a-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="bb47a-124">Zu diesen Erweiterungen gehören die Absenderzuverlässigkeit, die Geschichte des Absenders, die Geschichte des Empfängers, Verhaltensanalysen und weitere fortgeschrittene Techniken.</span><span class="sxs-lookup"><span data-stu-id="bb47a-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="bb47a-125">Eine Nachricht von einer Domäne, die keine E-Mail-Authentifizierungsrichtlinien verwendet, wird als Spoof gekennzeichnet, wenn sie nicht auf andere Weise signalisiert, dass es sich dabei um eine seriöse Nachricht handelt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="bb47a-126">Eine allgemeine Ankündigung von Microsoft finden Sie unter [A Sea of Phish Part 2 – Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="bb47a-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="bb47a-127">Zusammengesetzte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb47a-127">Composite authentication</span></span>

<span data-ttu-id="bb47a-128">Obwohl SPF, DKIM und DMARC an sich hilfreich sind, wird hier der Authentifizierungsstatus nicht ausreichend kommuniziert, wenn eine Nachricht keine expliziten Authentifizierungsdatensätze enthält.</span><span class="sxs-lookup"><span data-stu-id="bb47a-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="bb47a-129">Daher hat Microsoft einen Algorithmus für implizite E-Mail-Authentifizierung entwickelt, der mehrere Signale in einem einzelnen Wert kombiniert, auch als _Composite Authentication (zusammengesetzte Authentifizierung)_ oder kurz „compauth“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bb47a-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="bb47a-130">Der Compauth-Wert wird im **Authentication-Results**-Header im Nachrichtenheader vermerkt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="bb47a-131">Authentifizierungsergebnisse:</span><span class="sxs-lookup"><span data-stu-id="bb47a-131">Authentication-Results:</span></span><br/><span data-ttu-id="bb47a-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="bb47a-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="bb47a-133">Diese Werte werden in der [Nachrichtenkopfzeile „Authentication-results“](anti-spam-message-headers.md#authentication-results-message-header) erklärt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="bb47a-134">Durch Untersuchung der Nachrichtenkopfzeilen können Administratoren oder sogar Endbenutzer ermitteln, wie Microsoft 365 ermittelt hat, dass der Absender gefälscht ist.</span><span class="sxs-lookup"><span data-stu-id="bb47a-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="bb47a-135">Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen</span><span class="sxs-lookup"><span data-stu-id="bb47a-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="bb47a-136">Falls Sie sich nur auf die Aufzeichnungen der E-Mail-Authentifizierung verlassen, um zu beurteilen, ob eine eingehende Nachricht gefälscht ist, unterliegt ihr Urteilsvermögen den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="bb47a-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="bb47a-137">Die sendende Domäne könnte nicht über die erforderlichen DNS-Aufzeichnungen verfügen oder die Aufzeichnungen sind falsch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="bb47a-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="bb47a-138">Die Quelldomäne hat DNS-Einträge zwar ordnungsgemäß konfiguriert, aber diese Domäne entspricht nicht der Domäne in der Von-Adresse.</span><span class="sxs-lookup"><span data-stu-id="bb47a-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="bb47a-139">SPF und DKIM machen es nicht erforderlich, dass die Domäne in der Von-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bb47a-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="bb47a-140">Angreifer oder legitime Dienste können eine Domäne registrieren, SPF und DKIM für die Domäne konfigurieren, eine vollkommen andere Domäne in der Von-Adresse verwenden und diese Nachricht wird sowohl SPF als auch DKIM passieren.</span><span class="sxs-lookup"><span data-stu-id="bb47a-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="bb47a-141">Die zusammengesetzte Authorisierung kann gegen diese Einschränkungen Abhilfe schaffen, indem Sie Nachrichten passieren lässt, die E-Mail-Authentifizierungsprüfungen andernfalls nicht bestanden hätten.</span><span class="sxs-lookup"><span data-stu-id="bb47a-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="bb47a-142">Wie zuvor beschrieben, verwendet die implizite E-Mail-Authentifizierung mehrere Signale, um festzustellen, ob eine Nachricht legitim ist.</span><span class="sxs-lookup"><span data-stu-id="bb47a-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="bb47a-143">Die folgenden Beispiele konzentrieren sich zur Vereinfachung auf E-Mail-Authentifizierungsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="bb47a-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="bb47a-144">Andere Back-End-Intelligenz-Faktoren könnten Nachrichten, die durch die E-Mail-Authentifizierung als gefälscht eingestuft werden, passieren lassen oder Nachrichten, die durch die E-Mail-Authentifizierung als legitim eingestuft werden, als gefälscht identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bb47a-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="bb47a-145">So hat beispielsweise die fabrikam.com-Domäne keine SPF-, DKIM- oder DMARC-Einträge.</span><span class="sxs-lookup"><span data-stu-id="bb47a-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="bb47a-146">Nachrichten von Absendern in der Domäne fabrikam.com können die zusammengesetzte Authentifizierung ggfs. nicht durchlaufen (beachten Sie den `compauth`-Wert und den Grund):</span><span class="sxs-lookup"><span data-stu-id="bb47a-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="bb47a-147">Wenn fabrikam.com einen SPF-, aber keinen DKIM-Eintrag konfiguriert, kann Nachricht die zusammengesetzte Authentifizierung bestehen, da die Domäne, die SPF übergeben hat, der Domäne in der „Von“-Adresse entspricht:</span><span class="sxs-lookup"><span data-stu-id="bb47a-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="bb47a-148">Falls fabrikam.com einen DKIM-Eintrag, jedoch keinen SPF-Eintrag konfiguriert, kann die Nachricht die zusammengesetzte Authentifizierung bestehen, weil die Domäne in der übergebenen DKIM-Signatur der Domäne in der Von-Adresse entspricht:</span><span class="sxs-lookup"><span data-stu-id="bb47a-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="bb47a-149">Wenn die Domäne in SPF oder der DKIM-Signatur nicht mit der Domäne in der Von-Adresse übereinstimmt, kann die Nachricht eine zusammengesetzte Authentifizierung ggfs. nicht bestehen:</span><span class="sxs-lookup"><span data-stu-id="bb47a-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="bb47a-150">Lösungen für legitime Absender, die nicht-authentifizierte E-Mails senden</span><span class="sxs-lookup"><span data-stu-id="bb47a-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="bb47a-151">Microsoft 365 verfolgt, wer nicht authentifizierte E-Mails an Ihre Organisation sendet.</span><span class="sxs-lookup"><span data-stu-id="bb47a-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="bb47a-152">Wenn der Dienst annimmt, dass der Absender nicht seriös ist, wird die Nachricht als Fehler bei der zusammengesetzten Authorisierung markiert.</span><span class="sxs-lookup"><span data-stu-id="bb47a-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="bb47a-153">Um dies zu vermeiden, können Sie die Empfehlungen in diesem Abschnitt verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="bb47a-154">Konfigurieren der E-Mail-Authentifizierung für Domänen, die Sie besitzen</span><span class="sxs-lookup"><span data-stu-id="bb47a-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="bb47a-155">Sie können diese Methode verwenden, um Probleme mit organisationsinternem und domänenübergreifendem Spoofing zu beheben, wenn Sie mehrere Mandanten besitzen oder mit diesen interagieren.</span><span class="sxs-lookup"><span data-stu-id="bb47a-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="bb47a-156">Sie kann auch zum Beheben von Problemen mit domänenübergreifendem Spoofing verwendet werden, wenn Sie Nachrichten an andere Kunden innerhalb von Microsoft 365 oder an Drittanbieter senden, die von anderen Anbietern gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="bb47a-157">[Konfiguration von SPF-Einträgen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) für Ihre Domänen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="bb47a-158">[Konfiguration von DKIM-Einträgen](use-dkim-to-validate-outbound-email.md) für Ihre primären Domänen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="bb47a-159">[Ziehen Sie es in Erwägung, DMARC-Einträge für Ihre Domäne](use-dmarc-to-validate-email.md) einzurichten, um Ihre seriösen Absender zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="bb47a-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="bb47a-160">Microsoft bietet keine detaillierten Implementierungsrichtlinien für SPF, DKIM und DMARC-Einträge.</span><span class="sxs-lookup"><span data-stu-id="bb47a-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="bb47a-161">Es gibt jedoch eine Menge Informationen, die online verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bb47a-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="bb47a-162">Es gibt auch Drittanbieter, die Ihrer Organisation dabei helfen, E-Mail-Authentifizierungsdatensätze einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bb47a-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="bb47a-163">Sie kennen nicht alle Quellen Ihrer E-Mails</span><span class="sxs-lookup"><span data-stu-id="bb47a-163">You don't know all sources for your email</span></span>

<span data-ttu-id="bb47a-164">Viele Domänen veröffentlichen keine SPF-Einträge, da Sie nicht alle E-Mail-Quellen für Nachrichten in Ihrer Domäne kennen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="bb47a-165">Beginnen Sie damit, einen SPF-Eintrag für all jene E-Mail-Quellen zu veröffentlichen, die Sie kennen (insbesondere diejenigen, bei denen sich der Datenverkehr Ihres Unternehmens befindet), und veröffentlichen Sie eine neutrale SPF-Richtlinie `?all`:</span><span class="sxs-lookup"><span data-stu-id="bb47a-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="bb47a-166">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb47a-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="bb47a-167">Dieses Beispiel bedeutet, dass E-Mails aus Ihrer Unternehmensinfrastruktur die E-Mail-Authentifizierung passieren, aber E-Mails aus unbekannten Quellen auf neutral zurückfallen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="bb47a-168">Microsoft 365 behandelt eingehende E-Mails aus Ihrer Unternehmensinfrastruktur als authentifiziert, aber E-Mail-Nachrichten aus unbekannten Quellen werden möglicherweise weiterhin als Fälschung gekennzeichnet (je nachdem, ob sie von Microsoft 365 implizit authentifiziert werden können).</span><span class="sxs-lookup"><span data-stu-id="bb47a-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="bb47a-169">Dies stellt jedoch immer noch eine Verbesserung dazu dar, dass alle E-Mails von Microsoft 365 als Spoofing markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="bb47a-170">Sobald Sie mit einer SPF-Fallback-Richtlinie von `?all`begonnen haben, können Sie nach und nach weitere E-Mail-Quellen für Ihre Nachrichten entdecken und dann Ihren SPF-Eintrag mit einer strikteren Richtlinie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bb47a-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="bb47a-171">Verwenden der Spoofingintelligenz zum Konfigurieren zulässiger Absender nicht authentifizierter E-Mails</span><span class="sxs-lookup"><span data-stu-id="bb47a-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="bb47a-172">Sie können Sie auch [Spoofingintelligenz](learn-about-spoof-intelligence.md) verwenden, damit Absender nicht authentifizierte Nachrichten an Ihre Organisation senden können.</span><span class="sxs-lookup"><span data-stu-id="bb47a-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="bb47a-173">Bei externen Domänen handelt es sich bei dem gefälschten Benutzer um die Domäne in der Von-Adresse, während es sich bei der sendenden Infrastruktur entweder um die Quell-IP-Adresse (aufgeteilt in /24 CIDR-Bereiche) oder um die Organisationsdomäne des Reverse DNS-Eintrags (PTR) handelt.</span><span class="sxs-lookup"><span data-stu-id="bb47a-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="bb47a-174">Im folgenden Screenshot kann die IP 131.107.18.4 lauten und den PTR-Eintrag outbound.mail.protection.outlook.com aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="bb47a-175">Dies würde als Outlook.com als sendende Infrastruktur annzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="bb47a-176">Damit dieser Absender nicht authentifizierte E-Mails senden kann, ändern Sie die Einstellung von **No** zu **Yes**.</span><span class="sxs-lookup"><span data-stu-id="bb47a-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Einrichten von zulässigen Spoofingabsendern](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="bb47a-178">Erstellen eines Zulassungseintrags für das Absender/Empfänger-Paar</span><span class="sxs-lookup"><span data-stu-id="bb47a-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="bb47a-179">Wenn Sie die Spamfilterung, einige Teile der Phishing-Filterung, aber nicht die Malware-Filterung für bestimmte Absender umgehen möchten, lesen Sie [Erstellen von Listen sicherer Absender in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bb47a-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="bb47a-180">Bitten Sie den Absender, die E-Mail-Authentifizierung für Domänen, die Sie nicht besitzen, zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bb47a-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="bb47a-181">Aufgrund des Problems mit Spam und Phishing empfiehlt Microsoft die E-Mail-Authentifizierung für alle E-Mail-Organisationen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="bb47a-182">Statt manuelle Außerkraftsetzungen in Ihrer Organisation zu konfigurieren, können Sie einen Administrator in der sendenden Domäne bitten, ihre E-Mail-Authentifizierungseinträge zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bb47a-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="bb47a-183">Auch wenn sie in der Vergangenheit keine E-Mail-Authentifizierungseinträge veröffentlichen mussten, sollten sie dies tun, wenn sie E-Mails an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="bb47a-184">Richten Sie SPF ein, um die sendenden IP-Adressen Ihrer Domäne zu veröffentlichen, und DKIM (falls verfügbar) zum digitalen Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="bb47a-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="bb47a-185">Sie sollten auch das Einrichten von DMARC-Einträgen in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="bb47a-186">Wenn sie zum Senden von E-Mails Massenversender verwenden, überprüfen Sie, ob die Domäne in der Von-Adresse (sofern sie ihnen gehört) mit der Domäne übereinstimmt, die SPF oder DMARC passiert.</span><span class="sxs-lookup"><span data-stu-id="bb47a-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="bb47a-187">Überprüfen Sie, ob die folgenden Speicherorte (sofern sie diese verwenden) Bestandteil des SPF-Eintrags sind:</span><span class="sxs-lookup"><span data-stu-id="bb47a-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="bb47a-188">Lokale E-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="bb47a-188">On-premises email servers.</span></span>
  - <span data-ttu-id="bb47a-189">E-Mail-Nachrichten von einem SaaS-Anbieter (Software-as-a-Service) versendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bb47a-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="bb47a-190">E-Mail-Nachrichten, die von einem Cloud-Hostingdienst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services usw.) versendet wurden</span><span class="sxs-lookup"><span data-stu-id="bb47a-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="bb47a-191">Konfigurieren Sie für kleine Domänen, die von einem ISP gehostet werden, den SPF-Eintrag gemäß den Anweisungen des ISPs.</span><span class="sxs-lookup"><span data-stu-id="bb47a-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="bb47a-192">Obwohl es am Anfang möglicherweise schwierig wird, sendende Domänen zur Authentifizierung zu veranlassen, werden sie im Laufe der Zeit, da immer mehr E-Mail-Filter die Nachrichten dieser Domänen als Junk einstufen oder sie sogar ablehnen, die entsprechenden Datensätze einrichten, um eine bessere Zustellung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb47a-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="bb47a-193">Außerdem kann ihre Beteiligung im Kampf gegen Phishing helfen und die Möglichkeit von Phishing-Angriffen in ihrer Organisation oder ihren Organisationen verringern, an die sie e-Mails senden.</span><span class="sxs-lookup"><span data-stu-id="bb47a-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="bb47a-194">Informationen für Infrastrukturanbieter (ISPs, ESPs oder Cloud-Hostinganbieter)</span><span class="sxs-lookup"><span data-stu-id="bb47a-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="bb47a-195">Wenn Sie E-Mails einer Domäne hosten oder eine Hostinginfrastruktur anbieten, die E-Mails senden kann, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="bb47a-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="bb47a-196">Stellen Sie sicher, dass Ihre Kunden über Dokumentationen verfügen, die erläutern, wie Ihre Kunden ihre SPF-Einträge konfigurieren sollten.</span><span class="sxs-lookup"><span data-stu-id="bb47a-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="bb47a-197">Ziehen Sie in Erwägung, ausgehende E-Mails mit DKIM-Signaturen zu signieren, selbst wenn der Kunde dies nicht explizit eingerichtet hat (Signieren mit Standarddomäne).</span><span class="sxs-lookup"><span data-stu-id="bb47a-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="bb47a-198">Sie können die E-Mail sogar doppelt mit DKIM-Signaturen signieren (mit der Domäne des Kunden, falls eingerichtet, und mit der DKIM-Signatur Ihres Unternehmens).</span><span class="sxs-lookup"><span data-stu-id="bb47a-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="bb47a-199">Die Zustellbarkeit an Microsoft ist auch nicht garantiert, wenn Sie E-Mails, die von Ihrer Plattform stammen, authentifizieren. Es wird jedoch zumindest sichergestellt, dass Ihre E-Mail nicht als Junk-E-Mail von Microsoft eingestuft wird, weil sie nicht authentifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="bb47a-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="bb47a-200">Weitere Informationen zu bewährten Methoden für Dienstanbieter finden Sie unter [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span><span class="sxs-lookup"><span data-stu-id="bb47a-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
