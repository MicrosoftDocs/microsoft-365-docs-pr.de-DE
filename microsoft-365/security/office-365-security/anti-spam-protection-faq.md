---
title: Häufig gestellte Fragen zum Antispamschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können häufig gestellte Fragen und Antworten zum Antispamschutz in Exchange Online Protection (EOP) anzeigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae91e1184d8b95b936065f785b3c6bfecf9f250f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206874"
---
# <a name="anti-spam-protection-faq"></a>Häufig gestellte Fragen zum Antispamschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Dieses Thema enthält häufig gestellte Fragen und Antworten zum Schutz vor Schadsoftware für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.

Informationen zu Fragen und Antworten in Bezug auf Quarantäne finden Sie unter [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum Schutz [vor Schadsoftware.](anti-malware-protection-faq-eop.md)

Fragen und Antworten zum Schutz vor Spoofing finden Sie unter Häufig gestellte Fragen zum Schutz [vor Spoofing.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Was passiert standardmäßig mit einer Nachricht, die als Spam erkannt wird?

**Für eingehende Nachrichten:** Der Großteil des Spams wird über die Verbindungsfilterung gelöscht, die auf der IP-Adresse des Quell-E-Mail-Servers basiert. Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bezeichnet) prüfen und klassifizieren Nachrichten als Spam, Massen oder Phishing. Standardmäßig werden Nachrichten, die als Spam oder Massennachrichten klassifiziert sind, an den Junk-E-Mail-Ordner des Empfängers zugestellt, während Nachrichten, die als Phishing klassifiziert sind, in Quarantäne gestellt werden. Sie können die Standardmäßige Antispamrichtlinie ändern (gilt für alle Empfänger), oder Sie können benutzerdefinierte Antispamrichtlinien mit strengeren Einstellungen für bestimmte Benutzergruppen erstellen (Sie können z. B. Spam unter Quarantäne stellen, der an Führungskräfte gesendet wird). Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien](configure-your-spam-filter-policies.md) und [Empfohlene Antispamrichtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> In Hybridbereitstellungen, in denen EOP lokale Postfächer schützt, müssen Sie zwei Exchange-Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in Ihrer lokalen Exchange-Organisation konfigurieren, um die EOP-Spamfilterheader zu erkennen, die Nachrichten hinzugefügt werden. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **Für ausgehende Nachrichten:** Die Nachricht wird entweder [](high-risk-delivery-pool-for-outbound-messages.md) über den Pool mit hohem Risiko geroutet oder in einem Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bekannt) an den Absender zurückgegeben. Weitere Informationen zum Schutz ausgehender Spamnachrichten finden Sie unter [Outbound spam controls](outbound-spam-controls.md).

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Was ist eine Zero-Day-Spamvariante und wie wird sie vom Dienst behandelt?

Eine Zero-Day-Spamvariante ist eine bisher unbekannte Variante von Spam der ersten Generation, die nie erfasst oder analysiert wurde. Daher stehen unseren Antispamfiltern noch keine Informationen zum Erkennen zur Verfügung. Nachdem ein Zero-Day-Spambeispiel von unseren Spamanalysten erfasst und analysiert wurde, werden unsere Antispamfilter aktualisiert, um sie zu erkennen, wenn es die Spamklassifizierungskriterien erfüllt, und es wird nicht mehr als "Zero-Day" betrachtet.

**Hinweis:** Wenn Sie eine Nachricht erhalten, die eine Zero-Day-Spamvariante sein kann, um uns bei der Verbesserung des Diensts zu unterstützen, übermitteln Sie die Nachricht bitte mithilfe einer der unter Melden von Nachrichten und Dateien an Microsoft beschriebenen Methoden an [Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Muss ich den Dienst für Antispamschutz konfigurieren?

Nachdem Sie sich für den Dienst registrieren und Ihre Domäne hinzugefügt haben, wird die Spamfilterung automatisch aktiviert. Standardmäßig ist die Spamfilterung so abgestimmt, dass Sie ohne zusätzliche Konfiguration geschützt werden (abgesehen von der zuvor erwähnten Ausnahme für eigenständige EOP-eigenständige Kunden in Hybridumgebungen). Als Administrator können Sie die Standardmäßigen Spamfiltereinstellungen bearbeiten, um die Anforderungen Ihrer Organisation optimal zu erfüllen. Für eine höhere Granularität können Sie auch Antispamrichtlinien und ausgehende Antispamrichtlinien erstellen, die auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation angewendet werden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Weitere Informationen finden Sie in den folgenden Themen:

[Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365-Sicherheit](recommended-settings-for-eop-and-office365.md)

[Konfigurieren der Verbindungsfilterung in EOP](configure-the-connection-filter-policy.md)

[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)

[Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Wie lange dauert es, bis von mir vorgenommene Änderungen an einer Antivirusrichtlinie übernommen werden?

Es kann bis zu einer Stunde dauern, bis die Änderungen übernommen werden.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Ist die Filterung von Massen-E-Mails automatisch aktiviert?

Ja. Weitere Informationen zu Massen-E-Mails finden Sie unter Was ist der Unterschied zwischen Junk-E-Mails [und Massen-E-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="does-the-service-provide-url-filtering"></a>Bietet der Dienst die URL-Filterung?

Ja, der Dienst verfügt über einen URL-Filter, der in Nachrichten nach URLs sucht. Mit bekannten Spam- oder nicht sicheren Inhalten verbundene URLs werden erkannt und die Nachrichten anschließend als Spam markiert.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Wie können Kunden den Dienst verwenden, um falsch negative Ergebnisse (Spam) und falsch positive Ergebnisse (kein Spam) an Microsoft zu senden?

Es gibt verschiedene Möglichkeiten, Spamnachrichten und Nachrichten, die kein Spam sind, zur Analyse an Microsoft zu übermitteln. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kann ich Spamberichte abrufen?

Ja, Sie können beispielsweise einen Spamerkennungsbericht im Microsoft 365 Admin Center erhalten. Dieser Bericht weist das Spamvolumen als Anzahl eindeutiger Nachrichten aus. Weitere Informationen zur Berichterstellung finden Sie unter den folgenden Themen:

Exchange Online-Kunden: [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](/exchange/monitoring/monitoring)

Eigenständige EOP-Kunden: [Berichterstellung und Nachrichtenverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Jemand hat mir eine Nachricht gesendet, und ich kann sie nicht finden. Ich vermute, dass sie als Spam erkannt wurde. Gibt es ein Tool, mit dem ich das herausfinden kann?

Ja, mit dem Tool für die Nachrichtenverfolgung können Sie E-Mail-Nachrichten beim Passieren des Diensts verfolgen, um herauszufinden, was mit ihnen passiert ist. Weitere Informationen zur Verwendung des Nachrichtenverfolgungstools, um herauszufinden, warum eine Nachricht als Spam gekennzeichnet wurde, finden Sie unter Wurde eine Nachricht [als Spam markiert?](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Schränkt der Dienst meine E-Mail ein (begrenzt ihre Rate), wenn die Benutzer ausgehenden Spam senden?

Wenn mehr als die Hälfte der E-Mails, die von einem Benutzer über den Dienst innerhalb eines bestimmten Zeitrahmens (z. B. pro Stunde) gesendet werden, von EOP als Spam erkannt wird, wird der Benutzer am Senden von Nachrichten blockiert. Wenn eine ausgehende Nachricht als Spam identifiziert wird, wird sie in den meisten Fällen durch den Pool für besonders riskante Zustellungen geleitet, der die Wahrscheinlichkeit reduziert, dass der normale Pool für ausgehende IP-Adressen einer Liste blockierter IP-Adressen hinzugefügt wird.

Sie können eine Benachrichtigung an eine angegebene E-Mail-Adresse senden, wenn ein Absender für das Senden ausgehender Spamnachrichten blockiert wird. Weitere Informationen zu dieser Einstellung finden Sie unter [Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md).

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kann ich eine Drittanbieterlösung zum Schutz vor Antispam- und Antischadsoftware zusammen mit Exchange Online einsetzen?

Ja. Es wird zwar empfohlen, Ihren MX-Eintrag auf Microsoft zu verweisen, es gibt jedoch berechtigte geschäftliche Gründe, Ihre E-Mails zuerst an einen anderen Ort als Microsoft weiter zu senden.

- **Eingehenden :** Ändern Sie Ihre MX-Einträge so, dass sie auf den Drittanbieter verweisen, und leiten Sie die Nachrichten dann zur weiteren Verarbeitung an EOP weiter. Weitere Informationen finden Sie unter [Erweiterte Filterung für Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Ausgehend:** Konfigurieren Sie das Smarthostrouting von Microsoft 365 zum Zielanbieter eines Drittanbieters.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Bietet Microsoft Informationen, wie ich mich gegen betrügerische Phishing-Versuche schützen kann?

Ja. Weitere Informationen finden Sie unter [Schützen Ihrer Privatsphäre im Internet](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Werden Spam- und Malwarenachrichten darauf untersucht, wer sie gesendet hat, oder werden sie an Strafverfolgungsbehörden weitergeleitet?

Der Dienst konzentriert sich auf die Erkennung und Entfernung von Spam und Schadsoftware, wobei wir gelegentlich besonders gefährliche oder schädliche Spam- oder Angriffskampagnen untersuchen und die Angreifer verfolgen können. Dies kann die Zusammenarbeit mit unseren einheiten für rechtliche und digitale Straftaten umfassen, um ein Spammer-Botnet zu verwenden, den Spammer an der Verwendung des Diensts zu blockieren (wenn er ihn zum Senden ausgehender E-Mails verwendet) und die Informationen zur Strafverfolgung an die Strafverfolgungsbehörden weiter zu übergeben.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Mit welchen bewährten Methoden für das Senden ausgehender E-Mails kann ich sicherstellen, dass meine E-Mails zugestellt werden?

Die unten aufgeführten Richtlinien beschreiben bewährte Methoden für das Senden ausgehender E-Mails.

- **Die Quell-E-Mail-Domäne sollte in DNS aufgelöst werden.**

  Wenn der Absender beispielsweise user@fabrikam wird, wird die Domäne fabrikam in die IP-Adresse 192.0.43.10 aufgelöst.

  Wenn eine sendende Domäne nicht über einen A-Eintrag und nicht über einen MX-Eintrag in DNS verfügt, leitet der Dienst die Nachricht stets durch den Pool für besonders riskante Zustellungen, unabhängig davon, ob es sich bei ihrem Inhalt um Spam handelt. Weitere Informationen zum Pool für die Bereitstellung mit höherem Risiko finden Sie unter [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).

- **Der E-Mail-Server für ausgehende E-Mails sollte über einen Reverse-DNS-Eintrag (Reverse DNS, PTR) verfügen.**

  Wenn beispielsweise die E-Mail-Quell-IP-Adresse 192.0.43.10 ist, wäre der umgekehrte DNS-Eintrag `43-10.any.icann.org` ."

- **Die Befehle HELO/EHLO und MAIL FROM sollten konsistent sein und in Form eines Domänennamens vorliegen, nicht in Form einer IP-Adresse.**

  Der Befehl HELO/EHLO sollte so konfiguriert sein, dass er dem Reverse-DNS der Absender-IP-Adresse entspricht, sodass die Domäne in allen Teilen des Nachrichtenkopfs gleich ist.

- **Stellen Sie sicher, dass ordnungsgemäße SPF-Einträge im DNS eingerichtet sind.**

  Bei SPF-Einträgen handelt es sich um einen Mechanismus, mit dem überprüft wird, ob von einer Domäne gesendete E-Mails wirklich von dieser Domäne stammen und kein Spoofing vorliegt. Weitere Informationen zu SPF-Einträgen finden Sie unter den folgenden Links:

  [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Häufig gestellte Fragen zu Domänen](../../admin/setup/domains-faq.yml#how-can-i-validate-spf-records-for-my-domain)

- **Wenn Sie E-Mails mit DKIM signieren, melden Sie sich mit eingeschränkter Kanonisierung an.**

  Wenn ein Absender seine Nachrichten mit DKIM (Domain Keys Identified Mail) signieren und ausgehende E-Mails über den Dienst senden möchte, sollte er sich mit dem Algorithmus für die eingeschränkte Kanonisierung der Kopfzeilen anmelden. Wenn Sie sich mit strenger Kanonisierung der Kopfzeilen anmelden, wird die Signatur beim Durchlaufen des Diensts möglicherweise als ungültig erklärt.

- **Domänenbesitzer sollten über korrekte Informationen in der WHOIS-Datenbank verfügen.**

  Mit diesen wird identifiziert, wem die Domäne gehört und wie die Besitzer kontaktiert werden können, indem das übergeordnete Unternehmen, der Kontakt und die Namenserver eingegeben werden.

- **Bei Absendern von Massen-E-Mails sollte der Name unter "Von:" zeigen, wer der Absender ist, und der Betreff der Nachricht sollte kurz zusammenfassen, um was es geht.**

  Der Nachrichtentext sollte das Angebot, den Dienst oder das Produkt klar erkennen lassen. Wenn ein Absender zum Beispiel eine Massensendung vom Unternehmen Contoso aus versendet, sollten die Felder "Von" und "Betreff" der E-Mails etwa wie folgt festgelegt werden:

  > From: marketing@contoso.com <br> Betreff: Neuer, aktualisierter Katalog für die Weihnachtszeit!

  Das folgende Beispiel zeigt, wie Sie es nicht machen sollten, da die Angaben nicht aussagekräftig sind:

  > From: user@hotmail.com <br> Betreff: Kataloge

- **Wenn Sie eine Massensendung an zahlreiche Empfänger senden und die Nachricht ein Newsletterformat aufweist, sollte unten in der Nachricht mitgeteilt werden, wie der Newsletter abbestellt werden kann.**

  Die Option zum Abmelden sollte etwa folgendermaßen aussehen:

  > Diese Nachricht wurde von "sender@fabrikam.com" an "example@contoso.com" geschickt. Aktualisieren von Profil-/E-Mail-| Sofortiges Entfernen mit **SafeUnsubscribe** &trade; | Datenschutzrichtlinien

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

- **Formatieren ausgehender Unzustellbarkeitsnachrichten.**

  Beim Generieren von Zustellungsstatusbenachrichtigungen (auch als Unzustellbarkeitsberichte, Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) sollten Absender das Format einer Unzustellbarkeit wie in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)angegeben befolgen.

- **Entfernen Sie E-Mail-Adressen, an die Nachrichten nicht zugestellt werden können, weil die Benutzer nicht vorhanden sind.**

  Wenn Sie einen Unzustellbarkeitsbericht erhalten, der anzeigt, dass eine E-Mail-Adresse nicht mehr verwendet wird, entfernen Sie den entsprechenden E-Mail-Alias von Ihrer Liste. E-Mail-Adressen ändern sich mit der Zeit, und manchmal verwerfen die Benutzer sie.

- **Verwenden Sie das Hotmail-Programm Smart Network Data Services (SNDS).**

  Hotmail verwendet das Programm Smart Network Data Services, mit dem Absender Beschwerden von Endbenutzern überprüfen können. SNDS ist das primäre Portal für die Problembehandlung bei der Übermittlung an Hotmail.