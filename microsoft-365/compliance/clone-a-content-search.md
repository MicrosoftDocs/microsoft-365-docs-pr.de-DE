---
title: Klonen einer Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie das PowerShell-Skript in diesem Artikel, um eine vorhandene Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365 schnell zu klonen.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918061"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="86d51-103">Klonen einer Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="86d51-103">Clone a Content Search</span></span>

<span data-ttu-id="86d51-104">Das Erstellen einer Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365, die viele Postfächer durchsucht, oder SharePoint- und OneDrive for #A0 kann eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="86d51-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="86d51-105">Das Angeben der zu durchsuchenden Websites kann auch fehleranfällig sein, wenn Sie eine URL falsch eingeben.</span><span class="sxs-lookup"><span data-stu-id="86d51-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="86d51-106">Um diese Probleme zu vermeiden, können Sie das Windows PowerShell in diesem Artikel verwenden, um eine vorhandene Inhaltssuche schnell zu klonen.</span><span class="sxs-lookup"><span data-stu-id="86d51-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="86d51-107">Wenn Sie eine Suche klonen, wird eine neue Suche (mit einem anderen Namen) erstellt, die die gleichen Eigenschaften (z. B. die Inhaltsorte und die Suchabfrage) wie die ursprüngliche Suche enthält.</span><span class="sxs-lookup"><span data-stu-id="86d51-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="86d51-108">Anschließend können Sie die neue Suche bearbeiten, indem Sie die Stichwortabfrage oder den Datumsbereich ändern und ausführen.</span><span class="sxs-lookup"><span data-stu-id="86d51-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="86d51-109">Warum Inhaltssuchen klonen?</span><span class="sxs-lookup"><span data-stu-id="86d51-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="86d51-110">Zum Vergleichen der Ergebnisse verschiedener Schlüsselwortsuchabfragen werden an denselben Inhaltsstandorten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="86d51-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="86d51-111">Um zu sparen, dass Sie beim Erstellen einer neuen Suche eine große Anzahl von Inhaltsstandorten erneut einsenken müssen.</span><span class="sxs-lookup"><span data-stu-id="86d51-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="86d51-112">So verringern Sie die Größe der Suchergebnisse.</span><span class="sxs-lookup"><span data-stu-id="86d51-112">To decrease the size of the search results.</span></span> <span data-ttu-id="86d51-113">Wenn Sie beispielsweise über eine Suche verfügen, die zu viele Zu exportierende Ergebnisse zurückgibt, können Sie die Suche klonen und dann eine Suchbedingung basierend auf einem Datumsbereich hinzufügen, um die Anzahl der Suchergebnisse zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="86d51-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="86d51-114">Skriptinformationen</span><span class="sxs-lookup"><span data-stu-id="86d51-114">Script information</span></span>

- <span data-ttu-id="86d51-115">Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center sein, um das in diesem Thema beschriebene Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86d51-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="86d51-116">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="86d51-116">The script includes minimal error handling.</span></span> <span data-ttu-id="86d51-117">Der Hauptzweck des Skripts besteht im schnellen Klonen einer Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="86d51-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="86d51-118">Das Skript erstellt eine neue Inhaltssuche, startet sie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="86d51-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="86d51-119">Dieses Skript berücksichtigt, ob die Inhaltssuche, die Sie klonen, einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="86d51-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="86d51-120">Wenn die Suche einem Fall zugeordnet ist, wird die neue Suche auch demselben Fall zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="86d51-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="86d51-121">Wenn die vorhandene Suche keinem Fall zugeordnet ist, wird die  neue Suche auf der Seite Inhaltssuche im Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="86d51-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="86d51-122">Das in diesem Thema bereitgestellte Beispielskript wird in keinem Standardsupportprogramm oder -dienst von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="86d51-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="86d51-123">Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="86d51-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="86d51-124">Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="86d51-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="86d51-125">Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="86d51-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="86d51-126">In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="86d51-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="86d51-127">Schritt 1: Ausführen des Skripts zum Klonen einer Suche</span><span class="sxs-lookup"><span data-stu-id="86d51-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="86d51-128">Das Skript in diesem Schritt erstellt eine neue Inhaltssuche durch Klonen eines vorhandenen.</span><span class="sxs-lookup"><span data-stu-id="86d51-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="86d51-129">Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="86d51-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="86d51-130">**Ihre Benutzeranmeldeinformationen** – Das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit dem Security & Compliance Center für Ihre Organisation mit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86d51-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="86d51-131">Wie bereits erwähnt, müssen Sie Mitglied der Rollengruppe eDiscovery Manager im Security & compCompliance Center sein, um das Skript ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="86d51-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="86d51-132">**Der Name der vorhandenen Suche** – Dies ist die Inhaltssuche, die Sie klonen möchten.</span><span class="sxs-lookup"><span data-stu-id="86d51-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="86d51-133">**Der** Name der neuen Suche, die erstellt wird: Wenn Sie diesen Wert leer lassen, erstellt das Skript einen Namen für die neue Suche, der auf dem Namen der Suche basiert, die Sie klonen.</span><span class="sxs-lookup"><span data-stu-id="86d51-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="86d51-134">So klonen Sie eine Suche:</span><span class="sxs-lookup"><span data-stu-id="86d51-134">To clone a search:</span></span>
  
1. <span data-ttu-id="86d51-135">Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="86d51-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="86d51-136">Öffnen Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="86d51-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="86d51-137">Führen Sie das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86d51-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="86d51-138">Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre E-Mail-Adresse und Ihr Kennwort ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86d51-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="86d51-139">Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="86d51-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="86d51-140">Geben Sie alle Informationen ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="86d51-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="86d51-141">Der Name der vorhandenen Suche.</span><span class="sxs-lookup"><span data-stu-id="86d51-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="86d51-142">Der Name der neuen Suche.</span><span class="sxs-lookup"><span data-stu-id="86d51-142">The name of the new search.</span></span>
    
    <span data-ttu-id="86d51-143">Das Skript erstellt die neue Inhaltssuche, startet sie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="86d51-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="86d51-144">Dadurch haben Sie die Möglichkeit, die Suche im nächsten Schritt zu bearbeiten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="86d51-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="86d51-145">Sie können die Eigenschaften der neuen Suche anzeigen, indem Sie das **Cmdlet Get-ComplianceSearch** ausführen oder zur Seite Inhaltssuche oder **eDiscovery** im Compliance Center gehen, je nachdem, ob die neue Suche einem Fall zugeordnet ist. </span><span class="sxs-lookup"><span data-stu-id="86d51-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="86d51-146">Schritt 2: Bearbeiten und Ausführen der geklonten Suche im Compliance Center</span><span class="sxs-lookup"><span data-stu-id="86d51-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="86d51-147">Nachdem Sie das Skript zum Klonen einer vorhandenen Inhaltssuche ausgeführt haben, gehen Sie im nächsten Schritt zum Compliance Center, um die neue Suche zu bearbeiten und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86d51-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="86d51-148">Wie bereits erwähnt, können Sie eine Suche bearbeiten, indem Sie die Schlüsselwortsuchabfrage ändern und Suchbedingungen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="86d51-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="86d51-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="86d51-149">For more information, see:</span></span>
  
- [<span data-ttu-id="86d51-150">Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="86d51-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="86d51-151">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="86d51-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="86d51-152">eDiscovery-Fälle</span><span class="sxs-lookup"><span data-stu-id="86d51-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)