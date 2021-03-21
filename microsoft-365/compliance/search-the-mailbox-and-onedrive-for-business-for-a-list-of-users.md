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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Verwenden Sie die Inhaltssuche, um das Postfach und die OneDrive for Business-Website nach einer Liste mit Benutzern zu durchsuchen.

Das Security & Compliance Center bietet eine Reihe Windows PowerShell Cmdlets, mit deren Unterstützung Sie zeitaufwändige eDiscovery-bezogene Aufgaben automatisieren können. Derzeit dauert das Erstellen einer Inhaltssuche im Security & Compliance Center zum Durchsuchen einer großen Anzahl von Speicherorten von Custodian-Inhalten Zeit und Vorbereitung. Bevor Sie eine Suche erstellen, müssen Sie die URL für jede OneDrive for #A0 sammeln und dann jedes Postfach und die OneDrive for #A1 der Suche hinzufügen. In zukünftigen Versionen ist dies im Security & Compliance Center einfacher. Bis dahin können Sie das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren. Dieses Skript fordert Sie auf, den Namen der MySite-Domäne Ihrer Organisation (z. B. **contoso** in der URL), eine Liste der E-Mail-Adressen des Benutzers, den Namen der neuen Inhaltssuche und die zu verwendende Suchabfrage ein. `https://contoso-my.sharepoint.com` Das Skript ruft die OneDrive for #A0 für jeden Benutzer in der Liste ab, und dann erstellt und startet es eine Inhaltssuche, die das Postfach und die OneDrive for #A1 für jeden Benutzer in der Liste mithilfe der von Ihnen angegebenen Suchabfrage durchsucht.
  
## <a name="permissions-and-script-information"></a>Berechtigungen und Skriptinformationen

- Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center und ein globaler SharePoint Online-Administrator sein, um das Skript in Schritt 3 auszuführen.

- Achten Sie darauf, die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, im gleichen Ordner zu speichern. Dies erleichtert das Ausführen des Skripts.

- Das Skript enthält eine minimale Fehlerbehandlung. Der Hauptzweck besteht im schnellen und einfachen Durchsuchen des Postfachs und der OneDrive for #A0 jedes Benutzers.

- Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Schritt 1: Installieren der SharePoint Online-Verwaltungsshell

Der erste Schritt besteht in der Installation der SharePoint Online-Verwaltungsshell. Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen sie installieren, da sie die erforderlichen Voraussetzungen für das Skript enthält, das Sie in Schritt 3 ausführen. Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive for #A0 zu erhalten.
  
Wechseln Sie [zu Einrichten der SharePoint Online-Verwaltungsshell Windows PowerShell,](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell zu installieren.
  
## <a name="step-2-generate-a-list-of-users"></a>Schritt 2: Generieren einer Liste von Benutzern

Das Skript in Schritt 3 erstellt eine Inhaltssuche, um die Postfächer und #A0 nach einer Liste von Benutzern zu durchsuchen. Sie können einfach die E-Mail-Adressen in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste der E-Mail-Adressen zu erhalten und sie in einer Datei zu speichern (in dem Ordner, in dem Sie das Skript in Schritt 3 speichern).
  
Hier ist ein [Exchange Online PowerShell-Befehl,](/powershell/exchange/connect-to-exchange-online-powershell) den Sie ausführen können, um eine Liste der E-Mail-Adressen für alle Benutzer in Ihrer Organisation zu erhalten und in einer Textdatei namens zu `Users.txt` speichern. 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Nachdem Sie diesen Befehl ausgeführt haben, müssen Sie die Datei öffnen und den Header entfernen, der den Eigenschaftennamen enthält,  `PrimarySmtpAddress` . Die Textdatei sollte nur eine Liste von E-Mail-Adressen und nichts anderes enthalten. Stellen Sie sicher, dass vor oder nach der Liste der E-Mail-Adressen keine leeren Zeilen vorhanden sind.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Schritt 3: Ausführen des Skripts zum Erstellen und Starten der Suche

Wenn Sie das Skript in diesem Schritt ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert. Stellen Sie sicher, dass diese Informationen bereit sind, bevor Sie das Skript ausführen.
  
- **Ihre** Benutzeranmeldeinformationen – Das Skript verwendet Ihre Anmeldeinformationen, um auf SharePoint Online zu zugreifen, um die OneDrive for Business-URLs zu erhalten und eine Verbindung mit dem Security & Compliance Center mit Der Remote-PowerShell herzustellen. 
    
- **Name Ihrer MySite-Domäne** – Die MySite-Domäne ist die Domäne, die alle OneDrive for #A0 in Ihrer Organisation enthält. Wenn beispielsweise die URL für Ihre MySite-Domäne ist, geben Sie ein, wenn das Skript Sie zum Namen Ihrer **https://contoso-my.sharepoint.com**  `contoso` MySite-Domäne anfordert. 
    
- **Pfadname der Textdatei aus Schritt 2** : Der Pfadname der Textdatei, die Sie in Schritt 2 erstellt haben. Wenn sich die Textdatei und das Skript im gleichen Ordner befinden, geben Sie den Namen der Textdatei ein. Geben Sie andernfalls den vollständigen Pfadnamen für die Textdatei ein. 
    
- **Name der Inhaltssuche** – Der Name der Inhaltssuche, die vom Skript erstellt wird. 
    
- **Suchabfrage** – Die Suchabfrage, die mit der Inhaltssuche verwendet wird, wird erstellt und ausgeführt. Weitere Informationen zu Suchabfragen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).


**So führen Sie das Skript aus:**
    
1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: `SearchEXOOD4B.ps1` . Speichern Sie die Datei in dem Ordner, in dem Sie die Liste der Benutzer in Schritt 2 gespeichert haben.
    
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

2. Öffnen Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript und die Liste der Benutzer aus Schritt 2 gespeichert haben.
    
3. Starten Sie das Skript. Zum Beispiel:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre E-Mail-Adresse und Ihr Kennwort ein, und klicken Sie dann auf **OK**. 
    
5. Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden. Geben Sie alle Informationen ein, und drücken Sie dann die **EINGABETASTE.**
    
    - Der Name Ihrer MySite-Domäne. 
    
    - Der Pfadname der Textdatei, die die Liste der Benutzer enthält.
    
    - Ein Name für die Inhaltssuche.
    
    - Die Suchabfrage (lassen Sie diese leer, um alle Elemente an den Inhaltsstandorten zurückzukehren).
    
    Das Skript ruft die URLs für jede OneDrive for #A0 ab und erstellt dann die Suche und startet sie. Sie können entweder das **Cmdlet Get-ComplianceSearch** in Security & Compliance Center PowerShell ausführen, um die  Suchstatistiken und -ergebnisse anzuzeigen, oder Sie können zur Seite Inhaltssuche im Security & Compliance Center wechseln, um Informationen zur Suche anzuzeigen.