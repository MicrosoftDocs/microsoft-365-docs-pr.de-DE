---
title: Erstellen einer Entwurfssammlung
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Eine Entwurfssammlung ist eine eDiscovery-Suche nach verwahrten und nicht verwahrbaren Datenquellen in einem Advanced eDiscovery-Fall, die eine Suchschätzung zurückgibt, die der Suchabfrage der Auflistung entspricht. Sie können Suchstatistiken überprüfen, eine Vorschau eines Samplings von Elementen anzeigen und die Auflistung überarbeiten und erneut ausführen, bevor Sie die Ergebnisse für einen Überprüfungssatz festlegen.
ms.openlocfilehash: 18f018a5e00f355c3f320a963135e76ecc51f086
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838896"
---
# <a name="create-a-draft-collection-in-advanced-ediscovery"></a>Erstellen einer Entwurfssammlung in Advanced eDiscovery

Nachdem Sie Verwahrer und andere Datenquellen identifiziert haben, die nicht für den Fall zuständig sind, können Sie eine Reihe relevanter Dokumente identifizieren und suchen. Verwenden Sie dazu das Tool Sammlungen, um Datenquellen nach relevanten Inhalten zu durchsuchen. Dazu erstellen Sie eine Auflistung, die bestimmte Datenquellen nach Inhalten durchsucht, die Ihren Suchkriterien entsprechen. Sie haben die Möglichkeit, eine Entwurfssammlung *zu* erstellen, bei der es sich um eine Schätzung der gefundenen Elemente handelt, oder Sie können eine Auflistung erstellen, die die Elemente automatisch zu einem Überprüfungssatz hinzufügt. Wenn Sie eine Entwurfssammlung erstellen, können Sie Informationen zu den geschätzten Ergebnissen anzeigen, die mit der Suchabfrage übereinstimmen, z. B. die Gesamtanzahl und Größe der gefundenen Elemente, die verschiedenen Datenquellen, in denen sie gefunden wurden, und Statistiken zur Suchabfrage. Sie können auch eine Vorschau eines Beispiels von Elementen anzeigen, die von der Auflistung zurückgegeben wurden. Mithilfe dieser Statistiken können Sie die Suchabfrage ändern und die Entwurfssammlung erneut ausführen, um die Ergebnisse zu einengt. Sobald Sie mit den Sammlungsergebnissen zufrieden sind, können Sie die Auflistung auf einen Überprüfungssatz festlegen. Wenn Sie ein Commit für eine Entwurfssammlung durchführen, werden die von der Auflistung zurückgegebenen Elemente einem Überprüfungssatz zur Überprüfung, Analyse und zum Exportieren hinzugefügt.

## <a name="before-you-create-a-draft-collection"></a>Vor dem Erstellen einer Entwurfssammlung

- Fügen Sie dem Fall Custodians und nicht verwahrte Datenquellen hinzu, bevor Sie eine Entwurfssammlung erstellen. Dies ist erforderlich, damit Sie beim Erstellen einer Entwurfssammlung die Datenquellen auswählen können. Weitere Informationen finden Sie hier:

  - [Hinzufügen von Verwaltungsberechtigten zu einem Fall](add-custodians-to-case.md)

  - [Hinzufügen von nicht-verwahrten Datenquellen zu einem Fall](non-custodial-data-sources.md)

- Sie können zusätzliche Datenquellen (die dem Fall nicht als Verwahrungs- oder nicht verwahrstellende Speicherorte hinzugefügt wurden) in einer Entwurfssammlung nach Inhalten durchsuchen, die für den Fall relevant sein können. Zu diesen Datenquellen können Postfächer, SharePoint-Websites und Teams gehören. Wenn diese Situation für Ihren Fall gilt, kompilieren Sie eine Liste dieser Datenquellen, damit Sie sie der Auflistung hinzufügen können.

## <a name="create-a-draft-collection"></a>Erstellen einer Entwurfssammlung

1. Öffnen Sie im Microsoft 365 Compliance Center den Fall Advanced eDiscovery, und wählen Sie dann die Registerkarte **Sammlungen** aus.

2. Wählen Sie **auf der** Seite Sammlungen die Option **Neue Auflistung**  >  **Standard-Auflistung aus.**

3. Geben Sie einen Namen (erforderlich) und eine Beschreibung (optional) für die Auflistung ein. Nachdem die Auflistung erstellt wurde, können Sie den Namen nicht ändern, aber Sie können die Beschreibung ändern.

4. Gehen Sie **auf der** Seite "Verwahrerdatenquellen" wie folgt vor, um die Verwahrdatenquellen zu identifizieren, aus der Inhalte gesammelt werden sollen:

   - Klicken **Sie auf Custodians auswählen,** um bestimmte Verwahrer zu durchsuchen, die dem Fall hinzugefügt wurden. Wenn Sie diese Option verwenden, wird eine Liste der Fallverwahrer angezeigt. Wählen Sie einen oder mehrere Verwahrer aus. Nachdem Sie die Verwahrer ausgewählt und hinzugefügt haben, können Sie auch die spezifischen Datenquellen auswählen, um nach jedem Custodian zu suchen. Diese datenquellen, die angezeigt werden, wurden angegeben, als der Verwahrer dem Fall hinzugefügt wurde.

   - Klicken Sie **auf die Umschalte** Alle auswählen, um alle Custodians zu durchsuchen, die dem Fall hinzugefügt wurden. Wenn Sie diese Option auswählen, werden alle Datenquellen für alle Verwahrer durchsucht.

5. Gehen Sie **auf** der Seite Nicht verwahrte Datenquellen wie folgt vor, um die nicht verwahrten Datenquellen zum Sammeln von Inhalten zu identifizieren:

   - Klicken **Sie auf Nicht verwahrungsfreie Datenquellen** auswählen, um bestimmte datenquellen auszuwählen, die dem Fall hinzugefügt wurden. Wenn Sie diese Option verwenden, wird eine Liste der Datenquellen angezeigt. Wählen Sie eine oder mehrere dieser Datenquellen aus.

   - Klicken Sie **auf die** Umschalte Alle auswählen, um alle nicht verwahrten Datenquellen auszuwählen, die dem Fall hinzugefügt wurden.

6. Auf der **Seite Zusätzliche Datenquellen** können Sie andere Postfächer und Websites auswählen, die als Teil der Auflistung durchsucht werden. Diese Arten von Datenquellen wurden in dem Fall nicht als Speicherorte für Verwahrungs- oder nicht verwahrstellende Daten hinzugefügt. Sie haben auch zwei Optionen beim Durchsuchen zusätzlicher Datenquellen:

   - Um alle Inhaltsspeicherorte nach einem bestimmten Dienst (Exchange-Postfächer, SharePoint- und #A0 oder öffentliche #A1) zu durchsuchen, klicken Sie in der Spalte **Status** auf den entsprechenden Umschalter **Alle** auswählen. Mit dieser Option werden alle Inhaltsstandorte im ausgewählten Dienst durchsucht.

   - Klicken Sie zum Durchsuchen eines bestimmten  Inhaltsspeicherorts für einen Dienst in der Spalte **Status** auf den entsprechenden  Umschalter Alle auswählen, und klicken Sie dann auf **Benutzer, Gruppen** oder Teams (für #A0) oder Auf Websites auswählen für (SharePoint- und OneDrive-Websites), um bestimmte Inhaltsspeicherorte zu durchsuchen.

7. Auf der **Seite** Bedingungen können Sie die Suchabfrage erstellen, die zum Sammeln von Elementen aus den Datenquellen verwendet wird, die Sie auf den vorherigen Assistentenseiten identifiziert haben. Sie können nach Schlüsselwörtern, Property:Value-Paaren oder einer Stichwortliste suchen. Sie können auch verschiedene Suchbedingungen hinzufügen, um den Bereich der Auflistung zu einenten. Weitere Informationen finden Sie unter [Erstellen von Suchabfragen für Sammlungen](building-search-queries.md).

8. Wählen Sie auf der Seite Als Entwurf speichern oder **hinzufügen,** um den Satz zu überprüfen die Option **Sammlung als Entwurf speichern aus.**

   > [!NOTE]
   > Mit der anderen Option auf dieser Seite können Sie Elemente sammeln und direkt zu einem Überprüfungssatz hinzufügen. Anstatt eine Entwurfssammlung zu erstellen, mit der Sie Statistiken für die Sammlungsergebnisse überprüfen und eine Vorschau anzeigen können, überspringt diese Option diesen Prozess und fügt die Auflistung automatisch einem Überprüfungssatz hinzu. Wenn Sie die zweite Option zum Hinzufügen der Sammlung zu einem Überprüfungssatz auswählen, müssen Sie zusätzliche Einstellungen konfigurieren, z. B. das Sammeln ganzer Chat-Unterhaltungsthreads in Microsoft Teams und Yammer und das Sammeln von Cloudanlagen (auch als moderne Anlagen *bezeichnet).* Weitere Informationen zu diesen Einstellungen finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md).

9. Auf der **Seite Ihre Sammlung überprüfen** können Sie die Sammlungseinstellungen überprüfen und aktualisieren, die Sie auf den vorherigen Seiten konfiguriert haben.

   - **Registerkarte** Zusammenfassung: Überprüfen und ändern Sie den Namen und die Beschreibung der Auflistung, die Sammlungssuchkriterien, zusätzliche Datenspeicherorte und den Sammlungstyp.

   - **Registerkarte Quellen:** Überprüfen und ändern Sie die Datenquellen für verwahrungs- und nicht verwahrstellende Daten für die Sammlung.

10. Klicken Sie **auf Übermitteln,** um die Entwurfssammlung zu erstellen. Es wird eine Seite angezeigt, die bestätigt, dass die Auflistung erstellt wurde.

## <a name="what-happens-after-you-create-a-draft-collection"></a>Was geschieht, nachdem Sie eine Entwurfssammlung erstellt haben

Nachdem Sie eine Entwurfssammlung erstellt  haben, wird sie in dem Fall auf der Seite Sammlungen aufgeführt, und der Status zeigt, dass sie ausgeführt wird. Ein Auftrag mit **dem Namen Vorbereiten der Suchvorschau** und Schätzungen wird ebenfalls erstellt und in diesem Fall auf der Seite Aufträge angezeigt. 

Während des Entwurfssammlungsprozesses führt Advanced eDiscovery eine Suchschätzung mithilfe der Suchkriterien und Datenquellen aus, die Sie in der Auflistung angegeben haben. Advanced eDiscovery bereitet außerdem ein Sampling von Elementen vor, die Sie in der Vorschau anzeigen können. Wenn die Auflistung abgeschlossen ist, werden die folgenden Spalten und entsprechenden Werte auf der **Seite Sammlung** aktualisiert:

![Statusstatus für eine Entwurfssammlung](../media/DraftCollectionStatus.png)

- **Status**: Gibt den Status und den Typ der Auflistung an. Der Wert **Estimated** gibt an, dass eine Entwurfssammlung abgeschlossen ist. Dieser Wert gibt auch an, dass es sich bei der Auflistung um eine Entwurfssammlung handelt und dass sie keinem Überprüfungssatz hinzugefügt wurde. Der Wert **Committed** in der **Spalte Status** gibt an, dass die Auflistung einem Überprüfungssatz hinzugefügt wurde.

- **Schätzstatus**: Gibt den Status der geschätzten Suchergebnisse an und gibt an, ob die Suchschätzungen und Statistiken zur Überprüfung bereit sind. Der Wert **Successful** gibt an, dass die Ergebnisse der Entwurfssammlung zur Überprüfung bereit sind. Nachdem Sie eine Entwurfssammlung zum ersten Mal übermittelt haben, wird der Wert **In** Bearbeitung angezeigt, um anzugeben, dass die Auflistung noch ausgeführt wird.

- **Vorschaustatus**: Gibt den Status der Beispielelemente an, die Sie in der Vorschau anzeigen können. Der Wert **Erfolgreich** gibt an, dass die Elemente für die Vorschau bereit sind. Nachdem Sie eine Entwurfssammlung zum ersten Mal übermittelt haben, wird der Wert **In** Bearbeitung angezeigt, um anzugeben, dass die Auflistung noch ausgeführt wird.

## <a name="next-steps-after-a-draft-collection-is-complete"></a>Nächste Schritte nach Abschluss einer Entwurfssammlung

Nachdem die Entwurfssammlung erfolgreich abgeschlossen wurde, können Sie verschiedene Aufgaben ausführen. Um die meisten dieser Aufgaben auszuführen, wechseln Sie einfach zur **Registerkarte** Sammlungen, und klicken Sie auf den Namen der Entwurfssammlung, um die Flyoutseite anzeigen zu können.

![Flyoutseite für eine Entwurfssammlung](../media/DraftCollectionFlyoutPage.png)

Hier ist eine Liste der Dinge, die Sie auf der Flyoutseite der Auflistung tun können:

- Wählen Sie **die Registerkarte Zusammenfassung** aus, um Zusammenfassungsinformationen zur Auflistung und die von der Auflistung zurückgegebenen geschätzten Suchergebnisse anzeigen zu können. Dies umfasst die Gesamtanzahl der Elemente und die Größe der geschätzten Suchergebnisse, die Anzahl der Postfächer und Websites, die Suchergebnisse enthalten, und die Suchbedingungen (sofern verwendet), die zum Bereich der Auflistung verwendet werden.

- Wählen Sie **die Registerkarte** Datenquellen aus, um eine Liste der Custodians und nicht verwahrten Datenquellen zu sehen, die in der Sammlung durchsucht wurden. Alle weiteren Inhaltsstandorte, die durchsucht wurden, werden unter **Speicherorte** auf der Registerkarte **Zusammenfassung** aufgeführt.

- Wählen Sie die **Registerkarte Suchstatistik** aus, um Statistiken zur Auflistung anzeigen zu können. Dies umfasst die Gesamtanzahl und Größe der Elemente, die in jedem Dienst gefunden werden (z. B. Exchange-Postfächer oder SharePoint-Websites) und einen Bedingungsbericht, der Statistiken über die Anzahl der Elemente anzeigt, die von verschiedenen Komponenten der von der Auflistung verwendeten Suchabfrage zurückgegeben werden. Weitere Informationen finden Sie unter [Sammlungsstatistiken und -berichte](collection-statistics-reports.md).

- Klicken **Sie auf Beispiel überprüfen** (unten auf der Flyoutseite), um eine Vorschau eines Beispiels der von der Auflistung zurückgegebenen Elemente anzuzeigen.

- Commit der Entwurfssammlung für einen Überprüfungssatz (durch Klicken auf **Actions**  >  **Edit collection**). Dies bedeutet, dass Sie die Auflistung erneut ausführen (mithilfe der aktuellen Einstellungen) und die von der Auflistung zurückgegebenen Elemente zu einem Überprüfungssatz hinzufügen. Wie bereits erläutert, können Sie auch zusätzliche Einstellungen (z. B. Unterhaltungsthreading und cloudbasierte Anlagen) konfigurieren, wenn Sie die Auflistung einem Überprüfungssatz hinzufügen. Weitere Informationen und schrittweise Anweisungen finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md).

## <a name="manage-a-draft-collection"></a>Verwalten einer Entwurfssammlung

Sie können die Optionen im **Menü** Aktionen auf der Flyoutseite einer Entwurfssammlung verwenden, um verschiedene Verwaltungsaufgaben auszuführen.

![Optionen im Menü Aktionen für die Entwurfssammlung](../media/DraftCollectionActionsMenu.png)

Im Folgenden finden Sie Beschreibungen der Verwaltungsoptionen.

- **Edit-Auflistung**: Ändern Sie die Einstellungen der Entwurfssammlung. Nachdem Sie Änderungen vorgenommen haben, können Sie die Auflistung erneut ausführen und die Suchschätzungen und Statistiken aktualisieren. Wie bereits erläutert, verwenden Sie diese Option, um eine Entwurfssammlung für einen Überprüfungssatz zu commiten.  

- **Delete-Auflistung**: Löschen einer Entwurfssammlung. Beachten Sie, dass eine Entwurfssammlung nach dem Festlegen eines Engagements für einen Überprüfungssatz nicht gelöscht werden kann.

- **Aktualisierungsschätzungen**: Führen Sie die Abfrage (für die Datenquellen) erneut aus, die in der Entwurfssammlung angegeben ist, um die Suchschätzungen und Statistiken zu aktualisieren.

- **Als Bericht exportieren:** Exportiert Informationen zur Entwurfssammlung in eine CSV-Datei, die Sie auf Ihren lokalen Computer herunterladen können. Der Exportbericht enthält die folgenden Informationen:

  - Die Identität jedes Inhaltsspeicherorts, der Elemente enthält, die der Suchabfrage in der Entwurfssammlung entsprechen. Bei diesen Speicherorten handelt es sich in der Regel um Postfächer oder Websites.
  
  - Die Gesamtanzahl der Elemente an jedem Inhaltsspeicherort.
  
  - Die Gesamtgröße (in Byte) der Elemente an jedem Inhaltsspeicherort.

  - Der Dienst (z. B. Exchange oder SharePoint), in dem sich der Inhaltsspeicherort befindet.

- **Copy-Auflistung**: Erstellen Sie eine neue Entwurfssammlung, indem Sie die Einstellungen aus einer vorhandenen Auflistung kopieren. Sie müssen einen anderen Namen für die neue Auflistung verwenden. Sie haben auch die Möglichkeit, die Einstellungen zu ändern, bevor Sie die neue Auflistung übermitteln. Nachdem Sie sie übermittelt haben, wird die Suchabfrage ausgeführt, und es werden neue Schätzungen und Statistiken generiert. Die ist eine gute Möglichkeit, um schnell zusätzliche Entwurfssammlungen zu erstellen und ausgewählte Einstellungen bei Bedarf zu ändern, während weiterhin Informationen in der ursprünglichen Auflistung beibehalten werden. Auf diese Weise können Sie auch die Ergebnisse von zwei ähnlichen Auflistungen problemlos vergleichen.

> [!NOTE]
> Nachdem eine Entwurfssammlung für einen Überprüfungssatz festgelegt wurde, können Sie die Auflistung nur kopieren und einen Bericht exportieren.
