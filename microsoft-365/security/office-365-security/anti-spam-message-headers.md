---
title: Antispam-Nachrichtenkopfzeilen
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Nachrichtenkopfzeilen und die Werte, die Nachrichten von Exchange Online Protection hinzugefügt werden.
ms.openlocfilehash: 7a89a5dc0c05bd390669b5008b9d589a89488171
ms.sourcegitcommit: b0396171d24c6298b809b43bb109d3afed4de5b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37451117"
---
# <a name="anti-spam-message-headers"></a>Antispam-Nachrichtenkopfzeilen

Wenn Exchange Online Protection eingehende E-Mail-Nachrichten prüft, wird jeder Nachricht die Kopfzeile **X-Forefront-Antispam-Report** hinzugefügt. Mit den Feldern in dieser Kopfzeile können Administratoren Information zur Nachricht und deren Verarbeitung bereitgestellt werden. Die Felder in der Kopfzeile **X-Microsoft-Antispam** liefern zusätzliche Informationen über Massensendungen und Phishing. Zusätzlich zu diesen beiden Kopfzeilen fügt Exchange Online Protection auch E-Mail-Authentifizierungsergebnisse für jede verarbeitete Nachricht in die Kopfzeile **Authentication-results** ein.

Informationen dazu, wie Sie einen E-Mail-Nachrichtenkopf in verschiedenen E-Mail-Clients anzeigen, finden Sie unter [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).

> [!TIP]
> Sie können den Inhalt einer Nachrichtenkopfzeile kopieren und in das Tool [Message Analyzer](https://testconnectivity.microsoft.com/?tabid=mha) einfügen. Mit diesem Tool können Sie Kopfzeilen analysieren und in ein besser lesbares Format umwandeln.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Forefront-Antispam-Report

Suchen Sie nach dem Zugriff auf die Nachrichtenkopfzeileninformationen nach **X-Forefront-Antispam-Report**, und suchen Sie nach den folgenden Feldern: Andere Felder in dieser Kopfzeile werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

|**Kopfzeilenfeld**|**Beschreibung**|
|:-----|:-----|
|CIP: \[IP-Adresse\]|Die IP-Verbindungsadresse. Sie sollten diese IP-Adresse angeben, wenn Sie im Verbindungsfilter eine IP-Zulassungsliste oder eine Liste für geblockte IP-Adressen erstellen. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilterrichtlinie](configure-the-connection-filter-policy.md).  |
|CTRY|Das Land, aus dem die Nachricht mit dem Dienst verbunden wurde. Es wird anhand der Verbindungs-IP-Adresse ermittelt, die nicht notwendigerweise mit der ursprünglichen Sende-IP-Adresse übereinstimmen muss.|
|LANG|Die Sprache, in der die Nachricht verfasst wurde, wie im Ländercode angegeben (z. B. ru_RU für Russisch).|
|SCL|Die SCL-Bewertung (Spam Confidence Level) einer Nachricht. Weitere Informationen zur Interpretation dieser Werte finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).  |
|PCL|Der PCL-Wert (Phishing Confidence Level) der Nachricht.|
|SRV:BULK|Die Nachricht wurde als Massen-E-Mail identifiziert. Ist die erweiterte Spamfilteroption **Alle Massen-E-Mail-Nachrichten sperren** aktiviert, wird sie als Spam markiert. Ist die nicht aktiviert, wird sie nur dann als Spam markiert, wenn der Rest der Filterungsregeln festlegt, dass es sich bei der Nachricht um Spam handelt.|
|SFV:SFE|Filterung wurde übersprungen, und die Nachricht wurde durchgelassen, da sie von einem Absender aus der Liste mit sicheren Absendern stammt.|
|SFV:BLK|Filterung wurde übersprungen, und die Nachricht wurde blockiert, da sie von einem Absender aus der Liste mit blockierten Absendern stammt.  <br/> **Tipp**: Weitere Informationen zum Erstellen von Listen mit sicheren oder blockierten Absendern finden Sie unter [Sperren oder Zulassen (Junk-E-Mail-Einstellungen)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook im Web) und [Übersicht über den Junk-E-Mail-Filter](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).|
|IPV:CAL|Die Nachricht wurde durch die Spam-Filter gelassen, weil die IP-Adrese in einer IP-Zulassungsliste im Verbindungsfilter angegeben wurde.|
|IPV:NLI|Die IP-Adresse war nicht in einer IP-Zuverlässigkeitsliste aufgeführt.|
|SFV:SPM|Die Nachricht wurde vom Inhaltsfilter als Spam markiert.|
|SFV:SKS|Die Nachricht wurde bereits als Spam markiert, noch bevor sie vom Inhaltsfilter verarbeitet wurde Dies beinhaltet Nachrichten, bei denen die Nachricht einer Nachrichtenflussregel (auch als Transportregel bezeichnet) entsprach, die diese automatisch als Spam markiert und alle zusätzlichen Filterungen umgeht.|
|SFV:SKA|Die Nachricht hat das Filtern übersprungen und wurde im Posteingang zugestellt, da sie einer Zulassenliste in der Richtlinie für den Spamfilter entsprach, wie z. B. die Liste **Absender zulassen**.|
|SFV:SKB|Die Nachricht wurde als Spam markiert, da sie einer Sperrliste in der Richtlinie für den Spamfilter entsprach, wie z. B. die Liste **Absender blockieren**.|
|SFV:SKN|Die Nachricht wurde bereits als Nicht-Spam markiert, noch bevor sie vom Inhaltsfilter verarbeitet wurde. Dies beinhaltet Nachrichten, bei denen die Nachricht einer Nachrichtenflussregel entsprach, die diese automatisch als Nicht-Spam markiert und alle zusätzlichen Filterungen umgeht.|
|SFV:SKI|Ähnlich wie SFV:SKN, die Filterung der Nachricht wurde aus einem anderen Grund übersprungen, wie eine unternehmensinterne E-Mail innerhalb einer Mandantenstruktur.|
|SFV:SKQ|Die Nachricht wurde aus der Quarantäne freigegeben und an die vorgesehenen Empfänger gesendet.|
|SFV:NSPM|Die Nachricht wurde als "Nicht-Spam" markiert und an die vorgesehenen Empfänger gesendet.|
|H: \[HELI-String\]|Die Zeichenfolge HELO oder EHLO des verbundenen E-Mail-Servers.|
|PTR: \[ReverseDNS\]|Der PTR-Eintrag (bzw. der Zeigereintrag) der Absender-IP-Adresse, auch als Reverse-DNS-Adresse bezeichnet.|
|CAT:|Die Kategorie der Schutzrichtlinie, die auf die Nachricht angewendet wurde: <br/>MALW: Malware <br/>PHSH: Phishing <br/>HSPM: Spam mit hoher Vertrauenswürdigkeit <br/>SPOOF: Spoofing <br/>SPM: Spam <br/>BULK: Massenaktion <br/>DIMP: Domänenidentitätswechsel <br/>UIMP: Benutzeridentitätswechsel <br/>Möglicherweise wird eine eingehende Nachricht durch mehrere Schutzformen und mehrere Erkennungsscans gekennzeichnet. Richtlinien haben unterschiedliche Prioritäten, und die Richtlinie mit der höchsten Priorität wird angewendet. Ziehen Sie [Welche Richtlinie gilt, wenn mehrere Schutzmethoden und Erkennungsscans für Ihre E-Mails ausgeführt werden?](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-policies-and-protections-are-combined) zurate.|
|SFTY|Die Nachricht wurde als Phishing-E-Mail erkannt und wird außerdem mit einem der folgenden Werte gekennzeichnet: <br/>9.1: Standardwert. Die Nachricht enthält eine Phishing-URL, kann weitere Phishinginhalte enthalten oder wurde möglicherweise vor der Weiterleitung an Office 365 von einem anderen E-Mail-Filter (z. B. einer lokalen Version von Exchange Server) als Phishing-E-Mail gekennzeichnet. <br/>9.11: Nachricht hat Antispoofing-Überprüfungen nicht bestanden, wobei die Absenderdomäne in der "From:"-Kopfzeile mit der Empfängerdomäne übereinstimmt oder Teil der gleichen Organisation ist. Dies weist auf organisationsinternes Spoofing hin. Ein Sicherheitstipp wird hinzugefügt. <br/>9.19: Nachricht hat Domänenidentitätswechsel-Überprüfungen nicht bestanden, wobei die Absenderdomäne versucht, die Identität einer Domäne des Empfängers oder einer benutzerdefinierten, von der Antiphishing-Richtlinie geschützten Domäne anzunehmen. Dies weist auf einen Identitätswechsel hin. Ein Sicherheitstipp wird zur Nachricht hinzugefügt, wenn dies über die Antiphishing-Richtlinie aktiviert ist. <br/>9.20: Nachricht hat Benutzeridentitätswechsel-Überprüfungen nicht bestanden, wobei der sendende Benutzer versucht, die Identität eines Benutzers innerhalb der Organisation des Empfängers oder eines benutzerdefinierten, von der Antiphishing-Richtlinie geschützten Benutzers anzunehmen. Dies weist auf einen Identitätswechsel hin. Ein Sicherheitstipp wird zur Nachricht hinzugefügt, wenn dies über die Antiphishing-Richtlinie aktiviert ist. <br/>9.21: Nachricht hat Antispoofing-Überprüfungen nicht bestanden, wobei die Absenderdomäne in der "From:"-Kopfzeile sich nicht authentifiziert und aus einer externen Domäne stammt. Wird in Kombination mit CompAuth verwendet (siehe Authentifizierungsergebnisse). <br/>9.22: identisch mit 9.21, außer dass der Benutzer über ein sicherer Absender ist, der überschrieben wurde. <br/>9.23: identisch mit 9.22, außer dass die Organisation über einen zulässigen Absender oder eine zulässige Domäne verfügt, die überschrieben wurde. <br/>9.24: identisch mit 9.23, außer dass der Benutzer über eine Exchange-Nachrichtenflussregel verfügt, die überschrieben wurde.|
|X-CustomSpam: \[ASFOption\]|Die Nachricht stimmte mit einer erweiterten Spamfilteroption überein. So bedeutet z. B. **X-CustomSpam: Bildlinks zu Remotestandorten**, dass eine Übereinstimmung mit der ASF-Option **Bildlinks zu Remotestandorten** besteht. Informationen dazu, welcher X-Headertext für die jeweilige ASF-Funktion hinzugefügt wird, finden Sie unter [Erweiterte Optionen für die Spamfilterung](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Microsoft-Antispam

In der folgenden Tabelle werden die hilfreiche Felder der Nachrichtenkopfzeile **X-Microsoft-Antispam** beschrieben: Andere Felder in dieser Kopfzeile werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

|**Kopfzeilenfeld**|**Beschreibung**|
|:-----|:-----|
|PCL|Der PCL-Wert (Phishing Confidence Level) der Nachricht, der anzeigt, ob es sich um eine Phishing-Nachricht handelt. Dieser Status kann als einer der folgenden numerischen Werte zurückgegeben werden: <br/>**0-3**: Der Inhalt der Nachricht wird wahrscheinlich nicht zum Phishing genutzt. <br/>**4-8**: Der Inhalt der Nachricht wird wahrscheinlich zum Phishing genutzt. <br/>**-9990**: (nur Exchange Online Protection) Der Inhalt der Nachricht wird wahrscheinlich als Phishing eingestuft.  <br/>  Anhand dieser Werte wird ermittelt, welche Aktion Ihr E-Mail-Client für die Nachrichten ausführt. Outlook verwendet z. B. den PCL-Stempel, um den Inhalt von verdächtigen Nachrichten zu blockieren. Weitere Informationen über Phishing und darüber, wie Outlook Phishingnachrichten verarbeitet, finden Sie unter [Aktivieren und Deaktivieren von Links in E-Mail-Nachrichten](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).|
|

## <a name="authentication-results-message-header"></a>Nachrichtenkopfzeile „Authentication-results“

Die Ergebnisse der SPF-, DKIM- und DMARC-Überprüfungen werden aufgezeichnet, oder in der Nachrichtenkopfzeile **Authentication-results** von Office 365 markiert, wenn unsere E-Mail-Server eine E-Mail erhalten.

### <a name="check-stamp-syntax-and-examples"></a>Überprüfen der Stempelsyntax und Beispiele

Die folgenden Syntaxbeispiele zeigen einen Teil des „Textstempels“, den Office 365 in der Nachrichtenkopfzeile für jede E-Mail-Nachricht anwendet, die beim Empfang durch Ihren Mailserver eine E-Mail-Authentifizierungsprüfung durchlaufen. Dieser Stempel wird der Kopfzeile mit den Authentifizierungsergebnissen hinzugefügt:

#### <a name="syntax-spf-check-stamp"></a>Syntax: SPF-Prüfstempel

Für SPF gilt die folgende Syntax.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**Beispiele: SPF-Prüfstempel

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Syntax: DKIM-Prüfstempel

Für DKIM gilt die folgende Syntax.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**Beispiele: DKIM-Prüfstempel

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Syntax: DMARC-Prüfstempel

Für DMARC gilt die folgende Syntax.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

#### <a name="examples-dmarc-check-stamp"></a>Beispiele: DMARC-Prüfstempel

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Kopfzeilenfelder mit Authentifizierungsergebnissen, die von der Office 365-E-Mail-Authentifizierung verwendet werden

In dieser Tabelle werden die Felder und die möglichen Werte für jede E-Mail-Authentifizierungsprüfung beschrieben.

|**Kopfzeilenfeld**|**Beschreibung**|
|:-----|:-----|
|SPF|Beschreibt die Ergebnisse der SPF-Prüfung für die Nachricht. Mögliche Werte sind: <br/>**pass (IP-Adresse)**: Gibt an, dass die SPF-Überprüfung für die Nachricht bestanden wurde, und enthält die IP-Adresse des Absenders. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten. <br/>**fail (IP-Adresse)**: Gibt an, dass die SPF-Überprüfung für die Nachricht fehlgeschlagen ist, und enthält die IP-Adresse des Absenders. Dies wird häufig als _hard fail_ bezeichnet. <br/>**soft fail (Ursache)**: Gibt an, dass der SPF-Eintrag bestimmt hat, dass der Host nicht die Erlaubnis zum Senden hat, sich jedoch im Übergang befindet. <br/>**neutral**: Gibt an, dass der SPF-Eintrag explizit angegeben hat, dass nicht angegeben wird, ob die IP-Adresse autorisiert ist. <br/>**none**: Gibt an, dass die Domäne nicht über einen SPF-Eintrag verfügt oder dass der SPF-Eintrag nicht zu einem Ergebnis ausgewertet wird. <br/>**temperror**: Gibt an, dass ein Fehler aufgetreten ist, der möglicherweise vorübergehend ist, zum Beispiel ein DNS-Fehler. Wenn Sie es später noch einmal versuchen, kann der Vorgang möglicherweise ohne Eingreifen von Seiten eines Administrators erfolgreich ausgeführt werden. <br/>**permerror**: Gibt an, dass ein dauerhafter Fehler aufgetreten ist. Dies geschieht, wenn die Domäne beispielsweise einen falsch formatierten SPF-Eintrag aufweist.|
|smtp.mailfrom|Enthält die Quelldomäne, von der die Nachricht gesendet wurde. Alle Fehler zu dieser E-Mail-Nachricht werden an den Postmaster oder an die Entität gesendet, der bzw. die für die Domäne verantwortlich ist. Diese Adresse wird im Nachrichtenumschlag manchmal als 5321.MailFrom Adresse oder als reverse-path-Adresse bezeichnet.|
|dkim|Beschreibt die Ergebnisse der DKIM-Prüfung für die Nachricht. Mögliche Werte sind: <br/>**pass**: Gibt an, dass die Nachricht die DKIM-Prüfung bestanden hat. <br/>**fail (Ursache)**: Gibt an, dass die Nachricht die DKIM-Prüfung nicht bestanden hat und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte. <br/>**none**: Gibt an, dass die Nachricht nicht signiert war. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.|
|header.d|Die in der DKIM-Signatur identifizierte Domäne, sofern vorhanden. Dies ist die Domäne, die für den öffentlichen Schlüssel abgefragt wird.|
|dmarc|Beschreibt die Ergebnisse der DMARC-Prüfung für die Nachricht. Mögliche Werte sind: <br/>**pass**: Gibt an, dass die Nachricht die DMARC-Prüfung bestanden hat. <br/>**fail**: Gibt an, dass die Nachricht die DMARC-Prüfung nicht bestanden hat. <br/>**bestguesspass**: Gibt an, dass kein DMARC-TXT-Eintrag für die Domäne vorhanden ist. Wenn jedoch ein Eintrag vorhanden gewesen wäre, hätte die Nachricht die DMARC-Prüfung bestanden. Dies kommt daher, dass die Domäne in der Adresse "5321.MailFrom" der Domäne in der Adresse "5322.From" entspricht. <br/>**none**: Gibt an, dass kein DKIM-TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.|
|Aktion|Gibt die Aktion an, die vom Spamfilter basierend auf den Ergebnissen der DMARC-Prüfung ausgeführt wird. Beispiel: <br/>**permerror**: Bei der DMARC-Prüfung ist ein dauerhafter Fehler aufgetreten, wie z. B. ein falsch formatierter DMARC-TXT-Eintrag in DNS. Der Versuch, die Nachricht erneut zu senden, wird höchstwahrscheinlich kein anderes Ergebnis liefern. Stattdessen müssen Sie sich möglicherweise an den Domänenbesitzer wenden, um das Problem zu beheben. <br/>**temperror**: Bei der DMARC-Prüfung ist ein temporärer Fehler aufgetreten. Sie können den Absender der Nachricht möglicherweise bitten, die Nachricht kurze Zeit später erneut zu senden, damit sie dann ordnungsgemäß verarbeitet werden kann. <br/>**oreject** oder **o.reject**: Dies bedeutet "override reject". Office 365 wendet diese Aktion an, wenn es Nachrichten empfängt, die die DMARC-Prüfung nicht bestehen und die von Domänen stammen, für deren DMARC-TXT-Eintrag die Richtlinie „p=reject“ festgelegt ist. Anstatt die Nachricht abzulehnen oder zu löschen, kennzeichnet Office 365 die Nachricht als Spam. Weitere Informationen darüber, warum Office 365 auf diese Weise konfiguriert ist, finden Sie unter [So behandelt Office 365 eingehende E-Mail-Nachrichten, die DMARC-Prüfungen nicht bestehen](use-dmarc-to-validate-email.md#inbounddmarcfail). <br/>**pct.quarantine**: Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Quarantäne" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll. <br/>**pct.reject**: Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Ablehnen" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll.|
|header.from|Die Domäne der „Von“-Adresse in der Kopfzeile der E-Mail-Nachricht. Dies wird manchmal auch als _5322.From_-Adresse bezeichnet.|
|compauth|Ergebnis der zusammengesetzten Authentifizierung. Wird von Office 365 verwendet, um mehrere Authentifizierungstypen zu kombinieren, z. B. SPF, DKIM, DMARC oder einen beliebigen anderen Teil der Nachricht, um festzustellen, ob die Nachricht authentifiziert ist oder nicht. Verwendet die "From:"-Domäne als Grundlage für die Prüfung.|
|reason|Der Grund, warum die zusammengesetzte Authentifizierung erfolgreich war oder fehlgeschlagen ist. Der Wert für den Grund besteht aus drei Ziffern: <br/>**000**: Die Authentifizierung der Nachricht ist explizit fehlgeschlagen. Die Nachricht hat beispielsweise eine DMARC-Prüfung nicht bestanden (mit der Aktion "Quarantäne" oder "Ablehnen"). <br/>**001**: Die Authentifizierung der Nachricht ist implizit fehlgeschlagen, und die Absenderdomäne hat keine Authentifizierungsrichtlinien veröffentlicht. Beispielsweise eine DMARC-Richtlinie "p=none". <br/>**1xx**: Die Authentifizierung der Nachricht war erfolgreich. Die letzten beiden Ziffern sind von Office 365 verwendete interne Codes. <br/>**2xx**: Die Nachricht wurde mit dem Ergebnis "soft-pass" authentifiziert. Die letzten beiden Ziffern sind von Office 365 verwendete interne Codes. <br/>**3xx**: Die Nachricht wurde nicht auf die zusammengesetzte Authentifizierung überprüft. <br/>**4xx**: Die zusammengesetzte Authentifizierung wurde für die Nachricht umgangen. Die letzten beiden Ziffern sind von Office 365 verwendete interne Codes.|
|
