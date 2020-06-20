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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lesen Sie die grundlegenden Schritte zum Erstellen eines Stichwort Wörterbuchs im Office 365 Security & Compliance Center.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818054"
---
# <a name="create-a-keyword-dictionary"></a>Erstellen eines Schlüsselwörterbuchs

Mit der Verhinderung von Datenverlust (DLP) können Sie vertrauliche Informationen identifizieren, überwachen und schützen. Das Identifizieren von vertraulichen Informationen erfordert manchmal das Suchen nach Stichwörtern, insbesondere wenn generische Inhalte (wie etwa gesundheitsbezogene Kommunikation) oder ungeeignete oder explizite Sprache identifiziert werden. Zwar können Sie Stichwortlisten in Typen mit vertraulichen Informationen erstellen, Keyword-Listen sind jedoch in ihrer Größe limitiert und müssen zum Erstellen oder Bearbeiten von XML geändert werden. Stichwort Wörterbücher bieten eine einfachere Verwaltung von Schlüsselwörtern und in einem weitaus größeren Umfang, sodass bis zu 100.000 Begriffe pro Wörterbuch unterstützt werden.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Grundlegende Schritte zum Erstellen eines Schlüsselwörterbuchs

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. Verwenden Sie das **Security & Compliance Center** ( [https://protection.office.com](https://protection.office.com) ), oder stellen Sie eine Verbindung mit dem **Security &amp; Compliance Center PowerShell**her.
    
2. **Definieren oder laden Sie Ihre Schlüsselwörter aus ihrer beabsichtigten Quelle**. Der Assistent und das Cmdlet akzeptieren beide eine durch trennzeichengetrennte Liste von Schlüsselwörtern, um ein benutzerdefiniertes Stichwort Wörterbuch zu erstellen, sodass dieser Schritt geringfügig variiert, je nachdem, woher Ihre Schlüsselwörter stammen. Nach dem Laden werden diese codiert und in ein Bytearray konvertiert, bevor sie importiert werden.
    
3. **Erstellen Sie Ihr Wörterbuch**. Wählen Sie einen Namen und eine Beschreibung aus, und erstellen Sie Ihr Wörterbuch.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Erstellen eines Stichwort Wörterbuchs mithilfe des Security & Compliance Centers

Verwenden Sie die folgenden Schritte zum Erstellen und Importieren von Schlüsselwörtern für ein Benutzerwörterbuch:

1. Stellen Sie eine Verbindung mit dem Security & Compliance Center her ( [https://protection.office.com](https://protection.office.com) ).

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

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Kopieren Sie die Schlüsselwörter in eine Textdatei, und stellen Sie sicher, dass sich jedes Schlüsselwort in einer separaten Zeile befindet.
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
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

Beispielsweise ändern wir einige Ausdrücke in PowerShell, speichern die Begriffe Lokal, wo Sie Sie in einem Editor ändern können, und aktualisieren dann die vorherigen Ausdrücke. 

Rufen Sie zuerst das Wörterbuchobjekt ab:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

`$dict`Beim Drucken werden die verschiedenen Variablen angezeigt. Die Schlüsselwörter selbst werden in einem Objekt im Back-End gespeichert, `$dict.KeywordDictionary` enthalten jedoch eine Zeichenfolgendarstellung, die Sie zum Ändern des Wörterbuchs verwenden. 

Bevor Sie das Wörterbuch ändern, müssen Sie die Zeichenfolge von Ausdrücken mithilfe der-Methode wieder in ein Array umwandeln `.split(',')` . Anschließend bereinigen Sie die unerwünschten Leerzeichen zwischen den Stichwörtern mit der `.trim()` -Methode, sodass nur die Schlüsselwörter für die Arbeit übrig bleiben. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Verwenden von Schlüsselwörterbüchern in benutzerdefinierten vertraulichen Informationstypen und DLP-Richtlinien

Stichwort Wörterbücher können als Teil der Übereinstimmungs Anforderungen für einen benutzerdefinierten Typ vertraulicher Informationen oder als vertraulicher Informationstyp selbst verwendet werden. Beide erfordern die Erstellung eines [benutzerdefinierten Typs für vertrauliche Informationen](create-a-custom-sensitive-information-type-in-scc-powershell.md). Befolgen Sie die Anweisungen im verknüpften Artikel, um einen Typ für vertrauliche Informationen zu erstellen. Sobald Sie über den XML-Code verfügen, benötigen Sie den GUID-Bezeichner für das Wörterbuch, um ihn zu verwenden.
  
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


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
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
