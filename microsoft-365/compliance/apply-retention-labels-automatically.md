---
title: Aufbewahrungsbezeichnungen automatisch anwenden, um Inhalte beizubehalten oder zu löschen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erstellen Sie Aufbewahrungsbezeichnungen und veröffentlichen Sie diese automatisch, damit Sie diese Bezeichnungen automatisch auf Inhalte anwenden können, die Sie beibehalten möchten und nicht benötigte Inhalte löschen können.
ms.openlocfilehash: 9a4b19bd30201f5a5ff75b49ec384b451526b91b
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877302"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>Aufbewahrungsbezeichnungen automatisch anwenden, um Inhalte beizubehalten oder zu löschen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Dieses Szenario wird für [regulatorische Datensätze](records-management.md#records) nicht unterstützt.

Eines der leistungsstärksten Features von [Aufbewahrungsbezeichnungen](retention.md) ist die Möglichkeit, diese automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen. In diesem Fall müssen die Personen in Ihrer Organisation die Bezeichnungen nicht selber anwenden. Das wird von Microsoft 365 erledigt.
  
Das automatische Anwenden von Aufbewahrungsbezeichnungen ist aus den folgenden Gründen besonders effektiv:
  
- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.
    
- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.
    
- Benutzer müssen nicht mehr über Governance-Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.
    
Sie können Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, wenn diese Inhalte vertrauliche Informationen, Schlüsselwörter oder durchsuchbare Eigenschaften aufweisen oder [trainierbaren Klassifizierungsmerkmalen](classifier-get-started-with.md) entsprechen.

> [!TIP]
> Verwenden Sie jetzt in der Vorschau durchsuchbare Eigenschaften, um [Aufnahmen von Teams-Besprechungen](#microsoft-teams-meeting-recordings) zu ermitteln.

Folgende Prozesse können eine Aufbewahrungsbezeichnung entsprechend dieser Bedingungen automatisch anwenden:

![Diagramm der Rollen und Aufgaben für automatisch angewendete Bezeichnungen](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

Befolgen Sie für die beiden Administratorschritte die nachfolgenden Anweisungen.

> [!NOTE]
> Automatische Richtlinien verwenden dienstseitige Bezeichnungen mit Bedingungen, um Aufbewahrungsbezeichnungen automatisch anzuwenden. Sie können eine Aufbewahrungsbezeichnung auch automatisch mit einer Bezeichnungsrichtlinie anwenden. Gehen Sie dazu folgendermaßen vor: 
>
> - Wenden Sie eine Standardaufbewahrungsbezeichnung auf eine SharePoint-Bibliothek, einen Ordner oder eine Dokumentenmappe an, damit nicht beschriftete Inhalte in diesem Container automatisch gekennzeichnet werden
>- Automatisches Anwenden einer Aufbewahrungsbezeichnung auf E-Mails mithilfe von Regeln
>
> Informationen zu diesen Szenarien finden Sie unter [Erstellen und Anwenden von Aufbewahrungsbezeichnungen in Apps](create-apply-retention-labels.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-auto-apply-a-retention-label"></a>Aufbewahrungsbezeichnungen automatisch anwenden

Erstellen Sie zunächst Ihre Aufbewahrungsbezeichnung. Erstellen Sie anschließend eine automatische Richtlinie, um diese Bezeichnung anzuwenden. Wenn Sie Ihre Aufbewahrungsbezeichnung bereits erstellt haben, wechseln Sie zu [Erstellen einer automatischen Richtlinie](#step-2-create-an-auto-apply-policy).

Die Navigationsanweisungen sind davon abhängig, ob Sie die [Datensatzverwaltung](records-management.md)verwenden oder nicht. Es werden Anweisungen für beide Szenarios bereitgestellt.

### <a name="step-1-create-a-retention-label"></a>Schritt 1: Erstellen einer Aufbewahrungsbezeichnung.

1. Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:
    
    - Wenn Sie die Datensatzverwaltung verwenden:
        - **Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**
        
    - Wenn Sie die Datensatzverwaltung nicht verwenden:
       - **Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**
    
    Sehen Sie nicht sofort die gewünschte Option? Wählen Sie zuerst **Alle anzeigen** aus. 

2. Folgen Sie den Anweisungen des Assistenten. Wenn Sie die Datensatzverwaltung verwenden:
    
    - Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).
    
    - Wenn Sie Datensätze mithilfe der Aufbewahrungsbezeichnung deklarieren möchten, wählen Sie **Elemente als Datensätze markieren** oder **Elemente als regulatorische Datensätze markieren** aus. Weitere Informationen finden Sie unter [Aufbewahrungsbezeichnungen zum Deklarieren von Datensätzen konfigurieren](declare-records.md#configuring-retention-labels-to-declare-records).

3. Nachdem Sie die Bezeichnung erstellt haben und Ihnen die Optionen zum Veröffentlichen der Bezeichnung, zum automatischen Anwenden der Bezeichnung oder zum Speichern der Bezeichnung angezeigt werden: Wählen Sie **Diese Bezeichnung automatisch auf einen bestimmten Inhaltstyp anwenden** und dann **Fertig** aus, um den Assistenten zum Erstellen automatischer Bezeichnungen zu starten, der Sie direkt zu Schritt 2 des folgenden Verfahrens führt.

Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die Bezeichnungsbeschreibungen und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.


### <a name="step-2-create-an-auto-apply-policy"></a>Schritt 2: Erstellen einer Richtlinie für die automatische Anwendung

Wenn Sie eine Richtlinie für die automatische Anwendung erstellen, wird eine gewählte Aufbewahrungsbezeichnung automatisch anhand festgelegter Bedingungen auf Inhalte angewendet.

1. Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:
    
    - Wenn Sie die Datensatzverwaltung verwenden: **Informationsgovernance** :
        - **Lösungen** > **Datensatzverwaltung** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**
    
    - Wenn Sie die Datensatzverwaltung nicht verwenden:
        - **Lösungen** > **Informationgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**
    
    Sehen Sie nicht sofort die gewünschte Option? Wählen Sie zuerst **Alle anzeigen** aus. 

2. Folgen Sie den Eingabeaufforderungen im Assistenten zum Erstellen automatischer Bezeichnungen.
    
    Informationen zum Konfigurieren der Bedingungen, die zur automatischen Anwendung der Aufbewahrungsbezeichnung führen, finden Sie im Abschnitt [Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen](#configuring-conditions-for-auto-apply-retention-labels) auf dieser Seite.
    
    Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](retention.md#retention-label-policies-and-locations).

Wenn Sie eine vorhandene Richtlinie zum automatischen Anwenden von Bezeichnungen bearbeiten möchten, wählen Sie sie aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die ausgewählte Aufbewahrungsrichtlinie und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen

Aufbewahrungsbezeichnungen können automatisch auf Inhalte angewendet werden, wenn diese folgende Bedingungen erfüllen:

- [Der Inhalt enthält bestimmte vertrauliche Informationen.](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [Der Inhalt enthält bestimmte Stichwörter oder durchsuchbare Eigenschaften, die einer von Ihnen erstellten Abfrage entsprechen](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Eine Übereinstimmung für trainierbare Klassifizierungen](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Automatisches Anwenden von Bezeichnungen auf Inhalte mit bestimmten Typen von vertraulichen Informationen

Wenn Sie automatisch angewendete Richtlinien für Aufbewahrungsbezeichnungen für vertrauliche Informationen erstellen, wird dieselbe Liste von Richtlinienvorlagen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt. Jede Vorlage ist für die Suche nach bestimmten Typen vertraulicher Informationen vorkonfiguriert. Die hier gezeigte Vorlage sucht beispielsweise nach US ITIN-, SSN- und Reisepassnummern aus der **Datenschutz** -Kategorie und der Vorlage **USA – Daten mit persönlich identifizierbaren Informationen (PII)** :

![Richtlinienvorlagen für Arten von vertraulichen Informationen](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

Weitere Informationen zu Typen vertraulicher Informationen finden Sie unter [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md).

Nach der Auswahl einer Richtlinienvorlage können Sie beliebige Typen vertraulicher Informationen hinzufügen oder entfernen, und Sie können die Instanzenzahl und die Übereinstimmungsgenauigkeit ändern. Im folgenden Beispielscreenshot wird eine Aufbewahrungsbezeichnung nur dann automatisch angewendet, wenn Folgendes zutrifft:
  
- Der erkannte Typ vertraulicher Informationen hat eine Übereinstimmungsgenauigkeit (oder eine Zuverlässigkeitsstufe) von mindestens 75. Viele vertrauliche Informationstypen werden mit mehreren Mustern definiert. Dabei erfordert ein Muster mit einer höheren Übereinstimmungsgenauigkeit mehr Nachweise, um gefunden zu werden (z. B. Stichwörter, Datumsangaben oder Adressen), während ein Muster mit einer niedrigeren Übereinstimmungsgenauigkeit weniger Nachweise erfordert.  Je niedriger die **minimale** Übereinstimmungsgenauigkeit, desto einfacher können Inhalte die Bedingung erfüllen.

- Der Inhalt besteht aus zwischen einer und neun Instanzen von einem dieser drei vertraulichen Informationstypen. Sie können den **bis** -Wert löschen, sodass er in **Beliebig** geändert wird.

Weitere Informationen zu diesen Optionen finden Sie in der folgenden Anleitung aus der DLP-Dokumentation [Optimieren von Regeln, um Übereinstimmungen zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).
    
![Optionen zum Identifizieren von Typen vertraulicher Informationen](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Automatisches Anwenden von Bezeichnungen auf Inhalte mit Stichwörtern oder durchsuchbare Eigenschaften

Sie können automatische Bezeichnungen auf Inhalte mithilfe einer Abfrage anwenden, die bestimmte Wörter, Ausdrücke oder durchsuchbare Eigenschaften enthält. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie UND, ODER und NICHT verfeinern.

![Abfrage-Editor](../media/new-retention-query-editor.png)

Weitere Informationen zur Abfragesyntax, bei der die Keyword Query Language (KQL) angewendet wird, finden Sie unter [Syntaxreferenz für die Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

Abfragebasierte Bezeichnungen verwenden den Suchindex, um Inhalte zu identifizieren. Weitere Informationen zu den durchsuchbaren Eigenschaften, die Sie verwenden können, finden Sie unter:

- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
- [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> Obwohl bei den in SharePoint verwalteten Eigenschaften Aliase unterstützt werden, sollten Sie diese bei der Konfiguration von Aufbewahrungsbezeichnungen nicht verwenden. Sie müssen immer den tatsächlichen Namen der verwalteten Eigenschaft angeben, z. B „RefinableString01“.

Beispiele für Abfragen:

| Arbeitslast | Beispiel |
|:-----|:-----|
|Exchange   | `subject:"Quarterly Financials"` |
|Exchange   | `recipients:garthf@contoso.com` |
|SharePoint | `contenttype:contract` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a>Aufnahmen von Microsoft Teams-Besprechungen

> [!NOTE]
> Die Möglichkeit zum Aufbewahren und Löschen von Teams-Besprechungen wird in der Vorschau eingeführt und funktioniert nicht, bis Aufnahmen auf OneDrive oder Microsoft Office SharePoint Online gespeichert werden. Weitere Informationen finden Sie unter [Verwenden von OneDrive for Business und SharePoint Online oder Stream für Besprechungsaufzeichnungen](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).

Wenn Sie Aufnahmen von Microsoft Teams-Besprechungen ermitteln möchten, die in den OneDrive-Konten von Benutzern oder in SharePoint gespeichert sind, geben Sie im **Stichwortabfrage-Editor** Folgendes an:

``` 
ProgID:Media AND ProgID:Meeting
```

Diese Aufbewahrungsbezeichnung müssen Sie auch auf den OneDrive-Konten oder Microsoft Office SharePoint Online-Sites der jeweiligen Benutzer veröffentlichen, indem Sie eine Bezeichnungsrichtlinie erstellen. Meistens werden die Besprechungsaufnahmen auf OneDrive gespeichert, aber Kanalbesprechungen werden in Microsoft Office SharePoint Online gespeichert.

Wenn Sie die Richtlinie für Aufbewahrungsbezeichnungen für die automatische Anwendung gespeichert haben:

1. Wählen Sie die Registerkarte **Bezeichnungsrichtlinien** > **Veröffentlichen von Bezeichnungen**.

2. Wenn Sie zur Auswahl einer Bezeichnung aufgefordert werden, wählen Sie dieselbe Bezeichnung, die Sie für die Richtlinie für die automatische Anwendung ausgewählt haben, die die Aufzeichnungen von Teams-Besprechungen kennzeichnet.

3. Wenn Sie zur Angabe des Speicherorts aufgefordert werden, wählen Sie **Microsoft Office SharePoint Online-Sites** und **OneDrive-Konten** aus. Sie können die Standardeinstellung **Alle** beibehalten oder einzelne Speicherorte angeben, z. B. bestimmte OneDrive-Konten ein- oder ausschließen.

4. Schließen Sie den Assistenten ab, und speichern Sie diese Bezeichnungsrichtlinie.

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Automatisches Anwenden von Bezeichnungen auf Inhalte mithilfe von trainierbare Klassifizierungen

Wenn Sie die Option für eine trainierbare Klassifizierung auswählen, können Sie eine der integrierten Klassifizierungen oder eine benutzerdefinierte Klassifizierung auswählen. Zu den integrierten Klassifizierungen gehören **Lebensläufe** , **Quellcode** , **Gezielte Belästigung** , **Vulgäre Ausdrücke** und **Drohungen** :

![Trainierbare Klassifizierung auswählen](../media/retention-label-classifers.png)

> [!CAUTION]
> Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie diese integrierte Klassifizierung nicht mehr, und ändern Sie Ihre Geschäftsprozesse entsprechend, falls sie derzeit noch verwendet wird. Wir empfehlen stattdessen die Verwendung der integrierten Klassifizierungen **Gezielte Belästigung** , **Obszönitäten** und **Bedrohung**.

Wenn Sie eine Bezeichnung mithilfe dieser Option automatisch anwenden möchten, müssen SharePoint-Websites und -Postfächer mindestens 10 MB Daten umfassen.

Weitere Informationen über trainierbare Klassifizierer finden Sie unter [Weitere Informationen zu trainierbaren Klassifizierern (Vorschau)](classifier-learn-about.md).

> [!TIP]
> Wenn Sie trainierbare Klassifizierungsmerkmale für Exchange verwenden, lesen Sie die kürzlich veröffentlichte [Anleitung zum Neutrainieren einer Klassifizierung im Inhaltsexplorer (Vorschau)](classifier-how-to-retrain-content-explorer.md).

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Wie lange es dauert, bis Aufbewahrungsbezeichnungen wirksam werden

Wenn Sie Aufbewahrungsbezeichnungen automatisch anwenden, kann es bis zu sieben Tage dauern, bevor die Aufbewahrungsbezeichnungen auf alle vorhandenen Inhalte angewendet werden, die diesen Kriterien entsprechen.
  
![Diagramm, wann automatisch angewendete Bezeichnungen wirksam werden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

Wenn die erwarteten Bezeichnungen nach sieben Tagen nicht erscheinen, überprüfen Sie den **Status** der Richtlinie für die automatische Anwendung, indem Sie sie auf der Seite **Richtlinien für Bezeichnungen** im Compliance Center auswählen. Wenn der Status **Aus (Fehler)** angezeigt wird und in den Details für die Standorte eine Meldung angezeigt wird, dass die Bereitstellung der Richtlinie (für SharePoint) oder der Versuch der Neuverteilung der Richtlinie (für OneDrive) länger als erwartet dauert, versuchen Sie, den PowerShell-Befehl [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) auszuführen, um die Richtlinienverteilung erneut zu versuchen:

1. [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Führen Sie den folgenden Befehl aus:
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```



## <a name="updating-retention-labels-and-their-policies"></a>Aktualisieren von Aufbewahrungsbezeichnungen und der entsprechenden Richtlinien

Wenn Sie eine Aufbewahrungsbezeichnung oder eine Richtlinie für die automatische Anwendung bearbeiten, und die Aufbewahrungsbezeichnung bereits auf Inhalte angewendet wird, werden Ihre aktualisierten Einstellungen automatisch zusätzlich auf diese Inhalte sowie auf neu identifizierte Inhalte angewendet.

Einige Einstellungen können nicht geändert werden, nachdem die Bezeichnung oder Richtlinie erstellt und gespeichert wurde. Dazu gehören:
- Die Aufbewahrungseinstellungen außer dem Aufbewahrungszeitraum, es sei denn, Sie haben die Bezeichnung so konfiguriert, dass der Inhalt basierend auf dem Zeitpunkt der Erstellung beibehalten oder gelöscht wird.
- Die Option zum Markieren von Elementen als Datensatz.

## <a name="next-steps"></a>Nächste Schritte

Unter [Verwenden von Aufbewahrungsbezeichnungen zum Verwalten des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md) finden Sie ein Beispielszenario, in dem eine automatisch angewendete Richtlinie für Aufbewahrungsbezeichnungen mit verwalteten Eigenschaften in SharePoint und die ereignisbasierte Aufbewahrung zum Starten des Aufbewahrungszeitraums verwendet wird.
