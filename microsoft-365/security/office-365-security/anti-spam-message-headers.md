---
title: Antispam-Nachrichtenkopfzeilen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können mehr über die Nachrichtenkopfzeilen erfahren, die Nachrichten von Exchange Online Protection (EOP) hinzugefügt werden. Diese Kopfzeilenfelder enthalten Informationen zu der Nachricht und deren Verarbeitung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5617353d291b6c7a98999c831107d8964dba6318
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754468"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Antispam-Nachrichtenkopfzeilen in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In allen Microsoft 365-Organisationen überprüft Exchange Online Protection (EOP) alle eingehenden Nachrichten auf Spam, Malware und andere Bedrohungen. Die Ergebnisse dieser Scans werden den folgenden Kopfzeilenfeldern in Nachrichten hinzugefügt:

- **X-Forefront-Antispam-Report** : enthält Informationen zur Nachricht und ihrer Verarbeitung.

- **X-Microsoft-Antispam** : liefert zusätzliche Informationen über Massensendungen und Phishing.

- **Authentifizierungsergebnisse** : enthält Informationen zu den Ergebnissen von SPF, DKIM und DMARC (E-Mail-Authentifizierung).

In diesem Artikel wird beschrieben, was in diesen Kopfzeilenfeldern verfügbar ist.

Informationen dazu, wie Sie einen E-Mail-Nachrichtenkopf in verschiedenen E-Mail-Clients anzeigen, finden Sie unter [Anzeigen von Internet Nachrichtenkopfzeilen in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Sie können den Inhalt einer Nachrichtenkopfzeile kopieren und in das Tool [Nachrichtenkopfanalyse](https://mha.azurewebsites.net/) einfügen. Mit diesem Tool können Sie Kopfzeilen analysieren und in ein besser lesbares Format umwandeln.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Forefront-Antispam-Report

Wenn Sie die Nachrichtenheader-Informationen haben, suchen Sie nach dem **X-Forefront-Antispam-Report** -Header. In dieser Kopfzeile sind mehrere Felder und Wertepaare vorhanden, die durch Semikolons (;) getrennt sind. Zum Beispiel:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

Die einzelnen Felder und Werte werden in der folgenden Tabelle beschrieben.

> [!NOTE]
> Die **X-Forefront-Antispam-Report** -Kopfzeile enthält viele verschiedene Kopfzeilenfelder und Werte. Felder, die nicht in der Tabelle beschrieben werden, werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

****

|Feld|Beschreibung|
|---|---|
|`ARC`|Das `ARC`-Protokoll weist die folgenden Felder auf: <ul><li>`AAR`: Zeichnet den Inhalt der **Authentifizierungsergebnis** -Kopfzeile aus DMARC auf.</li><li>`AMS`: Enthält kryptographische Signaturen der Nachrichten.</li><li>`AS`: Enthält kryptographische Signaturen der Nachrichtenkopfzeilen. Dieses Feld enthält ein Tag einer Kettenüberprüfung mit der Bezeichnung `"cv="`, das das Ergebnis der Kettenüberprüfung in Form von **kein** , **bestanden** oder **fehlgeschlagen** enthält.</li></ul>|
|`CAT:`|Die Kategorie der Schutzrichtlinie, die auf die Nachricht angewendet wurde: <ul><li>`BULK`: Massensendung</li><li>`DIMP`:Domänenidentitätswechsel</li><li>`GIMP`: [Mailbox Intelligence-basierter Identitätswechsel](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</li><li>`HPHSH` oder `HPHISH`: Hohe Phishingwahrscheinlichkeit</li><li>`HSPM`: Hohe Spamwahrscheinlichkeit</li><li>`MALW`: Schadsoftware</li><li>`PHSH`: Phishing</li><li>`SPM`: Spam</li><li>`SPOOF`: Spoofing</li><li>`UIMP`: Benutzeridentitätswechsel</li><li>`AMP`: Antischadsoftware</li><li>`SAP`: Sichere Anlagen</li><li>`OSPM`: Ausgehende Spamnachricht</li></ul><br/>Eine eingehende Nachricht kann durch mehrere Schutzformen und mehrere Erkennungsscans gekennzeichnet werden. Richtlinien haben unterschiedliche Prioritäten, und die Richtlinie mit der höchsten Priorität wird zuerst angewendet. Weitere Informationen finden Sie unter [Welche Richtlinie gilt, wenn mehrere Schutzmethoden und Erkennungsscans für Ihre E-Mails ausgeführt werden?](how-policies-and-protections-are-combined.md)|
|`CIP:[IP address]`|Die IP-Verbindungsadresse. Sie können diese IP-Adresse in der Liste der zugelassenen IP-Adressen oder in der IP-Sperrliste verwenden. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).|
|`CTRY`|Das anhand der Verbindungs-IP-Adresse ermittelte Quellland. Die IP-Adresse muss nicht notwendigerweise mit der ursprünglichen Sende-IP-Adresse übereinstimmen.|
|`H:[helostring]`|Die HELO- oder EHLO-Zeichenfolge des verbindenden E-Mail-Servers.|
|`IPV:CAL`|Die Nachricht wurde von der Spamfilterung übersprungen, da sich die IP-Quelladresse in der Liste der zugelassenen IP-Adressen befand. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).|
|`IPV:NLI`|Die IP-Adresse wurde in keiner IP-Zuverlässigkeitsliste gefunden.|
|`LANG`|Die Sprache, in der die Nachricht verfasst wurde, wie im Ländercode angegeben (z. B. ru_RU für Russisch).|
|`PTR:[ReverseDNS]`|Der PTR-Eintrag (auch bekannt als Reverse-DNS-Lookup) der Quell-IP-Adresse.|
|`SCL`|Die SCL-Bewertung (Spam Confidence Level) der Nachricht. Ein höherer Wert gibt an, dass die Nachricht mit größerer Wahrscheinlichkeit Spam ist. Weitere Informationen finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).|
|`SFTY`|Die Nachricht wurde als Phishing-E-Mail erkannt und wird außerdem mit einem der folgenden Werte gekennzeichnet: <ul><li>9.1: Standardwert. Die Nachricht enthält einige oder alle der folgenden Elemente: eine Phishing-URL, sonstige Phishinginhalte oder eine lokale Exchange-Kennzeichnung als Phishingnachricht.</li><li>9.11: [Organisationsinternes oder „Self-to-Self“-Spoofing](anti-spoofing-protection.md#different-types-of-spoofing). Der Nachricht wird ein Sicherheitstipp für Organisationsinternes Spoofing beigefügt.</li><li>9.19:Domänenidentitätswechsel. Die sendende Domäne versucht, [die Identität einer geschützten Domäne](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies) anzunehmen. Der Sicherheitstipp für Domänenidentitätswechsel wird der Nachricht (sofern aktiviert) hinzugefügt.</li><li>9.20: Benutzeridentitätswechsel. Der sendende Benutzer versucht, die Identität eines Benutzers in der Organisation des Empfängers oder die eines geschützten Benutzers, der in einer ATP Anti-Phishing-Richtlinie festgelegt ist, nachzuahmen. Der Sicherheitstipp für Benutzeridentitätswechsel wird der Nachricht (sofern aktiviert) hinzugefügt.</li><li>9.21: [Domänenübergreifendes Spoofing](anti-spoofing-protection.md#different-types-of-spoofing). Fehler bei der Meldung "Antispoofing-Prüfungen". Die Absenderdomäne des Absenders in der „Von“-Kopfzeile konnte nicht authentifiziert werden und ist eine externe Domäne. Wird in Kombination mit [zusammengesetzter Authentifizierung](#authentication-results-message-header-fields) verwendet.</li><li>9.22: identisch mit 9.21, außer dass der Benutzer über ein sicherer Absender ist, der überschrieben wurde.</li><li>9.23: identisch mit 9.22, außer dass die Organisation über einen zulässigen Absender oder eine zulässige Domäne verfügt, die überschrieben wurde.</li><li>9.24: identisch mit 9.23, außer dass der Benutzer über eine Exchange-Nachrichtenflussregel (auch als Transportregel bezeichnet) verfügt, die überschrieben wurde.</li></ul>|
|`SFV:BLK`|Die Filterung wurde übersprungen, und die Nachricht wurde blockiert, da sie von einem Absender stammt, der sich in der Liste mit blockierten Absendern des Benutzers befindet.<br/></br> Weitere Informationen dazu, wie Administratoren die Liste blockierter Absender eines Benutzers verwalten können, finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:NSPM`|Die Nachricht wurde von der Spamfilterung als "Kein Spam" markiert und an die beabsichtigten Empfänger gesendet.|
|`SFV:SFE`|Die Filterung wurde übersprungen und die Nachricht wurde zugelassen, da sie von einer Adresse stammt, die sich in der Liste der sicheren Absendern des Benutzers befindet.<br/></br> Weitere Informationen dazu, wie Administratoren die Liste sicherer Absender eines Benutzers verwalten können, finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:SKA`|Die Nachricht wurde von der Spamfilterung übersprungen und an den Posteingang übermittelt, da sich der Absender in der Liste der zulässigen Absender oder in der Liste der zulässigen Domänen in einer Antispamrichtlinie befand. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|`SFV:SKB`|Die Nachricht wurde als Spam gekennzeichnet, da sie einem Sender in der Liste der blockierten Absender oder in der Liste der blockierten Domänen in einer Antispamrichtlinie entsprach. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|`SFV:SKI`|Ähnlich wie SFV:SKN wurde die Nachricht von der Spamfilterung aus einem anderen Grund übersprungen (z. B. eine unternehmensinterne E-Mail innerhalb eines Mandanten).|
|`SFV:SKN`|Die Nachricht wurde bereits als Nicht-Spam markiert, noch bevor sie vom Spamfilter verarbeitet wurde. Die Nachricht wurde durch eine Nachrichtenflussregel z. B. als SCL-1 oder **Spamfilter umgehen** markiert.|
|`SFV:SKQ`|Die Nachricht wurde aus der Quarantäne freigegeben und an die vorgesehenen Empfänger gesendet.|
|`SFV:SKS`|Die Nachricht wurde bereits als Spam markiert, noch bevor sie vom Spamfilter verarbeitet wurde. Die Nachricht wurde beispielsweise durch eine Nachrichtenflussregel als SCL-5 bis 9 markiert.|
|`SFV:SPM`|Die Nachricht wurde vom Spamfilter als Spam markiert.|
|`SRV:BULK`|Die Nachricht wurde von der Spamfilterung und durch den BCL-Schwellenwert (Bulk Complaint Level) als Massen-E-Mail erkannt. Wenn der Parameter _MarkAsSpamBulkMail_ auf `On` festgelegt ist (dies ist die Standardeinstellung), wird eine Massen-E-Mail-Nachricht als SCL-9 (Hoge Spamwahrscheinlichkeit) markiert. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|`X-CustomSpam: [ASFOption]`|Die Nachricht stimmte mit einer erweiterten Einstellung für Spamfilter (AFL) überein. Informationen zum Anzeigen des X-Header-Werts für jede ASF-Einstellung finden Sie unter [Erweiterte Einstellungen für Spamfilter (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Felder der Nachrichtenkopfzeile X-Microsoft-Antispam

In der folgenden Tabelle werden die hilfreiche Felder der Nachrichtenkopfzeile **X-Microsoft-Antispam** beschrieben: Andere Felder in dieser Kopfzeile werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet.

****

|Feld|Beschreibung|
|---|---|
|`BCL`|Das Massenbeschwerdeniveau (Bulk Complaint Level, BCL) der Nachricht. Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist). Weitere Informationen finden Sie unter [BCL-Werte (Bulk Complaint Level)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Nachrichtenkopfzeile „Authentication-results“

Die Ergebnisse der E-Mail-Authentifizierungsüberprüfung für SPF, DKIM und DMARC werden in eingehende Nachrichten in der Nachrichtenkopfzeile **Authentifizierungsergebnisse** aufgezeichnet.

Die folgende Liste beschreibt den Text, der der Kopfzeile **Authentifizierungsergebnisse** für jede Art der E-Mail-Authentifizierungsprüfung hinzugefügt wird:

- SPF verwendet die folgende Syntax:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Zum Beispiel:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM verwendet die folgende Syntax:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Zum Beispiel:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC verwendet die folgende Syntax:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Zum Beispiel:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Nachrichtenkopfzeilenfelder “Authentifizierungsergebnisse”

In der folgenden Tabelle werden die Felder und die möglichen Werte für jede E-Mail-Authentifizierungsprüfung beschrieben.

****

|Feld|Beschreibung|
|---|---|
|`action`|Gibt die Aktion an, die vom Spamfilter basierend auf den Ergebnissen der DMARC-Prüfung ausgeführt wird. Zum Beispiel: <ul><li>**oreject** oder **o.reject** : Dies bedeutet "override reject". Microsoft 365 wendet diese Aktion an, wenn es Nachrichten empfängt, die die DMARC-Prüfung nicht bestehen und die von Domänen stammen, für deren DMARC-TXT-Eintrag die Richtlinie „p=reject“ festgelegt ist. Anstatt die Nachricht abzulehnen oder zu löschen, kennzeichnet Microsoft 365 die Nachricht als Spam. Weitere Informationen darüber, warum Microsoft 365 auf diese Weise konfiguriert ist, finden Sie unter [So behandelt Microsoft 365 eingehende E-Mail-Nachrichten, die DMARC-Prüfungen nicht bestehen](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</li><li>**pct.quarantine** : Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Quarantäne" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll.</li><li>**pct.reject** : Gibt an, dass ein Prozentsatz von weniger als 100 % der Nachrichten, welche die DMARC-Prüfung nicht bestehen, trotzdem übermittelt wird. Das bedeutet, dass die Nachricht die DMARC-Prüfung nicht bestanden hat und die Richtlinie auf "Ablehnen" festgelegt wurde. Das PCT-Feld wurde jedoch nicht auf 100 % festgelegt, und das System hat gemäß der Richtlinie der angegebenen Domäne zufällig bestimmt, dass die DMARC-Aktion nicht angewendet werden soll.</li><li>**permerror** : Bei der DMARC-Prüfung ist ein dauerhafter Fehler aufgetreten, wie z. B. ein falsch formatierter DMARC-TXT-Eintrag in DNS. Der Versuch, die Nachricht erneut zu senden, wird höchstwahrscheinlich kein anderes Ergebnis liefern. Stattdessen müssen Sie sich möglicherweise an den Domänenbesitzer wenden, um das Problem zu beheben.</li><li>**temperror** : Bei der DMARC-Prüfung ist ein temporärer Fehler aufgetreten. Sie können den Absender der Nachricht möglicherweise bitten, die Nachricht kurze Zeit später erneut zu senden, damit sie dann ordnungsgemäß verarbeitet werden kann.</li></ul>|
|`compauth`|Ergebnis der zusammengesetzten Authentifizierung. Wird von Microsoft 365 verwendet, um mehrere Authentifizierungstypen zu kombinieren, z. B. SPF, DKIM, DMARC oder einen beliebigen anderen Teil der Nachricht, um festzustellen, ob die Nachricht authentifiziert ist oder nicht. Verwendet die "From:"-Domäne als Grundlage für die Prüfung.|
|`dkim`|Beschreibt die Ergebnisse der DKIM-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>**pass** : Gibt an, dass die Nachricht die DKIM-Prüfung bestanden hat.</li><li>**fail (Ursache)** : Gibt an, dass die Nachricht die DKIM-Prüfung nicht bestanden hat und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte.</li><li>**none** : Gibt an, dass die Nachricht nicht signiert war. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.</li></ul>|
|`dmarc`|Beschreibt die Ergebnisse der DMARC-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>**pass** : Gibt an, dass die Nachricht die DMARC-Prüfung bestanden hat.</li><li>**fail** : Gibt an, dass die Nachricht die DMARC-Prüfung nicht bestanden hat.</li><li>**bestguesspass** : Gibt an, dass kein DMARC-TXT-Eintrag für die Domäne vorhanden ist. Wenn jedoch ein Eintrag vorhanden gewesen wäre, hätte die Nachricht die DMARC-Prüfung bestanden. Dies liegt daran, dass die Domäne in der `5321.MailFrom`-Adresse (auch als MAIL FROM-Adresse, P1-Absender oder Umschlagabsender bezeichnet) mit der Domäne in der `5322.From`-Adresse (auch als Absenderadresse oder P2-Absender bezeichnet) übereinstimmt.</li><li>**none** : Gibt an, dass kein DMARC-TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.|
|`header.d`|Die in der DKIM-Signatur identifizierte Domäne, sofern vorhanden. Dies ist die Domäne, die für den öffentlichen Schlüssel abgefragt wird.|
|`header.from`|Die Domäne der `5322.From`-Adresse im Kopf der E-Mail-Nachricht (auch als Absenderadresse oder P2-Absender bezeichnet). Empfänger sehen die Absenderadresse in E-Mail-Clients.|
|`reason`|Der Grund, warum die zusammengesetzte Authentifizierung erfolgreich war oder fehlgeschlagen ist. Bei dem Wert handelt es sich um einen dreistelligen Code. Zum Beispiel: <ul><li>**000** : Die explizite Authentifizierung der Nachricht ist fehlgeschlagen (`compauth=fail`). Die Nachricht hat beispielsweise eine DMARC-Prüfung nicht bestanden (mit der Aktion "Quarantäne" oder "Ablehnen").</li><li>**001** Die implizite Authentifizierung der Nachricht ist fehlgeschlagen (`compauth=fail`). Das bedeutet, dass die sendende Domäne keine E-Mail-Authentifizierungseinträge veröffentlicht hat oder, wenn sie sie veröffentlicht hat, sie eine schwächere Fehlerrichtlinie hatten (SPF Soft Fail oder neutral, DMARC-Richtlinie von `p=none`).</li><li>**002** gibt an, dass die Organisation über eine Richtlinie für das Absender/Domänepaar verfügt, für die das Senden von gefälschten E-Mails explizit untersagt ist. Diese Einstellung wird manuell von einem Administrator festgelegt.</li><li>**010** gibt an, dass DMARC für die Nachricht mit einer Aktion der Ablehnung oder Quarantäne fehlgeschlagen ist und die sendende Domäne eine der in der Organisation zulässigen Domänen ist (Dies ist Teil von Self-to-Self Spoofing oder organisationsinternem Spoofing).</li><li>**1xx** oder **7xx** : Die Authentifizierung der Nachricht war erfolgreich (`compauth=pass`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**2xx** : Die Nachricht wurde mit dem Ergebnis „soft-pass“ implizit authentifiziert (`compauth=softpass`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**3xx** : Die Nachricht wurde nicht auf die zusammengesetzte Authentifizierung überprüft. (`compauth=none`)</li><li>**4xx** oder **9xx** : Die zusammengesetzte Authentifizierung wurde für die Nachricht umgangen (`compauth=none`). Die letzten beiden Ziffern sind von Microsoft 365 verwendete, interne Codes.</li><li>**6xx** : Die implizite E-Mail-Authentifizierung für die Nachricht ist fehlgeschlagen und die sendende Domäne ist eine der in der Organisation zulässigen Domänen (Dies ist Teil von Self-to-Self-Spoofing oder organisationsinternem Spoofing).</li></ul>|
|`smtp.mailfrom`|Die Domäne der `5321.MailFrom`-Adresse (auch als MAIL FROM-Adresse, P1-Absender oder Umschlagabsender bezeichnet). Dies ist die E-Mail-Adresse, die für Unzustellbarkeitsberichte (auch als NDRs oder Unzustellbarkeitsnachricht bezeichnet) verwendet wird.|
|`spf`|Beschreibt die Ergebnisse der SPF-Prüfung für die Nachricht. Mögliche Werte sind: <ul><li>`pass (IP address)`: Die SPF-Überprüfung für die Nachricht wurde bestanden und enthält die IP-Adresse des Absenders. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten.</li><li>`fail (IP address)`: Die SPF-Überprüfung für die Nachricht ist fehlgeschlagen, und enthält die IP-Adresse des Absenders. Dies wird manchmal auch als _schwerer Fehler_ bezeichnet.</li><li>`softfail (reason)`: Der SPF-Eintrag hat bestimmt, dass der Host nicht die Erlaubnis zum Senden hat, sich jedoch im Übergang befindet.</li><li>`neutral`: Der SPF-Eintrag gibt explizit an, dass nicht bestätigt wird, dass die IP-Adresse zum Versenden autorisiert ist.</li><li>`none`: Die Domäne verfügt nicht über einen SPF-Eintrag oder der SPF-Eintrag führt zu keinem Ergebnis.</li><li>`temperror`: Es ist ein vorübergehender Fehler aufgetreten. Dabei kann es sich beispielsweise um einen DNS-Fehler handeln. Dieselbe Überprüfung ist zu einem späteren Zeitpunkt möglicherweise erfolgreich.</li><li>`permerror`: Es ist ein dauerhafter Fehler aufgetreten. Dabei kann es sich zum Beispiel um einen Fehler handeln, bei dem die Domäne einen falsch formatierten SPF-Eintrag aufweist.</li></ul>|
|
