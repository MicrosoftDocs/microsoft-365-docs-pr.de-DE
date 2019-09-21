---
title: Verwalten von Aufträgen in Daten Untersuchungen
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
description: 'Sie können den Status langwieriger Prozesse nachverfolgen, die beim Ausführen von Aufgaben im Tool zur Datenermittlung im Security #a0 Compliance Center auftreten.'
ms.openlocfilehash: 0c93df9e7d5ec176c2150e706fe99ed239be8527
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081596"
---
# <a name="manage-jobs-in-data-investigations-preview"></a>Verwalten von Aufträgen in Daten Untersuchungen (Vorschau)

Im folgenden finden Sie eine Liste der Aufträge (in der Regel langwierige Prozesse), die auf der Registerkarte **Aufträge** einer Untersuchung in Data Investigations (Preview) nachverfolgt werden. Diese Aufträge werden durch Benutzeraktionen bei der Verwendung und Verwaltung von Untersuchungen ausgelöst.

| Auftragstyp           | Beschreibung     |
| :----------------- | :----------     |
|Hinzufügen von Daten zu einem Beweissatzes | Ein Benutzer fügt die Ergebnisse einer Suche zu einem Beweissatz hinzu.  Weitere Informationen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md). |
|Hinzufügen von Daten zu einem anderen Beweissatzes | Ein Benutzer fügt Dokumente aus einem Beweissatz in demselben Fall in einen anderen Beweissatz ein.|
|Hinzufügen von nicht Office 365-Daten zu einem Beweissatzes | Ein Benutzer lädt nicht Office 365 Daten in einen Beweissatz hoch. Die Daten werden auch während dieses Prozesses indiziert. Beispielsweise werden Dateien von einem lokalen Dateiserver oder einem Clientcomputer in einen Beweissatz hochgeladen. Weitere Informationen finden Sie unter [Laden von nicht Office 365 Daten in Beweise](load-non-office365-data.md).| 
|Hinzufügen von korrigierten Daten zu einem Evidence-Datensatz | Daten mit Verarbeitungsfehlern werden wiederhergestellt und in einen Beweissatz zurückgeladen. Weitere Informationen finden Sie unter [Fehlerkorrektur bei der Verarbeitung von Daten für eine Untersuchung](error-remediation.md). | 
|Vergleichen von Lastsätzen | Ein Benutzer prüft die Unterschiede zwischen verschiedenen Lastsätzen in einem Beweissatz. Bei einem Lastsatz handelt es sich um eine Instanz des Hinzufügens von Daten zu einem Beweissatz. Wenn Sie beispielsweise die Ergebnisse zweier unterschiedlicher Suchvorgänge dem gleichen Beweissatz hinzufügen, würde jeder einen Lastsatz darstellen. Weitere Informationen finden Sie unter [Manage Last Sets](manage-load-sets.md). |
|Konvertieren von behandelten Dokumenten in PDF|Nachdem ein Benutzer ein Dokument in einem Beweissatz kommentiert und einen Teil davon verarbeitet hat, kann er das in eine PDF-Datei konvertierte Dokument auswählen. Dadurch wird sichergestellt, dass der behandelte Teil nicht sichtbar ist, wenn das Dokument zur Präsentation exportiert wird. Weitere Informationen finden Sie unter [Überprüfen von Daten in Evidence](review-data-in-evidence.md). |
|Elemente aus ursprünglichen Speicherorten löschen | Dieser Auftrag wird ausgelöst, wenn ein Benutzer Post Fach-und Websiteelemente in einem Beweissatz auswählt und dann im Menü **Aktion** auf **Elemente aus ursprünglichen Speicherorten löschen** klickt, um Sie zu löschen. Dieser Auftrag verfolgt den Fortschritt des weichen Löschens der ausgewählten Elemente von den ursprünglichen Inhaltsspeicherorten. Weitere Informationen finden Sie unter [Löschen von Elementen aus dem ursprünglichen Speicherort](delete-items-from-original-locations.md).|
|Schätzen von Suchergebnissen | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), durchsucht das Such Tool den Index nach Elementen, die mit der Suchabfrage übereinstimmen, und bereitet eine Schätzung vor, die die Anzahl und die Gesamtgröße aller Elemente durch die Suche sowie die Anzahl der Datenquellen enthält. Sea rched.  Weitere Informationen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md). | 
|Vorbereiten von Daten für den Export | Ein Benutzer exportiert Dokumente aus einem Evidence-Datensatz. Wenn der Exportvorgang abgeschlossen ist, können Sie die exportierten Daten auf einen lokalen Computer herunterladen. Weitere Informationen finden Sie unter [Exportieren von Daten aus einer Untersuchung](export-data.md). | 
|Vorbereiten der Fehlerbehebung |Wenn ein Benutzer eine Datei auswählt und eine Fehlerkorrektur in der Fehleransicht auf der Registerkarte **Verarbeitung** einer Untersuchung erstellt, besteht der erste Schritt im Prozess darin, die Datei mit dem Verarbeitungsfehler an einen Azure-Speicherort in der Microsoft-Cloud hochzuladen. Dieser Auftrag verfolgt den Fortschritt des Upload-Prozesses. Weitere Informationen zum Fehlerkorrektur-Workflow finden Sie unter [Fehlerbehebung bei der Verarbeitung von Daten für eine Untersuchung](error-remediation.md).| 
|Vorbereiten der Suchvorschau | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), bereitet das Such Tool eine Beispiel Teilmenge von Elementen vor, die mit der Suchabfrage übereinstimmen, die in der Vorschau angezeigt werden kann. Die Vorschau der Suchergebnisse kann Ihnen helfen, die Effektivität der Suche zu ermitteln.  Weitere Informationen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md). | 
|Erneutes Indizieren von Daten von interessanten Personen | Wenn Sie eine Person von Interesse zu einer Untersuchung hinzufügen, werden alle teilweise indizierten Elemente in der Person von Interesse ausgewählte Datenquellen durch einen Prozess namens *Erweiterte Indizierung*neu indiziert. Dieser Auftrag wird auch ausgelöst, wenn Sie auf der Registerkarte **Verarbeitung** einer Untersuchung auf **Indexansicht aktualisieren** klicken. Weitere Informationen finden Sie unter [Erweiterte Indizierung von Daten für eine Untersuchung](index-data-people-of-interest.md).
|Durchführen von Analysen | Ein Benutzer analysiert Daten in einem Beweissatz, indem er Analysetools wie etwa doppelte Erkennung, e-Mail-Threading Analyse und Design Analyse ausführt. Weitere Informationen finden Sie unter [Ausführen von Analysen, um schneller zu untersuchen](run-analytics-to-investigate-faster.md). | 
|Markieren von Dokumenten | Dieser Auftrag wird ausgelöst, wenn ein Benutzer beim Überprüfen von Dokumenten in einem Beweismittel im **taggingbereich auf "** **Tagging-Auftrag starten** " klickt. Ein Benutzer kann diesen Auftrag starten, nachdem er Dokumente in einem Beweissatz markiert und diese dann im Dokument Panel anzeigen massenhaft ausgewählt hat. Weitere Informationen finden Sie unter [Tag Documents in Evidence](tag-documents.md). | 
|||

## <a name="job-status"></a>Auftragsstatus

In der folgenden Tabelle werden die unterschiedlichen Statuszustände für Aufträge beschrieben.

| Status           | Beschreibung     |
| :----------------- | :----------     |
| Übermittelt | Ein neuer Auftrag wurde erstellt.  Das Datum und die Uhrzeit, zu denen der Auftrag übermittelt wurde, werden in der Spalte **erstellt** auf der Registerkarte **Aufträge** angezeigt. |
| Übermittlung fehlgeschlagen | Fehler bei der Auftragsübermittlung.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut auszuführen. |
| In Arbeit | Der Auftrag wird ausgeführt. Sie können den Status des Auftrags auf der Registerkarte **Aufträge** überwachen. |
| Erfolgreiche | Der Auftrag wurde erfolgreich abgeschlossen. Das Datum und die Uhrzeit, zu der der Auftrag abgeschlossen wurde, werden auf der Registerkarte **Aufträge** in der Spalte **abgeschlossen** angezeigt. |
| Teilweise erfolgreich | Der Auftrag war teilweise erfolgreich. |
| Failed | Der Auftrag ist fehlgeschlagen.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut auszuführen. Wenn der Auftrag ein zweites Mal fehlschlägt, sollten Sie sich an den Microsoft-Support wenden und die Supportinformationen aus dem Auftrag bereitstellen. |
|||
