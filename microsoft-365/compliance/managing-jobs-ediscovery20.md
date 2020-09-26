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
description: Erweiterte eDiscovery-Aufträge unterstützen Sie beim Nachverfolgen des Status von langwierigen Prozessen im Zusammenhang mit der Ausführung verschiedener erweiterter eDiscovery-Aufgaben.
ms.openlocfilehash: d41ac3572c462b85ff8f0bac0cc7205a5c012ce9
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285169"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Verwalten von Aufträgen in Advanced eDiscovery

Im folgenden finden Sie eine Liste der Aufträge (in der Regel langwierige Prozesse), die auf der Registerkarte **Aufträge** eines Falls in Advanced eDiscovery verfolgt werden. Diese Aufträge werden durch Benutzeraktionen bei der Verwendung und Verwaltung von Fällen ausgelöst.

| Auftragstyp           | Beschreibung     |
| :----------------- | :----------     |
|Hinzufügen von Daten zu einem Überprüfungs Satzes | Ein Benutzer fügt die Ergebnisse einer Suche zu einem Überprüfungs Satzes hinzu. Dieser Auftrag besteht aus zwei untergeordneten Aufträgen: </br>• **GatheringItems** – eine Liste mit Elementen, die mit der Suchabfrage übereinstimmen (und der Microsoft 365-Datenquelle, in der Sie sich befinden) wird generiert. </br>• **Einnahme & Indizierung** – die Elemente, die mit der Suchabfrage übereinstimmen, werden in einen Azure-Speicherort (in einem Prozess, der als " *Einnahme*" bezeichnet wird) kopiert, und dann werden diese Elemente im Azure-Speicherplatz neu indiziert. Dieser neue Index wird beim Abfragen und Analysieren von Elementen in dem DataSet verwendet. </br></br>Weitere Informationen finden Sie unter [Hinzufügen von Suchergebnissen zu einer Überprüfungsgruppe](add-data-to-review-set.md). |
|Hinzufügen von Daten zu einem anderen Überprüfungs Satzes | Ein Benutzer fügt in demselben Fall Dokumente aus einem Überprüfungs Satzes zu einem anderen Überprüfungs Sätze hinzu. Weitere Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungs Sätze aus einem anderen Überprüfungs Sätze](add-data-to-review-set-from-another-review-set.md).|
|Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes | Ein Benutzer lädt nicht-Microsoft 365-Daten in einen Überprüfungs-Datensatz hoch. Die Daten werden auch während dieses Prozesses indiziert. Beispielsweise werden Dateien von einem lokalen Dateiserver oder einem Clientcomputer in einen Überprüfungs-Datensatz hochgeladen. Weitere Informationen finden Sie unter [Laden von nicht-Microsoft 365-Daten in einen Überprüfungs Satzes](load-non-office365-data.md).| 
|Hinzufügen von wiederherzustellenden Daten zu einem Überprüfungs Satzes | Daten mit Verarbeitungsfehlern werden wiederhergestellt und in einen Überprüfungs Satz zurückgeladen. Weitere Informationen finden Sie unter:</br>• [Fehlerkorrektur bei der Verarbeitung von Daten](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Fehlerbehebung für einzelne Elemente](single-item-error-remediation.md)| 
|Vergleichen von Lastsätzen | Ein Benutzer prüft die Unterschiede zwischen verschiedenen Lastsätzen in einem Überprüfungs Satz. Ein Ladesatz ist eine Instanz beim Hinzufügen von Daten zu einem Prüfdateisatz. Wenn Sie beispielsweise die Ergebnisse von zwei unterschiedlichen Suchvorgängen zu demselben Überprüfungs Sätzen hinzufügen, würde jeder einen Lastsatz darstellen. Weitere Informationen finden Sie unter [Manage Last Sets](manage-load-sets.md). |
|Wiederherstellung von Unterhaltungen|Wenn ein Benutzer einer Konversations Überprüfungsgruppe die Ergebnisse einer Suche hinzufügt, werden Sofortnachrichtenunterhaltungen (auch als *Thread Unterhaltung*bezeichnet) in Diensten wie Microsoft Teams in einer PDF-Datei rekonstruiert. Dieser Auftrag wird auch ausgelöst, wenn ein Benutzer auf **Aktion klickt > unter Haltungs-PDFs** in einem Überprüfungs Satzes zu erstellen. Weitere Informationen finden Sie unter [Review Conversations in Advanced eDiscovery](conversation-review-sets.md).
|Konvertieren von behandelten Dokumenten in PDF|Nachdem ein Benutzer ein Dokument in einem Überprüfungs Satz kommentiert und einen Teil davon verarbeitet hat, kann er die Konvertierung des Dokuments in eine PDF-Datei auswählen. Dadurch wird sichergestellt, dass der behandelte Teil nicht sichtbar ist, wenn das Dokument zur Präsentation exportiert wird. Weitere Informationen finden Sie unter [View Documents in a Review Sets](annotating-and-redacting-documents.md). |
|Schätzen von Suchergebnissen | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), durchsucht das Such Tool den Index nach Elementen, die mit der Suchabfrage übereinstimmen, und bereitet eine Schätzung vor, die die Anzahl und die Gesamtgröße aller Elemente durch die Suche sowie die Anzahl der durchsuchten Datenquellen enthält.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md). | 
|Vorbereiten von Daten für den Export | Ein Benutzer exportiert Dokumente aus einem Überprüfungs Satzes. Wenn der Exportvorgang abgeschlossen ist, können Sie die exportierten Daten auf einen lokalen Computer herunterladen. Weitere Informationen finden Sie unter [Export Case Data](exporting-data-ediscover20.md). | 
|Vorbereiten der Fehlerbehebung |Wenn ein Benutzer eine Datei auswählt und in der Fehleransicht auf der Registerkarte **Verarbeitung** eines Falls eine neue Fehlerkorrektur erstellt, besteht der erste Schritt im Prozess darin, die Datei mit dem Verarbeitungsfehler an einen Azure-Speicherort in der Microsoft-Cloud hochzuladen. Dieser Auftrag verfolgt den Fortschritt des Upload-Prozesses. Weitere Informationen zum Fehlerkorrektur-Workflow finden Sie unter [Fehlerbehebung bei der Verarbeitung von Daten](error-remediation.md). | 
|Vorbereiten der Suchvorschau | Nachdem ein Benutzer eine neue Suche erstellt und ausgeführt hat (oder eine vorhandene Suche erneut ausführt), bereitet das Such Tool eine Beispiel Teilmenge von Elementen vor, die mit der Suchabfrage übereinstimmen, die in der Vorschau angezeigt werden kann. Die Vorschau der Suchergebnisse hilft Ihnen bei der Ermittlung der Effektivität der Suche.  Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Erneutes Indizieren von Depotdaten | Wenn Sie eine Depotbank zu einem Fall hinzufügen, werden alle teilweise indizierten Elemente in den ausgewählten Datenquellen der Depotbank durch einen Prozess mit dem Namen *Erweiterte Indizierung*neu indiziert. Dieser Auftrag wird auch ausgelöst, wenn Sie auf der Registerkarte **Verarbeitung** eines Falls auf **Index aktualisieren** klicken, und wenn Sie den Index für eine bestimmte Depotbank auf der Seite Depot Eigenschaften-Flyout aktualisieren. Weitere Informationen finden Sie unter [Erweiterte Indizierung von Depotdaten](indexing-custodian-data.md).
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
| Teilweise erfolgreich | Der Auftrag war teilweise erfolgreich. Dieser Status wird in der Regel zurückgegeben, wenn der Auftrag in einigen der Depotbank-Datenquellen keine teilweise indizierten Daten (auch nicht indizierte *Daten*genannt) gefunden hat.  |
| Fehlgeschlagen | Der Auftrag ist fehlgeschlagen.  Sie sollten versuchen, die Aktion, die den Auftrag ausgelöst hat, erneut auszuführen. Wenn der Auftrag ein zweites Mal fehlschlägt, sollten Sie sich an den Microsoft-Support wenden und die Supportinformationen aus dem Auftrag bereitstellen. |
|||
