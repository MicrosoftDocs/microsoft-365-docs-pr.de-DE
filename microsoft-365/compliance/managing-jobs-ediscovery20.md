---
title: Verwalten von Aufträgen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery können Sie den Status von prozessen mit langer Laufzeit im Zusammenhang mit der Ausführung verschiedener Aufgaben Advanced eDiscovery nachverfolgen.
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471078"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Verwalten von Aufträgen in Advanced eDiscovery

Hier finden Sie eine Liste der Aufträge (bei denen es sich  in der Regel um lange ausgeführte Prozesse handelt), die auf der Registerkarte Aufträge eines Falls in einem Fall in Advanced eDiscovery. Diese Aufträge werden durch Benutzeraktionen ausgelöst, wenn Sie Fälle verwenden und verwalten.

| Auftragstyp           | Beschreibung     |
| :----------------- | :----------     |
|Hinzufügen von Daten zu einem Überprüfungssatz | Ein Benutzer fügt einem Überprüfungssatz eine Auflistung hinzu. Dieser Auftrag besteht aus zwei Unteraufträgen: </br>• **Export** – Eine Liste der Elemente in der Auflistung wird generiert. </br>• **Ingestion & Indizierung** : Die Elemente in der Auflistung, die mit der Suchabfrage übereinstimmen, werden an einen Azure Storage-Speicherort (in einem Prozess namens *Ingestion)* kopiert, und dann werden diese Elemente am Speicherort Azure Storage neu indiziert. Dieser neue Index wird beim Abfragen und Analysieren von Elementen im Datensatz verwendet. </br></br>Weitere Informationen finden Sie unter [Hinzufügen von Suchergebnissen zu einem Überprüfungssatz](add-data-to-review-set.md). |
|Hinzufügen von Daten zu einem anderen Überprüfungssatz | Ein Benutzer fügt Dokumente aus einem Überprüfungssatz einem anderen Überprüfungssatz im gleichen Fall hinzu. Weitere Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungssatz aus einem anderen Überprüfungssatz](add-data-to-review-set-from-another-review-set.md).|
|Hinzufügen nicht Microsoft 365 Daten zu einem Überprüfungssatz | Ein Benutzer lädt nicht Microsoft 365 Daten in einen Überprüfungssatz hoch. Die Daten werden auch während dieses Vorgangs indiziert. Beispielsweise werden Dateien von einem lokalen Dateiserver oder einem Clientcomputer in einen Überprüfungssatz hochgeladen. Weitere Informationen finden Sie unter [Load non-Microsoft 365 data into a review set](load-non-office-365-data-into-a-review-set.md).| 
|Hinzufügen von behobenen Daten zu einem Überprüfungssatz | Daten mit Verarbeitungsfehlern werden behoben und wieder in einen Überprüfungssatz geladen. Weitere Informationen finden Sie unter:</br>• [Fehlerbehebung beim Verarbeiten von Daten](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Fehlerbehebung für einzelne Elemente](single-item-error-remediation.md)| 
|Vergleichen von Lastensätzen | Ein Benutzer betrachtet die Unterschiede zwischen verschiedenen Lastensätzen in einem Überprüfungssatz. Ein Ladesatz ist eine Instanz beim Hinzufügen von Daten zu einem Prüfdateisatz. Wenn Sie z. B. die Ergebnisse von zwei unterschiedlichen Suchen zum gleichen Überprüfungssatz hinzufügen, stellt jede einen Lastensatz dar. |
|Unterhaltungsrekonstruktion|Wenn ein Benutzer die Ergebnisse einer Suche zu einem Unterhaltungsüberprüfungssatz hinzufügt, werden Chatunterhaltungen (auch Threadunterhaltungen *genannt)* in Diensten wie Microsoft Teams in einer PDF-Datei rekonstruiert. Dieser Auftrag wird auch ausgelöst, wenn ein Benutzer auf **Aktion klickt, > Unterhaltungs-PDFs** in einem Überprüfungssatz erstellen. Weitere Informationen finden Sie unter [Überprüfen von Unterhaltungen in Advanced eDiscovery](conversation-review-sets.md).
|Konvertieren von redaktierten Dokumenten in PDF|Nachdem ein Benutzer ein Dokument in einem Überprüfungssatz kommentiert und einen Teil davon neu abgibt, kann er das redaktierte Dokument in eine PDF-Datei konvertieren. Dadurch wird sichergestellt, dass der rotierte Teil nicht angezeigt wird, wenn das Dokument zur Präsentation exportiert wird. Weitere Informationen finden Sie unter [Anzeigen von Dokumenten in einem Überprüfungssatz](annotating-and-redacting-documents.md). |
|Schätzen von Suchergebnissen | Nachdem ein Benutzer eine Entwurfssammlung erstellt und ausgeführt oder erneut ausgeführt hat, durchsucht das Suchtool den Index nach Elementen, die mit der Suchabfrage übereinstimmen, und bereitet eine Schätzung vor, die die Anzahl und Gesamtgröße aller Elemente der Suche sowie die Anzahl der durchsuchten Datenquellen enthält.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md). | 
|Vorbereiten von Daten für den Export | Ein Benutzer exportiert Dokumente aus einem Überprüfungssatz. Wenn der Exportvorgang abgeschlossen ist, können sie die exportierten Daten auf einen lokalen Computer herunterladen. Weitere Informationen finden Sie unter [Export case data](exporting-data-ediscover20.md). | 
|Vorbereiten der Fehlerauflösung |Wenn ein Benutzer eine Datei auswählt und eine neue Fehlerbehebung in der Fehleransicht auf der Registerkarte Verarbeitung eines Falls erstellt, besteht der erste Schritt im Prozess im Hochladen der Datei mit dem Verarbeitungsfehler an einen Azure Storage-Speicherort in der Microsoft-Cloud.  Dieser Auftrag verfolgt den Fortschritt des Uploadvorgangs. Weitere Informationen zum Fehlerbehebungsworkflow finden Sie unter [Error remediation when processing data](error-remediation-when-processing-data-in-advanced-ediscovery.md). | 
|Vorbereiten der Suchvorschau | Nachdem ein Benutzer eine neue Entwurfssammlung erstellt und ausgeführt hat (oder eine vorhandene Entwurfssammlung erneut ausgeführt hat), bereitet das Suchtool eine Beispielmenge von Elementen (die mit der Suchabfrage übereinstimmen) vor, die in der Vorschau angezeigt werden kann. Die Vorschau der Suchergebnisse hilft Ihnen, die Effektivität der Suche zu bestimmen.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Erneute Indizierung von Verwahrerdaten | Wenn Sie einem Fall einen Verwahrer hinzufügen, werden alle teilweise indizierten Elemente in den ausgewählten Datenquellen des Custodians durch einen Prozess namens Erweiterte Indizierung neu *indiziert.* Dieser Auftrag wird auch  ausgelöst, wenn  Sie auf der Registerkarte Verarbeitung eines Falls auf Index aktualisieren klicken und wenn Sie den Index für einen bestimmten Custodian auf der Flyoutseite der Custodian-Eigenschaften aktualisieren. Weitere Informationen finden Sie unter [Advanced indexing of custodian data](indexing-custodian-data.md).
|Ausführen von Analysen | Ein Benutzer analysiert Daten in einem Überprüfungssatz, indem Advanced eDiscovery Wie z. B. die Erkennung von Duplikaten, die E-Mail-Threadinganalyse und die Designsanalyse ausgeführt werden. Weitere Informationen finden Sie unter [Analysieren von Daten in einem Überprüfungssatz](analyzing-data-in-review-set.md). | 
|Markieren von Dokumenten | Dieser Auftrag wird ausgelöst, wenn ein Benutzer beim Überprüfen von Dokumenten in einem Überprüfungssatz auf Den **Taggingauftrag** starten im **Tagging-Bereich** klickt. Ein Benutzer kann diesen Auftrag starten, nachdem er Dokumente in einem Überprüfungssatz markieren und dann im Ansichtsdokumentbereich massen auswählen kann. Weitere Informationen finden Sie [unter Tag documents in a review set](tagging-documents.md). | 
|||

## <a name="job-status"></a>Auftragsstatus

In der folgenden Tabelle werden die verschiedenen Statuszustände für Aufträge beschrieben.

| Status           | Beschreibung     |
| :----------------- | :----------     |
| Übermittelt | Ein neuer Auftrag wurde erstellt.  Datum und Uhrzeit, zu der der Auftrag übermittelt wurde, werden in der Spalte **Erstellt** auf der Registerkarte **Aufträge** angezeigt. |
| Übermittlung fehlgeschlagen | Fehler bei der Auftragsübermittlung.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut ausführen. |
| In Arbeit | Der Auftrag wird ausgeführt, Sie können den Fortschritt des Auftrags auf der Registerkarte **Aufträge** überwachen. |
| Erfolgreich | Der Auftrag wurde erfolgreich abgeschlossen. Datum und Uhrzeit, zu der der Auftrag abgeschlossen wurde, werden in der Spalte **Abgeschlossen** auf der Registerkarte **Aufträge** angezeigt. |
| Teilweise erfolgreich | Der Auftrag war erfolgreich. Dieser Status wird in der Regel zurückgegeben, wenn der Auftrag in einigen der Vertrauenswürdigen Datenquellen keine teilweise indizierten Daten (auch als nicht *indizierte* Daten bezeichnet) fand.  |
| Fehlgeschlagen | Fehler beim Auftrag.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut ausführen. Wenn der Auftrag ein zweites Mal fehlschlägt, wird empfohlen, sich an den Microsoft Support zu wenden und die Supportinformationen aus dem Auftrag zur Verfügung zu stellen. |
|||
