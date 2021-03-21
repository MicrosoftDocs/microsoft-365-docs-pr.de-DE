---
title: Durchsuchen des Postfachs & OneDrive for & nach einer Liste von Benutzern mit Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 'Verwenden Sie die Inhaltssuche und das Skript in diesem Artikel, um die Postfächer und OneDrive for #A0 nach einer Gruppe von Benutzern zu durchsuchen.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922467"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="cd98b-103">Verwenden Sie die Inhaltssuche, um das Postfach und die OneDrive for Business-Website nach einer Liste mit Benutzern zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="cd98b-104">Das Security & Compliance Center bietet eine Reihe Windows PowerShell Cmdlets, mit deren Unterstützung Sie zeitaufwändige eDiscovery-bezogene Aufgaben automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="cd98b-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="cd98b-105">Derzeit dauert das Erstellen einer Inhaltssuche im Security & Compliance Center zum Durchsuchen einer großen Anzahl von Speicherorten von Custodian-Inhalten Zeit und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="cd98b-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="cd98b-106">Bevor Sie eine Suche erstellen, müssen Sie die URL für jede OneDrive for #A0 sammeln und dann jedes Postfach und die OneDrive for #A1 der Suche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="cd98b-107">In zukünftigen Versionen ist dies im Security & Compliance Center einfacher.</span><span class="sxs-lookup"><span data-stu-id="cd98b-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="cd98b-108">Bis dahin können Sie das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="cd98b-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="cd98b-109">Dieses Skript fordert Sie auf, den Namen der MySite-Domäne Ihrer Organisation (z. B. **contoso** in der URL), eine Liste der E-Mail-Adressen des Benutzers, den Namen der neuen Inhaltssuche und die zu verwendende Suchabfrage ein. `https://contoso-my.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="cd98b-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="cd98b-110">Das Skript ruft die OneDrive for #A0 für jeden Benutzer in der Liste ab, und dann erstellt und startet es eine Inhaltssuche, die das Postfach und die OneDrive for #A1 für jeden Benutzer in der Liste mithilfe der von Ihnen angegebenen Suchabfrage durchsucht.</span><span class="sxs-lookup"><span data-stu-id="cd98b-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="cd98b-111">Berechtigungen und Skriptinformationen</span><span class="sxs-lookup"><span data-stu-id="cd98b-111">Permissions and script information</span></span>

- <span data-ttu-id="cd98b-112">Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center und ein globaler SharePoint Online-Administrator sein, um das Skript in Schritt 3 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="cd98b-113">Achten Sie darauf, die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, im gleichen Ordner zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cd98b-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="cd98b-114">Dies erleichtert das Ausführen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="cd98b-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="cd98b-115">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="cd98b-115">The script includes minimal error handling.</span></span> <span data-ttu-id="cd98b-116">Der Hauptzweck besteht im schnellen und einfachen Durchsuchen des Postfachs und der OneDrive for #A0 jedes Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cd98b-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="cd98b-p104">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd98b-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="cd98b-122">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="cd98b-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="cd98b-123">Der erste Schritt besteht in der Installation der SharePoint Online-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="cd98b-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="cd98b-124">Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen sie installieren, da sie die erforderlichen Voraussetzungen für das Skript enthält, das Sie in Schritt 3 ausführen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="cd98b-125">Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive for #A0 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cd98b-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="cd98b-126">Wechseln Sie [zu Einrichten der SharePoint Online-Verwaltungsshell Windows PowerShell,](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cd98b-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="cd98b-127">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="cd98b-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="cd98b-128">Das Skript in Schritt 3 erstellt eine Inhaltssuche, um die Postfächer und #A0 nach einer Liste von Benutzern zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="cd98b-129">Sie können einfach die E-Mail-Adressen in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste der E-Mail-Adressen zu erhalten und sie in einer Datei zu speichern (in dem Ordner, in dem Sie das Skript in Schritt 3 speichern).</span><span class="sxs-lookup"><span data-stu-id="cd98b-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="cd98b-130">Hier ist ein [Exchange Online PowerShell-Befehl,](/powershell/exchange/connect-to-exchange-online-powershell) den Sie ausführen können, um eine Liste der E-Mail-Adressen für alle Benutzer in Ihrer Organisation zu erhalten und in einer Textdatei namens zu `Users.txt` speichern.</span><span class="sxs-lookup"><span data-stu-id="cd98b-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="cd98b-131">Nachdem Sie diesen Befehl ausgeführt haben, müssen Sie die Datei öffnen und den Header entfernen, der den Eigenschaftennamen enthält,  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="cd98b-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="cd98b-132">Die Textdatei sollte nur eine Liste von E-Mail-Adressen und nichts anderes enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd98b-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="cd98b-133">Stellen Sie sicher, dass vor oder nach der Liste der E-Mail-Adressen keine leeren Zeilen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cd98b-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="cd98b-134">Schritt 3: Ausführen des Skripts zum Erstellen und Starten der Suche</span><span class="sxs-lookup"><span data-stu-id="cd98b-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="cd98b-135">Wenn Sie das Skript in diesem Schritt ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cd98b-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="cd98b-136">Stellen Sie sicher, dass diese Informationen bereit sind, bevor Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="cd98b-137">**Ihre** Benutzeranmeldeinformationen – Das Skript verwendet Ihre Anmeldeinformationen, um auf SharePoint Online zu zugreifen, um die OneDrive for Business-URLs zu erhalten und eine Verbindung mit dem Security & Compliance Center mit Der Remote-PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="cd98b-138">**Name Ihrer MySite-Domäne** – Die MySite-Domäne ist die Domäne, die alle OneDrive for #A0 in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="cd98b-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="cd98b-139">Wenn beispielsweise die URL für Ihre MySite-Domäne ist, geben Sie ein, wenn das Skript Sie zum Namen Ihrer **https://contoso-my.sharepoint.com**  `contoso` MySite-Domäne anfordert.</span><span class="sxs-lookup"><span data-stu-id="cd98b-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="cd98b-140">**Pfadname der Textdatei aus Schritt 2** : Der Pfadname der Textdatei, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cd98b-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="cd98b-141">Wenn sich die Textdatei und das Skript im gleichen Ordner befinden, geben Sie den Namen der Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="cd98b-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="cd98b-142">Geben Sie andernfalls den vollständigen Pfadnamen für die Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="cd98b-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="cd98b-143">**Name der Inhaltssuche** – Der Name der Inhaltssuche, die vom Skript erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cd98b-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="cd98b-144">**Suchabfrage** – Die Suchabfrage, die mit der Inhaltssuche verwendet wird, wird erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd98b-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="cd98b-145">Weitere Informationen zu Suchabfragen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="cd98b-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="cd98b-146">**So führen Sie das Skript aus:**</span><span class="sxs-lookup"><span data-stu-id="cd98b-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="cd98b-147">Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="cd98b-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="cd98b-148">Speichern Sie die Datei in dem Ordner, in dem Sie die Liste der Benutzer in Schritt 2 gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="cd98b-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="cd98b-149">Öffnen Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript und die Liste der Benutzer aus Schritt 2 gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="cd98b-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="cd98b-150">Starten Sie das Skript. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cd98b-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="cd98b-151">Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre E-Mail-Adresse und Ihr Kennwort ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd98b-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="cd98b-152">Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="cd98b-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="cd98b-153">Geben Sie alle Informationen ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="cd98b-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="cd98b-154">Der Name Ihrer MySite-Domäne.</span><span class="sxs-lookup"><span data-stu-id="cd98b-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="cd98b-155">Der Pfadname der Textdatei, die die Liste der Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="cd98b-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="cd98b-156">Ein Name für die Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="cd98b-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="cd98b-157">Die Suchabfrage (lassen Sie diese leer, um alle Elemente an den Inhaltsstandorten zurückzukehren).</span><span class="sxs-lookup"><span data-stu-id="cd98b-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="cd98b-158">Das Skript ruft die URLs für jede OneDrive for #A0 ab und erstellt dann die Suche und startet sie.</span><span class="sxs-lookup"><span data-stu-id="cd98b-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="cd98b-159">Sie können entweder das **Cmdlet Get-ComplianceSearch** in Security & Compliance Center PowerShell ausführen, um die  Suchstatistiken und -ergebnisse anzuzeigen, oder Sie können zur Seite Inhaltssuche im Security & Compliance Center wechseln, um Informationen zur Suche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd98b-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>