---
title: Verwenden des Sender Policy Framework (SPF) durch Office 365 zum Verhindern von Spoofing
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
ms.openlocfilehash: 9a0cbbe29a43a223a006b1a8495d2522ca2386c4
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772219"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Verwenden des Sender Policy Framework (SPF) durch Office 365 zum Verhindern von Spoofing

 **Zusammenfassung:** Dieser Artikel beschreibt, wie Office 365 den Sender Policy Framework (SPF) TXT-Eintrag in DNS verwendet, um sicherzustellen, dass von Ihrer benutzerdefinierten Domäne gesendete Nachrichten von Ziel-E-Mail-Systemen als vertrauenswürdig eingestuft werden. Dies gilt für ausgehende E-Mail-Nachrichten von Office 365. Nachrichten, die von Office 365 an einen Empfänger in Office 365 gesendet werden, durchlaufen immer SPF. 
  
Ein SPF TXT-Eintrag ist ein DNS-Eintrag, der Ihnen hilft, Spoofing und Phishing zu verhindern, indem der Name der Domäne überprüft wird, von der aus E-Mail-Nachrichten gesendet werden. SPF überprüft den Ursprung von E-Mails, indem die IP-Adresse des Absenders mit dem vorgeblichen Besitzer der Absenderdomäne verglichen wird. 
  
> [!NOTE]
> SPF-Eintragstypen wurden von der Internet Engineering Task Force (IETF) 2014 als veraltet eingestuft. Stellen Sie stattdessen sicher, dass Sie zum Veröffentlichen von SPF-Informationen TXT-Einträge in DNS verwenden. Der Rest dieses Artikels verwendet aus Gründen der Klarheit den Begriff SPF TXT-Eintrag. 
  
Domänenadministratoren veröffentlichen SPF-Informationen in TXT-Einträgen in DNS. Durch die SPF-Informationen werden autorisierte Server für ausgehende E-Mails identifiziert. Von Ziel-E-Mail-Systemen wird überprüft, ob die Nachrichten von autorisierten Servern für ausgehende E-Mails stammen. Wenn Sie bereits mit SPF vertraut sind oder über eine einfache Bereitstellung verfügen und nur wissen möchten, was Sie in Ihren SPF TXT-Eintrag in DNS für Office 365 einschließen müssen, können Sie zu [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) wechseln. Wenn Ihre Bereitstellung nicht vollständig in Office 365 gehostet wird, oder wenn Sie weitere Informationen zur Funktionsweise von SPF oder zur Problembehandlung von SPF für Office 365 benötigen, lesen Sie hier weiter.
  
> [!NOTE]
> Zuvor mussten Sie einen anderen SPF TXT-Eintrag zu Ihrer benutzerdefinierten Domäne hinzufügen, wenn Sie auch SharePoint Online verwendet haben. Dies ist nicht mehr erforderlich. Diese Änderung sollte das Risiko reduzieren, dass SharePoint Online-Benachrichtigungsnachrichten im Junk-E-Mail-Ordner landen. Sie müssen keine Änderungen sofort vornehmen, aber wenn Sie den Fehler "zu viele Nachschlagevorgänge" erhalten, ändern Sie Ihren SPF TXT-Eintrag wie unter Einrichten von [SPF in Office 365 beschrieben, um Spoofing zu verhindern](set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a>Funktionsweise von SPF zur Verhinderung von Spoofing und Phishing in Office 365
<a name="HowSPFWorks"> </a>

SPF ermittelt, ob ein Absender im Auftrag einer Domäne senden darf. Wenn der Absender dazu nicht berechtigt ist, wenn die E-Mail also die SPF-Prüfung auf dem empfangenden Server nicht besteht, ermittelt die Spamrichtlinie, die auf diesem Server konfiguriert ist, was mit der Nachricht geschieht.
  
Jeder SPF TXT-Eintrag enthält drei Teile: die Deklaration, dass es sich um einen SPF TXT-Eintrag handelt, die IP-Adressen, die berechtigt sind, E-Mail-Nachrichten aus Ihrer Domäne zu senden, und die externen Domänen, die im Auftrag Ihrer Domäne senden können, sowie eine Regel für die Durchsetzung. Sie benötigen alle drei in einem gültigen SPF TXT-Eintrag. In diesem Artikel wird beschrieben, wie Sie Ihren SPF TXT-Eintrag erstellen. Außerdem werden bewährte Methoden für die Arbeit mit den Diensten in Office 365 bereitgestellt. Auch Links zu Anweisungen für die Arbeit mit Ihrer Domänenregistrierungsstelle zum Veröffentlichen Ihres Eintrags in DNS werden bereitgestellt.
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-Grundlagen: IP-Adressen, die von Ihrer benutzerdefinierten Domäne aus senden dürfen
<a name="SPFBasicsIPaddresses"> </a>

Sehen Sie sich die allgemeine Syntax für eine SPF-Regel an:
  
v=spf1 \<IP\> \<Durchsetzungsregel\>
  
Nehmen wir z. B. an, dass die folgende SPF-Regel für „contoso.com" vorhanden ist:
  
v=spf1 \<IP-Adresse #1\> \<IP-Adresse #2\> \<IP-Adresse #3\> \<Durchsetzungsregel\>
  
In diesem Beispiel weist die SPF-Regel den empfangenden E-Mail-Server an, nur E-Mail-Nachrichten von diesen IP-Adressen für die Domäne „contoso.com" zu akzeptieren:
  
- IP-Adresse #1
    
- IP-Adresse #2
    
- IP-Adresse #3
    
Diese SPF-Regel weist den empfangenden E-Mail-Server an, dass er, wenn eine Nachricht von „contoso.com", aber nicht von einer dieser drei IP-Adressen kommt, die Durchsetzungsregel auf die Nachricht anwenden soll. Die Durchsetzungsregel bietet normalerweise eine der folgenden Optionen:
  
- **Hard fail** (schwerer Fehler). Markieren Sie die Nachricht mit „Hard fail" im Nachrichtenumschlag, und folgen Sie dann der konfigurierten Spamrichtlinie des empfangenden Server für diese Art von Nachricht. 
    
- **Soft fail** (nicht schwerwiegender Fehler). Markieren Sie die Nachricht mit „Soft fail" im Nachrichtenumschlag. E-Mail-Server sind in der Regel so konfiguriert, dass diese Nachrichten trotzdem übermittelt werden. Die meisten Endbenutzer sehen diese Markierung nicht. 
    
- **Neutral.** Keine Aktion, d. h. markieren Sie den Nachrichtenumschlag nicht. Dies ist normalerweise für Testzwecke reserviert und wird nur selten verwendet. 
    
Die folgenden Beispiele zeigen, wie SPF in unterschiedlichen Situationen funktioniert. In diesen Beispielen ist „contoso.com“ der Absender und „woodgrovebank.com“ der Empfänger.
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Beispiel 1: E-Mail-Authentifizierung einer Nachricht, die direkt vom Absender an den Empfänger gesendet wird
<a name="spfExample1"> </a>

SPF funktioniert am besten, wenn der Pfad vom Absender zum Empfänger direkt ist, z. B.:
  
![Diagramm, in dem gezeigt wird, wie SPF E-Mails authentifiziert, wenn diese direkt von Server zu Server gesendet werden.](../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
Wenn „woodgrovebank.com“ die Nachricht empfängt, wenn IP-Adresse #1 im SPF TXT-Eintrag für „contoso.com“ vorhanden ist, besteht die Meldung die SPF-Prüfung und wird authentifiziert.
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Beispiel 2: Gefälschte Absenderadresse besteht die SPF-Prüfung nicht
<a name="spfExample2"> </a>

Nehmen wir an, ein Phisher findet eine Möglichkeit zum Spoofing in „contoso.com":
  
![Diagramm, in dem gezeigt wird, wie SPF E-Mails authentifiziert, wenn diese von einem gefälschten Server gesendet werden.](../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
Da die IP-Adresse #12 nicht im SPF TXT-Eintrag von „contoso.com" enthalten ist, besteht die Meldung die SPF-Prüfung nicht, und der Empfänger kann sie als Spam markieren.
  
### <a name="example-3-spf-and-forwarded-messages"></a>Beispiel 3: SPF und weitergeleitete Nachrichten
<a name="spfExample3"> </a>

Ein Nachteil von SPF liegt darin, dass es nicht funktioniert, wenn eine E-Mail-Nachricht weitergeleitet wurde. Nehmen Sie beispielsweise an, dass der Benutzer in „woodgrovebank.com" eine Weiterleitungsregel eingerichtet hat, um alle E-Mail-Nachrichten an ein „outlook.com"-Konto zu senden:
  
![Diagramm, in dem gezeigt wird, dass SPF E-Mails nicht authentifizieren kann, wenn die Nachricht weitergeleitet wird.](../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
Die Nachricht besteht ursprünglich die SPF-Prüfung von „woodgrovebank.com", besteht aber nicht die SPF-Prüfung von „outlook.com", da IP-Adresse #25 nicht im SPF TXT-Eintrag von „contoso.com" vorhanden ist. „Outlook.com" kann dann die Nachricht als Spam markieren. Um dieses Problem zu umgehen, verwenden Sie SPF in Verbindung mit anderen E-Mail-Authentifizierungsmethoden, z. B. DKIM und DMARC.
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-Grundlagen: Einschließlich von Drittanbieterdomänen, die E-Mails im Auftrag Ihrer Domäne senden können
<a name="SPFBasicsIncludes"> </a>

Zusätzlich zu den IP-Adressen können Sie auch Ihren SPF TXT-Eintrag zum Einschließen von Domänen als Absender konfigurieren. Diese werden als dem SPF TXT-Eintrag als „include"-Anweisungen hinzugefügt. „contoso.com" möchte beispielsweise alle IP-Adressen der E-Mail-Server aus „contoso.net" und „contoso.org", die es auch besitzt, einschließen. Zu diesem Zweck veröffentlicht „contoso.com" einen SPF TXT-Eintrag, der etwa wie folgt aussieht:
  
```
v=spf1 include:contoso.net include:contoso.org -all
```

Wenn der empfangende Server diesen Eintrag in DNS sieht, führt er auch eine DNS-Suche für den SPF TXT-Eintrag für contoso.net und dann für contoso.org aus. Wenn eine zusätzliche include-Anweisung in den Datensätzen für contoso.net oder contoso.org gefunden wird, werden diese ebenfalls befolgt. Um DOS-Angriffe zu verhindern, beträgt die maximale Anzahl von DNS-Suchen für eine einzelne E-Mail-Nachricht 10. Jede „include“-Anweisung stellt eine zusätzliche DNS-Suche dar. Wenn eine Nachricht das Limit von 10 überschreitet, schlägt die Nachricht für SPF fehl. Sobald eine Nachricht diesen Grenzwert erreicht hat, kann der Absender abhängig von der Konfiguration des empfangenden Servers eine Meldung erhalten, die besagt, dass die Nachricht "zu viele Nachschlagevorgänge" generiert wurde oder dass die maximale Anzahl von Hops für die Nachricht überschritten wurde (was passieren kann, wenn die Lookups-Schleife und überschreitet das DNS-Timeout). Tipps, zum Vermeiden dieses Problems finden Sie unter [Problembehandlung: Bewährte Methoden für SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a>Anforderungen für Ihren SPF TXT-Eintrag und Office 365
<a name="SPFReqsinO365"> </a>

Wenn Sie E-Mail zusammen mit Office 365 eingerichtet haben, wurde bereits ein SPF-Eintrag erstellt, der die Microsoft-Messagingserver als rechtmäßige E-Mail-Quelle für Ihre Domäne identifiziert. Dieser Eintrag sieht wahrscheinlich wie folgt aus:
  
```
v=spf1 include:spf.protection.outlook.com -all
```

Wenn Sie ein vollständig gehosteter Office 365-Kunde sind, d. h., Sie haben keine lokalen E-Mail-Server, die ausgehende E-Mails senden, ist dies der einzige SPF TXT-Eintrag, den Sie für Office 365 veröffentlichen müssen.
  
Wenn Sie eine Hybridbereitstellung haben (d. h. einige Postfächer lokal und einige in Office 365 hosten), oder wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde sind (d. h. Ihre Organisation verwendet EOP zum Schutz Ihrer lokalen Postfächer), sollten Sie die ausgehende IP-Adresse für jeden Ihrer lokalen Edge-E-Mail-Server zum SPF TXT-Eintrag in DNS hinzufügen.
  
## <a name="form-your-spf-txt-record-for-office-365"></a>Erstellen Ihres SPF TXT-Eintrags für Office 365
<a name="FormYourSPF"> </a>

Verwenden Sie die Syntaxinformationen in diesem Artikel, um den SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne zu erstellen. Obwohl es auch andere Optionen gibt, die hier nicht genannt werden, sind dies die am häufigsten verwendeten Syntaxoptionen. Nachdem Sie Ihren Eintrag erstellt haben, müssen Sie den Eintrag bei Ihrer Domänenregistrierungsstelle aktualisieren.
  
Informationen zu den Domänen, die Sie für Office 365 einschließen müssen, finden Sie unter [Für SPF erforderliche externe DNS-Einträge](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US). Verwenden Sie die [schrittweisen Anweisungen](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) zur Aktualisierung von SPF (TXT)-Einträgen für Ihre Domänenregistrierungsstelle. Wenn die Registrierungsstelle nicht aufgeführt ist, müssen Sie sie separat kontaktieren, um Informationen zum Aktualisieren Ihres Eintrags zu erhalten. 
  
### <a name="spf-txt-record-syntax-for-office-365"></a>Syntax des SPF TXT-Eintrags für Office 365
<a name="SPFSyntaxO365"> </a>

Ein typischer SPF TXT-Eintrag für Office 365 weist die folgende Syntax auf:
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Beispiel:
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

Dabei gilt:
  
- **v=spf1** ist erforderlich. Dies definiert den TXT-Eintrag als SPF TXT-Eintrag. 
    
- **ip4** gibt an, dass Sie IP-Adressen der Version 4 verwenden. **ip6** gibt an, dass Sie IP-Adressen der Version 6 verwenden. Wenn Sie IPv6-IP-Adressen verwenden, ersetzen Sie in den Beispielen in diesem Artikel **ip4** durch **ip6**. Sie können auch IP-Adressbereiche in CIDR-Schreibweise angeben, z. B. **ip4:192.168.0.1/26**.
    
-  _IP address_ ist die IP-Adresse, die Sie dem SPF TXT-Eintrag hinzufügen möchten. Normalerweise ist dies die IP-Adresse des Servers für ausgehende E-Mails für Ihre Organisation. Sie können mehrere ausgehende Mailserver auflisten. Weitere Informationen finden Sie unter [Beispiel: SPF TXT-Eintrag für mehrere ausgehende lokale E-Mail-Server und Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).
    
-  _domain name_ ist die Domäne, die Sie als legitimen Absender hinzufügen möchten. Eine Liste der Domänen, die Sie für Office 365 einschließen sollten, finden Sie unter [Für SPF erforderliche externe DNS-Einträge](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).
    
- Die Durchsetzungsregel bietet normalerweise eine der folgenden Optionen:
    
  - -all
    
    Zeigt einen schweren Fehler an. Wenn Sie alle autorisierten IP-Adressen für Ihre Domäne kennen, listen Sie diese im SPF TXT-Eintrag auf, und verwenden Sie die Option „-all“ (schwerer Fehler). Wenn Sie nur SPF verwenden, wenn sie also weder DMARC noch DKIM verwenden, sollten Sie ebenfalls die Option „-all“ verwenden. Es wird empfohlen, immer diese Option zu verwenden.
    
  - ~all
    
    Zeigt einen nicht schwerwiegenden Fehler an. Wenn Sie nicht sicher sind, ob Sie die vollständige Liste der IP-Adressen haben, sollten Sie die Option „~all" (nicht schwerwiegender Fehler) verwenden. Auch bei Verwendung von DMARC mit „p=quarantine" oder „p=reject" können Sie „~all" verwenden. Verwenden Sie andernfalls „-all".
    
  - ?all
    
    Zeigt neutral an. Wird verwendet, um SPF zu testen. Wir empfehlen nicht, diese Option in Ihrer Livebereitstellung zu verwenden.
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a>Beispiel: Zu verwendender SPF TXT-Eintrag, wenn alle Ihre E-Mail-Nachrichten von Office 365 gesendet werden
<a name="ExampleSPFNoSP"> </a>

Wenn alle Ihre E-Mail-Nachrichten von Office 365 gesendet werden, verwenden Sie Folgendes in Ihrem SPF TXT-Eintrag:
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a>Beispiel: SPF TXT-Eintrag für ein Hybridszenario mit einem lokalen Exchange-Server und Office 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Wenn in einer Hybridumgebung die IP-Adresse des lokalen Exchange-Servers „192.168.0.1“ lautet, um die SPF-Durchsetzungsregel auf einen schweren Fehler festzulegen, erstellen Sie den SPF TXT-Eintrag wie folgt:
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a>Beispiel: SPF TXT-Eintrag für mehrere ausgehende lokale E-Mail-Server und Office 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Wenn Sie über mehrere ausgehende E-Mail-Server verfügen, schließen Sie die IP-Adresse für jeden E-Mail-Server in den SPF TXT-Eintrag ein, und trennen Sie die IP-Adressen mit einem Leerzeichen, gefolgt von „ip4:". Beispiel:
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a>Nächste Schritte: Einrichten von SPF für Office 365
<a name="SPFNextSteps"> </a>

Nachdem Sie den SPF TXT-Eintrag erstellt haben, führen Sie die Schritte in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) durch, um ihn Ihrer Domäne hinzuzufügen. 
  
Obwohl SPF Spoofing verhindern soll, gibt es Spoofingtechniken, gegen die SPF nicht schützen kann. Zum Einrichten eines entsprechenden Schutzes sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren. Die ersten Schritte finden Sie unter [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md). Lesen Sie anschließend [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365](use-dmarc-to-validate-email.md).
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a>Problembehandlung: Bewährte Methoden für SPF in Office 365
<a name="SPFTroubleshoot"> </a>

Sie dürfen nur einen SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne erstellen. Das Erstellen von mehreren Einträgen führt zu einer Roundrobin-Situation, und SPF verursacht einen Fehler. Um dies zu vermeiden, können Sie separate Einträge für jede Unterdomäne erstellen. Erstellen Sie z. B. einen Eintrag für „contoso.com" und einen anderen für „bulkmail.contoso.com".
  
Wenn eine E-Mail-Nachricht mehr als 10 DNS-Suchvorgänge verursacht, bevor sie zugestellt wird, antwortet der empfangende E-Mail-Server mit einem permanenten Fehler, der auch als  _permerror_ bezeichnet wird und dazu führt, dass die Nachricht die SPF-Prüfung nicht besteht. Der empfangende Server kann auch mit einem Unzustellbarkeitsbericht (NDR) antworten, der eine Fehlermeldung ähnlich der folgenden enthält:
  
- Die Nachricht hat die Hop-Anzahl überschritten.
    
- Die Nachricht hat zu viele Suchvorgänge benötigt.
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a>Vermeiden der Fehlermeldung "zu viele Suchvorgänge" bei der Verwendung von Drittanbieterdomänen mit Office 365
<a name="SPFTroubleshoot"> </a>

Einige SPF TXT-Einträge für Drittanbieterdomänen weisen den empfangenden Server an, eine große Anzahl von DNS-Suchvorgängen auszuführen. „salesforce.com" enthält z. B. zum Zeitpunkt der Erstellung dieses Dokuments im Eintrag fünf „include"-Anweisungen:
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Um den Fehler zu vermeiden, können Sie eine Richtlinie implementieren, bei der jeder, der z. B. Massen-E-Mails sendet, eine speziell für diesen Zweck eingerichtete Unterdomäne verwenden muss. Dann definieren Sie einen unterschiedlichen SPF TXT-Eintrag für die Unterdomäne, die die Massen-E-Mails enthält.
  
 In einigen Fällen, wie im Beispiel „salesforce.com", müssen Sie die Domäne in Ihrem SPF TXT-Eintrag verwenden, aber in anderen Fällen hat der Drittanbieter möglicherweise bereits eine Unterdomäne erstellt, die Sie zu diesem Zweck verwenden können. „exacttarget.com" hat beispielsweise eine Unterdomäne erstellt, die Sie für Ihren SPF TXT-Eintrag verwenden müssen: 
  
```
cust-spf.exacttarget.com
```

Wenn Sie in Ihren SPF TXT-Eintrag Drittanbieterdomänen einschließen, müssen Sie mit dem Drittanbieter absprechen, welche Domäne oder Unterdomäne verwendet werden soll, um das Erreichen des Limits der 10 Suchvorgänge zu vermeiden.
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Anzeigen des aktuellen SPF TXT-Eintrags und Ermitteln der benötigten Anzahl der Suchvorgänge
<a name="SPFTroubleshoot"> </a>

Sie können nslookup zum Anzeigen der DNS-Einträge verwenden, einschließlich des SPF TXT-Eintrags. Es gibt aber auch eine Reihe von kostenlosen Tools, die Sie verwenden können, um den Inhalt Ihres SPF TXT-Eintrags anzuzeigen. Durch das Überprüfen des SPF TXT-Eintrags und durch Folgen der Kette der „include"-Anweisungen und -Umleitungen können Sie ermitteln, wie viele DNS-Suchvorgänge für den Eintrag erforderlich sind. Einige Onlinetools können diese Suchvorgänge sogar zählen und anzeigen. Das Überwachen dieser Anzahl verhindert, dass Nachrichten, die von Ihrer Organisation gesendet werden, auf dem empfangenden Server einen permanenten Fehler auslösen, der auch als permerror bezeichnet wird.
  
## <a name="for-more-information"></a>Weitere Informationen
<a name="SPFTroubleshoot"> </a>

Benötigen Sie Hilfe beim Hinzufügen des SPF-TXT-Eintrags? Lesen Sie den Artikel [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide#add-a-txt-record-for-spf-to-help-prevent-email-spam) ausführliche Informationen zur Verwendung von Sender Policy Framework mit Ihrer benutzerdefinierten Domäne in Office 365. [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) umfasst die Syntax- und Kopfzeilenfelder, die von Office 365 für SPF-Überprüfungen verwendet werden. 
  

