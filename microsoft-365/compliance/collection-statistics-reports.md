---
title: Sammlungsstatistiken und -berichte
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie auf Statistiken und Berichte für Entwurfssammlungen und Sammlungen zugreifen und diese verwenden, die in Advanced eDiscovery einem Überprüfungssatz verpflichtet wurden.
ms.openlocfilehash: 5edbd4a3b7212e027c777ed6ce5284f4e9cf595c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838929"
---
# <a name="collection-statistics-and-reports-in-advanced-ediscovery"></a>Sammlungsstatistiken und -berichte in Advanced eDiscovery

Nachdem Sie eine Entwurfssammlung erstellt haben, können Sie Statistiken zu den abgerufenen Elementen anzeigen, z. B. die Inhaltspositionen, die die meisten Elemente enthalten, die den Suchkriterien entsprechen, und die Anzahl der von der Suchabfrage zurückgegebenen Elemente. Sie können auch eine Vorschau einer Teilmenge der Ergebnisse anzeigen.

Wenn Sie den Satz von Dokumenten identifiziert haben, den Sie weiter untersuchen möchten, können Sie die Suchergebnisse zu einem Prüfsatz hinzufügen, der gesammelt und verarbeiten werden soll.

## <a name="statistics-and-reports-for-draft-collections"></a>Statistiken und Berichte für Entwurfssammlungen

In diesem Abschnitt werden die Statistiken beschrieben, die für Entwurfssammlungen verfügbar sind. Diese Statistiken sind auf der Registerkarte **Suchstatistik** auf der Flyoutseite einer Entwurfssammlung verfügbar.

### <a name="collection-estimates"></a>Sammlungsschätzungen

In diesem Abschnitt wird eine grafische Zusammenfassung der geschätzten Elemente angezeigt, die von der Auflistung zurückgegeben werden. Dies gibt die Anzahl der Elemente an, die den Suchkriterien der Auflistung entsprechen. Diese Informationen geben Ihnen eine Vorstellung von der geschätzten Anzahl von Elementen, die von der Auflistung zurückgegeben werden.

![Sammlungsschätzungen für eine Entwurfssammlung](../media/AeDCollectionEstimates.png)

- **Geschätzte Elemente nach Speicherorten:** Die Gesamtanzahl der geschätzten Elemente, die von der Auflistung zurückgegeben werden. Die bestimmte Anzahl von Elementen, die sich in Postfächern und auf Websites befinden, wird ebenfalls angezeigt.

- **Geschätzte Speicherorte mit Treffern:** Die Gesamtanzahl der Inhaltspositionen, die von der Auflistung zurückgegebene Elemente enthalten. Die spezifische Anzahl von Postfach- und Standortspeicherorten wird ebenfalls angezeigt.

- **Datenvolumen nach Speicherort (in MB):** Die Gesamtgröße aller geschätzten Elemente, die von der Auflistung zurückgegeben werden. Die spezifische Größe von Postfachelementen und Websiteelementen wird ebenfalls angezeigt.

### <a name="condition-report"></a>Bedingungsbericht

In diesem Abschnitt werden Statistiken zur Sammlungssuchabfrage und zur Anzahl der geschätzten Elemente angezeigt, die verschiedenen Teilen der Suchabfrage entsprechen. Sie können diese Statistiken verwenden, um die Anzahl der Elemente zu analysieren, die mit jeder Komponente der Suchabfrage übereinstimmen. Dies kann Ihnen helfen, die Suchkriterien für die Auflistung zu verfeinern und bei Bedarf den Bereich der Auflistung zu einenten.

- **Speicherorttyp**: Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken anwendbar sind. Der Wert von **Exchange** gibt einen Postfachspeicherort an. Ein Wert von **SharePoint** gibt einen Websitespeicherort an.

- **Teil**: Der Teil der Suchabfrage, auf den die Statistiken anwendbar sind. **Primär** gibt die gesamte Suchabfrage an. **Schlüsselwort** gibt an, dass die Statistiken in der Zeile für ein bestimmtes Schlüsselwort verwendet werden. Wenn Sie bei der Suchabfrage in der Auflistung eine Schlüsselwortliste verwenden, sind Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten.

- **Bedingung:** Die tatsächliche Komponente (Schlüsselwort oder Bedingung) der Suchabfrage, die für die Entwurfssammlung ausgeführt wurde, die die in der entsprechenden Zeile angezeigten Statistiken zurückgegeben hat.

- **Speicherorte mit Treffern**: Die Anzahl  der Inhaltsspeicherorte (angegeben durch die Spalte Standorttyp), die Elemente enthalten, die der primären abfrage oder der Schlüsselwortabfrage in der Spalte **Bedingung** entsprechen.

- **Elemente**: Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der Spalte Bedingung aufgeführten **Abfrage** entsprechen. Wie bereits erläutert, wird ein Element nur einmal in dieser Spalte gezählt, wenn es mehrere Instanzen eines gesuchten Schlüsselworts enthält.

- **Size (MB)**: Die Gesamtgröße aller Gefundenen (am angegebenen Inhaltsspeicherort), die der Suchabfrage in der **Spalte Bedingung** entsprechen.

### <a name="top-locations"></a>Top locations

In diesem Abschnitt werden Statistiken zu den spezifischen Inhaltsstandorten mit den meisten von der Auflistung zurückgegebenen Elementen angezeigt.

- Der Name des Standortnamens (die E-Mail-Adresse von Postfächern und die URL für Websites).

- Speicherorttyp (Postfach oder Standort).

- Geschätzte Anzahl von Elementen am Inhaltsspeicherort, die von der Auflistung zurückgegeben werden.

- Die Gesamtgröße der geschätzten Elemente an jedem Inhaltsspeicherort.

## <a name="statistics-and-reports-for-committed-collections"></a>Statistiken und Berichte für verpflichtete Sammlungen

In diesem Abschnitt werden die Statistiken beschrieben, die verfügbar sind, nachdem Sie eine Auflistung zu einem Überprüfungssatz festgelegt haben, einschließlich der tatsächlichen Anzahl von Elementen, die dem Überprüfungssatz hinzugefügt wurden. Diese Statistiken enthalten (zusätzlich zu Denksatzinformationen) verlaufshistorische Informationen zu Inhalten, die einem Fall hinzugefügt wurden.

Nachdem Sie eine Auflistung für einen Überprüfungssatz festgelegt haben, werden die folgenden Registerkarten auf der Flyoutseite der gebundenen Verbindung angezeigt. Jede dieser Registerkarten enthält unterschiedliche Arten von Informationen zur Auflistung.

![Registerkarten auf der Flyoutseite der gebundenen Sammlung](../media/CommittedCollectionFlyoutPage.png)

### <a name="collection-contents"></a>Sammlungsinhalte

Dieser Abschnitt der Registerkarte **Zusammenfassung** enthält Statistiken und weitere Informationen zu den Elementen, die aus den Datenquellen in der Auflistung gesammelt und dem Überprüfungssatz hinzugefügt wurden.

- **Extrahierte Elemente insgesamt**. Die Gesamtanzahl der Elemente, die dem Überprüfungssatz hinzugefügt wurden. Diese Zahl gibt die Summe der übergeordneten und untergeordneten Elemente an, die dem Überprüfungssatz hinzugefügt wurden.

  > [!TIP]
  > Zeigen Sie mit dem Cursor auf die übergeordneten oder untergeordneten Elementleisten, um die Gesamtanzahl der übergeordneten oder untergeordneten Elemente anzeigen zu können.

- **Übergeordnete Elemente**. Die Anzahl der Elemente, die von der Auflistung zurückgegeben wurden, die zum Sammeln der Elemente verwendet wurde, die dem Überprüfungssatz hinzugefügt wurden. Diese Zahl entspricht (und entspricht) der geschätzten Anzahl von Elementen, die im Abschnitt **Auflistungsparameter angezeigt** werden. Die Anzahl der übergeordneten Elemente, die er sammelt, die zum Sammeln der Elemente verwendet wurden, die dem Überprüfungssatz hinzugefügt wurden.
 
   Ein übergeordnetes Element kann mehrere untergeordnete Elemente enthalten. Beispielsweise ist eine E-Mail-Nachricht ein übergeordnetes Element, wenn sie eine angefügte Datei enthält oder über eine Cloudanlage verfügt. In diesem Fall werden die angefügte Datei oder das Ziel der Cloudanlage als untergeordnete Elemente betrachtet. Wenn Sie ein Commit für eine Auflistung erstellen, werden übergeordnete Elemente und alle zugehörigen untergeordneten Elemente dem Überprüfungssatz als einzelne Elemente oder Dateien hinzugefügt.

- **Untergeordnete Elemente**. Die Anzahl der untergeordneten Elemente, die dem Überprüfungssatz hinzugefügt wurden. Untergeordnete Elemente sind Anlagen oder andere Teile eines übergeordneten Elements. Zu den untergeordneten Elementen gehören angefügte Dateien, Cloudanlagen, Bilder und E-Mail-Signaturen. Wenn Sie eine Auflistung für einen Überprüfungssatz festlegen, werden untergeordnete Elemente extrahiert, indiziert und dem Überprüfungssatz als einzelne Dateien hinzugefügt.

- **Eindeutige Elemente**. Die Anzahl der eindeutigen Elemente, die dem Überprüfungssatz hinzugefügt wurden. Eindeutige Elemente sind für den Überprüfungssatz eindeutig. Alle Elemente sind eindeutig, wenn die erste Auflistung einem neuen Überprüfungssatz hinzugefügt wird, da keine vorherigen Elemente im Überprüfungssatz enthalten waren.

- **Identifizierte doppelte Elemente**. Die Anzahl der Elemente aus der Auflistung, die dem Überprüfungssatz nicht hinzugefügt wurden, da das gleiche Element bereits im Überprüfungssatz vorhanden ist. Statistiken zu doppelten Elementen können dazu beitragen, die Unterschiede zwischen der Anzahl der geschätzten Elemente aus einer Entwurfssammlung und der tatsächlichen Anzahl der Elemente zu erklären, die dem Überprüfungssatz hinzugefügt wurden.

### <a name="indexing"></a>Indizierung

Der **Abschnitt Indizierung** auf der Registerkarte **Zusammenfassung** eines festgelegten Überprüfungssatz enthält Indizierungsinformationen zu den Elementen, die dem Überprüfungssatz hinzugefügt wurden.

**Neue indizierte Elemente**. Die Anzahl der Elemente, die neu indiziert wurden, bevor sie dem Überprüfungssatz hinzugefügt wurden. Ein Beispiel für ein neu indiziertes Element sind untergeordnete Elemente, die aus einem übergeordneten Element extrahiert und dann indiziert werden, bevor sie dem Überprüfungssatz hinzugefügt werden. Außerdem werden Elemente, die sich nicht in verwahrten Datenquellen und  nicht verwahrten Inhaltsspeicherorten befinden, die in dem Fall auf der Registerkarte Datenquellen aufgeführt sind, indiziert, bevor sie der Überprüfung hinzugefügt werden. Beispielsweise würden neu indizierte Elemente Elemente enthalten, die von zusätzlichen Speicherorten gesammelt wurden.

**Indizierte Elemente aktualisiert.** Die Anzahl der teilweise indizierten Elemente, die erfolgreich indiziert und dem Überprüfungssatz hinzugefügt wurden. Dies würde Elemente aus Verwahrungsspeicherorten  und nicht verwahrten Inhaltsspeicherorten teilweise indizierte Datenquellenregisterkarten, die erfolgreich indiziert wurden, als die Sammlung für den Überprüfungssatz festgelegt wurde.

**Indizierungsfehler**. Die Anzahl der teilweise indizierten Elemente, die nicht indiziert werden konnten, bevor sie dem Überprüfungssatz hinzugefügt wurden. Für diese Elemente ist möglicherweise eine Fehlerbehebung erforderlich.

### <a name="collection-parameters"></a>Auflistungsparameter

In diesem Abschnitt werden die Sammlungsinformationen angezeigt, die zum Sammeln der Elemente verwendet wurden, die dem Überprüfungssatz hinzugefügt wurden. Auf dieser Registerkarte werden Informationen angezeigt, die den Informationen auf der Registerkarte **Suchstatistik** ähneln. Dieser Abschnitt enthält einen Schnellstart der von der Auflistung verwendeten Suchabfrage, der durchsuchten Inhaltsorte und der geschätzten Sammlungsergebnisse. Wie bereits erläutert, entspricht die Anzahl der geschätzten Elemente in diesem Abschnitt der Anzahl der übergeordneten Elemente, die im Abschnitt **Sammlungsinhalt angezeigt** werden.

### <a name="search-statistics-tab"></a>Registerkarte "Suchstatistik"

Die auf der Registerkarte **Suchstatistik** angezeigten Statistiken sind die gleichen Statistiken wie beim letzten Ausführen einer Entwurfssammlung. Dazu gehören Auflistungsschätzungen, Bedingungsbericht und top-Speicherorte. Diese Informationen werden aus der Entwurfssammlung als historische Referenz beibehalten und können mit der tatsächlichen Auflistung verglichen werden, die für den Überprüfungssatz festgelegt wurde.

## <a name="differences-between-draft-collection-estimates-and-the-actual-committed-collection"></a>Unterschiede zwischen Entwurfssammlungsschätzungen und der tatsächlichen gebundenen Sammlung

Wenn Sie eine Entwurfssammlung ausführen, wird eine Schätzung der Anzahl der Elemente (und  deren Gesamtgröße), die die Sammlungskriterien erfüllen, auf der Registerkarte Zusammenfassung und im Abschnitt Sammlungsschätzungen der Registerkarte Suchstatistik **angezeigt.**  Nachdem Sie eine Entwurfssammlung für einen Überprüfungssatz festgelegt haben, unterscheiden sich die tatsächliche Anzahl der Elemente (und deren Gesamtgröße), die der Überprüfungssatz hinzugefügt hat, häufig von den Schätzungen. In den meisten Fällen werden dem Überprüfungssatz mehr Elemente hinzugefügt, als aus der Entwurfssammlung geschätzt wurden. In der folgenden Liste werden die häufigsten Gründe für diese Unterschiede und Tipps zur Identifizierung beschrieben:

- **Untergeordnete Elemente**. Untergeordnete Elemente, die aus ihren übergeordneten Elementen extrahiert und als einzelne Dateien hinzugefügt werden. Die Anzahl der untergeordneten Elemente kann die Anzahl der Elemente, die tatsächlich dem Überprüfungssatz hinzugefügt werden, erheblich erhöhen. Im Allgemeinen sollte die Anzahl der  übergeordneten Elemente, die im Abschnitt Sammlungsinhalte auf der Registerkarte Zusammenfassung einer gebundenen Auflistung identifiziert werden, der Anzahl der geschätzten Elemente aus der Entwurfssammlung entspricht. 

- **Doppelte Elemente**. Elemente aus der Entwurfssammlung, die dem Überprüfungssatz in einer früheren Auflistung bereits hinzugefügt wurden, werden nicht hinzugefügt. Wie bereits erläutert, wird die Anzahl der doppelten Elemente in der Auflistung im Abschnitt **Sammlungsinhalte** auf der Registerkarte **Zusammenfassung** angezeigt.

- **Sammlungskonfigurationsoptionen**. Wenn Sie eine Entwurfssammlung für einen Überprüfungssatz festlegen, müssen Sie die Option zum Einfügen von Unterhaltungsthreads, Cloudanlagen und Dokumentversionen verwenden. Alle diese Elemente, die dem Überprüfungssatz hinzugefügt werden, sind nicht in den Schätzungen der Entwurfssammlung enthalten. Sie werden nur identifiziert und gesammelt, wenn Sie ein Commit für die Sammlung festlegen. Wenn Sie diese Optionen auswählen, erhöht sich wahrscheinlich die Anzahl der Elemente, die dem Überprüfungssatz hinzugefügt wurden. 

    Beispielsweise sind mehrere Versionen von SharePoint-Dokumenten nicht in der Schätzung für die Entwurfssammlung enthalten. Wenn Sie jedoch beim Exportieren der Suchergebnisse die Option zum Einfügen aller Dokumentversionen auswählen, wird die tatsächliche Anzahl (und Gesamtgröße) der Elemente erhöht, die dem Überprüfungssatz hinzugefügt wurden. 

    Weitere Informationen zu diesen Optionen finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery). 

Dies sind weitere Gründe, warum die geschätzten Ergebnisse aus einer Entwurfssammlung von den tatsächlichen Ergebnissen für die Zugesagten abhingen können.

- **Die Art und Weise, wie Ergebnisse für Entwurfssammlungen geschätzt werden.** Eine Schätzung der suchergebnisse, die von einer Entwurfssammlung zurückgegeben werden, ist nur, dass eine Schätzung (und nicht eine tatsächliche Anzahl) der Elemente, die die Abfragekriterien der Auflistung erfüllen. Zum Kompilieren der Schätzung von E-Mail-Elementen wird eine Liste der Nachrichten-IDs angefordert, die die Suchkriterien erfüllen, aus der Exchange-Datenbank. Wenn Sie die Auflistung jedoch für einen Überprüfungssatz festlegen, wird die Auflistung erneut verwendet, und die tatsächlichen Nachrichten werden aus der Exchange-Datenbank abgerufen. Daher können Unterschiede aufgrund der Art und Weise, wie die geschätzte Anzahl von Elementen und die tatsächliche Anzahl von Elementen bestimmt werden, resulten.

- Änderungen, die zwischen dem Zeitpunkt des Schätzens **und Commits von Entwurfssammlungen auftreten.** Wenn Sie eine Entwurfssammlung für einen Überprüfungssatz festlegen, wird die Suche erneut zum Erfassen der neuesten Elemente im Suchindex, die die Suchkriterien erfüllen, erneut verwendet. Es ist möglich, dass zusätzliche Elemente erstellt, gesendet oder gelöscht wurden, die die Suchkriterien in der Zeit zwischen dem Zeitpunkt der letzten Ausführung der Entwurfssammlung und dem Zeitpunkt erfüllen, zu dem die Entwurfssammlung einem Überprüfungssatz verpflichtet ist. Es ist auch möglich, dass Elemente, die sich im Suchindex befinden, als die Entwurfssammlungsergebnisse geschätzt wurden, nicht mehr dort sind, da sie vor dem Commit der Sammlung aus einer Datenquelle gelöscht wurden. Eine Möglichkeit, dieses Problem zu beheben, besteht in der Angabe eines Datumsbereichs für eine Auflistung. Eine weitere Möglichkeit besteht in der Einbehalten von Inhaltspositionen, damit Elemente beibehalten werden und nicht gelöscht werden können.

- **Nicht indizierte Elemente**. Wenn in der Entwurfssammlung alle Exchange-Postfächer oder alle SharePoint-Websites durchsucht wurden, werden dem Überprüfungssatz nur nicht indizierte Elemente aus Inhaltsspeicherorten hinzugefügt, die Elemente enthalten, die den Sammlungskriterien entsprechen. Anders ausgedrückt: Wenn keine Ergebnisse in einem Postfach oder einer Website gefunden werden, werden nicht indizierte Elemente in diesem Postfach oder Standort nicht zum Überprüfungssatz hinzugefügt. Nicht indizierte Elemente von allen Inhaltsverzeichnissen (auch solche, die keine Elemente enthalten, die mit der Auflistungsabfrage übereinstimmen) werden jedoch in die geschätzten Sammlungsergebnisse einbezogen.

    Wenn die Entwurfssammlung bestimmte Inhaltsspeicherorte enthält (d. h. bestimmte  Postfächer oder Websites, die auf der Seite Zusätzliche Speicherorte im Entwurfssammlungs-Assistenten angegeben sind), werden nicht indizierte Elemente (die von den Sammlungskriterien nicht ausgeschlossen werden) von den in der Suche angegebenen Inhaltsspeicherorten exportiert. In diesem Fall sollten die geschätzte Anzahl nicht indizierter Elemente und die Anzahl der nicht indizierten Elemente, die dem Überprüfungssatz hinzugefügt werden, identisch sein.
