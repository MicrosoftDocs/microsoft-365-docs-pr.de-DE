---
title: Erstellen und Verwalten Advanced eDiscovery Fällen in Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird das Erstellen und Verwalten von Advanced eDiscovery beschrieben. Der erste Schritt besteht in der Erstellung eines Falls und der Verwendung Advanced eDiscovery Funktionen.
ms.openlocfilehash: 95e88bb071476de1ed66b3ffaa8942f0a9df89c2
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311640"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Erstellen und Verwalten eines Advanced eDiscovery Fall

Nach dem Einrichten Advanced eDiscovery und dem Zuweisen von Berechtigungen zu [eDiscovery-Managern](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) in Ihrer Organisation, die Fälle verwalten, besteht der nächste Schritt im Erstellen und Verwalten eines Falls.

Dieser Artikel bietet außerdem einen umfassenden Überblick über die Verwendung von Fällen zum Verwalten Advanced eDiscovery Workflow für einen Rechtsstreit oder andere Arten von Untersuchungen.

## <a name="create-a-case"></a>Erstellen eines Falls

Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt. Mitglieder des Falls können auf den Fall im Microsoft 365 zugreifen und Advanced eDiscovery ausführen.

1. Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto <https://compliance.microsoft.com> an, dem eDiscovery-Berechtigungen zugewiesen wurden. Mitglieder der Rollengruppe Organisationsverwaltung können auch Advanced eDiscovery erstellen.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

3. Klicken Sie **Advanced eDiscovery** Seite auf **die** Registerkarte Fälle, und klicken Sie dann auf **Fall erstellen**.

4. Geben Sie auf der Flyoutseite Neuer **eDiscovery-Fall** dem Fall einen Namen (erforderlich) zu, und geben Sie dann eine optionale Fallnummer und Beschreibung ein. Der Fallname muss in Ihrer Organisation eindeutig sein.

5. Klicken **Sie auf Speichern,** um den Fall zu erstellen.

   Der neue Fall wird erstellt, und **die Einstellungen** im neuen Fall wird angezeigt.

6. Klicken Sie **auf &** Registerkarte Zugriff **Einstellungen** Berechtigungen auf **Auswählen**.

7. Klicken Sie **auf der Seite** Flyout für diesen Fall verwalten unter Mitglieder **verwalten** auf **Hinzufügen,** um dem Fall Mitglieder hinzuzufügen.

8. Aktivieren Sie in der Liste der Personen das Kontrollkästchen neben den Namen der Personen, die Sie dem Fall hinzufügen möchten. Stellen Sie wie bereits erläutert sicher, dass den Personen, die Sie dem Fall hinzufügen, die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

9. Nachdem Sie die Personen ausgewählt haben, die als Mitglieder des Falls hinzugefügt werden, klicken Sie auf **Hinzufügen**.

10. Klicken Sie auf der Flyout-Seite **Fall verwalten** auf **Speichern**, um die neue Liste der Fallbeteiligten zu speichern.

11. Klicken Sie auf **die Registerkarte Start,** um zur Fall-Homepage zu wechseln.

## <a name="manage-the-workflow"></a>Verwalten des Workflows

Hier finden Sie einen Advanced eDiscovery, der an gängigen [eDiscovery-Methoden ausgerichtet ist.](advanced-ediscovery-edrm.md) In jedem dieser Schritte werden auch einige erweiterte Funktionen Advanced eDiscovery, die Sie erkunden können.

![Advanced eDiscovery-Workflow](../media/AeDWorkflow.png)

1. **[Fügen Sie dem Fall](add-custodians-to-case.md) Custodians und [nicht verwahrte](non-custodial-data-sources.md) Datenquellen hinzu.** Der erste Schritt nach dem Erstellen eines Falls besteht im Hinzufügen von Verwahrern. Ein *Verwahrer* ist eine Person mit administrativer Kontrolle über ein Dokument oder eine elektronische Datei, die für den Fall relevant sein kann. Darüber hinaus können Sie Datenquellen hinzufügen, die keinem bestimmten Benutzer zugeordnet sind, aber möglicherweise für den Fall relevant sind.

   Hier sind einige Dinge, die passieren (oder die Sie tun können), wenn Sie einem Fall Custodians hinzufügen:

   - Daten im Exchange-Postfach, im OneDrive-Konto und in allen Microsoft Teams- oder Yammer-Gruppen, in der der Custodian Mitglied ist, können in dem Fall als Verwahrerdaten "markiert" werden.
  
   - Verwahrerdaten werden neu indiziert (durch einen Prozess namens *Erweiterte Indizierung*). Dies trägt dazu bei, die Suche im nächsten Schritt zu optimieren.
  
   - Sie können Personenbezogene Daten in einem Halterecht speichern. Dadurch werden Daten beibehalten, die für den Fall während der Untersuchung relevant sein können.
  
   - Sie können einem Verwahrer andere Datenquellen zuordnen (z. B. können Sie eine SharePoint-Website oder eine Microsoft 365-Gruppe einem Verwahrer zuordnen), damit diese Daten wie die Daten im Postfach oder im OneDrive-Konto des Verwahrers neu indiziert, gespeichert und durchsucht werden können.

   - Sie können den [Kommunikationsworkflow](managing-custodian-communications.md) in Advanced eDiscovery verwenden, um eine Benachrichtigung über das gesetzliche Halterecht an Custodians zu senden.

2. **[Sammeln relevanter Inhalte aus Datenquellen](create-draft-collection.md)**. Nachdem Sie einem Fall Custodians und nicht verwahrte Datenquellen hinzugefügt haben, verwenden Sie das integrierte Sammlungstool, um diese Datenquellen nach Inhalten zu durchsuchen, die für den Fall relevant sein können. Sie verwenden Schlüsselwörter, Eigenschaften [](building-search-queries.md) und Bedingungen, um Suchabfragen zu erstellen, die Suchergebnisse mit den Daten zurückgeben, die für den Fall am ehesten relevant sind. Sie können auch Folgendes tun:

   - Zeigen [Sie Sammlungsstatistiken](collection-statistics-reports.md) an, mit deren Hilfe Sie eine Auflistung verfeinern können, um die Ergebnisse zu verfeinern.

   - Vorschau eines Beispiels der Auflistung, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Auflistung erneut aus.

3. **[Commit-Auflistung an einen Überprüfungssatz](commit-draft-collection.md)**. Nachdem Sie konfiguriert und überprüft haben, ob eine Suche die gewünschten Daten zurückgibt, fügen Sie im nächsten Schritt die Suchergebnisse zu einem Überprüfungssatz hinzu. Wenn Sie einem Überprüfungssatz Daten hinzufügen, werden Elemente vom ursprünglichen Speicherort an einen sicheren Speicherort Azure Storage kopiert. Die Daten werden erneut indiziert, um sie für eine sorgfältige und schnelle Suche beim Überprüfen und Analysieren von Elementen im Überprüfungssatz zu optimieren. Darüber hinaus können Sie [einem Überprüfungssatz Office 365](load-non-office-365-data-into-a-review-set.md)Daten hinzufügen.

   Es gibt auch eine spezielle Art von Überprüfungssatz, dem Sie Daten hinzufügen können, die als *Unterhaltungsüberprüfungssatz bezeichnet werden.* Diese Arten von Rezensionssätzen bieten Unterhaltungsrekonstruktionsfunktionen zum Rekonstruieren, Überprüfen und Exportieren von Threadunterhaltungen wie in Microsoft Teams. Weitere Informationen finden Sie unter [Überprüfen von Unterhaltungen in Advanced eDiscovery](conversation-review-sets.md).

4. **Überprüfen und Analysieren von Daten in einem Überprüfungssatz**. Da sich Die Daten nun in einem Überprüfungssatz befindet, können Sie eine Vielzahl von Tools und Funktionen verwenden, um die Falldaten mit dem Ziel zu anzeigen und zu analysieren, um den Datensatz auf das zu reduzieren, was für den fall, den Sie untersuchen, am relevantesten ist. Hier finden Sie eine Liste einiger Tools und Funktionen, die Sie während dieses Prozesses verwenden können.

   - [Anzeigen von Dokumenten](view-documents-in-review-set.md). Dazu gehören das Anzeigen der Metadaten für jedes Dokument in einem Überprüfungssatz und das Anzeigen des Dokuments in der systemeigenen Version oder Textversion.

   - [Erstellen von Abfragen und Filtern](review-set-search.md). Sie erstellen Suchabfragen mithilfe verschiedener Suchkriterien (einschließlich der Möglichkeit, alle Dateimetadateneigenschaften zu durchsuchen), um die Falldaten weiter zu verfeinern und auf das zu ändern, was für den Fall am relevantesten ist. [](document-metadata-fields-in-advanced-ediscovery.md) Sie können auch Überprüfungssatzfilter verwenden, um schnell andere Bedingungen auf die Ergebnisse einer Suchabfrage anzuwenden, um diese Ergebnisse weiter zu verfeinern. 

   - [Erstellen und Verwenden von Tags](tagging-documents.md). Sie können Tags auf Dokumente in einem Überprüfungssatz anwenden, um die reaktionsschnellen (oder nicht reaktionsschnellen) Dokumente zu identifizieren und diese Tags dann beim Erstellen von Suchabfragen zu verwenden, um die markierten Dokumente ein- oder auszuschließen. Sie können auch markierungen, um zu bestimmen, welche Dokumente exportiert werden.

   - [Anmerkungen und Redact-Dokumente](view-documents-in-review-set.md#annotate-view). Sie können das Anmerkungstool in einer Rezension verwenden, um Dokumente zu kommentieren und Inhalte in Dokumenten als Arbeitsprodukt zu rotieren. Wir generieren während der Überprüfung eine PDF-Version eines kommentierten oder redaktierten Dokuments, um das Risiko zu verringern, dass die nicht gewagte systemeigene Version des Dokuments exportiert wird.

   - [Analysieren von Falldaten](analyzing-data-in-review-set.md). Die Analysefunktionalität in Advanced eDiscovery ist leistungsstark. Nachdem Sie Analysen für die Daten im Überprüfungssatz ausgeführt haben, führen wir Analysen durch, z. B. in der Nähe von Duplikaterkennung, E-Mail-Threading und Designs, die dazu beitragen können, die Menge an Dokumenten zu reduzieren, die Sie überprüfen müssen. Außerdem generieren wir einen Analysebericht, der das Ergebnis der ausgeführten Analyse zusammenfasst. Wie bereits erläutert, wird bei der Ausführung der Analyse auch [das Erkennungsmodell der Anwalts-Client-Rechte ausgeführt.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportieren und Herunterladen von Falldaten**. Ein letzter Schritt nach dem Sammeln, Überprüfen und Analysieren von Falldaten besteht im Exportieren aus Advanced eDiscovery zur externen Überprüfung oder zur Überprüfung durch Personen außerhalb des Untersuchungsteams. Das Exportieren von Daten ist ein Zwei-Schritt-Prozess. Der erste Schritt [](export-documents-from-review-set.md) besteht im Exportieren von Daten aus dem Überprüfungssatz und kopieren Sie sie an einen anderen Azure Storage (einer von Microsoft oder einer, der von Ihrer Organisation verwaltet wird). Anschließend verwenden Sie Azure Storage-Explorer, [um die Daten auf](download-export-jobs.md) einen lokalen Computer herunterzuladen. Zusätzlich zu den exportierten Datendateien enthält der Inhalt des Exportpakets auch einen Exportbericht, einen Zusammenfassenden Bericht und einen Fehlerbericht.

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery Architektur

Hier ist ein Architekturdiagramm, das den Advanced eDiscovery-End-to-End-Workflow in einer Einzel-Geo-Umgebung und in einer Multi-Geo-Umgebung sowie den End-to-End-Datenfluss zeigt, der mit dem elektronischen Discoveryreferenzmodell abgestimmt [ist.](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Modellposter: Advanced eDiscovery Architektur in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Anzeigen als Bild](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Herunterladen als PDF-Datei](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Herunterladen als Visio Datei](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
