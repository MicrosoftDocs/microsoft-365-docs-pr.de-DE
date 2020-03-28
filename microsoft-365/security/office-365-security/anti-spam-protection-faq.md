---
title: Anti-Spam Protection in Office 365 FAQ
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 47970cd2f67873b3c8b1fbfa70b7e1754fc8359c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033494"
---
# <a name="anti-spam-protection-in-office-365-faq"></a>Anti-Spam Protection in Office 365 FAQ

Dieses Thema enthält häufig gestellte Fragen und Antworten zum Schutz vor Spam für Office 365 Kunden mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutz Kunden (EoP) ohne Exchange Online Postfächer.

Informationen zu Fragen und Antworten in Bezug auf Quarantäne finden Sie unter [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md).

## <a name="q-by-default-what-happens-to-a-spam-detected-message"></a>F: Was passiert standardmäßig mit einer Nachricht, die als Spam erkannt wird?

A: **Für eingehende Nachrichten:** Die Mehrzahl der Spam Daten werden über die Verbindungsfilterung gelöscht, die auf der IP-Adresse des Quell-e-Mail-Servers basiert. Anti-Spam-Richtlinien (auch bekannt als Spamfilter-oder Inhaltsfilter Richtlinien) überprüfen und Klassifizieren von Nachrichten als Spam, Massen-oder Phishing. Standardmäßig werden Nachrichten, die als Spam oder Massen klassifiziert werden, an den Junk-e-Mail-Ordner des Empfängers übermittelt, während Nachrichten, die als Phishing klassifiziert wurden, isoliert werden. Sie können die standardmäßige Anti-Spam-Richtlinie ändern (gilt für alle Empfänger), oder Sie können benutzerdefinierte Anti-Spam-Richtlinien mit strengeren Einstellungen für bestimmte Benutzergruppen erstellen (beispielsweise können Sie Spam in Quarantäne verlagern, die an Führungskräfte gesendet werden). Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md) und [Recommended Anti-Spam Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> In hybridbereitstellungen, bei denen EoP lokale Postfächer schützt, müssen Sie zwei Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) in Ihrer lokalen Exchange-Organisation konfigurieren, um die EoP-Spamfilter Kopfzeilen zu ermitteln, die Nachrichten hinzugefügt werden. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zur Zustellung von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **Für ausgehende Nachrichten:** Die Nachricht wird entweder über den risikoreichen [Zustellungs Pool](high-risk-delivery-pool-for-outbound-messages.md) weitergeleitet oder an den Absender in einem Unzustellbarkeitsbericht (auch als NDR-oder Bounce-Nachricht bezeichnet) zurückgegeben. Weitere Informationen zum Schutz vor ausgehenden Spamnachrichten finden Sie unter [Outbound Spam Controls in Office 365](outbound-spam-controls.md).

## <a name="q-whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>F: Was ist eine Zero-Day-Spam Variante und wie wird Sie von dem Dienst verarbeitet?

A: Bei einer Zero-Day-Spam-Variante handelt es sich um eine erste Generation, bisher unbekannte Spam-Variante, die nie erfasst oder analysiert wurde, sodass unsere Anti-Spam-Filter noch keine Informationen zur Erkennung verfügbar haben. Wenn ein Zero-Day-Spam Beispiel erfasst und von unseren Spam Analysten analysiert wird, wenn es die Kriterien für die Spam Klassifizierung erfüllt, werden unsere Anti-Spam-Filter aktualisiert, um Sie zu erkennen, und Sie werden nicht mehr als "Zero-Day" betrachtet.

**Hinweis:** Wenn Sie eine Nachricht erhalten, die möglicherweise eine NULL tägige Spam Variante ist, um den Dienst zu verbessern, senden Sie die Nachricht mit einer der unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschriebenen Methoden an Microsoft.

## <a name="q-do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>F: Muss ich den Dienst für Antispamschutz konfigurieren?

A: Nachdem Sie sich für den Dienst angemeldet und Ihre Domäne hinzugefügt haben, wird die Spamfilterung automatisch aktiviert. Standardmäßig ist die Spamfilterung optimiert, um Sie zu schützen, ohne zusätzliche Konfigurationsinformationen zu benötigen (abgesehen von der zuvor erwähnten Ausnahme für eigenständige EoP-eigenständige Kunden in Hybrid Umgebungen). Als Administrator können Sie die Standardeinstellungen für Spamfilterung bearbeiten, um die Anforderungen Ihrer Organisation optimal zu erfüllen. Um eine höhere Granularität zu erzielen, können Sie auch Antispam-und ausgehende Anti-Spam-Richtlinien erstellen, die auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation angewendet werden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Weitere Informationen hierzu finden Sie in den folgenden Themen:

[Empfohlene Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)

[Konfigurieren von Anti-Policy](configure-the-connection-filter-policy.md)

[Konfigurieren von Antispamrichtlinien in Office 365](configure-your-spam-filter-policies.md)

[Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md)

## <a name="q-if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>F: Wie lange dauert es, bis von mir vorgenommene Änderungen an einer Antivirusrichtlinie übernommen werden?

A: Es kann bis zu einer Stunde dauern, bis die Änderungen übernommen werden.

## <a name="q-is-bulk-email-filtering-automatically-enabled"></a>F: Ist die Filterung von Massen-E-Mails automatisch aktiviert?

A. Ja. Weitere Informationen zu Massen-e-Mails finden Sie unter [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="q-does-the-service-provide-url-filtering"></a>F: Bietet der Dienst die URL-Filterung?

A: Ja, der Dienst verfügt über einen URL-Filter, der nach Nachrichten nach URLs sucht. Mit bekannten Spam- oder nicht sicheren Inhalten verbundene URLs werden erkannt und die Nachrichten anschließend als Spam markiert.

## <a name="q-how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>F: Wie können Kunden den Dienst verwenden, um falsch negative Ergebnisse (Spam) und falsch positive Ergebnisse (kein Spam) an Microsoft zu senden?

A: Es gibt verschiedene Möglichkeiten, Spamnachrichten und Nachrichten, die kein Spam sind, zur Analyse an Microsoft zu übermitteln. Weitere Informationen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-can-i-get-spam-reports"></a>F: Kann ich Spamberichte abrufen?

A: Ja, beispielsweise können Sie einen Spam Erkennungs Bericht im Microsoft 365 Admin Center erhalten. Dieser Bericht weist das Spamvolumen als Anzahl eindeutiger Nachrichten aus. Weitere Informationen zur Berichterstellung finden Sie unter den folgenden Themen:

Exchange Online Kunden: [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Eigenständige EoP-Kunden: [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Schutz](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="q-someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>F: Jemand hat mir eine Nachricht geschickt und ich kann Sie nicht finden. Ich vermute, dass sie als Spam erkannt wurde. Gibt es ein Tool, mit dem ich das herausfinden kann?

A: Ja, mit dem Tool für die Nachrichtenablaufverfolgung können Sie e-Mail-Nachrichten verfolgen, während Sie den Dienst durchlaufen, um herauszufinden, was mit Ihnen geschehen ist. Weitere Informationen zur Verwendung des Nachrichtenablauf Verfolgungs Tools, um herauszufinden, warum eine Nachricht als Spam gekennzeichnet wurde, finden Sie unter [war eine Nachricht als Spam gekennzeichnet?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="q-will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>F: Schränkt der Dienst meine E-Mail ein (begrenzt ihre Rate), wenn die Benutzer ausgehenden Spam senden?

A. Wenn mehr als der Hälfte der von einem Benutzer über den Dienst in einem bestimmten Zeitraum (z. B. in der Stunde) gesendeten E-Mails von Office 365 als Spam eingestuft werden, wird dieser Benutzer für das Senden von Nachrichten blockiert. Wenn eine ausgehende Nachricht als Spam identifiziert wird, wird sie in den meisten Fällen durch den Pool für besonders riskante Zustellungen geleitet, der die Wahrscheinlichkeit reduziert, dass der normale Pool für ausgehende IP-Adressen einer Liste blockierter IP-Adressen hinzugefügt wird.

Sie können eine Benachrichtigung an eine angegebene E-Mail-Adresse senden, wenn ein Absender für das Senden ausgehender Spamnachrichten blockiert wird. Weitere Informationen zu dieser Einstellung finden Sie unter [Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md).

## <a name="q-can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>F: Kann ich eine Drittanbieterlösung zum Schutz vor Antispam- und Antischadsoftware zusammen mit Exchange Online einsetzen?

A. Ja. Obwohl empfohlen wird, den MX-Eintrag auf Office 365 zu setzen, stellen wir fest, dass es legitime geschäftliche Gründe gibt, Ihre e-Mails an einen anderen Ort als Office 365 weiterzuleiten.

- **Eingehend**: Ändern Sie Ihre MX-Einträge so, dass Sie auf den Drittanbieter verweisen, und leiten Sie die Nachrichten dann zur weiteren Verarbeitung an EoP um. Weitere Informationen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Ausgehend **: Configure**Smart Host Routing from Office 365 to the Destination Third-Party Provider.

## <a name="q-does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>F: Bietet Microsoft Informationen, wie ich mich gegen betrügerische Phishing-Versuche schützen kann?

A. Ja. Weitere Informationen finden Sie unter [Schützen Ihrer Daten im Internet](https://support.microsoft.com/help/4091455)

## <a name="q-are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>F: Werden Spam- und Malwarenachrichten darauf untersucht, wer sie gesendet hat, oder werden sie an Strafverfolgungsbehörden weitergeleitet?

A. Der Dienst dient in erster Linie zum Erkennen und Entfernen von Spam und Malware. Wir untersuchen gelegentlich jedoch besonders gefährlichen oder schädlichen Spam bzw. Angriffe genauer und verfolgen die Täter. Hierzu arbeiten wir gegebenenfalls auch mit unseren Rechtsabteilungen und Abteilungen zum Schutz vor Computerkriminalität zusammen, um ein Spammer-Botnet zu zerschlagen, den Spammer an der Verwendung des Dienstes zu hindern (wenn er den Dienst zum Senden von E-Mails verwendet) und die Informationen an die Strafverfolgungsbehörden weiterzugeben.

## <a name="q-what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>F: Mit welchen bewährten Methoden für das Senden ausgehender E-Mails kann ich sicherstellen, dass meine E-Mails zugestellt werden?

A. Die unten aufgeführten Richtlinien beschreiben bewährte Methoden für das Senden ausgehender E-Mails.

- **Die Quell-e-Mail-Domäne sollte in DNS aufgelöst werden.**

  Wenn der Absender beispielsweise User@Fabrikam ist, wird die Domäne Fabrikam in die IP-Adresse 192.0.43.10 aufgelöst.
  
  Wenn eine sendende Domäne nicht über einen A-Eintrag und nicht über einen MX-Eintrag in DNS verfügt, leitet der Dienst die Nachricht stets durch den Pool für besonders riskante Zustellungen, unabhängig davon, ob es sich bei ihrem Inhalt um Spam handelt. Weitere Informationen zum Pool mit höherem Risiko für Zustellungen finden Sie unter [risikoreichen Zustellungs Pool für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).

- **Ausgehende e-Mail-eServer sollten einen Reverse-DNS-Eintrag (PTR) aufweisen.**

  Wenn die e-Mail-Quell-IP-Adresse beispielsweise 192.0.43.10 lautet, lautet der `43-10.any.icann.org`Reverse-DNS-Eintrag ".

- **Die Befehle HELO/EHLO und MAIL FROM sollten konsistent sein und in Form eines Domänennamens vorliegen, nicht in Form einer IP-Adresse.**

  Der Befehl HELO/EHLO sollte so konfiguriert sein, dass er dem Reverse-DNS der Absender-IP-Adresse entspricht, sodass die Domäne in allen Teilen des Nachrichtenkopfs gleich ist.

- **Stellen Sie sicher, dass ordnungsgemäße SPF-Einträge im DNS eingerichtet sind.**

  Bei SPF-Einträgen handelt es sich um einen Mechanismus, mit dem überprüft wird, ob von einer Domäne gesendete E-Mails wirklich von dieser Domäne stammen und kein Spoofing vorliegt. Weitere Informationen zu SPF-Einträgen finden Sie unter den folgenden Links:

  [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Häufig gestellte Fragen zu Domänen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Wenn Sie E-Mails mit DKIM signieren, melden Sie sich mit eingeschränkter Kanonisierung an.**

  Wenn ein Absender seine Nachrichten mit DKIM (Domain Keys Identified Mail) signieren und ausgehende E-Mails über den Dienst senden möchte, sollte er sich mit dem Algorithmus für die eingeschränkte Kanonisierung der Kopfzeilen anmelden. Wenn Sie sich mit strenger Kanonisierung der Kopfzeilen anmelden, wird die Signatur beim Durchlaufen des Diensts möglicherweise als ungültig erklärt.

- **Domänenbesitzer sollten über korrekte Informationen in der WHOIS-Datenbank verfügen.**

  Mit diesen wird identifiziert, wem die Domäne gehört und wie die Besitzer kontaktiert werden können, indem das übergeordnete Unternehmen, der Kontakt und die Namenserver eingegeben werden.

- **Bei Absendern von Massen-E-Mails sollte der Name unter "Von:" zeigen, wer der Absender ist, und der Betreff der Nachricht sollte kurz zusammenfassen, um was es geht.**

  Der Nachrichtentext sollte das Angebot, den Dienst oder das Produkt klar erkennen lassen. Wenn ein Absender zum Beispiel eine Massensendung vom Unternehmen Contoso aus versendet, sollten die Felder "Von" und "Betreff" der E-Mails etwa wie folgt festgelegt werden:

  > From: marketing@contoso.com <br/> Betreff: Neuer, aktualisierter Katalog für die Weihnachtszeit!

  Das folgende Beispiel zeigt, wie Sie es nicht machen sollten, da die Angaben nicht aussagekräftig sind:

  > From: user@hotmail.com <br/> Betreff: Kataloge

- **Wenn Sie eine Massensendung an zahlreiche Empfänger senden und die Nachricht ein Newsletterformat aufweist, sollte unten in der Nachricht mitgeteilt werden, wie der Newsletter abbestellt werden kann.**

  Die Option zum Abmelden sollte etwa folgendermaßen aussehen:

  > Diese Nachricht wurde von "sender@fabrikam.com" an "example@contoso.com" geschickt. Profil aktualisieren/e-Mail-Adresse | Sofortige Entfernung mit **SafeUnsubscribe** &trade; | Datenschutzrichtlinie

- **Wenn Sie Massen-E-Mails versenden möchten, sollten Sie Empfänger in einem Anmeldungsverfahren in zwei Schritten in Ihre Liste aufnehmen. Dies ist eine branchenweit bewährte Methode.**

  Bei einem Anmeldungsverfahren in zwei Schritten muss ein Benutzer zwei Aktionen durchführen, um sich für die Marketing-E-Mails zu registrieren:

  1. Zuerst muss der Benutzer auf ein zuvor deaktiviertes Kontrollkästchen klicken, um sich für weitere Angebote oder E-Mails von dem Händler anzumelden.

  2. Dann sendet der Händler eine Bestätigungs-E-Mail an die E-Mail-Adresse, die der Benutzer bereitgestellt hat. Darin wird der Benutzer aufgefordert, auf einen zeitlich begrenzt gültigen Link zu klicken, um die Bestätigung abzuschließen.

  Ein Anmeldungsverfahren in zwei Schritten trägt zum guten Ruf eines Versenders von Massen-E-Mail bei.

- **Massenversender sollten transparente Inhalte erstellen, für die sie zur Verantwortung gezogen werden können:**

  1. Textpassagen, in denen die Empfänger aufgefordert werden, den Absender zum Adressbuch hinzuzufügen, sollten deutlich mitteilen, dass dies keine Übermittlungsgarantie darstellt.

  2. Verwenden Sie bei der Erstellung von Umleitungen im Nachrichtentext ein konsistentes Format für die Links.

  3. Senden Sie keine großen Bilder oder Anlagen und keine Nachrichten, die nur aus einem Bild bestehen.

  4. Wenn Sie Nachverfolgungspixel (Web-Bugs oder Beacons) verwenden, machen Sie dies in Ihren öffentlichen Datenschutz- oder P3P-Einstellungen deutlich bekannt.

- **Formatieren Sie ausgehende Unzustellbarkeitsnachrichten.**

  Beim Generieren von Benachrichtigungen über den Zustellungsstatus (auch als Unzustellbarkeitsberichte, Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) sollten Absender dem Format eines Bounces entsprechen, wie in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)angegeben.

- **Entfernen Sie E-Mail-Adressen, an die Nachrichten nicht zugestellt werden können, weil die Benutzer nicht vorhanden sind.**

  Wenn Sie einen Unzustellbarkeitsbericht erhalten, der anzeigt, dass eine E-Mail-Adresse nicht mehr verwendet wird, entfernen Sie den entsprechenden E-Mail-Alias von Ihrer Liste. E-Mail-Adressen ändern sich mit der Zeit, und manchmal verwerfen die Benutzer sie.

- **Verwenden Sie das Hotmail-Programm Smart Network Data Services (SNDS).**

  Hotmail verwendet das Programm Smart Network Data Services, mit dem Absender Beschwerden von Endbenutzern überprüfen können. SNDS ist das primäre Portal für die Problembehandlung bei der Übermittlung an Hotmail.
