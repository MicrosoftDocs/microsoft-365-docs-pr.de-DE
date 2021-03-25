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
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Administratoren erfahren hier, wie EOP E-Mail-Authentifizierung (SPF, DKIM und DMARC) verwendet, um Spoofing, Phishing und Spam zu verhindern.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 633494717ad7cf68319a2332f435fd8b56fc8aeb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205906"
---
# <a name="email-authentication-in-eop"></a>E-Mail-Authentifizierung in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


E-Mail-Authentifizierung (auch als E-Mail-Validierung bezeichnet) ist eine Gruppe von Standards, die versucht, Spoofing (E-Mail-Nachrichten von gefälschten Absendern) entgegen zu wirken. In allen Microsoft 365-Organisationen nutzt EOP folgende Standards, um eingehende e-Mails zu überprüfen:

- [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [DKIM](use-dkim-to-validate-outbound-email.md)

- [DMARC](use-dmarc-to-validate-email.md)

Die E-Mail-Authentifizierung überprüft, ob E-Mail-Nachrichten eines Absenders (z.B. laura@contoso.com) seriös sind und aus den erwarteten Quellen für diese E-Mail-Domäne stammen (z.B. contoso.com.)

Der weitere Artikel erläutert, wie diese Technologien funktionieren und wie EOP sie verwendet, um eingehende E-Mails zu prüfen.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Verwenden von E-Mail-Authentifizierung, um Spoofing zu verhindern

DMARC verhindert Spoofing, indem die **Von**-Adresse in Nachrichten überprüft wird. Die **Von**-Adresse ist die E-Mail-Adresse des Absenders, die Benutzer in ihrem E-Mail-Client sehen. Die Ziel-E-Mail-Organisationen können auch überprüfen, ob die E-Mail-Domäne SPF oder DKIM erfolgreich bestanden hat. Anders ausgedrückt: Die Domäne wurde authentifiziert, daher wird die E-Mail-Adresse des Absenders nicht gespoofed.

DNS-Einträge für SPF, DKIM und DMARC (gemeinsam als "E-Mail-Authentifizierungsrichtlinien" bekannt) sind jedoch optional. Domänen mit starken E-Mail-Authentifizierungsrichtlinien wie microsoft.com und skype.com sind vor Spoofing geschützt. Aber Domänen mit schwächeren E-Mail-Authentifizierungsrichtlinien oder ohne jede Richtlinie sind hervorragende Ziele für Spoofing.

Im März 2018 verfügten nur 9 % der Domänen der Fortune 500-Unternehmen über sichere E-Mail-Authentifizierungsrichtlinien. Die verbleibenden 91% der Unternehmen können möglicherweise mithilfe von Spoofing angegriffen werden. Falls kein anderer E-Mail-Filtermechanismus aktiviert ist, werden E-Mails von gefälschten Absendern in diesen Domänen möglicherweise an die Benutzer übermittelt.

![DMARC-Richtlinien von Fortune 500-Unternehmen](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Der Anteil von kleinen und mittelständischen Unternehmen, die sichere E-Mail-Authentifizierungsrichtlinien verfügen, ist kleiner. Und die Zahl der E-Mail-Domänen außerhalb von Nordamerika und Westeuropa ist sogar noch geringer.

Das Fehlen sicherer E-Mail-Authentifizierungsrichtlinien stellt ein großes Problem dar. Während Organisationen möglicherweise nicht verstehen, wie die E-Mail-Authentifizierung funktioniert, sind sich Angreifer darüber sehr wohl im Klaren und nutzen dies zu ihrem Vorteil aus. Wegen der Sorge vor Phishing und der unzureichenden Einführung sicherer E-Mail-Authentifizierungsrichtlinien, verwendet Microsoft *implizite E-Mail-Authentifizierung*, um eingehende E-Mails zu überprüfen.

Die implizite E-Mail-Authentifizierung ist eine Erweiterung der regulären E-Mail-Authentifizierungsrichtlinien. Zu diesen Erweiterungen gehören: Absenderzuverlässigkeit, Absenderhistorie, Empfängerhistorie, Verhaltensanalysen und weitere fortgeschrittene Techniken. Beim Fehlen weiterer Signale dieser Erweiterungen werden Nachrichten, die von Domänen gesendet ohne E-Mail-Authentifizierungsrichtlinien gesendet werden, als Spoof gekennzeichnet.

Eine allgemeine Ankündigung von Microsoft finden Sie unter [A Sea of Phish Part 2 – Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Zusammengesetzte Authentifizierung

Wenn eine Domäne nicht über herkömmliche SPF-, DKIM- und DMARC-Einträge verfügt, vermitteln diese Datensatzprüfungen nicht genügend Informationen zum Authentifizierungsstatus. Deshalb hat Microsoft einen Algorithmus für die implizite E-Mail-Authentifizierung entwickelt. Dieser Algorithmus kombiniert mehrere Signale in einem einzelnen Wert, der auch als _Composite Authentication_ (zusammengesetzte Authentifizierung) oder `compauth` bezeichnet wird. Der `compauth`-Wert wird im Header der **Authentifizierungsergebnisse** im Nachrichtenheader vermerkt.

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

Diese Werte werden in der [Nachrichtenkopfzeile „Authentication-results“](anti-spam-message-headers.md#authentication-results-message-header) erklärt.

Durch Untersuchung der Nachrichtenkopfzeilen können Administratoren oder sogar Endbenutzer ermitteln, wie Microsoft 365 ermittelt hat, dass der Absender gefälscht ist.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen

Falls Sie sich nur auf die Aufzeichnungen der E-Mail-Authentifizierung verlassen, um zu beurteilen, ob eine eingehende Nachricht gefälscht ist, unterliegt ihr Urteilsvermögen den folgenden Einschränkungen:

- Die sendende Domäne könnte nicht über die erforderlichen DNS-Aufzeichnungen verfügen oder die Aufzeichnungen sind falsch konfiguriert.

- Die Quelldomäne hat DNS-Einträge zwar ordnungsgemäß konfiguriert, aber diese Domäne entspricht nicht der Domäne in der Von-Adresse. SPF und DKIM machen es nicht erforderlich, dass die Domäne in der Von-Adresse verwendet wird. Angreifer oder legitime Dienste können eine Domäne registrieren, SPF und DKIM für die Domäne konfigurieren und eine vollkommen andere Domäne in der “Von”-Adresse verwenden. Nachrichten von Absendern in dieser Domäne werden von SPF und DKIM nicht beanstandet.

Die zusammengesetzte Authentifizierung kann diesen Einschränkungen abhelfen, indem sie Nachrichten weitergibt, die E-Mail-Authentifizierungsprüfungen andernfalls nicht bestanden hätten.

Die folgenden Beispiele konzentrieren sich zur Vereinfachung auf E-Mail-Authentifizierungsergebnisse. Andere Back-End-Intelligenz-Faktoren könnten Nachrichten, die durch die E-Mail-Authentifizierung als gefälscht eingestuft werden, passieren lassen oder Nachrichten, die durch die E-Mail-Authentifizierung als legitim eingestuft werden, als gefälscht identifizieren.

So hat beispielsweise die fabrikam.com-Domäne keine SPF-, DKIM- oder DMARC-Einträge. Nachrichten von Absendern in der Domäne fabrikam.com können die zusammengesetzte Authentifizierung ggfs. nicht durchlaufen (beachten Sie den `compauth`-Wert und den Grund):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Wenn fabrikam.com einen SPF ohne einen DKIM-Eintrag konfiguriert, kann die Nachricht eine kombinierte Authentifizierung weitergeben. Die Domäne, die SPF-Prüfungen übergeben hat, wird an der Domäne in der “Von”-Adresse ausgerichtet:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Wenn fabrikam.com einen SP-Eintrag ohne einen DKIM-Eintrag konfiguriert, kann die Nachricht eine kombinierte Authentifizierung weitergeben. Die Domäne in der DKIM-Signatur, wird an der Domäne in der “Von”-Adresse ausgerichtet:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Wenn die Domäne in SPF oder der DKIM-Signatur nicht mit der Domäne in der “Von”-Adresse übereinstimmt, kann die Nachricht eine zusammengesetzte Authentifizierung ggfs. nicht bestehen:

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

Microsoft 365 verfolgt, wer nicht authentifizierte E-Mails an Ihre Organisation sendet. Wenn der Dienst annimmt, dass der Absender nicht seriös ist, werden die Nachrichten dieses Absenders als Fehlschlag bei der zusammengesetzten Authentifizierung markiert. Um dies zu vermeiden, können Sie die Empfehlungen in diesem Abschnitt verwenden.

### <a name="configure-email-authentication-for-domains-you-own"></a>Konfigurieren der E-Mail-Authentifizierung für Domänen, die Sie besitzen

Sie können diese Methode verwenden, um Probleme mit organisationsinternem und domänenübergreifendem Spoofing zu beheben, wenn Sie mehrere Mandanten besitzen oder mit diesen interagieren. Sie kann auch zum Beheben von Problemen mit domänenübergreifendem Spoofing verwendet werden, wenn Sie Nachrichten an andere Kunden innerhalb von Microsoft 365 oder an Drittanbieter senden, die von anderen Anbietern gehostet werden.

- [Konfiguration von SPF-Einträgen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) für Ihre Domänen.

- [Konfiguration von DKIM-Einträgen](use-dkim-to-validate-outbound-email.md) für Ihre primären Domänen.

- [Ziehen Sie es in Erwägung, DMARC-Einträge für Ihre Domäne](use-dmarc-to-validate-email.md) einzurichten, um Ihre seriösen Absender zu ermitteln.

Microsoft bietet keine detaillierten Implementierungsrichtlinien für SPF, DKIM und DMARC-Einträge. Es gibt jedoch viele Informationen, die online verfügbar sind. Es gibt auch Drittanbieter, die Ihrer Organisation dabei helfen, E-Mail-Authentifizierungsdatensätze einzurichten.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Sie kennen nicht alle Quellen Ihrer E-Mails

Viele Domänen veröffentlichen keine SPF-Einträge, da Sie nicht alle E-Mail-Quellen für Nachrichten in Ihrer Domäne kennen. Beginnen Sie damit, einen SPF-Eintrag für all jene E-Mail-Quellen zu veröffentlichen, die Sie kennen (insbesondere diejenigen, bei denen sich der Datenverkehr Ihres Unternehmens befindet), und veröffentlichen Sie eine neutrale SPF-Richtlinie `?all`: Zum Beispiel:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Dieses Beispiel bedeutet, dass E-Mails aus Ihrer Unternehmensinfrastruktur die E-Mail-Authentifizierung passieren, aber E-Mails aus unbekannten Quellen auf neutral zurückfallen.

Microsoft 365 behandelt eingehende E-Mails aus Ihrer Unternehmensinfrastruktur als authentifiziert. E-Mails von unbekannten Quellen sind möglicherweise weiterhin als Spoof gekennzeichnet, wenn die implizite Authentifizierung fehlschlägt. Dies stellt jedoch immer noch eine Verbesserung dazu dar, dass alle E-Mails von Microsoft 365 als Spoofing markiert wurden.

Sobald Sie mit einer SPF-Fallback-Richtlinie von `?all`begonnen haben, können Sie nach und nach weitere E-Mail-Quellen für Ihre Nachrichten entdecken und dann Ihren SPF-Eintrag mit einer strikteren Richtlinie aktualisieren.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Verwenden der Spoofingintelligenz zum Konfigurieren zulässiger Absender nicht authentifizierter E-Mails

Sie können Sie auch [Spoofingintelligenz](learn-about-spoof-intelligence.md) verwenden, damit Absender nicht authentifizierte Nachrichten an Ihre Organisation senden können.

Bei externen Domänen handelt es sich bei dem gefälschten Benutzer um die Domäne in der Von-Adresse, während es sich bei der sendenden Infrastruktur entweder um die Quell-IP-Adresse (aufgeteilt in /24 CIDR-Bereiche) oder um die Organisationsdomäne des Reverse DNS-Eintrags (PTR) handelt.

Im folgenden Screenshot kann die IP 131.107.18.4 lauten und den PTR-Eintrag outbound.mail.protection.outlook.com aufweisen. Dies würde als Outlook.com als sendende Infrastruktur annzeigen.

Damit dieser Absender nicht authentifizierte E-Mails senden kann, ändern Sie die Einstellung von **No** zu **Yes**.

![Einrichten von zulässigen Spoofingabsendern](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Erstellen eines Zulassungseintrags für das Absender/Empfänger-Paar

Wenn Sie die Spamfilterung, einige Teile der Phishing-Filterung, aber nicht die Malware-Filterung für bestimmte Absender umgehen möchten, lesen Sie [Erstellen von Listen sicherer Absender in Microsoft 365](create-safe-sender-lists-in-office-365.md).

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

## <a name="related-links"></a>Verwandte Links

Weitere Informationen zu bewährten Methoden für Dienstanbieter finden Sie unter [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).

Erfahren Sie, wie Office 365 SPF verwendet und die DKIM-Überprüfung unterstützt:

- [Weitere Informationen zu SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [Weitere Informationen zu DKIM](support-for-validation-of-dkim-signed-messages.md)
