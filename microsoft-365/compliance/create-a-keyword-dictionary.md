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
ms.openlocfilehash: b70deed531204f2ffe85253bd9ae2073dad291ec
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632191"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="ddc29-103">Schlüsselwörterbuch erstellen</span><span class="sxs-lookup"><span data-stu-id="ddc29-103">Create a keyword dictionary</span></span>

<span data-ttu-id="ddc29-104">Die Verhinderung von Datenverlust (DLP) kann Ihre vertraulichen Objekte identifizieren, überwachen und schützen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="ddc29-105">Das Identifizieren vertraulicher Objekte erfordert manchmal die Suche nach Schlüsselwörtern, insbesondere beim Erkennen von allgemeinen Inhalten (etwa bei Kommunikation im Gesundheitswesen) oder unangemessener oder unflätiger Sprache.</span><span class="sxs-lookup"><span data-stu-id="ddc29-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="ddc29-106">Obwohl Sie Schlüsselwortlisten in vertraulichen Informationstypen erstellen können, sind Schlüsselwortlisten in ihrer Größe begrenzt und erfordern eine Änderung von XML, um sie zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ddc29-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="ddc29-107">Schlüsselwörterbücher bieten eine einfachere Verwaltung von Stichwörtern und in einem viel größeren Umfang. Sie unterstützen bis zu 1 MB an Begriffen (Post-Kompression) im Wörterbuch und unterstützen alle Sprachen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="ddc29-108">Das Mandantenlimit liegt nach der Komprimierung ebenfalls bei 1 MB.</span><span class="sxs-lookup"><span data-stu-id="ddc29-108">The tenant limit is also 1MB after compression.</span></span> <span data-ttu-id="ddc29-109">Der 1 MB-Limit der Post-Kompression bedeutet, dass alle Wörterbücher zusammen über den gesamten Mandanten hinweg bis zu 1 Million Zeichen haben können.</span><span class="sxs-lookup"><span data-stu-id="ddc29-109">1MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million character.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="ddc29-110">Schlüsselwörterbücherlimits</span><span class="sxs-lookup"><span data-stu-id="ddc29-110">Keyword dictionary limits</span></span>

<span data-ttu-id="ddc29-111">Es gibt ein Limit von 50 Schlüsselwortwörterbuch-basierten vertraulichen Informationstypen, die pro Mandant erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="ddc29-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="ddc29-112">Um herauszufinden, wie viele Schlüsselwörterbücher Ihr Mandant enthält, können Sie dieses PowerShell-Skript für Ihren Mandanten ausführen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-112">To find out how many keyword dictionaries you have in your tenant, you can run this PowerShell script against your tenant.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="ddc29-113">Grundlegende Schritte zum Erstellen eines Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="ddc29-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="ddc29-p103">Die Schlüsselwörter für Ihr Wörterbuch können aus einer Vielzahl von Quellen stammen, meistens aber aus einer in den Dienst importierten Datei (etwa einer CSV- oder TXT-Liste), oder durch ein einem PowerShell-Cmdlet, aus einer Liste, die Sie direkt in das PowerShell-Cmdlet eingeben, oder aus einem vorhandenen Wörterbuch.Beim Erstellen eines Schlüsselwörterbuchs befolgen Sie die gleichen einfachen Schritte:</span><span class="sxs-lookup"><span data-stu-id="ddc29-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="ddc29-116">Verwenden Sie das **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) oder stellen Sie eine Verbindung zum **Security &amp; Compliance Center PowerShell** her.</span><span class="sxs-lookup"><span data-stu-id="ddc29-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="ddc29-117">**Definieren oder laden Sie Ihre Schlüsselwörter aus der vorgesehenen Quelle**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="ddc29-118">Sowohl der Assistent als auch das Cmdlet akzeptieren eine durch Komma getrennte Liste von Schlüsselwörtern, um ein benutzerdefiniertes Schlüsselwörterbuch zu erstellen. Dieser Schritt variiert daher leicht, je nachdem, woher Ihre Schlüsselwörter stammen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="ddc29-119">Sobald sie geladen sind, werden sie kodiert und in ein Byte-Array konvertiert, bevor sie importiert werden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="ddc29-120">**Erstellen Sie Ihr Wörterbuch**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-120">**Create your dictionary**.</span></span> <span data-ttu-id="ddc29-121">Wählen Sie einen Namen und eine Beschreibung und erstellen Sie Ihr Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="ddc29-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="ddc29-122">Schlüsselwörterbuch mit dem Security & Compliance Center erstellen</span><span class="sxs-lookup"><span data-stu-id="ddc29-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="ddc29-123">Verwenden Sie die folgenden Schritte zum Erstellen und Importieren von Schlüsselwörtern für ein Benutzerwörterbuch:</span><span class="sxs-lookup"><span data-stu-id="ddc29-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="ddc29-124">Stellen Sie die Verbindung zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) her.</span><span class="sxs-lookup"><span data-stu-id="ddc29-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="ddc29-125">Navigieren Sie zu **Klassifizierungen > Typen vertraulicher Informationen**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="ddc29-126">Wählen Sie **Erstellen** aus, geben Sie einen **Namen** und eine **Beschreibung** für Ihren vertraulichen Infotyp ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="ddc29-127">Wählen Sie **Element hinzufügen** und dann **Wörterbuch (große Schlüsselwörter)** in der Dropdownliste **Inhalt erkennen, der Folgendes enthält** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="ddc29-128">Wählen Sie **Wörterbuch hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="ddc29-129">Wählen Sie unter dem Steuerelement "Suche" die Option **Hier können Sie neue Schlüsselwörterbücher erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="ddc29-130">Geben Sie einen **Namen** für Ihr Benutzerwörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="ddc29-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="ddc29-131">Klicken Sie auf **Importieren**, und wählen Sie dann entweder **Aus Text** oder **Aus CSV** aus, je nach Typ der Schlüsselwortdatei.</span><span class="sxs-lookup"><span data-stu-id="ddc29-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="ddc29-132">Wählen Sie im Dialogfeld "Datei" die Schlüsselwortdatei auf Ihrem lokalen PC oder aus der Netzwerkfreigabe aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="ddc29-133">Klicken Sie auf **Speichern**, und wählen Sie dann Ihr Benutzerwörterbuch aus der Liste **Schlüsselwörterbücher** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="ddc29-134">Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="ddc29-135">Überprüfen und vervollständigen Sie den ausgewählten Typ vertraulicher Informationen, und wählen Sie dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ddc29-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="ddc29-136">Erstellen eines Schlüsselwörterbuchs aus einer Datei mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddc29-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="ddc29-137">Wenn Sie ein großes Wörterbuch erstellen, müssen Sie möglicherweise Schlüsselwörter verwenden, die aus einer Datei oder einer exportierten Liste aus einer anderen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="ddc29-138">In diesem Fall erstellen Sie ein Schlüsselwörterbuch, das eine Liste unangemessener Ausdrücke enthält, um von außen eingehende E-Mail-Nachrichten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="ddc29-139">Stellen Sie zunächst eine Verbindung zum [Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="ddc29-139">You must first [connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="ddc29-140">Kopieren Sie die Schlüsselwörter in eine Textdatei, und stellen Sie sicher, dass sich jedes Schlüsselwort in einer separaten Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="ddc29-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="ddc29-p107">Speichern Sie die Textdatei in Unicode-Codierung: Im Editor \> **Speichern als** \> **Codierung** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="ddc29-143">Lesen Sie die Datei in eine Variable, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddc29-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="ddc29-144">Erstellen Sie das Wörterbuch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddc29-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="ddc29-145">Ändern eines vorhandenen Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="ddc29-145">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="ddc29-146">Möglicherweise müssen Sie einmal Schlüsselwörter in einem Ihrer Schlüsselwörterbücher oder in einem der integrierten Wörterbücher ändern.</span><span class="sxs-lookup"><span data-stu-id="ddc29-146">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="ddc29-147">Derzeit können Sie mit PowerShell nur ein benutzerdefiniertes Schlüsselwörterbuch aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ddc29-147">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="ddc29-148">Beispielsweise ändern wir einige Begriffe in PowerShell und speichern diese lokal. Sie können sie in einem Editor bearbeiten und anschließend die vorherigen Begriffe an Ort und Stelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ddc29-148">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="ddc29-149">Rufen Sie zuerst das Wörterbuchobjekt ab:</span><span class="sxs-lookup"><span data-stu-id="ddc29-149">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="ddc29-150">Beim Drucken  `$dict` werden die verschiedenen Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddc29-150">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="ddc29-151">Die eigentlichen Schlüsselwörter sind in einem Objekt auf dem Back-End gespeichert. `$dict.KeywordDictionary` enthält sie jedoch als String, den Sie zum Ändern des Wörterbuchs verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-151">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="ddc29-152">Bevor Sie das Wörterbuch ändern, müssen Sie die Zeichenfolge der Begriffe mit der  `.split(',')`-Methode wieder in ein Array umwandeln.</span><span class="sxs-lookup"><span data-stu-id="ddc29-152">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="ddc29-153">Dann bereinigen Sie mit der `.trim()`-Methode die unerwünschten Leerzeichen zwischen den Schlüsselwörtern und lassen nur die Schlüsselwörter übrig, die Sie brauchen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-153">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="ddc29-p111">Jetzt entfernen Sie einige Ausdrücke aus dem Wörterbuch. Da das Beispielwörterbuch nur einige Schlüsselwörter enthält, können Sie diesen Schritt auch überspringen und mit dem Exportieren des Wörterbuchs und dem Bearbeiten im Editor fortfahren. Wörterbücher enthalten aber in der Regel eine große Textmenge, daher erfahren Sie zunächst, wie diese in PowerShell ganz einfach bearbeiten werden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="ddc29-p112">Im letzten Schritt haben Sie die Schlüsselwörter in einem Array gespeichert. Es gibt mehrere Möglichkeiten, um [Elemente aus einem Array zu entfernen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)). Der Einfachheit halber erstellen Sie aber ein Array der Ausdrücke, die Sie aus dem Wörterbuch entfernen möchten, und kopieren dann nur die Wörterbuchbegriffe dort hinein, die sich nicht in der Liste der zu entfernenden Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="ddc29-p113">Führen Sie den Befehl  `$terms` aus, um die aktuelle Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ddc29-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="ddc29-160">Führen Sie diesen Befehl aus, um die Ausdrücke anzugeben, die Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="ddc29-160">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="ddc29-161">Führen Sie diesen Befehl, um die Ausdrücke tatsächlich aus der Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ddc29-161">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="ddc29-p114">Führen Sie den Befehl  `$updatedTerms` aus, um die aktualisierte Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus (die angegebenen Ausdrücke wurden entfernt):</span><span class="sxs-lookup"><span data-stu-id="ddc29-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="ddc29-p115">Öffnen Sie jetzt einfach die Datei, fügen Sie Ihre zusätzlichen Ausdrücke hinzu, und speichern Sie die Datei mit Unicode-Codierung (UTF-16). Nun laden Sie die aktualisierten Ausdrücke hoch und aktualisieren das vorhandene Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="ddc29-p116">Das vorhandene Wörterbuch wurde nun aktualisiert. Beachten Sie, dass das Feld `Identity` den Namen des Wörterbuchs erhält. Wenn Sie auch den Namen Ihres Wörterbuchs mit dem `set-`-Cmdlet ändern möchten, müssten Sie oben einfach den `-Name`-Parameter mit dem neuen Wörterbuchnamen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="ddc29-169">Verwenden von Schlüsselwörterbüchern in benutzerdefinierten vertraulichen Informationstypen und DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ddc29-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="ddc29-170">Schlüsselwörterbücher können als Bestandteil der Übereinstimmungsanforderungen für einen benutzerdefinierten Typ vertraulicher Informationen oder selbst als Typ vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="ddc29-171">Für beide müssen Sie einen [benutzerdefinierten Typ vertraulicher Informationen](create-a-custom-sensitive-information-type-in-scc-powershell.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="ddc29-172">Befolgen Sie die Anweisungen im verknüpften Artikel um einen Typ vertraulicher Informationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddc29-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="ddc29-173">Sobald Sie über den XML-Code verfügen, benötigen Sie den GUID-Bezeichner für das Wörterbuch, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddc29-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="ddc29-174">Um die Identität des Wörterbuchs zu erhalten, führen Sie den folgenden Befehl aus, und kopieren Sie den **Identity**-Eigenschaftswert:</span><span class="sxs-lookup"><span data-stu-id="ddc29-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="ddc29-175">Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ddc29-175">The output of the command looks like this:</span></span>
  
<span data-ttu-id="ddc29-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="ddc29-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="ddc29-p118">Fügen Sie die Identität in den XML-Code Ihres benutzerdefinierten Typs vertraulicher Informationen ein, und laden Sie ihn hoch. Jetzt wird das Wörterbuch in Ihrer Liste der Typen vertraulicher Informationen angezeigt, und Sie können es direkt in Ihrer Richtlinie verwenden und festlegen, bei wie vielen Schlüsselwörtern eine Übereinstimmung festgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="ddc29-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="ddc29-179">Microsoft 365 Information Protection unterstützt in der Vorschauversion Sprachen mit Doppelbyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="ddc29-179">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="ddc29-180">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="ddc29-180">Chinese (simplified)</span></span>
> - <span data-ttu-id="ddc29-181">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="ddc29-181">Chinese (traditional)</span></span>
> - <span data-ttu-id="ddc29-182">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="ddc29-182">Korean</span></span>
> - <span data-ttu-id="ddc29-183">Japanisch</span><span class="sxs-lookup"><span data-stu-id="ddc29-183">Japanese</span></span>
>
><span data-ttu-id="ddc29-184">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ddc29-184">This support is available for sensitive information types.</span></span> <span data-ttu-id="ddc29-185">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="ddc29-185">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>