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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300106"
---
# <a name="create-a-keyword-dictionary"></a>Schlüsselwörterbuch erstellen

Die Verhinderung von Datenverlust (DLP) kann Ihre vertraulichen Objekte identifizieren, überwachen und schützen. Das Identifizieren vertraulicher Objekte erfordert manchmal die Suche nach Schlüsselwörtern, insbesondere beim Erkennen von allgemeinen Inhalten (etwa bei Kommunikation im Gesundheitswesen) oder unangemessener oder unflätiger Sprache. Obwohl Sie Schlüsselwortlisten in vertraulichen Informationstypen erstellen können, sind Schlüsselwortlisten in ihrer Größe begrenzt und erfordern eine Änderung von XML, um sie zu erstellen oder zu bearbeiten. Schlüsselwörterbücher bieten eine einfachere Verwaltung von Stichwörtern und in einem viel größeren Umfang. Sie unterstützen bis zu 1 MB an Begriffen (Post-Kompression) im Wörterbuch und unterstützen alle Sprachen. Das Mandantenlimit liegt nach der Komprimierung ebenfalls bei 1 MB. Der 1 MB-Limit der Post-Kompression bedeutet, dass alle Wörterbücher zusammen über den gesamten Mandanten hinweg bis zu 1 Million Zeichen haben können.

## <a name="keyword-dictionary-limits"></a>Schlüsselwörterbücherlimits

Es gibt ein Limit von 50 Schlüsselwortwörterbuch-basierten vertraulichen Informationstypen, die pro Mandant erstellt werden können. Um herauszufinden, wie viele Schlüsselwörterbücher Ihr Mandant enthält, stellen Sie mithilfe des in [Herstellen einer Verbindung zu Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) beschriebenen Verfahrens eine Verbindung zu Ihrem Mandanten her, und führen Sie dieses PowerShell-Skript aus.

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
> Microsoft 365 Information Protection unterstützt Sprachen mit Doppelbyte-Zeichensätzen für:
> - Chinesisch (vereinfacht)
> - Chinesisch (traditionell)
> - Koreanisch
> - Japanisch
>
>Diese Unterstützung ist für vertrauliche Informationstypen verfügbar. Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).

> [!TIP]
> Um Muster zu erkennen, die chinesische/japanische Zeichen und einzelne Bytezeichen enthalten, oder um Muster zu erkennen, die Chinesisch/Japanisch und Englisch enthalten, definieren Sie zwei Varianten des Schlüsselworts oder regulären Ausdrucks. 
>
> Verwenden Sie z. B. zwei Varianten des Schlüsselworts, um ein Schlüsselwort wie „机密的document“ zu erkennen; eine mit einem Leerzeichen zwischen dem japanischen und dem englischen Text und eine andere ohne Leerzeichen zwischen dem japanischen und dem englischen Text. Daher sollten die Schlüsselwörter, die in SIT hinzugefügt werden sollen, „机密的 document“ und „机密的document“ lauten. Ebenso sollten zwei Varianten verwendet werden, um den Ausdruck „東京オリンピック2020“ zu erkennen; „東京オリンピック 2020“ und „東京オリンピック2020“.
>
> Achten Sie beim Erstellen eines regulären Ausdrucks mit einem Doppeltbyte-Bindestrich oder einem Doppeltbyte-Punkt darauf, beide Zeichen mit Escapezeichen zu versehen, so wie man einen Bindestrich oder einen Punkt in einem regulären Ausdruck mit Escapezeichen versehen würde. Hier ist ein Referenzbeispiel eines regulären Ausdrucks:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> Es wird empfohlen, eine Zeichenfolgenübereinstimmung anstelle einer Wortübereinstimmung in einer Schlüsselwortliste zu verwenden.
