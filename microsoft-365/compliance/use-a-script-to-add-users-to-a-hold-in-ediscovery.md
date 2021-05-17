---
title: Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltebereich in einem Core eDiscovery-Fall
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
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Sie ein Skript ausführen, um Postfächer & OneDrive for Business Websites einem neuen Archiv hinzuzufügen, das einem eDiscovery-Fall im Microsoft 365 zugeordnet ist.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909915"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltebereich in einem Core eDiscovery-Fall

Security & Compliance Center PowerShell bietet Cmdlets, mit denen Sie zeitaufwändige Aufgaben im Zusammenhang mit dem Erstellen und Verwalten von eDiscovery-Fällen automatisieren können. Derzeit dauert die Verwendung des Core eDiscovery-Falls im Security & Compliance Center zum Platzieren einer großen Anzahl von Speicherorten für Custodian-Inhalte Zeit und Vorbereitung. Bevor Sie beispielsweise einen Halteraum erstellen, müssen Sie die URL für jede OneDrive for Business Website sammeln, die Sie in der Warteschleife platzieren möchten. Anschließend müssen Sie für jeden Benutzer, den Sie in der Warteschleife platzieren möchten, ihr Postfach und OneDrive for Business dem Halteraum hinzufügen. Sie können das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.
  
Das Skript fordert Sie auf, den Namen der Domäne "Meine Website" Ihrer Organisation (z. B. in der URL , den Namen eines vorhandenen `contoso` eDiscovery-Falls, den Namen des neuen Haltebereichs, der dem Fall zugeordnet ist, eine Liste der E-Mail-Adressen der Benutzer, die Sie in den Haltebereich setzen möchten, und eine Suchabfrage, die verwendet werden soll, wenn Sie einen abfragebasierten Haltebereich erstellen https://contoso-my.sharepoint.com) möchten. Das Skript ruft dann die URL für die OneDrive for Business-Website für jeden Benutzer in der Liste ab, erstellt den neuen Halteraum und fügt dann das Postfach und die OneDrive for Business-Website für jeden Benutzer in der Liste zum Archiv hinzu. Das Skript generiert auch Protokolldateien, die Informationen zum neuen Halteraum enthalten.
  
Hier sind die Schritte, um dies zu geschehen:
  
[Schritt 1: Installieren der SharePoint Online-Verwaltungsshell](#step-1-install-the-sharepoint-online-management-shell)
  
[Schritt 2: Generieren einer Liste von Benutzern](#step-2-generate-a-list-of-users)
  
[Schritt 3: Ausführen des Skripts zum Erstellen eines Halte- und Hinzufügens von Benutzern](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Vor dem Hinzufügen von Benutzern zu einem Halteraum

- Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center und ein SharePoint Online-Administrator sein, um das Skript in Schritt 3 auszuführen. Weitere Informationen finden Sie unter [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).

- Einem Archiv, das einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, können maximal 1.000 Postfächer und 100 Websites hinzugefügt werden. Unter der Annahme, dass jeder Benutzer, den Sie in der Warteschleife platzieren möchten, über eine OneDrive for Business-Website verfügt, können Sie mithilfe des Skripts in diesem Artikel maximal 100 Benutzer zu einem Halteraum hinzufügen.

- Achten Sie darauf, die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, im gleichen Ordner zu speichern. Dies erleichtert das Ausführen des Skripts.

- Das Skript fügt die Liste der Benutzer zu einem neuen Halteraum hinzu, der einem vorhandenen Fall zugeordnet ist. Stellen Sie sicher, dass der Fall, dem Sie den Halteraum zuordnen möchten, erstellt wird, bevor Sie das Skript ausführen.

- Das Skript in diesem Artikel unterstützt die moderne Authentifizierung beim Herstellen einer Verbindung mit Security & Compliance Center PowerShell und SharePoint Online Management Shell. Sie können das Skript wie folgt verwenden, wenn Sie ein Microsoft 365 oder eine Microsoft 365 GCC sind. Wenn Sie eine Office 365, eine Microsoft 365 GCC High Organization oder eine Microsoft 365 DoD-Organisation sind, müssen Sie das Skript bearbeiten, um es erfolgreich ausführen zu können. Insbesondere müssen Sie die Zeile bearbeiten und die `Connect-IPPSSession` *Parameter ConnectionUri* und *AzureADAuthorizationEndpointUri* (und die entsprechenden Werte für Ihren Organisationstyp) verwenden, um eine Verbindung mit Security & Compliance Center PowerShell herzustellen. Weitere Informationen finden Sie in den Beispielen in [Verbinden to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).

- Das Skript trennt automatisch die Verbindung von Security & Compliance Center PowerShell und SharePoint Online Management Shell.

- Das Skript enthält eine minimale Fehlerbehandlung. Der Hauptzweck besteht im schnellen und einfachen Platzieren des Postfachs und OneDrive for Business website der einzelnen Benutzer.

- Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Schritt 1: Installieren der SharePoint Online-Verwaltungsshell

Der erste Schritt besteht im Installieren der SharePoint Online-Verwaltungsshell, wenn sie noch nicht auf Ihrem lokalen Computer installiert ist. Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen sie installieren, da sie die erforderlichen Voraussetzungen für das Skript enthält, das Sie in Schritt 3 ausführen. Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive for Business erhalten.
  
Wechseln Sie [zu Einrichten der SharePoint Onlineverwaltungsshell Windows PowerShell,](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell auf Ihrem lokalen Computer zu installieren.

## <a name="step-2-generate-a-list-of-users"></a>Schritt 2: Generieren einer Liste von Benutzern

Das Skript in Schritt 3 erstellt ein Archiv, das einem eDiscovery-Fall zugeordnet ist, und das Hinzufügen der Postfächer und OneDrive for Business Websites einer Liste von Benutzern zum Archiv. Sie können einfach die E-Mail-Adressen in eine Textdatei eingeben, oder Sie können einen Befehl in Windows PowerShell ausführen, um eine Liste der E-Mail-Adressen zu erhalten und sie in einer Datei zu speichern (in dem Ordner, in dem Sie das Skript in Schritt 3 speichern).
  
Im Folgenden finden Sie einen PowerShell-Befehl (der mithilfe von Remote PowerShell ausgeführt wird, die mit Ihrer Exchange Online-Organisation verbunden ist), um eine Liste der E-Mail-Adressen für alle Benutzer in Ihrer Organisation zu erhalten und in einer Textdatei namens HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Öffnen Sie nach dem Ausführen dieses Befehls die Textdatei, und entfernen Sie die Kopfzeile, die den Eigenschaftennamen enthält,  `PrimarySmtpAddress` . Entfernen Sie dann alle E-Mail-Adressen mit Ausnahme der Adressen für die Benutzer, die Sie dem in Schritt 3 erstellten Halteraum hinzufügen möchten. Stellen Sie sicher, dass vor oder nach der Liste der E-Mail-Adressen keine leeren Zeilen vorhanden sind.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Schritt 3: Ausführen des Skripts zum Erstellen eines Halte- und Hinzufügens von Benutzern

Wenn Sie das Skript in diesem Schritt ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert. Stellen Sie sicher, dass diese Informationen bereit sind, bevor Sie das Skript ausführen.
  
- **Ihre Benutzeranmeldeinformationen:** Das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit security & Compliance Center mit PowerShell herzustellen. Diese Anmeldeinformationen werden auch verwendet, um auf SharePoint Online zu zugreifen, um die OneDrive for Business urLs für die Liste der Benutzer zu erhalten.

- **Name Ihrer SharePoint Domäne:** Das Skript fordert Sie auf, diesen Namen ein eingeben, damit es eine Verbindung mit dem SharePoint herstellen kann. Außerdem wird der Domänenname für die OneDrive URLs in Ihrer Organisation verwendet. Wenn beispielsweise die URL für Ihr Admin Center und die URL für OneDrive ist, geben Sie ein, wenn das Skript Sie zur Eingabe Ihres `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` Domänennamens anfordert.

- **Name des Falls:** Der Name eines vorhandenen Falls. Das Skript erstellt einen neuen Halteraum, der diesem Fall zugeordnet ist.

- **Name des Halteraums:** Der Name des Halteraums, den das Skript erstellt und dem angegebenen Fall zuzuordnen ist.

- **Suchabfrage für einen abfragebasierten Halteraum:** Sie können einen abfragebasierten Halteraum erstellen, sodass nur der Inhalt, der die angegebenen Suchkriterien erfüllt, in der Warteschleife platziert wird. Drücken Sie einfach die EINGABETASTE, wenn Sie zur Eingabe einer Suchabfrage aufgefordert werden, um alle Inhalte in der Warteschleife zu platzieren. 

- **Aktivieren des Haltepunkts oder nicht:** Sie können das Skript nach der Erstellung aktivieren oder das Skript den Halteraum erstellen lassen, ohne es zu aktivieren. Wenn sie das Skript nicht aktivieren, können Sie es später im Security & Compliance Center oder durch Ausführen der folgenden PowerShell-Befehle aktivieren:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Name der Textdatei mit** der Liste der Benutzer – Der Name der Textdatei aus Schritt 2, die die Liste der Benutzer enthält, die dem Halteraum hinzugefügt werden. Wenn sich diese Datei im gleichen Ordner wie das Skript befindet, geben Sie einfach den Namen der Datei ein (z. B. HoldUsers.txt). Wenn sich die Textdatei in einem anderen Ordner befindet, geben Sie den vollständigen Pfadnamen der Datei ein.

Nachdem Sie die Vom Skript aufgeforderten Informationen gesammelt haben, besteht der letzte Schritt in der Ausführung des Skripts zum Erstellen des neuen Halteraums und hinzufügen von Benutzern.
  
1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix `.ps1` verwenden. Beispiel: `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.

3. Führen Sie das Skript aus. Zum Beispiel:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Geben Sie die Vom Skript aufgeforderten Informationen ein.

   Das Skript stellt eine Verbindung mit Security & Compliance Center PowerShell ein, erstellt dann den neuen Halteraum im eDiscovery-Fall und fügt die Postfächer und OneDrive for Business für die Benutzer in der Liste hinzu. Sie können zu dem Fall auf der **eDiscovery-Seite** im Security & Compliance Center wechseln, um das neue Haltefeld zu sehen.

Nachdem das Skript ausgeführt wurde, werden die folgenden Protokolldateien erstellt und in dem Ordner gespeichert, in dem sich das Skript befindet.
  
- **LocationsOnHold.txt:** Enthält eine Liste der Postfächer und OneDrive for Business Websites, die das Skript erfolgreich in der Warteschleife platziert hat.

- **LocationsNotOnHold.txt:** Enthält eine Liste der Postfächer und OneDrive for Business Websites, die das Skript nicht in der Warteschleife gespeichert hat. Wenn ein Benutzer über ein Postfach verfügt, aber nicht über eine OneDrive for Business, wird der Benutzer in die Liste der OneDrive for Business websites aufgenommen, die nicht in den Halteraum gesetzt wurden.

- **GetCaseHoldPolicy.txt:** Enthält die Ausgabe des **Cmdlets Get-CaseHoldPolicy** für den neuen Halteraum, den das Skript nach dem Erstellen des neuen Halteraums ausgeführt hat. Die von diesem Cmdlet zurückgegebenen Informationen enthalten eine Liste der Benutzer, deren Postfächer und OneDrive for Business-Websites gesperrt wurden und ob der Halteraum aktiviert oder deaktiviert ist. 

- **GetCaseHoldRule.txt:** Enthält die Ausgabe des **Cmdlets Get-CaseHoldRule** für den neuen Halteraum, den das Skript nach dem Erstellen des neuen Halteraums ausgeführt hat. Die von diesem Cmdlet zurückgegebenen Informationen enthalten die Suchabfrage, wenn Sie das Skript zum Erstellen eines abfragebasierten Haltefelds verwendet haben.