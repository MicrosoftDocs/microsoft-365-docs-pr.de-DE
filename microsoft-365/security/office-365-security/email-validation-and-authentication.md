---
title: E-Mail-Authentifizierung in Office 365
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
description: Erfahren Sie, wie Exchange Online und Exchange Online Protection (EOP) in Office 365 E-Mail-Authentifizierung (SPF, DKIM und DMARC) verwenden, um Spoofing, Phishing und Spam zu verhindern.
ms.openlocfilehash: 609f1a9bf80acc266bdfc5b0089eb6006be4bd7c
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529864"
---
# <a name="email-authentication-in-office-365"></a>E-Mail-Authentifizierung in Office 365

E-Mail-Authentifizierung (auch als E-Mail-Validierung bezeichnet) ist eine Gruppe von Standards, die versucht, Spoofing (E-Mail-Nachrichten von gefälschten Absendern) entgegen zu wirken. In Office 365-Organisationen mit Exchange Online-Postfächern und in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer nutzt EOP die Standards, um eingehende E-Mails zu überprüfen:

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

Die E-Mail-Authentifizierung überprüft, ob E-Mail-Nachrichten eines Absenders (z.B. laura@contoso.com) seriös sind und aus den erwarteten Quellen für diese E-Mail-Domäne stammen (z.B. contoso.com.)

Der Rest dieses Artikels erläutert, wie diese Technologien funktionieren und wie EOP sie verwendet, um eingehende E-Mails zu prüfen.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Verwenden von E-Mail-Authentifizierung, um Spoofing zu verhindern

DMARC verhindert Spoofing, indem die **Von**-Adresse in Nachrichten untersucht wird (die Absender-E-Mail-Adresse, die Benutzer in ihren E-Mail-Clients sehen). Ziel-E-Mail-Organisationen könne auch überprüfen, ob die E-Mail-Domäne SPF oder DKIM durchlaufen hat. Dies würde darauf hin deuten, dass die Domäne authentifiziert wurde und daher kein Spoofing erfolgt. 

Allerdings ist das Problem, dass SPF-, DKIM- und DMARC-Einträge im DNS für die E-Mail-Authentifizierung (gemeinsam unter der Bezeichnung „E-Mail-Authentifizierungsrichtlinien“ bekannt) vollständig optional sind. Während Domänen mit Richtlinien für sichere E-Mail-Authentifizierung wie microsoft.com und skype.com vor Spoofing geschützt sind, werden Domänen mit schwächeren oder ohne E-Mail-Authentifizierungsrichtlinien zu einem hervorragenden Ziel für Spoofing.

Im März 2018 verfügen nur 9 % der Domänen der Fortune 500-Unternehmen über Richtlinien für sichere E-Mail-Authentifizierung. Die verbleibenden 91% der Unternehmen können möglicherweise von einem Angreifer gefälscht werden. Falls kein anderer E-Mail-Filtermechanismus aktiviert ist, werden E-Mails von gefälschten Absendern in diesen Domänen möglicherweise an die Benutzer übermittelt.

![DMARC-Richtlinien von Fortune 500-Unternehmen](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Der Anteil kleiner und mittelständischer Unternehmen, die keine Fortune 500-Unternehmen sind und Richtlinien für sichere E-Mail-Authentifizierung veröffentlichen, ist kleiner und noch kleiner für E-Mail-Domänen außerhalb von Nordamerika und Westeuropa.

Dies ist ein großes Problem, denn während Unternehmen möglicherweise nicht wissen, wie die E-Mail-Authentifizierung funktioniert, wissen Angreifer den Mangel auszunutzen. Da Phishing und ein solches Problem darstellt und die Einführung von Richtlinien für sichere E-Mail-Authentifizierung begrenzt ist, verwendet Microsoft *implizite E-Mail-Authentifizierung*, um eingehende E-Mails zu überprüfen.

Die implizite E-Mail-Authentifizierung basiert auf zahlreichen Erweiterungen zu regulären E-Mail-Authentifizierungsrichtlinien. Zu diesen Erweiterungen gehören die Absenderzuverlässigkeit, die Geschichte des Absenders, die Geschichte des Empfängers, Verhaltensanalysen und weitere fortgeschrittene Techniken. Eine Nachricht von einer Domäne, die keine E-Mail-Authentifizierungsrichtlinien verwendet, wird als Spoof gekennzeichnet, wenn sie nicht auf andere Weise signalisiert, dass es sich dabei um eine seriöse Nachricht handelt.

Eine allgemeine Ankündigung von Microsoft finden Sie unter [A Sea of Phish Part 2 – Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Zusammengesetzte Authentifizierung

Obwohl SPF, DKIM und DMARC an sich hilfreich sind, wird hier der Authentifizierungsstatus nicht ausreichend kommuniziert, wenn eine Nachricht keine expliziten Authentifizierungsdatensätze enthält. Daher hat Microsoft einen Algorithmus für implizite E-Mail-Authentifizierung entwickelt, der mehrere Signale in einem einzelnen Wert kombiniert, auch als _Composite Authentication (zusammengesetzte Authentifizierung)_ oder kurz „compauth“ bezeichnet. Der Compauth-Wert wird im **Authentication-Results**-Header im Nachrichtenheader vermerkt.

> Authentifizierungsergebnisse:<br/>&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\>

Diese Werte werden unter [Felder in der Nachrichtenkopfzeile „Authentication-results“, die durch die Office 365 E-Mail-Authentifizierung genutzt werden](anti-spam-message-headers.md#authentication-results-message-header-fields-used-by-office-365-email-authentication) erklärt.

Durch Untersuchung der Nachrichtenkopfzeilen können Administratoren oder sogar Endbenutzer ermitteln, wie Office 365 ermittelt hat, dass der Absender gefälscht ist.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen

Falls Sie sich nur auf die Aufzeichnungen der E-Mail-Authentifizierung verlassen, um zu beurteilen, ob eine eingehende Nachricht gefälscht ist, unterliegt ihr Urteilsvermögen den folgenden Einschränkungen:

- Die sendende Domäne könnte nicht über die erforderlichen DNS-Aufzeichnungen verfügen oder die Aufzeichnungen sind falsch konfiguriert.

- Die Quelldomäne hat DNS-Einträge zwar ordnungsgemäß konfiguriert, aber diese Domäne entspricht nicht der Domäne in der Von-Adresse. SPF und DKIM machen es nicht erforderlich, dass die Domäne in der Von-Adresse verwendet wird. Angreifer oder legitime Dienste können eine Domäne registrieren, SPF und DKIM für die Domäne konfigurieren, eine vollkommen andere Domäne in der Von-Adresse verwenden und diese Nachricht wird sowohl SPF als auch DKIM passieren.

Die zusammengesetzte Authorisierung kann gegen diese Einschränkungen Abhilfe schaffen, indem Sie Nachrichten passieren lässt, die E-Mail-Authentifizierungsprüfungen andernfalls nicht bestanden hätten.

> [!NOTE]
> Wie zuvor beschrieben, verwendet die implizite E-Mail-Authentifizierung mehrere Signale, um festzustellen, ob eine Nachricht legitim ist. Die folgenden Beispiele konzentrieren sich zur Vereinfachung auf E-Mail-Authentifizierungsergebnisse. Andere Back-End-Intelligenz-Faktoren könnten Nachrichten, die durch die E-Mail-Authentifizierung als gefälscht eingestuft werden, passieren lassen oder Nachrichten, die durch die E-Mail-Authentifizierung als legitim eingestuft werden, als gefälscht identifizieren.

So hat beispielsweise die fabrikam.com-Domäne keine SPF-, DKIM- oder DMARC-Einträge. Nachrichten von Absendern in der Domäne fabrikam.com können die zusammengesetzte Authentifizierung ggfs. nicht durchlaufen (beachten Sie den `compauth`-Wert und den Grund):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Wenn fabrikam.com einen SPF-, aber keinen DKIM-Eintrag konfiguriert, kann Nachricht die zusammengesetzte Authentifizierung bestehen, da die Domäne, die SPF übergeben hat, der Domäne in der „Von“-Adresse entspricht:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Falls fabrikam.com einen DKIM-Eintrag, jedoch keinen SPF-Eintrag konfiguriert, kann die Nachricht die zusammengesetzte Authentifizierung bestehen, weil die Domäne in der übergebenen DKIM-Signatur der Domäne in der Von-Adresse entspricht:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Wenn die Domäne in SPF oder der DKIM-Signatur nicht mit der Domäne in der Von-Adresse übereinstimmt, kann die Nachricht eine zusammengesetzte Authentifizierung ggfs. nicht bestehen:

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Lösungen für legitime Absender, die nicht-authentifizierte E-Mails senden

Office 365 verfolgt, wer nicht authentifizierte E-Mails an Ihre Organisation sendet. Wenn der Dienst annimmt, dass der Absender nicht seriös ist, wird die Nachricht als Fehler bei der zusammengesetzten Authorisierung markiert. Um dies zu vermeiden, können Sie die Empfehlungen in diesem Abschnitt verwenden.

### <a name="configure-email-authentication-for-domains-you-own"></a>Konfigurieren der E-Mail-Authentifizierung für Domänen, die Sie besitzen

Sie können diese Methode verwenden, um Probleme mit organisationsinternem und domänenübergreifendem Spoofing zu beheben, wenn Sie mehrere Mandanten besitzen oder mit diesen interagieren. Sie kann auch zum Beheben von Problemen mit domänenübergreifenden Spoofing verwendet werden, wenn Sie Nachrichten an andere Kunden innerhalb von Office 365 oder an Drittanbieter senden, die von anderen Anbietern gehostet werden.

- [Konfiguration von SPF-Einträgen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) für Ihre Domänen.

- [Konfiguration von DKIM-Einträgen](use-dkim-to-validate-outbound-email.md) für Ihre primären Domänen.

- [Ziehen Sie es in Erwägung, DMARC-Einträge für Ihre Domäne](use-dmarc-to-validate-email.md) einzurichten, um Ihre seriösen Absender zu ermitteln.

Microsoft bietet keine detaillierten Implementierungsrichtlinien für SPF, DKIM und DMARC-Einträge. Es gibt jedoch eine Menge Informationen, die online verfügbar sind. Es gibt auch Drittanbieter, die Ihrer Organisation dabei helfen, E-Mail-Authentifizierungsdatensätze einzurichten.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Sie kennen nicht alle Quellen Ihrer E-Mails

Viele Domänen veröffentlichen keine SPF-Einträge, da Sie nicht alle E-Mail-Quellen für Nachrichten in Ihrer Domäne kennen. Beginnen Sie damit, einen SPF-Eintrag für all jene E-Mail-Quellen zu veröffentlichen, die Sie kennen (insbesondere diejenigen, bei denen sich der Datenverkehr Ihres Unternehmens befindet), und veröffentlichen Sie eine neutrale SPF-Richtlinie `?all`: Zum Beispiel:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Dieses Beispiel bedeutet, dass E-Mails aus Ihrer Unternehmensinfrastruktur die E-Mail-Authentifizierung passieren, aber E-Mails aus unbekannten Quellen auf neutral zurückfallen.

Office 365 behandelt eingehende E-Mails aus Ihrer Unternehmensinfrastruktur als authentifiziert, aber E-Mail-Nachrichten aus unbekannten Quellen werden möglicherweise weiterhin als Fälschung gekennzeichnet (je nachdem, ob sie von Office 365 implizit authentifiziert werden können). Dies stellt jedoch immer noch eine Verbesserung dazu dar, dass alle E-Mails von Office 365 als Spoofing markiert wurden.

Sobald Sie mit einer SPF-Fallback-Richtlinie von `?all`begonnen haben, können Sie nach und nach weitere E-Mail-Quellen für Ihre Nachrichten entdecken und dann Ihren SPF-Eintrag mit einer strikteren Richtlinie aktualisieren.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Verwenden der Spoofingintelligenz zum Konfigurieren zulässiger Absender nicht authentifizierter E-Mails

Sie können Sie auch [Spoofingintelligenz](learn-about-spoof-intelligence.md) verwenden, damit Absender nicht authentifizierte Nachrichten an Ihre Organisation senden können.

Bei externen Domänen handelt es sich bei dem gefälschten Benutzer um die Domäne in der Von-Adresse, während es sich bei der sendenden Infrastruktur entweder um die Quell-IP-Adresse (aufgeteilt in /24 CIDR-Bereiche) oder um die Organisationsdomäne des Reverse DNS-Eintrags (PTR) handelt.

Im folgenden Screenshot kann die IP 131.107.18.4 lauten und den PTR-Eintrag outbound.mail.protection.outlook.com aufweisen. Dies würde als Outlook.com als sendende Infrastruktur annzeigen.

Damit dieser Absender nicht authentifizierte E-Mails senden kann, ändern Sie die Einstellung von **No** zu **Yes**.

![Einrichten von zulässigen Spoofingabsendern](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Erstellen eines Zulassungseintrags für das Absender/Empfänger-Paar

Wenn Sie die Spamfilterung, einige Teile der Phishing-Filterung, aber nicht die Malware-Filterung für bestimmte Absender umgehen möchten, lesen Sie [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md).

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Bitten Sie den Absender, die E-Mail-Authentifizierung für Domänen, die Sie nicht besitzen, zu konfigurieren

Aufgrund des Problems mit Spam und Phishing empfiehlt Microsoft die E-Mail-Authentifizierung für alle E-Mail-Organisationen. Statt manuelle Außerkraftsetzungen in Ihrer Organisation zu konfigurieren, können Sie einen Administrator in der sendenden Domäne bitten, ihre E-Mail-Authentifizierungseinträge zu konfigurieren.

- Auch wenn sie in der Vergangenheit keine E-Mail-Authentifizierungseinträge veröffentlichen mussten, sollten sie dies tun, wenn sie E-Mails an Microsoft senden.

- Richten Sie SPF ein, um die sendenden IP-Adressen Ihrer Domäne zu veröffentlichen, und DKIM (falls verfügbar) zum digitalen Signieren von Nachrichten. Sie sollten auch das Einrichten von DMARC-Einträgen in Erwägung ziehen.

- Wenn sie zum Senden von E-Mails Massenversender verwenden, überprüfen Sie, ob die Domäne in der Von-Adresse (sofern sie ihnen gehört) mit der Domäne übereinstimmt, die SPF oder DMARC passiert.

- Überprüfen Sie, ob die folgenden Speicherorte (sofern sie diese verwenden) Bestandteil des SPF-Eintrags sind:
  
  - Lokale E-Mail-Server.
  - E-Mail-Nachrichten von einem SaaS-Anbieter (Software-as-a-Service) versendet wurde.
  - E-Mail-Nachrichten, die von einem Cloud-Hostingdienst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services usw.) versendet wurden

- Konfigurieren Sie für kleine Domänen, die von einem ISP gehostet werden, den SPF-Eintrag gemäß den Anweisungen des ISPs.

Obwohl es am Anfang möglicherweise schwierig wird, sendende Domänen zur Authentifizierung zu veranlassen, werden sie im Laufe der Zeit, da immer mehr E-Mail-Filter die Nachrichten dieser Domänen als Junk einstufen oder sie sogar ablehnen, die entsprechenden Datensätze einrichten, um eine bessere Zustellung sicherzustellen. Außerdem kann ihre Beteiligung im Kampf gegen Phishing helfen und die Möglichkeit von Phishing-Angriffen in ihrer Organisation oder ihren Organisationen verringern, an die sie e-Mails senden.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Informationen für Infrastrukturanbieter (ISPs, ESPs oder Cloud-Hostinganbieter)

Wenn Sie E-Mails einer Domäne hosten oder eine Hostinginfrastruktur anbieten, die E-Mails senden kann, sollten Sie wie folgt vorgehen:

- Stellen Sie sicher, dass Ihre Kunden über Dokumentationen verfügen, die erläutern, wie Ihre Kunden ihre SPF-Einträge konfigurieren sollten.

- Ziehen Sie in Erwägung, ausgehende E-Mails mit DKIM-Signaturen zu signieren, selbst wenn der Kunde dies nicht explizit eingerichtet hat (Signieren mit Standarddomäne). Sie können die E-Mail sogar doppelt mit DKIM-Signaturen signieren (mit der Domäne des Kunden, falls eingerichtet, und mit der DKIM-Signatur Ihres Unternehmens).

Die Zustellbarkeit an Microsoft ist auch nicht garantiert, wenn Sie E-Mails, die von Ihrer Plattform stammen, authentifizieren. Es wird jedoch zumindest sichergestellt, dass Ihre E-Mail nicht als Junk-E-Mail von Microsoft eingestuft wird, weil sie nicht authentifiziert ist.

Weitere Informationen zu bewährten Methoden für Dienstanbieter finden Sie unter [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
