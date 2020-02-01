---
title: Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: Nachdem Sie die Ergebnisse einer Office 365-Überwachungsprotokoll Suche in eine CSV-Datei exportiert und heruntergeladen haben, können Sie das JSON-Transformations Feature im Power Query-Editor in Excel verwenden, um die einzelnen Eigenschaften im JSON-Objekt in der Auditdata-Spalte in eine eigene Spalte aufzuteilen. Auf diese Weise können Sie schnell die spezifischen Überwachungsdaten Auffinden, nach denen Sie suchen.
ms.openlocfilehash: de116db76597c6eb7966541c3cc0f34f91c06c70
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594606"
---
# <a name="export-configure-and-view-audit-log-records"></a>Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen

Nachdem Sie das Office 365 Überwachungsprotokoll durchsucht und die Suchergebnisse in eine CSV-Datei heruntergeladen haben, enthält die Datei eine Spalte mit dem Namen **Auditdata**, die zusätzliche Informationen zu den einzelnen Ereignissen enthält. Die Daten in dieser Spalte werden als JSON-Objekt formatiert, das mehrere Eigenschaften enthält, die als *Eigenschaft: Wert-* Paare durch Kommas getrennt konfiguriert sind. Sie können das JSON-Transformations Feature im Power Query-Editor in Excel verwenden, um jede Eigenschaft im JSON-Objekt in der **Auditdata** -Spalte in mehrere Spalten aufzuteilen, sodass jede Eigenschaft eine eigene Spalte aufweist. Auf diese Weise können Sie eine oder mehrere dieser Eigenschaften sortieren und Filtern, die Ihnen helfen, die gewünschten Überwachungsdaten schnell zu finden.

## <a name="step-1-export-audit-log-search-results"></a>Schritt 1: Exportieren von Überwachungsprotokoll-Suchergebnissen

Der erste Schritt besteht darin, das Überwachungsprotokoll zu durchsuchen und die Ergebnisse dann in einer CSV-Datei (Comma-Separated Value) auf Ihren lokalen Computer zu exportieren.
  
1. Führen Sie eine [Überwachungsprotokoll Suche](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) aus, und überprüfen Sie bei Bedarf die Suchkriterien, bis Sie die gewünschten Ergebnisse haben.
    
2. Klicken Sie auf **Ergebnisse exportieren** , und wählen Sie **alle Ergebnisse herunterladen**aus. 
    
   ![Klicken Sie auf alle Ergebnisse herunterladen.](media/ExportAuditSearchResults.png)

   Diese Option zum Exportieren aller Überwachungsdatensätze aus der Überwachungsprotokoll Suche, die Sie in Schritt 1 ausgeführt haben, und zum Herunterladen der Rohdaten aus dem Überwachungsprotokoll in eine CSV-Datei. 

   Unten im Fenster wird eine Meldung angezeigt, in der Sie aufgefordert werden, die CSV-Datei zu öffnen oder zu speichern. 

3. Klicken Sie auf **speichern #a0** speichern unter, und speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Es dauert eine Weile, bis viele Suchergebnisse heruntergeladen wurden. Dies ist normalerweise der Fall, wenn Sie nach allen Aktivitäten oder einem breiten Datumsbereich suchen. Eine Meldung unten im Fenster wird angezeigt, wenn die CSV-Datei heruntergeladen wird.
 
   ![Meldung, die angezeigt wird, wenn die CSV-Datei heruntergeladen wird](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > Aus seiner einzigen Suche in einer Protokolldatei können Sie maximal 50.000 Einträge in eine CSV-Datei herunterladen. Wenn 50.000 Einträge in die CSV-Datei heruntergeladen werden, können Sie wahrscheinlich davon ausgehen, dass mehr als 50.000 Ereignisse die Suchkriterien erfüllen. Um mehr als diesen Grenzwert zu exportieren, verwenden Sie einen Datumsbereich, um die Anzahl der Überwachungsprotokolleinträge zu verringern. Möglicherweise müssen Sie mehrere Suchläufe mit kleineren Datumsbereichen durchführen, um mehr als 50.000 Einträge zu exportieren.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>Schritt 2: Formatieren des exportierten Überwachungsprotokolls mit dem Power Query-Editor

Im nächsten Schritt wird das JSON-Transformations Feature im Power Query-Editor in Excel verwendet, um die einzelnen Eigenschaften im JSON-Objekt in der **Auditdata** -Spalte in eine eigene Spalte aufzuteilen. Anschließend Filtern Sie Spalten, um Datensätze basierend auf den Werten bestimmter Eigenschaften anzuzeigen. Auf diese Weise können Sie schnell die spezifischen Überwachungsdaten Auffinden, nach denen Sie suchen.

1. Öffnen Sie eine leere Arbeitsmappe in Excel für Office 365, Excel 2019 oder Excel 2016.
    
2.  Klicken Sie auf der Registerkarte **Daten** in der Gruppe **#a0 Transformationsdaten abrufen** auf **von Text/CSV**.

    ![Klicken Sie auf der Registerkarte Daten auf aus Text/CSV.](media/JSONTransformOpenCSVFile.png)

3. Öffnen Sie die CSV-Datei, die Sie in Schritt 1 heruntergeladen haben.
    
4. Klicken Sie im angezeigten Fenster auf **Daten transformieren**.

   ![Klicken Sie auf Daten transformieren](media/JSONOpenPowerQuery.png)

Die CSV-Datei wird im **Abfrage-Editor**geöffnet. Es gibt vier Spalten: **CreationDate**, **userids**, **Operations**und **Auditdata**. Die **Auditdata** -Spalte ist ein JSON-Objekt, das mehrere Eigenschaften enthält. Im nächsten Schritt erstellen Sie eine Spalte für jede Eigenschaft im JSON-Objekt.
    
5. Klicken Sie mit der rechten Maustaste auf den Titel in der Spalte **Auditdata** , klicken Sie auf **transformieren**, und klicken Sie dann auf **JSON**. 
 
   ![Klicken Sie mit der rechten Maustaste auf die Spalte Auditdata, klicken Sie auf Transformation, und wählen Sie dann JSON aus.](media/JSONTransform.png)

6. Klicken Sie in der oberen rechten Ecke der Spalte **Auditdata** auf das Symbol erweitern.
    
   ![Klicken Sie in der Spalte Auditdata auf das Erweiterungssymbol](media/JSONTransformExpandIcon.png)

   Eine unvollständige Liste der Eigenschaften in den JSON-Objekten in der **Auditdata** -Spalte wird angezeigt.

7. Klicken Sie auf **mehr laden** , um alle Eigenschaften in den JSON-Objekten in der **Auditdata** -Spalte anzuzeigen.

   ![Klicken Sie auf mehr laden, um alle Eigenschaften im JSON-Objekt anzuzeigen.](media/JSONTransformLoadJSONProperties.png)

   Sie können das Kontrollkästchen neben einer Eigenschaft, die Sie nicht einschließen möchten, aufheben. Das Ausschließen von Spalten, die für Ihre Untersuchung nicht hilfreich sind, ist eine gute Möglichkeit, die im Überwachungsprotokoll angezeigte Datenmenge zu reduzieren. 

   > [!NOTE]
   > Die im vorherigen Screenshot angezeigten JSON-Eigenschaften (nachdem Sie auf **mehr laden**klicken) basieren auf den Eigenschaften, die in der **Auditdata** -Spalte aus den ersten 1.000-Zeilen in der CSV-Datei gefunden wurden. Wenn in Datensätzen nach den ersten 1.000-Zeilen unterschiedliche JSON-Eigenschaften vorhanden sind, werden diese Eigenschaften (und eine entsprechende Spalte) nicht berücksichtigt, wenn die **Auditdata** -Spalte in mehrere Spalten aufgeteilt wird. Um dies zu verhindern, sollten Sie die Überwachungsprotokoll Suche erneut durchführen und die Suchkriterien eingrenzen, sodass weniger Datensätze zurückgegeben werden. Eine weitere Problemumgehung besteht darin, Elemente in der Spalte **Vorgänge** zu filtern, um die Anzahl der Zeilen (vor dem Ausführen von Schritt 5 oben) zu reduzieren, bevor das JSON-Objekt in der **Auditdata** -Spalte transformiert wird.

8. Führen Sie eine der folgenden Aktionen aus, um den Titel der Spalten zu formatieren, die für jede ausgewählte JSON-Eigenschaft hinzugefügt werden.

    - Deaktivieren Sie das Kontrollkästchen **ursprünglichen Spaltennamen als Präfix verwenden** , um den Namen der JSON-Eigenschaft als Spaltennamen zu verwenden. beispielsweise **RecordType** oder **sourceFileName**.
    
   - Lassen Sie das Kontrollkästchen **ursprünglichen Spaltennamen als Präfix verwenden** aktiviert, um dem Spaltennamen das Auditdata-Präfix hinzuzufügen. Beispiel: **Auditdata. RecordType** oder **Auditdata. sourceFileName**.

9. Klicken Sie auf **OK**.
    
    Die **Auditdata** -Spalte wird in mehrere Spalten aufgeteilt. Jede neue Spalte entspricht einer Eigenschaft im JSON-Objekt Auditdata. Jede Zeile in der Spalte enthält den Wert für die Eigenschaft. Wenn die Eigenschaft keinen Wert enthält, wird der *null* -Wert angezeigt. In Excel sind Zellen mit NULL-Werten leer.
  
10. Klicken Sie auf der Registerkarte **Start** auf **#a0 Laden schließen** , um den Power Query-Editor zu schließen und die transformierte CSV-Datei in einer Excel-Arbeitsmappe zu öffnen. 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>Tipps zum Exportieren und Anzeigen des Überwachungsprotokolls

Im folgenden finden Sie einige Tipps und Beispiele für das Exportieren und Anzeigen des Überwachungsprotokolls vor und nach dem Verwenden des JSON-Transformations Features zum Aufteilen der **Auditdata** -Spalte in mehrere Spalten.

- Filtern Sie die **RecordType** -Spalte, um nur die Datensätze eines bestimmten Office 365 Diensts oder Funktionsbereichs anzuzeigen. Um beispielsweise Ereignisse im Zusammenhang mit SharePoint-Freigabe anzuzeigen, wählen Sie **14** (enum-Wert für Datensätze, die von SharePoint-freigabeaktivitäten ausgelöst werden) aus. Eine Liste der Office 365 Dienste, die den in der Spalte **RecordType** angezeigten Enumerationswerten entsprechen, finden Sie unter [detaillierte Eigenschaften im Office 365-Überwachungsprotokoll](detailed-properties-in-the-office-365-audit-log.md).

- Filtern Sie die Spalte **Vorgänge** , um die Datensätze für bestimmte Aktivitäten anzuzeigen. Eine Liste der meisten Vorgänge, die einer durchsuchbaren Aktivität im Überwachungsprotokoll-Such Tool im Security #a0 Compliance Center entsprechen, finden Sie im Abschnitt "überwachte Aktivitäten" unter [Durchsuchen des Überwachungsprotokolls im Security #a1 Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).

- Anstatt das Überwachungsprotokoll-Such Tool im Security #a0 Compliance Center zu verwenden, können Sie das Cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) in Exchange Online PowerShell verwenden, um die Ergebnisse einer Office 365 Überwachungsprotokoll Suche in eine CSV-Datei zu exportieren. Anschließend können Sie das gleiche Verfahren wie in Schritt 2 beschrieben ausführen, um das Überwachungsprotokoll mit dem Power Query-Editor zu formatieren. Ein Vorteil der Verwendung des PowerShell-Cmdlets besteht darin, dass Sie mithilfe des *RecordType* -Parameters nach Ereignissen eines bestimmten Office 365 Diensts suchen können. Im folgenden finden Sie einige Beispiele für die Verwendung von PowerShell zum Exportieren von Überwachungsdatensätzen in eine CSV-Datei, damit Sie den Power Query-Editor verwenden können, um das JSON-Objekt in der **Auditdata** -Spalte wie in Schritt 2 beschrieben zu transformieren.

   Führen Sie in diesem Beispiel die folgenden Befehle aus, um alle Datensätze im Zusammenhang mit SharePoint-Freigabe Vorgängen zurückzugeben. 
   
   ```powershell
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```powershell
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - Die Suchergebnisse werden in eine CSV-Datei mit dem Namen *PowerShellAuditlog* exportiert, die vier Spalten enthält: CreationDate, userids, RecordType, Auditdata).

   - Sie können den Namen oder den enum-Wert für den Record-Typ als Wert für den *RecordType* -Parameter verwenden. Eine Liste der Namen von Datensatztypen und der zugehörigen Enumerationswerte finden Sie in der *AuditLogRecordType* -Tabelle in [Office 365 API-Schema der Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).
   
   - Sie können nur einen einzelnen Wert für diesen Parameter einschließen. Um nach Überwachungsdatensätzen für andere Datensatztypen zu suchen, müssen Sie die beiden vorherigen Befehle erneut ausführen, um einen anderen Datensatztyp anzugeben und diese Ergebnisse an die ursprüngliche CSV-Datei anzufügen. Sie führen beispielsweise die folgenden beiden Befehle aus, um SharePoint-Dateiaktivitäten aus dem gleichen Datumsbereich zur PowerShellAuditlog. CSV-Datei hinzuzufügen.

          ```powershell
          $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
          ```

          ```powershell
          $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
          ```
