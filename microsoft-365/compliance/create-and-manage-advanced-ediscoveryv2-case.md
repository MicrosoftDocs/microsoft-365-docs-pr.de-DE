---
title: Erstellen und Verwalten von Advanced eDiscovery-Fällen in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Advanced eDiscovery-Fälle erstellt und verwaltet werden. Im ersten Schritt erstellen Sie einen Fall und beginnen mit der Verwendung von Advanced eDiscovery-Features und -Funktionen.
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841624"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Erstellen und Verwalten eines Advanced eDiscovery-Falls

Nach dem Einrichten von Advanced eDiscovery und dem Zuweisen von Berechtigungen zu [eDiscovery-Managern](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) in Ihrer Organisation, die Fälle verwalten, besteht der nächste Schritt im Erstellen und Verwalten eines Falls.

Dieser Artikel bietet auch eine übersicht über die Verwendung von Fällen zum Verwalten des Advanced eDiscovery-Workflows für eine rechtliche Untersuchung.

## <a name="create-a-case"></a>Erstellen eines Falls

Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt.

1. Wechseln Sie zu und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto [https://compliance.microsoft.com](https://compliance.microsoft.com) an, dem eDiscovery-Berechtigungen zugewiesen wurden. Mitglieder der Rollengruppe "Organisationsverwaltung" können auch Advanced eDiscovery-Fälle erstellen.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

3. Klicken Sie **auf der Seite "Advanced eDiscovery"** auf **die** Registerkarte "Fälle", und klicken Sie dann auf **"Fall erstellen".**

4. Geben Sie auf der Flyoutseite für neue **eDiscovery-Fälle** dem Fall einen Namen (erforderlich) zu, und geben Sie dann eine optionale Fallnummer und Beschreibung ein. Der Fallname muss in Ihrer Organisation eindeutig sein.

5. Klicken **Sie auf "Speichern",** um den Fall zu erstellen.

   Der neue Fall wird erstellt, **und** die Registerkarte "Einstellungen" im neuen Fall wird angezeigt.

6. Klicken Sie auf & Registerkarte **"Einstellungen"** auf der Registerkarte "Access-Berechtigungen" auf "Auswählen" **und** dann auf **"Aktualisieren".** 

7. Klicken Sie auf **Aktualisieren**.

8. Klicken Sie **auf der Flyoutseite "Diesen** Fall verwalten" unter "Mitglieder verwalten" auf **"Hinzufügen",** um dem Fall Mitglieder hinzuzufügen. 

9. Aktivieren Sie in der Liste der Personen das Kontrollkästchen neben den Namen der Personen, die Sie dem Fall hinzufügen möchten. Stellen Sie wie zuvor erläutert sicher, dass den Personen, die Sie dem Fall hinzufügen, die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

10. Nachdem Sie die Personen ausgewählt haben, die als Mitglieder des Falls hinzugefügt werden, klicken Sie auf **"Hinzufügen".**

11. Klicken Sie auf der Flyout-Seite **Fall verwalten** auf **Speichern**, um die neue Liste der Fallbeteiligten zu speichern.

12. Klicken Sie auf **die Registerkarte** "Start", um zur Fall-Startseite zu wechseln.

## <a name="manage-the-workflow"></a>Verwalten des Workflows

Als Einstieg in die Verwendung von Advanced eDiscovery finden Sie hier einen grundlegenden Workflow, der auf gängige [eDiscovery-Methoden ausgerichtet ist.](advanced-ediscovery-edrm.md) In jedem dieser Schritte werden auch einige erweiterte Erweiterte eDiscovery-Funktionen hervorgehoben, die Sie erkunden können.

![Advanced eDiscovery-Workflow](../media/AeDWorkflow.png)

1. **[Fügen Sie dem Fall](add-custodians-to-case.md) [Verwahrer und](non-custodial-data-sources.md)** Datenquellen ohne Verwahrer hinzu. Der erste Schritt nach dem Erstellen eines Falls besteht im Hinzufügen von Verwahrern. Ein *Verwahrer* ist eine Person, die die administrative Kontrolle über ein Dokument oder eine elektronische Datei hat, die für den Fall relevant sein kann. Darüber hinaus können Sie Datenquellen hinzufügen, die keinem bestimmten Benutzer zugeordnet sind, aber möglicherweise für den Fall relevant sind.

   Hier sind einige Dinge, die passieren (oder die Sie tun können), wenn Sie einem Fall Verwahrer hinzufügen:

   - Daten im Exchange-Postfach des Verwahrers, im #A0 und in allen Microsoft Teams- oder Yammer-Gruppen, in der der Verwahrer Mitglied ist, können in dem Fall als Verwahrerdaten "markiert" werden.
  
   - Verwahrerdaten werden neu indiziert (durch einen Prozess namens *Erweiterte Indizierung).* Dadurch wird die Suche im nächsten Schritt optimiert.
  
   - Sie können die Daten von Verwahrer in einem Haltespeicher platzieren. Dadurch werden Daten beibehalten, die für den Fall während der Untersuchung relevant sein können.
  
   - Sie können einem Verwahrer andere Datenquellen zuordnen (z. B. können Sie eine #A0 oder Eine Microsoft 365-Gruppe einem Verwahrer zuordnen), damit diese Daten neu indiziert, in den Haltepunkt gesetzt und durchsucht werden können, genau wie die Daten im Postfach oder #A1 des Wahrers.

   - Sie können den [Kommunikationsworkflow](managing-custodian-communications.md) in Advanced eDiscovery verwenden, um eine Benachrichtigung über die gesetzliche Haltebereichsaufbewahrung an Verwahrer zu senden.

2. **[Durchsuchen Sie Datenquellen nach Daten, die für den Fall relevant sind.](collecting-data-for-ediscovery.md)** Nachdem Sie verwahrer und nicht verwahrte Datenquellen zu einem Fall hinzugefügt haben, verwenden Sie das integrierte Suchtool, um diese Datenquellen nach Daten zu durchsuchen, die für den Fall relevant sein können. Sie verwenden Schlüsselwörter, Eigenschaften [](building-search-queries.md) und Bedingungen, um Suchabfragen zu erstellen, die Suchergebnisse mit den Daten zurückgeben, die wahrscheinlich für den Fall relevant sind. Sie können auch Folgendes tun:

   - Anzeigen [von Suchstatistiken,](search-statistics-in-advanced-ediscovery.md) mit deren Hilfe Sie eine Suchabfrage verfeinern können, um die Ergebnisse einengt.

   - Zeigen Sie eine Vorschau der Suchergebnisse an, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Suche erneut aus.

3. **[Hinzufügen von Daten zu einem Überprüfungssatz](add-data-to-review-set.md)**. Nachdem Sie konfiguriert und überprüft haben, ob eine Suche die gewünschten Daten zurückgibt, fügen Sie im nächsten Schritt die Suchergebnisse einem Überprüfungssatz hinzu. Wenn Sie einem Überprüfungssatz Daten hinzufügen, werden Elemente von ihrem ursprünglichen Speicherort an einen sicheren Speicherort in Azure kopiert. Die Daten werden erneut indiziert, um sie für gründliche und schnelle Suchen beim Überprüfen und Analysieren von Elementen im Überprüfungssatz zu optimieren. Darüber hinaus können Sie einem Überprüfungssatz [auch Nicht-Office 365-Daten hinzufügen.](load-non-office-365-data-into-a-review-set.md)

   Es gibt auch eine spezielle Art von Überprüfungssatz, dem Sie Daten hinzufügen können, die als *Unterhaltungsüberprüfungssatz bezeichnet werden.* Diese Arten von Rezensionssätzen bieten Funktionen zur Wiederherstellung von Unterhaltungen zum Rekonstruieren, Überprüfen und Exportieren von Threadunterhaltungen wie in Microsoft Teams. Weitere Informationen finden Sie unter ["Überprüfen von Unterhaltungen in Advanced eDiscovery".](conversation-review-sets.md)

4. **Überprüfen und Analysieren von Daten in einem Überprüfungssatz**. Da sich die Daten nun in einem Überprüfungssatz befindet, können Sie eine Vielzahl von Tools und Funktionen zum Anzeigen und Analysieren der Falldaten verwenden, um den Datensatz auf das zu reduzieren, was für den untersuchten Fall am relevantesten ist. Hier ist eine Liste einiger Tools und Funktionen, die Sie während dieses Prozesses verwenden können.

   - [Dokumente anzeigen](view-documents-in-review-set.md). Dies umfasst das Anzeigen der Metadaten für jedes Dokument in einem Überprüfungssatz und das Anzeigen des Dokuments in der systemeigenen Version oder Textversion.

   - [Erstellen sie Abfragen und Filter.](review-set-search.md) Sie erstellen Suchabfragen mithilfe verschiedener Suchkriterien (einschließlich der Möglichkeit, alle Dateimetadateneigenschaften zu [durchsuchen),](document-metadata-fields-in-advanced-ediscovery.md)um die Falldaten weiter zu verfeinern und zu dem zu ernennen, was für den Fall am relevantesten ist. Sie können auch Überprüfungssatzfilter verwenden, um schnell andere Bedingungen auf die Ergebnisse einer Suchabfrage anzuwenden, um diese Ergebnisse weiter zu verfeinern. 

   - [Erstellen und Verwenden von Tags](tagging-documents.md). Sie können Tags auf Dokumente in einem Überprüfungssatz anwenden, um zu identifizieren, welche reagieren (oder nicht auf den Fall reagieren) und diese Tags dann beim Erstellen von Suchabfragen verwenden, um die markierten Dokumente ein- oder auszuschließen. Sie können auch markierungen, um zu bestimmen, welche Dokumente exportiert werden.

   - [Dokumente kommentieren und rotieren.](view-documents-in-review-set.md#annotate-view) Sie können das Anmerkungstool in einer Rezension verwenden, um Dokumente zu kommentieren und Inhalte in Dokumenten als Arbeitsprodukt zu ändern. Wir generieren während der Überprüfung eine PDF-Version eines kommentierten oder redigierten Dokuments, um das Risiko zu verringern, dass die nicht gedacte systemeigene Version des Dokuments exportiert wird.

   - [Analysieren sie Falldaten.](analyzing-data-in-review-set.md) Die Analysefunktionalität in Advanced eDiscovery ist leistungsstark. Nachdem Sie analysen für die Daten im Überprüfungssatz ausgeführt haben, führen wir Analysen durch, z. B. die Erkennung nahezu doppelter Duplikate, E-Mail-Threading und Designs, mit deren Hilfe Sie die Menge der dokumente reduzieren können, die Sie überprüfen müssen. Außerdem generieren wir analyseberichte, die das Ergebnis der Ausführung von Analysen zusammenfassen. Wie zuvor erläutert, wird bei der Ausführung der Analyse auch das [Anwalts-Client-Berechtigungserkennungsmodell ausgeführt.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportieren und Herunterladen von Falldaten.** Ein letzter Schritt nach dem Sammeln, Überprüfen und Analysieren von Falldaten besteht im Exportieren dieser Daten aus Advanced eDiscovery zur externen Überprüfung oder zur Überprüfung durch Personen außerhalb des Untersuchungsteams. Das Exportieren von Daten besteht aus zwei Schritte. Der erste Schritt [](export-documents-from-review-set.md) besteht im Exportieren von Daten aus dem Überprüfungssatz und kopieren sie an einen anderen Azure Storage-Speicherort (von Microsoft bereitgestellt oder von Ihrer Organisation verwaltet). Anschließend verwenden Sie Azure Storage Explorer, um [die Daten](download-export-jobs.md) auf einen lokalen Computer herunterzuladen. Zusätzlich zu den exportierten Datendateien enthält der Inhalt des Exportpakets auch einen Exportbericht, einen Zusammenfassungsbericht und einen Fehlerbericht.
