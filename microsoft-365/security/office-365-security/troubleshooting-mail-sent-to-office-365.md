---
title: Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: Dieser Artikel enthält Informationen zur Problembehandlung für Absender, die Probleme haben, E-Mails an Postfächer in Office 365 zu senden, und bewährte Methoden für Massenmailings an Office 365-Kunden.
ms.openlocfilehash: 59c02b31b759870892846947940744e123c73788
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441182"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="b1363-103">Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden</span><span class="sxs-lookup"><span data-stu-id="b1363-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="b1363-104">Dieser Artikel enthält Informationen zur Problembehandlung für Absender, die Probleme haben, E-Mails an Postfächer in Office 365 zu senden, und bewährte Methoden für Massenmailings an Office 365-Kunden.</span><span class="sxs-lookup"><span data-stu-id="b1363-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="b1363-105">Problembehandlung bei häufig auftretenden Probleme mit E-Mail-Übermittlung an Office 365</span><span class="sxs-lookup"><span data-stu-id="b1363-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="b1363-106">Wählen Sie aus den folgenden häufig auftretenden Problemen.</span><span class="sxs-lookup"><span data-stu-id="b1363-106">Choose from one of these commonly encountered issues.</span></span>

- [<span data-ttu-id="b1363-107">Verwalten Sie die Sendezuverlässigkeit Ihrer IP-Adresse und Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="b1363-107">Are you managing your IP and domain's sending reputation?</span></span>](#are-you-managing-your-ip-and-domains-sending-reputation)

- [<span data-ttu-id="b1363-108">Senden Sie E-Mails von neuen IP-Adressen?</span><span class="sxs-lookup"><span data-stu-id="b1363-108">Are you sending email from new IP addresses?</span></span>](#are-you-sending-email-from-new-ip-addresses)

- [<span data-ttu-id="b1363-109">Bestätigen, dass Ihr DNS ordnungsgemäß eingerichtet ist</span><span class="sxs-lookup"><span data-stu-id="b1363-109">Confirm that your DNS is set up correctly</span></span>](#confirm-that-your-dns-is-set-up-correctly)

- [<span data-ttu-id="b1363-110">Stellen Sie sicher, dass Sie sich selbst nicht als nicht routbare IP-Adresse bewerben.</span><span class="sxs-lookup"><span data-stu-id="b1363-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [<span data-ttu-id="b1363-111">Sie haben einen Unzustellbarkeitsbericht (NDR) beim Senden von E-Mails an einen Benutzer in Office 365 erhalten.</span><span class="sxs-lookup"><span data-stu-id="b1363-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [<span data-ttu-id="b1363-112">Meine E-Mails sind im Junk-Ordner des Empfängers in EOP gelandet.</span><span class="sxs-lookup"><span data-stu-id="b1363-112">My email landed in the recipient's junk folder in EOP</span></span>](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [<span data-ttu-id="b1363-113">Datenverkehr von meiner IP-Adresse wird durch EOP beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b1363-113">Traffic from my IP address is throttled by EOP</span></span>](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="b1363-114">Verwalten Sie die Sendezuverlässigkeit Ihrer IP-Adresse und Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="b1363-114">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="b1363-p101">EOP-Filtertechnologien sollen Anti-Spam-Schutz für Microsoft Office 365 sowie andere Microsoft-Produkte wie Exchange Server, Microsoft Office Outlook und Windows Live Mail bereitstellen. Wir nutzen auch SPF, DKIM und DMARC; E-Mail-Authentifizierungstechnologien, mit denen das Problem des Spoofings und Phishings durch Überprüfen, ob die Domäne, die die E-Mail sendet, dazu berechtigt ist, gelöst werden kann. EOP-Filter werden von einer Reihe von Faktoren der sendenden IP-Adresse, Domäne, Authentifizierung, Listengenauigkeit, Beschwerdehäufigkeit, Inhalte und mehr beeinflusst. Einer der wichtigsten Faktoren ist das Reduzieren der Absenderzuverlässigkeit und der Möglichkeit der E-Mail-Zustellung durch die Junk-E-Mail-Beschwerdehäufigkeit. </span><span class="sxs-lookup"><span data-stu-id="b1363-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="b1363-119">Senden Sie E-Mails von neuen IP-Adressen?</span><span class="sxs-lookup"><span data-stu-id="b1363-119">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="b1363-p102">IP-Adressen, die bisher nicht verwendet wurden, um E-Mails zu senden, verfügen in der Regel in unseren Systemen über keinerlei Zuverlässigkeitswertung. Dementsprechend gibt es bei E-Mails von neuen IP-Adressen eher Übermittlungsprobleme. Nachdem die IP-Adresse eine gewisse Zuverlässigkeit aufgebaut hat, da kein Spam gesendet wurde, lässt EOP in der Regel eine bessere E-Mail-Übermittlung zu.</span><span class="sxs-lookup"><span data-stu-id="b1363-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="b1363-p103">Neue IP-Adressen, die für Domänen hinzugefügt werden, die unter den vorhandenen SPF-Einträgen authentifiziert werden, haben in der Regel den Vorteil, einen Teil der Sendezuverlässigkeit der Domäne zu erben. Hat Ihre Domäne eine gute Sendezuverlässigkeit, wird er Vorgang bei neuen IP-Adressen möglicherweise beschleunigt. Eine neue IP-Adresse kann innerhalb von zwei Wochen oder früher – je nach Volumen, Listengenauigkeit und Junk-E-Mail-Beschwerdehäufigkeit – als zuverlässig anerkannt werden.</span><span class="sxs-lookup"><span data-stu-id="b1363-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="b1363-126">Bestätigen, dass Ihr DNS ordnungsgemäß eingerichtet ist</span><span class="sxs-lookup"><span data-stu-id="b1363-126">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="b1363-127">Anweisungen zum Erstellen und Verwalten von DNS-Einträgen, einschließlich des MX-Eintrags für E-Mail-Weiterleitung, erhalten Sie von Ihrem DNS-Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="b1363-127">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="b1363-128">Stellen Sie sicher, dass Sie sich selbst nicht als nicht routbare IP-Adresse bewerben.</span><span class="sxs-lookup"><span data-stu-id="b1363-128">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="b1363-p104">Wir akzeptieren möglicherweise keine E-Mail-Nachrichten von Absendern, für die eine Reverse-DNS-Suche fehlschlägt. In einigen Fällen bewerben sich seriöse Absender fälschlicherweise als nicht routbare IP-Adresse bei dem Versuch, eine Verbindung zu EOP zu öffnen. IP-Adressen, die für private (nicht routbare) Netzwerke reserviert sind, enthalten:</span><span class="sxs-lookup"><span data-stu-id="b1363-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="b1363-132">192.168.0.0/16 (oder 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="b1363-132">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="b1363-133">10.0.0.0/8 (oder 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="b1363-133">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="b1363-134">172.16.0.0/11 (oder 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="b1363-134">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="b1363-135">Sie haben einen Unzustellbarkeitsbericht erhalten, wenn Sie e-Mails an einen Benutzer in Office 365 senden.</span><span class="sxs-lookup"><span data-stu-id="b1363-135">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="b1363-p105">Einige Probleme bei der Übermittlung sind das Ergebnis der IP-Adresse des Absenders, die von Microsoft blockiert wird, oder weil das Benutzerkonto als gesperrter Absender aufgrund von vorherigen Spam-Aktivitäten identifiziert wird. Wenn Sie glauben, dass Sie den NDR irrtümlich erhalten haben, führen Sie zunächst alle Anweisungen in der NDR-Nachricht aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b1363-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="b1363-138">Weitere Informationen zu dem Fehler, den Sie erhalten haben, finden Sie in der vollständigen Liste der SMTP-Fehlercodes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1363-138">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>

 <span data-ttu-id="b1363-139">Wenn Sie z. B. den folgenden Unzustellbarkeitsbericht erhalten haben, wurde die IP-Adresse des Absenders wahrscheinlich durch Microsoft blockiert.</span><span class="sxs-lookup"><span data-stu-id="b1363-139">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="b1363-140">Um die Entfernung aus dieser Liste anzufordern, können Sie wie folgt vorgehen: [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="b1363-140">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="b1363-141">Meine E-Mails sind im Junk-Ordner des Empfängers in EOP gelandet.</span><span class="sxs-lookup"><span data-stu-id="b1363-141">My email landed in the recipient's junk folder in EOP</span></span>

<span data-ttu-id="b1363-p106">Falls eine Nachricht fälschlicherweise von EOP als Spam identifiziert wurde, können Sie diese falsch positive Nachricht zusammen mit dem Empfänger an das Microsoft-Spamanalyseteam weiterleiten, das die Nachricht bewertet und untersucht. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann. Sie können Nachrichten, die nicht als Spam klassifiziert werden sollen, per E-Mail an Microsoft weiterleiten. Gehen Sie dabei wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="b1363-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="b1363-146">So verwenden Sie eine E-Mail, um falsch positive Nachrichten an das Microsoft-Spamanalyseteam zu senden</span><span class="sxs-lookup"><span data-stu-id="b1363-146">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="b1363-147">Speichern Sie die an Microsoft zu sendende Nachricht als Nicht-Spamnachricht.</span><span class="sxs-lookup"><span data-stu-id="b1363-147">Save the message you want to submit as non-spam.</span></span>

2. <span data-ttu-id="b1363-148">Erstellen Sie eine neue, leere Nachricht und hängen die Nichtspamnachricht an.</span><span class="sxs-lookup"><span data-stu-id="b1363-148">Create a new, blank message and attach the non-spam message to it.</span></span>

    <span data-ttu-id="b1363-149">Sie können bei Bedarf mehrere Nicht-Spamnachrichten anhängen.</span><span class="sxs-lookup"><span data-stu-id="b1363-149">You can attach multiple non-spam messages if needed.</span></span>

3. <span data-ttu-id="b1363-150">Kopieren Sie den Betreff der ursprünglichen Nachricht, und fügen Sie ihn in den Betreff der neuen Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="b1363-150">Copy and paste the original message subject line into the new message subject line.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b1363-151">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="b1363-151">Leave the body of the new message empty.</span></span>

4. <span data-ttu-id="b1363-152">Senden Sie Ihre neue Nachricht an [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b1363-152">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="b1363-153">Datenverkehr von meiner IP-Adresse wird durch EOP beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b1363-153">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="b1363-154">Wenn Sie einen Unzustellbarkeitsbericht von EOP erhalten, der angibt, dass Ihre IP-Adresse von EOP beschränkt wird, z. B.:</span><span class="sxs-lookup"><span data-stu-id="b1363-154">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="b1363-p107">Sie haben einen NDR erhalten, da an der betreffenden IP-Adresse eine verdächtige Aktivität erfasst. Die IP-Adresse wurde vorübergehend beschränkt, solange sie weiter ausgewertet wird. Wenn der Verdacht durch Bewertung aufgelöst wird, wird diese Einschränkung in Kürze aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b1363-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="b1363-157">Ich kann keine E-Mails von Absendern in Office 365 erhalten.</span><span class="sxs-lookup"><span data-stu-id="b1363-157">I can't receive email from senders in Office 365</span></span>

 <span data-ttu-id="b1363-158">Damit Sie Nachrichten von unseren Benutzern empfangen können, muss Ihr Netzwerk Verbindungen von den IP-Adressen zulassen, die EOP in unseren Rechenzentren verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1363-158">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="b1363-159">Weitere Informationen finden Sie unter [Exchange Online Protection IP addresses](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="b1363-159">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="b1363-160">Bewährte Methoden für Massen-E-Mails an Office 365-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b1363-160">Best practices for bulk emailing to Office 365 users</span></span>

<span data-ttu-id="b1363-161">Wenn Sie häufig Massen-E-Mail-Kampagnen für Benutzer von Office 365 durchführen und sicherstellen möchten, dass Ihre E-Mails sicher und zeitnah eintreffen, folgen Sie den Tipps in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1363-161">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="b1363-162">Stellen Sie sicher, dass der Name unter „Von:“ angibt, wer die Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="b1363-162">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="b1363-p109">Der Betreff sollte eine kurze Zusammenfassung der Nachricht darstellen, und der Nachrichtentext sollte klar und eindeutig angeben, um was es beim Angebot, Dienst oder Produkt geht. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1363-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="b1363-165">Richtig:</span><span class="sxs-lookup"><span data-stu-id="b1363-165">Correct:</span></span>

> <span data-ttu-id="b1363-166">Von: Marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="b1363-166">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="b1363-167">Betreff: aktualisierter Katalog für die Weihnachtszeit!</span><span class="sxs-lookup"><span data-stu-id="b1363-167">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="b1363-168">Falsch:</span><span class="sxs-lookup"><span data-stu-id="b1363-168">Incorrect:</span></span>

> <span data-ttu-id="b1363-169">Von: someone@Outlook.com</span><span class="sxs-lookup"><span data-stu-id="b1363-169">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="b1363-170">Betreff: Kataloge</span><span class="sxs-lookup"><span data-stu-id="b1363-170">Subject: Catalogs</span></span>

<span data-ttu-id="b1363-171">Je einfacher Sie es den Benutzern machen, ihre Identität und Absichten zu erkennen, desto weniger Probleme haben Sie bei der Zustellung durch die meisten Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="b1363-171">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="b1363-172">Schließen Sie in Kampagnen-E-Mails immer eine Option zum Abbestellen ein.</span><span class="sxs-lookup"><span data-stu-id="b1363-172">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="b1363-p110">Marketing-E-Mails, insbesondere Newsletter, sollten immer eine Möglichkeit enthalten, zukünftige E-Mails abzubestellen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1363-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`

<span data-ttu-id="b1363-p111">Einige Absender fügen diese Option hinzu, indem Empfänger eine E-Mail-Nachricht an einen bestimmten Alias mit „Unsubscribe" im Betreff senden müssen. Das oben genannte Ein-Klick-Beispiel ist aber vorzuziehen. Wenn Sie sich dafür entscheiden, dass Empfänger eine E-Mail senden müssen, stellen Sie sicher, dass alle erforderlichen Felder bereits ausgefüllt sind, wenn sie auf den Link klicken.</span><span class="sxs-lookup"><span data-stu-id="b1363-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="b1363-178">Verwenden der doppelten Anmeldeoption für die Registrierung für Marketing-E-Mails oder Newsletter</span><span class="sxs-lookup"><span data-stu-id="b1363-178">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="b1363-p112">Die bewährte Methode der Branche wird empfohlen, wenn Ihr Unternehmen möchte, dass Benutzer ihre Kontaktinformationen registrieren, um auf das Produkt oder den Dienst zuzugreifen. In einigen Unternehmen werden Benutzer automatisch während der Registrierung für Marketing-E-Mails oder Newsletter angemeldet, was aber als fragliche Marketingmethode in der Welt der E-Mail-Filterung angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="b1363-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="b1363-181">Wenn während der Registrierung Kontrollkästchen wie „Ja, Newsletter senden" oder „Ja, Sonderangebote senden" standardmäßig aktiviert sind, können sich Benutzer, die nicht darauf achten, versehentlich für Marketing-E-Mails oder Newsletter anmelden, die sie nicht erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="b1363-181">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="b1363-p113">Es empfiehlt sich stattdessen die doppelte Anmeldeoption, was bedeutet, dass das Kontrollkästchen für Marketing-E-Mails oder Newsletter standardmäßig deaktiviert ist. Nachdem das Registrierungsformular gesendet wurde, wird zudem eine Überprüfungs-E-Mail mit einer URL an den Benutzer gesendet, die es ihm ermöglicht, seine Entscheidung für Marketing-E-Mails zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b1363-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="b1363-184">Dadurch wird sichergestellt, dass nur Benutzer, die Marketing-E-Mails erhalten möchten, für die E-Mail-Nachrichten angemeldet werden, und das sendende Unternehmen setzt keine fraglichen E-Mail-Marketingmethoden ein.</span><span class="sxs-lookup"><span data-stu-id="b1363-184">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="b1363-185">Sicherstellen, dass E-Mail-Nachrichteninhalte transparent und nachverfolgbar sind</span><span class="sxs-lookup"><span data-stu-id="b1363-185">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="b1363-p114">Der Inhalt von E-Mails ist genauso wichtig wie die Sendemethode. Beim Erstellen von E-Mail-Inhalt verwenden Sie die folgenden bewährten Methoden, um sicherzustellen, dass die E-Mails nicht durch E-Mail-Filterdienste gekennzeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="b1363-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="b1363-188">Wenn die E-Mail Empfänger dazu auffordert, den Absender zum Adressbuch hinzuzufügen, sollte deutlich darauf hingewiesen werden, dass dies keine Übermittlungsgarantie darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1363-188">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="b1363-p115">Weiterleitungen im Textkörper der Nachricht sollten ähnlich und konsistent sein, nicht zahlreich und unterschiedlich. Eine Weiterleitung ist in diesem Kontext etwas, das von der Nachricht wegführt, z. B. Links und Dokumente. Wenn Sie viele Werbe- oder Abbestellungslinks haben oder die Profillinks aktualisieren, sollten sie alle auf dieselbe Domäne verweisen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1363-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="b1363-193">Richtig:</span><span class="sxs-lookup"><span data-stu-id="b1363-193">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="b1363-194">Falsch:</span><span class="sxs-lookup"><span data-stu-id="b1363-194">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profiles.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="b1363-195">Senden Sie keine Inhalte mit großen Bilder oder Anlagen und keine Nachrichten, die nur aus einem Bild bestehen.</span><span class="sxs-lookup"><span data-stu-id="b1363-195">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="b1363-196">Ihre öffentlichen Datenschutz- oder P3P-Einstellungen sollten deutlich angeben, dass Sie Nachverfolgungspixel (Web-Bugs oder Beacons) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1363-196">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="b1363-197">Entfernen falscher E-Mail-Aliasnamen aus den Datenbanken</span><span class="sxs-lookup"><span data-stu-id="b1363-197">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="b1363-p116">Jeder E-Mail-Alias in der Datenbank, die eine Rücksendung auslöst, ist unnötig und kann dazu führen, dass Ihre ausgehenden E-Mails für weitere Analysen durch E-Mail-Filterdienste herangezogen werden. Stellen Sie sicher, dass Ihre E-Mail-Datenbank auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="b1363-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
