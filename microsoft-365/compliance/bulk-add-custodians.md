---
title: Massenhafte Hinzufügen von Depot Betreuern zu einem erweiterten eDiscovery-Fall
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
ROBOTS: NOINDEX, NOFOLLOW
description: Verwenden Sie das Tool Bulk-Add, um schnell mehrere Verwalter und die zugehörigen Datenquellen zu einem Fall in Advanced eDiscovery hinzuzufügen.
ms.openlocfilehash: ab9626be01814fa95a959141433b431df9bf7724
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024665"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a>Massenhafte Hinzufügen von Depot Betreuern zu einem erweiterten eDiscovery-Fall

Für erweiterte eDiscovery-Fälle, in denen viele depotverwalter involviert sind, können Sie mehrere Verwalter gleichzeitig durch eine CSV-Datei importieren, die alle Informationen enthält, die erforderlich sind, um Sie zu einem Fall hinzuzufügen.

## <a name="bulk-add-custodians"></a>Massen-Hinzufügen von Depot Betreuern

1. Geben Sie Case ein, und navigieren Sie zur Registerkarte **Quellen** .

2. Klicken Sie auf **depotverwalter importieren** .

3. Klicken Sie auf der Seite Flyout auf **leere Vorlage herunterladen** , um eine CSV-Depot Vorlagendatei herunterzuladen.

4. Fügen Sie die Informationen zum Freiheitsentzug der CSV-Datei hinzu, und speichern Sie Sie auf dem lokalen Computer. Im nächsten Abschnitt finden Sie Informationen zu den Eigenschaften in der CSV-Datei.

5. Klicken Sie auf der Registerkarte **Quellen** erneut auf **Verwalter importieren** .

6. Klicken Sie auf der Seite Flyout auf **Durchsuchen** , und laden Sie die CSV-Datei hoch.

   Nachdem die CSV-Datei hochgeladen wurde, wird ein BulkAddCustodian-Auftrag erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die depotverwalter und die zugehörigen Datenquellen und fügt Sie dann der Registerkarte **Verwalter** auf der Seite **Quellen** der Anfrage hinzu.

## <a name="custodian-csv-file"></a>Depot-CSV-Datei

Nachdem Sie die CSV-Vorlage heruntergeladen haben, können Sie in jeder Zeile Verwalter und deren Datenquelle hinzufügen. Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern.

| Spaltenname|Beschreibung|
|:------- |:------------------------------------------------------------|
|**Depot Kontakt**     | UPN-e-Mail der Depotbank. Beispiel: Sarad@onmicrosoft.contoso.com           |
|**Exchange aktiviert** | TRUE/false-Wert, ob depotverwalter Postfach hinzugefügt werden soll.      |
|**OneDrive aktiviert** | TRUE/false-Wert, ob das OneDrive für Unternehmen Konto des Verwalters hinzugefügt werden soll. |
|**Ist OnHold**        | TRUE/false-Wert, ob depotverwalter in den Haltebereich platziert werden soll.       |
|**Workload1-Typ**         | Zeichenfolgenwert, der den Typ der Datenquelle angibt, die der Depotbank zugeordnet werden soll. <br />Mögliche Werte sind: <br />ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Workload1-Speicherort**     | Je nach Arbeits Auslastungs wäre dies der Datenspeicherort Ihrer Arbeitsauslastung (beispielsweise die e-Mail-Adresse eines Exchange-Postfachs oder die URL für eine SharePoint-Website). |
|||

Hier ist ein Beispiel für eine CSV-Datei mit Depotinformationen:  

| ContactEmail      | Exchange aktiviert | OneDrive aktiviert | Ist OnHold | Workload1-Typ | Workload1-Speicherort             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Depotbank und Datenquellen Überprüfung

Wenn Sie die Depot-CSV-Datei hochladen, führt Advanced eDiscovery folgende Schritte aus:

1. Überprüft die depotverwalter und deren Datenquellen. 

2. Indiziert alle Datenquellen für jede Depotstelle und platziert Sie in der Warteschleife (wenn die Eigenschaft ist OnHold auf true festgelegt ist).

### <a name="custodian-validation"></a>Depot Überprüfung

Derzeit wird nur das Importieren von Depot Inhabern unterstützt, die sich in Azure Active Directory (AAD) befinden.

Mithilfe des UPN-Werts in der Spalte **Kontakt-e-Mail** in der CSV-Datei validieren und finden Sie Verwalter. Überprüfte Verwalter werden automatisch dem Fall hinzugefügt und auf der Registerkarte **Depot** auf der Seite **Quellen** der Anfrage aufgeführt. Wenn eine Depotstelle nicht überprüft werden kann, werden Sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in der Anfrage auf der Registerkarte **Aufträge** aufgeführt ist. Nicht validierte depotverwalter werden dem Fall nicht hinzugefügt.

### <a name="data-source-validation"></a>Datenquellen Überprüfung

Nachdem die Verwalter überprüft und dem Fall hinzugefügt wurden, wird jede Datenquelle validiert, die einer Depotbank zugeordnet ist. Wenn keine Datenquelle für eine Depotstelle gefunden werden kann, wird der Wert, der **nicht überprüft** wurde, in der Spalte **validiert** auf der Registerkarte **Depot** für diese Depotbank angezeigt.

### <a name="remediating-unvalidated-data-sources"></a>Remediation nicht validierter Datenquellen

So beheben Sie Verwalter mit nicht validierten Datenquellen: 

1. Wählen Sie auf der Registerkarte **depotverwalter** eine nicht validierte Depotbank aus.

2. Führen Sie auf der Seite depotverwalter einen Bildlauf zum Abschnitt **Datenquellen** durch, um die Datenquellen anzuzeigen, die der Depotbank zugeordnet sind. Es werden sowohl validierte als auch nicht validierte Datenquellen aufgeführt.

3. Klicken Sie im Abschnitt **Datenquellen** auf **Bearbeiten**.

4. Entfernen Sie auf der Seite **Speicherorte auswählen** eine nicht validierte Datenquelle.

5. Klicken Sie auf der Seite **weitere Speicherorte auswählen** auf **Aktualisieren** , um zusätzliche Datenquellen für eine Depotstelle hinzuzufügen.
