---
title: Antispam-Nachrichtenkopfzeilen
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
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Header-Felder, die Exchange Online Protection den Nachrichten hinzufügt, um Informationen über die Nachricht und ihre Verarbeitung zu liefern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 035b081980e52d1e68d21e6227636ed78697b4cc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033750"
---
# <a name="anti-spam-message-headers"></a>Antispam-Nachrichtenkopfzeilen

Wenn Exchange Online Protection (EOP) eingehende E-Mail-Nachrichten prüft, wird jeder Nachricht die Kopfzeile **X-Forefront-Antispam-Report** hinzugefügt. Mit den Feldern in dieser Kopfzeile können Administratoren Information zur Nachricht und deren Verarbeitung bereitgestellt werden. Die Felder in der Kopfzeile **X-Microsoft-Antispam** liefern zusätzliche Informationen über Massensendungen und Phishing. Zusätzlich zu diesen beiden Kopfzeilen fügt Exchange Online Protection auch E-Mail-Authentifizierungsergebnisse für jede verarbeitete Nachricht in die Kopfzeile **Authentication-results** ein.

Informationen dazu, wie Sie einen E-Mail-Nachrichtenkopf in verschiedenen E-Mail-Clients anzeigen, finden Sie unter [Anzeigen von Internet Nachrichtenkopfzeilen in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Sie können den Inhalt einer Nachrichtenkopfzeile kopieren und in das Tool [Message Analyzer](https://testconnectivity.microsoft.com/?tabid=mha) einfügen. Mit diesem Tool können Sie Kopfzeilen analysieren und in ein besser lesbares Format umwandeln.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Forefront-Antispam-Report

Suchen Sie nach dem Zugriff auf die Nachrichtenkopfzeileninformationen nach **X-Forefront-Antispam-Report**, und suchen Sie nach den folgenden Feldern: Andere Felder in dieser Kopfzeile werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

|||
|---|---|
|**Kopfzeilenfeld**|**Beschreibung**|
|ARC|Das ARC-Protokoll weist die folgenden Header auf: <ul><li>AAR: Zeichnet den Inhalt des Authentifizierungsergebnis-Headers aus DMARC auf.</li><li>AMS: Dieser Header enthält kryptographische Signaturen der Nachricht.</li><li>AS: Enthält kryptographische Signaturen der Nachrichtenkopfzeilen. Dieser Header enthält einen Tag einer Kettenüberprüfung mit der Bezeichnung "cv=", das das Ergebnis der Kettenüberprüfung als **none**, **pass** oder **fail** enthält.</li></ul>|
|CAT:|Die Kategorie der Schutzrichtlinie, die auf die Nachricht angewendet wurde: <ul><li>BULK: Massenaktion</li><li>DIMP: Domänenidentitätswechsel</li><li>GIMP: Mailbox Intelligence</li><li>HPHSH oder HPHISH : Hohe Phishing-Wahrscheinlichkeit </li><li>HSPM: Spam mit hoher Vertrauenswürdigkeit</li><li>MALW: Malware</li><li>PHSH: Phishing</li><li>SPM: Spam</li><li>SPOOF: Spoofing</li><li>UIMP: Benutzeridentitätswechsel</li></ul><br/>Eine eingehende Nachricht kann durch mehrere Schutzformen und mehrere Erkennungsscans gekennzeichnet werden. Richtlinien haben unterschiedliche Prioritäten, und die Richtlinie mit der höchsten Priorität wird zuerst angewendet. Weitere Informationen finden Sie unter [Welche Richtlinie gilt, wenn mehrere Schutzmethoden und Erkennungsscans für Ihre E-Mails ausgeführt werden?](how-policies-and-protections-are-combined.md)|
|CIP: \[IP-Adresse\]|Die IP-Verbindungsadresse. Sie können diese IP-Adresse in der Liste der zugelassenen IP-Adressen oder in der IP-Sperrliste verwenden. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).|
|CTRY|Das anhand der Verbindungs-IP-Adresse ermittelte Quellland, die nicht notwendigerweise mit der ursprünglichen Sende-IP-Adresse übereinstimmen muss.|
|H:\[helostring\]|Die HELO- oder EHLO-Zeichenfolge des verbindenden E-Mail-Servers.|
|IPV:CAL|Die Nachricht wurde von der Spamfilterung übersprungen, da sich die IP-Quelladresse in der Liste der zugelassenen IP-Adressen befand. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).|
|IPV:NLI|Die IP-Adresse war nicht in einer IP-Zuverlässigkeitsliste aufgeführt.|
|LANG|Die Sprache, in der die Nachricht verfasst wurde, wie im Ländercode angegeben (z. B. ru_RU für Russisch).|
|PTR:\[ReverseDNS\]|Der PTR-Eintrag (auch bekannt als Reverse-DNS-Lookup) der Quell-IP-Adresse.|
|SCL|Die SCL-Bewertung (Spam Confidence Level) der Nachricht. Ein höherer Wert gibt an, dass die Nachricht mit größerer Wahrscheinlichkeit Spam ist. Weitere Informationen finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).|
|SFTY|Die Nachricht wurde als Phishing-E-Mail erkannt und wird außerdem mit einem der folgenden Werte gekennzeichnet: <ul><li>9.1: Standardwert. Die Nachricht enthält eine Phishing-URL, kann weitere Phishinginhalte enthalten oder wurde möglicherweise vor der Weiterleitung an Microsoft 365 von einem anderen E-Mail-Filter (z. B. einem lokalen Exchange) als Phishing-E-Mail gekennzeichnet.</li><li>9.11: [Organisationsinternes oder „Self-to-Self“-Spoofing](anti-spoofing-protection.md#different-types-of-spoofing). Die Nachricht hat Antispoofing-Überprüfungen nicht bestanden, wobei die Domäne der Absender-E-Mail in der „Von:“-Kopfzeile mit der Empfängerdomäne übereinstimmt oder Teil der gleichen Organisation ist. Der Nachricht wird ein Sicherheitstipp für Organisationsinternes Spoofing beigefügt.</li><li>9.19:Domänenidentitätswechsel. Die sendende Domäne versucht, die Identität einer geschützten Domäne (einer Domäne, die sich im Besitz der Organisation des Empfängers oder einer benutzerdefinierten Domäne befindet), die in einer ATP-Richtlinie für Anti-Phishing angegeben ist, nachzuahmen. Der Sicherheitstipp für Domänen-Identitätswechsel wird der Nachricht hinzugefügt (wenn der Sicherheitstipp in der ATP-Anti-Phishing-Richtlinie aktiviert ist).</li><li>9.20: Benutzeridentitätswechsel. Der sendende Benutzer versucht, die Identität eines Benutzers in der Organisation des Empfängers oder die eines geschützten Benutzers, der in einer ATP Anti-Phishing-Richtlinie festgelegt ist, nachzuahmen. Der Sicherheitstipp für Benutzer-Identitätswechsel wird der Nachricht hinzugefügt (wenn der Sicherheitstipp in der ATP-Anti-Phishing-Richtlinie aktiviert ist).</li><li>9.21: [Domänenübergreifendes Spoofing](anti-spoofing-protection.md#different-types-of-spoofing). Die Nachricht hat Antispoofing-Überprüfungen nicht bestanden, da sich die Absenderdomäne in der „Von:“-Kopfzeile nicht authentifiziert und eine externe Domäne ist. Wird in Kombination mit [CompAuth](#authentication-results-message-header-fields-used-by-microsoft-email-authentication) verwendet).</li><li>9.22: identisch mit 9.21, außer dass der Benutzer über ein sicherer Absender ist, der überschrieben wurde.</li><li>9.23: identisch mit 9.22, außer dass die Organisation über einen zulässigen Absender oder eine zulässige Domäne verfügt, die überschrieben wurde.</li><li>9.24: identisch mit 9.23, außer dass der Benutzer über eine Exchange-Nachrichtenflussregel (auch als Transportregel bezeichnet) verfügt, die überschrieben wurde.</li></ul>|
|SFV:BLK|Filterung wurde übersprungen, und die Nachricht wurde blockiert, da sie von einer Adresse gesendet wurde, die sich in der Sperrliste des Benutzers (in Outlook blockierte Absender) befindet.<br/></br> Weitere Informationen dazu, wie Administratoren die Liste blockierter Absender eines Benutzers verwalten können, finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:NSPM|Die Nachricht wurde von der Spamfilterung als "Nicht-Spam" markiert und an die beabsichtigten Empfänger gesendet.|
|SFV:SFE|Filterung wurde übersprungen, und die Nachricht wurde durchgelassen, da sie von einer Adresse gesendet wurde, die sich in der Benutzerliste der sicheren Absender (Outlook-Liste sicherer Absender) befindet.<br/></br> Weitere Informationen dazu, wie Administratoren die Liste sicherer Absender eines Benutzers verwalten können, finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:SKA|Die Nachricht wurde von der Spamfilterung übersprungen und an den Posteingang übermittelt, da sie einem Eintrag in der Liste der zulässigen Absender oder in der Liste der zulässigen Domänen in einer Antispamrichtlinie entsprach. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|SFV:SKB|Die Nachricht wurde als Spam gekennzeichnet, da sie einem Eintrag in der Liste der blockierten Absender oder in der Liste der blockierten Domänen in einer Antispamrichtlinie entsprach. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|SFV:SKI|Ähnlich wie SFV:SKN; die Nachricht wurde von der Spamfilterung aus einem anderen Grund übersprungen (z. B. unternehmensinterne E-Mail innerhalb eines Mandanten).|
|SFV:SKN|Die Nachricht wurde vor der Verarbeitung durch die Spamfilterung als "Nicht-Spam" markiert, (beispielsweise wurde die Nachricht durch eine Nachrichtenflussregel als SCL-1 oder **Spamfilter umgehen** markiert).|
|SFV:SKQ|Die Nachricht wurde aus der Quarantäne freigegeben und an die vorgesehenen Empfänger gesendet.|
|SFV:SKS|Die Nachricht wurde vor der Verarbeitung durch die Spamfilterung als Spam markiert (beispielsweise wurde die Nachricht durch eine Nachrichtenflussregel als SCL-5 bis 9 markiert).|
|SFV:SPM|Die Nachricht wurde von der Spamfilterung als Spam markiert.|
|SRV:BULK|Die Nachricht wurde von der Spamfilterung und durch den BCL-Schwellenwert (Bulk Complaint Level) als Massen-E-Mail erkannt. Wenn der Parameter _MarkAsSpamBulkMail_ auf `On` festgelegt ist (dies ist die Standardeinstellung), wird eine Massen-E-Mail-Nachricht als SCL-9 (Hoge Spamwahrscheinlichkeit) markiert. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|X-CustomSpam: \[ASFOption\]|Die Nachricht stimmte mit einer erweiterten Einstellung für Spamfilter (AFL) überein. Informationen zum Anzeigen des X-Header-Werts für jede ASF-Einstellung finden Sie unter [Erweiterte Einstellungen für Spamfilter (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Microsoft-Antispam

In der folgenden Tabelle werden die hilfreiche Felder der Nachrichtenkopfzeile **X-Microsoft-Antispam** beschrieben: Andere Felder in dieser Kopfzeile werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

|||
|---|---|
|**Kopfzeilenfeld**|**Beschreibung**|
|BCL|Die BCL-Wert (Bulk Complaint Level) der Nachricht. Ein höherer BCL zeigt an, dass eine Massen-E-Mail-Nachricht (auch als _Gray Mail_ bezeichnet) mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist). Weitere Informationen finden Sie unter [BCL-Werte (Bulk Complaint Level)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Nachrichtenkopfzeile „Authentication-results“

Die Ergebnisse der SPF-, DKIM- und DMARC-Überprüfungen werden aufgezeichnet, oder in der Nachrichtenkopfzeile **Authentifizierungsergebnissen** von Microsoft 365 markiert, wenn unsere E-Mail-Server eine E-Mail erhalten.

### <a name="check-stamp-syntax-and-examples"></a>Überprüfen der Stempelsyntax und Beispiele

Die folgenden Syntaxbeispiele zeigen einen Teil des „Textstempels“, den Microsoft 365 in der Nachrichtenkopfzeile für jede E-Mail-Nachricht anwendet, die beim Empfang durch Ihren Mailserver eine E-Mail-Authentifizierungsprüfung durchlaufen. Dieser Stempel wird der Kopfzeile mit den**Authentifizierungsergebnissen** hinzugefügt.

#### <a name="syntax-spf-check-stamp"></a>Syntax: SPF-Prüfstempel

Für SPF gilt die folgende Syntax.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Beispiele: SPF-Prüfstempel

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Syntax: DKIM-Prüfstempel

Für DKIM gilt die folgende Syntax.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Beispiele: DKIM-Prüfstempel

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Syntax: DMARC-Prüfstempel

Für DMARC gilt die folgende Syntax.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Beispiele: DMARC-Prüfstempel

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-microsoft-email-authentication"></a>Kopfzeilenfelder mit Authentifizierungsergebnissen, die von der Microsoft-E-Mail-Authentifizierung verwendet werden

In dieser Tabelle werden die Felder und die möglichen Werte für jede E-Mail-Authentifizierungsprüfung beschrieben.

|||
|---|---|
|**Kopfzeilenfeld**|**Beschreibung**|
|Aktion|Gibt die Aktion an, die vom Spamfilter basierend auf den Ergebnissen der DMARC-Prüfung ausgeführt wird. Beispiel: <ul><li>**oreject** oder **o.reject**: Dies bedeutet "override reject". Microsoft 365 wendet diese Aktion an, wenn es Nachrichten empfängt, die die DMARC-Prüfung nicht bestehen und die von Domänen stammen, für deren DMARC-TXT-Eintrag die Richtlinie „p=reject“ festgelegt ist. Anstatt die Nachricht abzulehnen oder zu löschen, kennzeichnet Microsoft 365 die Nachricht als Spam. Weitere Informationen darüber, warum Microsoft 365 auf diese Weise konfiguriert ist, finden Sie unter [So behandelt Microsoft 365 eingehende E-Mail-Nachrichten, die DMARC-Prüfungen nicht bestehen](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</li><li>**pct.quarantine**: Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Quarantäne" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll.</li><li>**pct.reject**: Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Ablehnen" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll.</li><li>**permerror**: Bei der DMARC-Prüfung ist ein dauerhafter Fehler aufgetreten, wie z. B. ein falsch formatierter DMARC-TXT-Eintrag in DNS. Der Versuch, die Nachricht erneut zu senden, wird höchstwahrscheinlich kein anderes Ergebnis liefern. Stattdessen müssen Sie sich möglicherweise an den Domänenbesitzer wenden, um das Problem zu beheben.</li><li>**temperror**: Bei der DMARC-Prüfung ist ein temporärer Fehler aufgetreten. Sie können den Absender der Nachricht möglicherweise bitten, die Nachricht kurze Zeit später erneut zu senden, damit sie dann ordnungsgemäß verarbeitet werden kann.</li></ul>|
|compauth|Ergebnis der zusammengesetzten Authentifizierung. Wird von Microsoft 365 verwendet, um mehrere Authentifizierungstypen zu kombinieren, z. B. SPF, DKIM, DMARC oder einen beliebigen anderen Teil der Nachricht, um festzustellen, ob die Nachricht authentifiziert ist oder nicht. Verwendet die "From:"-Domäne als Grundlage für die Prüfung.|
|dkim|Beschreibt die Ergebnisse der DKIM-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>**pass**: Gibt an, dass die Nachricht die DKIM-Prüfung bestanden hat.</li><li>**fail (Ursache)**: Gibt an, dass die Nachricht die DKIM-Prüfung nicht bestanden hat und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte.</li><li>**none**: Gibt an, dass die Nachricht nicht signiert war. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.</li></ul>|
|dmarc|Beschreibt die Ergebnisse der DMARC-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>**pass**: Gibt an, dass die Nachricht die DMARC-Prüfung bestanden hat.</li><li>**fail**: Gibt an, dass die Nachricht die DMARC-Prüfung nicht bestanden hat.</li><li>**bestguesspass**: Gibt an, dass kein DMARC-TXT-Eintrag für die Domäne vorhanden ist. Wenn jedoch ein Eintrag vorhanden gewesen wäre, hätte die Nachricht die DMARC-Prüfung bestanden. Dies liegt daran, dass die Domäne in der `5321.MailFrom`-Adresse (auch als MAIL FROM-Adresse, P1-Absender oder Umschlagabsender bezeichnet) mit der Domäne in der `5322.From`-Adresse (auch als Absenderadresse oder P2-Absender bezeichnet) übereinstimmt.</li><li>**none**: Gibt an, dass kein DKIM-TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.|
|header.d|Die in der DKIM-Signatur identifizierte Domäne, sofern vorhanden. Dies ist die Domäne, die für den öffentlichen Schlüssel abgefragt wird.|
|header.from|Die Domäne der `5322.From`-Adresse im Kopf der E-Mail-Nachricht (auch als Absenderadresse oder P2-Absender bezeichnet). Empfänger sehen die Absenderadresse in E-Mail-Clients.|
|reason|Der Grund, warum die zusammengesetzte Authentifizierung erfolgreich war oder fehlgeschlagen ist. Bei dem Wert handelt es sich um einen dreistelligen Code. Zum Beispiel: <ul><li>**000**: Die explizite Authentifizierung der Nachricht ist fehlgeschlagen (`compauth=fail`). Die Nachricht hat beispielsweise eine DMARC-Prüfung nicht bestanden (mit der Aktion "Quarantäne" oder "Ablehnen").</li><li>**001** Die implizite Authentifizierung der Nachricht ist fehlgeschlagen (`compauth=fail`). Das bedeutet, dass die sendende Domäne keine E-Mail-Authentifizierungseinträge veröffentlicht hat oder, wenn sie sie veröffentlicht hat, sie eine schwächere Fehlerrichtlinie hatten (SPF Soft Fail oder neutral, DMARC-Richtlinie von `p=none`).</li><li>**002** gibt an, dass die Organisation über eine Richtlinie für das Absender/Domänepaar verfügt, für die das Senden von gefälschten E-Mails explizit untersagt ist. Diese Einstellung wird manuell von einem Administrator festgelegt.</li><li>**010** gibt an, dass DMARC für die Nachricht mit einer Aktion der Ablehnung oder Quarantäne fehlgeschlagen ist und die sendende Domäne eine der in der Organisation zulässigen Domänen ist (Dies ist Teil von Self-to-Self Spoofing oder organisationsinternem Spoofing).</li><li>**1xx** oder **7xx**: Die Authentifizierung der Nachricht war erfolgreich (`compauth=pass`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**2xx**: Die Nachricht wurde mit dem Ergebnis „soft-pass“ implizit authentifiziert (`compauth=softpass`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**3xx**: Die Nachricht wurde nicht auf die zusammengesetzte Authentifizierung überprüft. (`compauth=none`)</li><li>**4xx** oder **9xx**: Die zusammengesetzte Authentifizierung wurde für die Nachricht umgangen (`compauth=none`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**6xx**: Die implizite E-Mail-Authentifizierung für die Nachricht ist fehlgeschlagen und die sendende Domäne ist eine der in der Organisation zulässigen Domänen (Dies ist Teil von Self-to-Self-Spoofing oder organisationsinternem Spoofing).</li></ul>|
|smtp.mailfrom|Die Domäne der `5321.MailFrom`-Adresse (auch als MAIL FROM-Adresse, P1-Absender oder Umschlagabsender bezeichnet). Dies ist die E-Mail-Adresse, die für Unzustellbarkeitsberichte (auch als NDRs oder Unzustellbarkeitsnachricht bezeichnet) verwendet wird.|
|SPF|Beschreibt die Ergebnisse der SPF-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>**pass (IP-Adresse)**: Gibt an, dass die SPF-Überprüfung für die Nachricht bestanden wurde, und enthält die IP-Adresse des Absenders. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten.</li><li>**fail (IP-Adresse)**: Gibt an, dass die SPF-Überprüfung für die Nachricht fehlgeschlagen ist, und enthält die IP-Adresse des Absenders. Dies wird häufig als _hard fail_ bezeichnet.</li><li>**soft fail (Ursache)**: Gibt an, dass der SPF-Eintrag bestimmt hat, dass der Host nicht die Erlaubnis zum Senden hat, sich jedoch im Übergang befindet.</li><li>**neutral**: Gibt an, dass der SPF-Eintrag explizit angegeben hat, dass nicht angegeben wird, ob die IP-Adresse autorisiert ist.</li><li>**none**: Gibt an, dass die Domäne nicht über einen SPF-Eintrag verfügt oder dass der SPF-Eintrag nicht zu einem Ergebnis ausgewertet wird.</li><li>**temperror**: Gibt an, dass ein Fehler aufgetreten ist, der möglicherweise vorübergehend ist, zum Beispiel ein DNS-Fehler. Wenn Sie es später noch einmal versuchen, kann der Vorgang möglicherweise ohne Eingreifen von Seiten eines Administrators erfolgreich ausgeführt werden.</li><li>**permerror**: Gibt an, dass ein dauerhafter Fehler aufgetreten ist. Dies geschieht, wenn die Domäne beispielsweise einen falsch formatierten SPF-Eintrag aufweist.</li></ul>|
|
