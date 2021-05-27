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
ms.openlocfilehash: 24f6bb636c702438be8ca9520c6523031f297410
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683763"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="df349-103">Schlüsselwörterbuch erstellen</span><span class="sxs-lookup"><span data-stu-id="df349-103">Create a keyword dictionary</span></span>

<span data-ttu-id="df349-104">Die Verhinderung von Datenverlust (DLP) kann Ihre vertraulichen Objekte identifizieren, überwachen und schützen.</span><span class="sxs-lookup"><span data-stu-id="df349-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="df349-105">Das Identifizieren vertraulicher Objekte erfordert manchmal die Suche nach Schlüsselwörtern, insbesondere beim Erkennen von allgemeinen Inhalten (etwa bei Kommunikation im Gesundheitswesen) oder unangemessener oder unflätiger Sprache.</span><span class="sxs-lookup"><span data-stu-id="df349-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="df349-106">Obwohl Sie Schlüsselwortlisten in vertraulichen Informationstypen erstellen können, sind Schlüsselwortlisten in ihrer Größe begrenzt und erfordern eine Änderung von XML, um sie zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="df349-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="df349-107">Schlüsselwörterbücher bieten eine einfachere Verwaltung von Stichwörtern und in einem viel größeren Umfang. Sie unterstützen bis zu 1 MB an Begriffen (Post-Kompression) im Wörterbuch und unterstützen alle Sprachen.</span><span class="sxs-lookup"><span data-stu-id="df349-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="df349-108">Das Mandantenlimit liegt nach der Komprimierung ebenfalls bei 1 MB.</span><span class="sxs-lookup"><span data-stu-id="df349-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="df349-109">Der 1 MB-Limit der Post-Kompression bedeutet, dass alle Wörterbücher zusammen über den gesamten Mandanten hinweg bis zu 1 Million Zeichen haben können.</span><span class="sxs-lookup"><span data-stu-id="df349-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="df349-110">Schlüsselwörterbücherlimits</span><span class="sxs-lookup"><span data-stu-id="df349-110">Keyword dictionary limits</span></span>

<span data-ttu-id="df349-111">Es gibt ein Limit von 50 Schlüsselwortwörterbuch-basierten vertraulichen Informationstypen, die pro Mandant erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="df349-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="df349-112">Um herauszufinden, wie viele Schlüsselwörterbücher Ihr Mandant enthält, stellen Sie mithilfe des in [Herstellen einer Verbindung zu Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) beschriebenen Verfahrens eine Verbindung zu Ihrem Mandanten her, und führen Sie dieses PowerShell-Skript aus.</span><span class="sxs-lookup"><span data-stu-id="df349-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="df349-113">Grundlegende Schritte zum Erstellen eines Schlüsselwörterbuchs</span><span class="sxs-lookup"><span data-stu-id="df349-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="df349-p103">Die Schlüsselwörter für Ihr Wörterbuch können aus verschiedenen Quellen stammen, meistens aber aus einer in den Dienst importierten Datei (etwa einer CSV- oder TXT-Liste), oder durch ein einem PowerShell-Cmdlet, aus einer Liste, die Sie direkt in das PowerShell-Cmdlet eingeben, oder aus einem vorhandenen Wörterbuch.Beim Erstellen eines Schlüsselwörterbuchs befolgen Sie die gleichen einfachen Schritte:</span><span class="sxs-lookup"><span data-stu-id="df349-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="df349-116">Verwenden Sie das **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) oder stellen Sie eine Verbindung zum **Security &amp; Compliance Center PowerShell** her.</span><span class="sxs-lookup"><span data-stu-id="df349-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="df349-117">**Definieren oder laden Sie Ihre Schlüsselwörter aus der vorgesehenen Quelle**.</span><span class="sxs-lookup"><span data-stu-id="df349-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="df349-118">Sowohl der Assistent als auch das Cmdlet akzeptieren eine durch Komma getrennte Liste von Schlüsselwörtern, um ein benutzerdefiniertes Schlüsselwörterbuch zu erstellen. Dieser Schritt variiert daher leicht, je nachdem, woher Ihre Schlüsselwörter stammen.</span><span class="sxs-lookup"><span data-stu-id="df349-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="df349-119">Sobald sie geladen sind, werden sie kodiert und in ein Byte-Array konvertiert, bevor sie importiert werden.</span><span class="sxs-lookup"><span data-stu-id="df349-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="df349-120">**Erstellen Sie Ihr Wörterbuch**.</span><span class="sxs-lookup"><span data-stu-id="df349-120">**Create your dictionary**.</span></span> <span data-ttu-id="df349-121">Wählen Sie einen Namen und eine Beschreibung und erstellen Sie Ihr Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="df349-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="df349-122">Schlüsselwörterbuch mit dem Security & Compliance Center erstellen</span><span class="sxs-lookup"><span data-stu-id="df349-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="df349-123">Verwenden Sie die folgenden Schritte zum Erstellen und Importieren von Schlüsselwörtern für ein Benutzerwörterbuch:</span><span class="sxs-lookup"><span data-stu-id="df349-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="df349-124">Stellen Sie die Verbindung zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) her.</span><span class="sxs-lookup"><span data-stu-id="df349-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="df349-125">Navigieren Sie zu **Klassifizierungen > Typen vertraulicher Informationen**.</span><span class="sxs-lookup"><span data-stu-id="df349-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="df349-126">Wählen Sie **Erstellen** aus, geben Sie einen **Namen** und eine **Beschreibung** für Ihren vertraulichen Infotyp ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="df349-127">Wählen Sie **Element hinzufügen** und dann **Wörterbuch (große Schlüsselwörter)** in der Dropdownliste **Inhalt erkennen, der Folgendes enthält** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="df349-128">Wählen Sie **Wörterbuch hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="df349-129">Wählen Sie unter dem Steuerelement "Suche" die Option **Hier können Sie neue Schlüsselwörterbücher erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="df349-130">Geben Sie einen **Namen** für Ihr Benutzerwörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="df349-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="df349-131">Klicken Sie auf **Importieren**, und wählen Sie dann entweder **Aus Text** oder **Aus CSV** aus, je nach Typ der Schlüsselwortdatei.</span><span class="sxs-lookup"><span data-stu-id="df349-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="df349-132">Wählen Sie im Dialogfeld "Datei" die Schlüsselwortdatei auf Ihrem lokalen PC oder aus der Netzwerkfreigabe aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="df349-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="df349-133">Klicken Sie auf **Speichern**, und wählen Sie dann Ihr Benutzerwörterbuch aus der Liste **Schlüsselwörterbücher** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="df349-134">Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="df349-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="df349-135">Überprüfen und vervollständigen Sie den ausgewählten Typ vertraulicher Informationen, und wählen Sie dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="df349-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="df349-136">Erstellen eines Schlüsselwörterbuchs aus einer Datei mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="df349-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="df349-137">Wenn Sie ein großes Wörterbuch erstellen, müssen Sie möglicherweise Schlüsselwörter verwenden, die aus einer Datei oder einer exportierten Liste aus einer anderen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="df349-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="df349-138">In diesem Fall erstellen Sie ein Schlüsselwörterbuch, das eine Liste unangemessener Ausdrücke enthält, um von außen eingehende E-Mail-Nachrichten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="df349-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="df349-139">Zunächst müssen Sie [eine Verbindung zu Security &amp; Compliance Center PowerShell herstellen](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="df349-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="df349-140">Kopieren Sie die Schlüsselwörter in eine Textdatei, und stellen Sie sicher, dass sich jedes Schlüsselwort in einer separaten Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="df349-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="df349-p107">Speichern Sie die Textdatei in Unicode-Codierung: Im Editor \> **Speichern als** \> **Codierung** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="df349-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="df349-143">Lesen Sie die Datei in eine Variable, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="df349-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="df349-144">Erstellen Sie das Wörterbuch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="df349-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="df349-145">Verwenden von Schlüsselwörterbüchern in benutzerdefinierten vertraulichen Informationstypen und DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="df349-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="df349-146">Schlüsselwörterbücher können als Bestandteil der Übereinstimmungsanforderungen für einen benutzerdefinierten Typ vertraulicher Informationen oder selbst als Typ vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df349-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="df349-147">Für beide müssen Sie einen [benutzerdefinierten Typ vertraulicher Informationen](create-a-custom-sensitive-information-type-in-scc-powershell.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="df349-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="df349-148">Befolgen Sie die Anweisungen im verknüpften Artikel um einen Typ vertraulicher Informationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df349-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="df349-149">Sobald Sie über den XML-Code verfügen, benötigen Sie den GUID-Bezeichner für das Wörterbuch, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="df349-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="df349-150">Um die Identität des Wörterbuchs zu erhalten, führen Sie den folgenden Befehl aus, und kopieren Sie den **Identity**-Eigenschaftswert:</span><span class="sxs-lookup"><span data-stu-id="df349-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="df349-151">Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="df349-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="df349-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="df349-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="df349-p109">Fügen Sie die Identität in den XML-Code Ihres benutzerdefinierten Typs vertraulicher Informationen ein, und laden Sie ihn hoch. Jetzt wird das Wörterbuch in Ihrer Liste der Typen vertraulicher Informationen angezeigt, und Sie können es direkt in Ihrer Richtlinie verwenden und festlegen, bei wie vielen Schlüsselwörtern eine Übereinstimmung festgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="df349-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="df349-155">Microsoft 365 Information Protection unterstützt in der Vorschauversion Sprachen mit Doppelbyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="df349-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="df349-156">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="df349-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="df349-157">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="df349-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="df349-158">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="df349-158">Korean</span></span>
> - <span data-ttu-id="df349-159">Japanisch</span><span class="sxs-lookup"><span data-stu-id="df349-159">Japanese</span></span>
>
><span data-ttu-id="df349-160">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df349-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="df349-161">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="df349-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
