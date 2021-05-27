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
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="831be-103">Ändern eines Schlüsselwortwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="831be-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="831be-104">Möglicherweise müssen Sie einmal Schlüsselwörter in einem Ihrer Schlüsselwörterbücher oder in einem der integrierten Wörterbücher ändern.</span><span class="sxs-lookup"><span data-stu-id="831be-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="831be-105">Sie können dies über PowerShell oder über das Compliance Center tun.</span><span class="sxs-lookup"><span data-stu-id="831be-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="831be-106">Ändern eines Schlüsselwortwörterbuchs im Compliance Center</span><span class="sxs-lookup"><span data-stu-id="831be-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="831be-107">Schlüsselwortwörterbücher können als oder `Primary elements` `Supporting elements` in Sit-Mustern (Sensitive Information Type) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="831be-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="831be-108">Sie können ein Schlüsselwortwörterbuch bearbeiten, während Sie eine SIT oder eine vorhandene SIT erstellen.</span><span class="sxs-lookup"><span data-stu-id="831be-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="831be-109">So bearbeiten Sie z. B. ein vorhandenes Schlüsselwortwörterbuch:</span><span class="sxs-lookup"><span data-stu-id="831be-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="831be-110">Öffnen Sie das Muster mit dem Schlüsselwortwörterbuch, das Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="831be-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="831be-111">Suchen Sie das Schlüsselwortwörterbuch, das Sie aktualisieren möchten, und wählen Sie Bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="831be-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="831be-112">Nehmen Sie Ihre Bearbeitungen mit einem Schlüsselwort pro Zeile vor.</span><span class="sxs-lookup"><span data-stu-id="831be-112">Make your edits, using one keyword per line.</span></span>

![Screenshot bearbeiten von Schlüsselwörtern](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="831be-114">Wählen Sie `Done` aus.</span><span class="sxs-lookup"><span data-stu-id="831be-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="831be-115">Ändern eines Schlüsselwortwörterbuchs mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="831be-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="831be-116">Beispielsweise ändern wir einige Begriffe in PowerShell und speichern diese lokal. Sie können sie in einem Editor bearbeiten und anschließend die vorherigen Begriffe an Ort und Stelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="831be-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="831be-117">Rufen Sie zuerst das Wörterbuchobjekt ab:</span><span class="sxs-lookup"><span data-stu-id="831be-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="831be-118">Beim Drucken  `$dict` werden die verschiedenen Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="831be-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="831be-119">Die eigentlichen Schlüsselwörter sind in einem Objekt auf dem Back-End gespeichert. `$dict.KeywordDictionary` enthält sie jedoch als String, den Sie zum Ändern des Wörterbuchs verwenden.</span><span class="sxs-lookup"><span data-stu-id="831be-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="831be-120">Bevor Sie das Wörterbuch ändern, müssen Sie die Zeichenfolge der Begriffe mit der  `.split(',')`-Methode wieder in ein Array umwandeln.</span><span class="sxs-lookup"><span data-stu-id="831be-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="831be-121">Dann bereinigen Sie mit der `.trim()`-Methode die unerwünschten Leerzeichen zwischen den Schlüsselwörtern und lassen nur die Schlüsselwörter übrig, die Sie brauchen.</span><span class="sxs-lookup"><span data-stu-id="831be-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="831be-p105">Jetzt entfernen Sie einige Ausdrücke aus dem Wörterbuch. Da das Beispielwörterbuch nur einige Schlüsselwörter enthält, können Sie diesen Schritt auch überspringen und mit dem Exportieren des Wörterbuchs und dem Bearbeiten im Editor fortfahren. Wörterbücher enthalten aber in der Regel eine große Textmenge, daher erfahren Sie zunächst, wie diese in PowerShell ganz einfach bearbeiten werden.</span><span class="sxs-lookup"><span data-stu-id="831be-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="831be-p106">Im letzten Schritt haben Sie die Schlüsselwörter in einem Array gespeichert. Es gibt mehrere Möglichkeiten, um [Elemente aus einem Array zu entfernen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)). Der Einfachheit halber erstellen Sie aber ein Array der Ausdrücke, die Sie aus dem Wörterbuch entfernen möchten, und kopieren dann nur die Wörterbuchbegriffe dort hinein, die sich nicht in der Liste der zu entfernenden Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="831be-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="831be-p107">Führen Sie den Befehl  `$terms` aus, um die aktuelle Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="831be-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="831be-128">Führen Sie diesen Befehl aus, um die Ausdrücke anzugeben, die Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="831be-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="831be-129">Führen Sie diesen Befehl, um die Ausdrücke tatsächlich aus der Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="831be-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="831be-p108">Führen Sie den Befehl  `$updatedTerms` aus, um die aktualisierte Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus (die angegebenen Ausdrücke wurden entfernt):</span><span class="sxs-lookup"><span data-stu-id="831be-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="831be-p109">Öffnen Sie jetzt die Datei, fügen Sie Ihre anderen Ausdrücke hinzu, und speichern Sie die Datei mit Unicode-Codierung (UTF-16). Nun laden Sie die aktualisierten Ausdrücke hoch und aktualisieren das vorhandene Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="831be-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="831be-134">Jetzt wurde das Wörterbuch an Ort und Stelle aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="831be-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="831be-135">Das Feld `Identity` nimmt den Namen des Wörterbuchs an.</span><span class="sxs-lookup"><span data-stu-id="831be-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="831be-136">Wenn Sie mithilfe des Cmdlets `set-` auch den Namen Ihres Wörterbuchs ändern wollten, müssten Sie lediglich der Zeile oben den Parameter `-Name` mit dem neuen Namen des Wörterbuchs hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="831be-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="831be-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="831be-137">See Also</span></span>
- [<span data-ttu-id="831be-138">Erstellen eines Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="831be-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="831be-139">Erstellen eines benutzerdefinierten vertraulichen Informationstyps</span><span class="sxs-lookup"><span data-stu-id="831be-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
