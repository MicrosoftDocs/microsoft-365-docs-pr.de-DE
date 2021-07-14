---
title: Dateiplan verwenden für die Verwaltung von Aufbewahrungsbezeichnungen über den gesamten Inhaltslebenszyklus hinweg
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Der Dateiplan bietet erweiterte Verwaltungsfunktionen für Aufbewahrungsbezeichnungen.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 920a613cdc3a32267415d42cebe962e62ff6831a
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419763"
---
# <a name="use-file-plan-to-manage-retention-labels"></a>Dateiplan zum Verwalten von Aufbewahrungsbezeichnungen verwenden

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Sie können zwar Aufbewahrungsbezeichnungen von **Informationsgovernance** im Microsoft 365 Compliance Center erstellen und verwalten, aber der Dateiplan aus **Datensatzverwaltung** verfügt über zusätzliche Verwaltungsfunktionen:

- Sie können die Aufbewahrungsbezeichnungen in einem Stapel erstellen, indem Sie die relevanten Informationen aus einer Kalkulationstabelle importieren.

- Sie können die Informationen aus vorhandenen Aufbewahrungsbezeichnungen für die Analyse und Offline-Zusammenarbeit exportieren.

- Weitere Informationen zu den Aufbewahrungsbezeichnungen werden angezeigt, um die Einstellungen aller Aufbewahrungsbezeichnungen in einer Ansicht anzuzeigen.

- Dateiplandeskriptoren unterstützen zusätzliche und optionale Informationen für jede Bezeichnung.

Der Dateiplan kann für alle Aufbewahrungsbezeichnungen verwendet werden, auch wenn sie Inhalt nicht als Datensatz markieren.

![Seite "Dateiplan"](../media/compliance-file-plan.png)

Informationen zu den Aufbewahrungsbezeichnungen und deren Verwendung finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).

## <a name="accessing-file-plan"></a>Zugriff auf den Dateiplan

Um auf den Dateiplan zuzugreifen, müssen Sie über eine der folgenden Administratorrollen verfügen:
    
- Aufbewahrungs-Manager

- Aufbewahrungs-Manager (schreibgeschützt)

Wechseln Sie im Microsoft 365 Compliance Center zu **Lösungen** > **Datensatzverwaltung** > **Dateiplan**. 

Wenn **Datensatzverwaltung** im Navigationsbereich nicht angezeigt wird, scrollen Sie nach unten und wählen Sie **Alle anzeigen** aus.

![Seite "Dateiplan"](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a>Navigieren in Ihrem Dateiplan

Wenn Sie bereits Aufbewahrungsbezeichnungen aus **Informationsgovernance** im Microsoft 365 Compliance Center erstellt haben, werden diese Bezeichnungen automatisch in Ihrem Dateiplan angezeigt. 

Wenn Sie nun im Dateiplan Aufbewahrungsbezeichnungen erstellen, stehen diese auch über **Informationsgovernance** zur Verfügung, wenn die Bezeichnungen nicht so konfiguriert sind, dass Inhalte als Datensatz gekennzeichnet werden.

Auf der Seite **Dateiplan** werden alle Ihre Bezeichnungen mit Ihrem Status und Ihren Einstellungen, optionalen Dateiplandeskriptoren, einer Exportoption zum Analysieren oder Aktivieren von Offline-Überprüfungen Ihrer Bezeichnungen und einer Importoption zum Erstellen von Aufbewahrungsbezeichnungen angezeigt. 

### <a name="label-settings-columns"></a>Spalten mit Bezeichnungseinstellungen

Alle Spalten, mit Ausnahme der Bezeichnung **Namen**, können angezeigt oder ausgeblendet werden, indem Sie die Option **Spalten anpassen** auswählen. Standardmäßig werden in den ersten Spalten Informationen zum Bezeichnungsstatus und den zugehörigen Einstellungen angezeigt: 

- **Status** gibt an, ob die Bezeichnung in einer Bezeichnungsrichtlinie enthalten ist oder dass die Richtlinie automatisch angewendet wird (**aktive**) oder nicht (**inaktive**).

- **Basierend auf** wird angegeben, wie oder wann der Aufbewahrungszeitraum beginnt. Gültige Werte:
    - Ereignis
    - Zeitpunkt der Erstellung
    - Zuletzt geändert
    - Zeitpunkt der Bezeichnung

- **Ist-Datensatz** identifiziert, ob das Element als Datensatz gekennzeichnet ist, wenn die Bezeichnung angewendet wird. Gültige Werte:
    - Nein
    - Ja
    - Yes (Vorgeschrieben)

- **Aufbewahrungsdauer** bezeichnet den Aufbewahrungszeitraum. Gültige Werte:
    - Tage
    - Monate
    - Jahre
    - Für immer
    - Keine

- **Löschungstyp** gibt an, was mit dem Inhalt am Ende des Aufbewahrungszeitraums geschieht. Gültige Werte:
    - Keine Aktion
    - Automatisch löschen
    - Überprüfung erforderlich

### <a name="file-plan-descriptors-columns"></a>Spalten mit Dateiplandeskriptoren

Mit dem Dateiplan können Sie weitere Informationen als Teil der Aufbewahrungsbezeichnungen hinzuzufügen. Diese Dateiplandeskriptoren bieten weitere Optionen zur Verbesserung von Verwaltung und Organisation der zu beschriftenden Inhalte.

Standardmäßig werden in den nächsten Spalten, beginnend mit **Referenz-ID**, diese optionalen Dateiplandeskriptoren angezeigt, die Sie beim Erstellen einer Aufbewahrungsbezeichnung oder beim Bearbeiten einer vorhandene Bezeichnung angeben können. 

Zum Einstieg gibt es einige besondere Werte für die folgenden Dateiplandeskriptoren: 
- Geschäftsfunktion/-abteilung
- Kategorie
- Autoritätstyp
- Bestimmung/Zitat 

Beispiel für Dateiplandeskriptoren beim Erstellen oder Bearbeiten einer Aufbewahrungsbezeichnung:

![Dateiplandeskriptoren beim Erstellen oder Bearbeiten einer Aufbewahrungsbezeichnung](../media/file-plan-descriptors.png)

Beispielansicht der Spalten mit Dateiplandeskriptoren:

![Spalten mit Dateiplandeskriptoren](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a>Exportieren aller Aufbewahrungsbezeichnungen zum Analysieren oder Aktivieren von Offline-Überprüfungen

Aus dem Dateiplan können Sie die Details aller Aufbewahrungsbezeichnungen in eine CSV-Datei exportieren, mit deren Hilfe Sie regelmäßige Complianceüberprüfungen, mit den Beteiligten der Datengovernance Ihrer Organisation, durchführen können.

Um alle Aufbewahrungsbezeichnungen zu exportieren, gehen Sie zur Seite **Dateiplan** und klicken auf **Exportieren**:

![Option zum Exportieren des Dateiplans](../media/compliance-file-plan-export-labels.png)

Eine CSV-Datei mit allen vorhandenen Aufbewahrungsbeschriftungen wird geöffnet. Zum Beispiel:

![CSV-Datei, in der alle Aufbewahrungsbeschriftungen angezeigt werden](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importieren von Aufbewahrungsbezeichnungen in Ihren Dateiplan

Im Dateiplan können Sie neue Aufbewahrungsbezeichnungen per Massenimport importieren, indem Sie eine CSV-Datei mit einem bestimmten Format verwenden. Nachdem die Bezeichnungen importiert wurden, können Sie Änderungen in der CSV-Datei vornehmen und die Datei erneut importieren, um die Massenbearbeitung vorhandener Aufbewahrungsbezeichnungen zu vereinfachen.

So importieren Sie neue Aufbewahrungsbezeichnungen und ändern vorhandene Aufbewahrungsbezeichnungen: 

1. Klicken Sie auf der Seite **Dateiplan** auf **Importieren**, um die Seite **Ihren Dateiplan ausfüllen und importieren** zu verwenden:

   ![Option zum Importieren des Dateiplans](../media/compliance-file-plan-import-labels.png)

   ![Option zum Herunterladen einer leeren Vorlage für den Dateiplan](../media/file-plan-blank-template-option.png)

2. Laden Sie, wie angewiesen, eine leere Vorlage herunter:

   ![Leere Vorlage eines Dateiplans wird in Excel geöffnet](../media/file-plan-blank-template.png)

3. Füllen Sie die Vorlage aus. Verwenden Sie die folgenden Informationen, die jeweils die Eigenschaften und ihre gültigen Werte beschreiben. Für den Import haben einige Werte eine maximale Länge:
    
    - **LabelName**: Maximale Länge von 64 Zeichen
    - **Kommentar** und **Notizen**: Maximale Länge von 1024 Zeichen
    - Alle anderen Werte: Unbegrenzte Länge
    <br/>
    
   |Eigenschaft|Typ|Erforderlich|Gültige Werte|
   |:-----|:-----|:-----|:-----|
   |LabelName|Zeichenfolge|Ja|Diese Eigenschaft gibt den Namen der Aufbewahrungsbezeichnung an und muss auf Ihrem Mandanten eindeutig sein.|
   |Kommentar|Zeichenfolge|Nein|Verwenden Sie diese Eigenschaft, um eine Beschreibung der Aufbewahrungsbezeichnung für Administratoren hinzuzufügen. Diese Beschreibung wird nur Administratoren angezeigt, die die Aufbewahrungsbeschreibung im Compliance Center verwalten.|
   |Notes|Zeichenfolge|Nein|Verwenden Sie diese Eigenschaft, um eine Beschreibung der Aufbewahrungsbezeichnung für Benutzer hinzuzufügen. Diese Beschreibung wird angezeigt, wenn Benutzer den Mauszeiger über die Bezeichnung in Apps wie Outlook, SharePoint und OneDrive bewegen. Wenn Sie diese Eigenschaft leer lassen, wird eine Standardbeschreibung angezeigt, in der die Aufbewahrungseinstellungen der Bezeichnung erläutert werden. |
   |IsRecordLabel|Zeichenfolge|Nein, es sei denn, **Regulatory** ist **TRUE**|Diese Eigenschaft gibt an, ob die Bezeichnung eine Datensatzbezeichnung ist. Gültige Werte sind:</br>**TRUE**: die Bezeichnung kennzeichnet das Element als Datensatz. Das Element kann daher nicht gelöscht werden. </br>**FALSE**: die Bezeichnung kennzeichnet den Inhalt nicht als Datensatz. Dies ist der Standardwert. </br> </br> Gruppenabhängigkeiten: Wenn diese Eigenschaft angegeben wird, müssen auch „RetentionAction“, „RetentionDuration“ und „RetentionType“ angegeben werden.|
   |RetentionAction|Zeichenfolge|Nein, es sei denn, **RetentionDuration**, **RetentionType** oder **ReviewerEmail** sind angegeben|Diese Eigenschaft gibt an, welche Aktion auszuführen ist, nachdem der durch die RetentionDuration-Eigenschaft angegebene Wert (falls angegeben) abläuft. Gültige Werte sind:</br>**Delete**: Elemente, die älter als der von der RetentionDuration-Eigenschaft angegebene Wert sind, werden gelöscht.</br>**Keep**: Elemente werden für die durch die RetentionDuration-Eigenschaft festgelegte Dauer beibehalten. Nach Ablauf dieses Zeitraums wird nichts ausgeführt. </br>**KeepAndDelete**: Elemente werden für die durch die RetentionDuration-Eigenschaft festgelegte Dauer beibehalten. Nach Ablauf dieses Zeitraums werden sie gelöscht. </br> </br> Gruppenabhängigkeiten: Wenn diese Eigenschaft angegeben wird, müssen auch „RetentionDuration“ und „RetentionType“ angegeben werden. |
   |RetentionDuration|Zeichenfolge|Nein, es sei denn, **RetentionAction** oder **RetentionType** sind angegeben|Diese Eigenschaft gibt die Anzahl der Tage an, die der Inhalt aufbewahrt werden soll. Gültige Werte sind:</br>**Unlimited**: Elemente werden auf unbestimmte Zeit aufbewahrt. </br>**_n_*: Eine positive ganze Zahl in Tagen, z. B. **365**. Die maximal unterstützte Anzahl beträgt 24.855, also 68 Jahre. Wenn Sie mehr als diesen Höchstwert benötigen, verwenden Sie stattdessen „Unlimited“.</br> </br> Gruppenabhängigkeiten: Wenn diese Eigenschaft angegeben wird, müssen auch „RetentionAction“ und „RetentionType“ angegeben werden.
   |RetentionType|Zeichenfolge|Nein, es sei denn, **RetentionAction** oder **RetentionDuration** sind angegeben|Diese Eigenschaft gibt an, ob die Aufbewahrungsdauer (falls angegeben) aus dem Datum der Inhaltserstellung, des Ereignisses, Bezeichnung oder der letzten Änderung berechnet wird. Gültige Werte sind:</br>**CreationAgeInDays**</br>**EventAgeInDays**</br>**TaggedAgeInDays**</br>**ModificationAgeInDays** </br> </br> Gruppenabhängigkeiten: Wenn diese Eigenschaft angegeben wird, müssen auch „RetentionAction“ und „RetentionDuraction“ angegeben werden.|
   |ReviewerEmail|SmtpAddress|Nein|Wird diese Eigenschaft angegeben, wird eine Dispositionsüberprüfung ausgelöst, sobald die Aufbewahrungsdauer abgelaufen ist. Diese Eigenschaft gibt die E-Mail-Adresse einer Prüferin oder eines Prüfers für die Aufbewahrungsaktionen **KeepAndDelete** an. </br> </br> Sie können die E-Mail-Adressen einzelner Benutzer, Verteiler- oder Sicherheitsgruppen auf Ihrem Mandanten einschließen. Mehrere E-Mail-Adressen können durch Semikolons (;) getrennt angegeben werden. </br> </br> Gruppenabhängigkeiten: Wenn diese Eigenschaft angegeben wird, müssen auch **RetentionAction** (mit dem Wert **KeepAndDelete**), **RetentionDuration** und **RetentionType** angegeben werden.|
   |ReferenceId|Zeichenfolge|Nein|Diese Eigenschaft gibt den Wert an, der im Dateiplandeskriptor **Referenz-ID** angezeigt wird und den Sie als eindeutigen Wert für Ihre Organisation verwenden können.| 
   |DepartmentName|Zeichenfolge|Nein|Diese Eigenschaft gibt den Wert an, der in der Dateiplanbeschreibung **Funktion/Abteilung** angezeigt wird.|
   |Kategorie|Zeichenfolge|Nein|Diese Eigenschaft gibt den Wert an, der in der Dateiplanbeschreibung **Kategorie** angezeigt wird.|
   |SubCategory|Zeichenfolge|Nein|Diese Eigenschaft gibt den Wert an, der in der Dateiplanbeschreibung **Unterkategorie** angezeigt wird.|
   |AuthorityType|Zeichenfolge|Nein|Diese Eigenschaft gibt den Wert an, der in der Dateiplanbeschreibung **Autoritätstyp** angezeigt wird.|
   |CitationName|Zeichenfolge|Nein|Diese Eigenschaft gibt das Zitat an, das im Dateiplandeskriptor **Bereitstellung/Zitat** angezeigt wird. Beispielsweise „Sarbanes-Oxley Act von 2002“. |
   |CitationUrl|Zeichenfolge|Nein|Diese Eigenschaft gibt die URL an, die in der Dateiplanbeschreibung **Bereitstellung/Zitat** angezeigt wird.|
   |CitationJurisdiction|Zeichenfolge|Nein|Diese Eigenschaft gibt die Zuständigkeit oder Behörde an, die in der Dateiplanbeschreibung **Bereitstellung/Zitat** angezeigt wird, z. B. „U.S Securities and Exchange Commission (SEC)“.|
   |Behördlich|Zeichenfolge|Nein|Diese Eigenschaft gibt an, ob die Bezeichnung den Inhalt als regulatorischen Datensatz markiert, der [restriktiver](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) als ein einfacher Datensatz ist. Um diese Bezeichnungskonfiguration verwenden zu können, muss Ihr Mandant so konfiguriert sein, dass [die Option zum Markieren von Inhalt als regulatorischer Datensatz](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) angezeigt wird. Andernfalls schlägt die Importüberprüfung fehl. Gültige Werte sind: </br>**TRUE**: Die Bezeichnung kennzeichnet das Element als regulatorischen Datensatz. Sie müssen auch die Eigenschaft **IsRecordLabel** auf TRUE festlegen.</br>**FALSE**: die Bezeichnung kennzeichnet den Inhalt nicht als regulatorischen Datensatz. Dies ist der Standardwert.|
   |EventType|Zeichenfolge|Nein, es sei denn, **RetentionType** ist auf **EventAgeInDays** festgelegt|Diese Eigenschaft gibt einen Ereignistyp an, der für [ereignisbasierte Aufbewahrung](event-driven-retention.md) verwendet wird. Geben Sie einen vorhandenen Ereignistyp an, der unter **Datensatzverwaltung** > **Ereignisse** > **Ereignistypen verwalten** angezeigt wird. Verwenden Sie alternativ das Cmdlet [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype), um die verfügbaren Ereignistypen anzuzeigen. Es gibt zwar einige integrierte Ereignistypen, z. B. **Employee-Aktivität** und **Produktlebensdauer**, Sie können aber auch eigene Ereignistypen erstellen. </br> </br> Wenn Sie Ihren eigenen Ereignistyp festlegen, muss er vor dem Import vorhanden sein, da der Name im Rahmen des Importvorgangs überprüft wird.|
   |||

   Nachfolgend finden Sie ein Beispiel für die Vorlage mit den Informationen zu Aufbewahrungsbezeichnungen.

   ![Dateiplanvorlage mit ausgefüllten Informationen](../media/file-plan-filled-out-template.png)

4. Klicken Sie unter Schritt 3 auf der Seite **Ausfüllen und Importieren eines Dateiplans** auf **Nach Dateien suchen**, um die ausgefüllte Vorlage hochzuladen, und wählen Sie dann **Weiter** aus.

   Der Dateiplan lädt die Datei hoch, überprüft die Einträge und zeigt die Importstatistiken an.

   ![Dateiplan-Importstatistiken](../media/file-plan-import-statistics.png)

5. Abhängig von den Überprüfungsergebnissen:
    
    - Wenn die Überprüfung fehlschlägt: Notieren Sie sich die Zeilennummer und den Spaltennamen, um sie in der Importdatei zu korrigieren. Wählen Sie **Schließen** und dann zum Bestätigen **Ja** aus. Korrigieren Sie die Fehler in der Datei, und speichern Sie sie. Wählen Sie die Option **Importieren** erneut aus, und kehren Sie zu Schritt 4 zurück.
    
    - Wenn die Überprüfung erfolgreich ist, können Sie **Go Live** auswählen, um die Aufbewahrungsbezeichnungen in Ihrem Mandanten verfügbar zu machen. Oder schließen Sie die Seite mithilfe des Schließen-Symbols, und wählen Sie **Ja** aus, um zu bestätigen, dass Sie den Assistenten schließen möchten, ohne die Aufbewahrungsbezeichnungen zurzeit in Ihrem Mandanten verfügbar zu machen.

Nachdem die importierten Bezeichnungen zu Ihrem Mandanten hinzugefügt wurden, können Sie sie nun einer neuen Richtlinie für die Aufbewahrungsbezeichnungen hinzufügen oder automatisch anwenden. Sie können diesen Schritt direkt über die Seite **Dateiplan** vornehmen, indem Sie die Dropdownliste von **+ Bezeichnung erstellen** und dann **Richtlinie zum Veröffentlichen von Bezeichnungen** oder **Richtlinie für Bezeichnung automatisch anwenden** auswählen.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien finden Sie im folgenden Leitfaden:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)