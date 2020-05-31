---
title: Übersicht über die ereignisgesteuerte Aufbewahrung
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
description: Mit Aufbewahrungsbezeichnungen können Sie einen Aufbewahrungszeitraum darauf basieren, wann ein bestimmter Ereignistyp auftritt. Das Ereignis löst den Beginn des Aufbewahrungszeitraums aus, und auf alle Inhalte, denen eine Aufbewahrungsbezeichnung für diese Art von Ereignis zugewiesen wurde, werden die Aufbewahrungsaktionen dieser Bezeichnung angewendet. Die ereignisgesteuerte Aufbewahrung wird in der Regel als Teil eines Prozesses für die Datensatzverwaltung verwendet.
ms.openlocfilehash: 100381d87c51a8ef403a88f19159235081c2a8df
ms.sourcegitcommit: 330e9baf02b5bc220d61f777c2338814459626ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44385007"
---
# <a name="overview-of-event-driven-retention"></a>Übersicht über die ereignisgesteuerte Aufbewahrung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie Inhalte aufbewahren, basiert der Aufbewahrungszeitraum häufig auf dem Alter des Inhalts. Sie bewahren Dokumente beispielsweise für sieben Jahre nach der Erstellung auf, und anschließend werden sie gelöscht. Mit Aufbewahrungsbezeichnungen in Microsoft 365 können Sie jedoch auch einen Aufbewahrungszeitraum festlegen, der auf dem Auftreten eines bestimmten Ereignistyps basiert. Das Ereignis löst den Beginn des Aufbewahrungszeitraums aus, und auf alle Inhalte, denen eine Aufbewahrungsbezeichnung für diesen Ereignistyp zugewiesen wurde, werden die Aufbewahrungsaktionen angewendet.
  
Sie können Bezeichnungen mit ereignisgesteuerter Aufbewahrung zum Beispiel in den folgenden Szenarien verwenden:
  
- **Mitarbeiter verlässt das Unternehmen** – Angenommen, dass Mitarbeiterdatensätze für 10 Jahre ab dem Zeitpunkt aufbewahrt werden müssen, an dem ein Mitarbeiter das Unternehmen verlässt. Nach Ablauf von 10 Jahren müssen alle Dokumente im Zusammenhang mit der Einstellung, der Leistung und der Beendigung des Arbeitsverhältnisses für diesen Mitarbeiter vernichtet werden. Das Ereignis, das den Aufbewahrungszeitraum von 10 Jahren auslöst, ist der Zeitpunkt, zu dem der Mitarbeiter die Organisation verlässt. 
    
- **Vertragsablauf** – Angenommen, alle Datensätze im Zusammenhang mit Verträgen müssen für fünf Jahre ab dem Zeitpunkt aufbewahrt werden, an dem der Vertrag abläuft. Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren auslöst, ist das Ablaufdatum des Vertrags. 
    
- **Produktlebensdauer** – Ihre Organisation hat möglicherweise Aufbewahrungspflichten, die sich auf das letzte Fertigungsdatum von Produkten für Inhalte wie technische Daten beziehen. In diesem Fall ist das Datum der letzte Fertigung das Ereignis, das den Aufbewahrungszeitraum auslöst. 
    
Die ereignisgesteuerte Aufbewahrung wird in der Regel als Teil eines Prozesses für die Datensatzverwaltung verwendet. Dies bedeutet:
  
- Bezeichnungen, die auf Ereignissen basieren, klassifizieren den Inhalt in der Regel auch als einen Datensatz. Weitere Informationen finden Sie unter [Verwenden der Inhaltssuche zum Suchen des gesamten Inhalts, auf den eine bestimmte Aufbewahrungsbezeichnung angewendet wurde](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Ein Dokument, das als Datensatz deklariert wurde, dessen Ereignisauslöser jedoch noch nicht ausgelöst wurde, wird auf unbegrenzte Zeit beibehalten (Datensätze können nicht dauerhaft gelöscht werden), bis ein Ereignis den Aufbewahrungszeitraum des Dokuments auslöst.
    
- Aufbewahrungsbezeichnungen, die auf einem Ereignis basieren, lösen in der Regel am Ende des Aufbewahrungszeitraums eine Dispositionsprüfung aus, damit ein Datensatzverwalter den Inhalt manuell überprüfen und vernichten kann. Weitere Informationen finden Sie unter [Entfernung von Inhalten](disposition.md).
    
Eine ereignisbasierte Aufbewahrungsbezeichnung hat die gleichen Funktionen wie jede andere Aufbewahrungsbezeichnung in Microsoft 365. Weitere Informationen hierzu finden Sie unter [Übersicht über Bezeichnungen](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Grundlegendes zur Beziehung zwischen Ereignistypen, Bezeichnungen, Ereignissen und Asset-IDs

Um die ereignisgesteuerte Aufbewahrung erfolgreich zu verwenden, müssen Sie die Beziehung zwischen Ereignistypen, Aufbewahrungsbezeichnungen, Ereignissen und Asset-IDs verstehen, wie in den Diagrammen und der nachfolgenden Erklärung gezeigt: 
  
![Diagramm der Ereignistypen, Bezeichnungen, Ereignisse und Anlage IDs](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramm der Ereignistypen, Bezeichnungen, Ereignisse und Anlage IDs](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Sie erstellen Aufbewahrungsbezeichnungen für unterschiedliche Arten von Inhalten und ordnen diesen dann einen Ereignistyp zu. Aufbewahrungsbezeichnungen für verschiedene Arten von Produktdateien und Datensätzen werden beispielsweise einem Ereignistyp mit der Bezeichnung „Product Lifetime“ zugeordnet, da diese Datensätze ab dem Ende des Produktlebenszyklus für 10 Jahre aufbewahrt werden müssen.
    
2. Benutzer (in der Regel Datensatzverwalter) wenden diese Aufbewahrungsbezeichnungen auf Inhalte an, und geben (bei SharePoint- und OneDrive-Dokumenten) eine Objekt-ID für jedes Element ein. In diesem Beispiel ist die Objekt-ID ein von der Organisation verwendeter Produktname oder -code. Daher wird den Datensätzen jedes Produkts eine Aufbewahrungsbezeichnung zugewiesen, und jeder Datensatz verfügt über eine Eigenschaft, die eine Objekt-ID enthält. Das Diagramm stellt **alle Inhalte** für alle Produktdatensätze in einer Organisation dar, wobei jedes Element die Objekt-ID des Produkts trägt, um dessen Datensatz es sich handelt. 
    
3. „Product Lifetime“ ist der Ereignistyp. Ein bestimmtes Produkt, das das Ende seines Lebenszyklus erreicht, ist ein Ereignis. Wenn ein Ereignis dieses Typs auftritt (in diesem Fall, wenn ein Produkt das Ende seiner Lebensdauer erreicht), erstellen Sie ein Ereignis, das Folgendes angibt:
    
  - Eine Asset-ID (für SharePoint- und OneDrive-Dokumente)
    
  - Schlüsselwörter (für Exchange-Elemente). In diesem Beispiel verwendet das Unternehmen einen Produktcode in Nachrichten, die Produktdatensätze enthalten, sodass das Schlüsselwort für Exchange-Elemente der Objekt-ID für SharePoint- und OneDrive-Dokumente entspricht.
    
  - Das Datum, an dem das Ereignis aufgetreten ist. Dieses Datum wird als Beginn des Aufbewahrungszeitraums verwendet. Dieses Datum kann das aktuelle, ein vergangenes oder ein zukünftiges Datum sein.
    
4. Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps aufweisen und die angegebene Objekt-ID bzw. das angegebene Schlüsselwort enthalten. Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern. Im vorherigen Diagramm haben alle rot eingekreisten Elemente den Aufbewahrungszeitraum durch dieses Ereignis ausgelöst. Mit anderen Worten, wenn dieses Produkt das Ende seiner Lebensdauer erreicht, löst dieses Ereignis den Aufbewahrungszeitraum für die Produktdatensätze aus.
    
Es ist wichtig zu verstehen, dass der Aufbewahrungszeitraum für **alle Inhalte** mit einer Bezeichnung dieses Ereignistyps durch das Ereignis ausgelöst wird, wenn Sie keine Objekt-ID oder Schlüsselwörter für ein Ereignis angeben. Dies bedeutet, dass im vorherigen Diagramm der Aufbewahrungszeitraum für alle Inhalte beginnen würde. Dies ist möglicherweise nicht, was Sie beabsichtigen. 
  
Denken Sie schließlich daran, dass es zu jeder Aufbewahrungsbezeichnung eigene Aufbewahrungseinstellungen gibt. In diesem Beispiel ist für alle ein Zeitraum von 10 Jahren angegeben, aber es ist möglich, dass ein Ereignis Aufbewahrungsbezeichnungen mit unterschiedlichen Aufbewahrungszeiträumen auslöst.
  
## <a name="how-to-set-up-event-driven-retention"></a>So richten Sie die ereignisgesteuerte Aufbewahrung ein

Allgemeiner Workflow für die ereignisgesteuerte Aufbewahrung:
  
![Diagramm des Arbeitsablaufs zum Einrichten der ereignisgesteuerten Aufbewahrung](../media/event-based-retention-process.png)
  
> [!TIP]
> Unter [Verwalten des Lebenszyklus von SharePoint-Dokumenten mithilfe von Aufbewahrungsbezeichnungen](auto-apply-retention-labels-scenario.md) finden Sie ein detailliertes Szenario zur Verwendung von verwalteten Eigenschaften in SharePoint, um Aufbewahrungsbezeichnungen automatisch anzuwenden und die ereignisgesteuerte Aufbewahrung zu implementieren.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Schritt 1: Eine Bezeichnung erstellen, deren Aufbewahrungszeitraum auf einem Ereignis basiert

Wählen Sie im Microsoft 365 Compliance Center, Microsoft 365 Security Center oder Security &amp; Compliance Center in der linken Navigation **Klassifikation** > **Aufbewahrungsbezeichnungen** > **Bezeichnungen** (Registerkarte) > **Bezeichnung erstellen** aus.
  
Wenn Sie die Bezeichnung erstellen, aktivieren Sie die Aufbewahrung und wählen Sie die unten aufgeführte Option zum Beibehalten oder Löschen von Inhalt basierend auf einem Ereignis. Dies bedeutet, dass die Aufbewahrungseinstellungen erst in Schritt 5 wirksam werden, wenn Sie auf der Seite **Ereignisse** ein Ereignis erstellen. 
  
Beachten Sie, dass die ereignisgesteuerte Aufbewahrung in der Regel für Inhalt verwendet wird, der als Datensatz klassifiziert ist. Aus diesem Grund sollten Sie, wenn Sie Aufbewahrungsbezeichnungen basierend auf einem Ereignis erstellen, in der Regel die Option **Bezeichnung verwenden, um Inhalte als "Datensatz" zu klassifizieren** auswählen.
  
Beachten Sie außerdem, dass für die ereignisgesteuerte Aufbewahrung Aufbewahrungseinstellungen erforderlich sind, die:
  
- Inhalte aufbewahren.
    
- den Inhalt automatisch löschen oder eine Dispositionsprüfung am Ende des Aufbewahrungszeitraums auslösen.
    
![Option, um eine Bezeichnung auf einem Ereignis zu basieren](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Schritt 2: Einen Ereignistyps für die Bezeichnung auswählen

Nachdem Sie die Option ausgewählt haben, dass die Bezeichnung auf **einem Ereignis** basieren soll, wird in den Bezeichnungseinstellungen die Option zum **Auswählen eines Ereignistyps** angezeigt. Ein Ereignistyp ist einfach eine allgemeine Beschreibung eines Ereignisses, das Sie der Bezeichnung zuordnen möchten.
  
Wenn Sie zum Beispiel einen Ereignistyp mit dem Namen „Product Lifetime“ haben, erstellen Sie ereignisbasierte Aufbewahrungsbezeichnungen mit Namen, die beschreiben, auf welchen Inhaltstyp die Bezeichnungen angewendet werden sollen, z. B. „Produktentwicklungsdateien“ oder „Produktgeschäft-Entscheidungsdatensätze“.
  
Beachten Sie, dass der Ereignistyp nicht mehr geändert werden kann, sobald Sie einen Ereignistyp ausgewählt und die Aufbewahrungsbezeichnung erstellt haben.
  
![Optionen zum Erstellen oder Auswählen eines Ereignistyps](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Schritt 3: Veröffentlichen oder automatisches Zuweisen der ereignisbasierten Aufbewahrungsbezeichnungen

Wie jede Aufbewahrungsbezeichnung müssen Sie auch ereignisbasierte Bezeichnungen [veröffentlichen oder automatisch zuweisen](create-retention-labels.md), damit es Inhalten manuell oder automatisch zugewiesen werden kann.

> [!NOTE]
> Wenn Sie eine ereignisgesteuerte Aufbewahrungsbezeichnung aus der Registerkarte **Datensatzverwaltung** > **Dateiplan** oder der Registerkarte **Datensteuerung** > **Bezeichnungen** wühlen, ist die Schaltfläche **Bezeichnung automatisch anwenden** nicht verfügbar.
> 
> Statt dieser Schaltfläche verwenden Sie die Option **Bezeichnung automatisch anwenden** über der Liste der Bezeichnungen oder Richtlinien aus einer der folgenden Speicherorte:
> - Registerkarte **Datensatzverwaltung** > **Bezeichnungsrichtlinien**
> - Registerkarte **Datensteuerung** > **Bezeichnungen**  oder Registerkarte **Bezeichnungsrichtlinien**

### <a name="step-4-enter-an-asset-id"></a>Schritt 4: Eine Asset-ID eingeben

Nachdem eine ereignisgesteuerte Bezeichnung auf Inhalt angewendet wurde, können Sie für jedes Element eine Objekt-ID eingeben. Ihre Organisation kann beispielsweise folgende Elemente verwenden:
  
- Produktcodes, um Inhalt nur für ein bestimmtes Produkt aufzubewahren.
    
- Projektcodes, um Inhalt nur für ein bestimmtes Projekt aufzubewahren.
    
- Mitarbeiter-IDs, die Sie zum Aufbewahren von Inhalten für eine bestimmte Person verwenden können.
    
Beachten Sie, dass die Objekt-ID nur eine weitere Dokumenteigenschaft in SharePoint und OneDrive for Business ist. Ihre Organisation verwendet möglicherweise bereits andere Dokumenteigenschaften und IDs zum Klassifizieren von Inhalten. In diesem Falle können Sie beim Erstellen eines Ereignisses auch diese Eigenschaften und Werte verwenden – siehe nachfolgenden Schritt 6. Wichtig ist hierbei, dass Ihre Organisation in den Dokumenteigenschaften eine Kombination aus Eigenschaft und Wert verwenden muss, um dieses Element mit einem Ereignistyp zu verknüpfen.
  
![Textfeld zum Eingeben einer Asset-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Schritt 5: Erstellen eines Ereignisses

Wenn eine bestimmte Instanz dieses Ereignistyps eintritt (ein Produkt erreicht z. B. das Ende seiner Lebensdauer), gehen Sie zur Seite **Datensatzverwaltung** > **Ereignisse** im Security &amp; Compliance Center, und erstellen Sie ein Ereignis. Sie müssen ein Ereignis manuell auslösen, indem Sie es erstellen.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Schritt 6: Auswählen des gleichen Ereignistyps, der von der Bezeichnung in Schritt 2 verwendet wird

Wenn Sie ein Ereignis erstellen, wählen Sie den gleichen Ereignistyp aus, der von der Aufbewahrungsbezeichnung in Schritt 2 verwendet wird, z. B. „Product Lifetime“. Nur für Inhalte, denen Aufbewahrungsbezeichnungen des betreffenden Ereignistyps zugeordnet wurden, wird der Aufbewahrungszeitraum ausgelöst.
  
![Option in den Ereigniseinstellungen zum Auswählen eines Ereignistyps](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Schritt 7: Stichwörter oder Asset-ID eingeben

Jetzt können Sie den Umfang der Inhalte eingrenzen, indem Sie Asset-IDs für SharePoint- und OneDrive-Inhalte oder Stichwörter für Exchange-Inhalte angeben. Bei Asset IDs wird die Aufbewahrung nur für Inhalte mit dem angegebenen Eigenschaft-Wert-Paar erzwungen. Wenn keine Asset-ID eingegeben wird, wird der **gesamte Inhalt**, der Bezeichnungen dieses Ereignistyps aufweist, mit dem gleichen Aufbewahrungsdatum versehen. 
  
Beachten Sie, dass die Objekt-ID nur eine weitere Dokumenteigenschaft in SharePoint und OneDrive for Business ist. Wenn Sie die Eigenschaft "Objekt-ID" verwenden, geben Sie "ComplianceAssetID:\<value\>" in das untenstehende Feld für Objekt-IDs ein.
  
Ihre Organisation hat möglicherweise andere Eigenschaften und IDs auf die Dokumente angewendet, die sich auf diesen Ereignistyp beziehen. Wenn Sie zum Beispiel die Datensatz eines bestimmten Produkts ermitteln müssen, kann die ID eine Kombination aus Ihrer benutzerdefinierten ProductID-Eigenschaft und den Wert „XYZ“ sein. In diesem Fall würden Sie „ProductID:XYZ“ in das Feld für die Asset-IDs eingeben.
  
Für Exchange-Elemente können Sie Stichwörter verwenden. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie AND, OR und NOT verfeinern. Weitere Informationen zu Operatoren finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
Wählen Sie schließlich das Datum aus, an dem das Ereignis eingetreten ist. Dieses Datum wird als Anfang des Aufbewahrungszeitraums verwendet. Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps, die Objekt-ID und die Schlüsselwörter aufweisen.  Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern.
  
![Seite „Ereigniseinstellungen“](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Verwenden der Inhaltssuche zum Suchen des gesamten Inhalts, dem eine bestimmte Bezeichnung oder Asset-ID zugewiesen ist

Nachdem Aufbewahrungsbezeichnungen Inhalten zugewiesen wurden, können Sie die Inhaltssuche verwenden, um alle Inhalte zu suchen, die durch eine bestimmte Aufbewahrungsbezeichnung klassifiziert wurden oder eine bestimmte Asset-ID enthalten.
  
Beachten Sie beim Erstellen einer Inhaltssuche Folgendes:
  
- Um alle Inhalte mit einer bestimmten Aufbewahrungsbezeichnung zu finden, wählen Sie die Bedingung **Compliancetag**, und geben Sie dann den vollständigen oder teilweisen Bezeichnungsnamen ein, oder verwenden Sie ein Platzhalterzeichen. 
    
- Um alle Inhalte mit einer bestimmten Asset-ID zu finden, geben Sie die **ComplianceAssetID**-Eigenschaft und einen Wert ein, und zwar im Format „ComplianceAssetID:\<value\>“. 
    
Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Berechtigungen

Um Zugriff auf die Seite **Ereignisse** zu erhalten, müssen Prüfer Mitglied einer Rollengruppe sein, die die Rolle **Disposition Management** und die Rolle **View-Only Audit Logs** hat. Es wird empfohlen, eine neue Rollengruppe namens „Disposition Reviewers“ zu erstellen, diese beiden Rollen zu dieser Rollengruppe hinzuzufügen und anschließend Mitglieder zur Rollengruppe hinzuzufügen. 
  
Weitere Informationen finden Sie unter [Gewähren des Zugriffs auf das Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatisieren von Ereignissen mit PowerShell

Im Admin Center können Sie Ereignisse nur manuell erstellen. Es ist nicht möglich, ein Ereignis bei seinem Auftreten automatisch auszulösen. Sie können jedoch eine Rest-API verwenden, um automatisch Ereignisse auszulösen; weitere Informationen finden Sie unter [Automatisieren ereignisbasierter Aufbewahrung](automate-event-driven-retention.md).

Sie können auch ereignisbasierte Aufbewahrung aus Ihren Geschäftsanwendungen heraus mithilfe eines PowerShell-Skripts automatisieren. PowerShell-Cmdlets für die ereignisgesteuerte Aufbewahrung:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

