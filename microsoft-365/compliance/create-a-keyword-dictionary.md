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
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="4c067-103">Erstellen eines Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="4c067-103">Create a keyword dictionary</span></span>

<span data-ttu-id="4c067-104">Mit der Verhinderung von Datenverlust (DLP) können Sie vertrauliche Informationen identifizieren, überwachen und schützen.</span><span class="sxs-lookup"><span data-stu-id="4c067-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="4c067-105">Das Identifizieren von vertraulichen Informationen erfordert manchmal das Suchen nach Stichwörtern, insbesondere wenn generische Inhalte (wie etwa gesundheitsbezogene Kommunikation) oder ungeeignete oder explizite Sprache identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-105">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="4c067-106">Zwar können Sie Stichwortlisten in Typen mit vertraulichen Informationen erstellen, Keyword-Listen sind jedoch in ihrer Größe limitiert und müssen zum Erstellen oder Bearbeiten von XML geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="4c067-107">Stichwort Wörterbücher bieten eine einfachere Verwaltung von Schlüsselwörtern und in einem weitaus größeren Umfang, sodass bis zu 100.000 Begriffe pro Wörterbuch unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="4c067-108">Grundlegende Schritte zum Erstellen eines Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="4c067-108">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="4c067-p102">Die Schlüsselwörter für Ihr Wörterbuch können aus einer Vielzahl von Quellen stammen, meistens aber aus einer in den Dienst importierten Datei (etwa einer CSV- oder TXT-Liste), oder durch ein einem PowerShell-Cmdlet, aus einer Liste, die Sie direkt in das PowerShell-Cmdlet eingeben, oder aus einem vorhandenen Wörterbuch.Beim Erstellen eines Schlüsselwörterbuchs befolgen Sie die gleichen einfachen Schritte:</span><span class="sxs-lookup"><span data-stu-id="4c067-p102">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="4c067-111">Verwenden Sie das **Security & Compliance Center** ( [https://protection.office.com](https://protection.office.com) ), oder stellen Sie eine Verbindung mit dem **Security &amp; Compliance Center PowerShell**her.</span><span class="sxs-lookup"><span data-stu-id="4c067-111">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="4c067-112">**Definieren oder laden Sie Ihre Schlüsselwörter aus ihrer beabsichtigten Quelle**.</span><span class="sxs-lookup"><span data-stu-id="4c067-112">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="4c067-113">Der Assistent und das Cmdlet akzeptieren beide eine durch trennzeichengetrennte Liste von Schlüsselwörtern, um ein benutzerdefiniertes Stichwort Wörterbuch zu erstellen, sodass dieser Schritt geringfügig variiert, je nachdem, woher Ihre Schlüsselwörter stammen.</span><span class="sxs-lookup"><span data-stu-id="4c067-113">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="4c067-114">Nach dem Laden werden diese codiert und in ein Bytearray konvertiert, bevor sie importiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-114">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="4c067-115">**Erstellen Sie Ihr Wörterbuch**.</span><span class="sxs-lookup"><span data-stu-id="4c067-115">**Create your dictionary**.</span></span> <span data-ttu-id="4c067-116">Wählen Sie einen Namen und eine Beschreibung aus, und erstellen Sie Ihr Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="4c067-116">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="4c067-117">Erstellen eines Stichwort Wörterbuchs mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="4c067-117">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="4c067-118">Verwenden Sie die folgenden Schritte zum Erstellen und Importieren von Schlüsselwörtern für ein Benutzerwörterbuch:</span><span class="sxs-lookup"><span data-stu-id="4c067-118">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="4c067-119">Stellen Sie eine Verbindung mit dem Security & Compliance Center her ( [https://protection.office.com](https://protection.office.com) ).</span><span class="sxs-lookup"><span data-stu-id="4c067-119">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="4c067-120">Navigieren Sie zu **Klassifizierungen > Typen vertraulicher Informationen**.</span><span class="sxs-lookup"><span data-stu-id="4c067-120">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="4c067-121">Wählen Sie **Erstellen** aus, geben Sie einen **Namen** und eine **Beschreibung** für Ihren vertraulichen Infotyp ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-121">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="4c067-122">Wählen Sie **Element hinzufügen** und dann **Wörterbuch (große Schlüsselwörter)** in der Dropdownliste **Inhalt erkennen, der Folgendes enthält** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-122">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="4c067-123">Wählen Sie **Wörterbuch hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-123">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="4c067-124">Wählen Sie unter dem Steuerelement "Suche" die Option **Hier können Sie neue Schlüsselwörterbücher erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-124">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="4c067-125">Geben Sie einen **Namen** für Ihr Benutzerwörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="4c067-125">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="4c067-126">Klicken Sie auf **Importieren**, und wählen Sie dann entweder **Aus Text** oder **Aus CSV** aus, je nach Typ der Schlüsselwortdatei.</span><span class="sxs-lookup"><span data-stu-id="4c067-126">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="4c067-127">Wählen Sie im Dialogfeld "Datei" die Schlüsselwortdatei auf Ihrem lokalen PC oder aus der Netzwerkfreigabe aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="4c067-127">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="4c067-128">Klicken Sie auf **Speichern**, und wählen Sie dann Ihr Benutzerwörterbuch aus der Liste **Schlüsselwörterbücher** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-128">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="4c067-129">Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c067-129">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="4c067-130">Überprüfen und vervollständigen Sie den ausgewählten Typ vertraulicher Informationen, und wählen Sie dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4c067-130">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="4c067-131">Erstellen eines Schlüsselwörterbuchs aus einer Datei mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c067-131">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="4c067-p105">Häufig, wenn Sie ein großes Wörterbuch erstellen müssen, können Sie Stichwörter aus einer Datei oder aus einer aus einer anderen Quelle exportierten Liste verwenden. In diesem Fall erstellen Sie ein Stichwort Wörterbuch mit einer Liste ungeeigneter Sprache, die in externen e-Mails angezeigt wird. Sie müssen zunächst [eine Verbindung mit dem Security &amp; Compliance Center PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c067-p105">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="4c067-135">Kopieren Sie die Schlüsselwörter in eine Textdatei, und stellen Sie sicher, dass sich jedes Schlüsselwort in einer separaten Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="4c067-135">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="4c067-p106">Speichern Sie die Textdatei in Unicode-Codierung: Im Editor \> **Speichern als** \> **Codierung** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="4c067-p106">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="4c067-138">Lesen Sie die Datei in eine Variable, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="4c067-138">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="4c067-139">Erstellen Sie das Wörterbuch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="4c067-139">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="4c067-140">Ändern eines vorhandenen Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="4c067-140">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="4c067-141">Möglicherweise müssen Sie einmal Schlüsselwörter in einem Ihrer Schlüsselwörterbücher oder in einem der integrierten Wörterbücher ändern.</span><span class="sxs-lookup"><span data-stu-id="4c067-141">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="4c067-142">Derzeit können Sie mit PowerShell nur ein benutzerdefiniertes Schlüsselwörterbuch aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4c067-142">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="4c067-143">Beispielsweise ändern wir einige Ausdrücke in PowerShell, speichern die Begriffe Lokal, wo Sie Sie in einem Editor ändern können, und aktualisieren dann die vorherigen Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4c067-143">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="4c067-144">Rufen Sie zuerst das Wörterbuchobjekt ab:</span><span class="sxs-lookup"><span data-stu-id="4c067-144">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="4c067-145">`$dict`Beim Drucken werden die verschiedenen Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c067-145">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="4c067-146">Die Schlüsselwörter selbst werden in einem Objekt im Back-End gespeichert, `$dict.KeywordDictionary` enthalten jedoch eine Zeichenfolgendarstellung, die Sie zum Ändern des Wörterbuchs verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c067-146">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="4c067-147">Bevor Sie das Wörterbuch ändern, müssen Sie die Zeichenfolge von Ausdrücken mithilfe der-Methode wieder in ein Array umwandeln `.split(',')` .</span><span class="sxs-lookup"><span data-stu-id="4c067-147">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="4c067-148">Anschließend bereinigen Sie die unerwünschten Leerzeichen zwischen den Stichwörtern mit der `.trim()` -Methode, sodass nur die Schlüsselwörter für die Arbeit übrig bleiben.</span><span class="sxs-lookup"><span data-stu-id="4c067-148">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="4c067-p110">Jetzt entfernen Sie einige Ausdrücke aus dem Wörterbuch. Da das Beispielwörterbuch nur einige Schlüsselwörter enthält, können Sie diesen Schritt auch überspringen und mit dem Exportieren des Wörterbuchs und dem Bearbeiten im Editor fortfahren. Wörterbücher enthalten aber in der Regel eine große Textmenge, daher erfahren Sie zunächst, wie diese in PowerShell ganz einfach bearbeiten werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-p110">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="4c067-p111">Im letzten Schritt haben Sie die Schlüsselwörter in einem Array gespeichert. Es gibt mehrere Möglichkeiten, um [Elemente aus einem Array zu entfernen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)). Der Einfachheit halber erstellen Sie aber ein Array der Ausdrücke, die Sie aus dem Wörterbuch entfernen möchten, und kopieren dann nur die Wörterbuchbegriffe dort hinein, die sich nicht in der Liste der zu entfernenden Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="4c067-p111">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="4c067-p112">Führen Sie den Befehl  `$terms` aus, um die aktuelle Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4c067-p112">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="4c067-155">Führen Sie diesen Befehl aus, um die Ausdrücke anzugeben, die Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="4c067-155">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="4c067-156">Führen Sie diesen Befehl, um die Ausdrücke tatsächlich aus der Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="4c067-156">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="4c067-p113">Führen Sie den Befehl  `$updatedTerms` aus, um die aktualisierte Liste von Ausdrücken anzuzeigen. Die Ausgabe des Befehls sieht wie folgt aus (die angegebenen Ausdrücke wurden entfernt):</span><span class="sxs-lookup"><span data-stu-id="4c067-p113">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="4c067-p114">Öffnen Sie jetzt einfach die Datei, fügen Sie Ihre zusätzlichen Ausdrücke hinzu, und speichern Sie die Datei mit Unicode-Codierung (UTF-16). Nun laden Sie die aktualisierten Ausdrücke hoch und aktualisieren das vorhandene Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="4c067-p114">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="4c067-p115">Das vorhandene Wörterbuch wurde nun aktualisiert. Beachten Sie, dass das Feld `Identity` den Namen des Wörterbuchs erhält. Wenn Sie auch den Namen Ihres Wörterbuchs mit dem `set-`-Cmdlet ändern möchten, müssten Sie oben einfach den `-Name`-Parameter mit dem neuen Wörterbuchnamen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c067-p115">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="4c067-164">Verwenden von Schlüsselwörterbüchern in benutzerdefinierten vertraulichen Informationstypen und DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4c067-164">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="4c067-165">Stichwort Wörterbücher können als Teil der Übereinstimmungs Anforderungen für einen benutzerdefinierten Typ vertraulicher Informationen oder als vertraulicher Informationstyp selbst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c067-165">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="4c067-166">Beide erfordern die Erstellung eines [benutzerdefinierten Typs für vertrauliche Informationen](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-166">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="4c067-167">Befolgen Sie die Anweisungen im verknüpften Artikel, um einen Typ für vertrauliche Informationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c067-167">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="4c067-168">Sobald Sie über den XML-Code verfügen, benötigen Sie den GUID-Bezeichner für das Wörterbuch, um ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c067-168">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="4c067-169">Um die Identität des Wörterbuchs zu erhalten, führen Sie den folgenden Befehl aus, und kopieren Sie den **Identity**-Eigenschaftswert:</span><span class="sxs-lookup"><span data-stu-id="4c067-169">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="4c067-170">Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4c067-170">The output of the command looks like this:</span></span>
  
<span data-ttu-id="4c067-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="4c067-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="4c067-p117">Fügen Sie die Identität in den XML-Code Ihres benutzerdefinierten Typs vertraulicher Informationen ein, und laden Sie ihn hoch. Jetzt wird das Wörterbuch in Ihrer Liste der Typen vertraulicher Informationen angezeigt, und Sie können es direkt in Ihrer Richtlinie verwenden und festlegen, bei wie vielen Schlüsselwörtern eine Übereinstimmung festgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="4c067-p117">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
