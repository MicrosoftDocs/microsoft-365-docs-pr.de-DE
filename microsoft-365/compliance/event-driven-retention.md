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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Normalerweise ein Bestandteil einer Datensatzverwaltungslösung. Sie können eine Aufbewahrungsbezeichnung so konfigurieren, dass der Aufbewahrungszeitraum basierend auf einem von Ihnen festgelegten Ereignis gestartet wird.
ms.openlocfilehash: a0e0025d23bda36d8b9e6315cb932e58d4237a5c
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068124"
---
# <a name="overview-of-event-driven-retention"></a>Übersicht über die ereignisgesteuerte Aufbewahrung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie Inhalte aufbewahren, basiert der Aufbewahrungszeitraum häufig auf dem Alter des Inhalts. Sie könnten beispielsweise Dokumente für sieben Jahre nach der Erstellung aufbewahren, und anschließend werden sie gelöscht. Wenn Sie jedoch [Aufbewahrungsbezeichnungen](labels.md) konfigurieren, können Sie auch einen Aufbewahrungszeitraum festlegen, der auf dem Auftreten eines bestimmten Ereignistyps basiert. Das Ereignis löst den Beginn des Aufbewahrungszeitraums aus, und auf alle Inhalte, denen eine Aufbewahrungsbezeichnung für diesen Ereignistyp zugewiesen wurde, werden die Aufbewahrungsaktionen angewendet.
  
Beispiele für die Verwendung der ereignisgesteuerten Aufbewahrung:
  
- **Mitarbeiter verlassen die Organisation** Angenommen, Mitarbeiterdatensätze müssen ab dem Zeitpunkt, an dem ein Angestellter das Unternehmen verlässt, 10 Jahre lang aufbewahrt werden. Nach 10 Jahren müssen alle Dokumente im Zusammenhang mit der Einstellung, Leistung und Kündigung dieses Angestellten gelöscht werden. Das Ereignis, das den Aufbewahrungszeitraum von 10 Jahren auslöst, ist die Beendigung des Beschäftigungsverhältnisses des Mitarbeiters bei der Organisation. 
    
- **Vertragsablauf** Angenommen, alle Datensätze im Zusammenhang mit Verträgen müssen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft. Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags. 
    
- **Produktlebensdauer** – Ihre Organisation hat möglicherweise Aufbewahrungspflichten, die sich auf das letzte Fertigungsdatum von Produkten für Inhalte wie technische Daten beziehen. In diesem Fall ist das Datum der letzte Fertigung das Ereignis, das den Aufbewahrungszeitraum auslöst. 
    
Die ereignisgesteuerte Aufbewahrung wird in der Regel als Teil eines Prozesses für die Datensatzverwaltung verwendet. Dies bedeutet:
  
- Bezeichnungen auf Basis von Ereignissen klassifizieren in der Regel auch Inhalte als Datensatz. Weitere Informationen finden Sie unter [Informationen zu Datensätzen](records.md).
    
- Ein Dokument, das als Datensatz klassifiziert wurde, dessen Ereignisauslöser jedoch noch nicht eingetreten ist, wird unbegrenzt aufbewahrt (Datensätze können nicht dauerhaft gelöscht werden), bis der Aufbewahrungszeitraum für das Dokument durch ein Ereignis ausgelöst wird.
    
- Aufbewahrungsbezeichnungen auf Basis von Ereignissen lösen in der Regel eine Löschungsprüfung am Ende des Aufbewahrungszeitraums aus, damit ein Datensatzverwalter den Inhalt manuell überprüfen und löschen kann. Weitere Informationen finden Sie unter [Entfernung von Inhalten](disposition.md).
    
Eine auf einem Ereignis basierende Aufbewahrungsbezeichnung weist die gleichen Funktionen wie jede Aufbewahrungsbezeichnung in Microsoft 365 auf. Weitere Informationen finden Sie unter [Informationen zu Aufbewahrungskennzeichen](labels.md).

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
    
4. Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps aufweisen und die angegebene Objekt-ID bzw. das angegebene Schlüsselwort enthalten. Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern. Bei allen rot eingekreisten Elementen im vorigen Diagramm wird der Aufbewahrungszeitraum durch dieses Ereignis ausgelöst. Mit anderen Worten, wenn dieses Produkt das Ende seiner Lebensdauer erreicht, löst dieses Ereignis den Aufbewahrungszeitraum für die Produktdatensätze aus.
    
Folgendes sollten Sie verstehen: Wenn Sie für ein Ereignis keine Objekt-ID und keine Schlüsselwörter angeben, wird der Aufbewahrungszeitraum für **alle Inhalte** mit einer Bezeichnung dieses Ereignistyps durch das Ereignis ausgelöst. Dies bedeutet, dass im vorherigen Diagramm der Aufbewahrungszeitraum für alle Inhalte beginnen würde. Dies ist möglicherweise nicht, was Sie beabsichtigen. 
  
Denken Sie schließlich daran, dass es zu jeder Aufbewahrungsbezeichnung eigene Aufbewahrungseinstellungen gibt. In diesem Beispiel ist für alle ein Zeitraum von 10 Jahren angegeben, aber es ist möglich, dass ein Ereignis Aufbewahrungsbezeichnungen mit unterschiedlichen Aufbewahrungszeiträumen auslöst.
  
## <a name="how-to-set-up-event-driven-retention"></a>So richten Sie die ereignisgesteuerte Aufbewahrung ein

Allgemeiner Workflow für die ereignisgesteuerte Aufbewahrung:
  
![Diagramm des Arbeitsablaufs zum Einrichten der ereignisgesteuerten Aufbewahrung](../media/event-based-retention-process.png)
  
> [!TIP]
> Unter [Verwalten des Lebenszyklus von SharePoint-Dokumenten mithilfe von Aufbewahrungsbezeichnungen](auto-apply-retention-labels-scenario.md)finden Sie ein detailliertes Szenario zur Verwendung von verwalteten Eigenschaften in SharePoint, um Aufbewahrungsbezeichnungen automatisch anzuwenden und die ereignisgesteuerte Aufbewahrung zu implementieren.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Schritt 1: Eine Bezeichnung erstellen, deren Aufbewahrungszeitraum auf einem Ereignis basiert

Folgen Sie zum Erstellen und Konfigurieren Ihrer Aufbewahrungsbezeichnung den Anweisungen unter [Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen](create-retention-labels.md#create-and-configure-retention-labels), und wählen Sie beim Aktivieren der Aufbewahrung die Option aus, den Inhalt auf der Grundlage eines Ereignisses aufzubewahren oder zu löschen. Durch diese Einstellung werden die Aufbewahrungseinstellungen nur wirksam, wenn Sie in Schritt 5 auf der Seite **Ereignisse** ein Ereignis erstellen. 
  
Die ereignisgesteuerte Aufbewahrung wird in der Regel für Inhalte verwendet, die als Datensatz klassifiziert sind. Dies ist daher ein guter Zeitpunkt, um zu überprüfen, ob Sie auch die Option zum Markieren von Inhalten als Datensatz auswählen müssen.
  
Für die ereignisgesteuerte Aufbewahrung sind Aufbewahrungseinstellungen erforderlich, die:
  
- Inhalte aufbewahren.
    
- den Inhalt automatisch löschen oder eine Dispositionsprüfung am Ende des Aufbewahrungszeitraums auslösen.
    
![Option, um eine Bezeichnung auf einem Ereignis zu basieren](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a>Schritt 2: Einen Ereignistyps für die Bezeichnung auswählen

Nachdem Sie in den Bezeichnungseinstellungen die Option ausgewählt haben, die Bezeichnung auf **einem Ereignis** zu basieren, wird die Option zum **Auswählen eines Ereignistyps** angezeigt. Ein Ereignistyp ist einfach eine allgemeine Beschreibung eines Ereignisses, das Sie einer Bezeichnung zuordnen möchten.
  
Wenn Sie zum Beispiel einen Ereignistyp mit dem Namen „Product Lifetime“ haben, erstellen Sie ereignisbasierte Aufbewahrungsbezeichnungen mit Namen, die beschreiben, auf welchen Inhaltstyp die Bezeichnungen angewendet werden sollen, z. B. „Produktentwicklungsdateien“ oder „Produktgeschäft-Entscheidungsdatensätze“.

Wählen Sie einen der integrierten Ereignistypen aus, oder erstellen Sie einen eigenen und wählen Sie diesen dann aus.

Der Ereignistyp kann nicht mehr geändert werden, sobald Sie ihn ausgewählt und die Aufbewahrungsbezeichnung gespeichert haben.
  
![Optionen zum Erstellen oder Auswählen eines Ereignistyps](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Schritt 3: Veröffentlichen oder automatisches Zuweisen der ereignisbasierten Aufbewahrungsbezeichnungen

Wie jede Aufbewahrungsbezeichnung müssen Sie auch ereignisbasierte Bezeichnungen [veröffentlichen oder automatisch anwenden](create-retention-labels.md), damit sie auf Dokumente und E-Mails angewendet werden können.

> [!NOTE]
> Wenn Sie eine ereignisbasierte Aufbewahrungsbezeichnung auf der Registerkarte **Datensatzverwaltung** > **Dateiplan** oder der Registerkarte **Datengovernance** > **Bezeichnungen** wählen, ist die Schaltfläche **Bezeichnung automatisch anwenden** nicht verfügbar.
> 
> Statt dieser Schaltfläche verwenden Sie die Option **Bezeichnung automatisch anwenden** über der Liste der Bezeichnungen oder Richtlinien aus einer der folgenden Speicherorte:
> - Registerkarte **Datensatzverwaltung** > **Bezeichnungsrichtlinien**
> - Registerkarte **Datensteuerung** > **Bezeichnungen**  oder Registerkarte **Bezeichnungsrichtlinien**


![Optionen zum Veröffentlichen oder automatischen Anwenden einer Aufbewahrungsbezeichnung](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Schritt 4: Eine Asset-ID eingeben

Nachdem eine ereignisbasierte Bezeichnung auf Inhalte angewendet wurde, können Sie für jedes Element eine Objekt-ID eingeben. Ihre Organisation kann beispielsweise folgende Elemente verwenden:
  
- Produktcodes, um Inhalt nur für ein bestimmtes Produkt aufzubewahren.
    
- Projektcodes, um Inhalt nur für ein bestimmtes Projekt aufzubewahren.
    
- Mitarbeiter-IDs, die Sie zum Aufbewahren von Inhalten für eine bestimmte Person verwenden können.
    
Die Objekt-ID ist einfach eine weitere in SharePoint und OneDrive verfügbare Dokumenteigenschaft. Ihre Organisation verwendet möglicherweise bereits andere Dokumenteigenschaften und IDs zum Klassifizieren von Inhalten. In diesem Falle können Sie beim Erstellen eines Ereignisses auch diese Eigenschaften und Werte verwenden – siehe nachfolgenden Schritt 6. Wichtig ist hierbei, dass Sie in den Dokumenteigenschaften eine *Kombination aus Eigenschaft und Wert* verwenden müssen, um dieses Element mit einem Ereignistyp zu verknüpfen.
  
![Textfeld zum Eingeben einer Asset-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Schritt 5: Erstellen eines Ereignisses

Wenn eine bestimmte Instanz dieses Ereignistyps auftritt – z. B. wenn ein Produkt das Ende seiner Lebensdauer erreicht –, rufen Sie die Seite **Datensatzverwaltung** > **Ereignisse** im Microsoft 365 Compliance Center auf, und erstellen Sie ein Ereignis. Ein Ereignis wird durch seine Erstellung ausgelöst.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Schritt 6: Auswählen des gleichen Ereignistyps, der von der Bezeichnung in Schritt 2 verwendet wird

Wenn Sie ein Ereignis erstellen, wählen Sie den gleichen Ereignistyp aus, der von der Aufbewahrungsbezeichnung in Schritt 2 verwendet wird, z. B. „Product Lifetime“. Nur für Inhalte, denen Aufbewahrungsbezeichnungen des betreffenden Ereignistyps zugeordnet wurden, wird der Aufbewahrungszeitraum ausgelöst.
  
![Option in den Ereigniseinstellungen zum Auswählen eines Ereignistyps](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
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
  
- Um alle Inhalte mit einer bestimmten Aufbewahrungsbezeichnung zu finden, wählen Sie die Bedingung **Compliancebezeichnung**, und geben Sie dann den vollständigen oder teilweisen Bezeichnungsnamen ein, oder verwenden Sie einen Platzhalter. 
    
- Um alle Inhalte mit einer bestimmten Objekt-ID zu finden, geben Sie die **ComplianceAssetID**-Eigenschaft und einen Wert ein, und zwar im Format: `ComplianceAssetID:<value>`. 
    
Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Berechtigungen

Um Zugriff auf die Seite **Ereignisse** zu erhalten, müssen Prüfer Mitglied einer Rollengruppe sein, die die Rolle **Disposition Management** und die Rolle **View-Only Audit Logs** hat. Es wird empfohlen, eine neue Rollengruppe namens „Disposition Reviewers“ zu erstellen, diese beiden Rollen zu dieser Rollengruppe hinzuzufügen und anschließend Mitglieder zur Rollengruppe hinzuzufügen. 
  
Weitere Informationen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatisieren von Ereignissen mit PowerShell

Das Microsoft 365 Compliance Center ermöglicht es Ihnen, Ereignisse manuell zu erstellen, und unterstützt nicht das automatische Auslösen eines Ereignisses, wenn es eintritt. Sie können jedoch eine Rest-API verwenden, damit Ereignisse automatisch ausgelöst werden. Weitere Informationen finden Sie unter [Automatisieren der ereignisbasierten Aufbewahrung](automate-event-driven-retention.md).

Sie können die ereignisbasierte Aufbewahrung auch aus Ihren Geschäftsanwendungen heraus mithilfe eines PowerShell-Skripts automatisieren. PowerShell-Cmdlets für die ereignisbasierte Aufbewahrung:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

