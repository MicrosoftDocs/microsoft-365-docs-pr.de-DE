---
title: Ändern eines Schlüsselwortwörterbuchs
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
description: Erfahren Sie, wie Sie ein Schlüsselwortwörterbuch im Microsoft 365 Compliance Center ändern.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685210"
---
# <a name="modify-a-keyword-dictionary"></a>Ändern eines Schlüsselwortwörterbuchs

Möglicherweise müssen Sie einmal Schlüsselwörter in einem Ihrer Schlüsselwörterbücher oder in einem der integrierten Wörterbücher ändern. Sie können dies über PowerShell oder über das Compliance Center tun.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Ändern eines Schlüsselwortwörterbuchs im Compliance Center

Schlüsselwortwörterbücher können als oder `Primary elements` `Supporting elements` in Sit-Mustern (Sensitive Information Type) verwendet werden. Sie können ein Schlüsselwortwörterbuch bearbeiten, während Sie eine SIT oder eine vorhandene SIT erstellen. So bearbeiten Sie z. B. ein vorhandenes Schlüsselwortwörterbuch:

1. Öffnen Sie das Muster mit dem Schlüsselwortwörterbuch, das Sie aktualisieren möchten.
2. Suchen Sie das Schlüsselwortwörterbuch, das Sie aktualisieren möchten, und wählen Sie Bearbeiten aus. 
3.  Nehmen Sie Ihre Bearbeitungen mit einem Schlüsselwort pro Zeile vor.

![Screenshot bearbeiten von Schlüsselwörtern](../media/edit-keyword-dictionary.png)

4. Wählen Sie `Done` aus.

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Ändern eines Schlüsselwortwörterbuchs mithilfe von PowerShell 

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

Siehe auch
- [Erstellen eines Schlüsselwörterbuchs](create-a-keyword-dictionary.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md)
