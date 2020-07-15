---
title: Verwenden von DMARC zum Überprüfen von E-Mails
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC) konfigurieren, um von Ihrer Organisation gesendete Nachrichten zu validieren.
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016321"
---
# <a name="use-dmarc-to-validate-email"></a>Verwenden von DMARC zum Überprüfen von E-Mails

[DMARC](https://dmarc.org) (Domain-based Message Authentication, Reporting, and Conformance) verwendet SPF (Sender Policy Framework) und DKIM (DomainKeys Identified Mail) zum Authentifizieren von E-Mail-Absendern, und um sicherzustellen, dass Ziel-E-Mail-Systeme die von Ihrer Domäne gesendeten E-Mail-Nachrichten als vertrauenswürdig einstufen. Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails. DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben.

> [!TIP]
> Besuchen Sie den [Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog)-Katalog, um zu sehen, welche Drittanbieter DMARC-Berichterstellung für Microsoft 365 bieten.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>Wie arbeiten SPF und DMARC zusammen, um E-Mails in Microsoft 365 zu schützen?

 Eine E-Mail-Nachricht kann mehrere Ersteller- oder Absenderadressen enthalten. Diese Adressen können für verschiedene Zwecke verwendet werden. Sehen Sie sich beispielsweise die folgenden Adressen an:

- Die **„Mail From“-Adresse** identifiziert den Absender und gibt an, wohin Hinweise zurückgesendet werden sollen, wenn Probleme bei der Übermittlung der Nachricht auftreten, z. B. Unzustellbarkeitsberichte. Sie erscheint im Umschlagbereich einer E-Mail-Nachricht und wird von der E-Mail-Anwendung in der Regel nicht angezeigt. Diese Adresse wird manchmal als „5321.MailFrom“- oder „reverse-path“-Adresse bezeichnet.

- **„Von"-Adresse**: die Adresse, die von der E-Mail-Anwendung als Absenderadresse angezeigt wird. Diese Adresse identifiziert den Autor der E-Mail. Das heißt, das Postfach der Person oder des Systems, das sich für das Schreiben der Nachricht verantwortlich zeichnet. Dies wird manchmal auch als 5322.From-Adresse bezeichnet.

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

In diesem Transkript lauten die Absenderadressen wie folgt:

- „E-Mail von“-Adresse (5321.MailFrom): phish@phishing.contoso.com

- „Von“-Adresse (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>Was ist ein DMARC-TXT-Eintrag?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Der DMARC-TXT-Eintrag von Microsoft sieht in etwa wie folgt aus:

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft sendet seine DMARC-Berichte an [Agari](https://agari.com), einen Drittanbieter. Agari erfasst und analysiert DMARC-Berichte. Besuchen Sie den [MISA-Katalog](https://www.microsoft.com/misapartnercatalog), um zu sehen, welche weiteren Drittanbieter DMARC-Berichterstellung für Microsoft 365 bieten.

## <a name="implement-dmarc-for-inbound-mail"></a>Implementieren von DMARC für eingehende E-Mail-Nachrichten

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Implementieren von DMARC für von Microsoft 365 ausgehende Nachrichten

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [Schritt 1: Identifizieren gültiger E-Mail-Nachrichtenquellen für Ihre Domäne](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Schritt 2: Einrichten von SPF für Ihre Domäne](#step-2-set-up-spf-for-your-domain)

- [Schritt 3: Einrichten von DKIM für Ihre benutzerdefinierte Domäne](#step-3-set-up-dkim-for-your-custom-domain)

- [Schritt 4: Erstellen des DMARC-TXT-Eintrags für Ihre Domäne](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Schritt 1: Identifizieren gültiger E-Mail-Nachrichtenquellen für Ihre Domäne

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- Welche IP-Adressen senden Nachrichten aus meiner Domäne?

- Was E-Mail-Nachrichten betrifft, die von Drittanbietern in meinem Auftrag gesendet werden: Stimmen die Domänen für „5321.MailFrom“ und „5322.From“ überein?

### <a name="step-2-set-up-spf-for-your-domain"></a>Schritt 2: Einrichten von SPF für Ihre Domäne

Sie haben nun eine Liste aller gültigen Absender erstellt und können die Schritte unter [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) befolgen.

Beispiel: Angenommen, „contoso.com" sendet E-Mail-Nachrichten von Exchange Online, einem lokalen Exchange-Server mit der IP-Adresse 192.168.0.1 und einer Webanwendung mit der IP-Adresse 192.168.100.100, dann sieht der SPF-TXT-Eintrag wie folgt aus:

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Es ist eine bewährte Methode sicherzustellen, dass Ihr SPF-TXT-Eintrag auch Absenderadressen von Drittanbietern berücksichtigt.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Schritt 3: Einrichten von DKIM für Ihre benutzerdefinierte Domäne

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Anleitungen zum Einrichten von DKIM für Ihre Domäne, einschließlich der Einrichtung von DKIM für Drittanbieter als Absender, die Ihre Domäne verwenden, finden Sie unter [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Schritt 4: Erstellen des DMARC-TXT-Eintrags für Ihre Domäne

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

Dabei gilt:

- *domain* ist die Domäne, die Sie schützen möchten. Standardmäßig schützt der Eintrag E-Mail-Nachrichten von dieser Domäne und allen Unterdomänen. Beispiel: Wenn Sie \_dmarc.contoso.com angeben, schützt DMARC E-Mail-Nachrichten der Domäne und aller Unterdomänen, wie z. B. „housewares.contoso.com“ oder „plumbing.contoso.com“.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* gibt an, dass diese Regel für alle E-Mail-Nachrichten (100 %) verwendet werden soll.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Um mehr darüber zu erfahren, welche Optionen Sie verwenden sollten, machen Sie sich mit den Konzepten unter [Bewährte Methoden zum Implementieren von DMARC in Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365) vertraut.

Beispiele:

- Richtlinie auf „none“ festgelegt

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Richtlinien auf „quarantine“ festgelegt

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Richtlinie auf „reject“ festgelegt

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Bewährte Methoden zum Implementieren von DMARC in Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Überwachen der Auswirkungen, die die Implementierung von DMARC hat

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. Anfordern, dass externe E-Mail-Systeme Nachrichten isolieren, die die DMARC-Prüfung nicht bestehen

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. Anfordern, dass externe E-Mail-Systeme keine Nachrichten akzeptieren, die die DMARC-Prüfung nicht bestehen

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>So behandelt Microsoft 365 ausgehende E-Mail-Nachrichten, die DMARC-Prüfungen nicht bestehen

Wenn eine Nachricht von Microsoft 365 gesendet wird (ausgehende Nachricht), die DMARC-Prüfung nicht besteht und Sie die Richtlinie „p=quarantine" oder „p=reject“ festgelegt haben, wird die Nachricht über den [Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md) weitergeleitet. Für ausgehende E-Mail-Nachrichten erfolgt keine Außerkraftsetzung.

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>So behandelt Microsoft 365 eingehende E-Mail-Nachrichten, die DMARC-Prüfungen nicht bestehen

Wenn die DMARC-Richtlinie des sendenden Servers `p=reject` lautet, kennzeichnet EOP die Nachricht als Spoof, anstatt sie abzulehnen. Mit anderen Worten, Microsoft 365 behandelt im Hinblick auf eingehende E-Mails `p=reject` und `p=quarantine` auf die gleiche Weise. Administratoren können die Aktion definieren, die auf Nachrichten, die in der [Anti-Phishing-Richtlinie](set-up-anti-phishing-policies.md) als Spoof klassifiziert werden, angewendet werden soll.

Microsoft 365 ist so konfiguriert, da einige autorisierte E-Mail-Nachrichten die DMARC-Prüfung möglicherweise nicht bestehen. Eine Nachricht besteht die DMARC-Prüfung zum Beispiel möglicherweise nicht, wenn sie an eine Mailingliste gesendet wird, die die Nachricht an alle Teilnehmer auf der Liste weiterleitet. Wenn Microsoft 365 diese Nachrichten ablehnen würde, könnten autorisierte E-Mail-Nachrichten für Benutzer verloren gehen, ohne dass die Benutzer sie auf andere Weise abrufen können. Diese Nachrichten bestehen die DMARC-Prüfung daher weiterhin nicht, werden jedoch als Spam gekennzeichnet und nicht abgelehnt. Falls gewünscht, können Benutzer diese Nachrichten immer noch anhand einer der folgenden Methoden in ihrem Posteingang erhalten:

- Die Benutzer fügen mithilfe des E-Mail-Clients sichere Absender einzeln hinzu.

- Administratoren können die [Spoofing Intelligence](learn-about-spoof-intelligence.md)-Berichterstellung so aktualisieren, dass Spoofing zulässig ist.

- Administratoren erstellen eine Exchange-E-Mail-Flussregel (auch bekannt als Transportregel) für alle Benutzer, die Nachrichten dieser bestimmten Absender zulassen.

Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>So verwendet Microsoft 365 ARC (Authenticated Received Chain)

Alle gehosteten Postfächer in Microsoft 365 profitieren nun von ARC mit besserer Zustellbarkeit von Nachrichten und verbessertem Antispoofingschutz. ARC bewahrt die Ergebnisse der E-Mail-Authentifizierung aller teilnehmenden Mittler bzw. Hops, wenn eine E-Mail vom ursprünglichen Server an das Empfängerpostfach geleitet wird. Von Mittlern im E-Mail-Routing vorgenommene Änderungen, z. B. Weiterleitungsregeln oder automatische Signaturen, konnten vor der Verwendung von ARC zu DMARC-Fehlern führen, wenn die E-Mail das Empfängerpostfach erreichte. Mit ARC kann Microsoft 365 anhand der kryptografischen Aufbewahrung der Authentifizierungsergebnisse die Authentizität eines E-Mail-Absenders überprüfen.

Microsoft 365 verwendet ARC zurzeit zur Überprüfung der Authentifizierungsergebnissen, wenn Microsoft der ARC-Sealer ist, aber Sie sollten künftig Unterstützung für ARC-Sealer von Drittanbietern vorsehen.

## <a name="troubleshooting-your-dmarc-implementation"></a>Problembehandlung bei der DMARC-Implementierung

Wenn Sie die MX-Einträge Ihrer Domäne so konfiguriert haben, dass EOP nicht der erste Eintrag ist, werden für Ihre Domäne keine DMARC-Fehler erzwungen.

Wenn Sie Kunde sind und der primäre MX-Eintrag Ihrer Domäne nicht auf EOP verweist, können Sie die Vorteile von DMARC nicht nutzen. DMARC funktioniert beispielsweise nicht, wenn Sie den MX-Eintrag auf Ihren lokalen E-Mail-Server verweisen und anschließend E-Mail-Nachrichten mithilfe eines Connectors an EOP weiterleiten. In diesem Szenario ist die Empfängerdomäne eine der akzeptierten Domänen, EOP ist jedoch nicht der primäre MX-Eintrag. Nehmen Sie zum Beispiel einmal an, dass „contoso.com“ seinen MX auf sich selbst verweist und EOP als sekundären MX-Eintrag verwendet. Der MX-Eintrag von „contoso.com“ sieht dann wie folgt aus:

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Alle bzw. die meisten E-Mail-Nachrichten werden zuerst an „mail.contoso.com“ weitergeleitet, da dies der primäre MX-Eintrag ist. Anschließend werden die E-Mail-Nachrichten an EOP weitergeleitet. In einigen Fällen führen Sie EOP möglicherweise gar nicht als MX-Eintrag auf, sondern verbinden einfach Connectors zum Weiterleiten von E-Mail-Nachrichten. EOP muss nicht der erste Eintrag sein, damit die DMARC-Validierung durchgeführt werden kann. Es stellt lediglich die Validierung sicher, da wir nicht sicher sein können, dass alle lokalen bzw. Nicht-O365-Server alle DMARC-Prüfungen durchführen.  DMARC kann beim Einrichten des DMARC-TXT-Eintrags für die Domäne eines Kunden (nicht den Server) erzwungen werden, aber der empfangende Server muss die Erzwingung tatsächlich ausführen.  Wenn Sie EOP als Empfangsserver einrichten, führt EOP die DMARC-Erzwingung durch.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Eine Grafik zur Problembehebung für DMARC, bereitgestellt von Daniel Mande":::

## <a name="for-more-information"></a>Weitere Informationen

Want more information about DMARC? These resources can help.

- [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) umfassen die Syntax- und Kopfzeilenfelder, die von Microsoft 365 für DMARC-Überprüfungen verwendet werden.

- Sehen Sie sich die [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) von M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group) an.

- Verwenden Sie die Checkliste von [dmarcian](https://space.dmarcian.com/deployment/).

- Schauen Sie direkt an der Quelle nach: [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Siehe auch

[Verwenden des Sender Policy Framework (SPF) durch Microsoft 365 zum Verhindern von Spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)

[Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Microsoft 365 gesendet werden](use-dkim-to-validate-outbound-email.md)
