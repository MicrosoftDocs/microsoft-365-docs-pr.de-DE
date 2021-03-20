---
title: Beginn der Aufbewahrung bei Auftreten eines Ereignisses
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Normalerweise ein Bestandteil einer Datensatzverwaltungslösung. Sie können eine Aufbewahrungsbezeichnung so konfigurieren, dass der Aufbewahrungszeitraum basierend auf einem von Ihnen festgelegten Ereignis gestartet wird.
ms.openlocfilehash: 49fe330fa6844361a77caaebb0e6a411297ee643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907015"
---
# <a name="start-retention-when-an-event-occurs"></a>Beginn der Aufbewahrung bei Auftreten eines Ereignisses

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Wenn Sie Inhalte aufbewahren, basiert der Aufbewahrungszeitraum häufig auf dem Alter des Inhalts. Sie könnten beispielsweise Dokumente für sieben Jahre nach der Erstellung aufbewahren, und anschließend werden sie gelöscht. Wenn Sie jedoch [Aufbewahrungsbezeichnungen](retention.md#retention-labels) konfigurieren, können Sie auch einen Aufbewahrungszeitraum festlegen, der auf dem Auftreten eines bestimmten Ereignistyps basiert. Das Ereignis löst den Beginn des Aufbewahrungszeitraums aus, und auf alle Inhalte, denen eine Aufbewahrungsbezeichnung für diesen Ereignistyp zugewiesen wurde, werden die Aufbewahrungsaktionen angewendet.
  
Beispiele für die Verwendung der ereignisbasierten Aufbewahrung:
  
- **Mitarbeiter verlassen die Organisation** Angenommen, Mitarbeiterdatensätze müssen ab dem Zeitpunkt, an dem ein Angestellter das Unternehmen verlässt, 10 Jahre lang aufbewahrt werden. Nach 10 Jahren müssen alle Dokumente im Zusammenhang mit der Einstellung, Leistung und Kündigung dieses Angestellten gelöscht werden. Das Ereignis, das den Aufbewahrungszeitraum von 10 Jahren auslöst, ist die Beendigung des Beschäftigungsverhältnisses des Mitarbeiters bei der Organisation. 
    
- **Vertragsablauf** Angenommen, alle Datensätze im Zusammenhang mit Verträgen müssen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft. Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags. 
    
- **Produktlebensdauer** – Ihre Organisation hat möglicherweise Aufbewahrungspflichten, die sich auf das letzte Fertigungsdatum von Produkten für Inhalte wie technische Daten beziehen. In diesem Fall ist das Datum der letzte Fertigung das Ereignis, das den Aufbewahrungszeitraum auslöst. 
    
Die ereignisbasierte Aufbewahrung wird in der Regel im Rahmen eines Prozesses für die Datensatzverwaltung verwendet. Dies bedeutet:
  
- Aufbewahrungsbezeichnungen auf Basis von Ereignissen kennzeichnen in der Regel auch Inhalte als Datensatz (als Teil einer Lösung für die Datensatzverwaltung). Weitere Informationen finden Sie unter [Informationen zur Datensatzverwaltung](records-management.md).

- Ein Dokument, das als Datensatz deklariert wurde, dessen Ereignisauslöser jedoch noch nicht ausgelöst wurde, wird auf unbegrenzte Zeit beibehalten (Datensätze können nicht dauerhaft gelöscht werden), bis ein Ereignis den Aufbewahrungszeitraum des Dokuments auslöst.
    
- Aufbewahrungsbezeichnungen auf Basis von Ereignissen lösen in der Regel eine Löschungsprüfung am Ende des Aufbewahrungszeitraums aus, damit ein Datensatzverwalter den Inhalt manuell überprüfen und löschen kann. Weitere Informationen finden Sie unter [Entfernung von Inhalten](disposition.md).
    

Eine auf einem Ereignis basierende Aufbewahrungsbezeichnung weist die gleichen Funktionen wie jede Aufbewahrungsbezeichnung in Microsoft 365 auf. Weitere Informationen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Grundlegendes zur Beziehung zwischen Ereignistypen, Bezeichnungen, Ereignissen und Asset-IDs

Um die ereignisbasierte Aufbewahrung erfolgreich zu verwenden, müssen Sie die Beziehung zwischen Ereignistypen, Aufbewahrungsbezeichnungen, Ereignissen und Objekt-IDs verstehen, wie in den Diagrammen und der nachfolgenden Erklärung dargestellt: 
  
![Diagramm 1 von 2: Ereignistyp, Bezeichnungen, Ereignisse und Objekt-IDs](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramm 2 von 2: Ereignistyp, Bezeichnungen, Ereignisse und Objekt-IDs](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Sie erstellen Aufbewahrungsbezeichnungen für unterschiedliche Arten von Inhalten und ordnen diesen dann einen Ereignistyp zu. Aufbewahrungsbezeichnungen für verschiedene Arten von Produktdateien und Datensätzen werden beispielsweise einem Ereignistyp mit der Bezeichnung „Product Lifetime“ zugeordnet, da diese Datensätze ab dem Ende des Produktlebenszyklus für 10 Jahre aufbewahrt werden müssen.
    
2. Benutzer (in der Regel Datensatzverwalter) wenden diese Aufbewahrungsbezeichnungen auf Inhalte an, und geben (bei Dokumenten in SharePoint und OneDrive) eine Objekt-ID für jedes Element ein. In diesem Beispiel ist die Objekt-ID ein von der Organisation verwendeter Produktname oder -code. Dann wird den Datensätzen jedes Produkts eine Aufbewahrungsbezeichnung zugewiesen, und jeder Datensatz verfügt über eine Eigenschaft, die eine Objekt-ID enthält. Das Diagramm stellt **alle Inhalte** für alle Produktdatensätze in einer Organisation dar, wobei jedes Element die Objekt-ID des Produkts trägt, um dessen Datensatz es sich handelt. 
    
3. „Product Lifetime“ ist der Ereignistyp. Ein bestimmtes Produkt, das das Ende seines Lebenszyklus erreicht, ist ein Ereignis. Wenn ein Ereignis dieses Typs auftritt (in diesem Fall, wenn ein Produkt das Ende seiner Lebensdauer erreicht), erstellen Sie ein Ereignis, das Folgendes angibt:
    
   - Eine Asset-ID (für SharePoint- und OneDrive-Dokumente)
    
   - Schlüsselwörter (für Exchange-Elemente). In diesem Beispiel verwendet das Unternehmen einen Produktcode in Nachrichten, die Produktdatensätze enthalten, sodass das Schlüsselwort für Exchange-Elemente funktional der Objekt-ID für SharePoint- und OneDrive-Dokumente entspricht.
    
   - Das Datum, an dem das Ereignis aufgetreten ist. Dieses Datum wird als Beginn des Aufbewahrungszeitraums verwendet. Dieses Datum kann das aktuelle, ein vergangenes oder ein zukünftiges Datum sein.

4. Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps aufweisen und die angegebene Objekt-ID bzw. das angegebene Schlüsselwort enthalten. Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern. Bei allen rot eingekreisten Elementen im vorigen Diagramm wird der Aufbewahrungszeitraum durch dieses Ereignis ausgelöst. Mit anderen Worten, wenn dieses Produkt das Ende seiner Lebensdauer erreicht, löst dieses Ereignis den Aufbewahrungszeitraum für die Produktdatensätze aus.

Es ist wichtig zu verstehen, dass der Aufbewahrungszeitraum für **alle Inhalte** mit einer Bezeichnung dieses Ereignistyps durch das Ereignis ausgelöst wird, wenn Sie keine Objekt-ID oder Schlüsselwörter für ein Ereignis angeben. Dies bedeutet, dass im vorherigen Diagramm der Aufbewahrungszeitraum für alle Inhalte beginnen würde. Dies ist möglicherweise nicht, was Sie beabsichtigen.

Denken Sie schließlich daran, dass es zu jeder Aufbewahrungsbezeichnung eigene Aufbewahrungseinstellungen gibt. In diesem Beispiel ist für alle ein Zeitraum von 10 Jahren angegeben, aber es ist möglich, dass ein Ereignis Aufbewahrungsbezeichnungen mit unterschiedlichen Aufbewahrungszeiträumen auslöst.
  
## <a name="how-to-set-up-event-driven-retention"></a>So richten Sie die ereignisgesteuerte Aufbewahrung ein

Allgemeiner Workflow für die ereignisgesteuerte Aufbewahrung:
  
![Diagramm des Arbeitsablaufs zum Einrichten der ereignisgesteuerten Aufbewahrung](../media/event-based-retention-process.png)
  
> [!TIP]
> Unter [Verwenden von Aufbewahrungsbezeichnungen zur Verwaltung des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md) finden Sie ein detailliertes Szenario zur Verwendung von verwalteten Eigenschaften in SharePoint, um Aufbewahrungsbezeichnungen automatisch anzuwenden und die ereignisgesteuerte Aufbewahrung zu implementieren.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Schritt 1: Eine Bezeichnung erstellen, deren Aufbewahrungszeitraum auf einem Ereignis basiert

Folgen Sie zum Erstellen und Konfigurieren Ihrer Aufbewahrungsbezeichnung den Anweisungen unter [Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen](./create-apply-retention-labels.md#create-and-configure-retention-labels). Wählen Sie aber spezifisch für die ereignisbasierte Aufbewahrung auf der Seite **Aufbewahrungseinstellungen definieren** des Assistenten zum Erstellen von Aufbewahrungsbezeichnungen zuerst **Aufbewahrungszeitraum starten basierend auf**, und dann einen der Standardereignistypen aus der Dropdownliste aus. Sie können aber auch **Neuen Ereignistyp erstellen** auswählen, um einen eigenen zu erstellen:

![Erstellen eines neuen Ereignistyps für eine Aufbewahrungsbezeichnung](../media/SPRetention6.png)

Ein Ereignistyp ist einfach eine allgemeine Beschreibung eines Ereignisses, das Sie einer Aufbewahrungsbezeichnung zuordnen möchten.

Die Standardereignistypen weisen **(Ereignistyp**) nach ihrem Namen in der Dropdownliste auf, um die Identifizierung zu vereinfachen. Sie können einen Ereignistyp auch über die Registerkarte **Datensatzverwaltung** > **Ereignisse** > **Ereignistypen verwalten** anzeigen und erstellen.

Für die ereignisbasierte Aufbewahrung sind Aufbewahrungseinstellungen erforderlich, die:
  
- Inhalte aufbewahren.
    
- den Inhalt automatisch löschen oder eine Dispositionsprüfung am Ende des Aufbewahrungszeitraums auslösen.
  
Die ereignisbasierte Aufbewahrung wird in der Regel für Inhalte verwendet, die als Datensatz deklariert sind. Dies ist daher ein guter Zeitpunkt, um zu überprüfen, ob Sie auch die Option zum Kennzeichnen von Inhalten als [Datensatz](records-management.md#records) auswählen müssen.

Wenn Sie einen vorhandenen Ereignistyp verwenden und nicht einen neuen erstellen, fahren Sie mit Schritt 3 fort.

> [!NOTE]
> Der Ereignistyp kann nicht mehr geändert werden, sobald Sie ihn ausgewählt und die Aufbewahrungsbezeichnung gespeichert haben.

### <a name="step-2-create-a-new-event-type-for-your-label"></a>Schritt 2: Erstellen eines neuen Ereignistyps für ihre Bezeichnung

Wenn Sie für die Aufbewahrungseinstellungen **Neuen Ereignistyp erstellen** ausgewählt haben, geben Sie einen Namen und eine Beschreibung für den Ereignistyp ein. Wählen Sie dann **Weiter**, **Senden** und **Fertig** aus.

Zurück auf der Seite **Aufbewahrungseinstellungen definieren** wählen Sie aus der Dropdownliste für **Aufbewahrungszeitraum starten basierend auf** den erstellten Ereignistyp aus.

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Schritt 3: Veröffentlichen oder automatisches Zuweisen der ereignisbasierten Aufbewahrungsbezeichnungen

Wie jede Aufbewahrungsbezeichnung müssen Sie auch ereignisbasierte Bezeichnungen veröffentlichen oder automatisch anwenden, damit sie auf Inhalte manuell oder automatisch angewendet werden können:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a>Schritt 4: Eine Asset-ID eingeben

Nachdem eine ereignisbasierte Bezeichnung auf Inhalte angewendet wurde, können Sie für jedes Element eine Objekt-ID eingeben. Ihre Organisation kann beispielsweise folgende Elemente verwenden:
  
- Produktcodes, um Inhalt nur für ein bestimmtes Produkt aufzubewahren.
    
- Projektcodes, um Inhalt nur für ein bestimmtes Projekt aufzubewahren.
    
- Mitarbeiter-IDs, die Sie zum Aufbewahren von Inhalten für eine bestimmte Person verwenden können.
    
Die Objekt-ID ist einfach eine weitere in SharePoint und OneDrive verfügbare Dokumenteigenschaft. Ihre Organisation verwendet möglicherweise bereits andere Dokumenteigenschaften und IDs zum Klassifizieren von Inhalten. In diesem Falle können Sie beim Erstellen eines Ereignisses auch diese Eigenschaften und Werte verwenden – siehe nachfolgenden Schritt 6. Wichtig ist hierbei, dass Sie in den Dokumenteigenschaften eine *Kombination aus Eigenschaft und Wert* verwenden müssen, um dieses Element mit einem Ereignistyp zu verknüpfen.
  
![Textfeld zum Eingeben einer Asset-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Schritt 5: Erstellen eines Ereignisses

Wenn eine bestimmte Instanz dieses Ereignistyps auftritt – z. B. wenn ein Produkt das Ende seiner Lebensdauer erreicht –, rufen Sie die Seite **Datensatzverwaltung** > **Ereignisse** im Microsoft 365 Compliance Center auf, und klicken Sie auf **+ Erstellen**, um ein Ereignis zu erstellen. Sie lösen das Ereignis aus, indem Sie es hier erstellen.

![Erstellen eines Ereignisses zum Auslösen des Aufbewahrungsbeginns für ereignisbasierte Aufbewahrungsbezeichnungen](../media/create-event-records-management.png)

Pro Mandant werden bis zu 1 Million Ereignisse unterstützt.

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Schritt 6: Auswählen des gleichen Ereignistyps, der von der Bezeichnung in Schritt 2 verwendet wird

Wenn Sie das Ereignis erstellen, wählen Sie den gleichen Ereignistyp aus, der in den Einstellungen für die Aufbewahrungsbezeichnung in Schritt 2 festgelegt wurde. Wenn Sie beispielsweise **Produktlebensdauer** als Ereignistyp für die Bezeichnungseinstellungen ausgewählt haben, wählen Sie beim Erstellen des Ereignisses ebenfalls **Produktlebensdauer** aus. Nur für Inhalte, denen Aufbewahrungsbezeichnungen des betreffenden Ereignistyps zugeordnet wurden, wird der Aufbewahrungszeitraum ausgelöst.

![Option in den Ereigniseinstellungen zum Auswählen eines Ereignistyps](../media/choose-event-type-records-management.png)

Wenn Sie ein Ereignis für mehrere Aufbewahrungsbezeichnungen erstellen müssen, die unterschiedliche Ereignistypen aufweisen, können Sie auch die Option **Vorhandene Bezeichnungen auswählen** auswählen. Wählen Sie dann die Bezeichnungen aus, die für die Ereignistypen konfiguriert sind, die Sie diesem Ereignis zuordnen möchten.

### <a name="step-7-enter-keywords-or-an-asset-id"></a>Schritt 7: Stichwörter oder Asset-ID eingeben

Schränken Sie nun den Umfang des Inhalts ein, indem Sie Objekt-IDs für SharePoint- und OneDrive-Inhalte bzw. Schlüsselwörter für Exchange-Inhalte angeben. Bei Objekt-IDs wird die Aufbewahrung nur für Inhalte mit der angegebenen Kombination aus *Eigenschaft und Wert* erzwungen. Wird keine Objekt-ID eingegeben, wird auf alle Inhalte mit Bezeichnungen dieses Ereignistyps dasselbe Aufbewahrungslimit angewendet.

Ein Beispiel: Wenn Sie die Eigenschaft "Objekt-ID" verwenden, geben Sie `ComplianceAssetID:<value>` in das untenstehende Feld für Objekt-IDs ein.
  
Möglicherweise hat Ihre Organisation andere Eigenschaften und IDs auf die mit diesem Ereignistyp verknüpften Dokumente angewendet. Wenn Sie beispielsweise die Datensätze zu einem bestimmten Produkt ermitteln müssen, könnte die ID eine Kombination aus Ihrer benutzerdefinierten Eigenschaft "ProductID" und dem Wert "XYZ" sein. In diesem Fall würden Sie in das Feld für Objekt-IDs, das in der folgenden Abbildung dargestellt ist, `ProductID:XYZ` eingeben.
  
Verwenden Sie für Exchange-Elemente Stichworte. Für eine Abfrage können Sie Suchoperatoren wie AND, OR und NOT verwenden. Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
Wählen Sie schließlich das Datum aus, an dem das Ereignis eingetreten ist. Dieses Datum wird als Anfang des Aufbewahrungszeitraums verwendet. Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps, die Objekt-ID und die Schlüsselwörter aufweisen.  Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern.
  
![Seite „Ereigniseinstellungen“](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

Nach dem Erstellen eines Ereignisses gelten die Aufbewahrungseinstellungen für bereits bezeichnete und indizierte Inhalte. Wenn die Aufbewahrungsbezeichnung zu neuen Inhalten hinzugefügt wird, nachdem das Ereignis erstellt wurde, müssen Sie ein neues Ereignis mit den gleichen Details erstellen.

Wenn Sie ein Ereignis löschen, werden dadurch die Aufbewahrungseinstellungen, die jetzt für bereits bezeichnete Inhalte in Kraft sind, nicht aufgehoben. Erstellen Sie dazu ein neues Ereignis mit den gleichen Details, lassen Sie das Datum aber leer. 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Verwenden der Inhaltssuche zum Auffinden aller Inhalte mit einer bestimmten Bezeichnung oder Objekt-ID

Nachdem Aufbewahrungsbezeichnungen Inhalten zugewiesen wurden, können Sie die Inhaltssuche verwenden, um alle Inhalte aufzufinden, die durch eine bestimmte Aufbewahrungsbezeichnung klassifiziert wurden oder eine bestimmte Objekt-ID enthalten.
  
- Um alle Inhalte mit einer bestimmten Aufbewahrungsbezeichnung zu finden, wählen Sie die Bedingung **Aufbewahrungsbezeichnung**, und geben Sie dann den vollständigen oder Bezeichnungsnamen oder einen Teil des Bezeichnungsnamens ein, und verwenden Sie einen Platzhalter. 
    
- Um alle Inhalte mit einer bestimmten Objekt-ID zu finden, geben Sie die **ComplianceAssetID**-Eigenschaft und einen Wert ein, und zwar im Format: `ComplianceAssetID:<value>`. 
    
Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).

## <a name="automate-events-by-using-powershell"></a>Automatisieren von Ereignissen mit PowerShell

Sie können ereignisbasierte Aufbewahrung aus Ihren Geschäftsanwendungen heraus mithilfe eines PowerShell-Skripts automatisieren. PowerShell-Cmdlets für die ereignisbasierte Aufbewahrung:
  
- [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [New-ComplianceRetentionEventType](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [Remove-ComplianceRetentionEventType](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [Set-ComplianceRetentionEventType](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [Get-ComplianceRetentionEvent](/powershell/module/exchange/get-complianceretentionevent)
    
- [New-ComplianceRetentionEvent](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a>Automatisieren von Ereignissen mithilfe einer REST-API

Sie können eine REST-API verwenden, um automatisch die Ereignisse zu erstellen, die den Beginn der Aufbewahrungszeit auslösen.

Bei einer REST-API handelt es sich um einen Dienstendpunkt, der Gruppen von HTTP-Vorgängen (Methoden) unterstützt, die Zugriff zum Erstellen/Abrufen/Aktualisieren/Löschen der Dienstressourcen bieten. Weitere Informationen finden Sie unter [Komponenten einer REST-API-Anfrage/-Anfrage](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). Mithilfe der Microsoft 365 REST-API können Ereignisse mit POST- und GET-Operationen erstellt und abgerufen werden.

Es gibt zwei Optionen für die Verwendung der REST-API:

- **Microsoft Power Automate oder eine ähnliche Anwendung** zum automatischen Auslösen des Ereignisses. Microsoft Power Automate ist ein Orchestrator zum Herstellen der Verbindung zu anderen Systemen, sodass Sie keine benutzerdefinierte Lösung erstellen müssen. Weitere Informationen finden Sie auf der [Power Automate-Website](https://flow.microsoft.com/de-DE/).

- **PowerShell oder ein HTTP-Client zum Aufrufen der REST-API**, um Ereignisse mithilfe von PowerShell (Version 6 oder höher) zu erstellen, was Teil einer benutzerdefinierten Lösung ist.

Bevor Sie die REST-API verwenden, überprüfen Sie als globaler Administrator die URL, die für den Aufruf des Aufbewahrungsereignisses verwendet werden soll. Führen Sie dazu ein GET-Aufbewahrungsereignisaufruf mithilfe der REST-API-URL aus:

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

Überprüfen Sie den Antwortcode. Wenn es sich um 302 handelt, rufen Sie die umgeleitete URL aus der „Location“-Eigenschaft des Antwortheaders ab, und verwenden Sie diese URL statt `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in den nachfolgenden Anweisungen.

Die automatisch erstellten Ereignisse können bestätigt werden, indem Sie sie im Microsoft 365 Compliance Center anzeigen > **Datensatzverwaltung** >  **Ereignisse**.

### <a name="use-microsoft-power-automate-to-create-the-event"></a>Verwenden von Microsoft Power Automate zum Erstellen des Ereignisses

Erstellen eines Ablaufs zum Erstellen eines Ereignisses mithilfe der Microsoft 365-REST-API:

![Verwenden von Flow zum Erstellen eines Ereignisses](../media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a>Erstellen eines Ereignisses

Beispielcode zum Aufrufen der REST-API:

- **Method**: POST
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Headers**: Key = Content-Type, Value = application/atom+xml
- **Body**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- **Authentication**: Basic
- **Username**: "Complianceuser"
- **Password**: "Compliancepassword"


##### <a name="available-parameters"></a>Verfügbare Parameter


|Parameter|Beschreibung|Anmerkungen|
|--- |--- |--- |
|<d:Name></d:Name>|Geben Sie einen eindeutigen Namen für das Ereignis an.|Der Name darf nachfolgende Leerzeichen oder die folgenden Zeichen nicht enthalten: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Geben Sie den Namen des Ereignistyps (oder GUID) ein.|Beispiel: "Mitarbeiterkündigung". Der Ereignistyp muss einer Aufbewahrungsbezeichnung zugeordnet sein.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Geben Sie "ComplianceAssetId:" + Mitarbeiter-ID ein|Beispiel: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Datum und Uhrzeit des Ereignisses|Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel: 2018-12-01T00:00:00Z
|

###### <a name="response-codes"></a>Antwortcodes

| Antwortcode | Beschreibung       |
| ----------------- | --------------------- |
| 302               | Umleiten              |
| 201               | Erstellt               |
| 403               | Autorisierung fehlgeschlagen  |
| 401               | Authentifizierung fehlgeschlagen |

##### <a name="get-events-based-on-a-time-range"></a>Abrufen von Ereignissen basierend auf einem Zeitraum

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"


###### <a name="response-codes"></a>Antwortcodes

| Antwortcode | Beschreibung                   |
| ----------------- | --------------------------------- |
| 200               | OK, eine Liste der Ereignisse in Atom + XML |
| 404               | Nicht gefunden                         |
| 302               | Umleiten                          |
| 401               | Autorisierung fehlgeschlagen              |
| 403               | Authentifizierung fehlgeschlagen             |

##### <a name="get-an-event-by-id"></a>Abrufen eines Ereignisses nach ID

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"

###### <a name="response-codes"></a>Antwortcodes

| Antwortcode | Beschreibung                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, der Antworttext enthält das Ereignis in Atom + XML |
| 404               | Nicht gefunden                                            |
| 302               | Umleiten                                             |
| 401               | Autorisierung fehlgeschlagen                                 |
| 403               | Authentifizierung fehlgeschlagen                                |

##### <a name="get-an-event-by-name"></a>Abrufen eines Ereignisses anhand des Namens

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"


###### <a name="response-codes"></a>Antwortcodes

| Antwortcode | Beschreibung                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, der Antworttext enthält das Ereignis in Atom + XML |
| 404               | Nicht gefunden                                            |
| 302               | Umleiten                                             |
| 401               | Autorisierung fehlgeschlagen                                 |
| 403               | Authentifizierung fehlgeschlagen                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a>Verwenden von PowerShell oder einem beliebigen HTTP-Client, um das Ereignis zu erstellen

Bei PowerShell muss es sich um Version 6 oder höher handeln.

Führen Sie in einer PowerShell-Sitzung das folgende Skript aus:

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```