---
title: Übersicht über inaktive Postfächer
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Postfachinhalte für ehemalige Mitarbeiter beibehalten, indem Sie das Postfach in ein inaktives Postfach umdrehen.
ms.openlocfilehash: 6aeb10f1557a991523b60b8e8e85a99fc61f4b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911251"
---
# <a name="overview-of-inactive-mailboxes"></a>Übersicht über inaktive Postfächer

Ihre Organisation muss möglicherweise die E-Mails ehemaliger Mitarbeiter beibehalten, nachdem sie die Organisation verlassen haben. Abhängig von den Aufbewahrungsanforderungen Ihrer Organisation müssen Sie Postfachinhalte möglicherweise einige Monate oder Jahre nach Dem Ende der Beschäftigung beibehalten, oder Sie müssen Postfachinhalte auf unbestimmte Zeit beibehalten. Unabhängig davon, wie lange Sie E-Mails aufbewahren müssen, können Sie inaktive Postfächer erstellen, um die Postfächer ehemaliger Mitarbeiter aufzubewahren.

## <a name="what-are-inactive-mailboxes"></a>Was sind inaktive Postfächer?

Wenn ein Mitarbeiter Ihre Organisation verlässt (oder einen längeren Abwesenheitsurlaub eingeht), können Sie seine Microsoft 365 entfernen. Die Postfachdaten des Mitarbeiters werden 30 Tage lang aufbewahrt, nachdem das Konto entfernt wurde. Während dieses Zeitraums können Sie die Postfachdaten weiterhin wiederherstellen, indem Sie das Konto rückgängig machen. Nach 30 Tagen werden die Daten endgültig entfernt.

Wenn Ihre Organisation jedoch Postfachinhalte für ehemalige Mitarbeiter beibehalten muss, können Sie das Postfach in ein inaktives Postfach verwandeln, indem Sie das Postfach in einem Prozessaufbewahrungsverfahren aktivieren oder eine Microsoft 365-Aufbewahrungsrichtlinie auf das Postfach im Security & Compliance Center anwenden und dann das entsprechende Microsoft 365-Konto entfernen. Der Inhalt eines inaktiven Postfachs wird für die Dauer des Aufbewahrungszeitraums für das Postfach oder den Aufbewahrungszeitraum der Aufbewahrungsrichtlinie aufbewahrt, die auf das Postfach angewendet wurde, bevor das Postfach gelöscht wurde. Sie können das entsprechende Benutzerkonto innerhalb eines Zeitraums von 30 Tagen wiederherstellen. Nach 30 Tagen wird das inaktive Postfach jedoch Microsoft 365 aufbewahrungs- oder aufbewahrungsrichtlinie entfernt.

> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird die Rente von In-Place Holds im Exchange Admin Center angekündigt. Das bedeutet, dass Sie die Aufbewahrungsrichtlinien für rechtsstreitigkeiten und Microsoft 365 verwenden sollten, um ein inaktives Postfach zu erstellen. Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online. Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern. Ab dem 1. Oktober 2020 können Sie die Haltedauer jedoch nicht mehr ändern. Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen. Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten. Weitere Informationen dazu, wann In-Place die Haltezeit eingestellt wird, finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Inaktive Postfächer und Microsoft 365 Aufbewahrungsrichtlinien

Zusätzlich zum Litigation Hold ist die Verwendung des neuen Microsoft 365-Aufbewahrungsrichtlinienfeatures im Microsoft 365 Compliance Center eine weitere Möglichkeit, ein Postfach inaktiv zu machen. Um ein Postfach mithilfe einer Aufbewahrungsrichtlinie als inaktiv festzulegen, müssen Sie wie folgt vorgehen:

- Sie muss so konfiguriert werden, dass Inhalte beibehalten oder beibehalten und dann gelöscht werden. Wenn eine Aufbewahrungsrichtlinie so konfiguriert ist, dass nur Inhalte gelöscht werden, wird ein Postfach, auf das die Richtlinie angewendet wird, beim Löschen des Benutzerkontos nicht inaktiv.

- Die Richtlinie muss auf Exchange-Postfächer oder Skype for Business-Speicherorte angewendet werden (da Skype-bezogene Inhalte im Postfach des Benutzers gespeichert werden).

- Sie kann abfragebasiert sein, sodass nur Elemente aufbewahrt werden, die einer Suchabfrage entsprechen.

Weitere Informationen zu Aufbewahrungsrichtlinien finden Sie [unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)

Wenn Sie eine Aufbewahrungsrichtlinie zum Erstellen eines inaktiven Postfachs verwenden, Microsoft 365 die Aufbewahrungsrichtlinie für das inaktive Postfach weiter verarbeiten. Dies bedeutet Folgendes: Wenn die Aufbewahrungsrichtlinie so konfiguriert ist, das Inhalte aufbewahrt und anschließend gelöscht werden, werden Elemente in den Ordner „Wiederherstellbare Elemente" verschoben, wenn die Aufbewahrungsdauer abläuft, und schließlich aus dem inaktiven Postfach gelöscht. Wenn die Aufbewahrungsrichtlinie nicht für gelöschte Elemente konfiguriert ist, werden Elemente, die vom Benutzer nicht endgültig gelöscht wurden (bevor das Postfach inaktiv gemacht wurde), nicht in den Ordner "Wiederherstellbare Elemente" verschoben und auf unbestimmte Zeit aufbewahrt, nachdem das Postfach inaktiv wird.

Sie können erwägen, eine Microsoft 365 aufbewahrungsrichtlinie speziell für inaktive Postfächer zu erstellen. Hier sind einige Gründe dafür und Punkte, die Sie beachten sollten.

- Sie können die Aufbewahrungsrichtlinie so konfigurieren, dass Postfachinhalte nur so lange aufbewahrt werden, wie erforderlich ist, um die Anforderungen Ihrer Organisation in Bezug auf ehemalige Mitarbeiter zu erfüllen.

- Es ist eine gute Möglichkeit, inaktive Postfächer zu identifizieren, da die Aufbewahrungsrichtlinie nur auf inaktive Postfächer angewendet wird.

- Sie können die Aufbewahrungsrichtlinie, die inaktiven Postfächern in Ihrer Organisation zugewiesen ist, schnell identifizieren. Dies erleichtert das Ändern der Aufbewahrungseinstellungen (oder Löscheinstellungen) bei Bedarf. Außerdem wird es einfacher, ein inaktives Postfach dauerhaft zu löschen, da Sie es mithilfe des Security & Compliance Center aus der Richtlinie entfernen können. Andernfalls müssen Sie Exchange Online PowerShell verwenden, um ein Prozessaufbewahrungsverfahren aus einem inaktiven Postfach zu entfernen oder security & Compliance Center PowerShell zu verwenden, um ein inaktives Postfach aus einer organisationsweiten aufbewahrungsrichtlinie Microsoft 365 auszuschließen.

- Wenn Sie eine Microsoft 365 für inaktive Postfächer erstellen, können Sie der Richtlinie maximal 1.000 Postfächer hinzufügen. Wenn Sie eine große Organisation sind, müssen Sie möglicherweise mehrere Microsoft 365 für inaktive Postfächer erstellen.

> [!CAUTION]
> Wenn Sie eine Aufbewahrungsrichtlinie verwenden, um ein Postfach inaktiv zu machen, ändern oder entfernen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) für das Postfach nicht, bevor Sie das entsprechende Benutzerkonto löschen. Ändern Sie außerdem nicht die primäre SMTP-Adresse (die vom UPN abgeleitet ist), oder entfernen Sie diese E-Mail-Adresse nicht aus der Liste der sekundären SMTP-Adressen, die dem Postfach zugeordnet sind, bevor Sie das Postfach inaktiv machen. Wenn Sie den UPN oder die E-Mail-Adressen ändern (die dem Postfach zum Zeitpunkt der Anwendung der Aufbewahrungsrichtlinie zugewiesen wurden) und dann das Benutzerkonto löschen, um das Postfach inaktiv zu machen, können Sie das inaktive Postfach nicht löschen, wenn Sie es nicht mehr beibehalten müssen. Das liegt daran, dass Sie das inaktive Postfach nicht mithilfe eines UPNs oder einer E-Mail-Adresse (zum Identifizieren des inaktiven Postfachs) aus der Aufbewahrungsrichtlinie entfernen können, die sich von denen unterscheiden, die bei der anfänglichen Anwendung der Aufbewahrungsrichtlinie auf das Postfach vorhanden waren. Weitere Informationen zum Löschen inaktiver Postfächer finden Sie unter [Löschen eines inaktiven Postfachs in Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Inaktive Postfächer und eDiscovery-Fallspeicher

Wenn ein Archiv, das einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, für ein Postfach platziert wird und dann das Postfach oder das Konto des Benutzers gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Die Verwendung von eDiscovery-Fallspeichern zum Festlegen eines Postfachs als inaktiv wird jedoch nicht empfohlen. Grund hierfür ist, dass eDiscovery-Fälle für bestimmte zeitgebundene Fälle im Zusammenhang mit einem rechtlichen Problem vorgesehen sind. An einem bestimmten Punkt wird ein Rechtsfall wahrscheinlich enden, die dem Fall zugeordneten Speicherverfahren werden entfernt, und der eDiscovery-Fall wird geschlossen. Wenn ein für ein inaktives Postfach festgelegtes Speicherverfahren einem eDiscovery-Fall zugeordnet ist und das Speicherverfahren anschließend aufgehoben oder der eDiscovery-Fall geschlossen (oder gelöscht) wird, wird das inaktive Postfach endgültig gelöscht. Außerdem können Sie keinen zeitbasierten eDiscovery-Halteschutz erstellen. Das bedeutet, dass Inhalte in einem inaktiven Postfach für immer aufbewahrt werden oder bis der Halteraum entfernt und das inaktive Postfach gelöscht wird. Aus diesem Grund wird die Verwendung eines Aufbewahrungszeitraums oder einer Aufbewahrungsrichtlinie für inaktive Postfächer empfohlen.

Weitere Informationen zu eDiscovery-Fällen und -Haltefällen finden Sie unter [eDiscovery-Fälle](./get-started-core-ediscovery.md).

## <a name="inactive-mailboxes-and-labels"></a>Inaktive Postfächer und Bezeichnungen

Aufbewahrungsbezeichnungen helfen Ihnen, E-Mail-Daten in Ihrer Organisation für die Steuerung zu klassifizieren und Aufbewahrungsregeln basierend auf dieser Klassifizierung zu erzwingen. Eine Aufbewahrungsbezeichnung kann entweder manuell von Benutzern oder automatisch von Administratoren auf ein E-Mail-Element angewendet werden, und einem E-Mail-Element kann nur eine bezeichnung zugewiesen werden. Wenn einem einzelnen E-Mail-Element im Postfach eines Benutzers eine Bezeichnung zugewiesen ist (und es so konfiguriert ist, dass das Element beibehalten oder beibehalten und dann gelöscht wird), und das Postfach oder das Benutzerkonto gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Ähnlich wie bei eDiscovery-Fallspeichern wird die Verwendung von Aufbewahrungsbezeichnungen nicht empfohlen, um ein Postfach inaktiv zu machen. Stattdessen wird empfohlen, ein Aufbewahrungsverfahren oder eine Aufbewahrungsrichtlinie zu verwenden. Bei Aufbewahrungsbezeichnungen ist ihnen möglicherweise nicht bewusst, dass eine Aufbewahrungsbezeichnung auf ein E-Mail-Element angewendet wurde, und stellen dann versehentlich ein inaktives Postfach ein, wenn Sie das Konto des Benutzers löschen.

Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen finden Sie unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen [in Office 365](retention.md).

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Inaktive Postfächer und automatisch erweiternde Archive

Ein inaktives Postfach, das mit einem automatisch erweiternden Archiv konfiguriert ist, kann nicht wiederhergestellt oder wiederhergestellt werden. In Situationen, in denen daten aus einem inaktiven Postfach mit einem automatisch erweiternden Archiv wiederhergestellt werden müssen, wird empfohlen, das Inhaltssuchtool zu verwenden, um die Daten aus dem Postfach zu exportieren und dann in ein anderes Postfach zu importieren. Schrittweise Anweisungen zum Durchsuchen eines inaktiven Postfachs und zum Exportieren der Suchergebnisse finden Sie unter:

- [Inhaltssuche](content-search.md)

- [Exportieren von Inhaltssuchergebnissen](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Inaktive Postfächer und Exchange MRM-Aufbewahrungsrichtlinien

Wenn eine Exchange-Aufbewahrungsrichtlinie (messaging records management, mrm, feature in Exchange Online) auf das Postfach angewendet wurde, als es inaktiv  gemacht wurde, werden alle Löschrichtlinien (bei denen es sich um Aufbewahrungstags handelt, die mit einer Aufbewahrungsaktion löschen konfiguriert sind) weiterhin für das inaktive Postfach verarbeitet. Mit einer Löschrichtlinie markierte Elemente werden demnach in den Ordner „Wiederherstellbare Elemente" verschoben, wenn der Aufbewahrungszeitraum abläuft. Diese Elemente werden aus dem inaktiven Postfach gelöscht, wenn die Aufbewahrungsdauer abläuft. Wenn keine Aufbewahrungsdauer für das inaktive Postfach angegeben wurde, werden Elemente im Ordner „Wiederherstellbare Elemente" unbegrenzt aufbewahrt.

Umgekehrt werden einem inaktiven Postfach zugewiesene Archivrichtlinien (mit der Aufbewahrungsaktion **MoveToArchive** konfigurierte Aufbewahrungstags) ignoriert, die in der Aufbewahrungsrichtlinie enthalten sind. Elemente in einem inaktiven Postfach, die mit einer Archivrichtlinie markiert sind, verbleiben demnach im primären Postfach, wenn die Aufbewahrungsdauer abläuft. Sie werden nicht in das Archivpostfach oder in den Ordner „Wiederherstellbare Elemente" im Archivpostfach verschoben. Sie werden unbegrenzt aufbewahrt.

## <a name="creating-an-inactive-mailbox"></a>Erstellen eines inaktiven Postfachs

Damit ein Postfach inaktiv wird, muss ihm eine Exchange Online Plan 2-Lizenz (oder eine Exchange Online Plan 1-Lizenz mit einer Exchange Online-Archivierung-Add-On-Lizenz) zugewiesen werden, damit eine Aufbewahrungsrichtlinie für Rechtsstreitigkeiten oder Microsoft 365 auf das Postfach angewendet werden kann, bevor es gelöscht wird. Nachdem das Benutzerkonto gelöscht wurde, Exchange Online dem Benutzerkonto zugeordnete Lizenz einem neuen Benutzer zugewiesen werden.

Die folgende Tabelle enthält eine Übersicht über das Verfahren, mit dem ein inaktives Postfach in verschiedenen Aufbewahrungsszenarios erstellt wird. Weitere Informationen finden Sie unter [Verwalten inaktiver Postfächer](create-and-manage-inactive-mailboxes.md).

****

|An...|Vorgehensweise|Ergebnis|
|---|---|---|
|Aufbewahren des Postfachinhalts für unbegrenzte Zeit, nachdem ein Mitarbeiter die Organisation verlassen hat|Setzen Sie das Postfach in das Aufbewahrungsverfahren für Rechtsstreitigkeiten ein, oder wenden Sie Microsoft 365 Aufbewahrungsrichtlinie (die für die Aufbewahrung von Inhalten konfiguriert ist) auf das Postfach an. <br/> Geben Sie keine Aufbewahrungsdauer für das Aufbewahrungsverfahren an, oder konfigurieren Sie die Aufbewahrungsrichtlinie nicht zum Löschen von Elementen. Alternativ können Sie eine Aufbewahrungsrichtlinie verwenden, die Elemente für immer behält. <br/> Entfernen Sie das Konto Microsoft 365 Benutzers.|Alle Inhalte im inaktiven Postfach, einschließlich Elemente im Ordner "Wiederherstellbare Elemente", werden auf unbestimmte Zeit aufbewahrt.|
|Aufbewahren des Postfachinhalts für einen bestimmten Zeitraum nach dem Ausscheiden des Mitarbeiters und anschließendes Löschen|Wenden Sie Microsoft 365 Aufbewahrungsrichtlinie auf das Postfach an. <br/> Konfigurieren Sie die Aufbewahrungsrichtlinie so, dass Elemente beibehalten und gelöscht werden, wenn der Aufbewahrungszeitraum abläuft. <br/> Entfernen Sie das Konto Microsoft 365 Benutzers.|Wenn der Aufbewahrungszeitraum für ein Postfachelement abläuft, wird das Element in den Ordner "Wiederherstellbare Elemente" verschoben und dann endgültig aus dem inaktiven Postfach gelöscht (gelöscht), wenn der Aufbewahrungszeitraum für gelöschte Elemente (für Exchange Postfächer) abläuft. Der Aufbewahrungszeitraum der aufbewahrungsrichtlinie Microsoft 365 kann basierend auf dem ursprünglichen Datum konfiguriert werden, an dem ein Postfachelement empfangen oder erstellt wurde oder wann es zuletzt geändert wurde.|
|

**HINWEIS:** Wenn bereits ein Aufbewahrungsverfahren für ein Postfach aktiviert ist oder eine Microsoft 365-Aufbewahrungsrichtlinie (die so konfiguriert ist, dass Inhalte beibehalten oder beibehalten und dann gelöscht werden) bereits auf das Postfach angewendet wird, müssen Sie nur das entsprechende Benutzerkonto löschen, um ein inaktives Postfach zu erstellen.

## <a name="managing-inactive-mailboxes"></a>Verwalten inaktiver Postfächer

Nachdem Sie ein Postfach als inaktiv festgelegt haben, können Sie verschiedene Verwaltungsaufgaben für inaktive Postfächer ausführen.

- **Ändern sie die Haltedauer für ein inaktives Postfach.** Nachdem ein Postfach inaktiv gemacht wurde, können Sie die Aufbewahrungsdauer des Rechtsstreitigkeitens oder Microsoft 365 aufbewahrungsrichtlinie ändern, die auf das inaktive Postfach angewendet wird. Schrittweise Verfahren finden Sie unter Ändern der [Haltedauer für ein inaktives Postfach](change-the-hold-duration-for-an-inactive-mailbox.md).

  > [!NOTE]
  > Sie können keine anderen Aufbewahrungsrichtlinien auf ein inaktives Postfach anwenden. Sie können nur die Aufbewahrungsdauer einer vorhandenen Aufbewahrungsrichtlinie ändern, die auf das inaktive Postfach angewendet wird.

- **Stellen Sie ein inaktives Postfach wiederher.** Wenn ein ehemaliger Mitarbeiter (oder ein Mitarbeiter in Abwesenheit) in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, um die Aufgaben des ehemaligen Mitarbeiters zu übernehmen, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach konvertiert, der Inhalt und die Ordnerstruktur des inaktiven Postfachs werden beibehalten, und das Postfach ist mit einem neuen Benutzerkonto verknüpft. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schrittweise Verfahren und Informationen dazu, was beim Wiederherstellen eines inaktiven Postfachs geschieht, finden Sie unter [Recover an inactive mailbox](recover-an-inactive-mailbox.md).

  > [!NOTE]
  > Wenn Sie ein inaktives Postfach wiederherstellen, das einer Aufbewahrungsrichtlinie mit Erhaltungssperre (als gesperrte Aufbewahrungsrichtlinie bezeichnet) zugewiesen *wurde,* wird das wiederhergestellte Postfach derselben gesperrten Aufbewahrungsrichtlinie zugewiesen. Wenn Sie ein inaktives Postfach wiederherstellen, das einer Aufbewahrungsrichtlinie ohne Erhaltungssperre zugewiesen wurde, wird das wiederhergestellte Postfach aus der entsperrten Aufbewahrungsrichtlinie entfernt. Für das wiederhergestellte Postfach ist jedoch das Aufbewahrungsverfahren aktiviert, um das Löschen von Postfachinhalten basierend auf organisationsweiten Aufbewahrungsrichtlinien zu verhindern, die Inhalte löschen, die älter als ein bestimmtes Alter sind.

- **Wiederherstellen eines inaktiven Postfachs.** Wenn ein anderer Mitarbeiter die Aufgaben eines ehemaligen Mitarbeiters übernimmt oder wenn eine andere Person Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Wenn Sie ein inaktives Postfach wiederherstellen, werden die Inhalte in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Das inaktive Postfach kann weiterhin mit eDiscovery-Tools durchsucht werden, seine Inhalte können in einem anderen Postfach wiederhergestellt und später wiederhergestellt oder gelöscht werden. Schrittweise Verfahren finden Sie unter [Restore an inactive mailbox](restore-an-inactive-mailbox.md).

- **Löschen eines inaktiven Postfachs.** Wenn Sie den Inhalt eines inaktiven Postfachs nicht mehr beibehalten müssen, können Sie es dauerhaft löschen, indem Sie alle Aufbewahrungs- oder Microsoft 365 auf das inaktive Postfach angewendeten Aufbewahrungsrichtlinien entfernen. Wenn ein Postfach vor mehr als 30 Tagen inaktiv gemacht wurde, wird es nach dem Entfernen des Haltezustands für das dauerhafte Löschen markiert. Wenn das Postfach innerhalb der letzten 30 Tage inaktiv gemacht wurde, können Sie es nach dem Entfernen der Aufbewahrungs- oder Aufbewahrungsrichtlinie wieder aktiv machen. Schrittweise Verfahren finden Sie unter [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md).