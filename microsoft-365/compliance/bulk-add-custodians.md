---
title: Importieren von Depot Inhabern in einen erweiterten eDiscovery-Fall
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
description: Verwenden Sie das Import Tool DTO, um schnell mehrere Verwalter und die zugehörigen Datenquellen zu einem Fall in Advanced eDiscovery hinzuzufügen.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740302"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importieren von Depot Inhabern in einen erweiterten eDiscovery-Fall

Für erweiterte eDiscovery-Fälle, in denen viele depotverwalter involviert sind, können Sie mehrere Verwalter gleichzeitig importieren, indem Sie eine CSV-Datei verwenden, die die Informationen enthält, die erforderlich sind, um Sie zu einem Fall hinzuzufügen.

## <a name="import-custodians"></a>Import Verwalter

1. Öffnen Sie den erweiterten eDiscovery-Fall, und wählen Sie die Registerkarte **Datenquellen** aus.

2. Klicken Sie auf **Datenquellen**  >  -**Import Verwalter** hinzufügen.

3. Klicken Sie auf der Seite " **depotverwalter importieren** " auf **leere Vorlage herunterladen** , um eine Depot Vorlagen-CSV-Datei herunterzuladen.

   ![Herunterladen einer CSV-Vorlage aus der Flyout-Seite "Verwalter importieren"](../media/ImportCustodians1.png)

4. Fügen Sie die Informationen zum Freiheitsentzug der CSV-Datei hinzu, und speichern Sie Sie auf dem lokalen Computer. Im Abschnitt [Depot-CSV-Datei](#custodian-csv-file) finden Sie Informationen zu den erforderlichen Eigenschaften in der CSV-Datei.

5. Nachdem Sie die CSV-Datei mit den Depotinformationen vorbereitet haben, kehren Sie zur Registerkarte **Datenquellen** zurück, und klicken Sie erneut auf Datenquellen-   >  **Import Verwalter** hinzufügen.

6. Klicken Sie auf der Seite **depotverwalter importieren** auf **Durchsuchen** , und laden Sie dann die CSV-Datei hoch, die die Depotinformationen enthält.

   Nachdem die CSV-Datei hochgeladen wurde, wird ein Auftrag mit dem Namen **BulkAddCustodian** erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die Verwalter und die zugehörigen Datenquellen und fügt Sie dann zur Seite **Datenquellen** des Falls hinzu.

## <a name="custodian-csv-file"></a>Depot-CSV-Datei

Nachdem Sie die Vorlage CSV Depot heruntergeladen haben, können Sie in jeder Zeile Verwalter und deren Datenquelle hinzufügen. Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern. Verwenden Sie die Spalten Arbeits Auslastungs und Arbeits Auslastungs Speicherort, um einer Depotbank andere Datenquellen zuzuordnen.

| Spaltenname|Beschreibung|
|:------- |:------------------------------------------------------------|
|**Depot Kontakt**     |Die UPN-e-Mail-Adresse des Depotbank. Beispiel: Sarad@contoso.onmicrosoft.com.           |
|**Exchange aktiviert** | TRUE/false-Wert, der das Postfach des Depotinhabers einschließen oder nicht einschließen soll.      |
|**OneDrive aktiviert** | TRUE/false-Wert, der das OneDrive für Unternehmen Konto des Verwalters enthält oder nicht enthält. |
|**Ist OnHold**        | TRUE/false-Wert, der angibt, ob die Depotdaten Quellen aufbewahrt werden sollen.       |
|**Workload1-Typ**         |Zeichenfolgenwert, der den Typ der Datenquelle angibt, die der Depotbank zugeordnet werden soll. Mögliche Werte sind: <br/>- ExchangeMailbox<br/> -SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1-Speicherort**     | Je nach Arbeits Auslastungs ist dies der Speicherort der Datenquelle. Beispielsweise die e-Mail-Adresse für ein Exchange-Postfach oder die URL für eine SharePoint-Website. |
|||

Hier ist ein Beispiel für eine CSV-Datei mit Depotinformationen:<br/><br/>

|Depot Kontakt      | Exchange aktiviert | OneDrive aktiviert | Ist OnHold | Workload1-Typ | Workload1-Speicherort             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Depotbank und Datenquellen Überprüfung

Nachdem Sie die Depot-CSV-Datei hochgeladen haben, führt Advanced eDiscovery folgende Schritte aus:

1. Überprüft die depotverwalter und deren Datenquellen.

2. Indiziert alle Datenquellen für jede Depotbank und legt Sie in die Warteschleife (wenn die Eigenschaft **ist OnHold** in der CSV-Datei auf true festgelegt ist).

### <a name="custodian-validation"></a>Depot Überprüfung

Derzeit unterstützen wir nur das Importieren von Depot Betreuern, die in der Azure-Active Directory Ihrer Organisation (Azure AD) enthalten sind.

Das depotverwalter-Import Tool sucht und überprüft Verwalter mithilfe des UPN-Werts in der Spalte **Depot Kontakt** in der CSV-Datei. Überprüfte Verwalter werden automatisch der Anfrage hinzugefügt und auf der Registerkarte **Datenquellen** der Anfrage aufgeführt. Wenn eine Depotstelle nicht überprüft werden kann, werden Sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in der Anfrage auf der Registerkarte **Aufträge** aufgeführt ist. Nicht validierte depotverwalter werden dem Fall nicht hinzugefügt oder auf der Registerkarte **Datenquellen** aufgeführt.

### <a name="data-source-validation"></a>Datenquellen Überprüfung

Nachdem Verwalter überprüft und dem Fall hinzugefügt wurden, werden alle primären Postfächer und OneDrive-Konten hinzugefügt, die einer Depotbank zugeordnet sind.

Wenn jedoch eine der anderen Datenquellen (wie SharePoint-Websites, Microsoft Teams, Microsoft 365-Gruppen oder Jammer Gruppen), die einer Depotbank zugeordnet sind, nicht gefunden werden können, wird keine dieser Informationen der Depotbank zugewiesen, und der Wert, der **nicht validiert** wurde, wird in der Spalte **Status** neben der Depotbank auf der Registerkarte **Datenquellen** angezeigt.

So fügen Sie einer Depotbank validierte Datenquellen hinzu:

1. Wählen Sie auf der Registerkarte **Datenquellen** eine Depotbank aus, die nicht validierte Datenquellen enthält.

2. Führen Sie auf der Seite depotverwalter einen Bildlauf zum Abschnitt **Speicherorte** durch, um sowohl validierte als auch nicht validierte Datenquellen anzuzeigen, die der Depotbank zugeordnet sind.

3. Klicken Sie oben auf der Flyout-Seite auf **Bearbeiten** , um ungültige Datenquellen zu entfernen oder neue hinzuzufügen.

4. Nachdem Sie nicht validierte Datenquellen entfernt oder ein neues hinzugefügt haben, wird der Wert **aktiv** in der Spalte **Status** für die Depotbank auf der Registerkarte **Datenquellen** angezeigt. Zum Hinzufügen von Quellen, die zuvor als ungültig erschienen sind, führen Sie die folgenden korrekturschritte aus, um Sie manuell zu einer Depotbank hinzuzufügen.

### <a name="remediating-invalid-data-sources"></a>Remediation ungültige Datenquellen

Manuelles Hinzufügen und Zuordnen einer zuvor ungültigen Datenquelle:

1. Wählen Sie auf der Registerkarte **Datenquellen** eine Depotbank aus, um eine zuvor ungültige Datenquelle manuell hinzuzufügen und zuzuordnen.

2. Klicken Sie oben auf der Flyout-Seite auf **Bearbeiten** , um der Depotbank Postfächer, Websites, Teams oder Jammer Gruppen zuzuordnen. Klicken Sie dazu neben dem entsprechenden Datenspeicherort auf **Bearbeiten** .

3. Klicken Sie auf **weiter** , um die Seite **halte Einstellungen** anzuzeigen, und konfigurieren Sie die Einstellung halten für die Datenquellen, die Sie hinzugefügt haben.

4. Klicken Sie auf **weiter** , um die Seite **Verwalter überprüfen** anzuzeigen, und klicken Sie dann auf über **Mitteln** , um die Änderungen zu speichern.
