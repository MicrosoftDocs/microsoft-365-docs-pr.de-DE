---
title: Importieren von Verwahrern in einen Advanced eDiscovery-Fall
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
description: Verwenden Sie das Importtool d, um einem Fall in Advanced eDiscovery schnell mehrere Verwahrer und die zugehörigen Datenquellen hinzuzufügen.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421612"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importieren von Verwahrern in einen Advanced eDiscovery-Fall

Bei Advanced eDiscovery-Fällen mit vielen Verwahrern können Sie mehrere Verwahrer gleichzeitig importieren, indem Sie eine CSV-Datei verwenden, die die erforderlichen Informationen zum Hinzufügen zu einem Fall enthält.

## <a name="import-custodians"></a>Import custodians

1. Öffnen Sie den Fall Advanced eDiscovery, und wählen Sie die Registerkarte **Datenquellen** aus.

2. Klicken **Sie auf Datenquelle hinzufügen** Import  >  **custodians**.

3. Klicken Sie auf der Flyoutseite **Custodians** importieren auf **Eine leere** Vorlage herunterladen, um eine CSV-Datei für die Verwahrervorlage herunterzuladen.

   ![Herunterladen einer CSV-Vorlage von der Flyoutseite " Custodians importieren"](../media/ImportCustodians1.png)

4. Fügen Sie die Verwahrungsinformationen zur CSV-Datei hinzu, und speichern Sie sie auf Ihrem lokalen Computer. Informationen zu den erforderlichen Eigenschaften in der CSV-Datei finden Sie im Abschnitt [Custodian CSV](#custodian-csv-file) file.

5. Nachdem Sie die CSV-Datei mit den Custodian-Informationen vorbereitet haben, wechseln Sie zur Registerkarte Datenquellen, und klicken Sie erneut auf Datenquelle    >   importieren.

6. Klicken Sie auf der Flyoutseite **Custodians** importieren auf **Durchsuchen,** und laden Sie dann die CSV-Datei hoch, die die Custodian-Informationen enthält.

   Nachdem die CSV-Datei hochgeladen wurde, wird ein Auftrag mit dem Namen **BulkAddCustodian** erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die Verwahrer und die zugehörigen  Datenquellen und fügt sie dann der Seite Datenquellen des Falls hinzu.

## <a name="custodian-csv-file"></a>Verwahrer-CSV-Datei

Nachdem Sie die CSV- Custodian-Vorlage heruntergeladen haben, können Sie Custodians und deren Datenquelle in jeder Zeile hinzufügen. Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern. Verwenden Sie die Spalten Arbeitsauslastungstyp und Arbeitsauslastungsspeicherort, um anderen Datenquellen einem Verwahrer zuzuordnen.

| Spaltenname|Beschreibung|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |Die UPN-E-Mail-Adresse des Custodians. Beispiel: sarad@contoso.onmicrosoft.com.           |
|**Exchange-aktiviert** | TRUE/FALSE-Wert, der das Postfach des Custodians enthält oder nicht.      |
|**OneDrive-aktiviert** | TRUE/FALSE-Wert, der das OneDrive for #A0 des Verwahrers enthalten soll oder nicht. |
|**Is OnHold**        | TRUE/FALSE-Wert, um anzugeben, ob die Custodian-Datenquellen in der Warteschleife gespeichert werden. <sup>1</sup>     |
|**Typ "Workload1"**         |Zeichenfolgenwert, der den Typ der Datenquelle angibt, die dem Custodian zugeordnet werden soll. Mögliche Werte sind: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1-Speicherort**     | Je nach Arbeitsauslastungstyp wäre dies der Speicherort der Datenquelle. Beispielsweise die E-Mail-Adresse für ein Exchange-Postfach oder die URL für eine SharePoint-Website. |
|||

> [!NOTE]
> <sup>1</sup> Sie können maximal 1.000 Postfächer und 100 Websites mithilfe des Custodian Import Process und der CSV-Datei in der Warteschleife platzieren. Sie können diesen Prozess verwenden, um einem Fall mehr als 1.000 Custodians hinzuzufügen, aber die Haltebeschränkungen gelten weiterhin. Weitere Informationen zu Haltebeschränkungen finden Sie [unter Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).

Hier ist ein Beispiel für eine CSV-Datei mit Custodian-Informationen:<br/><br/>

|Custodian contactEmail      | Exchange-aktiviert | OneDrive-aktiviert | Is OnHold | Typ "Workload1" | Workload1-Speicherort             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Verwahrer- und Datenquellenüberprüfung

Nachdem Sie die Custodian-CSV-Datei hochgeladen haben, führt Advanced eDiscovery die folgenden Schritte aus:

1. Überprüft die Verwahrer und ihre Datenquellen.

2. Indiziert alle Datenquellen für jeden Custodian und platziert sie in der Warteschleife (wenn die **Is OnHold-Eigenschaft** in der CSV-Datei auf TRUE festgelegt ist).

### <a name="custodian-validation"></a>Verwahrerüberprüfung

Derzeit unterstützen wir nur das Importieren von Verwahrern, die im Azure Active Directory (Azure AD) Ihrer Organisation enthalten sind.

Das Custodian-Importtool sucht und überprüft Custodians mithilfe des UPN-Werts in der Spalte **Custodian contactEmail** in der CSV-Datei. Verwahrer, die überprüft werden, werden dem Fall automatisch hinzugefügt und auf der Registerkarte **Datenquellen** des Falls aufgeführt. Wenn ein Verwahrer nicht überprüft werden kann, werden sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in diesem Fall auf der Registerkarte Aufträge aufgeführt ist.  Nichtvalidierte Verwahrer werden dem Fall nicht hinzugefügt oder auf der Registerkarte **Datenquellen** aufgeführt.

### <a name="data-source-validation"></a>Datenquellenüberprüfung

Nachdem Custodians überprüft und dem Fall hinzugefügt wurden, werden jedes primäre Postfach und jedes OneDrive-Konto hinzugefügt, das einem Custodian zugeordnet ist.

Wenn jedoch eine der anderen Datenquellen (z. B. SharePoint-Websites, Microsoft Teams, Microsoft 365-Gruppen oder Yammer-Gruppen), die einem Verwahrer  zugeordnet sind, nicht gefunden werden kann, wird keine  dieser Quellen dem Verwahrer zugewiesen, und der Wert Nicht überprüft wird in der Spalte **Status** neben dem Verwahrer auf der Registerkarte Datenquellen angezeigt.

So fügen Sie überprüfte Datenquellen für einen Verwahrer hinzu:

1. Wählen Sie **auf der** Registerkarte Datenquellen einen Verwahrer aus, der Datenquellen enthält, die nicht überprüft wurden.

2. Scrollen Sie auf der Flyoutseite des Verwahrers zum Abschnitt Verwahrungsspeicherorte, um sowohl überprüfte als auch nicht validierte Datenquellen zu sehen, die dem Verwahrer zugeordnet sind. 

3. Klicken **Sie oben** auf der Flyoutseite auf Bearbeiten, um ungültige Datenquellen zu entfernen oder neue hinzuzufügen.

4. Nachdem Sie nicht validierte Datenquellen entfernt oder eine neue hinzugefügt haben, wird der Wert **Active** in der Spalte **Status** für den Custodian auf der Registerkarte **Datenquellen** angezeigt. Um Quellen hinzuzufügen, die zuvor als ungültig betrachtet wurden, führen Sie die unten aufgeführten Korrekturschritte aus, um sie manuell einem Custodian hinzuzufügen.

### <a name="remediating-invalid-data-sources"></a>Behebung ungültiger Datenquellen

So fügen Sie eine zuvor ungültige Datenquelle manuell hinzu und ordnen sie zu:

1. Wählen Sie **auf der Registerkarte** Datenquellen einen Verwahrer aus, um eine zuvor ungültige Datenquelle manuell hinzuzufügen und zuzuordnen.

2. Klicken **Sie oben** auf der Flyoutseite auf Bearbeiten, um Postfächer, Websites, Teams oder Yammer dem Custodian zuzuordnen. Klicken Sie dazu **neben** dem entsprechenden Datentyp auf Bearbeiten.

3. Klicken **Sie auf Weiter,** **um** die Einstellungsseite für die Halteeinstellungen zu anzeigen und die Halteeinstellung für die hinzugefügten Datenquellen zu konfigurieren.

4. Klicken **Sie auf Weiter,** um die Seite **Custodians** überprüfen zu zeigen, und klicken Sie dann auf **Übermitteln,** um Ihre Änderungen zu speichern.
