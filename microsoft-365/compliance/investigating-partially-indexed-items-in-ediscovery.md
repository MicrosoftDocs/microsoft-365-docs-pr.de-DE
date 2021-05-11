---
title: Untersuchen teilweise indizierter Elemente in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie teilweise indizierte Elemente (auch als nicht indizierte Elemente bezeichnet) aus Exchange, SharePoint und OneDrive for Business in Ihrer Organisation verwalten.
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311454"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>Untersuchen teilweise indizierter Elemente in eDiscovery

Eine eDiscovery-Suche, die Sie über das Microsoft 365 Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen. Teilweise indizierte Elemente Exchange Postfachelemente und Dokumente auf SharePoint- und OneDrive for Business-Websites, die aus einem bestimmten Grund nicht vollständig für die Suche indiziert wurden. Die meisten E-Mail-Nachrichten und Websitedokumente werden erfolgreich indiziert, da sie innerhalb der Indizierungsgrenzwerte für [E-Mail-Nachrichten liegen.](limits-for-content-search.md#indexing-limits-for-email-messages) Einige Elemente überschreiten jedoch möglicherweise diese Indizierungsgrenzwerte und werden teilweise indiziert. Es gibt weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine eDiscovery-Suche ausführen:
  
- E-Mail-Nachrichten verfügen über eine angefügte Datei ohne gültigen Handler, z. B. Bilddateien. Dies ist die häufigste Ursache für teilweise indizierte E-Mail-Elemente.

- Die E-Mail enthält zu viele Dateien im Anhang.

- Die an die E-Mail angehängte Datei ist zu groß.

- Der Dateityp wird für die Indizierung unterstützt, aber es ist ein Indizierungsfehler für eine bestimmte Datei aufgetreten.

Obwohl dies unterschiedlich ist, verfügen die meisten Organisationen über weniger als 1 % des Inhalts nach Volumen und weniger als 12 % des Teils indizierten Inhalts. Der Grund für den Unterschied zwischen dem Volume und der Größe ist, dass größere Dateien eine höhere Wahrscheinlichkeit haben, Inhalte zu enthalten, die nicht vollständig indiziert werden können.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Warum ändert sich die teilweise indizierte Elementanzahl für eine Suche?

Nachdem Sie eine eDiscovery-Suche ausgeführt haben, werden die Gesamtanzahl und Größe teilweise indizierter Elemente an den durchsuchten Speicherorten in den Suchergebnisstatistiken aufgeführt, die in den detaillierten Statistiken für die Suche angezeigt werden. Beachten Sie, dass diese  *elemente in der Suchstatistik*  als nicht indizierte Elemente bezeichnet werden. Hier sind einige Dinge, die sich auf die Anzahl der teilweise indizierten Elemente auswirken, die in den Suchergebnissen zurückgegeben werden:
  
- Wenn ein Element teilweise indiziert ist und der Suchabfrage entspricht, ist es sowohl in der Anzahl (und Größe) von Suchergebnissen als auch in teilweise indizierten Elementen enthalten. Wenn jedoch die Ergebnisse derselben Suche exportiert werden, wird das Element nur in einer Reihe von Suchergebnissen enthalten. es ist nicht als teilweise indiziertes Element enthalten.

- Teilweise indizierte Elemente, die sich in SharePoint-  und OneDrive-Websites befinden, sind nicht in der Schätzung teilweise indizierter Elemente enthalten, die in den detaillierten Statistiken für die Suche angezeigt werden. Teilweise indizierte Elemente können jedoch exportiert werden, wenn Sie die Ergebnisse einer eDiscovery-Suche exportieren. Wenn Sie beispielsweise nur Websites durchsuchen, ist die geschätzte Anzahl teilweise indizierter Elemente null.
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Berechnen des Verhältnisses teilweise indizierter Elemente in Ihrer Organisation

Um die Belastung Ihrer Organisation gegenüber teilweise indizierten Elementen zu verstehen, können Sie eine Suche nach allen Inhalten in allen Postfächern (mithilfe einer leeren Schlüsselwortabfrage) ausführen. Im folgenden Beispiel sind 1.629.904 (146,46 GB) vollständig indizierte Elemente und 10.025 (10,27 GB) teilweise indizierte Elemente.
  
![Beispiel für Suchstatistiken mit teilweise indizierten Elementen](../media/PartiallyIndexedItemsTest.png)
  
Sie können den Prozentsatz teilweise indizierter Elemente mithilfe der folgenden Berechnungen bestimmen.
  
 **So berechnen Sie das Verhältnis von teilweise indizierten Elementen in Ihrer Organisation:**

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

Mithilfe der Suchergebnisse aus dem vorherigen Beispiel werden 0,62 % aller Postfachelemente teilweise indiziert.
  
 **So berechnen Sie den Prozentsatz der Größe teilweise indizierter Elemente in Ihrer Organisation:**

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

Im vorherigen Beispiel sind also 7 % der Gesamtgröße von Postfachelementen aus teilweise indizierten Elementen. Wie bereits erwähnt, verfügen die meisten Organisationen über weniger als 1 % des Inhalts nach Volumen und weniger als 12 % des Teils indizierten Inhalts.

## <a name="working-with-partially-indexed-items"></a>Arbeiten mit teilweise indizierten Elementen

In Fällen, in denen Sie teilweise Elemente untersuchen müssen, um zu [](export-a-content-search-report.md) überprüfen, ob sie keine relevanten Informationen enthalten, können Sie einen Inhaltssuchbericht exportieren, der Informationen zu teilweise indizierten Elementen enthält. Wenn Sie einen Inhaltssuchbericht exportieren, müssen Sie eine der Exportoptionen auswählen, die teilweise indizierte Elemente enthalten.
  
![Auswählen der zweiten oder dritten Option zum Exportieren teilweise indizierter Elemente](../media/PartiallyIndexedItemsExportOptions.png)
  
Wenn Sie eDiscovery-Suchergebnisse oder einen Suchbericht mit einer dieser Optionen exportieren, enthält der Export einen Bericht namens Unindexed Items.csv. Dieser Bericht enthält die meisten der gleichen Informationen wie die ResultsLog.csv Datei. Die Datei Nicht indizierte Items.csv enthält jedoch auch zwei Felder im Zusammenhang mit teilweise indizierten Elementen: **Fehlertags** und **Fehlereigenschaften**. Diese Felder enthalten Informationen zum Indizierungsfehler für jedes teilweise indizierte Element. Mithilfe der Informationen in diesen beiden Feldern können Sie ermitteln, ob sich der Indizierungsfehler für eine bestimmte Untersuchung auf Ihre Untersuchung aus wirkt. In diesem Fall können Sie eine gezielte Suche durchführen und bestimmte E-Mail-Nachrichten und SharePoint- oder OneDrive-Dokumente abrufen und exportieren, damit Sie diese untersuchen können, um festzustellen, ob sie für Ihre Untersuchung relevant sind. Schrittweise Anweisungen finden Sie unter [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).

> [!NOTE]
> Die Nicht indizierte Items.csv enthält auch felder mit dem Namen **Fehlertyp** und **Fehlermeldung**. Dies sind Legacyfelder, die Informationen enthalten, die  den Informationen in den Feldern **Fehlertags** und Fehlereigenschaften ähneln, jedoch mit weniger detaillierten Informationen. Sie können diese Legacyfelder sicher ignorieren.
  
## <a name="errors-related-to-partially-indexed-items"></a>Fehler im Zusammenhang mit teilweise indizierten Elementen

Fehlertags besteht aus zwei Informationsteilen, dem Fehler und dem Dateityp. Beispiel: In diesem Fehler-Datei-Typ-Paar:

```text
 parseroutputsize_xls
```

 `parseroutputsize` ist der Fehler und `xls` der Dateityp der Datei, in der der Fehler aufgetreten ist. In Fällen, in denen der Dateityp nicht erkannt wurde oder der Dateityp nicht auf den Fehler angewendet wurde, wird der Wert statt des `noformat` Dateityps angezeigt.
  
Im Folgenden finden Sie eine Liste der Indizierungsfehler und eine Beschreibung der möglichen Ursache des Fehlers.
  
| Fehlertag | Beschreibung |
|:-----|:-----|
| `attachmentcount` <br/> |Eine E-Mail-Nachricht hatte zu viele Anlagen, und einige dieser Anlagen wurden nicht verarbeitet.  <br/> |
| `attachmentdepth` <br/> |Der Inhalts-Retriever und der Dokumentparser haben zu viele Ebenen von Anlagen gefunden, die in anderen Anlagen geschachtelt sind. Einige dieser Anlagen wurden nicht verarbeitet.  <br/> |
| `attachmentrms` <br/> |Fehler beim Decodieren einer Anlage, da sie RMS-geschützt war.  <br/> |
| `attachmentsize` <br/> |Eine an eine E-Mail-Nachricht angefügte Datei war zu groß und konnte nicht verarbeitet werden.  <br/> |
| `indexingtruncated` <br/> |Beim Schreiben der verarbeiteten E-Mail-Nachricht in den Index war eine der indexierbaren Eigenschaften zu groß und wurde abgeschnitten. Die abgeschnittenen Eigenschaften werden im Feld Fehlereigenschaften aufgeführt.  <br/> |
| `invalidunicode` <br/> |Eine E-Mail-Nachricht enthielt Text, der nicht als gültiger Unicode-Code verarbeitet werden konnte. Die Indizierung für dieses Element kann unvollständig sein.  <br/> |
| `parserencrypted` <br/> |Der Inhalt der Anlage oder E-Mail-Nachricht ist verschlüsselt, und Microsoft 365 inhalte konnten nicht decodiert werden.  <br/> |
| `parsererror` <br/> |Bei der Analyse ist ein unbekannter Fehler aufgetreten. Dies resultiert in der Regel aus einem Softwarefehler oder einem Dienstabsturz.  <br/> |
| `parserinputsize` <br/> |Eine Anlage war für den Parser zu groß, und die Analyse dieser Anlage wurde nicht durchgeführt oder nicht abgeschlossen.  <br/> |
| `parsermalformed` <br/> |Eine Anlage wurde falsch formatiert und konnte vom Parser nicht verarbeitet werden. Dieses Ergebnis kann auf alte Dateiformate, dateien, die von inkompatibler Software erstellt wurden, oder Viren, die vorgeben, etwas anderes als beansprucht zu sein, verursacht werden.  <br/> |
| `parseroutputsize` <br/> |Die Ausgabe aus der Analyse einer Anlage war zu groß und musste abgeschnitten werden.  <br/> |
| `parserunknowntype` <br/> |Eine Anlage hatte einen Dateityp, Microsoft 365 nicht erkannt werden konnte.  <br/> |
| `parserunsupportedtype` <br/> |Eine Anlage hatte einen Dateityp, den Office 365 erkennen konnte, aber die Analyse dieses Dateityps wird nicht unterstützt.  <br/> |
| `propertytoobig` <br/> |Der Wert einer E-Mail-Eigenschaft in Exchange Store war zu groß, um abgerufen zu werden, und die Nachricht konnte nicht verarbeitet werden. Dies geschieht in der Regel nur für die body-Eigenschaft einer E-Mail-Nachricht.  <br/> |
| `retrieverrms` <br/> |Der Inhalts-Retriever konnte eine RMS-geschützte Nachricht nicht decodieren.  <br/> |
| `wordbreakertruncated` <br/> |Zu viele Wörter wurden während der Indizierung im Dokument identifiziert. Die Verarbeitung der Eigenschaft wurde beendet, wenn der Grenzwert erreicht wurde, und die Eigenschaft wird abgeschnitten.  <br/> |

Fehlerfelder beschreiben, welche Felder vom Verarbeitungsfehler betroffen sind, der im Feld Fehlertags aufgeführt ist. Wenn Sie eine Eigenschaft wie or durchsuchen, haben Fehler im Nachrichtentext keine Auswirkungen auf die Ergebnisse  `subject`  `participants` Ihrer Suche. Dies kann hilfreich sein, wenn Sie genau bestimmen, welche teilweise indizierten Elemente Sie möglicherweise weiter untersuchen müssen.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Verwenden eines PowerShell-Skripts zum Bestimmen der Belastung Ihrer Organisation gegenüber teilweise indizierten E-Mail-Elementen

In den folgenden Schritten wird gezeigt, wie Sie ein PowerShell-Skript ausführen, das nach allen Elementen in allen Exchange-Postfächern sucht und anschließend einen Bericht über das Verhältnis ihrer Organisation aus teilweise indizierten E-Mail-Elementen (nach Anzahl und Größe) generiert und die Anzahl der Elemente (und deren Dateityp) für jeden aufgetretenen Indizierungsfehler anzeigt. Verwenden Sie die Beschreibungen des Fehlertags im vorherigen Abschnitt, um den Indizierungsfehler zu identifizieren.
  
1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie ein Dateinamensuffix von .ps1; Beispiel: `PartiallyIndexedItems.ps1` .

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

2. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](/powershell/exchange/exchange-online-powershell).

3. Wechseln Sie & Compliance Center PowerShell zu dem Ordner, in dem Sie das Skript in Schritt 1 gespeichert haben, und führen Sie das Skript aus. Zum Beispiel:

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

Hier sehen Sie ein Beispiel für die vom Skript zurückgegebene Ausgabe.
  
![Beispiel für die Ausgabe aus einem Skript, das einen Bericht über die Belastung Ihrer Organisation gegenüber teilweise indizierten E-Mail-Elementen generiert](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> Beachten Sie Folgendes:
>  
> - Die Gesamtanzahl und Größe der E-Mail-Elemente und das Verhältnis Ihrer Organisation zu teilweise indizierten E-Mail-Elementen (nach Anzahl und Größe).
> 
> - Ein Listenfehlertags und die entsprechenden Dateitypen, für die der Fehler aufgetreten ist.
  
## <a name="see-also"></a>Siehe auch

[Teilweise indizierte Elemente in eDiscovery](partially-indexed-items-in-content-search.md)