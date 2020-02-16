---
title: Untersuchen von teilweise indizierten Elementen in Office 365 eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Teilweise indizierte Elemente (auch nicht indexierte Elemente aufrufen) sind Exchange-Postfachelemente und Dokumente auf SharePoint-und OneDrive-Websites, die aus irgendeinem Grund nicht vollständig für die Inhaltssuche indiziert wurden. In diesem Artikel erfahren Sie, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, Suchfehler für teilweise indizierte Elemente identifizieren und ein PowerShell-Skript verwenden, um die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Nachrichten zu ermitteln. Elemente.
ms.openlocfilehash: b67b7d5cfedd37315a9f8bc9027e03b820598846
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072347"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>Untersuchen von teilweise indizierten Elementen in Office 365 eDiscovery

Eine Inhaltssuche, die Sie im Security & Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen. Teilweise indizierte Elemente sind Exchange-Postfachelemente und Dokumente in SharePoint und OneDrive für Unternehmen Websites, die aus irgendeinem Grund nicht vollständig für die Suche indiziert wurden. Die meisten e-Mail-Nachrichten und Website Dokumente werden erfolgreich indiziert, da Sie innerhalb der [Grenzwerte für e-Mail-Nachrichten](limits-for-content-search.md#indexing-limits-for-email-messages)liegen. Einige Elemente können diese Grenzwerte für die Indizierung jedoch überschreiten und teilweise indiziert werden. Im folgenden finden Sie weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine Inhaltssuche ausführen:
  
- E-Mail-Nachrichten weisen eine angefügte Datei eines Dateityps auf, der nicht indiziert werden kann. in den meisten Fällen wird der Dateityp [für die Indizierung nicht erkannt oder nicht unterstützt](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search) .
    
- E-Mail-Nachrichten weisen eine angefügte Datei ohne gültigen Handler auf, beispielsweise Bilddateien; Dies ist die häufigste Ursache für teilweise indizierte e-Mail-Elemente
    
- Zu viele an eine e-Mail-Nachricht angefügte Dateien
    
- Eine an eine e-Mail-Nachricht angefügte Datei ist zu groß
    
- Der Dateityp wird für die Indizierung unterstützt, es ist jedoch ein Indizierungsfehler für eine bestimmte Datei aufgetreten.
    
Obwohl die meisten Office 365 Organisationen unterschiedlich sind, haben Kunden weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert ist. Der Grund für den Unterschied zwischen dem Volume und der Größe besteht darin, dass größere Dateien eine höhere Wahrscheinlichkeit enthalten, Inhalte zu enthalten, die nicht vollständig indiziert werden können.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Warum ändert sich die teilweise indizierte Elementanzahl für eine Suche?

Nachdem Sie eine Inhaltssuche im Security & Compliance Center ausgeführt haben, werden die Gesamtzahl und die Größe der teilweise indizierten Elemente an den durchsuchten Speicherorten in den Suchergebnis Statistiken aufgeführt, die in den detaillierten Statistiken für die Suche angezeigt werden. Hinweis Diese werden als nicht *indizierte Elemente* in den Suchstatistiken bezeichnet. Hier sind einige Dinge, die sich auf die Anzahl der teilweise indizierten Elemente auswirken, die in den Suchergebnissen zurückgegeben werden: 
  
- Wenn ein Element teilweise indiziert wird und mit der Suchabfrage übereinstimmt, ist es sowohl in der Anzahl (und der Größe) von Suchergebnis Elementen als auch in teilweise indizierten Elementen enthalten. Wenn die Ergebnisse der gleichen Suche jedoch exportiert werden, ist das Element nur mit einer Reihe von Suchergebnissen enthalten; Es ist nicht als teilweise indiziertes Element enthalten.
    
- Wenn Sie einen Datumsbereich für eine Suchabfrage angeben (indem Sie ihn in die Stichwortabfrage oder mithilfe einer Bedingung einbeziehen), ist ein teilweise indiziertes Element, das nicht mit dem Datumsbereich übereinstimmt, nicht Bestandteil der Anzahl der teilweise indizierten Elemente. Nur die teilweise indizierten Elemente, die innerhalb des Datumsbereichs liegen, sind in der Anzahl der teilweise indizierten Elemente enthalten.
    
 **Hinweis:** Teilweise indizierte Elemente, die sich in SharePoint-und OneDrive-Websites befinden, *sind nicht* in der Schätzung der teilweise indizierten Elemente enthalten, die in den detaillierten Statistiken für die Suche angezeigt werden. Teilweise indizierte Elemente können jedoch exportiert werden, wenn Sie die Ergebnisse einer Inhaltssuche exportieren. Wenn Sie beispielsweise nur Websites in einer Inhaltssuche durchsuchen, wird die geschätzte Anzahl der teilweise indizierten Elemente 0 (null) sein. 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Berechnen des Verhältnisses von teilweise indizierten Elementen in Ihrer Organisation

Um die Exposition ihrer Organisation gegenüber teilweise indizierten Elementen zu verstehen, können Sie eine Suche nach allen Inhalten in allen Postfächern ausführen (mithilfe einer leeren Stichwortabfrage). Im folgenden Beispiel sind 56.208 (4.830 MB) vollständig indizierte Elemente und teilweise indizierte Elemente mit 470 (316 MB) vorhanden.
  
![Beispiel für Suchstatistiken mit teilweise indizierten Elementen](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
Sie können den Prozentsatz der teilweise indizierten Elemente mit den folgenden Berechnungen ermitteln.
  
 **So berechnen Sie das Verhältnis von teilweise indizierten Elementen in Ihrer Organisation:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
Bei Verwendung der Suchergebnisse aus dem vorherigen Beispiel sind. 84% aller Postfachelemente teilweise indiziert.
  
 **So berechnen Sie den Prozentsatz der Größe von teilweise indizierten Elementen in Ihrer Organisation:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Im vorherigen Beispiel stammt 6,54% der Gesamtgröße der Postfachelemente aus teilweise indizierten Elementen. Wie bereits erwähnt, haben die meisten Kunden in Office 365 Organisationen weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert sind.

## <a name="working-with-partially-indexed-items"></a>Arbeiten mit teilweise indizierten Elementen

In Fällen, in denen Sie teilweise Elemente überprüfen müssen, um zu überprüfen, dass Sie keine relevanten Informationen enthalten, können Sie [einen Inhalts Suchbericht exportieren](export-a-content-search-report.md) , der Informationen zu teilweise indizierten Elementen enthält. Achten Sie beim Exportieren eines Inhalts Suchberichts darauf, eine der Exportoptionen zu wählen, die teilweise indizierte Elemente enthalten. 
  
![Auswählen der zweiten oder dritten Option zum Exportieren von teilweise indizierten Elementen](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Wenn Sie Inhalts Suchergebnisse oder einen Inhalts Suchbericht mit einer dieser Optionen exportieren, enthält der Export einen Bericht mit dem Namen nicht indizierte Elemente. CSV. Dieser Bericht enthält die meisten der gleichen Informationen wie die ResultsLog. CSV-Datei; die Datei unindexierte Elemente. csv enthält jedoch auch zwei Felder im Zusammenhang mit teilweise indizierten Elementen: **Error-Tags** und **Error-Eigenschaften**. Diese Felder enthalten Informationen zum Indizierungsfehler für jedes teilweise indizierte Element. Mithilfe der Informationen in diesen beiden Feldern können Sie bestimmen, ob der Indizierungsfehler für einen bestimmten Einfluss auf ihre Untersuchung hat. Wenn dies der Fall ist, können Sie eine gezielte Inhaltssuche durchführen und bestimmte e-Mail-Nachrichten und SharePoint-oder OneDrive-Dokumente abrufen und exportieren, sodass Sie Sie überprüfen können, um festzustellen, ob Sie für Ihre Untersuchung relevant sind. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Vorbereiten einer CSV-Datei für eine gezielte Inhaltssuche in Office 365](csv-file-for-an-id-list-content-search.md).
  
 **Hinweis:** Die Datei "unindizierte Elemente. csv" enthält auch die Felder " **Error Type** " und " **Error Message**". Hierbei handelt es sich um Legacy Felder, die Informationen enthalten, die den Informationen in den Feldern **Error-Tags** und **Error-Eigenschaften** ähneln, jedoch mit kleineren detaillierten Informationen. Sie können diese Legacy Felder problemlos ignorieren. 
  
## <a name="errors-related-to-partially-indexed-items"></a>Fehler im Zusammenhang mit teilweise indizierten Elementen

Fehler Tags bestehen aus zwei Informationselementen, dem Fehler und dem Dateityp. Beispielsweise in diesem Fehler/filetype-paar:

```text
 parseroutputsize_xls
```

   
 `parseroutputsize`ist der Fehler und `xls` ist der Dateityp der Datei, in der der Fehler aufgetreten ist. In Fällen, in denen der Dateityp nicht erkannt wurde oder der Dateityp nicht auf den Fehler angewendet wurde, wird der Wert `noformat` anstelle des Dateityps angezeigt. 
  
Im folgenden finden Sie eine Liste der Indizierungsfehler und eine Beschreibung der möglichen Fehlerursache.
  
|**Error-Tag**|**Beschreibung**|
|:-----|:-----|
| `attachmentcount` <br/> |Eine e-Mail-Nachricht weist zu viele Anlagen auf, und einige dieser Anlagen wurden nicht verarbeitet.  <br/> |
| `attachmentdepth` <br/> |Der Inhalts Such-und Dokumentparser hat zu viele Ebenen von Anlagen gefunden, die in anderen Anlagen geschachtelt sind. Einige dieser Anlagen wurden nicht verarbeitet.  <br/> |
| `attachmentrms` <br/> |Eine Anlage konnte nicht decodiert werden, da Sie RMS-geschützt war.  <br/> |
| `attachmentsize` <br/> |Eine an eine e-Mail-Nachricht angefügte Datei war zu groß und konnte nicht verarbeitet werden.  <br/> |
| `indexingtruncated` <br/> |Beim Schreiben der verarbeiteten e-Mail-Nachricht in den Index war eine der Indexeigenschaften zu groß und wurde abgeschnitten. Die abgeschnittenen Eigenschaften werden im Feld Fehlereigenschaften aufgelistet.  <br/> |
| `invalidunicode` <br/> |Eine e-Mail-Nachricht enthielt Text, der nicht als gültiger Unicode verarbeitet werden konnte. Die Indizierung für dieses Element ist möglicherweise unvollständig.  <br/> |
| `parserencrypted` <br/> |Der Inhalt der Anlage oder der e-Mail-Nachricht ist verschlüsselt, und der Inhalt konnte von Office 365 nicht decodiert werden.  <br/> |
| `parsererror` <br/> |Während der Analyse ist ein unbekannter Fehler aufgetreten. Dies resultiert in der Regel aus einem Softwarefehler oder einem Dienst Absturz.  <br/> |
| `parserinputsize` <br/> |Eine Anlage war zu groß, um vom Parser verarbeitet zu werden, und die Analyse dieser Anlage geschah nicht oder wurde nicht abgeschlossen.  <br/> |
| `parsermalformed` <br/> |Eine Anlage war fehlerhaft und konnte vom Parser nicht verarbeitet werden. Das Ergebnis können alte Dateiformate, Dateien, die von inkompatibler Software erstellt wurden, oder Viren, die als etwas anderes als beansprucht gelten.  <br/> |
| `parseroutputsize` <br/> |Die Ausgabe aus der Analyse einer Anlage war zu groß und musste abgeschnitten werden.  <br/> |
| `parserunknowntype` <br/> |Eine Anlage hatte einen Dateityp, den Office 365 nicht erkennen konnte.  <br/> |
| `parserunsupportedtype` <br/> |Eine Anlage hat einen Dateityp, den Office 365could erkennt, aber das Analysieren dieses Dateityps wird nicht unterstützt.  <br/> |
| `propertytoobig` <br/> |Der Wert einer e-Mail-Eigenschaft im Exchange-Informationsspeicher war zu groß, um abgerufen werden zu können, und die Nachricht konnte nicht verarbeitet werden. Dies geschieht normalerweise nur mit der Body-Eigenschaft einer e-Mail-Nachricht.  <br/> |
| `retrieverrms` <br/> |Fehler beim Decodieren einer RMS-geschützten Nachricht durch den Inhaltsabruf.  <br/> |
| `wordbreakertruncated` <br/> |Während der Indizierung wurden im Dokument zu viele Wörter identifiziert. Verarbeitung der Eigenschaft beim Erreichen des Grenzwerts angehalten, und die Eigenschaft wird abgeschnitten.  <br/> |
   
In den Fehler Feldern wird beschrieben, welche Felder vom Verarbeitungsfehler betroffen sind, der im Feld Fehler Tags aufgeführt ist. Wenn Sie eine Eigenschaft wie `subject` or `participants`durchsuchen, wirken sich Fehler im Textkörper der Nachricht nicht auf die Ergebnisse Ihrer Suche aus. Dies kann hilfreich sein, wenn Sie genau ermitteln, welche teilweise indizierten Elemente Sie möglicherweise noch genauer untersuchen müssen.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Verwenden eines PowerShell-Skripts, um die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen zu ermitteln

In den folgenden Schritten wird gezeigt, wie Sie ein PowerShell-Skript ausführen, das nach allen Elementen in allen Exchange-Postfächern sucht und dann einen Bericht über das Verhältnis ihrer Organisation mit teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe) generiert und die Anzahl der Elemente anzeigt (und deren Dateityp) für jeden auftretenden Indizierungsfehler. Verwenden Sie die Fehler-Tag-Beschreibungen im vorherigen Abschnitt, um den Indizierungsfehler zu identifizieren.
  
1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `PartiallyIndexedItems.ps1`.

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. [Stellen Sie eine Verbindung mit Security & Compliance Center PowerShell her](https://go.microsoft.com/fwlink/p/?linkid=627084).
    
3. Wechseln Sie in Security & Compliance Center PowerShell zu dem Ordner, in dem Sie das Skript in Schritt 1 gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

Im folgenden finden Sie ein Beispiel für die vom Skript zurückgegebene Ausgabe.
  
![Beispiel für die Ausgabe von einem Skript, das einen Bericht über die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen generiert](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
Beachten Sie Folgendes:
  
1. Die Gesamtanzahl und Größe von e-Mail-Elementen und das Verhältnis ihrer Organisation zu teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe)
    
2. A List Error Tags und die entsprechenden Dateitypen, für die der Fehler aufgetreten ist.
  
## <a name="see-also"></a>Siehe auch

[Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)
