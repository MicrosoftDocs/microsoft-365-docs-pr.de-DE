---
title: Verwenden der Inhaltssuche für gezielte Sammlungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Verwenden Sie die Inhaltssuche im Security & Compliance Center, um gezielte Sammlungen durchzuführen, die sicherstellen, dass sich die Elemente in einem bestimmten Postfach oder Standortordner befinden.
ms.openlocfilehash: 179d893c153af337cf6b8b9ed633172e22cf208a
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324581"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="96b4c-103">Verwenden der Inhaltssuche für gezielte Sammlungen</span><span class="sxs-lookup"><span data-stu-id="96b4c-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="96b4c-104">Das Feature "Inhaltssuche" im Security &amp; Compliance Center bietet keine direkte Möglichkeit in der Benutzeroberfläche, bestimmte Ordner in Exchange-Postfächern oder SharePoint-und OneDrive für Unternehmen-Websites zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="96b4c-105">Es ist jedoch möglich, bestimmte Ordner zu durchsuchen (als *gezielte Sammlung*bezeichnet), indem die Eigenschaft "Folder ID" für die Eigenschaft "Email" oder "Path" (DocumentLink) für Websites in der tatsächlichen Suchabfrage Syntax angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="96b4c-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="96b4c-106">Die Verwendung der Inhaltssuche zum Ausführen einer zielgerichteten Sammlung ist hilfreich, wenn Sie sicher sind, dass Elemente, die auf einen Fall reagieren, oder privilegierte Elemente sich in einem bestimmten Postfach oder Standortordner befinden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="96b4c-107">Sie können das Skript in diesem Artikel verwenden, um die Ordner-ID für Postfachordner oder den Pfad (DocumentLink) für Ordner auf einer SharePoint-und OneDrive für Unternehmen-Website zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="96b4c-108">Anschließend können Sie die Ordner-ID oder den Pfad in einer Suchabfrage verwenden, um Elemente zurückzugeben, die sich im Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="96b4c-109">Um Inhalte zurückzugeben, die sich in einem Ordner auf einer SharePoint-oder OneDrive für Unternehmen-Website befinden, verwendet das Skript in diesem Thema die verwaltete Eigenschaft DocumentLink anstelle der Path-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96b4c-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="96b4c-110">Die DocumentLink-Eigenschaft ist robuster als die Path-Eigenschaft, da Sie alle Inhalte in einem Ordner zurückgibt, während die Path-Eigenschaft einige Mediendateien zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="96b4c-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="96b4c-111">Vor dem Ausführen einer zielgerichteten Sammlung</span><span class="sxs-lookup"><span data-stu-id="96b4c-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="96b4c-112">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security &amp; Compliance Center sein, um das Skript in Schritt 1 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="96b4c-113">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="96b4c-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="96b4c-114">Darüber hinaus müssen Sie der Rolle "e-Mail-Empfänger" in Ihrer Exchange Online Organisation zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="96b4c-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="96b4c-115">Dies ist erforderlich, um das **Get-MailboxFolderStatistics-** Cmdlet auszuführen, das in dem Skript in Schritt 1 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="96b4c-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="96b4c-116">Standardmäßig ist die Rolle "e-Mail-Empfänger" der Rollengruppe "Organisationsverwaltung" und "Empfängerverwaltung" in Exchange Online zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="96b4c-117">Weitere Informationen zum Zuweisen von Berechtigungen in Exchange Online finden Sie unter [Verwalten von Rollengruppenmitgliedern](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="96b4c-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="96b4c-118">Sie können auch eine benutzerdefinierte Rollengruppe erstellen, ihr die Rolle "e-Mail-Empfänger" zuweisen und dann die Mitglieder hinzufügen, die das Skript in Schritt 1 ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="96b4c-119">Weitere Informationen finden Sie unter [Verwalten von Rollengruppen](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="96b4c-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="96b4c-120">Jedes Mal, wenn Sie das Skript in Schritt 1 ausführen, wird eine neue Remote-PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="96b4c-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="96b4c-121">Sie können also alle Remote-PowerShell-Sitzungen nutzen, die Ihnen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="96b4c-122">Um dies zu verhindern, können Sie den folgenden Befehl ausführen, um die Verbindung der aktiven Remote-PowerShell-Sitzungen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="96b4c-123">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="96b4c-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="96b4c-124">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="96b4c-124">The script includes minimal error handling.</span></span> <span data-ttu-id="96b4c-125">Der Hauptzweck des Skripts besteht darin, schnell eine Liste von Postfachordner-IDs oder Website Pfaden anzuzeigen, die in der Suchabfrage Syntax einer Inhaltssuche verwendet werden können, um eine gezielte Sammlung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="96b4c-126">Das in diesem Thema bereitgestellte Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96b4c-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="96b4c-127">Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="96b4c-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="96b4c-128">Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="96b4c-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="96b4c-129">Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="96b4c-130">In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="96b4c-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="96b4c-131">Schritt 1: Ausführen des Skripts zum Abrufen einer Liste von Ordnern für ein Postfach oder eine Website</span><span class="sxs-lookup"><span data-stu-id="96b4c-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="96b4c-132">Das Skript, das Sie in diesem ersten Schritt ausführen, gibt eine Liste der Postfachordner oder SharePoint-und OneDrive für Unternehmen-Ordner sowie die entsprechende Ordner-ID oder den entsprechenden Pfad für jeden Ordner zurück.</span><span class="sxs-lookup"><span data-stu-id="96b4c-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="96b4c-133">Wenn Sie dieses Skript ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="96b4c-134">**E-Mail-Adresse oder Website-URL**: Geben Sie eine e-Mail-Adresse der Depotbank ein, um eine Liste der Exchange-Postfachordner und Ordner-IDs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-134">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="96b4c-135">Oder geben Sie die URL für eine SharePoint-Website oder eine OneDrive für Unternehmen Website ein, um eine Liste der Pfade für die angegebene Website zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="96b4c-136">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="96b4c-136">Here are some examples:</span></span>

  - <span data-ttu-id="96b4c-137">**Exchange**: stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96b4c-137">**Exchange**: stacig@contoso.onmicrosoft.com</span></span> 

  - <span data-ttu-id="96b4c-138">**SharePoint**: https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="96b4c-138">**SharePoint**: https://contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="96b4c-139">**OneDrive für Unternehmen**: https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="96b4c-139">**OneDrive for Business**: https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="96b4c-140">**Ihre Benutzeranmeldeinformationen**: das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit Exchange Online und dem Security & Compliance Center mit Remote-PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-140">**Your user credentials**: The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="96b4c-141">Wie bereits erläutert, müssen Sie die entsprechenden Berechtigungen für die erfolgreiche Ausführung dieses Skripts zuweisen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-141">As previously explained, you have to assign the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="96b4c-142">So zeigen Sie eine Liste der Postfachordner oder Website documentlink (path) Namen an:</span><span class="sxs-lookup"><span data-stu-id="96b4c-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="96b4c-143">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="96b4c-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if (!$credentials)
   {
      $credentials = Get-Credential
   }
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="96b4c-144">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="96b4c-145">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96b4c-145">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="96b4c-146">Geben Sie die Informationen ein, die Sie vom Skript angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-146">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="96b4c-147">Das Skript zeigt eine Liste von Postfachordnern oder Websiteordnern für den angegebenen Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="96b4c-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="96b4c-148">Lassen Sie dieses Fenster geöffnet, damit Sie einen Ordner-ID-oder documentlink-Namen kopieren und in einer Suchabfrage in Schritt 2 einfügen können.</span><span class="sxs-lookup"><span data-stu-id="96b4c-148">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="96b4c-149">Anstatt eine Liste von Ordnern auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Skripts erneut an eine Textdatei weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="96b4c-150">Diese Datei wird in dem Ordner gespeichert, in dem sich das Skript befindet.</span><span class="sxs-lookup"><span data-stu-id="96b4c-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="96b4c-151">Um beispielsweise die Skriptausgabe in eine Textdatei umzuleiten, führen Sie den folgenden Befehl in Schritt 3  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` aus: dann können Sie eine Ordner-ID oder documentlink aus der Datei kopieren, die in einer Suchabfrage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="96b4c-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="96b4c-152">Skriptausgabe für Postfachordner</span><span class="sxs-lookup"><span data-stu-id="96b4c-152">Script output for mailbox folders</span></span>

<span data-ttu-id="96b4c-153">Wenn Sie Postfachordner-IDs abrufen, stellt das Skript eine Verbindung mit Exchange Online mithilfe von Remote-PowerShell her, führt das Cmdlet **Get-MailboxFolderStatisics** aus und zeigt dann die Liste der Ordner aus dem angegebenen Postfach an.</span><span class="sxs-lookup"><span data-stu-id="96b4c-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="96b4c-154">Für jeden Ordner im Postfach zeigt das Skript den Namen des Ordners in der Spalte **folderPath** und die Ordner-ID in der Spalte **FolderQuery** an.</span><span class="sxs-lookup"><span data-stu-id="96b4c-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="96b4c-155">Darüber hinaus fügt das Skript das Präfix von **Folder** ID (dem Namen der Postfacheigenschaft) zur Ordner-ID hinzu.</span><span class="sxs-lookup"><span data-stu-id="96b4c-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="96b4c-156">Da es sich bei der **Folder** -Eigenschaft um eine durchsuchbare Eigenschaft handelt, verwenden Sie in  `folderid:<folderid>` Schritt 2 eine Suchabfrage, um diesen Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="96b4c-157">Das Skript zeigt maximal 100 Postfachordner an.</span><span class="sxs-lookup"><span data-stu-id="96b4c-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96b4c-158">Das Skript in diesem Artikel enthält Codierungslogik, mit der die von **Get-MailboxFolderStatistics** zurückgegebenen 64-character-Ordner-ID-Werte in dasselbe 48-Zeichenformat konvertiert werden, das für die Suche indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="96b4c-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="96b4c-159">Wenn Sie einfach das Cmdlet **Get-MailboxFolderStatistics** in PowerShell ausführen, um eine Ordner-ID zu erhalten (anstatt das Skript in diesem Artikel auszuführen), schlägt eine Suchabfrage, die diesen Wert für die Ordner-ID verwendet, fehl.</span><span class="sxs-lookup"><span data-stu-id="96b4c-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="96b4c-160">Sie müssen das Skript ausführen, um die ordnungsgemäß formatierten Ordner-IDs abzurufen, die in einer Inhaltssuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="96b4c-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="96b4c-161">Im folgenden finden Sie ein Beispiel für die vom Skript für Postfachordner zurückgegebene Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="96b4c-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Beispiel für die Liste der Postfachordner und Ordner-IDs, die vom Skript zurückgegeben werden](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="96b4c-163">Das Beispiel in Schritt 2 zeigt die Abfrage, die zum Durchsuchen des Ordners "purges" im Ordner "Wiederherstellbare Elemente" des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96b4c-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="96b4c-164">Skriptausgabe für Websiteordner</span><span class="sxs-lookup"><span data-stu-id="96b4c-164">Script output for site folders</span></span>

<span data-ttu-id="96b4c-165">Wenn Sie den Pfad der **documentlink** -Eigenschaft von SharePoint oder OneDrive für Unternehmen-Websites erhalten, stellt das Skript eine Verbindung mit dem Security & Compliance Center mithilfe von Remote-PowerShell her, erstellt eine neue Inhaltssuche, die die Website nach Ordnern durchsucht, und zeigt dann eine Liste der Ordner an, die sich in der angegebenen Website befinden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="96b4c-166">Das Skript zeigt den Namen jedes Ordners an und fügt das Präfix **documentlink** der Ordner-URL hinzu.</span><span class="sxs-lookup"><span data-stu-id="96b4c-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="96b4c-167">Da es sich bei der **documentlink** -Eigenschaft um eine durchsuchbare Eigenschaft handelt, verwenden Sie in `documentlink:<path>` einer Suchabfrage in Schritt 2 die Eigenschaft: Wert-Paar, um diesen Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="96b4c-168">Das Skript zeigt maximal 200 Websiteordner an.</span><span class="sxs-lookup"><span data-stu-id="96b4c-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="96b4c-169">Wenn mehr als 200 Websiteordner vorhanden sind, werden die neuesten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96b4c-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="96b4c-170">Im folgenden finden Sie ein Beispiel für die vom Skript für Websiteordner zurückgegebene Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="96b4c-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![Beispiel für die Liste der documentlink Namen für Websiteordner, die vom Skript zurückgegeben werden](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="96b4c-172">Schritt 2: Verwenden einer Ordner-ID oder documentlink zum Durchführen einer zielgerichteten Sammlung</span><span class="sxs-lookup"><span data-stu-id="96b4c-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="96b4c-173">Nachdem Sie das Skript ausgeführt haben, um eine Liste der Ordner-IDs oder Dokumentverknüpfungen für einen bestimmten Benutzer zu sammeln, gehen Sie im nächsten Schritt zum Security & Compliance Center, und erstellen Sie eine neue Inhaltssuche, um einen bestimmten Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-173">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="96b4c-174">Sie verwenden das-  `folderid:<folderid>` oder  `documentlink:<path>` -Eigenschaft: Value-Paar in der Suchabfrage, die Sie im Feld Schlüsselwort für die Inhaltssuche konfigurieren (oder als Wert für den Parameter  *ContentMatchQuery*  , wenn Sie das Cmdlet **New-ComplianceSearch** verwenden).</span><span class="sxs-lookup"><span data-stu-id="96b4c-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="96b4c-175">Sie können die  `folderid` Eigenschaft oder  `documentlink` mit anderen Suchparametern oder Suchbedingungen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="96b4c-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="96b4c-176">Wenn Sie nur die  `folderid` oder  `documentlink` -Eigenschaft in die Abfrage einbeziehen, gibt die Suche alle Elemente zurück, die sich im angegebenen Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="96b4c-177">Wechseln Sie zu [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="96b4c-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="96b4c-178">Melden Sie sich mit dem Konto und den Anmeldeinformationen an, die Sie zum Ausführen des Skripts in Schritt 1 verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>

3. <span data-ttu-id="96b4c-179">Klicken Sie im linken Bereich des Security & Compliance Centers auf **Such** \> **Inhaltssuche**, und klicken Sie dann auf **Neues** ![ Symbol hinzufügen ](../media/O365-MDM-CreatePolicy-AddIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="96b4c-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>

4. <span data-ttu-id="96b4c-180">Geben Sie auf der Seite **Neue Suche** einen Namen für die Inhaltssuche ein.</span><span class="sxs-lookup"><span data-stu-id="96b4c-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="96b4c-181">Dieser Name muss in der Organisation eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="96b4c-181">This name has to be unique in your organization.</span></span> 

5. <span data-ttu-id="96b4c-182">Führen Sie einen der folgenden Schritte aus, je nachdem, ob Sie einen Postfachordner oder einen Websiteordner **durch**suchen:</span><span class="sxs-lookup"><span data-stu-id="96b4c-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="96b4c-183">Klicken Sie auf **bestimmte Postfächer für die Suche auswählen** , und fügen Sie dann das gleiche Postfach hinzu, das Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="96b4c-184">Oder:</span><span class="sxs-lookup"><span data-stu-id="96b4c-184">Or</span></span>

    - <span data-ttu-id="96b4c-185">Klicken Sie auf **bestimmte Websites zum Durchsuchen auswählen** , und fügen Sie dann die gleiche Website-URL hinzu, die Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-185">Click **Choose specific sites to search** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="96b4c-186">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-186">Click **Next**.</span></span>

7. <span data-ttu-id="96b4c-187">Fügen Sie in das Feld Stichwort auf der Seite **Was möchten Sie** , dass wir nach Seiten suchen die oder-Werte ein, die  `folderid:<folderid>`  `documentlink:<path>` von dem Skript in Schritt 1 zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 

    <span data-ttu-id="96b4c-188">Die Abfrage im folgenden Screenshot sucht beispielsweise im Ordner "Wiederherstellbare Elemente" des Benutzers nach einem beliebigen Element im Ordner "purges" (der Wert der `folderid` Eigenschaft für den Ordner "purges" ist im Screenshot in Schritt 1 dargestellt):</span><span class="sxs-lookup"><span data-stu-id="96b4c-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Fügen Sie die Ordner-oder documentlink in das Feld Stichwort der Suchabfrage ein.](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="96b4c-190">Klicken Sie auf **Suchen** , um die gezielte Sammlungs Suche zu starten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="96b4c-191">Beispiele für Suchabfragen für gezielte Auflistungen</span><span class="sxs-lookup"><span data-stu-id="96b4c-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="96b4c-192">Im folgenden finden Sie einige Beispiele für die Verwendung der  `folderid` and-  `documentlink` Eigenschaften in einer Suchabfrage, um eine gezielte Sammlung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="96b4c-193">Platzhalter werden für  `folderid:<folderid>` und  `documentlink:<path>` zum Speichern von Speicherplatz verwendet.</span><span class="sxs-lookup"><span data-stu-id="96b4c-193">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="96b4c-194">In diesem Beispiel werden drei verschiedene Postfachordner durchsucht.</span><span class="sxs-lookup"><span data-stu-id="96b4c-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="96b4c-195">Sie können ähnliche Abfragesyntax verwenden, um die ausgeblendeten Ordner im Ordner "refundable Items" eines Benutzers zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="96b4c-196">In diesem Beispiel wird ein Postfachordner nach Elementen durchsucht, die einen genauen Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="96b4c-197">In diesem Beispiel wird ein Websiteordner (und alle Unterordner) nach Dokumenten durchsucht, die die Buchstaben "NDA" im Titel enthalten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="96b4c-198">In diesem Beispiel wird ein Websiteordner (und ein beliebiger Unterordner) nach Dokumenten durchsucht, die innerhalb eines Datumsbereichs geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="96b4c-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96b4c-199">More information</span></span>

<span data-ttu-id="96b4c-200">Beachten Sie Folgendes, wenn Sie das Skript in diesem Artikel verwenden, um gezielte Sammlungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="96b4c-201">Das Skript entfernt keine Ordner aus den Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="96b4c-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="96b4c-202">Einige in den Ergebnissen aufgeführte Ordner sind möglicherweise nicht durchsuchbar (oder geben keine Elemente zurück), da Sie vom System generierte Inhalte enthalten oder nur Unterordner und keine Postfachelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="96b4c-203">Dieses Skript gibt nur Ordnerinformationen für das primäre Postfach des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="96b4c-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="96b4c-204">Es werden keine Informationen zu Ordnern im Archivpostfach des Benutzers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-204">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="96b4c-205">Wenn Sie Informationen zu Ordnern im Archivpostfach des Benutzers zurückgeben möchten, können Sie das Skript bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-205">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="96b4c-206">Ändern Sie dazu die Leitung in, `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` und speichern und führen Sie dann das bearbeitete Skript aus.</span><span class="sxs-lookup"><span data-stu-id="96b4c-206">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="96b4c-207">Durch diese Änderung werden die Ordner-IDs für Ordner und Unterordner im Archivpostfach des Benutzers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96b4c-207">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="96b4c-208">Zum Durchsuchen des gesamten Archivpostfachs können Sie alle Ordner-ID-Eigenschaft: Wert-Paare mit einem `OR` Operator in einer Suchabfrage verbinden.</span><span class="sxs-lookup"><span data-stu-id="96b4c-208">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="96b4c-209">Beim Durchsuchen von Postfachordnern wird nur der angegebene Ordner durchsucht, der durch seine `folderid` Eigenschaft identifiziert wird; Unterordner werden nicht durchsucht.</span><span class="sxs-lookup"><span data-stu-id="96b4c-209">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="96b4c-210">Zum Durchsuchen von Unterordnern müssen Sie die Ordner-ID für den Unterordner verwenden, den Sie durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="96b4c-210">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="96b4c-211">Beim Durchsuchen von Websiteordnern wird der Ordner (identifiziert durch seine `documentlink` Eigenschaft) und alle Unterordner durchsucht.</span><span class="sxs-lookup"><span data-stu-id="96b4c-211">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="96b4c-212">Wenn Sie die Ergebnisse einer Suche exportieren, in der Sie die `folderid` Eigenschaft nur in der Suchabfrage angegeben haben, können Sie die erste Exportoption auswählen: "alle Elemente, ausgenommen diejenigen, die ein nicht erkanntes Format haben, werden verschlüsselt oder aus anderen Gründen nicht indiziert."</span><span class="sxs-lookup"><span data-stu-id="96b4c-212">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="96b4c-213">Alle Elemente im Ordner werden unabhängig von Ihrem Indizierungsstatus immer exportiert, da die Ordner-ID immer indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="96b4c-213">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
