---
title: Erstellen eines Schlüsselwörterbuchs
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Grundlagen zum Erstellen eines Schlüsselwörterbuchs im Office 365 Security & Compliance Center.
ms.openlocfilehash: 94bacc2a2fe91fdc35aad753cc2e7db80a374e29
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876076"
---
# <a name="create-a-keyword-dictionary"></a>Schlüsselwörterbuch erstellen

Die Verhinderung von Datenverlust (DLP) kann Ihre vertraulichen Objekte identifizieren, überwachen und schützen. Das Identifizieren vertraulicher Objekte erfordert manchmal die Suche nach Schlüsselwörtern, insbesondere beim Erkennen von allgemeinen Inhalten (etwa bei Kommunikation im Gesundheitswesen) oder unangemessener oder unflätiger Sprache. Obwohl Sie Schlüsselwortlisten in vertraulichen Informationstypen erstellen können, sind Schlüsselwortlisten in ihrer Größe begrenzt und erfordern eine Änderung von XML, um sie zu erstellen oder zu bearbeiten. Schlüsselwörterbücher bieten eine einfachere Verwaltung von Stichwörtern und in einem viel größeren Umfang. Sie unterstützen bis zu 1 MB an Begriffen (Post-Kompression) im Wörterbuch und unterstützen alle Sprachen. Das Mandantenlimit liegt nach der Komprimierung ebenfalls bei 1 MB. Der 1 MB-Limit der Post-Kompression bedeutet, dass alle Wörterbücher zusammen über den gesamten Mandanten hinweg bis zu 1 Million Zeichen haben können.

## <a name="keyword-dictionary-limits"></a>Schlüsselwörterbücherlimits

Es gibt ein Limit von 50 Schlüsselwortwörterbuch-basierten vertraulichen Informationstypen, die pro Mandant erstellt werden können. Um herauszufinden, wie viele Schlüsselwörterbücher Ihr Mandant enthält, stellen Sie mithilfe des in [Herstellen einer Verbindung zu Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) beschriebenen Verfahrens eine Verbindung zu Ihrem Mandanten her, und führen Sie dieses PowerShell-Skript aus.

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Grundlegende Schritte zum Erstellen eines Schlüsselwörterbuchs

Die Schlüsselwörter für Ihr Wörterbuch können aus verschiedenen Quellen stammen, meistens aber aus einer in den Dienst importierten Datei (etwa einer CSV- oder TXT-Liste), oder durch ein einem PowerShell-Cmdlet, aus einer Liste, die Sie direkt in das PowerShell-Cmdlet eingeben, oder aus einem vorhandenen Wörterbuch.Beim Erstellen eines Schlüsselwörterbuchs befolgen Sie die gleichen einfachen Schritte:
  
1. Verwenden Sie das **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) oder stellen Sie eine Verbindung zum **Security &amp; Compliance Center PowerShell** her.
    
2. **Definieren oder laden Sie Ihre Schlüsselwörter aus der vorgesehenen Quelle**. Sowohl der Assistent als auch das Cmdlet akzeptieren eine durch Komma getrennte Liste von Schlüsselwörtern, um ein benutzerdefiniertes Schlüsselwörterbuch zu erstellen. Dieser Schritt variiert daher leicht, je nachdem, woher Ihre Schlüsselwörter stammen. Sobald sie geladen sind, werden sie kodiert und in ein Byte-Array konvertiert, bevor sie importiert werden.
    
3. **Erstellen Sie Ihr Wörterbuch**. Wählen Sie einen Namen und eine Beschreibung und erstellen Sie Ihr Wörterbuch.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Schlüsselwörterbuch mit dem Security & Compliance Center erstellen

Verwenden Sie die folgenden Schritte zum Erstellen und Importieren von Schlüsselwörtern für ein Benutzerwörterbuch:

1. Stellen Sie die Verbindung zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) her.

2. Navigieren Sie zu **Klassifizierungen > Typen vertraulicher Informationen**.

3. Wählen Sie **Erstellen** aus, geben Sie einen **Namen** und eine **Beschreibung** für Ihren vertraulichen Infotyp ein, und wählen Sie dann **Weiter** aus.

4. Wählen Sie **Element hinzufügen** und dann **Wörterbuch (große Schlüsselwörter)** in der Dropdownliste **Inhalt erkennen, der Folgendes enthält** aus.

5. Wählen Sie **Wörterbuch hinzufügen** aus.

6. Wählen Sie unter dem Steuerelement "Suche" die Option **Hier können Sie neue Schlüsselwörterbücher erstellen** aus.

7. Geben Sie einen **Namen** für Ihr Benutzerwörterbuch ein.

8. Klicken Sie auf **Importieren**, und wählen Sie dann entweder **Aus Text** oder **Aus CSV** aus, je nach Typ der Schlüsselwortdatei.

9. Wählen Sie im Dialogfeld "Datei" die Schlüsselwortdatei auf Ihrem lokalen PC oder aus der Netzwerkfreigabe aus, und klicken Sie dann auf **Öffnen**.

10. Klicken Sie auf **Speichern**, und wählen Sie dann Ihr Benutzerwörterbuch aus der Liste **Schlüsselwörterbücher** aus.

11. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Weiter**.

12. Überprüfen und vervollständigen Sie den ausgewählten Typ vertraulicher Informationen, und wählen Sie dann **Fertig stellen** aus.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Erstellen eines Schlüsselwörterbuchs aus einer Datei mit PowerShell

Wenn Sie ein großes Wörterbuch erstellen, müssen Sie möglicherweise Schlüsselwörter verwenden, die aus einer Datei oder einer exportierten Liste aus einer anderen Quelle stammen. In diesem Fall erstellen Sie ein Schlüsselwörterbuch, das eine Liste unangemessener Ausdrücke enthält, um von außen eingehende E-Mail-Nachrichten zu durchsuchen. Zunächst müssen Sie [eine Verbindung zu Security &amp; Compliance Center PowerShell herstellen](/powershell/exchange/connect-to-scc-powershell).
  
1. Kopieren Sie die Schlüsselwörter in eine Textdatei, und stellen Sie sicher, dass sich jedes Schlüsselwort in einer separaten Zeile befindet.
    
2. Speichern Sie die Textdatei in Unicode-Codierung: Im Editor \> **Speichern als** \> **Codierung** \> **Unicode**.
    
3. Lesen Sie die Datei in eine Variable, indem Sie das folgende Cmdlet ausführen:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Erstellen Sie das Wörterbuch, indem Sie das folgende Cmdlet ausführen:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Ändern eines vorhandenen Schlüsselwörterbuchs

Möglicherweise müssen Sie einmal Schlüsselwörter in einem Ihrer Schlüsselwörterbücher oder in einem der integrierten Wörterbücher ändern. Derzeit können Sie mit PowerShell nur ein benutzerdefiniertes Schlüsselwörterbuch aktualisieren. 

Beispielsweise ändern wir einige Begriffe in PowerShell und speichern diese lokal. Sie können sie in einem Editor bearbeiten und anschließend die vorherigen Begriffe an Ort und Stelle aktualisieren. 

Rufen Sie zuerst das Wörterbuchobjekt ab:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Beim Drucken  `$dict` werden die verschiedenen Variablen angezeigt. Die eigentlichen Schlüsselwörter sind in einem Objekt auf dem Back-End gespeichert. `$dict.KeywordDictionary` enthält sie jedoch als String, den Sie zum Ändern des Wörterbuchs verwenden. 

Bevor Sie das Wörterbuch ändern, müssen Sie die Zeichenfolge der Begriffe mit der  `.split(',')`-Methode wieder in ein Array umwandeln. Dann bereinigen Sie mit der `.trim()`-Methode die unerwünschten Leerzeichen zwischen den Schlüsselwörtern und lassen nur die Schlüsselwörter übrig, die Sie brauchen. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Jetzt entfernen Sie einige Ausdrücke aus dem Wörterbuch. Da das Beispielwörterbuch nur einige Schlüsselwörter enthält, können Sie diesen Schritt auch überspringen und mit dem Exportieren des Wörterbuchs und dem Bearbeiten im Editor fortfahren. Wörterbücher enthalten aber in der Regel eine große Textmenge, daher erfahren Sie zunächst, wie diese in PowerShell ganz einfach bearbeiten werden.
  
Im letzten Schritt haben Sie die Schlüsselwörter in einem Array gespeichert. Es gibt mehrere Möglichkeiten, um [Elemente aus einem Array zu entfernen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)). Der Einfachheit halber erstellen Sie aber ein Array der Ausdrücke, die Sie aus dem Wörterbuch entfernen möchten, und kopieren dann nur die Wörterbuchbegriffe dort hinein, die sich nicht in der Liste der zu entfernenden Ausdrücke befinden.
  
Führen Sie den Befehl  `$terms` aus, um die aktuelle Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus: 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

Führen Sie diesen Befehl aus, um die Ausdrücke anzugeben, die Sie entfernen möchten:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Führen Sie diesen Befehl, um die Ausdrücke tatsächlich aus der Liste zu entfernen:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Führen Sie den Befehl  `$updatedTerms` aus, um die aktualisierte Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus (die angegebenen Ausdrücke wurden entfernt): 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Öffnen Sie jetzt die Datei, fügen Sie Ihre anderen Ausdrücke hinzu, und speichern Sie die Datei mit Unicode-Codierung (UTF-16). Nun laden Sie die aktualisierten Ausdrücke hoch und aktualisieren das vorhandene Wörterbuch.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Jetzt wurde das Wörterbuch an Ort und Stelle aktualisiert. Das Feld `Identity` nimmt den Namen des Wörterbuchs an. Wenn Sie mithilfe des Cmdlets `set-` auch den Namen Ihres Wörterbuchs ändern wollten, müssten Sie lediglich der Zeile oben den Parameter `-Name` mit dem neuen Namen des Wörterbuchs hinzufügen. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Verwenden von Schlüsselwörterbüchern in benutzerdefinierten vertraulichen Informationstypen und DLP-Richtlinien

Schlüsselwörterbücher können als Bestandteil der Übereinstimmungsanforderungen für einen benutzerdefinierten Typ vertraulicher Informationen oder selbst als Typ vertraulicher Informationen verwendet werden. Für beide müssen Sie einen [benutzerdefinierten Typ vertraulicher Informationen](create-a-custom-sensitive-information-type-in-scc-powershell.md) erstellen. Befolgen Sie die Anweisungen im verknüpften Artikel um einen Typ vertraulicher Informationen zu erstellen. Sobald Sie über den XML-Code verfügen, benötigen Sie den GUID-Bezeichner für das Wörterbuch, um es zu verwenden.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Um die Identität des Wörterbuchs zu erhalten, führen Sie den folgenden Befehl aus, und kopieren Sie den **Identity**-Eigenschaftswert: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

Die Ausgabe des Befehls sieht wie folgt aus:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Fügen Sie die Identität in den XML-Code Ihres benutzerdefinierten Typs vertraulicher Informationen ein, und laden Sie ihn hoch. Jetzt wird das Wörterbuch in Ihrer Liste der Typen vertraulicher Informationen angezeigt, und Sie können es direkt in Ihrer Richtlinie verwenden und festlegen, bei wie vielen Schlüsselwörtern eine Übereinstimmung festgestellt werden muss.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> Microsoft 365 Information Protection unterstützt in der Vorschauversion Sprachen mit Doppelbyte-Zeichensätzen für:
> - Chinesisch (vereinfacht)
> - Chinesisch (traditionell)
> - Koreanisch
> - Japanisch
>
>Diese Unterstützung ist für vertrauliche Informationstypen verfügbar. Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).
