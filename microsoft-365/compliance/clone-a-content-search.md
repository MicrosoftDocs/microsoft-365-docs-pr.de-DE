---
title: Klonen einer Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie das Windows PowerShell-Skript in diesem Artikel, um schnell eine vorhandene Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365 zu klonen.
ms.openlocfilehash: 28f1264736f158fd686174813b9cefdd087c274c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818084"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="db1a4-103">Klonen einer Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="db1a4-103">Clone a Content Search</span></span>

<span data-ttu-id="db1a4-104">Das Erstellen einer Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365, die viele Postfächer oder SharePoint-und OneDrive für Unternehmen-Websites durchsucht, kann eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="db1a4-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="db1a4-105">Das Angeben der zu suchenden Websites kann auch fehleranfällig sein, wenn Sie eine URL vertippen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="db1a4-106">Um diese Probleme zu vermeiden, können Sie das Windows PowerShell-Skript in diesem Artikel verwenden, um eine vorhandene Inhaltssuche schnell zu klonen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="db1a4-107">Wenn Sie eine Suche Klonen, wird eine neue Suche (mit einem anderen Namen) erstellt, die dieselben Eigenschaften (wie die inhaltsspeicherorte und die Suchabfrage) als ursprüngliche Suche enthält.</span><span class="sxs-lookup"><span data-stu-id="db1a4-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="db1a4-108">Anschließend können Sie die neue Suche bearbeiten, indem Sie die Stichwortabfrage oder den Datumsbereich ändern und ausführen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="db1a4-109">Gründe für das Klonen von Inhalts suchen</span><span class="sxs-lookup"><span data-stu-id="db1a4-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="db1a4-110">Vergleichen Sie die Ergebnisse verschiedener Stichwort Suchabfragen, die an denselben Inhaltsspeicherorten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db1a4-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="db1a4-111">Sie müssen eine große Anzahl von Inhaltsspeicherorten erneut eingeben, wenn Sie eine neue Suche erstellen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="db1a4-112">, Um die Größe der Suchergebnisse zu verringern.</span><span class="sxs-lookup"><span data-stu-id="db1a4-112">To decrease the size of the search results.</span></span> <span data-ttu-id="db1a4-113">Wenn Sie beispielsweise eine Suche haben, die zu viele zu exportierende Ergebnisse zurückgibt, können Sie die Suche Klonen und dann eine Suchbedingung basierend auf einem Datumsbereich hinzufügen, um die Anzahl der Suchergebnisse zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="db1a4-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="db1a4-114">Skript Informationen</span><span class="sxs-lookup"><span data-stu-id="db1a4-114">Script information</span></span>

- <span data-ttu-id="db1a4-115">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein, um das in diesem Thema beschriebene Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="db1a4-116">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="db1a4-116">The script includes minimal error handling.</span></span> <span data-ttu-id="db1a4-117">Der Hauptzweck des Skripts besteht darin, eine Inhaltssuche schnell zu klonen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="db1a4-118">Das Skript erstellt eine neue Inhaltssuche, startet jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="db1a4-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="db1a4-119">Dieses Skript berücksichtigt, ob die Inhaltssuche, die Sie Klonen, einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="db1a4-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="db1a4-120">Wenn die Suche einem Fall zugeordnet ist, wird die neue Suche auch dem gleichen Fall zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="db1a4-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="db1a4-121">Wenn die vorhandene Suche keinem Fall zugeordnet ist, wird die neue Suche auf der Seite **Inhaltssuche** im Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="db1a4-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="db1a4-122">Das in diesem Thema bereitgestellte Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db1a4-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="db1a4-123">Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="db1a4-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="db1a4-124">Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="db1a4-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="db1a4-125">Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="db1a4-126">Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="db1a4-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="db1a4-127">Schritt 1: Ausführen des Skripts zum Klonen einer Suche</span><span class="sxs-lookup"><span data-stu-id="db1a4-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="db1a4-128">Mit dem Skript in diesem Schritt wird eine neue Inhaltssuche erstellt, indem ein vorhandenes klont wird.</span><span class="sxs-lookup"><span data-stu-id="db1a4-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="db1a4-129">Wenn Sie dieses Skript ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben:</span><span class="sxs-lookup"><span data-stu-id="db1a4-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="db1a4-130">**Ihre Benutzeranmeldeinformationen** – das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit dem Sicherheits & Compliance Center für Ihre Organisation mit Windows PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="db1a4-131">Wie bereits erwähnt, müssen Sie ein Mitglied der Rollengruppe "eDiscovery-Manager" im Sicherheits & compCompliance Center sein, um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="db1a4-132">**Der Name der vorhandenen Suche** -Dies ist die Inhaltssuche, die Sie klonen möchten.</span><span class="sxs-lookup"><span data-stu-id="db1a4-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="db1a4-133">**Der Name der neuen Suche, die erstellt wird** – Wenn Sie diesen Wert leer lassen, erstellt das Skript einen Namen für die neue Suche, der auf dem Namen der zu klonenden Suche basiert.</span><span class="sxs-lookup"><span data-stu-id="db1a4-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="db1a4-134">So Klonen Sie eine Suche:</span><span class="sxs-lookup"><span data-stu-id="db1a4-134">To clone a search:</span></span>
  
1. <span data-ttu-id="db1a4-135">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="db1a4-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="db1a4-136">Öffnen Sie Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="db1a4-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="db1a4-137">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db1a4-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="db1a4-138">Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre e-Mail-Adresse und Ihr Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db1a4-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="db1a4-139">Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="db1a4-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="db1a4-140">Geben Sie jede Information ein, und drücken **Sie**dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="db1a4-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="db1a4-141">Der Name der vorhandenen Suche.</span><span class="sxs-lookup"><span data-stu-id="db1a4-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="db1a4-142">Der Name der neuen Suche.</span><span class="sxs-lookup"><span data-stu-id="db1a4-142">The name of the new search.</span></span>
    
    <span data-ttu-id="db1a4-143">Das Skript erstellt die neue Inhaltssuche, startet es jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="db1a4-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="db1a4-144">Dadurch haben Sie die Möglichkeit, die Suche im nächsten Schritt zu bearbeiten und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="db1a4-145">Sie können die Eigenschaften der neuen Suche anzeigen, indem Sie das Cmdlet **Get-ComplianceSearch** ausführen oder im Compliance Center zur Seite **Inhaltssuche** oder **eDiscovery** wechseln, je nachdem, ob die neue Suche einer Anfrage zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="db1a4-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="db1a4-146">Schritt 2: Bearbeiten und Ausführen der geklonten Suche im Compliance Center</span><span class="sxs-lookup"><span data-stu-id="db1a4-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="db1a4-147">Nachdem Sie das Skript zum Klonen einer vorhandenen Inhaltssuche ausgeführt haben, müssen Sie im nächsten Schritt zum Compliance Center wechseln, um die neue Suche zu bearbeiten und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="db1a4-148">Wie bereits erwähnt, können Sie eine Suche bearbeiten, indem Sie die Stichwort Suchabfrage ändern und Suchbedingungen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="db1a4-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="db1a4-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="db1a4-149">For more information, see:</span></span>
  
- [<span data-ttu-id="db1a4-150">Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="db1a4-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="db1a4-151">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="db1a4-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="db1a4-152">eDiscovery-Fälle</span><span class="sxs-lookup"><span data-stu-id="db1a4-152">eDiscovery cases</span></span>](ediscovery-cases.md)
