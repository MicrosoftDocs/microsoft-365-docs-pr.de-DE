---
title: Die Microsoft Defender für Office 365 (MDO)-E-Mail-Entitätsseite
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
description: Microsoft Defender für Office 365 E5 sowie P1- und P2-Kunden können jetzt eine 360-Grad-Ansicht jeder E-Mail mit der E-Mail-Entitätsseite erhalten.
ms.openlocfilehash: d2f5a5b20034ef22b8e3894885079609a9ad5874
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083278"
---
# <a name="the-email-entity-page"></a>Die Seite „E-Mail-Entität"

**Inhalt dieses Artikels:**
- [Erreichen der E-Mail-Entitätsseite](#reach-the-email-entity-page)
- [Lesen der E-Mail-Entitätsseite](#read-the-email-entity-page)
- [Verwenden von Registerkarten der E-Mail-Entitätsseite](#use-email-entity-page-tabs)
- [Neu bei der E-Mail-Entitätsseite](#new-to-the-email-entity-page)

Administratoren von Microsoft Defender für Office 365 (oder MDO) E5 und MDO P1 und P2 verfügen über eine 360-Grad-Ansicht von E-Mails mithilfe der **Entitätsseite "E-Mail".** Diese Go-to-E-Mail-Seite wurde erstellt, um informationen zu verbessern, die im [Flyout "E-Mail-Details" des Bedrohungs-Explorers](threat-explorer-views.md)bereitgestellt werden.

## <a name="reach-the-email-entity-page"></a>Erreichen der E-Mail-Entitätsseite

Die E-Mail-Entitätsseite ist im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) im **E-Mail-& Zusammenarbeits-Explorer** \> verfügbar. Oder verwenden Sie , um direkt zur **Explorer-Seite** zu <https://security.microsoft.com/threatexplorer> wechseln.

Wählen Sie im **Explorer** den Betreff einer E-Mail aus, die Sie untersuchen. Oben im E-Mail-Flyout für diese E-Mail wird ein Goldbalken angezeigt. Diese Einladung zur neuen Seite lautet "Testen Sie unsere neue E-Mail-Entitätsseite mit erweiterten Daten...". Wählen Sie diese Option aus, um die neue Seite anzuzeigen.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Sie sehen ein goldfarbenes Banner mit den Wörtern *Testen Sie unsere neue E-Mail-Entitätsseite mit erweiterten Daten*, um zur neuen Oberfläche zu navigieren.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Diese Grafik der E-Mail-Entitätsseite konzentriert sich auf Überschriften, die Angezeigt werden. Beachten Sie, dass der E-Mail-Header hier angezeigt wird.":::

> [!NOTE]
> Die erforderlichen Berechtigungen zum Anzeigen und Verwenden dieser Seite sind die gleichen wie zum Anzeigen des **Explorers.** Der Administrator muss Mitglied des globalen Administrators oder globalen Lesers oder Sicherheitsadministrators oder Sicherheitsleseberechtigten sein. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).

## <a name="read-the-email-entity-page"></a>Lesen der E-Mail-Entitätsseite

Die Struktur ist so konzipiert, dass sie auf einen Blick leicht zu lesen und zu navigieren ist. Mit verschiedenen Registerkarten am oberen Rand der Seite können Sie ausführlicher untersuchen. So funktioniert das Layout:

1. Die am häufigsten benötigten Felder befinden sich auf der linken Seite des Flyouts. Diese Details sind "sticky", was bedeutet, dass sie links verankert sind, unabhängig von der Registerkarte, zu der Sie im restlichen Fly-Out navigieren.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Grafik der E-Mail-Entitätsseite mit hervorgehobener linker Seite. Der Titel und die Fakten zur E-Mail-Zustellung sind hier vorbei.":::

2. In der oberen rechten Ecke befinden sich die Aktionen, die für eine E-Mail ausgeführt werden können. Alle Aktionen, die über **explorer** ausgeführt werden können, sind auch über die E-Mail-Entitätsseite verfügbar.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Grafik der E-Mail-Entitätsseite mit hervorgehobener *right*-Seite, dieses Mal. Aktionen wie &quot;E-Mail-Vorschau&quot; und &quot;In Quarantäne gehen&quot; sind hier.":::

3. Eine ausführlichere Analyse kann durch Sortieren über den Rest der Seite erfolgen. Überprüfen Sie die E-Mail-Erkennungsdetails, den E-Mail-Authentifizierungsstatus und die Kopfzeile. Dieser Bereich sollte von Fall zu Fall betrachtet werden, aber die Informationen auf diesen Registerkarten sind für jede E-Mail verfügbar.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Der Hauptbereich dieser Seite enthält den E-Mail-Header und den Authentifizierungsstatus.":::

### <a name="use-email-entity-page-tabs"></a>Verwenden von Registerkarten der E-Mail-Entitätsseite

Mit den Registerkarten oben auf der Entitätsseite können Sie E-Mails effizient untersuchen.

1. **Zeitachse:** Die Zeitachsenansicht für eine E-Mail (pro Explorer-Zeitachse) zeigt die ursprüngliche Zustellung an Post-Delivery-Ereignisse an, die in einer E-Mail auftreten.  Bei E-Mails ohne Aktionen nach der Zustellung wird in der Ansicht die ursprüngliche Lieferzeile in der Zeitachsenansicht angezeigt. Ereignisse wie: Zero-Hour Auto Purge (ZAP), Remediate, URL clicks, et cetera, from sources like: system, admin, and user, show up here, in the order in which they occurred.
2. **Analyse:** Die Analyse zeigt Felder, die Administratoren helfen, eine E-Mail im Detail zu analysieren. Für Fälle, in denen Administratoren mehr über Erkennungs-, Absender-/Empfänger- und E-Mail-Authentifizierungsdetails wissen müssen, sollten sie die Registerkarte "Analyse" verwenden. Links für Anlagen und URLs finden Sie auch auf dieser Seite unter "Verwandte Entitäten". Sowohl Anlagen als auch identifizierte Bedrohungen sind hier nummeriert, und durch Klicken gelangen Sie direkt zu den Anlagen- und URL-Seiten. Diese Registerkarte verfügt auch über eine Ansichtsheaderoption, um *den E-Mail-Header anzuzeigen.* Administratoren können alle Details aus E-Mail-Kopfzeilen nebeneinander mit Informationen im Hauptbereich vergleichen, um Klarheit zu schaffen.
3. **Anlagen: Dies** überprüft Anlagen, die in der E-Mail gefunden wurden, mit anderen Details zu Anlagen. Die Anzahl der angezeigten Anlagen ist derzeit auf 10 begrenzt. Beachten Sie, dass detonation details for attachments found to be malicious is also shown here.
4. **URLs:** Diese Registerkarte listet URLs auf, die in der E-Mail mit anderen Details zu den URLs gefunden werden. Die Anzahl der URLs ist derzeit auf 10 beschränkt, aber diese 10 werden priorisiert, um *zuerst schädliche URLs* anzuzeigen. Die Priorisierung spart Ihnen Zeit und Ratenarbeit. Die URLs, die als bösartig und detoniert eingestuft wurden, werden hier ebenfalls angezeigt.
5. **Ähnliche E-Mails:** Auf dieser Registerkarte werden alle E-Mails aufgelistet, die der Kombination aus *Netzwerknachrichten-ID und Empfänger* ähneln, die für diese E-Mail spezifisch sind. Die Ähnlichkeit basiert nur auf dem *Nachrichtentext.* Die in E-Mails getroffenen Ermittlungen, um sie als "ähnlich" zu kategorisieren, umfassen keine Berücksichtigung von *Anlagen.*

## <a name="new-to-the-email-entity-page"></a>Neu bei der E-Mail-Entitätsseite

Diese E-Mail-Entitätsseite enthält neue Funktionen. Hier ist die Liste.

### <a name="email-preview-for-cloud-mailboxes"></a>E-Mail-Vorschau für Cloudpostfächer

Administratoren können eine Vorschau von E-Mails in Cloudpostfächern anzeigen, ***wenn*** die E-Mails noch in der Cloud vorhanden sind. Im Falle eines vorläufigen Löschens (durch einen Administrator oder Benutzer) oder ZAP (unter Quarantäne) sind E-Mails nicht mehr am Cloud-Speicherort vorhanden. In diesem Fall können Administratoren keine Vorschau dieser spezifischen E-Mails anzeigen. E-Mails, die verworfen wurden oder bei denen die Zustellung fehlgeschlagen ist, gelangten nie in das Postfach. Daher können Administratoren auch keine Vorschau dieser E-Mails anzeigen.

> [!WARNING]
> Für die Vorschau von E-Mails ist eine spezielle Rolle namens **"Vorschau"** erforderlich. Sie können diese Rolle im Microsoft 365 Defender Portal hinzufügen, wie unter [E-Mail & Rollen für die Zusammenarbeit im Microsoft 365 Defender Portal](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal)beschrieben. Möglicherweise müssen Sie dort eine neue Rollengruppe **"E-Mail & Zusammenarbeit"** erstellen und die **Rolle "Vorschau"** zu dieser neuen Rollengruppe hinzufügen oder die **Rolle "Vorschau"** zu einer Rollengruppe hinzufügen, mit der Administratoren in Ihrer Organisation im **Explorer** arbeiten können.

### <a name="detonation-details"></a>Detonationsdetails

Diese Details gelten speziell für E-Mail-Anlagen und URLs. Benutzer können diese Details sehen, indem sie zum Explorer wechseln und den *Erkennungstechnologiefilter* anwenden, der auf dateidetonation oder URL-Detonation festgelegt ist. E-Mails, die nach Dateidetonation gefiltert werden, enthalten eine schädliche Datei mit Detonationsdetails, und die nach URLs gefilterten E-Mails enthalten eine schädliche URL und deren Detonationsdetails.

Benutzern werden erweiterte Detonationsdetails für bekannte bösartige Anlagen oder URLs in ihren E-Mails angezeigt, die für ihren spezifischen Mandanten detoniert wurden. Es besteht aus Detonation Chain, Detonation Summary, Screenshot und Observed Behavior Details, um Kunden zu verstehen, warum die Anlage oder URL als bösartig und detoniert eingestuft wurde.

1. *Detonationskette*. Eine einzelne Datei oder URL-Detonation kann mehrere Detonationen auslösen. Die Detonationskette verfolgt den Pfad der Detonationen, einschließlich der ursprünglichen schädlichen Datei oder URL, die die Bewertung verursacht hat, und aller anderen Dateien oder URLs, die durch die Detonation ausgelöst wurden. Diese URLs oder angefügten Dateien sind möglicherweise nicht direkt in der E-Mail vorhanden, aber das Einschließen dieser Analyse ist wichtig, um zu bestimmen, warum die Datei oder URL als böswillig eingestuft wurde.  

    > [!NOTE]
    > Dies kann nur das Element der obersten Ebene anzeigen, wenn keine der mit ihm verknüpften Entitäten als problematisch eingestuft oder detoniert wurde.

1. *Die Detonation Summary* bietet eine grundlegende Zusammenfassung für die Detonation, z. B. *Analysezeit,* Zeitpunkt der Detonation, Betriebssystem und Anwendung, Betriebssystem und Anwendung, in denen die Detonation aufgetreten ist, Dateigröße und Bewertungsgrund.
1. *Screenshots* zeigen die Screenshots, die während der Detonation aufgenommen wurden. Während der Detonation kann es mehrere Screenshots geben. Es werden keine Screenshots für
    - Containertypdateien wie .zip oder .rar.
    - Wenn eine URL in einem Link geöffnet wird, der eine Datei direkt herunterlädt. Die heruntergeladene Datei wird jedoch in der Detonationskette angezeigt.
1. *Verhaltensdetails* sind ein Export, der Verhaltensdetails wie genaue Ereignisse anzeigt, die während der Detonation stattgefunden haben, und Observablen, die URLs, IPs, Domänen und Dateien enthalten, die während der Detonation gefunden wurden (und entweder problematisch oder gutartig sein können). Beachten Sie, dass möglicherweise keine Verhaltensdetails für Folgendes vorhanden sind:
    - Containerdateien wie .zip oder .rar, die andere Dateien enthalten.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot der Detonationszusammenfassung mit der Kette, Zusammenfassung, Detonationsdetails und Screenshot unter der Überschrift *Umfassende Analyse*.":::

### <a name="other-innovations"></a>Weitere Innovationen

*Tags:* Dies sind Tags, die auf Benutzer angewendet werden. Wenn der Benutzer ein Empfänger ist, wird Administratoren ein *Empfängertag* angezeigt. Ebenso gilt, wenn der Benutzer ein Absender ist, ein *Absendertag.* Dies wird auf der linken Seite der Seite "E-Mail-Entitäten" angezeigt (in dem Teil, der als *stickig* und damit an der Seite verankert ist).

*Letzter Zustellungsort:* Der neueste Zustellungsort ist der Ort, an dem eine E-Mail nach Systemaktionen wie ZAP oder Administratoraktionen wie "Zu gelöschten Elementen verschieben" gelandet ist. Der neueste Zustellungsort dient nicht dazu, Administratoren über den *aktuellen* Speicherort der Nachricht zu informieren. Wenn ein Benutzer beispielsweise eine Nachricht löscht oder in das Archiv verschiebt, wird der Übermittlungsort nicht aktualisiert. Wenn jedoch eine Systemaktion ausgeführt und der Speicherort aktualisiert wurde (z. B. ein ZAP, der dazu führt, dass eine E-Mail in Quarantäne verschoben wird), würde dies den neuesten Übermittlungsspeicherort in Quarantäne aktualisieren.

*E-Mail-Details:* Details, die für ein tieferes Verständnis der E-Mails erforderlich sind, die auf der Registerkarte *"Analyse"* verfügbar sind.

- *Exchange Transportregeln (auch als Nachrichtenflussregeln oder ETRs bezeichnet):* Diese Regeln werden auf eine Nachricht auf der Transportebene angewendet und haben Vorrang vor Phishing- und Spambewertungen. Diese können nur im Exchange Admin Center erstellt und geändert werden, aber wenn etr für eine Nachricht gilt, werden hier der ETR-Name und die GUID angezeigt. Wertvolle Informationen für Nachverfolgungszwecke.

- *Systemüberschreibungen: Dies* ist eine Möglichkeit, Ausnahmen vom Übermittlungsort zu machen, der für eine Nachricht vorgesehen ist, indem der vom System angegebene Übermittlungsort überschrieben wird (gemäß der Bedrohungs- und Erkennungstechnologie).

- *Junk-Postfachregel:*"Junk" ist eine ausgeblendete Posteingangsregel, die standardmäßig in jedem Postfach aktiviert ist.
  - Wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist, kann Exchange Online Protection (EOP) Nachrichten nach bestimmten Kriterien in Junk verschieben. Die Verschiebung kann auf der Spamfilterungsbewertungsaktion *"Nachricht in Junk-E-Mail-Ordner* verschieben" oder auf der Liste der blockierten Absender im Postfach basieren. Durch Deaktivieren der Junk-E-Mail-Regel wird die Zustellung von Nachrichten an den Junk-E-Mail-Ordner basierend auf der *Liste der Tresor Absender* im Postfach verhindert.
  - Wenn die Junk-E-Mail-Regel für das Postfach *deaktiviert* ist, kann EOP Nachrichten basierend auf der Spamfilter-Bewertungsaktion *"Nachricht in Junk-E-Mail-Ordner verschieben"* oder der sicheren Listensammlung im Postfach nicht in den Junk-E-Mail-Ordner verschieben.

- *BCL (Bulk Complaint Level):* Die BCL-Ebene (Bulk Complaint Level) der Nachricht. Ein höherer BCL-Wert weist darauf hin, dass eine Massen-E-Mail-Nachricht mit größerer Wahrscheinlichkeit Beschwerden generiert (das natürliche Ergebnis, wenn die E-Mail wahrscheinlich Spam ist).

- *SCL (Spam Confidence Level):* Die SCL-Stufe (Spam Confidence Level) der Nachricht. Ein höherer Wert gibt an, dass die Nachricht mit größerer Wahrscheinlichkeit Spam ist.

- *Domänenname:* Ist der Absenderdomänenname.

- *Domänenbesitzer:* Gibt den Besitzer der sendenden Domäne an.

- *Domänenspeicherort:* Gibt den Speicherort der sendenden Domäne an.

- *Erstellungsdatum* der Domäne: Gibt das Erstellungsdatum der sendenden Domäne an. Bei einer neu erstellten Domäne können Sie vorsichtig sein, wenn andere Signale auf verdächtiges Verhalten hinweisen.

*E-Mail-Authentifizierung:* E-Mail-Authentifizierungsmethoden, die von Microsoft 365 verwendet werden, umfassen SPF, DKIM und DMARC.

- Sender Policy Framework (**SPF**): Beschreibt die Ergebnisse für die SPF-Prüfung für die Nachricht. Mögliche Werte sind:
  - Pass (IP-Adresse): Die SPF-Prüfung auf die übergebene Nachricht und schließt die IP-Adresse des Absenders ein. Der Client kann E-Mails im Auftrag der Absenderdomäne senden oder weiterleiten.
  - Fehler (IP-Adresse): Die SPF-Prüfung auf die Nachricht ist fehlgeschlagen und enthält die IP-Adresse des Absenders. Dies wird häufig als „Schwerer Fehler“ bezeichnet.
  - Softfail (Grund): Der SPF-Eintrag hat festgelegt, dass der Host nicht senden darf, sich aber im Übergang befindet.
  - Neutral: Der SPF-Eintrag gibt explizit an, dass nicht bestätigt wird, ob die IP-Adresse zum Senden autorisiert ist.
  - Keine: Die Domäne verfügt nicht über einen SPF-Eintrag, oder der SPF-Eintrag wird nicht als Ergebnis ausgewertet.
  - Temperror: Ein temporärer Fehler ist aufgetreten. Dabei kann es sich beispielsweise um einen DNS-Fehler handeln. Dieselbe Überprüfung ist zu einem späteren Zeitpunkt möglicherweise erfolgreich.
  - Permerror: Ein dauerhafter Fehler ist aufgetreten. Dabei kann es sich zum Beispiel um einen Fehler handeln, bei dem die Domäne einen falsch formatierten SPF-Eintrag aufweist.

- DomainKeys Identified Mail (**DKIM**):
  - Pass: Gibt die DKIM-Prüfung für die übergebene Nachricht an.
  - Fehler (Grund): Gibt an, dass die DKIM-Überprüfung für die Nachricht fehlgeschlagen ist und warum. Wenn die Nachricht beispielsweise nicht signiert war oder die Signatur nicht überprüft werden konnte.
  - Keine: Gibt an, dass die Nachricht nicht signiert wurde. Dies kann darauf hinweisen, dass die Domäne über einen DKIM-Eintrag verfügt oder dass der DKIM-Eintrag nicht zu einem Ergebnis ausgewertet wird. Dieser Wert gibt nur an, dass die Nachricht nicht signiert war.

- Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (**DMARC**):
  - Pass: Gibt die DMARC-Prüfung für die übergebene Nachricht an.
  - Fehler: Gibt an, dass die DMARC-Prüfung für die Nachricht fehlgeschlagen ist.
  - Bestguesspass: Gibt an, dass kein DMARC TXT-Eintrag für die Domäne vorhanden ist, aber wenn einer vorhanden wäre, wäre die DMARC-Prüfung für die Nachricht erfolgreich.
  - Keine: Gibt an, dass kein DMARC TXT-Eintrag für die sendende Domäne in DNS vorhanden ist.

*Zusammengesetzte Authentifizierung:* Dies ist ein Wert, der von Microsoft 365 verwendet wird, um die E-Mail-Authentifizierung wie SPF, DKIM und DMARC zu kombinieren, um zu bestimmen, ob die Nachricht authentifiziert ist. Es verwendet die *From:-Domäne* der E-Mail als Grundlage für die Auswertung.
