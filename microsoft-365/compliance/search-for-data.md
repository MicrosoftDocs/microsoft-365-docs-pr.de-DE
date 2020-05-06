---
title: Suchen nach Daten in einer Untersuchung
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: ''
description: Erfahren Sie, wie Sie eine Suche erstellen, speichern und ausführen, um für Ihre Untersuchung relevante Daten zu identifizieren, und dann die Ergebnisse zu ihren beweisen hinzufügen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29a89c816c658b99b89de7f7a4e912c7b39b613c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036400"
---
# <a name="search-for-data-in-an-investigation"></a>Suchen nach Daten in einer Untersuchung

Auf der Registerkarte **Suchen** in einer Datenermittlung können Sie mithilfe von Schlüsselwörtern und Bedingungen nach ungespeicherten, vertraulichen oder vertraulichen Daten in Inhaltsspeicherorten suchen. 

Nachdem Sie eine Suche ausgeführt haben, können Sie Statistiken zu den von der Suche zurückgegebenen Elementen anzeigen, beispielsweise die inhaltsspeicherorte mit den meisten Elementen, die mit der Suchabfrage übereinstimmen. Sie können auch eine Vorschau einer Teilmenge der Ergebnisse anzeigen. Nachdem Sie den zu untersuchenden Dokumentensatz identifiziert haben, können Sie die Ergebnisse der Suche einem Beweissatz hinzufügen, um Sie weiter zu verarbeiten und zu analysieren.

## <a name="create-a-search"></a>Erstellen einer Suche

1. Klicken Sie in einer Untersuchung auf die Registerkarte **Suchen** , und klicken Sie dann auf **neue Suche**. 

    Es wird ein Assistent angezeigt, der Sie durch den Prozess des Erstellens einer Suche führt.

2. Geben Sie einen Such Namen und eine optionale Beschreibung für die Suche ein.

3. Definieren Sie Ihre Suchkriterien. Sie können Bedingungen für die Suche hinzufügen, indem Sie die vordefinierten Bedingungs Karten verwenden oder Sucheigenschaften Namen in der Stichwortabfrage verwenden. Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](build-search-queries.md).

4. Wählen Sie die zu durchsuchenden inhaltsspeicherorte (Datenquellen) aus. Sie können die Suche Bereichen, indem Sie die inhaltsspeicherorte bestimmter interessierter Personen auswählen (sofern Sie die Untersuchung hinzugefügt haben). Wenn Sie für die Untersuchung interessante Personen hinzugefügt haben, können Sie diese hinzufügen, indem Sie die Schritte unter [Verwalten von Personen mit Interesse](manage-people-of-interest.md#add-people-of-interest)ausführen.
 
   Manchmal müssen Sie möglicherweise zunächst alle inhaltsspeicherorte in Ihrer Organisation durchsuchen. Alternativ dazu müssen Sie möglicherweise Speicherorte durchsuchen, die nicht einer bestimmten Person gehören. In diesem Szenario können Sie auswählen, ob Sie Ihre gesamte Organisation oder alle Standorte für bestimmte Dienste (wie Exchange, SharePoint, OneDrive oder Teams) durchsuchen möchten.

5. Speichern Sie die Suche und führen Sie sie aus.

Nachdem die Suche erstellt wurde, wird eine Flyout-Seite mit Details zur Suche angezeigt. Die Schaltflächen **Statistik** und **Vorschau** sind anfänglich abgeblendet, da die Suche nicht abgeschlossen wurde. Sie können den Fortschritt der Suche nachverfolgen, indem Sie die Spalte **Status** auf der Registerkarte **Suchen** überwachen.

## <a name="view-statistics-and-search-results"></a>Anzeigen von Statistiken und Suchergebnissen

Nachdem Sie eine Daten Ermittlungs Suche erstellt und gestartet haben, verwendet das Tool die von Ihnen definierten Suchkriterien (Suchabfrage und inhaltsspeicherorte) und durchsucht einen Index im Live-Dienst für Elemente, die Ihren Suchkriterien entsprechen. Es gibt drei Komponenten einer Suche, die zurückgegeben werden, wenn die Suche abgeschlossen ist: 

- **Estimate** – da die Suche nur einen Index (statt die tatsächlichen inhaltsspeicherorte) durchsucht, sind die Ergebnisse einer Suche eine Schätzung (basierend auf dem, was im Index gefunden wurde, der den Suchergebnissen entsprach). Eine Zusammenfassung der Schätzung wird auf der Flyout-Seite "Suche" unter **Status**angezeigt. Der Status des Vorkalkulations Prozesses für eine Suche wird auf der Registerkarte **Suchen** in der Spalte **Schätz Status** angezeigt. Wenn die Such Schätzung abgeschlossen ist, wird dieser Status auf **erfolgreich**festgelegt.

- **Statistics** – Statistics bieten ausführlichere Informationen zu den Suchergebnissen. Dazu gehört Folgendes:

    - Zusammenfassung – Statistiken, die den Such schätzungs Ergebnissen ähneln, die auf der Flyout-Seite angezeigt werden.
    - Top Locations-Statistiken zur Anzahl der Elemente, die mit der Suchabfrage in jedem durchsuchten Inhaltsspeicherort übereinstimmen. 
    - Abfragen – detaillierte Statistiken zur Suchabfrage, einschließlich der Anzahl von Elementen, die mit jeder Bedingung in einer Suchabfrage übereinstimmen.

    Klicken Sie auf der Flyout-Seite auf **Statistik** , um diese Statistiken anzuzeigen. Diese Schaltfläche ist inaktiv, bis der Wert des **Vorkalkulationsstatus** auf der Registerkarte **Suchen** auf **erfolgreich**festgelegt ist. Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics.md).

- **Vorschau** – wenn die Suche abgeschlossen ist, können Sie die tatsächlichen Elemente aus einer Stichproben Teilmenge der Suchergebnisse anzeigen, die von der Suche zurückgegeben werden. In der systemeigenen Ansicht des Elementtyps können Sie auch die Metadaten des Elements anzeigen. Dies ist eine gute Möglichkeit, schnell festzustellen, ob Ihre Suchergebnisse Ihren Erwartungen entsprechen oder ob Sie die Suche bearbeiten und erneut ausführen müssen. Klicken Sie auf der Flyout-Seite auf **Vorschau** , um Elemente aus den Suchergebnissen anzuzeigen. Diese Schaltfläche ist inaktiv, bis der Wert des **Vorschaustatus** auf der Registerkarte **Suchen** auf **erfolgreich**festgelegt ist.
 
> [!NOTE]
> Die Statuswerte für die Spalten **Estimate Status** and **Preview Status** auf der Registerkarte **Suchen** werden **ausgeführt**und **erfolgreich** **gesendet**. Wenn ein Fehler bei der Suche vorliegt, wird der Status **fehlgeschlagen** angezeigt.

## <a name="add-search-results-to-evidence"></a>Hinzufügen von Suchergebnissen zu beweisen

Wenn Sie mit den Ergebnissen einer Suche zufrieden sind und diese Suchergebnisse analysieren und korrigieren möchten, können Sie Sie zu einem in der Untersuchung festgelegten Beweis hinzufügen. Wenn Sie einem Evidence-Element auf der Registerkarte **Beweise** Elemente hinzufügen, treten die folgenden drei Vorgänge auf:

- Die Suche wird erneut ausgeführt, und dem Beweissatz werden die neuesten Ergebnisse der Suche hinzugefügt. Das bedeutet, dass die Elemente, die zum Beweis hinzugefügt werden, unterschiedlich sein können als die geschätzten Suchergebnisse, die auf der Flyout-Suchseite angezeigt werden. Dies kann passieren, wenn sich zwischen dem letzten Ausführen der Suche und dem Hinzufügen der Suchergebnisse zu beweisen einige Zeit bestanden hat.

- Alle Elemente in den Suchergebnissen werden aus der Datenquelle im Live-Dienst kopiert und in einen sicheren Azure-Speicherort in der Microsoft-Cloud kopiert.

- Alle Elemente (einschließlich der Inhalte und Metadaten) werden erneut indiziert, sodass alle Daten im Evidence-Satzes während der Untersuchung vollständig durchsuchbar sind. Durch das erneute Indizieren der Daten werden eingehende und schnelle Suchvorgänge durchsucht, wenn Sie während der Untersuchung die Daten im Beweissatzes durchsuchen.

Ein Vorteil beim Kopieren der Livedaten in einen Beweissatz in Azure besteht darin, dass Sie für zeitkritische oder kritische Vorfälle schnell den Schaden durch sofortiges löschen verdächtiger Inhalte in der ursprünglichen Datenquelle im Live-Dienst und anschließend untersuchen des Vorfalls durch Analysieren der in die Quarantäne Umgebung des Azure-Speicherorts kopierten Beweise eindämmen können. 

Das Kopieren der ursprünglichen Daten in den Beweissatz erleichtert auch ihre Untersuchung, indem Sie erweiterte Analysetools wie die Erkennung von Designs, die Erkennung praktischer Duplikate und die e-Mail-Threadidentifikation bereitstellen.

Falls erforderlich, können Sie auch Daten aus nicht-Microcsoft 365-Datenquellen zu einem Beweissatz hinzufügen, sodass dieser zusammen mit den von Microsoft 365 gesammelten Daten gespeichert wird.

Zum Hinzufügen von Daten zu einem Beweissatz wählen Sie auf der Registerkarte **Suchen** eine Suche aus, und klicken Sie dann auf der Flyout-Seite auf **Ergebnisse zu Beweismitteln hinzufügen** . Sie können einem vorhandenen Beweissatz Daten hinzufügen oder die neuen Beweis Sätze schnell erstellen.

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a>Nachverfolgen des Fortschritts beim Hinzufügen von Suchergebnissen zu beweisen

Das Hinzufügen von Daten zu einem Evidence-Datensatz ist ein langwieriger Prozess. Der Prozess umfasst das Sammeln der Elemente, die die ursprüngliche Datenquelle von Microsoft 365 (beispielsweise von Postfächern und Websites), kopieren Sie Sie in den Azure-Speicherort (dieser Kopiervorgang wird auch als *Einnahme*bezeichnet), und dann erneut indizieren der Elemente. Sie können den Fortschritt entweder auf der Registerkarte **Aufträge** oder auf der Registerkarte **Suchen** in der Spalte **hinzugefügte Daten in Evidence nach** verfolgen. Nachdem die Verarbeitung der Beweis Verarbeitung abgeschlossen ist, können Sie zur Registerkarte **Beweise** wechseln, auf den Beweissatz klicken und dann Ihre Untersuchung starten, indem Sie die relevanten Daten nach Bedarf suchen, überprüfen, markieren und exportieren.
