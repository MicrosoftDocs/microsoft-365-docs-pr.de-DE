---
title: E-Mail-Authentifizierung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Administratoren erfahren hier, wie EOP E-Mail-Authentifizierung (SPF, DKIM und DMARC) verwendet, um Spoofing, Phishing und Spam zu verhindern.
ms.openlocfilehash: d490caf600fef9d9caab79a1a97ec29637e10d66
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202975"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="197fa-103">E-Mail-Authentifizierung in EOP</span><span class="sxs-lookup"><span data-stu-id="197fa-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="197fa-104">E-Mail-Authentifizierung (auch als E-Mail-Validierung bezeichnet) ist eine Gruppe von Standards, die versucht, Spoofing (E-Mail-Nachrichten von gefälschten Absendern) entgegen zu wirken.</span><span class="sxs-lookup"><span data-stu-id="197fa-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="197fa-105">In allen Microsoft 365-Organisationen nutzt EOP folgende Standards, um eingehende e-Mails zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="197fa-105">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="197fa-106">SPF</span><span class="sxs-lookup"><span data-stu-id="197fa-106">SPF</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing?view=o365-worldwide)

- [<span data-ttu-id="197fa-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="197fa-107">DKIM</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide)

- [<span data-ttu-id="197fa-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="197fa-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="197fa-109">Die E-Mail-Authentifizierung überprüft, ob E-Mail-Nachrichten eines Absenders (z.B. laura@contoso.com) seriös sind und aus den erwarteten Quellen für diese E-Mail-Domäne stammen (z.B. contoso.com.)</span><span class="sxs-lookup"><span data-stu-id="197fa-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="197fa-110">Der weitere Artikel erläutert, wie diese Technologien funktionieren und wie EOP sie verwendet, um eingehende E-Mails zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="197fa-110">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="197fa-111">Verwenden von E-Mail-Authentifizierung, um Spoofing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="197fa-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="197fa-112">DMARC verhindert Spoofing, indem die **Von**-Adresse in Nachrichten überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="197fa-112">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="197fa-113">Die **Von**-Adresse ist die E-Mail-Adresse des Absenders, die Benutzer in ihrem E-Mail-Client sehen.</span><span class="sxs-lookup"><span data-stu-id="197fa-113">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="197fa-114">Die Ziel-E-Mail-Organisationen können auch überprüfen, ob die E-Mail-Domäne SPF oder DKIM erfolgreich bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="197fa-114">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="197fa-115">Anders ausgedrückt: Die Domäne wurde authentifiziert, daher wird die E-Mail-Adresse des Absenders nicht gespoofed.</span><span class="sxs-lookup"><span data-stu-id="197fa-115">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="197fa-116">DNS-Einträge für SPF, DKIM und DMARC (gemeinsam als "E-Mail-Authentifizierungsrichtlinien" bekannt) sind jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="197fa-116">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="197fa-117">Domänen mit starken E-Mail-Authentifizierungsrichtlinien wie microsoft.com und skype.com sind vor Spoofing geschützt.</span><span class="sxs-lookup"><span data-stu-id="197fa-117">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="197fa-118">Aber Domänen mit schwächeren E-Mail-Authentifizierungsrichtlinien oder ohne jede Richtlinie sind hervorragende Ziele für Spoofing.</span><span class="sxs-lookup"><span data-stu-id="197fa-118">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="197fa-119">Im März 2018 verfügten nur 9 % der Domänen der Fortune 500-Unternehmen über sichere E-Mail-Authentifizierungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="197fa-119">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="197fa-120">Die verbleibenden 91% der Unternehmen können möglicherweise mithilfe von Spoofing angegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="197fa-120">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="197fa-121">Falls kein anderer E-Mail-Filtermechanismus aktiviert ist, werden E-Mails von gefälschten Absendern in diesen Domänen möglicherweise an die Benutzer übermittelt.</span><span class="sxs-lookup"><span data-stu-id="197fa-121">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![DMARC-Richtlinien von Fortune 500-Unternehmen](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="197fa-123">Der Anteil von kleinen und mittelständischen Unternehmen, die sichere E-Mail-Authentifizierungsrichtlinien verfügen, ist kleiner.</span><span class="sxs-lookup"><span data-stu-id="197fa-123">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="197fa-124">Und die Zahl der E-Mail-Domänen außerhalb von Nordamerika und Westeuropa ist sogar noch geringer.</span><span class="sxs-lookup"><span data-stu-id="197fa-124">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="197fa-125">Das Fehlen sicherer E-Mail-Authentifizierungsrichtlinien stellt ein großes Problem dar.</span><span class="sxs-lookup"><span data-stu-id="197fa-125">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="197fa-126">Während Organisationen möglicherweise nicht verstehen, wie E-Mail-Authentifizierung funktioniert, sind sich Angreifer darüber sehr wohl im Klaren – und nutzen das zu ihrem Vorteil.</span><span class="sxs-lookup"><span data-stu-id="197fa-126">W while organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="197fa-127">Wegen der Sorge vor Phishing und der unzureichenden Einführung sicherer E-Mail-Authentifizierungsrichtlinien, verwendet Microsoft *implizite E-Mail-Authentifizierung*, um eingehende E-Mails zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="197fa-127">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="197fa-128">Die implizite E-Mail-Authentifizierung ist eine Erweiterung der regulären E-Mail-Authentifizierungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="197fa-128">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="197fa-129">Zu diesen Erweiterungen gehören: Absenderzuverlässigkeit, Absenderhistorie, Empfängerhistorie, Verhaltensanalysen und weitere fortgeschrittene Techniken.</span><span class="sxs-lookup"><span data-stu-id="197fa-129">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="197fa-130">Beim Fehlen weiterer Signale dieser Erweiterungen werden Nachrichten, die von Domänen gesendet ohne E-Mail-Authentifizierungsrichtlinien gesendet werden, als Spoof gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="197fa-130">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="197fa-131">Eine allgemeine Ankündigung von Microsoft finden Sie unter [A Sea of Phish Part 2 – Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="197fa-131">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="197fa-132">Zusammengesetzte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="197fa-132">Composite authentication</span></span>

<span data-ttu-id="197fa-133">Wenn eine Domäne nicht über herkömmliche SPF-, DKIM- und DMARC-Einträge verfügt, vermitteln diese Datensatzprüfungen nicht genügend Informationen zum Authentifizierungsstatus.</span><span class="sxs-lookup"><span data-stu-id="197fa-133">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="197fa-134">Deshalb hat Microsoft einen Algorithmus für die implizite E-Mail-Authentifizierung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="197fa-134">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="197fa-135">Dieser Algorithmus kombiniert mehrere Signale in einem einzelnen Wert, der auch als _Composite Authentication_ (zusammengesetzte Authentifizierung) oder `compauth` bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="197fa-135">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="197fa-136">Der `compauth`-Wert wird im Header der **Authentifizierungsergebnisse** im Nachrichtenheader vermerkt.</span><span class="sxs-lookup"><span data-stu-id="197fa-136">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="197fa-137">Diese Werte werden in der [Nachrichtenkopfzeile „Authentication-results“](anti-spam-message-headers.md#authentication-results-message-header) erklärt.</span><span class="sxs-lookup"><span data-stu-id="197fa-137">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="197fa-138">Durch Untersuchung der Nachrichtenkopfzeilen können Administratoren oder sogar Endbenutzer ermitteln, wie Microsoft 365 ermittelt hat, dass der Absender gefälscht ist.</span><span class="sxs-lookup"><span data-stu-id="197fa-138">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="197fa-139">Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen</span><span class="sxs-lookup"><span data-stu-id="197fa-139">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="197fa-140">Falls Sie sich nur auf die Aufzeichnungen der E-Mail-Authentifizierung verlassen, um zu beurteilen, ob eine eingehende Nachricht gefälscht ist, unterliegt ihr Urteilsvermögen den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="197fa-140">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="197fa-141">Die sendende Domäne könnte nicht über die erforderlichen DNS-Aufzeichnungen verfügen oder die Aufzeichnungen sind falsch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="197fa-141">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="197fa-142">Die Quelldomäne hat DNS-Einträge zwar ordnungsgemäß konfiguriert, aber diese Domäne entspricht nicht der Domäne in der Von-Adresse.</span><span class="sxs-lookup"><span data-stu-id="197fa-142">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="197fa-143">SPF und DKIM machen es nicht erforderlich, dass die Domäne in der Von-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="197fa-143">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="197fa-144">Angreifer oder legitime Dienste können eine Domäne registrieren, SPF und DKIM für die Domäne konfigurieren und eine vollkommen andere Domäne in der “Von”-Adresse verwenden.</span><span class="sxs-lookup"><span data-stu-id="197fa-144">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="197fa-145">Nachrichten von Absendern in dieser Domäne werden von SPF und DKIM nicht beanstandet.</span><span class="sxs-lookup"><span data-stu-id="197fa-145">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="197fa-146">Die zusammengesetzte Authentifizierung kann diesen Einschränkungen abhelfen, indem sie Nachrichten weitergibt, die E-Mail-Authentifizierungsprüfungen andernfalls nicht bestanden hätten.</span><span class="sxs-lookup"><span data-stu-id="197fa-146">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="197fa-147">Die folgenden Beispiele konzentrieren sich zur Vereinfachung auf E-Mail-Authentifizierungsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="197fa-147">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="197fa-148">Andere Back-End-Intelligenz-Faktoren könnten Nachrichten, die durch die E-Mail-Authentifizierung als gefälscht eingestuft werden, passieren lassen oder Nachrichten, die durch die E-Mail-Authentifizierung als legitim eingestuft werden, als gefälscht identifizieren.</span><span class="sxs-lookup"><span data-stu-id="197fa-148">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="197fa-149">So hat beispielsweise die fabrikam.com-Domäne keine SPF-, DKIM- oder DMARC-Einträge.</span><span class="sxs-lookup"><span data-stu-id="197fa-149">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="197fa-150">Nachrichten von Absendern in der Domäne fabrikam.com können die zusammengesetzte Authentifizierung ggfs. nicht durchlaufen (beachten Sie den `compauth`-Wert und den Grund):</span><span class="sxs-lookup"><span data-stu-id="197fa-150">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="197fa-151">Wenn fabrikam.com einen SPF ohne einen DKIM-Eintrag konfiguriert, kann die Nachricht eine kombinierte Authentifizierung weitergeben.</span><span class="sxs-lookup"><span data-stu-id="197fa-151">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="197fa-152">Die Domäne, die SPF-Prüfungen übergeben hat, wird an der Domäne in der “Von”-Adresse ausgerichtet:</span><span class="sxs-lookup"><span data-stu-id="197fa-152">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="197fa-153">Wenn fabrikam.com einen SP-Eintrag ohne einen DKIM-Eintrag konfiguriert, kann die Nachricht eine kombinierte Authentifizierung weitergeben.</span><span class="sxs-lookup"><span data-stu-id="197fa-153">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="197fa-154">Die Domäne in der DKIM-Signatur, wird an der Domäne in der “Von”-Adresse ausgerichtet:</span><span class="sxs-lookup"><span data-stu-id="197fa-154">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="197fa-155">Wenn die Domäne in SPF oder der DKIM-Signatur nicht mit der Domäne in der “Von”-Adresse übereinstimmt, kann die Nachricht eine zusammengesetzte Authentifizierung ggfs. nicht bestehen:</span><span class="sxs-lookup"><span data-stu-id="197fa-155">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="197fa-156">Lösungen für legitime Absender, die nicht-authentifizierte E-Mails senden</span><span class="sxs-lookup"><span data-stu-id="197fa-156">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="197fa-157">Microsoft 365 verfolgt, wer nicht authentifizierte E-Mails an Ihre Organisation sendet.</span><span class="sxs-lookup"><span data-stu-id="197fa-157">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="197fa-158">Wenn der Dienst annimmt, dass der Absender nicht seriös ist, werden die Nachrichten dieses Absenders als Fehlschlag bei der zusammengesetzten Authentifizierung markiert.</span><span class="sxs-lookup"><span data-stu-id="197fa-158">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="197fa-159">Um dies zu vermeiden, können Sie die Empfehlungen in diesem Abschnitt verwenden.</span><span class="sxs-lookup"><span data-stu-id="197fa-159">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="197fa-160">Konfigurieren der E-Mail-Authentifizierung für Domänen, die Sie besitzen</span><span class="sxs-lookup"><span data-stu-id="197fa-160">Configure email authentication for domains you own</span></span>

<span data-ttu-id="197fa-161">Sie können diese Methode verwenden, um Probleme mit organisationsinternem und domänenübergreifendem Spoofing zu beheben, wenn Sie mehrere Mandanten besitzen oder mit diesen interagieren.</span><span class="sxs-lookup"><span data-stu-id="197fa-161">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="197fa-162">Sie kann auch zum Beheben von Problemen mit domänenübergreifendem Spoofing verwendet werden, wenn Sie Nachrichten an andere Kunden innerhalb von Microsoft 365 oder an Drittanbieter senden, die von anderen Anbietern gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="197fa-162">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="197fa-163">[Konfiguration von SPF-Einträgen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) für Ihre Domänen.</span><span class="sxs-lookup"><span data-stu-id="197fa-163">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="197fa-164">[Konfiguration von DKIM-Einträgen](use-dkim-to-validate-outbound-email.md) für Ihre primären Domänen.</span><span class="sxs-lookup"><span data-stu-id="197fa-164">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="197fa-165">[Ziehen Sie es in Erwägung, DMARC-Einträge für Ihre Domäne](use-dmarc-to-validate-email.md) einzurichten, um Ihre seriösen Absender zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="197fa-165">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="197fa-166">Microsoft bietet keine detaillierten Implementierungsrichtlinien für SPF, DKIM und DMARC-Einträge.</span><span class="sxs-lookup"><span data-stu-id="197fa-166">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="197fa-167">Es gibt jedoch viele Informationen, die online verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="197fa-167">However, there's many information available online.</span></span> <span data-ttu-id="197fa-168">Auch gibt es Drittanbieter, die Ihrer Organisation dabei helfen können, E-Mail-Authentifizierungsdatensätze einzurichten.</span><span class="sxs-lookup"><span data-stu-id="197fa-168">There are also third party companies dedicated to helping your organization setup email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="197fa-169">Sie kennen nicht alle Quellen Ihrer E-Mails</span><span class="sxs-lookup"><span data-stu-id="197fa-169">You don't know all sources for your email</span></span>

<span data-ttu-id="197fa-170">Viele Domänen veröffentlichen keine SPF-Einträge, da Sie nicht alle E-Mail-Quellen für Nachrichten in Ihrer Domäne kennen.</span><span class="sxs-lookup"><span data-stu-id="197fa-170">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="197fa-171">Beginnen Sie damit, einen SPF-Eintrag für all jene E-Mail-Quellen zu veröffentlichen, die Sie kennen (insbesondere diejenigen, bei denen sich der Datenverkehr Ihres Unternehmens befindet), und veröffentlichen Sie eine neutrale SPF-Richtlinie `?all`:</span><span class="sxs-lookup"><span data-stu-id="197fa-171">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="197fa-172">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="197fa-172">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="197fa-173">Dieses Beispiel bedeutet, dass E-Mails aus Ihrer Unternehmensinfrastruktur die E-Mail-Authentifizierung passieren, aber E-Mails aus unbekannten Quellen auf neutral zurückfallen.</span><span class="sxs-lookup"><span data-stu-id="197fa-173">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="197fa-174">Microsoft 365 behandelt eingehende E-Mails aus Ihrer Unternehmensinfrastruktur als authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="197fa-174">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="197fa-175">E-Mails von unbekannten Quellen sind möglicherweise weiterhin als Spoof gekennzeichnet, wenn die implizite Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="197fa-175">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="197fa-176">Dies stellt jedoch immer noch eine Verbesserung dazu dar, dass alle E-Mails von Microsoft 365 als Spoofing markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="197fa-176">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="197fa-177">Sobald Sie mit einer SPF-Fallback-Richtlinie von `?all`begonnen haben, können Sie nach und nach weitere E-Mail-Quellen für Ihre Nachrichten entdecken und dann Ihren SPF-Eintrag mit einer strikteren Richtlinie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="197fa-177">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="197fa-178">Verwenden der Spoofingintelligenz zum Konfigurieren zulässiger Absender nicht authentifizierter E-Mails</span><span class="sxs-lookup"><span data-stu-id="197fa-178">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="197fa-179">Sie können Sie auch [Spoofingintelligenz](learn-about-spoof-intelligence.md) verwenden, damit Absender nicht authentifizierte Nachrichten an Ihre Organisation senden können.</span><span class="sxs-lookup"><span data-stu-id="197fa-179">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="197fa-180">Bei externen Domänen handelt es sich bei dem gefälschten Benutzer um die Domäne in der Von-Adresse, während es sich bei der sendenden Infrastruktur entweder um die Quell-IP-Adresse (aufgeteilt in /24 CIDR-Bereiche) oder um die Organisationsdomäne des Reverse DNS-Eintrags (PTR) handelt.</span><span class="sxs-lookup"><span data-stu-id="197fa-180">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="197fa-181">Im folgenden Screenshot kann die IP 131.107.18.4 lauten und den PTR-Eintrag outbound.mail.protection.outlook.com aufweisen.</span><span class="sxs-lookup"><span data-stu-id="197fa-181">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="197fa-182">Dies würde als Outlook.com als sendende Infrastruktur annzeigen.</span><span class="sxs-lookup"><span data-stu-id="197fa-182">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="197fa-183">Damit dieser Absender nicht authentifizierte E-Mails senden kann, ändern Sie die Einstellung von **No** zu **Yes**.</span><span class="sxs-lookup"><span data-stu-id="197fa-183">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Einrichten von zulässigen Spoofingabsendern](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="197fa-185">Erstellen eines Zulassungseintrags für das Absender/Empfänger-Paar</span><span class="sxs-lookup"><span data-stu-id="197fa-185">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="197fa-186">Wenn Sie die Spamfilterung, einige Teile der Phishing-Filterung, aber nicht die Malware-Filterung für bestimmte Absender umgehen möchten, lesen Sie [Erstellen von Listen sicherer Absender in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="197fa-186">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="197fa-187">Bitten Sie den Absender, die E-Mail-Authentifizierung für Domänen, die Sie nicht besitzen, zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="197fa-187">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="197fa-188">Aufgrund des Problems mit Spam und Phishing empfiehlt Microsoft die E-Mail-Authentifizierung für alle E-Mail-Organisationen.</span><span class="sxs-lookup"><span data-stu-id="197fa-188">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="197fa-189">Statt manuelle Außerkraftsetzungen in Ihrer Organisation zu konfigurieren, können Sie einen Administrator in der sendenden Domäne bitten, ihre E-Mail-Authentifizierungseinträge zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="197fa-189">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="197fa-190">Auch wenn sie in der Vergangenheit keine E-Mail-Authentifizierungseinträge veröffentlichen mussten, sollten sie dies tun, wenn sie E-Mails an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="197fa-190">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="197fa-191">Richten Sie SPF ein, um die sendenden IP-Adressen Ihrer Domäne zu veröffentlichen, und DKIM (falls verfügbar) zum digitalen Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="197fa-191">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="197fa-192">Sie sollten auch das Einrichten von DMARC-Einträgen in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="197fa-192">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="197fa-193">Wenn sie zum Senden von E-Mails Massenversender verwenden, überprüfen Sie, ob die Domäne in der Von-Adresse (sofern sie ihnen gehört) mit der Domäne übereinstimmt, die SPF oder DMARC passiert.</span><span class="sxs-lookup"><span data-stu-id="197fa-193">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="197fa-194">Überprüfen Sie, ob die folgenden Speicherorte (sofern sie diese verwenden) Bestandteil des SPF-Eintrags sind:</span><span class="sxs-lookup"><span data-stu-id="197fa-194">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="197fa-195">Lokale E-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="197fa-195">On-premises email servers.</span></span>
  - <span data-ttu-id="197fa-196">E-Mail-Nachrichten von einem SaaS-Anbieter (Software-as-a-Service) versendet wurde.</span><span class="sxs-lookup"><span data-stu-id="197fa-196">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="197fa-197">E-Mail-Nachrichten, die von einem Cloud-Hostingdienst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services usw.) versendet wurden</span><span class="sxs-lookup"><span data-stu-id="197fa-197">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="197fa-198">Konfigurieren Sie für kleine Domänen, die von einem ISP gehostet werden, den SPF-Eintrag gemäß den Anweisungen des ISPs.</span><span class="sxs-lookup"><span data-stu-id="197fa-198">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="197fa-199">Obwohl es am Anfang möglicherweise schwierig wird, sendende Domänen zur Authentifizierung zu veranlassen, werden sie im Laufe der Zeit, da immer mehr E-Mail-Filter die Nachrichten dieser Domänen als Junk einstufen oder sie sogar ablehnen, die entsprechenden Datensätze einrichten, um eine bessere Zustellung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="197fa-199">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="197fa-200">Außerdem kann ihre Beteiligung im Kampf gegen Phishing helfen und die Möglichkeit von Phishing-Angriffen in ihrer Organisation oder ihren Organisationen verringern, an die sie e-Mails senden.</span><span class="sxs-lookup"><span data-stu-id="197fa-200">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="197fa-201">Informationen für Infrastrukturanbieter (ISPs, ESPs oder Cloud-Hostinganbieter)</span><span class="sxs-lookup"><span data-stu-id="197fa-201">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="197fa-202">Wenn Sie E-Mails einer Domäne hosten oder eine Hostinginfrastruktur anbieten, die E-Mails senden kann, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="197fa-202">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="197fa-203">Stellen Sie sicher, dass Ihre Kunden über Dokumentationen verfügen, die erläutern, wie Ihre Kunden ihre SPF-Einträge konfigurieren sollten.</span><span class="sxs-lookup"><span data-stu-id="197fa-203">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="197fa-204">Ziehen Sie in Erwägung, ausgehende E-Mails mit DKIM-Signaturen zu signieren, selbst wenn der Kunde dies nicht explizit eingerichtet hat (Signieren mit Standarddomäne).</span><span class="sxs-lookup"><span data-stu-id="197fa-204">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="197fa-205">Sie können die E-Mail sogar doppelt mit DKIM-Signaturen signieren (mit der Domäne des Kunden, falls eingerichtet, und mit der DKIM-Signatur Ihres Unternehmens).</span><span class="sxs-lookup"><span data-stu-id="197fa-205">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="197fa-206">Die Zustellbarkeit an Microsoft ist auch nicht garantiert, wenn Sie E-Mails, die von Ihrer Plattform stammen, authentifizieren. Es wird jedoch zumindest sichergestellt, dass Ihre E-Mail nicht als Junk-E-Mail von Microsoft eingestuft wird, weil sie nicht authentifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="197fa-206">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="197fa-207">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="197fa-207">Related links</span></span>

<span data-ttu-id="197fa-208">Weitere Informationen zu bewährten Methoden für Dienstanbieter finden Sie unter [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span><span class="sxs-lookup"><span data-stu-id="197fa-208">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="197fa-209">Erfahren Sie, wie Office 365 SPF verwendet und die DKIM-Überprüfung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="197fa-209">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="197fa-210">Weitere Informationen zu SPF</span><span class="sxs-lookup"><span data-stu-id="197fa-210">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="197fa-211">Weitere Informationen zu DKIM</span><span class="sxs-lookup"><span data-stu-id="197fa-211">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
