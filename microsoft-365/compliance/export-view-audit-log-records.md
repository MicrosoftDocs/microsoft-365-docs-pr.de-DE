---
title: Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 exportieren, konfigurieren und anzeigen.
ms.openlocfilehash: 4cea867b46d3bda7d3b3a8cd38f3d01938da8764
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906866"
---
# <a name="export-configure-and-view-audit-log-records"></a>Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen

Nachdem Sie das Überwachungsprotokoll durchsucht und die Suchergebnisse in eine CSV-Datei heruntergeladen haben, enthält die Datei eine Spalte namens **AuditData**, die zusätzliche Informationen zu jedem Ereignis enthält. Die Daten in dieser Spalte sind als JSON-Objekt formatiert, das mehrere Eigenschaften enthält, die als *Property:Value-Paare* durch Kommas getrennt konfiguriert sind. Sie können das JSON-Transformationsfeature im Power Query Editor in Excel verwenden, um jede Eigenschaft im JSON-Objekt in der **Spalte AuditData** in mehrere Spalten zu teilen, sodass jede Eigenschaft eine eigene Spalte hat. Auf diese Weise können Sie eine oder mehrere dieser Eigenschaften sortieren und filtern, wodurch Sie die gesuchten Überwachungsdaten schnell finden können.

## <a name="step-1-export-audit-log-search-results"></a>Schritt 1: Exportieren von Überwachungsprotokollsuchergebnissen

Der erste Schritt ist das Durchsuchen des Überwachungsprotokolls und anschließendes Exportieren der Ergebnisse in einer CSV-Datei (Comma-Separated Value) auf den lokalen Computer.
  
1. Führen Sie [eine Überwachungsprotokollsuche aus,](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) und überarbeiten Sie die Suchkriterien bei Bedarf, bis Sie die gewünschten Ergebnisse haben.

2. Klicken **Sie auf Ergebnisse exportieren,** und wählen Sie Alle Ergebnisse herunterladen **aus.** 

   ![Klicken Sie auf Alle Ergebnisse herunterladen](../media/ExportAuditSearchResults.png)

   Mit dieser Option können Sie alle Überwachungsdatensätze aus der Überwachungsprotokollsuche exportieren, die Sie in Schritt 1 erstellt haben, und die Rohdaten aus dem Überwachungsprotokoll in eine CSV-Datei herunterladen. 

   Am unteren Rand des Fensters wird eine Meldung angezeigt, in der Sie aufgefordert werden, die CSV-Datei zu öffnen oder zu speichern. 

3. Klicken **Sie > Speichern unter,** und speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Es dauert eine Weile, bis viele Suchergebnisse heruntergeladen werden. Dies ist in der Regel bei der Suche nach allen Aktivitäten oder einem breiten Datumsbereich der Fall. Eine Meldung am unteren Rand des Fensters wird angezeigt, wenn die CSV-Datei heruntergeladen wurde.

   ![Meldung, die angezeigt wird, wenn der Download der CSV-Datei abgeschlossen ist](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > Aus seiner einzigen Suche in einer Protokolldatei können Sie maximal 50.000 Einträge in eine CSV-Datei herunterladen. Wenn 50.000 Einträge in die CSV-Datei heruntergeladen werden, können Sie wahrscheinlich davon ausgehen, dass mehr als 50.000 Ereignisse die Suchkriterien erfüllen. Um mehr als diesen Grenzwert zu exportieren, versuchen Sie, einen Datumsbereich zu verwenden, um die Anzahl der Überwachungsprotokolldatensätze zu reduzieren. Möglicherweise müssen Sie mehrere Suchläufe mit kleineren Datumsbereichen durchführen, um mehr als 50.000 Einträge zu exportieren.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>Schritt 2: Formatieren des exportierten Überwachungsprotokolls mit dem Power Query Editor

Im nächsten Schritt wird das JSON-Transformationsfeature im Power Query Editor in Excel verwendet, um jede Eigenschaft im JSON-Objekt in der **Spalte AuditData** in eine eigene Spalte zu teilen. Anschließend filtern Sie Spalten, um Datensätze basierend auf den Werten bestimmter Eigenschaften anzuzeigen. Dies kann Ihnen dabei helfen, die bestimmten Überwachungsdaten, die Sie suchen, schnell zu finden.

1. Öffnen Sie eine leere Arbeitsmappe in Excel für Office 365, Excel 2019 oder Excel 2016.

2. Klicken Sie **auf** der Registerkarte Daten in der **Gruppe & Daten transformieren** auf Von **Text/CSV**.

    ![Klicken Sie auf der Registerkarte Daten auf Von Text/CSV](../media/JSONTransformOpenCSVFile.png)

3. Öffnen Sie die CSV-Datei, die Sie in Schritt 1 heruntergeladen haben.

4. Klicken Sie im angezeigten Fenster auf **Daten transformieren.**

   ![Klicken Sie auf Daten transformieren](../media/JSONOpenPowerQuery.png)

   Die CSV-Datei wird im **Abfrage-Editor geöffnet.** Es gibt vier Spalten: **CreationDate**, **UserIds**, **Operations** und **AuditData**. Die **Spalte AuditData** ist ein JSON-Objekt, das mehrere Eigenschaften enthält. Im nächsten Schritt erstellen Sie eine Spalte für jede Eigenschaft im JSON-Objekt.

5. Klicken Sie in der Spalte **AuditData** mit der rechten Maustaste auf den Titel, klicken Sie auf **Transformieren,** und klicken Sie dann **auf JSON**. 

   ![Klicken Sie mit der rechten Maustaste auf die Spalte AuditData, klicken Sie auf Transformieren, und wählen Sie dann JSON aus.](../media/JSONTransform.png)

6. Klicken Sie in der oberen rechten Ecke der **Spalte AuditData** auf das Erweiterungssymbol.

   ![Klicken Sie in der Spalte AuditData auf das Erweiterungssymbol.](../media/JSONTransformExpandIcon.png)

   Eine Teilliste der Eigenschaften in den JSON-Objekten in der **Spalte AuditData** wird angezeigt.

7. Klicken **Sie auf Weitere Laden,** um alle Eigenschaften in den JSON-Objekten in der Spalte **AuditData** anzeigen.

   ![Klicken Sie auf Weitere Objekte laden, um alle Eigenschaften im JSON-Objekt anzeigen zu können.](../media/JSONTransformLoadJSONProperties.png)

   Sie können das Kontrollkästchen neben einer beliebigen Eigenschaft deaktivieren, die Sie nicht enthalten möchten. Das Entfernen von Spalten, die für Ihre Untersuchung nicht hilfreich sind, ist eine gute Möglichkeit, die Im Überwachungsprotokoll angezeigte Datenmenge zu reduzieren. 

   > [!NOTE]
   > Die im vorherigen Screenshot angezeigten JSON-Eigenschaften (nachdem Sie auf Weitere Laden **geklickt** haben) basieren auf den Eigenschaften in der Spalte **AuditData** aus den ersten 1.000 Zeilen in der CSV-Datei. Wenn nach den ersten 1.000 Zeilen unterschiedliche JSON-Eigenschaften in Datensätzen vorhanden sind, werden diese Eigenschaften (und eine entsprechende Spalte) nicht einbezogen, wenn die **Spalte AuditData** in mehrere Spalten aufgeteilt wird. Um dies zu verhindern, sollten Sie die Überwachungsprotokollsuche erneut ausführen und die Suchkriterien einengen, sodass weniger Datensätze zurückgegeben werden. Eine weitere Problemumgehung  besteht im Filtern von Elementen in der Spalte Vorgänge, um die Anzahl der Zeilen zu reduzieren (bevor Sie Schritt 5 oben ausführen), bevor Sie das JSON-Objekt in der **Spalte AuditData** transformieren.

   > [!TIP]
   > Klicken Sie zum Anzeigen eines Attributs in einer Liste  wie AuditData.AffectedItems in der oberen rechten Ecke der Spalte, aus der Sie ein Attribut ziehen möchten, auf das Symbol Erweitern, und wählen Sie Dann Erweitern zu **Neue Zeile aus.**  Von dort wird es ein Datensatz  sein, und Sie können in der oberen rechten Ecke der Spalte auf das Symbol Erweitern klicken, die Attribute anzeigen und das Symbol auswählen, das Sie anzeigen oder extrahieren möchten.

8. Gehen Sie wie folgt vor, um den Titel der Spalten zu formatieren, die für jede ausgewählte JSON-Eigenschaft hinzugefügt werden.

    - Deaktivieren Sie das **Kontrollkästchen Ursprünglicher Spaltenname als Präfix** verwenden, um den Namen der JSON-Eigenschaft als Spaltennamen zu verwenden. beispiel: **RecordType** oder **SourceFileName**.

    - Lassen Sie **das Kontrollkästchen Ursprünglicher Spaltenname als Präfix** verwenden aktiviert, um den Spaltennamen das Präfix AuditData hinzuzufügen. Beispiel: **AuditData.RecordType** oder **AuditData.SourceFileName**.

9. Klicken Sie auf **OK**.

    Die **Spalte AuditData** ist in mehrere Spalten aufgeteilt. Jede neue Spalte entspricht einer Eigenschaft im AuditData-JSON-Objekt. Jede Zeile in der Spalte enthält den Wert für die Eigenschaft. Wenn die Eigenschaft keinen Wert enthält, wird der *Nullwert* angezeigt. In Excel sind Zellen mit Nullwerten leer.
  
10. Klicken Sie **auf der Registerkarte** Start auf Schließen & **Laden,** um den Power Query Editor zu schließen und die transformierte CSV-Datei in einer Excel öffnen.

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>Verwenden von PowerShell zum Durchsuchen und Exportieren von Überwachungsprotokolleinträgen

Anstatt das Überwachungsprotokollsuchtool im Security & Compliance Center zu verwenden, können Sie das [Cmdlet Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell verwenden, um die Ergebnisse einer Überwachungsprotokollsuche in eine CSV-Datei zu exportieren. Anschließend können Sie das in Schritt 2 beschriebene Verfahren ausführen, um das Überwachungsprotokoll mithilfe des Power Query-Editors zu formatieren. Ein Vorteil der Verwendung des PowerShell-Cmdlets besteht in der Suche nach Ereignissen eines bestimmten Diensts mithilfe des *RecordType-Parameters.* Nachfolgend finden Sie einige Beispiele für die Verwendung von PowerShell zum Exportieren von Überwachungsdatensätzen in eine CSV-Datei, damit Sie das JSON-Objekt mithilfe des Power Query-Editors in der **Spalte AuditData** transformieren können, wie in Schritt 2 beschrieben.

Führen Sie in diesem Beispiel die folgenden Befehle aus, um alle Datensätze im Zusammenhang mit SharePoint zurückzukehren.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

Die Suchergebnisse werden in eine CSV-Datei mit dem Namen *PowerShellAuditlog* exportiert, die vier Spalten enthält: CreationDate, UserIds, RecordType, AuditData).

Sie können auch den Namen oder Enumerationswert für den Datensatztyp als Wert für den *RecordType-Parameter* verwenden. Eine Liste der Datensatztypnamen und der zugehörigen Enumerationswerte finden Sie in der *Tabelle AuditLogRecordType* in [Office 365 Management Activity API schema](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).

Sie können nur einen einzelnen Wert für den *RecordType-Parameter* angeben. Zum Suchen nach Überwachungsdatensätzen für andere Datensatztypen müssen Sie die beiden vorherigen Befehle erneut ausführen, um einen anderen Datensatztyp anzugeben und diese Ergebnisse an die ursprüngliche CSV-Datei anfügen. Führen Sie beispielsweise die folgenden beiden Befehle aus, um SharePoint aus demselben Datumsbereich zur Datei PowerShellAuditlog.csv hinzufügen.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>Tipps zum Exportieren und Anzeigen des Überwachungsprotokolls

Hier sind einige Tipps und Beispiele für das Exportieren und Anzeigen des Überwachungsprotokolls vor und nach der Verwendung des JSON-Transformationsfeatures zum Aufteilen der **Spalte AuditData** in mehrere Spalten.

- Filtern Sie **die Spalte RecordType** so, dass nur die Datensätze aus einem bestimmten Dienst- oder Funktionsbereich angezeigt werden. Wenn Sie beispielsweise Ereignisse im Zusammenhang mit SharePoint anzeigen möchten, wählen Sie **14** aus (der Enumerationswert für Datensätze, die durch SharePoint freigabeaktivitäten ausgelöst werden). Eine Liste der Dienste, die den in der Spalte **RecordType** angezeigten Enumerationswerten entsprechen, finden Sie unter [Detaillierte Eigenschaften im Überwachungsprotokoll](detailed-properties-in-the-office-365-audit-log.md).

- Filtern Sie die **Spalte Vorgänge,** um die Datensätze für bestimmte Aktivitäten anzeigen zu können. Eine Liste der meisten Vorgänge, die einer durchsuchbaren Aktivität im Überwachungsprotokollsuchtool im Security & Compliance Center entsprechen, finden Sie im Abschnitt "Überwachte Aktivitäten" unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).