---
title: Verwalten von Aufträgen in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: c0dd3b19f1fb666e07f70c36db05ed520093bfac
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081574"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Verwalten von Aufträgen in Advanced eDiscovery

Im folgenden finden Sie eine Liste der Aufträge (in der Regel langwierige Prozesse), die auf der Registerkarte **Aufträge** eines Falls in Advanced eDiscovery verfolgt werden. Diese Aufträge werden durch Benutzeraktionen bei der Verwendung und Verwaltung von Fällen ausgelöst.

| Auftragstyp           | Beschreibung     |
| :----------------- | :----------     |
|Hinzufügen von Daten zu einem Überprüfungs Satzes | Ein Benutzer fügt die Ergebnisse einer Suche zu einem Überprüfungs Satzes hinzu. Dieser Auftrag besteht aus zwei untergeordneten Aufträgen: </br> </br>• **GatheringItems** – eine Liste mit Elementen, die mit der Suchabfrage übereinstimmen (und der Office 365 Datenquelle, in der Sie sich befinden) wird generiert. </br>• **Einnahme #a0 Indizierung** – die Elemente, die mit der Suchabfrage übereinstimmen, werden in einen Azure-Speicherort (in einem Prozess namens " *Ingestion*") kopiert, und anschließend werden diese Elemente im Azure-Speicherort neu indiziert. Dieser neue Index wird beim Abfragen und Analysieren von Elementen in dem DataSet verwendet. </br></br>Weitere Informationen finden Sie unter [Hinzufügen von Suchergebnissen zu einer Überprüfungsgruppe](add-data-to-review-set.md). |
|Hinzufügen von Daten zu einem anderen Überprüfungs Satzes | Ein Benutzer fügt in demselben Fall Dokumente aus einem Überprüfungs Satzes zu einem anderen Überprüfungs Sätze hinzu. Weitere Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungs Sätze aus einem anderen Überprüfungs Sätze](add-data-to-review-set-from-another-review-set.md).|
|Hinzufügen von nicht Office 365 Daten zu einem Überprüfungs Satzes | Ein Benutzer lädt nicht Office 365E Daten in einen Überprüfungs-Datensatz hoch. Die Daten werden auch während dieses Prozesses indiziert. Beispielsweise werden Dateien von einem lokalen Dateiserver oder einem Clientcomputer in einen Überprüfungs-Datensatz hochgeladen. Weitere Informationen finden Sie unter [Laden von nicht Office 365 Daten in einen Überprüfungs Sätze](load-non-office365-data.md).| 
|Hinzufügen von wiederherzustellenden Daten zu einem Überprüfungs Satzes | Daten mit Verarbeitungsfehlern werden wiederhergestellt und in einen Überprüfungs Satz zurückgeladen. Weitere Informationen finden Sie unter [Fehlerkorrektur bei der Verarbeitung von Daten](error-remediation.md). | 
|Vergleichen von Lastsätzen | Ein Benutzer prüft die Unterschiede zwischen verschiedenen Lastsätzen in einem Überprüfungs Satz. Bei einem Lastsatz handelt es sich um eine Instanz des Hinzufügens von Daten zu einem Überprüfungs Satzes. Wenn Sie beispielsweise die Ergebnisse von zwei unterschiedlichen Suchvorgängen zu demselben Überprüfungs Sätzen hinzufügen, würde jeder einen Lastsatz darstellen. Weitere Informationen finden Sie unter [Manage Last Sets](manage-load-sets.md). |
|Konvertieren von behandelten Dokumenten in PDF|Nachdem ein Benutzer ein Dokument in einem Überprüfungs Satz kommentiert und einen Teil davon verarbeitet hat, kann er die Konvertierung des Dokuments in eine PDF-Datei auswählen. Dadurch wird sichergestellt, dass der behandelte Teil nicht sichtbar ist, wenn das Dokument zur Präsentation exportiert wird. Weitere Informationen finden Sie unter [View Documents in a Review Sets](annotating-and-redacting-documents.md). |
|Schätzen von Suchergebnissen | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), durchsucht das Such Tool den Index nach Elementen, die mit der Suchabfrage übereinstimmen, und bereitet eine Schätzung vor, die die Anzahl und Gesamtgröße aller Elemente durch die Suche sowie die Anzahl der Datenquellen anbraten enthält. Ched.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md). | 
|Vorbereiten von Daten für den Export | Ein Benutzer exportiert Dokumente aus einer Überprüfungsgruppe. Wenn der Exportvorgang abgeschlossen ist, können Sie die exportierten Daten auf einen lokalen Computer herunterladen. Weitere Informationen finden Sie unter [Export Case Data](exporting-data-ediscover20.md). | 
|Vorbereiten der Fehlerbehebung |Wenn ein Benutzer eine Datei auswählt und in der Fehleransicht auf der Registerkarte **Verarbeitung** eines Falls eine neue Fehlerkorrektur erstellt, besteht der erste Schritt im Prozess darin, die Datei mit dem Verarbeitungsfehler an einen Azure-Speicherort in der Microsoft-Cloud hochzuladen. Dieser Auftrag verfolgt den Fortschritt des Upload-Prozesses. Weitere Informationen zum Fehlerkorrektur-Workflow finden Sie unter [Fehlerbehebung bei der Verarbeitung von Daten](error-remediation.md). | 
|Vorbereiten der Suchvorschau | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), bereitet das Such Tool eine Beispiel Teilmenge von Elementen vor, die mit der Suchabfrage übereinstimmen, die in der Vorschau angezeigt werden kann. Die Vorschau der Suchergebnisse hilft Ihnen bei der Ermittlung der Effektivität der Suche.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Erneutes Indizieren von Depotdaten | Wenn Sie eine Depotbank zu einem Fall hinzufügen, werden alle teilweise indizierten Elemente in den ausgewählten Datenquellen der Depotbank durch einen Prozess mit dem Namen *Advanced Indexing*erneut indiziert. Dieser Auftrag wird auch ausgelöst, wenn Sie in der Indexansicht auf der Registerkarte **Verarbeitung** eines Falls auf **Index aktualisieren** klicken. Weitere Informationen finden Sie unter [Erweiterte Indizierung von Depotdaten](indexing-custodian-data.md).
|Durchführen von Analysen | Ein Benutzer analysiert Daten in einem Überprüfungs, indem er erweiterte eDiscovery Analytics-Tools ausführt, beispielsweise nahezu doppelte Erkennung, e-Mail-Threading-Analyse und Design Analyse. Weitere Informationen finden Sie unter [Analysieren von Daten in einem Überprüfungs Satzes](analyzing-data-in-review-set.md). | 
|Markieren von Dokumenten | Dieser Auftrag wird ausgelöst, wenn ein Benutzer beim Überprüfen von Dokumenten in einem Überprüfungs **Bereich im taggingfenster auf "** **Tagging-Auftrag starten** " klickt. Ein Benutzer kann diesen Auftrag nach dem Markieren von Dokumenten in einem Überprüfungs Satzes starten und dann im Dokument Panel anzeigen. Weitere Informationen finden Sie unter [Tag Documents in a Review Sets](tagging-documents.md). | 
|||


## <a name="job-status"></a>Auftragsstatus

In der folgenden Tabelle werden die unterschiedlichen Statuszustände für Aufträge beschrieben.

| Status           | Beschreibung     |
| :----------------- | :----------     |
| Übermittelt | Ein neuer Auftrag wurde erstellt.  Das Datum und die Uhrzeit, zu denen der Auftrag übermittelt wurde, werden in der Spalte **erstellt** auf der Registerkarte **Aufträge** angezeigt. |
| Übermittlung fehlgeschlagen | Fehler bei der Auftragsübermittlung.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut auszuführen. |
| In Arbeit | Der Auftrag wird ausgeführt, Sie können den Status des Auftrags auf der Registerkarte **Aufträge** überwachen. |
| Erfolgreiche | Der Auftrag wurde erfolgreich abgeschlossen. Das Datum und die Uhrzeit, zu der der Auftrag abgeschlossen wurde, werden auf der Registerkarte **Aufträge** in der Spalte **abgeschlossen** angezeigt. |
| Teilweise erfolgreich | Der Auftrag war teilweise erfolgreich. |
| Failed | Der Auftrag ist fehlgeschlagen.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut auszuführen. Wenn der Auftrag ein zweites Mal fehlschlägt, sollten Sie sich an den Microsoft-Support wenden und die Supportinformationen aus dem Auftrag bereitstellen. |
