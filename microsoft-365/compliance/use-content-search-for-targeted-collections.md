---
title: Verwenden der Inhaltssuche für gezielte Sammlungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Verwenden Sie die Inhaltssuche im Microsoft 365 Compliance Center, um eine gezielte Sammlung durchzuführen, die nach Elementen in einem bestimmten Postfach oder Websiteordner sucht.
ms.openlocfilehash: 925a6e5e0e56c63cde8bfa1b39cca6e64abcd016
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114752"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="6c8f9-103">Verwenden der Inhaltssuche für gezielte Sammlungen</span><span class="sxs-lookup"><span data-stu-id="6c8f9-103">Use Content search for targeted collections</span></span>

<span data-ttu-id="6c8f9-104">Das Tool für die Inhaltssuche im Microsoft 365 Compliance Center bietet keine direkte Möglichkeit in der Benutzeroberfläche, bestimmte Ordner in Exchange Postfächern oder SharePoint und OneDrive for Business Websites zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-104">The Content search tool in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="6c8f9-105">Es ist jedoch möglich, bestimmte Ordner (als *gezielte Sammlung* bezeichnet) zu durchsuchen, indem Sie die Ordner-ID-Eigenschaft für E-Mail- oder Pfadeigenschaft (DocumentLink) für Websites in der tatsächlichen Suchabfragesyntax angeben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="6c8f9-106">Die Verwendung der Inhaltssuche zum Ausführen einer gezielten Sammlung ist hilfreich, wenn Sie sicher sind, dass sich Elemente, die auf einen Fall reagieren, oder privilegierte Elemente in einem bestimmten Postfach oder Websiteordner befinden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="6c8f9-107">Sie können das Skript in diesem Artikel verwenden, um die Ordner-ID für Postfachordner oder den Pfad (DocumentLink) für Ordner auf einer SharePoint und OneDrive for Business Website abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="6c8f9-108">Anschließend können Sie die Ordner-ID oder den Pfad in einer Suchabfrage verwenden, um Elemente zurückzugeben, die sich im Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="6c8f9-109">Um Inhalte in einem Ordner in einer SharePoint oder OneDrive for Business Website zurückzugeben, verwendet das Skript in diesem Thema die verwaltete DocumentLink-Eigenschaft anstelle der Path-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="6c8f9-110">Die DocumentLink-Eigenschaft ist robuster als die Path-Eigenschaft, da sie alle Inhalte in einem Ordner zurückgibt, während die Path-Eigenschaft keine Mediendateien zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="6c8f9-111">Vor dem Ausführen einer zielgerichteten Sammlung</span><span class="sxs-lookup"><span data-stu-id="6c8f9-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="6c8f9-112">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein, um das Skript in Schritt 1 ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-112">You have to be a member of the eDiscovery Manager role group in Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="6c8f9-113">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6c8f9-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="6c8f9-114">Außerdem muss Ihnen die Rolle "E-Mail-Empfänger" in Ihrer Exchange Online Organisation zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-114">You also have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="6c8f9-115">Dies ist erforderlich, um das Cmdlet **"Get-MailboxFolderStatistics"** auszuführen, das im Skript enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="6c8f9-116">Standardmäßig wird die Rolle "E-Mail-Empfänger" den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" in Exchange Online zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="6c8f9-117">Weitere Informationen zum Zuweisen von Berechtigungen in Exchange Online finden Sie unter [Verwalten von Rollengruppenmitgliedern.](/exchange/manage-role-group-members-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="6c8f9-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span></span> <span data-ttu-id="6c8f9-118">Sie können auch eine benutzerdefinierte Rollengruppe erstellen, ihr die Rolle "E-Mail-Empfänger" zuweisen und dann die Mitglieder hinzufügen, die das Skript in Schritt 1 ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="6c8f9-119">Weitere Informationen finden Sie unter [Verwalten von Rollengruppen.](/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="6c8f9-119">For more information, see [Manage role groups](/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="6c8f9-120">Das Skript in diesem Artikel unterstützt die moderne Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="6c8f9-121">Sie können das Skript wie besehen verwenden, wenn Sie ein Microsoft 365 oder eine Microsoft 365 GCC Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="6c8f9-122">Wenn Sie eine Office 365 Deutschland-Organisation, eine Microsoft 365 GCC High-Organisation oder eine Microsoft 365 DoD-Organisation sind, müssen Sie das Skript bearbeiten, um es erfolgreich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="6c8f9-123">Insbesondere müssen Sie die Zeile bearbeiten `Connect-ExchangeOnline` und den *Parameter ExchangeEnvironmentName* (und den entsprechenden Wert für Ihren Organisationstyp) verwenden, um eine Verbindung mit Exchange Online PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="6c8f9-124">Außerdem müssen Sie die Zeile bearbeiten `Connect-IPPSSession` und die Parameter *ConnectionUri* und *AzureADAuthorizationEndpointUri* (und die entsprechenden Werte für Ihren Organisationstyp) verwenden, um eine Verbindung mit Security & Compliance Center PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="6c8f9-125">Weitere Informationen finden Sie in den Beispielen in [Verbinden zu Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) und [Verbinden zu Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="6c8f9-125">For more information, see the examples in [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="6c8f9-126">Jedes Mal, wenn Sie das Skript ausführen, wird eine neue PowerShell-Remotesitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="6c8f9-127">Das bedeutet, dass Sie alle verfügbaren Remote-PowerShell-Sitzungen nutzen können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="6c8f9-128">Um dies zu verhindern, führen Sie den folgenden Befehl aus, um ihre aktiven PowerShell-Remotesitzungen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="6c8f9-129">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6c8f9-129">For more information, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6c8f9-130">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-130">The script includes minimal error handling.</span></span> <span data-ttu-id="6c8f9-131">Der Hauptzweck des Skripts besteht darin, schnell eine Liste der Postfachordner-IDs oder Websitepfade anzuzeigen, die in der Suchabfragesyntax einer Inhaltssuche zum Ausführen einer Zielsammlung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="6c8f9-132">Das in diesem Thema bereitgestellte Beispielskript wird unter keinem Microsoft-Standardsupportprogramm oder -dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="6c8f9-133">Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="6c8f9-134">Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="6c8f9-135">Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="6c8f9-136">In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="6c8f9-137">Schritt 1: Ausführen des Skripts zum Abrufen einer Liste von Ordnern für ein Postfach oder eine Website</span><span class="sxs-lookup"><span data-stu-id="6c8f9-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="6c8f9-138">Das Skript, das Sie in diesem ersten Schritt ausführen, gibt eine Liste der Postfachordner oder SharePoint und OneDrive for Business Ordner sowie die entsprechende Ordner-ID oder den Pfad für jeden Ordner zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="6c8f9-139">Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-139">When you run this script, it will prompt you for the following information.</span></span>

- <span data-ttu-id="6c8f9-140">**E-Mail-Adresse oder Website-URL:** Geben Sie eine E-Mail-Adresse des Verwalters ein, um eine Liste Exchange Postfachordner und Ordner-IDs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="6c8f9-141">Oder geben Sie die URL für eine SharePoint-Website oder eine OneDrive for Business-Website ein, um eine Liste der Pfade für die angegebene Website zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="6c8f9-142">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-142">Here are some examples:</span></span>

  - <span data-ttu-id="6c8f9-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="6c8f9-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="6c8f9-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="6c8f9-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span>

  - <span data-ttu-id="6c8f9-145">**OneDrive for Business**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="6c8f9-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span>

- <span data-ttu-id="6c8f9-146">**Ihre Benutzeranmeldeinformationen:** Das Skript verwendet Ihre Anmeldeinformationen, um mithilfe der modernen Authentifizierung eine Verbindung mit Exchange Online PowerShell oder Security & Compliance Center PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="6c8f9-147">Wie zuvor erläutert, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden, um dieses Skript erfolgreich ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="6c8f9-148">So zeigen Sie eine Liste von Postfachordnern oder Websitedokumentlinknamen (Pfadnamen) an:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>

1. <span data-ttu-id="6c8f9-149">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="6c8f9-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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

2. <span data-ttu-id="6c8f9-150">Öffnen Sie auf Ihrem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="6c8f9-151">Führen Sie das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="6c8f9-152">Geben Sie die Informationen ein, nach denen Sie vom Skript aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="6c8f9-153">Das Skript zeigt eine Liste der Postfachordner oder Websiteordner für den angegebenen Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="6c8f9-154">Lassen Sie dieses Fenster geöffnet, damit Sie eine Ordner-ID oder einen Documentlink-Namen kopieren und in eine Suchabfrage in Schritt 2 einfügen können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="6c8f9-155">Anstatt eine Liste der Ordner auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Skripts erneut an eine Textdatei weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="6c8f9-156">Diese Datei wird in dem Ordner gespeichert, in dem sich das Skript befindet.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="6c8f9-157">Um die Skriptausgabe beispielsweise an eine Textdatei umzuleiten, führen Sie den folgenden Befehl in Schritt 3 aus:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Anschließend können Sie eine Ordner-ID oder einen Dokumentlink aus der Datei kopieren, um sie in einer Suchabfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>

### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="6c8f9-158">Skriptausgabe für Postfachordner</span><span class="sxs-lookup"><span data-stu-id="6c8f9-158">Script output for mailbox folders</span></span>

<span data-ttu-id="6c8f9-159">Wenn Sie Postfachordner-IDs abrufen, stellt das Skript eine Verbindung mit Exchange Online PowerShell her, führt das Cmdlet **"Get-MailboxFolderStatisics"** aus und zeigt dann die Liste der Ordner aus dem angegebenen Postfach an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="6c8f9-160">Für jeden Ordner im Postfach zeigt das Skript den Namen des Ordners in der **FolderPath-Spalte** und die Ordner-ID in der **FolderQuery-Spalte** an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="6c8f9-161">Darüber hinaus fügt das Skript der Ordner-ID das Präfix **folderId** (d. h. den Namen der Postfacheigenschaft) hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="6c8f9-162">Da es sich bei der **FolderID-Eigenschaft** um eine durchsuchbare Eigenschaft handelt, verwenden Sie  `folderid:<folderid>` in einer Suchabfrage in Schritt 2, um diesen Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="6c8f9-163">Das Skript zeigt maximal 100 Postfachordner an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c8f9-164">Das Skript in diesem Artikel enthält Codierungslogik, die die 64-Zeichen-Ordner-ID-Werte konvertiert, die von **Get-MailboxFolderStatistics** in dasselbe 48-Zeichen-Format zurückgegeben werden, das für die Suche indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="6c8f9-165">Wenn Sie einfach das Cmdlet **"Get-MailboxFolderStatistics"** in PowerShell ausführen, um eine Ordner-ID abzurufen (anstatt das Skript in diesem Artikel auszuführen), schlägt eine Suchabfrage fehl, die diesen Ordner-ID-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="6c8f9-166">Sie müssen das Skript ausführen, um die richtig formatierten Ordner-IDs abzurufen, die in einer Inhaltssuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>

<span data-ttu-id="6c8f9-167">Hier ist ein Beispiel für die Ausgabe, die vom Skript für Postfachordner zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-167">Here's an example of the output returned by the script for mailbox folders.</span></span>

![Beispiel für die Liste der Postfachordner und Ordner-IDs, die vom Skript zurückgegeben werden](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

<span data-ttu-id="6c8f9-169">Das Beispiel in Schritt 2 zeigt die Abfrage, die zum Durchsuchen des Unterordners "Löschelemente" im Ordner "Wiederherstellbare Elemente" des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>

### <a name="script-output-for-site-folders"></a><span data-ttu-id="6c8f9-170">Skriptausgabe für Websiteordner</span><span class="sxs-lookup"><span data-stu-id="6c8f9-170">Script output for site folders</span></span>

<span data-ttu-id="6c8f9-171">Wenn Sie den Pfad der **documentlink-Eigenschaft** von SharePoint oder OneDrive for Business Websites abrufen, stellt das Skript eine Verbindung mit Security & Compliance PowerShell her, erstellt eine neue Inhaltssuche, die die Website nach Ordnern durchsucht, und zeigt dann eine Liste der Ordner an, die sich auf der angegebenen Website befinden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="6c8f9-172">Das Skript zeigt den Namen der einzelnen Ordner an und fügt der Ordner-URL das Präfix **"documentlink"** hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="6c8f9-173">Da es sich bei der **documentlink-Eigenschaft** um eine durchsuchbare Eigenschaft handelt, verwenden Sie `documentlink:<path>` das Eigenschaften-Wert-Paar in einer Suchabfrage in Schritt 2, um diesen Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="6c8f9-174">Das Skript zeigt maximal 200 Websiteordner an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="6c8f9-175">Wenn mehr als 200 Websiteordner vorhanden sind, werden die neuesten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>

<span data-ttu-id="6c8f9-176">Hier ist ein Beispiel für die Ausgabe, die vom Skript für Websiteordner zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-176">Here's an example of the output returned by the script for site folders.</span></span>

![Beispiel für die Liste der documentlink-Namen für Websiteordner, die vom Skript zurückgegeben werden](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="6c8f9-178">Schritt 2: Verwenden einer Ordner-ID oder eines Dokumentlinks zum Ausführen einer zielgerichteten Sammlung</span><span class="sxs-lookup"><span data-stu-id="6c8f9-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="6c8f9-179">Nachdem Sie das Skript ausgeführt haben, um eine Liste der Ordner-IDs oder Dokumentlinks für einen bestimmten Benutzer zu sammeln, fahren Sie im nächsten Schritt mit dem Microsoft 365 Compliance Center fort und erstellen eine neue Inhaltssuche, um einen bestimmten Ordner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="6c8f9-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="6c8f9-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="6c8f9-181">Sie können die  `folderid`  `documentlink` Eigenschaft mit anderen Suchparametern oder Suchbedingungen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="6c8f9-182">Wenn Sie nur die  `folderid`  `documentlink` Oder-Eigenschaft in die Abfrage einschließen, gibt die Suche alle Elemente zurück, die sich im angegebenen Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>

1. <span data-ttu-id="6c8f9-183">Wechseln Sie zu <https://compliance.microsoft.com> und melden Sie sich mit dem Konto und den Anmeldeinformationen an, die Sie zum Ausführen des Skripts in Schritt 1 verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-183">Go to <https://compliance.microsoft.com> and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="6c8f9-184">Klicken Sie im linken Bereich des Compliance Centers auf **"Alle**  >  **Inhaltssuche** anzeigen", und klicken Sie dann auf **"Neue Suche".**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="6c8f9-185">Fügen Sie in das Feld **Schlüsselwörter** den `folderid:<folderid>` wert ein, der vom Skript in Schritt  `documentlink:<path>/*` 1 zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>/*` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="6c8f9-186">Die Abfrage im folgenden Screenshot sucht beispielsweise nach einem beliebigen Element im Unterordner "Löschungen" im Ordner "Wiederherstellbare Elemente" des Benutzers (der Wert der `folderid` Eigenschaft für den Unterordner "Löschungen" wird im Screenshot in Schritt 1 angezeigt):</span><span class="sxs-lookup"><span data-stu-id="6c8f9-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Einfügen der Ordner-ID oder des Documentlinks in das Schlüsselwortfeld der Suchabfrage](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > <span data-ttu-id="6c8f9-188">Für dokumentlinksuchvorgänge ist die Verwendung einer nachgestellten  `asterisk '/*'` .</span><span class="sxs-lookup"><span data-stu-id="6c8f9-188">documentlink searches require the use of a trailing  `asterisk '/*'`.</span></span>  

4. <span data-ttu-id="6c8f9-189">Wählen Sie unter **"Speicherorte"** **bestimmte Speicherorte aus,** und klicken Sie dann auf **"Ändern".**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-189">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="6c8f9-190">Führen Sie eine der folgenden Aktionen aus, je nachdem, ob Sie einen Postfachordner oder einen Websiteordner durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-190">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="6c8f9-191">Klicken Sie neben **Exchange E-Mail** auf **Benutzer, Gruppen oder Teams auswählen,** und fügen Sie dann dasselbe Postfach hinzu, das Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-191">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="6c8f9-192">Oder</span><span class="sxs-lookup"><span data-stu-id="6c8f9-192">Or</span></span>

    - <span data-ttu-id="6c8f9-193">Klicken Sie neben **SharePoint Websites** auf **"Websites auswählen",** und fügen Sie dann dieselbe Website-URL hinzu, die Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-193">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="6c8f9-194">Klicken Sie nach dem Speichern des zu durchsuchenden Inhaltsspeicherorts auf **"Speichern & ausführen",** geben Sie einen Namen für die Inhaltssuche ein, und klicken Sie dann auf **"Speichern",** um die Zielsammlungssuche zu starten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-194">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span>

### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="6c8f9-195">Beispiele für Suchabfragen für gezielte Sammlungen</span><span class="sxs-lookup"><span data-stu-id="6c8f9-195">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="6c8f9-196">Hier sind einige Beispiele für die Verwendung der Eigenschaften und der  `folderid`  `documentlink` Eigenschaften in einer Suchabfrage zum Ausführen einer Zielsammlung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-196">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="6c8f9-197">Platzhalter werden  `folderid:<folderid>`  `documentlink:<path>` verwendet, um Platz zu sparen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-197">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span>

- <span data-ttu-id="6c8f9-198">In diesem Beispiel werden drei verschiedene Postfachordner durchsucht.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-198">This example searches three different mailbox folders.</span></span> <span data-ttu-id="6c8f9-199">Sie können eine ähnliche Abfragesyntax verwenden, um die ausgeblendeten Ordner im Ordner "Wiederherstellbare Elemente" eines Benutzers zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-199">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="6c8f9-200">In diesem Beispiel wird ein Postfachordner nach Elementen durchsucht, die einen genauen Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-200">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="6c8f9-201">In diesem Beispiel wird ein Websiteordner (und alle Unterordner) nach Dokumenten durchsucht, die die Buchstaben "NDA" im Titel enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-201">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- <span data-ttu-id="6c8f9-202">In diesem Beispiel wird ein Websiteordner (und ein beliebiger Unterordner) nach Dokumenten durchsucht, die innerhalb eines Datumsbereichs geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-202">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="6c8f9-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c8f9-203">More information</span></span>

<span data-ttu-id="6c8f9-204">Beachten Sie bei der Verwendung des Skripts in diesem Artikel die folgenden Punkte, um gezielte Sammlungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-204">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>

- <span data-ttu-id="6c8f9-205">Das Skript entfernt keine Ordner aus den Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-205">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="6c8f9-206">Einige Ordner, die in den Ergebnissen aufgeführt sind, sind möglicherweise nicht durchsuchbar (oder geben Nullelemente zurück), da sie vom System generierte Inhalte enthalten oder weil sie nur Unterordner und keine Postfachelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-206">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="6c8f9-207">Dieses Skript gibt nur Ordnerinformationen für das primäre Postfach des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-207">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="6c8f9-208">Es werden keine Informationen zu Ordnern im Archivpostfach des Benutzers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-208">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="6c8f9-209">Um Informationen zu Ordnern im Archivpostfach des Benutzers zurückzugeben, können Sie das Skript bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-209">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="6c8f9-210">Ändern Sie dazu die Zeile in das `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` bearbeitete Skript, speichern und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-210">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="6c8f9-211">Diese Änderung gibt die Ordner-IDs für Ordner und Unterordner im Archivpostfach des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-211">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="6c8f9-212">Um das gesamte Archivpostfach zu durchsuchen, können Sie alle Ordner-ID-Eigenschaft:Wert-Paare mit einem `OR` Operator in einer Suchabfrage verbinden.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-212">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="6c8f9-213">Beim Durchsuchen von Postfachordnern wird nur der angegebene Ordner (durch seine `folderid` Eigenschaft identifiziert) durchsucht. Unterordner werden nicht durchsucht.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-213">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="6c8f9-214">Um Unterordner zu durchsuchen, müssen Sie die Ordner-ID für den Unterordner verwenden, den Sie durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-214">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="6c8f9-215">Beim Durchsuchen von Websiteordnern werden der Ordner (durch seine `documentlink` Eigenschaft identifiziert) und alle Unterordner durchsucht.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-215">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span>

- <span data-ttu-id="6c8f9-216">Beim Exportieren der Ergebnisse einer Suche, in der Sie nur die Eigenschaft in der Suchabfrage angegeben `folderid` haben, können Sie die erste Exportoption auswählen: "Alle Elemente, mit Ausnahme von Elementen mit einem nicht erkannten Format, werden verschlüsselt oder wurden aus anderen Gründen nicht indiziert."</span><span class="sxs-lookup"><span data-stu-id="6c8f9-216">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="6c8f9-217">Alle Elemente im Ordner werden unabhängig von ihrem Indizierungsstatus immer exportiert, da die Ordner-ID immer indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-217">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
