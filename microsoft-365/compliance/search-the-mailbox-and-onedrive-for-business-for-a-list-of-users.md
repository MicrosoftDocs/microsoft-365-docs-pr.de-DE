---
title: Durchsuchen des Postfachs & OneDrive für Unternehmen Website nach einer Liste von Benutzern mit Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Verwenden Sie die Inhaltssuche und das Skript in diesem Artikel, um die Postfächer und OneDrive für Unternehmen Websites für eine Gruppe von Benutzern zu durchsuchen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 714574739256f98353f01478fb9216432f3dcb47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818975"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="17efa-103">Verwenden Sie die Inhaltssuche, um das Postfach und die OneDrive for Business-Website nach einer Liste mit Benutzern zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="17efa-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="17efa-104">Das Security & Compliance Center bietet eine Reihe von Windows PowerShell-Cmdlets, mit denen Sie zeitaufwändige eDiscovery-bezogene Aufgaben automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="17efa-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="17efa-105">Das Erstellen einer Inhaltssuche im Security & Compliance Center zum Durchsuchen einer großen Anzahl von Speicherorten für Depot Inhalte erfordert Zeit und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="17efa-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="17efa-106">Bevor Sie eine Suche erstellen, müssen Sie die URL für jede OneDrive für Unternehmen Website erfassen und dann jedes Postfach und OneDrive für Unternehmen Website der Suche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="17efa-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="17efa-107">In zukünftigen Versionen ist dies im Security & Compliance Center einfacher.</span><span class="sxs-lookup"><span data-stu-id="17efa-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="17efa-108">Bis dahin können Sie das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="17efa-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="17efa-109">In diesem Skript werden Sie zur Angabe des Namens der mysite-Domäne Ihrer Organisation aufgefordert (beispielsweise " **contoso** " in der URL https://contoso-my.sharepoint.com) , eine Liste der e-Mail-Adressen der Benutzer, der Name der neuen Inhaltssuche und die zu verwendende Suchabfrage.</span><span class="sxs-lookup"><span data-stu-id="17efa-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="17efa-110">Das Skript ruft die OneDrive für Unternehmen-URL für jeden Benutzer in der Liste ab und erstellt und startet dann eine Inhaltssuche, die das Postfach und die OneDrive für Unternehmen Website für jeden Benutzer in der Liste durchsucht, wobei die von Ihnen bereitgestellte Suchabfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17efa-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="17efa-111">Berechtigungen und Skript Informationen</span><span class="sxs-lookup"><span data-stu-id="17efa-111">Permissions and script information</span></span>

- <span data-ttu-id="17efa-112">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center und SharePoint Online globaler Administrator sein, um das Skript in Schritt 3 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="17efa-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="17efa-113">Achten Sie darauf, dass Sie die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, in demselben Ordner speichern.</span><span class="sxs-lookup"><span data-stu-id="17efa-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="17efa-114">Dadurch wird das Ausführen des Skripts vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="17efa-114">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="17efa-115">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="17efa-115">The script includes minimal error handling.</span></span> <span data-ttu-id="17efa-116">Der primäre Zweck besteht darin, das Postfach und die OneDrive für Unternehmen Website jedes Benutzers schnell und einfach zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="17efa-116">It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="17efa-117">Die in diesem Thema bereitgestellten Beispielskripts werden unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17efa-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="17efa-118">Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="17efa-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="17efa-119">Microsoft lehnt weiter alle i [https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283) mplied Garantien, einschließlich, ohne Einschränkung, alle implizierten Garantien für die Marktgängigkeit oder Eignung für einen bestimmten Zweck.</span><span class="sxs-lookup"><span data-stu-id="17efa-119">Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="17efa-120">Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="17efa-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="17efa-121">Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="17efa-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="17efa-122">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="17efa-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="17efa-123">Der erste Schritt besteht darin, die SharePoint Online Management-Shell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="17efa-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="17efa-124">Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen Sie installieren, da Sie Voraussetzungen enthält, die für das in Schritt 3 ausgeführte Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="17efa-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="17efa-125">Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive für Unternehmen Websites abzurufen.</span><span class="sxs-lookup"><span data-stu-id="17efa-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="17efa-126">Wechseln Sie zum [Einrichten der SharePoint Online Verwaltungsshell Windows PowerShell Umgebung](https://go.microsoft.com/fwlink/p/?LinkID=286318) , und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online Verwaltungsshell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="17efa-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="17efa-127">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="17efa-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="17efa-128">Mit dem Skript in Schritt 3 wird eine Inhaltssuche erstellt, um die Postfächer und OneDrive-Konten nach einer Liste von Benutzern zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="17efa-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="17efa-129">Sie können die e-Mail-Adressen einfach in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste mit e-Mail-Adressen zu erhalten und diese in einer Datei zu speichern (in demselben Ordner, in dem Sie das Skript in Schritt 3 speichern werden).</span><span class="sxs-lookup"><span data-stu-id="17efa-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="17efa-130">Hier ist ein [Exchange Onlineer PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) -Befehl, mit dem Sie eine Liste von e-Mail-Adressen für alle Benutzer in Ihrer Organisation erhalten und in einer Textdatei namens speichern können `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="17efa-130">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="17efa-131">Nachdem Sie diesen Befehl ausgeführt haben, müssen Sie die Datei öffnen und die Kopfzeile mit dem Eigenschaftennamen entfernen `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="17efa-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="17efa-132">Die Textdatei sollte nur eine Liste von e-Mail-Adressen enthalten, und nichts anderes.</span><span class="sxs-lookup"><span data-stu-id="17efa-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="17efa-133">Stellen Sie sicher, dass keine leeren Zeilen vor oder nach der Liste der e-Mail-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="17efa-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="17efa-134">Schritt 3: Ausführen des Skripts zum Erstellen und Starten der Suche</span><span class="sxs-lookup"><span data-stu-id="17efa-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="17efa-135">Wenn Sie das Skript in diesem Schritt ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="17efa-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="17efa-136">Stellen Sie sicher, dass diese Informationen vor dem Ausführen des Skripts verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="17efa-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="17efa-137">**Ihre Benutzeranmeldeinformationen** – das Skript verwendet Ihre Anmeldeinformationen, um auf SharePoint Online zuzugreifen, um die OneDrive für Unternehmen-URLs abzurufen und eine Verbindung mit dem Security & Compliance Center mit Remote-PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="17efa-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="17efa-138">**Name Ihrer mysite-Domäne** : die mysite-Domäne ist die Domäne, die alle OneDrive für Unternehmen Websites in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="17efa-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="17efa-139">Wenn beispielsweise die URL für Ihre mysite-Domäne lautet **https://contoso-my.sharepoint.com** , geben Sie ein, `contoso` Wenn Sie vom Skript nach dem Namen Ihrer mysite-Domäne gefragt werden.</span><span class="sxs-lookup"><span data-stu-id="17efa-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="17efa-140">**Pfadname der Textdatei aus Schritt 2** -der Pfadname der Textdatei, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="17efa-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="17efa-141">Wenn sich die Textdatei und das Skript im gleichen Ordner befinden, geben Sie den Namen der Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="17efa-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="17efa-142">Geben Sie andernfalls den vollständigen Pfadnamen für die Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="17efa-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="17efa-143">**Name der Inhaltssuche** -der Name der Inhaltssuche, die vom Skript erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="17efa-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="17efa-144">**Suchabfrage** – die Suchabfrage, die bei der Inhaltssuche verwendet wird, wird erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="17efa-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="17efa-145">Weitere Informationen zu Suchabfragen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="17efa-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="17efa-146">**So führen Sie das Skript aus:**</span><span class="sxs-lookup"><span data-stu-id="17efa-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="17efa-147">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="17efa-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="17efa-148">Speichern Sie die Datei im gleichen Ordner, in dem Sie die Liste der Benutzer in Schritt 2 gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="17efa-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="17efa-149">Öffnen Sie Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben, und der Liste der Benutzer aus Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="17efa-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="17efa-150">Starten des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17efa-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="17efa-151">Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre e-Mail-Adresse und Ihr Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="17efa-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="17efa-152">Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="17efa-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="17efa-153">Geben Sie jede Information ein, und drücken **Sie**dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="17efa-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="17efa-154">Der Name Ihrer mysite-Domäne.</span><span class="sxs-lookup"><span data-stu-id="17efa-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="17efa-155">Der Pfadname der Textdatei, die die Liste der Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="17efa-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="17efa-156">Ein Name für die Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="17efa-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="17efa-157">Die Suchabfrage (lassen Sie das Feld leer, um alle Elemente an den Inhaltsspeicherorten zurückzugeben).</span><span class="sxs-lookup"><span data-stu-id="17efa-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="17efa-158">Das Skript ruft die URLs für jede OneDrive für Unternehmen Website ab und erstellt dann die Suche und startet diese.</span><span class="sxs-lookup"><span data-stu-id="17efa-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="17efa-159">Sie können entweder das Cmdlet **Get-ComplianceSearch** in Security & Compliance Center PowerShell ausführen, um die Suchstatistiken und Ergebnisse anzuzeigen, oder Sie können zur Seite **Inhaltssuche** im Security & Compliance Center wechseln, um Informationen zur Suche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17efa-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
