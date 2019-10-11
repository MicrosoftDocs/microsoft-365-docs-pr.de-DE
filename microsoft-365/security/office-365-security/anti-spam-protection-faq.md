---
title: Häufig gestellte Fragen zum Antispamschutz
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Dieses Thema enthält häufig gestellte Fragen und Antworten zum Thema Antispamschutz. Die Antworten richten sich an Kunden von Microsoft Exchange Online und Exchange Online Protection.
ms.openlocfilehash: 504fb93a271a60db4c43aa48ba6578a904c8bb5a
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441092"
---
# <a name="anti-spam-protection-faq"></a>Häufig gestellte Fragen zum Antispamschutz

Dieses Thema enthält häufig gestellte Fragen und Antworten zum Thema Antispamschutz. Die Antworten richten sich an Kunden von Microsoft Exchange Online und Exchange Online Protection. 
  
> [!TIP]
> Informationen zu Fragen und Antworten in Bezug auf sichere Absender und gesperrte Absender finden Sie unter [Listen sicherer und blockierter Absender in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). Informationen zu Fragen und Antworten in Bezug auf Quarantäne finden Sie unter [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md). 
  
 **F. Was passiert standardmäßig mit einer Nachricht, die als Spam erkannt wird?**
  
A. **Für eingehende Nachrichten:** Der Großteil der Spamnachrichten wird mithilfe der Verbindungsfilterung gelöscht, die auf der IP-Adresse des Absenders basiert. Der Dienst untersucht anschließend den Inhalt der Nachricht. Standardmäßig wird durch die Inhaltsfilterung abgefangener Spam an den Junk E-Mail-Ordner des Empfängers gesendet. Sie können diese Aktion ändern. Beispielsweise können Sie durch Konfigurieren der Inhaltsfilterrichtlinie auswählen, dass Spamnachrichten stattdessen in die Quarantäne gesendet werden. 
  
> [!IMPORTANT]
> Für EoP-eigenständige Kunden: um sicherzustellen, dass die Aktion **Nachricht in Junk-e-Mail-Ordner verschieben** mit lokalen Postfächern funktioniert, müssen Sie zwei Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) auf Ihren lokalen Servern konfigurieren, um zu erkennen von EoP hinzugefügte Spam Kopfzeilen. Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
 **Für ausgehende Nachrichten:** Die Nachricht wird entweder durch den Pool für besonders riskante Zustellungen geleitet oder ist unzustellbar und wird nicht zugestellt. In diesem Fall sollte der Absender eine Benachrichtigung über den Übermittlungsstatus (Delivery Status Notification, DSN) erhalten, in der ihm mitgeteilt wird, dass die Nachricht nicht zugestellt werden konnte. 
  
 **F. Was ist eine Zero-Day-Spamvariante, und wie wird sie vom Dienst verarbeitet?**
  
A. Eine Zero-Day-Spamvariante ist eine bisher unbekannte Spamvariante der ersten Generation, die noch niemals zuvor erfasst oder analysiert wurde, sodass unsere Spaminhaltsfilter noch keine Definitionen haben, um sie zu erkennen. Wenn unsere Spamanalysten ein Beispiel einer Zero-Day-Spamvariante erfasst und analysiert haben und diese die Kriterien für die Klassifizierung als Spam erfüllt, werden unsere Spaminhaltsfilter dafür konfiguriert, sie zu erkennen. Ab diesem Zeitpunkt wird sie nicht mehr als "Zero-Day" betrachtet. ( **Hinweis:** Wenn Sie eine Nachricht erhalten, bei der es sich um eine Zero-Day-Spamvariante handeln könnte, senden Sie die Nachricht bitte mithilfe einer der unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) beschriebenen Methoden an Microsoft. Sie helfen uns damit, unseren Service zu verbessern.)
  
 **F. Muss ich den Dienst für Antispamschutz konfigurieren?**
  
A. Nachdem Sie sich für den Dienst registriert und Ihre Domäne hinzugefügt haben, wird die Spamfilterung unternehmensweit automatisch mithilfe der standardmäßigen Antispamrichtlinien aktiviert. Die Standardrichtlinien sind so optimiert, dass sie ohne zusätzliche Konfiguration Schutz bereitstellen (abgesehen von der oben aufgeführten Ausnahme für Kunden mit einer Lösung von EOP). Als Administrator können Sie die standardmäßigen Antispamrichtlinien jedoch bearbeiten, um sie genau an die Anforderungen Ihrer Organisation anzupassen. Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte Inhaltsfilterrichtlinien erstellen und diese auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.
  
Weitere Informationen zum Konfigurieren der Antispamrichtlinien finden Sie unter den folgenden Themen:
  
[Konfigurieren der Verbindungsfilterrichtlinie](configure-the-connection-filter-policy.md)
  
[Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md)
  
[Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md)
  
 **F. Wie lange dauert es, bis von mir vorgenommene Änderungen an einer Antivirusrichtlinie übernommen werden?**
  
A. Es kann bis zu einer Stunde dauern, bis die Änderungen übernommen werden.
  
 **F. Ist die Filterung von Massen-E-Mails automatisch aktiviert?**
  
A. Standardmäßig ist die erweiterte Spamfilterungsoption **Massen-E-Mail** für neue Kunden aktiviert. Bei migrierten Kunden richtet sich diese Einstellung nach Ihrer FOPE-Konfiguration. Weitere Informationen zu Massen-E-Mails finden Sie unter [Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
 **Q. Bietet der Dienst die URL-Filterung?**
  
A. Ja, der Dienst verfügt über einen URL-Filter, der die URLs in Nachrichten überprüft. Mit bekannten Spam- oder nicht sicheren Inhalten verbundene URLs werden erkannt und die Nachrichten anschließend als Spam markiert.
  
 **F. Wie können Kunden den Dienst verwenden, um falsch negative Ergebnisse (Spam) und falsch positive Ergebnisse (kein Spam) an Microsoft zu senden?**
  
A. Es gibt verschiedene Möglichkeiten, Spamnachrichten und Nachrichten, die kein Spam sind, zur Analyse an Microsoft zu übermitteln. Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **F. Kann ich Spamberichte abrufen?**
  
A. Ja, beispielsweise können Sie einen Spam Erkennungs Bericht im Microsoft 365 Admin Center erhalten. Dieser Bericht weist das Spamvolumen als Anzahl eindeutiger Nachrichten aus. Weitere Informationen zur Berichterstellung finden Sie unter den folgenden Themen:
  
Exchange Online Kunden: [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)
  
Kunden von Exchange Online Protection: [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)
  
 **F. Jemand hat mir eine Nachricht gesendet, aber ich finde sie nicht. Ich vermute, dass sie als Spam erkannt wurde. Gibt es ein Tool, mit dem ich das herausfinden kann?**
  
A. Ja, mit dem Tool für die Nachrichtenablaufverfolgung können Sie e-Mail-Nachrichten verfolgen, während Sie den Dienst durchlaufen, um herauszufinden, was mit Ihnen geschehen ist. Weitere Informationen zur Verwendung des Nachrichtenablauf Verfolgungs Tools, um herauszufinden, warum eine Nachricht als Spam gekennzeichnet wurde, finden Sie unter [war eine Nachricht als Spam gekennzeichnet?](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)
  
 **F. Schränkt der Dienst meine E-Mail ein (begrenzt ihre Rate), wenn die Benutzer ausgehenden Spam senden?**
  
A. Wenn mehr als der Hälfte der von einem Benutzer über den Dienst in einem bestimmten Zeitraum (z. B. in der Stunde) gesendeten E-Mails von Office 365 als Spam eingestuft werden, wird dieser Benutzer für das Senden von Nachrichten blockiert. Wenn eine ausgehende Nachricht als Spam identifiziert wird, wird sie in den meisten Fällen durch den Pool für besonders riskante Zustellungen geleitet, der die Wahrscheinlichkeit reduziert, dass der normale Pool für ausgehende IP-Adressen einer Liste blockierter IP-Adressen hinzugefügt wird.
  
Sie können eine Benachrichtigung an eine angegebene E-Mail-Adresse senden, wenn ein Absender für das Senden ausgehender Spamnachrichten blockiert wird. Weitere Informationen zu dieser Einstellung finden Sie unter [Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md).
  
 **F. Kann ich eine Drittanbieterlösung zum Schutz vor Antispam- und Antischadsoftware zusammen mit Exchange Online einsetzen?**
  
A. Ja, Sie können einen anderen Filterdienst zum Schutz vor Spam und Schadsoftware konfigurieren, um Ihre Exchange Online-Postfächer zu schützen. Zu diesem Zweck müssen Sie für eingehende E-Mail-Nachrichten Ihre E-Mail-Nachrichten an einen Drittanbieter weiterleiten, indem Sie Ihre MX-Einträge ändern, um auf den Drittanbieter zu verweisen. Leiten Sie die Nachrichten anschließend zur weiteren Bearbeitung an den EOP-Dienst weiter. Für Ausgehende E-Mail-Nachrichten muss der Drittanbieter (Smarthost) als Übermittlungsziel für die Nachrichten angegeben werden, siehe [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).
  
 **F. Bietet Microsoft Informationen, wie ich mich gegen betrügerische Phishing-Versuche schützen kann?**
  
A. Ja, lesen Sie dazu die folgenden Artikel:
  
[Informationen zu Phishing, Lotteriebetrug und andere Arten von Betrug](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[E-Mail- und Internetbetrügereien: So schützen Sie sich](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 **F. Werden Spam- und Malwarenachrichten darauf untersucht, wer sie gesendet hat, oder werden sie an Strafverfolgungsbehörden weitergeleitet?**
  
A. Der Dienst dient in erster Linie zum Erkennen und Entfernen von Spam und Malware. Wir untersuchen gelegentlich jedoch besonders gefährlichen oder schädlichen Spam bzw. Angriffe genauer und verfolgen die Täter. Hierzu arbeiten wir gegebenenfalls auch mit unseren Rechtsabteilungen und Abteilungen zum Schutz vor Computerkriminalität zusammen, um ein Spammer-Botnet zu zerschlagen, den Spammer an der Verwendung des Dienstes zu hindern (wenn er den Dienst zum Senden von E-Mails verwendet) und die Informationen an die Strafverfolgungsbehörden weiterzugeben.
  
 **F. Mit welchen bewährten Methoden für das Senden ausgehender E-Mails kann ich sicherstellen, dass meine E-Mails zugestellt werden?**
  
A. Die unten aufgeführten Richtlinien beschreiben bewährte Methoden für das Senden ausgehender E-Mails.
  
1. **Die Domain des E-Mail-Absenders sollte im DNS aufgelöst werden können.**
    
    Wenn der Absender beispielsweise "user@example.com" ist, wir die Domäne "example.com" zu der IP-Adresse 192.0.43.10 aufgelöst. Wenn eine sendende Domäne nicht über einen A-Eintrag und nicht über einen MX-Eintrag in DNS verfügt, leitet der Dienst die Nachricht stets durch den Pool für besonders riskante Zustellungen, unabhängig davon, ob es sich bei ihrem Inhalt um Spam handelt. Weitere Informationen zum Pool mit höherem Risiko für Zustellungen finden Sie unter [risikoreichen Zustellungs Pool für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md). 
    
2. **Die Absender-IP-Adresse des ausgehenden E-Mail-Servers sollte über einen Reverse-DNS-Eintrag (PTR-Eintrag) verfügen.**
    
    Wenn beispielsweise von der IP-Adresse 192.0.43.10 aus gesendet wird, lautet der Reverse-DNS-Eintrag "43-10.any.icann.org". 
    
3. **Die Befehle HELO/EHLO und MAIL FROM sollten konsistent sein und in Form eines Domänennamens vorliegen, nicht in Form einer IP-Adresse.**
    
    Der Befehl HELO/EHLO sollte so konfiguriert sein, dass er dem Reverse-DNS der Absender-IP-Adresse entspricht, sodass die Domäne in allen Teilen des Nachrichtenkopfs gleich ist.
    
4. **Stellen Sie sicher, dass ordnungsgemäße SPF-Einträge im DNS eingerichtet sind.**
    
    Bei SPF-Einträgen handelt es sich um einen Mechanismus, mit dem überprüft wird, ob von einer Domäne gesendete E-Mails wirklich von dieser Domäne stammen und kein Spoofing vorliegt. Weitere Informationen zu SPF-Einträgen finden Sie unter den folgenden Links:
    
    [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [Erstellen von DNS-Einträgen für Office 365](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. **Wenn Sie E-Mails mit DKIM signieren, melden Sie sich mit eingeschränkter Kanonisierung an.**
    
    Wenn ein Absender seine Nachrichten mit DKIM (Domain Keys Identified Mail) signieren und ausgehende E-Mails über den Dienst senden möchte, sollte er sich mit dem Algorithmus für die eingeschränkte Kanonisierung der Kopfzeilen anmelden. Wenn Sie sich mit strenger Kanonisierung der Kopfzeilen anmelden, wird die Signatur beim Durchlaufen des Diensts möglicherweise als ungültig erklärt.
    
6. **Domänenbesitzer sollten über korrekte Informationen in der WHOIS-Datenbank verfügen.**
    
    Mit diesen wird identifiziert, wem die Domäne gehört und wie die Besitzer kontaktiert werden können, indem das übergeordnete Unternehmen, der Kontakt und die Namenserver eingegeben werden.
    
7. **Bei Absendern von Massen-E-Mails sollte der Name unter "Von:" zeigen, wer der Absender ist, und der Betreff der Nachricht sollte kurz zusammenfassen, um was es geht.**
    
    Der Nachrichtentext sollte das Angebot, den Dienst oder das Produkt klar erkennen lassen. Wenn ein Absender zum Beispiel eine Massensendung vom Unternehmen Contoso aus versendet, sollten die Felder "Von" und "Betreff" der E-Mails etwa wie folgt festgelegt werden:
    
    From: marketing@contoso.com
    
    Betreff: Neuer, aktualisierter Katalog für die Weihnachtszeit! 
    
    Das folgende Beispiel zeigt, wie Sie es nicht machen sollten, da die Angaben nicht aussagekräftig sind:
    
    From: user@hotmail.com
    
    Betreff: Kataloge
    
8. **Wenn Sie eine Massensendung an zahlreiche Empfänger senden und die Nachricht ein Newsletterformat aufweist, sollte unten in der Nachricht mitgeteilt werden, wie der Newsletter abbestellt werden kann.**
    
    Die Option zum Abmelden sollte etwa folgendermaßen aussehen:
    
    Diese Nachricht wurde von "sender@fabrikam.com" an "example@contoso.com" geschickt. Profil/E-Mail-Adresse aktualisieren | Sofortige Abbestellung mit **SafeUnsubscribe** | Datenschutzerklärung
    
9. **Wenn Sie Massen-E-Mails versenden möchten, sollten Sie Empfänger in einem Anmeldungsverfahren in zwei Schritten in Ihre Liste aufnehmen. Dies ist eine branchenweit bewährte Methode.**
    
    Bei einem Anmeldungsverfahren in zwei Schritten muss ein Benutzer zwei Aktionen durchführen, um sich für die Marketing-E-Mails zu registrieren:
    
1. Zuerst muss der Benutzer auf ein zuvor deaktiviertes Kontrollkästchen klicken, um sich für weitere Angebote oder E-Mails von dem Händler anzumelden.
    
2. Dann sendet der Händler eine Bestätigungs-E-Mail an die E-Mail-Adresse, die der Benutzer bereitgestellt hat. Darin wird der Benutzer aufgefordert, auf einen zeitlich begrenzt gültigen Link zu klicken, um die Bestätigung abzuschließen.
    
    Ein Anmeldungsverfahren in zwei Schritten trägt zum guten Ruf eines Versenders von Massen-E-Mail bei.
    
10. **Massenversender sollten transparente Inhalte erstellen, für die sie zur Verantwortung gezogen werden können:**
    
1. Textpassagen, in denen die Empfänger aufgefordert werden, den Absender zum Adressbuch hinzuzufügen, sollten deutlich mitteilen, dass dies keine Übermittlungsgarantie darstellt.
    
2. Verwenden Sie bei der Erstellung von Umleitungen im Nachrichtentext ein konsistentes Format für die Links.
    
3. Senden Sie keine großen Bilder oder Anlagen und keine Nachrichten, die nur aus einem Bild bestehen.
    
4. Wenn Sie Nachverfolgungspixel (Web-Bugs oder Beacons) verwenden, machen Sie dies in Ihren öffentlichen Datenschutz- oder P3P-Einstellungen deutlich bekannt.
    
11. **Formatieren Sie ausgehende Benachrichtigungen über den Übermittlungsstatus.**
    
    Beim Generieren von Benachrichtigungen über den Übermittlungsstatus sollten Absender das Format für eine Unzustellbarkeitsnachricht verwenden, das in [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715) spezifiziert ist.
    
12. **Entfernen Sie E-Mail-Adressen, an die Nachrichten nicht zugestellt werden können, weil die Benutzer nicht vorhanden sind.**
    
    Wenn Sie einen Unzustellbarkeitsbericht erhalten, der anzeigt, dass eine E-Mail-Adresse nicht mehr verwendet wird, entfernen Sie den entsprechenden E-Mail-Alias von Ihrer Liste. E-Mail-Adressen ändern sich mit der Zeit, und manchmal verwerfen die Benutzer sie.
    
13. **Verwenden Sie das Hotmail-Programm Smart Network Data Services (SNDS).**
    
    Hotmail verwendet das Programm Smart Network Data Services, mit dem Absender Beschwerden von Endbenutzern überprüfen können. SNDS ist das primäre Portal für die Problembehandlung bei der Übermittlung an Hotmail.
    
## <a name="for-more-information"></a>Weitere Informationen

[Antispamschutz für Office 365-E-Mails](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[Listen sicherer und blockierter Absender in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)
  
[Rückläufernachrichten und EOP](backscatter-messages-and-eop.md)
  

