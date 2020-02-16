---
title: Verwenden des Sender Policy Framework (SPF) durch Office 365 zum Verhindern von Spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 'Zusammenfassung: Dieser Artikel beschreibt, wie Office 365 den Sender Policy Framework (SPF) TXT-Eintrag in DNS verwendet, um sicherzustellen, dass von Ihrer benutzerdefinierten Domäne gesendete Nachrichten von Ziel-E-Mail-Systemen als vertrauenswürdig eingestuft werden. Dies gilt für ausgehende E-Mail-Nachrichten von Office 365. Nachrichten, die von Office 365 an einen Empfänger in Office 365 gesendet werden, durchlaufen immer SPF.'
ms.openlocfilehash: e2863c0b8a66fa511c4ce842dc8026e880594292
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085997"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="f8cfc-105">Verwenden des Sender Policy Framework (SPF) durch Office 365 zum Verhindern von Spoofing</span><span class="sxs-lookup"><span data-stu-id="f8cfc-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="f8cfc-p102">**Zusammenfassung:** Dieser Artikel beschreibt, wie Office 365 den Sender Policy Framework (SPF) TXT-Eintrag in DNS verwendet, um sicherzustellen, dass von Ihrer benutzerdefinierten Domäne gesendete Nachrichten von Ziel-E-Mail-Systemen als vertrauenswürdig eingestuft werden. Dies gilt für ausgehende E-Mail-Nachrichten von Office 365. Nachrichten, die von Office 365 an einen Empfänger in Office 365 gesendet werden, durchlaufen immer SPF.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p102">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain. This applies to outbound mail sent from Office 365. Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span>

<span data-ttu-id="f8cfc-p103">Ein SPF TXT-Eintrag ist ein DNS-Eintrag, der Ihnen hilft, Spoofing und Phishing zu verhindern, indem der Name der Domäne überprüft wird, von der aus E-Mail-Nachrichten gesendet werden. SPF überprüft den Ursprung von E-Mails, indem die IP-Adresse des Absenders mit dem vorgeblichen Besitzer der Absenderdomäne verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p103">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="f8cfc-p104">SPF-Eintragstypen wurden von der Internet Engineering Task Force (IETF) 2014 als veraltet eingestuft. Stellen Sie stattdessen sicher, dass Sie zum Veröffentlichen von SPF-Informationen TXT-Einträge in DNS verwenden. Der Rest dieses Artikels verwendet aus Gründen der Klarheit den Begriff SPF TXT-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p104">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="f8cfc-114">Domänenadministratoren veröffentlichen SPF-Informationen in TXT-Einträgen in DNS.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-114">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="f8cfc-115">Durch die SPF-Informationen werden autorisierte Server für ausgehende E-Mails identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-115">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="f8cfc-116">Von Ziel-E-Mail-Systemen wird überprüft, ob die Nachrichten von autorisierten Servern für ausgehende E-Mails stammen.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-116">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="f8cfc-117">Wenn Sie bereits mit SPF vertraut sind oder über eine einfache Bereitstellung verfügen und nur wissen möchten, was Sie in Ihren SPF TXT-Eintrag in DNS für Office 365 einschließen müssen, können Sie zu [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) wechseln.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-117">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="f8cfc-118">Wenn Ihre Bereitstellung nicht vollständig in Office 365 gehostet wird, oder wenn Sie weitere Informationen zur Funktionsweise von SPF oder zur Problembehandlung von SPF für Office 365 benötigen, lesen Sie hier weiter.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-118">If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="f8cfc-119">Zuvor mussten Sie einen anderen SPF TXT-Eintrag zu Ihrer benutzerdefinierten Domäne hinzufügen, wenn Sie auch SharePoint Online verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-119">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="f8cfc-120">Dies ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-120">This is no longer required.</span></span> <span data-ttu-id="f8cfc-121">Diese Änderung sollte das Risiko reduzieren, dass SharePoint Online-Benachrichtigungsnachrichten im Junk-E-Mail-Ordner landen.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-121">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="f8cfc-122">Sie müssen keine Änderungen sofort vornehmen, aber wenn Sie den Fehler "zu viele Nachschlagevorgänge" erhalten, ändern Sie Ihren SPF TXT-Eintrag wie unter Einrichten von [SPF in Office 365 beschrieben, um Spoofing zu verhindern](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-122">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="f8cfc-123">Funktionsweise von SPF zur Verhinderung von Spoofing und Phishing in Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="f8cfc-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-124"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="f8cfc-p107">SPF ermittelt, ob ein Absender im Auftrag einer Domäne senden darf. Wenn der Absender dazu nicht berechtigt ist, wenn die E-Mail also die SPF-Prüfung auf dem empfangenden Server nicht besteht, ermittelt die Spamrichtlinie, die auf diesem Server konfiguriert ist, was mit der Nachricht geschieht.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p107">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="f8cfc-p108">Jeder SPF TXT-Eintrag enthält drei Teile: die Deklaration, dass es sich um einen SPF TXT-Eintrag handelt, die IP-Adressen, die berechtigt sind, E-Mail-Nachrichten aus Ihrer Domäne zu senden, und die externen Domänen, die im Auftrag Ihrer Domäne senden können, sowie eine Regel für die Durchsetzung. Sie benötigen alle drei in einem gültigen SPF TXT-Eintrag. In diesem Artikel wird beschrieben, wie Sie Ihren SPF TXT-Eintrag erstellen. Außerdem werden bewährte Methoden für die Arbeit mit den Diensten in Office 365 bereitgestellt. Auch Links zu Anweisungen für die Arbeit mit Ihrer Domänenregistrierungsstelle zum Veröffentlichen Ihres Eintrags in DNS werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p108">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule. You need all three in a valid SPF TXT record. This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365. Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="f8cfc-131">SPF-Grundlagen: IP-Adressen, die von Ihrer benutzerdefinierten Domäne aus senden dürfen</span><span class="sxs-lookup"><span data-stu-id="f8cfc-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="f8cfc-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-132"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="f8cfc-133">Sehen Sie sich die allgemeine Syntax für eine SPF-Regel an:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-133">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="f8cfc-134">v=spf1 \<IP\> \<Durchsetzungsregel\></span><span class="sxs-lookup"><span data-stu-id="f8cfc-134">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="f8cfc-135">Nehmen wir z. B. an, dass die folgende SPF-Regel für „contoso.com" vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="f8cfc-136">v=spf1 \<IP-Adresse #1\> \<IP-Adresse #2\> \<IP-Adresse #3\> \<Durchsetzungsregel\></span><span class="sxs-lookup"><span data-stu-id="f8cfc-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="f8cfc-137">In diesem Beispiel weist die SPF-Regel den empfangenden E-Mail-Server an, nur E-Mail-Nachrichten von diesen IP-Adressen für die Domäne „contoso.com" zu akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="f8cfc-138">IP-Adresse #1</span><span class="sxs-lookup"><span data-stu-id="f8cfc-138">IP address #1</span></span>

- <span data-ttu-id="f8cfc-139">IP-Adresse #2</span><span class="sxs-lookup"><span data-stu-id="f8cfc-139">IP address #2</span></span>

- <span data-ttu-id="f8cfc-140">IP-Adresse #3</span><span class="sxs-lookup"><span data-stu-id="f8cfc-140">IP address #3</span></span>

<span data-ttu-id="f8cfc-p109">Diese SPF-Regel weist den empfangenden E-Mail-Server an, dass er, wenn eine Nachricht von „contoso.com", aber nicht von einer dieser drei IP-Adressen kommt, die Durchsetzungsregel auf die Nachricht anwenden soll. Die Durchsetzungsregel bietet normalerweise eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p109">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="f8cfc-p110">**Hard fail** (schwerer Fehler). Markieren Sie die Nachricht mit „Hard fail" im Nachrichtenumschlag, und folgen Sie dann der konfigurierten Spamrichtlinie des empfangenden Server für diese Art von Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p110">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="f8cfc-p111">**Soft fail** (nicht schwerwiegender Fehler). Markieren Sie die Nachricht mit „Soft fail" im Nachrichtenumschlag. E-Mail-Server sind in der Regel so konfiguriert, dass diese Nachrichten trotzdem übermittelt werden. Die meisten Endbenutzer sehen diese Markierung nicht.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p111">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="f8cfc-p112">**Neutral.** Keine Aktion, d. h. markieren Sie den Nachrichtenumschlag nicht. Dies ist normalerweise für Testzwecke reserviert und wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p112">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="f8cfc-p113">Die folgenden Beispiele zeigen, wie SPF in unterschiedlichen Situationen funktioniert. In diesen Beispielen ist „contoso.com“ der Absender und „woodgrovebank.com“ der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p113">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="f8cfc-154">Beispiel 1: E-Mail-Authentifizierung einer Nachricht, die direkt vom Absender an den Empfänger gesendet wird</span><span class="sxs-lookup"><span data-stu-id="f8cfc-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="f8cfc-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-155"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="f8cfc-156">SPF funktioniert am besten, wenn der Pfad vom Absender zum Empfänger direkt ist, z. B.:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![Diagramm, in dem gezeigt wird, wie SPF E-Mails authentifiziert, wenn diese direkt von Server zu Server gesendet werden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="f8cfc-158">Wenn „woodgrovebank.com“ die Nachricht empfängt, wenn IP-Adresse #1 im SPF TXT-Eintrag für „contoso.com“ vorhanden ist, besteht die Meldung die SPF-Prüfung und wird authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="f8cfc-159">Beispiel 2: Gefälschte Absenderadresse besteht die SPF-Prüfung nicht</span><span class="sxs-lookup"><span data-stu-id="f8cfc-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="f8cfc-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-160"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="f8cfc-161">Nehmen wir an, ein Phisher findet eine Möglichkeit zum Spoofing in „contoso.com":</span><span class="sxs-lookup"><span data-stu-id="f8cfc-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![Diagramm, in dem gezeigt wird, wie SPF E-Mails authentifiziert, wenn diese von einem gefälschten Server gesendet werden.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="f8cfc-163">Da die IP-Adresse #12 nicht im SPF TXT-Eintrag von „contoso.com" enthalten ist, besteht die Meldung die SPF-Prüfung nicht, und der Empfänger kann sie als Spam markieren.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="f8cfc-164">Beispiel 3: SPF und weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f8cfc-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="f8cfc-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-165"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="f8cfc-p114">Ein Nachteil von SPF liegt darin, dass es nicht funktioniert, wenn eine E-Mail-Nachricht weitergeleitet wurde. Nehmen Sie beispielsweise an, dass der Benutzer in „woodgrovebank.com" eine Weiterleitungsregel eingerichtet hat, um alle E-Mail-Nachrichten an ein „outlook.com"-Konto zu senden:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p114">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![Diagramm, in dem gezeigt wird, dass SPF E-Mails nicht authentifizieren kann, wenn die Nachricht weitergeleitet wird.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="f8cfc-p115">Die Nachricht besteht ursprünglich die SPF-Prüfung von „woodgrovebank.com", besteht aber nicht die SPF-Prüfung von „outlook.com", da IP-Adresse #25 nicht im SPF TXT-Eintrag von „contoso.com" vorhanden ist. „Outlook.com" kann dann die Nachricht als Spam markieren. Um dieses Problem zu umgehen, verwenden Sie SPF in Verbindung mit anderen E-Mail-Authentifizierungsmethoden, z. B. DKIM und DMARC.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p115">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="f8cfc-172">SPF-Grundlagen: Einschließlich von Drittanbieterdomänen, die E-Mails im Auftrag Ihrer Domäne senden können</span><span class="sxs-lookup"><span data-stu-id="f8cfc-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="f8cfc-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-173"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="f8cfc-p116">Zusätzlich zu den IP-Adressen können Sie auch Ihren SPF TXT-Eintrag zum Einschließen von Domänen als Absender konfigurieren. Diese werden als dem SPF TXT-Eintrag als „include"-Anweisungen hinzugefügt. „contoso.com" möchte beispielsweise alle IP-Adressen der E-Mail-Server aus „contoso.net" und „contoso.org", die es auch besitzt, einschließen. Zu diesem Zweck veröffentlicht „contoso.com" einen SPF TXT-Eintrag, der etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p116">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="f8cfc-178">Wenn der empfangende Server diesen Eintrag in DNS sieht, führt er auch eine DNS-Suche für den SPF TXT-Eintrag für contoso.net und dann für contoso.org aus. Wenn eine zusätzliche include-Anweisung in den Datensätzen für contoso.net oder contoso.org gefunden wird, werden diese ebenfalls befolgt.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-178">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="f8cfc-179">Um DOS-Angriffe zu verhindern, beträgt die maximale Anzahl von DNS-Suchen für eine einzelne E-Mail-Nachricht 10.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-179">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="f8cfc-180">Jede „include“-Anweisung stellt eine zusätzliche DNS-Suche dar.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-180">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="f8cfc-181">Wenn eine Nachricht das Limit von 10 überschreitet, schlägt die Nachricht für SPF fehl.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-181">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="f8cfc-182">Sobald eine Nachricht diesen Grenzwert erreicht hat, kann der Absender abhängig von der Konfiguration des empfangenden Servers eine Meldung erhalten, die besagt, dass die Nachricht "zu viele Nachschlagevorgänge" generiert wurde oder dass die maximale Anzahl von Hops für die Nachricht überschritten wurde (was passieren kann, wenn die Lookups-Schleife und überschreitet das DNS-Timeout).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-182">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="f8cfc-183">Tipps, zum Vermeiden dieses Problems finden Sie unter [Problembehandlung: Bewährte Methoden für SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-183">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="f8cfc-184">Anforderungen für Ihren SPF TXT-Eintrag und Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="f8cfc-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-185"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="f8cfc-p118">Wenn Sie E-Mail zusammen mit Office 365 eingerichtet haben, wurde bereits ein SPF-Eintrag erstellt, der die Microsoft-Messagingserver als rechtmäßige E-Mail-Quelle für Ihre Domäne identifiziert. Dieser Eintrag sieht wahrscheinlich wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p118">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain. This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="f8cfc-188">Wenn Sie ein vollständig gehosteter Office 365-Kunde sind, d. h., Sie haben keine lokalen E-Mail-Server, die ausgehende E-Mails senden, ist dies der einzige SPF TXT-Eintrag, den Sie für Office 365 veröffentlichen müssen.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="f8cfc-189">Wenn Sie eine Hybridbereitstellung haben (d. h. einige Postfächer lokal und einige in Office 365 hosten), oder wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde sind (d. h. Ihre Organisation verwendet EOP zum Schutz Ihrer lokalen Postfächer), sollten Sie die ausgehende IP-Adresse für jeden Ihrer lokalen Edge-E-Mail-Server zum SPF TXT-Eintrag in DNS hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="f8cfc-190">Erstellen Ihres SPF TXT-Eintrags für Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="f8cfc-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-191"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="f8cfc-p119">Verwenden Sie die Syntaxinformationen in diesem Artikel, um den SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne zu erstellen. Obwohl es auch andere Optionen gibt, die hier nicht genannt werden, sind dies die am häufigsten verwendeten Syntaxoptionen. Nachdem Sie Ihren Eintrag erstellt haben, müssen Sie den Eintrag bei Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p119">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="f8cfc-195">Informationen zu den Domänen, die Sie für Office 365 einschließen müssen, finden Sie unter [Für SPF erforderliche externe DNS-Einträge](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-195">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="f8cfc-196">Verwenden Sie die [schrittweisen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) zur Aktualisierung von SPF (TXT)-Einträgen für Ihre Domänenregistrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-196">Use the [step-by-step instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="f8cfc-197">Syntax des SPF TXT-Eintrags für Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-197">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="f8cfc-198"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-198"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="f8cfc-199">Ein typischer SPF TXT-Eintrag für Office 365 weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-199">A typical SPF TXT record for Office 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="f8cfc-200">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-200">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="f8cfc-201">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-201">where:</span></span>

- <span data-ttu-id="f8cfc-p121">**v=spf1** ist erforderlich. Dies definiert den TXT-Eintrag als SPF TXT-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p121">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="f8cfc-p122">**ip4** gibt an, dass Sie IP-Adressen der Version 4 verwenden. **ip6** gibt an, dass Sie IP-Adressen der Version 6 verwenden. Wenn Sie IPv6-IP-Adressen verwenden, ersetzen Sie in den Beispielen in diesem Artikel **ip4** durch **ip6**. Sie können auch IP-Adressbereiche in CIDR-Schreibweise angeben, z. B. **ip4:192.168.0.1/26**.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p122">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="f8cfc-p123">_IP address_ ist die IP-Adresse, die Sie dem SPF TXT-Eintrag hinzufügen möchten. Normalerweise ist dies die IP-Adresse des Servers für ausgehende E-Mails für Ihre Organisation. Sie können mehrere ausgehende Mailserver auflisten. Weitere Informationen finden Sie unter [Beispiel: SPF TXT-Eintrag für mehrere ausgehende lokale E-Mail-Server und Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p123">_IP address_ is the IP address that you want to add to the SPF TXT record. Usually, this is the IP address of the outbound mail server for your organization. You can list multiple outbound mail servers. For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="f8cfc-p124">_domain name_ ist die Domäne, die Sie als legitimen Absender hinzufügen möchten. Eine Liste der Domänen, die Sie für Office 365 einschließen sollten, finden Sie unter [Für SPF erforderliche externe DNS-Einträge](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p124">_domain name_ is the domain you want to add as a legitimate sender. For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span>

- <span data-ttu-id="f8cfc-214">Die Durchsetzungsregel bietet normalerweise eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-214">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="f8cfc-215">-all</span><span class="sxs-lookup"><span data-stu-id="f8cfc-215">-all</span></span>

    <span data-ttu-id="f8cfc-p125">Zeigt einen schweren Fehler an. Wenn Sie alle autorisierten IP-Adressen für Ihre Domäne kennen, listen Sie diese im SPF TXT-Eintrag auf, und verwenden Sie die Option „-all“ (schwerer Fehler). Wenn Sie nur SPF verwenden, wenn sie also weder DMARC noch DKIM verwenden, sollten Sie ebenfalls die Option „-all“ verwenden. Es wird empfohlen, immer diese Option zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p125">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="f8cfc-220">~all</span><span class="sxs-lookup"><span data-stu-id="f8cfc-220">~all</span></span>

    <span data-ttu-id="f8cfc-p126">Zeigt einen nicht schwerwiegenden Fehler an. Wenn Sie nicht sicher sind, ob Sie die vollständige Liste der IP-Adressen haben, sollten Sie die Option „~all" (nicht schwerwiegender Fehler) verwenden. Auch bei Verwendung von DMARC mit „p=quarantine" oder „p=reject" können Sie „~all" verwenden. Verwenden Sie andernfalls „-all".</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p126">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>

  - <span data-ttu-id="f8cfc-225">?all</span><span class="sxs-lookup"><span data-stu-id="f8cfc-225">?all</span></span>

    <span data-ttu-id="f8cfc-p127">Zeigt neutral an. Wird verwendet, um SPF zu testen. Wir empfehlen nicht, diese Option in Ihrer Livebereitstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p127">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="f8cfc-229">Beispiel: Zu verwendender SPF TXT-Eintrag, wenn alle Ihre E-Mail-Nachrichten von Office 365 gesendet werden</span><span class="sxs-lookup"><span data-stu-id="f8cfc-229">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="f8cfc-230"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-230"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="f8cfc-231">Wenn alle Ihre E-Mail-Nachrichten von Office 365 gesendet werden, verwenden Sie Folgendes in Ihrem SPF TXT-Eintrag:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-231">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="f8cfc-232">Beispiel: SPF TXT-Eintrag für ein Hybridszenario mit einem lokalen Exchange-Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-232">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="f8cfc-233"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-233"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="f8cfc-234">Wenn in einer Hybridumgebung die IP-Adresse des lokalen Exchange-Servers „192.168.0.1“ lautet, um die SPF-Durchsetzungsregel auf einen schweren Fehler festzulegen, erstellen Sie den SPF TXT-Eintrag wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-234">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="f8cfc-235">Beispiel: SPF TXT-Eintrag für mehrere ausgehende lokale E-Mail-Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-235">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="f8cfc-236"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-236"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="f8cfc-p128">Wenn Sie über mehrere ausgehende E-Mail-Server verfügen, schließen Sie die IP-Adresse für jeden E-Mail-Server in den SPF TXT-Eintrag ein, und trennen Sie die IP-Adressen mit einem Leerzeichen, gefolgt von „ip4:". Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p128">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="f8cfc-239">Nächste Schritte: Einrichten von SPF für Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-239">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="f8cfc-240"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-240"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="f8cfc-241">Nachdem Sie den SPF TXT-Eintrag erstellt haben, führen Sie die Schritte in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) durch, um ihn Ihrer Domäne hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-241">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="f8cfc-p129">Obwohl SPF Spoofing verhindern soll, gibt es Spoofingtechniken, gegen die SPF nicht schützen kann. Zum Einrichten eines entsprechenden Schutzes sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren. Die ersten Schritte finden Sie unter [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md). Lesen Sie anschließend [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p129">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="f8cfc-246">Problembehandlung: Bewährte Methoden für SPF in Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-246">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="f8cfc-247"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-247"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="f8cfc-p130">Sie dürfen nur einen SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne erstellen. Das Erstellen von mehreren Einträgen führt zu einer Roundrobin-Situation, und SPF verursacht einen Fehler. Um dies zu vermeiden, können Sie separate Einträge für jede Unterdomäne erstellen. Erstellen Sie z. B. einen Eintrag für „contoso.com" und einen anderen für „bulkmail.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p130">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="f8cfc-p131">Wenn eine E-Mail-Nachricht mehr als 10 DNS-Suchvorgänge verursacht, bevor sie zugestellt wird, antwortet der empfangende E-Mail-Server mit einem permanenten Fehler, der auch als  _permerror_ bezeichnet wird und dazu führt, dass die Nachricht die SPF-Prüfung nicht besteht. Der empfangende Server kann auch mit einem Unzustellbarkeitsbericht (NDR) antworten, der eine Fehlermeldung ähnlich der folgenden enthält:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p131">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="f8cfc-254">Die Nachricht hat die Hop-Anzahl überschritten.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-254">The message exceeded the hop count.</span></span>

- <span data-ttu-id="f8cfc-255">Die Nachricht hat zu viele Suchvorgänge benötigt.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-255">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="f8cfc-256">Vermeiden der Fehlermeldung "zu viele Suchvorgänge" bei der Verwendung von Drittanbieterdomänen mit Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cfc-256">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="f8cfc-257"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-257"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="f8cfc-p132">Einige SPF TXT-Einträge für Drittanbieterdomänen weisen den empfangenden Server an, eine große Anzahl von DNS-Suchvorgängen auszuführen. „salesforce.com" enthält z. B. zum Zeitpunkt der Erstellung dieses Dokuments im Eintrag fünf „include"-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p132">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="f8cfc-p133">Um den Fehler zu vermeiden, können Sie eine Richtlinie implementieren, bei der jeder, der z. B. Massen-E-Mails sendet, eine speziell für diesen Zweck eingerichtete Unterdomäne verwenden muss. Dann definieren Sie einen unterschiedlichen SPF TXT-Eintrag für die Unterdomäne, die die Massen-E-Mails enthält.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p133">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="f8cfc-p134">In einigen Fällen, wie im Beispiel „salesforce.com", müssen Sie die Domäne in Ihrem SPF TXT-Eintrag verwenden, aber in anderen Fällen hat der Drittanbieter möglicherweise bereits eine Unterdomäne erstellt, die Sie zu diesem Zweck verwenden können. „exacttarget.com" hat beispielsweise eine Unterdomäne erstellt, die Sie für Ihren SPF TXT-Eintrag verwenden müssen:</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p134">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="f8cfc-264">Wenn Sie in Ihren SPF TXT-Eintrag Drittanbieterdomänen einschließen, müssen Sie mit dem Drittanbieter absprechen, welche Domäne oder Unterdomäne verwendet werden soll, um das Erreichen des Limits der 10 Suchvorgänge zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-264">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="f8cfc-265">Anzeigen des aktuellen SPF TXT-Eintrags und Ermitteln der benötigten Anzahl der Suchvorgänge</span><span class="sxs-lookup"><span data-stu-id="f8cfc-265">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="f8cfc-266"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-266"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="f8cfc-p135">Sie können nslookup zum Anzeigen der DNS-Einträge verwenden, einschließlich des SPF TXT-Eintrags. Es gibt aber auch eine Reihe von kostenlosen Tools, die Sie verwenden können, um den Inhalt Ihres SPF TXT-Eintrags anzuzeigen. Durch das Überprüfen des SPF TXT-Eintrags und durch Folgen der Kette der „include"-Anweisungen und -Umleitungen können Sie ermitteln, wie viele DNS-Suchvorgänge für den Eintrag erforderlich sind. Einige Onlinetools können diese Suchvorgänge sogar zählen und anzeigen. Das Überwachen dieser Anzahl verhindert, dass Nachrichten, die von Ihrer Organisation gesendet werden, auf dem empfangenden Server einen permanenten Fehler auslösen, der auch als permerror bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-p135">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f8cfc-272">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8cfc-272">For more information</span></span>
<span data-ttu-id="f8cfc-273"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cfc-273"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="f8cfc-274">Benötigen Sie Hilfe beim Hinzufügen des SPF-TXT-Eintrags?</span><span class="sxs-lookup"><span data-stu-id="f8cfc-274">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="f8cfc-275">Lesen Sie den Artikel [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) ausführliche Informationen zur Verwendung von Sender Policy Framework mit Ihrer benutzerdefinierten Domäne in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-275">Read the article [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Office 365.</span></span> <span data-ttu-id="f8cfc-276">[Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) umfasst die Syntax- und Kopfzeilenfelder, die von Office 365 für SPF-Überprüfungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8cfc-276">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span>


