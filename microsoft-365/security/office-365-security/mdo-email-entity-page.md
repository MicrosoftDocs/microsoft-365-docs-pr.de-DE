---
title: Die E-Mail-Entitätsseite von Microsoft Defender für Office 365 (MDO)
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
description: Microsoft Defender für Office 365 E5- und ATP P1- und ATP -P2-Kunden können jetzt eine 360-Grad-Ansicht jeder E-Mail mit E-Mail-Entitätsseite erhalten.
ms.openlocfilehash: 0a866b4d635e5c9e26b6fc065503b44ee2063e9f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289485"
---
# <a name="the-email-entity-page"></a>Die Seite "E-Mail-Entität"

**Inhalt dieses Artikels:**
- [Erreichen der E-Mail-Entitätsseite](#reach-the-email-entity-page)
- [Lesen der E-Mail-Entitätsseite](#read-the-email-entity-page)
- [Verwenden von Registerkarten der E-Mail-Entitätsseite](#use-email-entity-page-tabs)
- [Neu auf der E-Mail-Entitätsseite](#new-to-the-email-entity-page)

Administratoren von Microsoft Defender für Office 365 (oder MDO) E5 sowie MDO P1 und P2 verfügen über eine 360-Grad-Ansicht von E-Mails auf der Seite "E-Mail-Entität". Diese Go-to-E-Mail-Seite wurde erstellt, um Informationen zu verbessern, die über das [Flyout "E-Mail-Details" des Bedrohungs-Explorers übermittelt wurden.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>Erreichen der E-Mail-Entitätsseite

Über das vorhandene Office Security and Compliance Center (protection.office.com) oder das neue Microsoft 365 Security Center (security.microsoft.com) können Sie die E-Mail-Entitätsseite anzeigen und verwenden.

|Zentriert  |URL  |Navigation  |
|---------|---------|---------|
|Sicherheit & Compliance |protection.office.com | Threat Management > Explorer   |
|Microsoft 365 Security Center |security.microsoft.com | E-mail & Collaboration > Explorer |

Wählen Sie im Bedrohungs-Explorer den Betreff einer E-Mail aus, die Sie untersuchen. Oben im E-Mail-Flyout für diese E-Mail wird eine goldfarbene Leiste angezeigt. Diese Einladung zur neuen Seite lautet "Testen Sie unsere neue E-Mail-Entitätsseite mit anreicherten Daten...". Wählen Sie diese Option aus, um die neue Seite anzeigen zu können.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Sie sehen ein goldfarbenes Banner mit den Wörtern *Probieren Sie unsere neue E-Mail-Entitätsseite mit bereicherten Daten* aus, um zur neuen Erfahrung zu navigieren.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Diese Grafik der E-Mail-Entitätsseite konzentriert sich auf Überschriften, die Angezeigt werden. Beachten Sie, dass hier der E-Mail-Header angezeigt wird.":::

> [!NOTE]
> Die zum Anzeigen und Verwenden dieser Seite erforderlichen Berechtigungen sind dieselben wie zum Anzeigen des Bedrohungs-Explorers. Der Administrator muss Mitglied des globalen Admins oder globalen Lesers oder Sicherheitsadministrators oder Sicherheitsleseers sein.

## <a name="read-the-email-entity-page"></a>Lesen der E-Mail-Entitätsseite

Die Struktur ist so konzipiert, dass sie auf einen Blick leicht zu lesen und zu navigieren ist. Verschiedene Registerkarten am oberen Rand der Seite ermöglichen ihnen eine ausführlichere Untersuchung. So funktioniert das Layout:

1. Die am häufigsten benötigten Felder befinden sich auf der linken Seite des Flyouts. Diese Details sind "sticky", d. h., sie sind links verankert, unabhängig von der Registerkarte, zu der Sie im restlichen Flyout navigieren.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Grafik der E-Mail-Entitätsseite mit hervorgehobener linker Seite. Der Titel und die Fakten zur E-Mail-Zustellung sind hier zu Ende.":::

2. In der oberen rechten Ecke befinden sich die Aktionen, die für eine E-Mail-Nachricht ergriffen werden können. Alle Aktionen, die über Explorer ergriffen werden können, sind auch über die E-Mail-Entitätsseite verfügbar.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Grafik der E-Mail-Entitätsseite mit hervorgehobener *right*-Seite. Aktionen wie &quot;E-Mail-Vorschau&quot; und &quot;In Quarantäne wechseln&quot; sind hier zu finden.":::

3. Eine tiefer gehende Analyse kann durch Sortieren der restlichen Seite durchgeführt werden. Überprüfen Sie die E-Mail-Erkennungsdetails, den E-Mail-Authentifizierungsstatus und die Kopfzeile. Dieser Bereich sollte von Fall zu Fall betrachtet werden, aber die Informationen auf diesen Registerkarten sind für jede E-Mail verfügbar.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Der Hauptbereich dieser Seite enthält den E-Mail-Header und den Authentifizierungsstatus.":::

### <a name="use-email-entity-page-tabs"></a>Verwenden von Registerkarten der E-Mail-Entitätsseite

Mit den Registerkarten oben auf der Entitätsseite können Sie E-Mails effizient untersuchen.

1. **Zeitachse:** In der Zeitachsenansicht für eine E-Mail (auf der Zeitachse des Bedrohungs-Explorers) wird die ursprüngliche Zustellung an Post-Delivery-Ereignisse angezeigt, die in einer E-Mail auftreten. Bei E-Mails ohne Aktionen nach der Zustellung wird in der Ansicht die ursprüngliche Zustellungszeile in der Zeitachsenansicht angezeigt. Ereignisse wie: Automatische Bereinigung zur Nullstunde (ZAP), Behebung, URL-Klicks, usw. aus Quellen wie: System, Administrator und Benutzer, werden hier in der Reihenfolge angezeigt, in der sie aufgetreten sind.
2. **Analyse:** Analyse zeigt Felder, die Administratoren dabei helfen, eine E-Mail im Detail zu analysieren. In Fällen, in denen Administratoren mehr über Erkennungs-, Absender-/Empfänger- und E-Mail-Authentifizierungsdetails wissen müssen, sollten sie die Registerkarte "Analyse" verwenden. Links für Anlagen und URLs finden Sie auch auf dieser Seite unter "Verwandte Entitäten". Sowohl Anlagen als auch identifizierte Bedrohungen sind hier nummeriert, und wenn Sie darauf klicken, werden Sie direkt zu den Seiten "Anlagen" und "URL" geklickt. Diese Registerkarte verfügt auch über eine Ansichtskopfoption zum *Anzeigen des E-Mail-Headers.* Administratoren können aus Gründen der Übersichtlichkeit alle Details aus E-Mail-Kopfzeilen nebeneinander mit Informationen im Hauptbereich vergleichen.
3. **Anlagen:** Dadurch werden Anlagen untersucht, die in der E-Mail mit anderen Details zu Anlagen gefunden wurden. Die Anzahl der angezeigten Anlagen ist derzeit auf 10 beschränkt. Beachten Sie, dass hier auch Details zur Detonation von Anlagen angezeigt werden, die als bösartig festgestellt wurden.
4. **URLs:** Auf dieser Registerkarte werden URLs in der E-Mail mit weiteren Details zu den URLs aufgeführt. Die Anzahl der URLs ist derzeit auf 10 beschränkt, aber diese 10 sind priorisiert, um zuerst schädliche *URLs zu zeigen.* Priorisierung spart Ihnen Zeit und Erratenarbeit. Die URLs, die als bösartig und detoniert gefunden wurden, werden hier ebenfalls angezeigt.
5. **Ähnliche** E-Mails: Auf dieser Registerkarte werden alle E-Mails aufgeführt, die der Für diese E-Mail spezifischen Kombination aus Netzwerknachrichten-ID und Empfängern ähneln.  Ähnlichkeit basiert nur auf dem *Textkörper der* Nachricht. Die E-Mail-Entscheidung, sie als "ähnlich" zu kategorisieren, umfasst keine Überlegungen zu *Anlagen.*

## <a name="new-to-the-email-entity-page"></a>Neu auf der E-Mail-Entitätsseite

Diese E-Mail-Entitätsseite enthält neue Funktionen. Hier ist die Liste.

### <a name="email-preview-for-cloud-mailboxes"></a>E-Mail-Vorschau für Cloudpostfächer
Administratoren können eine Vorschau von E-Mails in Cloudpostfächern ***anzeigen,*** wenn die E-Mails noch in der Cloud vorhanden sind. Bei einem soft delete (durch einen Administrator oder Benutzer) oder ZAP (in Quarantäne) sind E-Mails am Cloudspeicherort nicht mehr vorhanden. In diesem Fall können Administratoren diese bestimmten E-Mails nicht in der Vorschau anzeigen. E-Mails, die gelöscht wurden oder bei denen die Zustellung fehlgeschlagen ist, haben es nie tatsächlich in das Postfach verschoben. Aus diesem Grund können Administratoren auch keine Vorschau dieser E-Mails anzeigen.

> [!WARNING]
>Für die Vorschau von E-Mails muss administratoren eine spezielle Rolle namens ***Preview** _ zugewiesen werden. Sie können diese Rolle hinzufügen, indem Sie zu _ *Permissions & roles** > Email & collaboration **roles** in *security.microsoft.com* oder **Permissions** in *protection.office.com .* Fügen Sie ***die Vorschaurolle*** zu einer der Rollengruppen oder eine Kopie einer Rollengruppe hinzu, mit der Administratoren in Ihrer Organisation im Bedrohungs-Explorer arbeiten können.

### <a name="detonation-details"></a>Detonation details

Diese Details sind spezifisch für E-Mail-Anlagen und URLs.

Benutzern werden detailreichere Detonationsdetails für bekannte schädliche Anlagen oder Hyperlinks in ihren Postfächern angezeigt, einschließlich Detonation Chain, Detonation Summary, Screenshot, and Observed Behavior Details, um Kunden zu verstehen, warum die Anlage oder URL als bösartig und abgesenkt eingestuft wurde.
 
- *Detonationskette:* Eine einzelne Datei- oder URL-Detonation kann mehrere Detonationen auslösen. Die Detonation Chain verfolgt den Pfad der Detonationen, einschließlich der ursprünglichen schädlichen Datei oder URL, die die Wertung verursacht hat, und alle anderen Dateien oder URLs, die durch die Detonation verursacht wurden. Diese URLs oder angefügten Dateien sind möglicherweise nicht direkt in der E-Mail vorhanden, aber die Analyse ist wichtig, um zu ermitteln, warum die Datei oder URL als bösartig ermittelt wurde.
- *Zusammenfassung der Detonation:* Hier finden Sie Informationen zu:
    - Zeitbereich der Detonation.
    - Die Angefügte Datei oder URL wird überprüft.
    - Verwandte Informationen (Dateinummer, URLs, IPs oder Domänen), bei denen es sich um andere Entitäten handelt, die während der Detonation untersucht werden.
- *Screenshot der Detonation:* Zeigt Screenshot(en), die während des Detonationsprozesses aufgenommen wurden.
- *Detonation details:* These are the exact behavior details of each process that was was place during the detonation.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot of the detonation summary showing the chain, summary, detonation details, and screenshot under the heading *Deep Analysis*.":::

### <a name="other-innovations"></a>Weitere Innovationen

*Tags:* Dies sind Tags, die auf Benutzer angewendet werden. Wenn der Benutzer ein Empfänger ist, wird Administratoren ein *Empfängertag* angezeigt. Ebenso, wenn der Benutzer ein Absender ist, ein *Absendertag.* Diese wird auf der linken Seite der Seite mit den E-Mail-Entitäten angezeigt (in dem Teil, der als *"sticky"* beschrieben wird und somit mit der Seite verankert ist).

*Aktueller* Zustellungsspeicherort: Der aktuelle Zustellungsspeicherort ist der Ort, an dem eine E-Mail nach Systemaktionen wie ZAP oder Administratoraktionen wie "Nach gelöschten Elementen verschieben" gelandet ist. Der aktuelle Zustellungsspeicherort dient nicht dazu, Administratoren über den aktuellen Speicherort der *Nachricht zu* informieren. Wenn ein Benutzer beispielsweise eine Nachricht löscht oder in ein Archiv verschiebt, wird der Zustellungsspeicherort nicht aktualisiert. Wenn jedoch eine Systemaktion stattgefunden hat und der Speicherort aktualisiert wurde (z. B. ein ZAP, das zu einer E-Mail führt, die in Quarantäne verschoben wird), würde dies den neuesten Zustellungsspeicherort in "Quarantäne" aktualisieren.

*E-Mail-Details:* Details, die für ein tieferes Verständnis der E-Mails erforderlich sind, die auf der Registerkarte *"Analyse" verfügbar* sind.

- *Exchange-Transportregeln (ETRs oder E-Mail-Regeln):* Diese Regeln werden auf eine Nachricht auf der Transportebene angewendet und haben Vorrang vor Phishing- und Spamverkündungen. Diese können nur im Exchange Admin Center erstellt und geändert werden. Wenn jedoch etR für eine Nachricht gilt, werden hier der ETR-Name und die GUID angezeigt. Wertvolle Informationen für Nachverfolgungszwecke.
    
- *Systemüberschreibungen: Dies* ist eine Möglichkeit, Ausnahmen vom Für eine Nachricht vorgesehenen Zustellungsspeicherort zu machen, indem der vom System angegebene Übermittlungsort außer Kraft gesetzt wird (je nach Bedrohungs- und Erkennungstechnologie).
    
- *Junk-Postfachregel:*"Junk" ist ausgeblendete Posteingangsregel, die standardmäßig in jedem Postfach aktiviert ist.
    - Wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist, kann Exchange Online Protection (EOP) Nachrichten gemäß einigen Kriterien in Junk verschieben. Die Verschieben kann auf der Spamfilterungsaktion "Nachricht in Junk-E-Mail-Ordner verschieben" oder auf der Liste blockierter Absender für das Postfach basieren.  Durch Deaktivieren der Junk-E-Mail-Regel wird die Zustellung von Nachrichten an den Junk-E-Mail-Ordner basierend auf der Liste sicherer *Absender* im Postfach verhindert.
    - Wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, kann EOP Nachrichten nicht basierend auf der Spamfilterungsaktion "Nachricht in Junk-E-Mail-Ordner verschieben" oder der Sammlung sicherer Listen im Postfach in den Junk-E-Mail-Ordner verschieben. 
    
- *BCL (Bulk Compliant Level):* Der BCL (Bulk Complaint Level) der Nachricht. Ein höherer BCL zeigt an, dass eine Massen-E-Mail-Nachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (das natürliche Ergebnis, wenn es sich bei der E-Mail wahrscheinlich um Spam handelt).
    
- *SCL (Spam Confidence Level):* Die SCL (Spam Confidence Level) der Nachricht. Ein höherer Wert gibt an, dass die Nachricht mit größerer Wahrscheinlichkeit Spam ist.

- *Domänenname:* Ist der Domänenname des Absenders.
    
- *Domänenbesitzer:* Gibt den Besitzer der sendenden Domäne an.
    
- *Domänenspeicherort:* Gibt den Speicherort der sendenden Domäne an.
    
- *Erstellungsdatum der Domäne:* Gibt das Erstellungsdatum der sendenden Domäne an. Eine neu erstellte Domäne kann vorsichtig sein, wenn andere Signale auf verdächtiges Verhalten hinweisen.

E-Mail-Authentifizierung: Von Microsoft 365 verwendete E-Mail-Authentifizierungsmethoden umfassen SPF, DKIM und DMARC.

- Sender Policy Framework (**SPF**): Beschreibt ergebnisse für die SPF-Überprüfung für die Nachricht. Mögliche Werte sind:
    - Pass (IP-Adresse): Die SPF-Überprüfung für die übergebene Nachricht und enthält die IP-Adresse des Absenders. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten.
    - Fehler (IP-Adresse): Fehler bei der SPF-Überprüfung der Nachricht und enthält die IP-Adresse des Absenders. Dies wird häufig als „Schwerer Fehler“ bezeichnet.
    - Softfail (Grund): Der SPF-Eintrag hat festgelegt, dass der Host nicht senden darf, sich aber im Übergang befindet.
    - Neutral: Der SPF-Eintrag gibt explizit an, dass nicht bestätigt wird, ob die IP-Adresse zum Senden autorisiert ist.
    - Keine: Die Domäne hat keinen SPF-Eintrag, oder der SPF-Eintrag wird nicht zu einem Ergebnis ausgewertet.
    - Temperror: Ein temporärer Fehler ist aufgetreten. Dabei kann es sich beispielsweise um einen DNS-Fehler handeln. Dieselbe Überprüfung ist zu einem späteren Zeitpunkt möglicherweise erfolgreich.
    - Permerror: Ein dauerhafter Fehler ist aufgetreten. Dabei kann es sich zum Beispiel um einen Fehler handeln, bei dem die Domäne einen falsch formatierten SPF-Eintrag aufweist.

- DomainKeys Identified Mail (**DKIM**):
    - Pass: Gibt die DKIM-Überprüfung für die übergebene Nachricht an.
    - Fehler (Grund): Gibt an, dass die DKIM-Überprüfung auf die Nachricht fehlgeschlagen ist und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte.
    - Keine: Gibt an, dass die Nachricht nicht signiert wurde. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.

- Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (**DMARC**):
    - Pass: Gibt die DMARC-Überprüfung für die übergebene Nachricht an.
    - Fehler: Gibt an, dass die DMARC-Überprüfung für die Nachricht fehlgeschlagen ist.
    - Bestguesspass: Gibt an, dass kein DMARC-TXT-Eintrag für die Domäne vorhanden ist, aber wenn einer vorhanden wäre, wäre die DMARC-Überprüfung für die Nachricht erfolgreich.
    - Keine: Gibt an, dass kein DMARC-TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.

*Zusammengesetzte Authentifizierung:* Dies ist ein Wert, der von Microsoft 365 verwendet wird, um die E-Mail-Authentifizierung wie SPF, DKIM und DMARC zu kombinieren, um zu ermitteln, ob die Nachricht authentifiziert ist. Als Grundlage für die Auswertung wird die *"Von:"-Domäne* der E-Mail verwendet.
