---
title: Microsoft 365 Exchange Online Datenlöschung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie das Löschen von Daten für Postfächer und Elemente in Postfächern in Exchange Online umgehen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4b4d30da70001967ca73377f10a4cd417577b72
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695951"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Exchange Online Löschen von Daten in Microsoft 365

In Exchange Online gibt es zwei Arten von Löschungen: weiche Löschungen und harte Löschungen. Dies gilt sowohl für Postfächer als auch für Elemente in einem Postfach.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Vorläufig gelöschte und hart gelöschte Postfächer
Ein vorläufig gelöschtes Benutzerpostfach ist ein Postfach, das mit dem Microsoft 365 Admin Center oder dem Cmdlet Remove-Mailbox gelöscht wurde und sich noch nicht länger als 30 Tage im Papierkorb von Azure Active Directory befindet. Ein Postfach kann auf eine der folgenden Arten vorläufig gelöscht werden:
- Das zugeordnete Azure Active Directory-Benutzerkonto des Benutzerpostfachs wird vorläufig gelöscht (das Benutzerobjekt liegt außerhalb des Gültigkeitsbereichs oder im Papierkorb Container).
- Das zugeordnete Azure Active Directory-Benutzerkonto des Benutzerpostfachs wurde endgültig gelöscht, das Exchange Online Postfach jedoch unter einem Beweissicherungsverfahren oder einem eDiscovery-Speicher.
- Das zugeordnete Azure-Active Directory Benutzerkonto des Benutzerpostfachs wurde in den letzten 30 Tagen bereinigt. Hierbei handelt es sich um die maximale Beibehaltungsdauer Exchange Online das Postfach in einem weichen Status befindet, bevor es endgültig gelöscht und nicht wiederhergestellt werden kann.

Ein hart gelöschtes Benutzerpostfach ist ein Postfach, das auf eine der folgenden Weisen gelöscht wurde:
- Das Benutzerpostfach wurde für mehr als 30 Tage vorläufig gelöscht, und der zugehörige Azure Active Directory-Benutzer wurde endgültig gelöscht. Alle Postfachinhalte wie e-Mails, Kontakte und Dateien werden endgültig gelöscht.
- Das Benutzerkonto, das dem Benutzerpostfach zugeordnet ist, wurde aus dem Azure-Active Directory hart gelöscht. Das Benutzerpostfach ist jetzt in Exchange Online vorläufig gelöscht und wird 30 Tage lang in einem Soft-Deleted-Zustand verbleibt. Wenn in einem Zeitraum von 30 Tagen ein neuer Azure Active Directory-Benutzer vom ursprünglichen Empfängerkonto mit demselben **ExchangeGuid** oder **ArchiveGuid**synchronisiert wird und dieses neue Konto für Exchange Online lizenziert wird, führt dies zu einem harten Löschen des ursprünglichen Benutzerpostfachs. Alle Postfachinhalte wie e-Mails, Kontakte und Dateien werden endgültig gelöscht.
- Ein vorläufig gelöschtes Postfach wird mithilfe von **Remove-Mailbox-PermanentlyDelete**gelöscht.

In den obigen Lösch Szenarien wird davon ausgegangen, dass das Benutzerpostfach nicht in einem der Haltestatus, wie Beweissicherungsverfahren oder eDiscovery halten. Wenn das Postfach einen beliebigen Aufbewahrungs aufweist, kann das Postfach nicht gelöscht werden. Für alle Empfängertypen von e-Mail-Benutzern werden alle [Aufbewahrungs](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) Einstellungen ignoriert und haben keine Auswirkung auf hart Löschungen oder weiche Löschvorgänge.

## <a name="soft-deleted-and-hard-deleted-items"></a>Vorläufig gelöschte und hart gelöschte Elemente
Wenn ein Benutzer ein Postfachelement löscht (beispielsweise eine e-Mail-Nachricht, einen Kontakt, einen Kalendertermin oder eine Aufgabe), wird das Element in den Ordner "refundable Items" und in einen Unterordner mit dem Namen "Deletions" verschoben. Dies wird als weiche Löschung bezeichnet. Die Aufbewahrungsdauer für gelöschte Elemente im Ordner Löschvorgänge hängt von der Aufbewahrungsdauer für gelöschte Elemente ab, die für das Postfach festgelegt ist. In einem Exchange Online Postfach werden gelöschte Elemente standardmäßig 14 Tage lang aufbewahrt, aber Exchange Online Administratoren können diese Einstellung ändern, um den Zeitraum auf maximal 30 Tage zu verlängern. (Ausführliche Anweisungen zum Verlängern des Aufbewahrungszeitraums für gelöschte Elemente für ein Exchange Online Postfach finden Sie unter Ändern der Aufbewahrungsdauer [für ein Exchange Online Postfach für dauerhaft gelöschte Elemente](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).) Benutzer können gelöschte Elemente wiederherstellen oder löschen, bevor die Aufbewahrungszeit für ein gelöschtes Element abläuft. Dazu verwenden Sie das Feature Gelöschte Elemente wiederherstellen in Microsoft Outlook oder Outlook im Internet.

Wenn ein Benutzer ein gelöschtes Element mithilfe der Funktion Gelöschte Elemente wiederherstellen in Outlook oder Outlook im Internet löscht, wird dies als schweres Löschen bezeichnet. In Exchange Online ist die Wiederherstellung einzelner Elemente standardmäßig aktiviert, wenn ein neues Postfach erstellt wird, sodass ein Administrator weiterhin hart gelöschte Elemente [Wiederherstellen](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) kann, bevor der Aufbewahrungszeitraum für gelöschte Elemente abläuft. Zudem werden Kopien des ursprünglichen Elements, wenn die Wiederherstellung einzelner Elemente aktiviert ist, beibehalten, sofern die Nachricht durch einen Benutzer oder Prozess geändert wird.

## <a name="page-zeroing"></a>Unwiderrufliches Löschen
*Nullen* ist ein Sicherheitsmechanismus, der entweder Nullen oder ein binäres Muster über gelöschte Daten schreibt, sodass die Wiederherstellung der gelöschten Daten schwieriger ist. In Exchange Online verwenden Postfachdatenbanken *Seiten* als ihre Speichereinheit und implementieren einen überschreibenden Prozess namens *"Seiten-NULL*stellen". Die Seiten zurücknullung ist standardmäßig aktiviert und kann nicht von Kunden oder von Microsoft deaktiviert werden. Vorgänge zur Nullstellung von Seiten werden in den Transaktionsprotokolldateien aufgezeichnet, sodass alle Kopien einer bestimmten Datenbank auf ähnliche Weise auf Seite Null gestellt werden. Durch das unwiderrufliche Löschen einer Seite in einer aktiven Datenbankkopie wird die Seite auf passiven Kopien der Datenbank gelöscht.

Das unwiderrufliche Löschen von Seiten schreibt ein binäres Muster über hart gelöschte Datensätze. Das Muster für Seiten Nullen ist spezifisch für ESE-Vorgänge (Extensible Storage Engine) (der Name des internen Datenbankmoduls, das von Servern in Exchange Online verwendet wird) und unterscheidet sich für Laufzeitvorgänge im Vergleich zu Hintergrunddaten Bank Wartungsvorgängen. (Die Wartung der Hintergrund Datenbank ist ein Prozess, der die einzelnen Datenbanken kontinuierlich überprüft und überprüft. Die primäre Funktion besteht in der Prüfsummen Datenbank-Seiten, aber Sie behandelt auch das Bereinigen von Leerzeichen und das Löschen von Datensätzen und Seiten, die aufgrund eines Speicher Absturzes nicht gelöscht wurden.)

In der folgenden Tabelle sind die Füllmuster zusammengestellt, die für die speziellen Laufzeitvorgänge verwendet werden.

| ESE-Laufzeitvorgang   | Füllmuster |
|--------------------------|--------------|
| Ersetzen                  | R            |
| Datensatz/Long-Wert löschen | D            |
| Freigegebener Seitenspeicherplatz         | H            |


In der folgenden Tabelle sind die Füllmuster zusammengestellt, die den speziellen Vorgängen entsprechen, die bei der Hintergrundwartung einer ESE-Datenbank ausgeführt werden.

| Hintergrundwartungsvorgang für ESE-Datenbank | Füllmuster |
|-----------------------------------------------|--------------|
| Datensatz löschen                                 | D            |
| Long-Wert löschen                             | L            |
| Freigegebener Seitenspeicherplatz einer teilweise verwendeten Seite       | Z            |
| Freigegebener Seitenspeicherplatz einer nicht verwendeten Seite               | U            |


### <a name="page-zeroing-process"></a>Prozess für das unwiderrufliche Löschen von Seiten
Der Vorgang für die Löschung von Seiten hängt vom Lösch Szenario ab. In der folgenden Tabelle ist für verschiedene Datenbanklöschszenarien erläutert, wann Funktionen zum unwiderruflichen Löschen ausgeführt werden.

| Datenbanklöschszenario | ESE-Vorgang und -Zeitrahmen für unwiderrufliches Löschen von Datenbankdaten |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Das Element läuft basierend auf dem Aufbewahrungszeitraum für gelöschte Elemente ab. | Ein asynchroner Thread schreibt ein binäres Muster über die gelöschten Daten. Diese Aktion wird innerhalb von Millisekunden nach dem Datensatzlöschvorgang ausgeführt. Wenn der Speicherprozess abstürzt, während die asynchrone Null-Arbeit noch aussteht (oder die Bereinigung des Versionsspeichers aufgrund des Wachstums des Versionsspeichers abgebrochen wird), wird die Nullstellung abgeschlossen, wenn die Hintergrunddaten Bank Wartung diesen Abschnitt der Datenbank verarbeitet. |
| Szenario anzeigen: Ablauf von Outlook/Outlook-Elementen in der Webordneransicht (beispielsweise Unterhaltungsansicht) | Unwiderrufliches Löschen von Daten wird ausgeführt, wenn die Hintergrundwartung der Datenbank diesen Abschnitt der Datenbank verarbeitet. |
| Postfach-/Lösch Postfach-Szenario: Quellpostfach gelöscht (Ablauf des gelöschten Postfachs) | Unwiderrufliches Löschen von Daten wird ausgeführt, wenn die Hintergrundwartung der Datenbank diesen Abschnitt der Datenbank verarbeitet. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Postfachdatentypen ohne unwiderrufliches Löschen
Die folgenden Post Fach Datentypen haben keine Rückstellungen für die Nullstellung von Seiten:
- **Postfachdatenbank-Transaktionsprotokolle** – wenn Transaktionsprotokolle im Rahmen normaler Vorgänge gelöscht werden, gibt es keinen Prozess zum aufnullen der Blöcke im Dateisystem, die die gelöschten Protokolldateien gespeichert haben. Wahrscheinlich wird das Dateisystem diesen freien Speicherplatz für neu erstellte Protokolle schnell wieder verwenden, aber es gibt keine Garantie dafür, dass dies geschieht.
- **Inhaltsindex-Katalogdateien** – Exchange Online verwendet die Such Foundation (auch bekannt als fast) für die Such Indizierungsfunktionalität. Der Suchindexkatalog besteht aus mehreren Dutzend Dateien, die auf demselben Volume gespeichert sind wie die Postfachdatenbankdatei. Wenn eine Nachricht aus der Postfachdatenbank hart gelöscht wird, werden die zugeordneten Inhalte im Suchkatalog nicht sofort gelöscht. Das Löschen von Inhalten erfolgt, wenn Search Foundation einen Schatten (oder eine Hauptzusammenführung) vieler kleiner Katalogdateien in einer einzelnen größeren Datei ausführt. Nach Abschluss der Masterzusammenführung werden die kleineren Katalogdateien gelöscht. Es gibt keinen Prozess zum aufnullen der Blöcke, die die gelöschten Katalogdateien gespeichert haben.

## <a name="continuous-replication"></a>Fortlaufende Replikation
Die fortlaufende Replikation (auch als Protokollversand und-Wiedergabe bezeichnet) ist Technologie in Exchange Online, die Kopien jeder Postfachdatenbank erstellt und verwaltet, um hohe Verfügbarkeit, Ausfallsicherheit von Standorten und Notfallwiederherstellung bereitzustellen. Durch die fortlaufende Replikation wird die Exchange Server Unterstützung der Datenbankabsturz Wiederherstellung verwendet, um Technologie bereitzustellen, die eine asynchrone Aktualisierung einer oder mehrerer Kopien einer Postfachdatenbank ausführt. Jeder Postfachserver zeichnet Datenbankaktualisierungen auf, die für eine aktive Datenbank (beispielsweise Benutzer-e-Mail-Aktivität) als Protokolldatensätze in einem sequenziellen Satz von 1 MB Transaktionsprotokolldateien vorgenommen wurden. Diese Dateigruppe wird als Protokolldatenstrom bezeichnet. Bei der fortlaufenden Replikation wird der Protokolldatenstrom auch verwendet, um eine oder mehrere Kopien einer Datenbank asynchron zu aktualisieren. Dies wird erreicht, indem die Protokolle an einen Speicherort mit einer passiven Kopie der aktiven Datenbank übertragen und anschließend in der passiven Datenbankkopie wiedergegeben werden. Wenn alle Protokolle aus der aktiven Datenbank für eine passive Kopie der Datenbank wiedergegeben werden, sind die beiden Datenbanken äquivalent, und es wird durch diesen Prozess jede physische Änderung an einer aktiven Datenbank auf alle passiven Kopien dieser Datenbank repliziert.

Alle Löschungen aus einer Postfachdatenbank, unabhängig davon, ob es sich um ein Postfachelement oder ein gesamtes Postfach handelt, und ob es sich bei einer Soft-Delete-oder einer Hard-Delete-Aktion um eine physische Änderung an der aktiven Datenbank handelt. Das unwiderrufliche Löschen von Seiten beinhaltet auch das vornehmen physischer Änderungen an der aktiven Datenbank. Diese Änderungen werden durch einen Prozess namens "fortlaufende Replikation" in die Protokolldateien geschrieben, und wenn diese Protokolldateien für passive Kopien der Datenbank wiedergegeben werden, werden dieselben physikalischen Änderungen an diesen passiven Datenbanken vorgenommen.