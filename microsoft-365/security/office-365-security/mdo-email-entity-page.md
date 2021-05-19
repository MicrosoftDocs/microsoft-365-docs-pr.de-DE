---
title: Die Microsoft Defender for Office 365 (MDO)-E-Mail-Entitätsseite
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender für Office 365 E5- und P1- und P2-Kunden können jetzt eine 360-Grad-Ansicht jeder E-Mail mit E-Mail-Entitätsseite erhalten.
ms.openlocfilehash: aa5d7effb66c4805f6983fa1afac19255bc996e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539095"
---
# <a name="the-email-entity-page"></a>Die Seite „E-Mail-Entität"

**Inhalt dieses Artikels:**
- [Erreichen der E-Mail-Entitätsseite](#reach-the-email-entity-page)
- [Lesen der E-Mail-Entitätsseite](#read-the-email-entity-page)
- [Verwenden von E-Mail-Entitätsseitenregisterkarten](#use-email-entity-page-tabs)
- [Neu auf der E-Mail-Entitätsseite](#new-to-the-email-entity-page)

Administratoren von Microsoft Defender für Office 365 (oder MDO) E5 und MDO P1 und P2 verfügen über eine 360-Grad-Ansicht von E-Mails auf der Seite **"E-Mail-Entität".** Diese Go-to-E-Mail-Seite wurde erstellt, um informationen zu verbessern, die über das [Fly-Out "E-Mail-Details"](threat-explorer-views.md)des Bedrohungs-Explorers übermittelt wurden.

## <a name="reach-the-email-entity-page"></a>Erreichen der E-Mail-Entitätsseite

Entweder das vorhandene Security & Compliance Center (protection.office.com) oder das neue Microsoft 365 Security Center (security.microsoft.com) können Sie die E-Mail-Entitätsseite anzeigen und verwenden.

|Zentriert|URL|Navigation|
|---|---|---|
|Sicherheit und Compliance |protection.office.com|Threat Management \> Explorer|
|Microsoft 365 Security Center |security.microsoft.com|E&-Explorer \> für die Zusammenarbeit|

Wählen Sie im Bedrohungs-Explorer den Betreff einer E-Mail aus, die Sie untersuchen. Am oberen Rand des E-Mail-Flyouts für diese E-Mail wird eine Goldleiste angezeigt. Diese Einladung zur neuen Seite lautet "Testen Sie unsere neue E-Mail-Entitätsseite mit bereicherten Daten...". Wählen Sie diese Option aus, um die neue Seite anzeigen zu können.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Sie sehen ein goldenes Banner mit den Wörtern *Probieren Sie unsere neue E-Mail-Entitätsseite mit bereicherten Daten* aus, um zur neuen Erfahrung zu navigieren.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Diese Grafik der E-Mail-Entitätsseite konzentriert sich auf Überschriften, die Angezeigt werden. Beachten Sie, dass der E-Mail-Header hier angezeigt wird.":::

> [!NOTE]
> Die berechtigungen, die zum Anzeigen und Verwenden dieser Seite erforderlich sind, sind identisch mit dem Anzeigen des Bedrohungs-Explorers. Der Administrator muss Mitglied des globalen Admins oder des globalen Lesers oder des Sicherheitsadministrators oder des Sicherheitslesers sein.

## <a name="read-the-email-entity-page"></a>Lesen der E-Mail-Entitätsseite

Die Struktur ist so konzipiert, dass sie auf einen Blick leicht zu lesen und zu navigieren ist. Verschiedene Registerkarten am oberen Rand der Seite ermöglichen ihnen eine ausführlichere Untersuchung. So funktioniert das Layout:

1. Die am häufigsten benötigten Felder befinden sich auf der linken Seite des Flyouts. Diese Details sind "sticky", d. h. sie sind links verankert, unabhängig von der Registerkarte, zu der Sie im restlichen Fly-Out navigieren.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Grafik der E-Mail-Entitätsseite mit hervorgehobener linker Seite. Der Titel und die Fakten zur E-Mail-Zustellung sind hier zu Ende.":::

2. In der oberen rechten Ecke befinden sich die Aktionen, die für eine E-Mail ergriffen werden können. Alle Aktionen, die über Explorer ergriffen werden können, sind auch über die E-Mail-Entitätsseite verfügbar.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Grafik der E-Mail-Entitätsseite, deren Seite *rechts* dieses Mal hervorgehoben ist. Aktionen wie &quot;E-Mail-Vorschau&quot; und &quot;In Quarantäne gehen&quot; finden Sie hier.":::

3. Eine tiefergehende Analyse kann durchgeführt werden, indem der Rest der Seite sortiert wird. Überprüfen Sie die E-Mail-Erkennungsdetails, den E-Mail-Authentifizierungsstatus und die Kopfzeile. Dieser Bereich sollte von Fall zu Fall betrachtet werden, aber die Informationen auf diesen Registerkarten sind für jede E-Mail verfügbar.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Der Hauptbereich dieser Seite enthält den E-Mail-Header und den Authentifizierungsstatus.":::

### <a name="use-email-entity-page-tabs"></a>Verwenden von E-Mail-Entitätsseitenregisterkarten

Mit den Registerkarten am oberen Rand der Entitätsseite können Sie E-Mails effizient untersuchen.

1. **Zeitachse**: Die Zeitachsenansicht für eine E-Mail (pro Zeitachse des Bedrohungs-Explorers) zeigt die ursprüngliche Zustellung an Ereignisse nach der Zustellung an, die in einer E-Mail auftreten. Bei E-Mails ohne Postzustellungsaktionen zeigt die Ansicht die ursprüngliche Zustellungszeile in der Zeitachsenansicht an. Ereignisse wie: Automatische Null-Stunden-Bereinigung (ZAP), Behebung, URL-Klicks usw. aus Quellen wie: System, Administrator und Benutzer, werden hier in der Reihenfolge angezeigt, in der sie aufgetreten sind.
2. **Analysis**: Analysis shows fields that help admins analyze an email in depth. In Fällen, in denen Administratoren mehr über Erkennungs-, Absender-/Empfänger- und E-Mail-Authentifizierungsdetails wissen müssen, sollten sie die Registerkarte Analyse verwenden. Links für Anlagen und URLs finden Sie auch auf dieser Seite unter "Verwandte Entitäten". Sowohl Anlagen als auch identifizierte Bedrohungen sind hier nummeriert, und wenn Sie auf klicken, werden Sie direkt zu den Seiten Anlagen und URL geklickt. Diese Registerkarte verfügt auch über eine Ansichtskopfoption zum *Anzeigen des E-Mail-Headers.* Administratoren können alle Details aus E-Mail-Kopfzeilen nebeneinander mit Informationen im Hauptbereich vergleichen, um Klarheit zu schaffen.
3. **Anlagen**: Dadurch werden Anlagen in der E-Mail mit anderen Details zu Anlagen untersucht. Die Anzahl der angezeigten Anlagen ist derzeit auf 10 beschränkt. Beachten Sie, dass detonation details for attachments found to be malicious is also shown here.
4. **URLs:** Auf dieser Registerkarte werden URLs in der E-Mail mit weiteren Details zu den URLs aufgeführt. Die Anzahl der URLs ist derzeit auf 10 beschränkt, aber diese 10 werden priorisiert, um zuerst schädliche *URLs zu zeigen.* Die Priorisierung spart Ihnen Zeit und Ratenarbeit. Die URLs, die als bösartig und detoniert gefunden wurden, werden ebenfalls hier angezeigt.
5. **Ähnliche** E-Mails: Auf dieser Registerkarte werden alle E-Mails aufgeführt, die der für diese E-Mail spezifischen Netzwerknachrichten-ID *+ Empfängerkombination* ähneln. Ähnlichkeit basiert nur auf *dem Nachrichtentext.* Die Festlegungen für E-Mails, sie als "ähnlich" zu kategorisieren, enthalten keine Überlegungen zu *Anlagen.*

## <a name="new-to-the-email-entity-page"></a>Neu auf der E-Mail-Entitätsseite

Diese E-Mail-Entitätsseite enthält neue Funktionen. Hier ist die Liste.

### <a name="email-preview-for-cloud-mailboxes"></a>E-Mail-Vorschau für Cloudpostfächer

Administratoren können eine Vorschau von E-Mails in Cloudpostfächern ***anzeigen,*** wenn die E-Mails noch in der Cloud vorhanden sind. Bei einem soft delete (durch einen Administrator oder Benutzer) oder ZAP (in Quarantäne) sind E-Mails nicht mehr am Cloudspeicherort vorhanden. In diesem Fall können Administratoren keine Vorschau dieser bestimmten E-Mails anzeigen. E-Mails, die gelöscht wurden oder bei denen die Zustellung fehlgeschlagen ist, haben es nie tatsächlich in das Postfach geschafft. Aus diesem Grund können Administratoren auch keine Vorschau dieser E-Mails anzeigen.

> [!WARNING]
> Für die Vorschau von E-Mails ist eine spezielle Rolle namens ***Preview** _ erforderlich, um Administratoren zugewiesen zu werden. Sie können diese Rolle hinzufügen, indem Sie zu _ *Permissions & roles** > Email & collaboration **roles** in *security.microsoft.com* oder **Permissions** in *protection.office.com .* Fügen Sie ***die Vorschaurolle*** zu einer der Rollengruppen oder eine Kopie einer Rollengruppe hinzu, mit der Administratoren in Ihrer Organisation im Bedrohungs-Explorer arbeiten können.

### <a name="detonation-details"></a>Detonation details

Diese Details sind spezifisch für E-Mail-Anlagen und URLs.

Benutzern werden bereicherte Detonationsdetails für bekannte schädliche Anlagen oder Hyperlinks in ihren Postfächern angezeigt, einschließlich Detonation Chain, Detonation Summary, Screenshot und Observed Behavior Details, um Kunden zu verstehen, warum die Anlage oder URL als bösartig und detoniert eingestuft wurde.

- *Detonationskette:* Eine einzelne Datei- oder URL-Detonation kann mehrere Detonationen auslösen. Die Detonationskette verfolgt den Pfad der Detonationen, einschließlich der ursprünglichen schädlichen Datei oder URL, die das Urteil verursacht hat, und allen anderen Dateien oder URLs, die durch die Detonation verursacht wurden. Diese URLs oder angefügten Dateien sind möglicherweise nicht direkt in der E-Mail vorhanden, aber das Einfügen dieser Analyse ist wichtig, um zu ermitteln, warum die Datei oder URL als schädlich festgestellt wurde.
- *Detonation Summary*: This gives information on:
  - Detonationszeitbereich.
  - Das Urteil über die angefügte Datei oder URL.
  - Verwandte Informationen (Dateinummer, URLs, IPs oder Domänen), bei denen es sich um andere Entitäten handelt, die während der Detonation untersucht werden.
- *Screenshot der Detonation:* Dies zeigt Screenshot(n), die während des Detonationsprozesses aufgenommen wurden.
- *Detonation Details*: Dies sind die genauen Verhaltensdetails jedes Prozesses, der während der Detonation stattgefunden hat.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot der Detonationszusammenfassung mit der Kette, Zusammenfassung, Detonation und Screenshot unter der Überschrift *Deep Analysis*.":::

### <a name="other-innovations"></a>Weitere Innovationen

*Tags:* Dies sind Tags, die auf Benutzer angewendet werden. Wenn der Benutzer ein Empfänger ist, werden Administratoren ein *Empfängertag* angezeigt. Ebenso, wenn der Benutzer ein Absender ist, ein *Absendertag.* Dies wird auf der linken Seite der Seite "E-Mail-Entitäten" angezeigt (in dem Teil, der als *"sticky"* bezeichnet wird und somit an der Seite verankert ist).

*Aktueller* Zustellungsspeicherort: Der aktuelle Zustellungsspeicherort ist der Ort, an dem eine E-Mail nach Systemaktionen wie ZAP oder Administratoraktionen wie Verschieben zu gelöschten Elementen gelandet ist. Der aktuelle Zustellungsspeicherort ist nicht dazu gedacht, Administratoren über den aktuellen Speicherort der *Nachricht zu* informieren. Wenn ein Benutzer beispielsweise eine Nachricht löscht oder in das Archiv verschiebt, wird der Zustellungsspeicherort nicht aktualisiert. Wenn jedoch eine Systemaktion stattgefunden und den Speicherort aktualisiert hat (z. B. eine ZAP, die zu einem Verschieben einer E-Mail in Quarantäne führt), würde dies den Neuesten Zustellungsspeicherort in Quarantäne aktualisieren.

*E-Mail-Details:* Details, die für ein tieferes Verständnis der E-Mail erforderlich sind, die auf der Registerkarte *Analyse verfügbar* sind.

- *Exchange Transport rules (ETRs or Mailflow rules)*: Diese Regeln werden auf eine Nachricht auf der Transportebene angewendet und haben Vorrang vor Phishing- und Spamverkündungen. Diese können nur im Exchange Admin Center erstellt und geändert werden. Wenn jedoch etR für eine Nachricht gilt, werden hier der NAME und die GUID des ETR angezeigt. Wertvolle Informationen zur Nachverfolgung.

- *System Overrides*: Dies ist eine Möglichkeit, Ausnahmen vom Für eine Nachricht vorgesehenen Zustellungsspeicherort zu machen, indem der vom System angegebene Zustellungsspeicherort außer Kraft gesetzt wird (je nach Bedrohungs- und Erkennungstechnologie).

- *Junkpostfachregel:*"Junk" ist verborgene Posteingangsregel, die standardmäßig in jedem Postfach aktiviert ist.
  - Wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist, Exchange Online Protection (EOP) Nachrichten nach bestimmten Kriterien in Junk verschieben. Die Verschieben kann auf der Spamfilterungsverkündungsaktion Nachricht in Junk-E-Mail-Ordner verschieben oder auf der Liste blockierter Absender im Postfach basieren.  Durch Deaktivieren der Junk-E-Mail-Regel wird die Zustellung von Nachrichten an den Junk-E-Mail-Ordner basierend auf der Liste sicherer *Absender* im Postfach verhindert.
  - Wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, kann EOP Nachrichten nicht in den Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilterungs-Verdict-Aktion Nachricht in Junk-E-Mail-Ordner verschieben oder die Sammlung sicherer Listen im Postfach.  

- *Massenbeschwerdestufe (Bulk Complaint Level, BCL):* Die Massenbeschwerdestufe (Bulk Complaint Level, BCL) der Nachricht. Eine höhere BCL gibt an, dass eine Massen-E-Mail-Nachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (das natürliche Ergebnis, wenn es sich bei der E-Mail wahrscheinlich um Spam handelt).

- *Spam Confidence Level (SCL)*: Die Spamsicherheitsstufe (Spam Confidence Level, SCL) der Nachricht. Ein höherer Wert gibt an, dass die Nachricht mit größerer Wahrscheinlichkeit Spam ist.

- *Domänenname*: Ist der Absenderdomänenname.

- *Domänenbesitzer*: Gibt den Besitzer der sendenden Domäne an.

- *Domänenspeicherort*: Gibt den Speicherort der sendenden Domäne an.

- *Datum der Erstellung der Domäne*: Gibt das Erstellungsdatum der sendenden Domäne an. Eine neu erstellte Domäne ist etwas, mit dem Sie vorsichtig sein können, wenn andere Signale auf ein verdächtiges Verhalten hinweisen.

E-Mail-Authentifizierung: E-Mail-Authentifizierungsmethoden, die von Microsoft 365 verwendet werden, umfassen SPF, DKIM und DMARC.

- Sender Policy Framework (**SPF**): Beschreibt die Ergebnisse für die SPF-Überprüfung für die Nachricht. Mögliche Werte sind:
  - Pass (IP-Adresse): Die SPF-Überprüfung auf die übergebene Nachricht und enthält die IP-Adresse des Absenders. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten.
  - Fail (IP-Adresse): Die SPF-Überprüfung auf die Nachricht ist fehlgeschlagen und enthält die IP-Adresse des Absenders. Dies wird häufig als „Schwerer Fehler“ bezeichnet.
  - Softfail (Grund): Der SPF-Eintrag hat den Host als nicht senden zugelassen, befindet sich aber im Übergang.
  - Neutral: Der SPF-Eintrag gibt explizit an, dass nicht angegeben wird, ob die IP-Adresse zum Senden autorisiert ist.
  - Keine: Die Domäne hat keinen SPF-Eintrag, oder der SPF-Eintrag wird nicht zu einem Ergebnis ausgewertet.
  - Temperror: Ein temporärer Fehler ist aufgetreten. Dabei kann es sich beispielsweise um einen DNS-Fehler handeln. Dieselbe Überprüfung ist zu einem späteren Zeitpunkt möglicherweise erfolgreich.
  - Permerror: Ein dauerhafter Fehler ist aufgetreten. Dabei kann es sich zum Beispiel um einen Fehler handeln, bei dem die Domäne einen falsch formatierten SPF-Eintrag aufweist.

- DomainKeys Identified Mail (**DKIM**):
  - Pass: Gibt die DKIM-Prüfung für die übergebene Nachricht an.
  - Fail (reason): Gibt an, dass die DKIM-Überprüfung auf die Nachricht fehlgeschlagen ist und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte.
  - None: Gibt an, dass die Nachricht nicht signiert wurde. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.

- Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (**DMARC**):
  - Pass: Gibt die DMARC-Prüfung für die übergebene Nachricht an.
  - Fail: Gibt an, dass die DMARC-Überprüfung für die Nachricht fehlgeschlagen ist.
  - Bestguesspass: Gibt an, dass kein DMARC TXT-Eintrag für die Domäne vorhanden ist, aber wenn ein Eintrag vorhanden war, wäre die DMARC-Überprüfung auf die Nachricht bestanden.
  - None: Gibt an, dass kein DMARC TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.

*Zusammengesetzte Authentifizierung:* Dies ist ein Wert, der von Microsoft 365 verwendet wird, um die E-Mail-Authentifizierung wie SPF, DKIM und DMARC zu kombinieren, um zu ermitteln, ob die Nachricht authentifiziert ist. Es verwendet die *From:-Domäne* der E-Mail als Auswertungsgrundlage.
