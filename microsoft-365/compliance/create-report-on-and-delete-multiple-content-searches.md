---
title: Erstellen, Ausführen von Berichten und Löschen mehrerer Inhaltssuchen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Erfahren Sie, wie Sie Aufgaben zur Inhaltssuche automatisieren, beispielsweise das Erstellen von Suchvorgängen und das Ausführen von Berichten über PowerShell-Skripts im Security & Compliance Center in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0412c0d217603acb4e200e3ccd62a7748610297e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357585"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Erstellen, Ausführen von Berichten und Löschen mehrerer Inhaltssuchen

 Das schnelle Erstellen und melden von Ermittlungs suchen ist häufig ein wichtiger Schritt in eDiscovery und Untersuchungen, wenn Sie sich mit den zugrunde liegenden Daten und dem Umfang und der Qualität Ihrer Suche vertraut machen möchten. Dazu bietet die Security & Compliance Center PowerShell eine Reihe von Cmdlets zum Automatisieren zeitaufwändiger Inhalts Suchaufgaben. Diese Skripts bieten eine schnelle und einfache Möglichkeit zum Erstellen einer Reihe von Suchvorgängen und führen dann Berichte der geschätzten Suchergebnisse aus, mit denen Sie die Menge der fraglichen Daten bestimmen können. Sie können die Skripts auch verwenden, um verschiedene Versionen von Suchvorgängen zu erstellen, um die Ergebnisse zu vergleichen, die von jedem erstellt werden. Diese Skripts können Ihnen dabei helfen, Ihre Daten schnell und effizient zu identifizieren und zu pflücken.

## <a name="before-you-create-a-content-search"></a>Vor dem Erstellen einer Inhaltssuche

- Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein, um die in diesem Thema beschriebenen Skripts auszuführen.

- Informationen zum Sammeln einer Liste der URLs für die OneDrive für Unternehmen Websites in Ihrer Organisation, die Sie der CSV-Datei in Schritt 1 hinzufügen können, finden Sie unter [Erstellen einer Liste mit allen OneDrive-Speicherorten in Ihrer Organisation](https://docs.microsoft.com/onedrive/list-onedrive-urls).

- Achten Sie darauf, alle in diesem Thema erstellten Dateien in demselben Ordner zu speichern. Dadurch wird das Ausführen der Skripts vereinfacht.

- Die Skripts enthalten eine minimale Fehlerbehandlung. Ihr Hauptzweck besteht darin, mehrere Inhalts suchen schnell zu erstellen, zu melden und zu löschen.

- Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Schritt 1: Erstellen Sie eine CSV-Datei, die Informationen zu den Suchvorgängen enthält, die Sie ausführen möchten.

Die CSV-Datei (Comma Separated Value), die Sie in diesem Schritt erstellen, enthält eine Zeile für jeden Benutzer, der durchsucht werden soll. Sie können das Exchange Online Postfach des Benutzers durchsuchen (einschließlich des Archivpostfachs, sofern es aktiviert ist) und dessen OneDrive für Unternehmen Website. Sie können auch nur das Postfach oder die OneDrive für Unternehmen Website durchsuchen. Sie können auch jede Website in Ihrer SharePoint Online Organisation durchsuchen. Durch das in Schritt 3 ausgeführte Skript wird eine separate Suche für jede Zeile in der CSV-Datei erstellt.

1. Kopieren Sie den folgenden Text, und fügen Sie ihn mit Notepad in eine txt-Datei ein. Speichern Sie diese Datei in einem Ordner auf Ihrem lokalen Computer. Sie speichern die anderen Skripts ebenfalls in diesem Ordner.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   In der ersten Zeile oder Kopfzeile der Datei werden die Parameter aufgelistet, die von **New-ComplianceSearch** Cmdlet (im Skript in Schritt 3) verwendet werden, um eine neue Inhaltssuche zu erstellen. Die einzelnen Parameternamen werden jeweils durch ein Komma getrennt. Stellen Sie sicher, dass keine Leerzeichen in der Überschriftenzeile vorhanden sind. Jede Zeile unter der Kopfzeile stellt die Parameterwerte für jede Suche dar. Achten Sie darauf, die Platzhalterdaten in der CSV-Datei durch ihre tatsächlichen Daten zu ersetzen.

2. Öffnen Sie die txt-Datei in Excel, und verwenden Sie dann die Informationen in der folgenden Tabelle, um die Datei mit Informationen für jede Suche zu bearbeiten.

   ****

   |Parameter|Beschreibung|
   |---|---|
   |`ExchangeLocation`|Die SMTP-Adresse des Postfachs des Benutzers.|
   |`SharePointLocation`|Die URL für die OneDrive für Unternehmen Website des Benutzers oder die URL für eine beliebige Website in Ihrer Organisation. Verwenden Sie für die URL für OneDrive für Unternehmen Websites folgendes Format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` . Zum Beispiel: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|Die Suchabfrage für die Suche. Weitere Informationen zum Erstellen einer Suchabfrage finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).|
   |`StartDate`|Für e-Mail das Datum, an dem oder nachdem eine Nachricht von einem Empfänger empfangen oder vom Absender gesendet wurde. Für Dokumente auf SharePoint-oder OneDrive für Unternehmen-Websites das Datum, an dem oder nachdem ein Dokument zuletzt geändert wurde.|
   |`EndDate`|Für e-Mail das Datum, an dem oder vor dem eine Nachricht von einem Benutzer gesendet wurde. Für Dokumente auf SharePoint-oder OneDrive für Unternehmen-Websites das Datum an oder vor der letzten Änderung eines Dokuments.|
   |

3. Speichern Sie die Excel-Datei als CSV-Datei in einem Ordner auf Ihrem lokalen Computer. Das in Schritt 3 erstellte Skript verwendet die Informationen in dieser CSV-Datei, um die Suchvorgänge zu erstellen.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Schritt 2: Herstellen einer Verbindung mit Security & Compliance Center-PowerShell

Der nächste Schritt besteht darin, eine Verbindung mit der Security & Compliance Center PowerShell für Ihre Organisation herzustellen. Schrittweise Anleitungen erhalten Sie unter [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Schritt 3: Ausführen des Skripts zum Erstellen und Starten der Suche

Mit dem Skript in diesem Schritt wird eine separate Inhaltssuche für jede Zeile in der CSV-Datei erstellt, die Sie in Schritt 1 erstellt haben. Wenn Sie dieses Skript ausführen, werden Sie aufgefordert, zwei Werte einzugeben:

- **Suchgruppen-ID** – dieser Name bietet eine einfache Möglichkeit zum Organisieren der aus der CSV-Datei erstellten Suchvorgänge. Jede erstellte Suche wird mit der Suchgruppen-ID benannt, und dann wird dem Suchnamen eine Zahl angefügt. Wenn Sie beispielsweise **ContosoCase** für die Suchgruppen-ID eingeben, werden die Suchvorgänge **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**usw. benannt. Beachten Sie, dass bei dem von Ihnen eingegebenen Namen Groß-/Kleinschreibung beachtet wird. Wenn Sie in Schritt 4 und Schritt 5 die Suchgruppen-ID verwenden, müssen Sie den gleichen Fall wie beim Erstellen verwenden.

- **CSV-Datei** : der Name der CSV-Datei, die Sie in Schritt 1 erstellt haben. Achten Sie darauf, dass Sie den vollständigen Dateinamen verwenden, einschließlich der CSV-Dateierweiterung; Beispiel:  `ContosoCase.csv` .

So führen Sie das Skript aus

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `CreateSearches.ps1` . Speichern Sie die Datei im gleichen Ordner, in dem Sie die anderen Dateien gespeichert haben.

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     $searchName = $searchGroup +'_' + $searchCounter
     $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
     if ($search)
     {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
     }
     $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     # Create the query
     $query = $_.ContentMatchQuery
     if(($_.StartDate -or $_.EndDate))
     {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
     }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

     # Create and run the search
     $searchName = $searchGroup +'_' + $searchCounter
     Write-Host "Creating and running search: " $searchName -NoNewline
     $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

     # Start and wait for each search to complete
     Start-ComplianceSearch $search.Name
     while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
     {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
     }
     Write-Host ""

     $searchCounter++
   }
   ```

2. Wechseln Sie in Windows PowerShell zu dem Ordner, in dem Sie das Skript im vorherigen Schritt gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. Geben Sie an der Eingabeaufforderung der **Suchgruppen-ID** einen Suchgruppen Namen ein, und drücken Sie dann die **EINGABETASTE**; Beispiel:  `ContosoCase` . Beachten Sie, dass bei diesem Namen die Groß-/Kleinschreibung beachtet wird, sodass Sie Sie in den nachfolgenden Schritten auf die gleiche Weise eingeben müssen.

4. Geben Sie an der Eingabeaufforderung der **Quell-CSV-Datei** den Namen der CSV-Datei ein, einschließlich der CSV-Dateierweiterung; Beispiel:  `ContosoCase.csv` .

5. Drücken **Sie die EINGABETASTE** , um das Skript weiter auszuführen.

   Das Skript zeigt den Fortschritt beim Erstellen und Ausführen der Suchvorgänge an. Wenn das Skript abgeschlossen ist, wird es an die Eingabeaufforderung zurückgegeben.

   ![Beispielausgabe aus dem Ausführen des Skripts zum Erstellen mehrerer Kompatibilitäts Suchvorgänge](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Schritt 4: Ausführen des Skripts zum Melden der Such Schätzungen

Nachdem Sie die Suchvorgänge erstellt haben, besteht der nächste Schritt darin, ein Skript auszuführen, mit dem ein einfacher Bericht über die Anzahl der Suchtreffer für jede in Schritt 3 erstellte Suche angezeigt wird. Der Bericht enthält auch die Größe der Ergebnisse für jede Suche sowie die Gesamtanzahl der Treffer und die Gesamtgröße aller Suchvorgänge. Wenn Sie das Berichts Skript ausführen, werden Sie zur Eingabe der Suchgruppen-ID und eines CSV-Datei namens aufgefordert, wenn Sie den Bericht in einer CSV-Datei speichern möchten.

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `SearchReport.ps1` . Speichern Sie die Datei im gleichen Ordner, in dem Sie die anderen Dateien gespeichert haben.

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. Wechseln Sie in Windows PowerShell zu dem Ordner, in dem Sie das Skript im vorherigen Schritt gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:

   ```Powershell
   .\SearchReport.ps1
   ```

3. Geben Sie an der Eingabeaufforderung der **Suchgruppen-ID** einen Suchgruppen Namen ein, und drücken Sie dann die **EINGABETASTE**; zum Beispiel  `ContosoCase` . Beachten Sie, dass bei diesem Namen die Groß-/Kleinschreibung beachtet wird, sodass Sie ihn auf die gleiche Weise wie beim Ausführen des Skripts in Schritt 3 eingeben müssen.

4. Geben Sie am **Dateipfad zum Speichern des Berichts in einer CSV-Datei (leer lassen, um die Meldung anzuzeigen)** den Dateinamen des vollständigen Pfadnamens (einschließlich der CSV-Dateierweiterung) ein, wenn Sie den Bericht in einer CSV-Datei speichern möchten. Name der CSV-Datei, einschließlich der CSV-Dateierweiterung. Sie können beispielsweise eingeben, um  `ContosoCaseReport.csv` es im aktuellen Verzeichnis zu speichern, oder Sie können eingeben  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` , um es in einem anderen Ordner zu speichern. Sie können die Eingabeaufforderung auch leer lassen, um den Bericht anzuzeigen, jedoch nicht in einer Datei zu speichern.

5. Drücken Sie **EINGABE**.

   Das Skript zeigt den Fortschritt beim Erstellen und Ausführen der Suchvorgänge an. Wenn das Skript abgeschlossen ist, wird der Bericht angezeigt.

   ![Ausführen des Suchberichts zum Anzeigen der Schätzungen für die suchgruppe](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> Wenn das gleiche Postfach oder die gleiche Website als Inhaltsspeicherort in mehreren Suchergebnissen in einer suchgruppe angegeben ist, kann die Gesamtergebnis Schätzung im Bericht (sowohl für die Anzahl der Elemente als auch für die Gesamtgröße) Ergebnisse für dieselben Elemente enthalten. Das liegt daran, dass die gleiche e-Mail-Nachricht oder das gleiche Dokument mehr als einmal gezählt wird, wenn Sie mit der Abfrage für unterschiedliche Suchvorgänge in der suchgruppe übereinstimmt.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>Schritt 5: Ausführen des Skripts zum Löschen der Suchvorgänge

Da Sie vielleicht viele Suchvorgänge erstellen, vereinfacht dieses letzte Skript einfach das schnelle Löschen der in Schritt 3 erstellten Suchvorgänge. Wie bei den anderen Skripts werden Sie auch von diesem aufgefordert, die Suchgruppen-ID einzugeben. Wenn Sie dieses Skript ausführen, werden alle Suchvorgänge mit der Suchgruppen-ID im Suchnamen gelöscht.

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `DeleteSearches.ps1` . Speichern Sie die Datei im gleichen Ordner, in dem Sie die anderen Dateien gespeichert haben.

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. Wechseln Sie in Windows PowerShell zu dem Ordner, in dem Sie das Skript im vorherigen Schritt gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. Geben Sie an der Eingabeaufforderung der **Suchgruppen-ID** einen Suchgruppen Namen für die Suchvorgänge ein, die Sie löschen möchten, und drücken Sie dann die **EINGABETASTE**; Beispiel:  `ContosoCase` . Beachten Sie, dass bei diesem Namen die Groß-/Kleinschreibung beachtet wird, sodass Sie ihn auf die gleiche Weise wie beim Ausführen des Skripts in Schritt 3 eingeben müssen.

   Das Skript zeigt den Namen jeder gelöschten Suche an.

   ![Ausführen des Skripts zum Löschen der Suchvorgänge in der Gruppe "Suche"](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
