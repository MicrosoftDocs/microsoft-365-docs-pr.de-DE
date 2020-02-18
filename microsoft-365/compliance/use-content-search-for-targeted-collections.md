---
title: Verwenden der Inhaltssuche in Office 365 für gezielte Auflistungen
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
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Verwenden Sie die Inhaltssuche im Security & Compliance Center, um gezielte Sammlungen durchzuführen. Eine gezielte Sammlung bedeutet, dass Sie sicher sind, dass Elemente, die auf einen Fall reagieren, oder privilegierte Elemente sich in einem bestimmten Postfach oder Standortordner befinden. Verwenden Sie das Skript in diesem Artikel, um die Ordner-ID oder den Pfad für das jeweilige Postfach oder die Websiteordner zu erhalten, die Sie durchsuchen möchten.
ms.openlocfilehash: b8afe9e65aa65c697d9c5cefbeaf89638c1782d4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080805"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Verwenden der Inhaltssuche in Office 365 für gezielte Auflistungen

Das Feature "Inhaltssuche" im Office 365 &amp; Security Compliance Center bietet keine direkte Möglichkeit in der Benutzeroberfläche, bestimmte Ordner in Exchange-Postfächern oder SharePoint-und OneDrive für Unternehmen-Websites zu durchsuchen. Es ist jedoch möglich, bestimmte Ordner zu durchsuchen (als *gezielte Sammlung*bezeichnet), indem die Eigenschaft "Folder ID" für die Eigenschaft "Email" oder "Path" (DocumentLink) für Websites in der tatsächlichen Suchabfrage Syntax angegeben wird. Die Verwendung der Inhaltssuche zum Ausführen einer zielgerichteten Sammlung ist hilfreich, wenn Sie sicher sind, dass Elemente, die auf einen Fall reagieren, oder privilegierte Elemente sich in einem bestimmten Postfach oder Standortordner befinden. Sie können das Skript in diesem Artikel verwenden, um die Ordner-ID für Postfachordner oder den Pfad (DocumentLink) für Ordner auf einer SharePoint-und OneDrive für Unternehmen-Website zu erhalten. Anschließend können Sie die Ordner-ID oder den Pfad in einer Suchabfrage verwenden, um Elemente zurückzugeben, die sich im Ordner befinden.

> [!NOTE]
> Um Inhalte zurückzugeben, die sich in einem Ordner auf einer SharePoint-oder OneDrive für Unternehmen-Website befinden, verwendet das Skript in diesem Thema die verwaltete Eigenschaft DocumentLink anstelle der Path-Eigenschaft. Die DocumentLink-Eigenschaft ist robuster als die Path-Eigenschaft, da Sie alle Inhalte in einem Ordner zurückgibt, während die Path-Eigenschaft einige Mediendateien zurückgibt.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security &amp; Compliance Center sein, um das Skript in Schritt 1 auszuführen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
    
    Darüber hinaus müssen Sie der Rolle "e-Mail-Empfänger" in Ihrer Exchange Online Organisation zugewiesen sein. Dies ist erforderlich, um das **Get-MailboxFolderStatistics-** Cmdlet auszuführen, das in dem Skript in Schritt 1 enthalten ist. Standardmäßig ist die Rolle "e-Mail-Empfänger" der Rollengruppe "Organisationsverwaltung" und "Empfängerverwaltung" in Exchange Online zugewiesen. Weitere Informationen zum Zuweisen von Berechtigungen in Exchange Online finden Sie unter [Verwalten von Rollengruppenmitgliedern](https://go.microsoft.com/fwlink/p/?linkid=692102). Sie können auch eine benutzerdefinierte Rollengruppe erstellen, ihr die Rolle "e-Mail-Empfänger" zuweisen und dann die Mitglieder hinzufügen, die das Skript in Schritt 1 ausführen müssen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Jedes Mal, wenn Sie das Skript in Schritt 1 ausführen, wird eine neue Remote-PowerShell-Sitzung erstellt. Sie können also alle Remote-PowerShell-Sitzungen nutzen, die Ihnen zur Verfügung stehen. Um dies zu verhindern, können Sie den folgenden Befehl ausführen, um die Verbindung der aktiven Remote-PowerShell-Sitzungen zu trennen.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Das Skript enthält eine minimale Fehlerbehandlung. Der Hauptzweck des Skripts besteht darin, schnell eine Liste von Postfachordner-IDs oder Website Pfaden anzuzeigen, die in der Suchabfrage Syntax einer Inhaltssuche verwendet werden können, um eine gezielte Sammlung auszuführen.
    
- Das in diesem Thema bereitgestellte Beispielskript wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt. Das Beispielskript wird ohne jegliche Gewährleistung bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das aus der Verwendung oder der Leistung des Beispielskripts und der Dokumentation erwachsen, bleibt bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Schritt 1: Ausführen des Skripts zum Abrufen einer Liste von Ordnern für ein Postfach oder eine Website

Das Skript, das Sie in diesem ersten Schritt ausführen, gibt eine Liste der Postfachordner oder SharePoint-und OneDrive für Unternehmen-Ordner sowie die entsprechende Ordner-ID oder den entsprechenden Pfad für jeden Ordner zurück. Wenn Sie dieses Skript ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben.
  
- **E-Mail-Adresse oder Website-URL** Geben Sie eine e-Mail-Adresse der Depotbank ein, um eine Liste der Exchange-Postfachordner und Ordner-IDs zurückzugeben. Oder geben Sie die URL für eine SharePoint-Website oder eine OneDrive für Unternehmen Website ein, um eine Liste der Pfade für die angegebene Website zurückzugeben. Im Folgenden finden Sie einige Beispiele: 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **Share** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive für Unternehmen** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Ihre Benutzeranmeldeinformationen** – das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit Exchange Online und dem Security & Compliance Center mit Remote-PowerShell herzustellen. Wie bereits erläutert, müssen Sie die entsprechenden Berechtigungen für die erfolgreiche Ausführung dieses Skripts zugewiesen haben.
    
So zeigen Sie eine Liste der Postfachordner oder Website documentlink (path) Namen an:
  
1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `GetFolderSearchParameters.ps1`.
    
  ```powershell
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
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

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.
    
3. Ausführen des Skripts; Zum Beispiel:
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. Geben Sie die Informationen ein, die Sie vom Skript angefordert haben.
    
    Das Skript zeigt eine Liste von Postfachordnern oder Websiteordnern für den angegebenen Benutzer an. Lassen Sie dieses Fenster geöffnet, damit Sie einen Ordner-ID-oder documentlink-Namen kopieren und in einer Suchabfrage in Schritt 2 einfügen können.
    
    > [!TIP]
    > Anstatt eine Liste von Ordnern auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Skripts erneut an eine Textdatei weiterleiten. Diese Datei wird in dem Ordner gespeichert, in dem sich das Skript befindet. Um beispielsweise die Skriptausgabe in eine Textdatei umzuleiten, führen Sie den folgenden Befehl in Schritt 3 `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` aus: dann können Sie eine Ordner-ID oder documentlink aus der Datei kopieren, die in einer Suchabfrage verwendet werden soll.
  
### <a name="script-output-for-mailbox-folders"></a>Skriptausgabe für Postfachordner

Wenn Sie Postfachordner-IDs abrufen, stellt das Skript eine Verbindung mit Exchange Online mithilfe von Remote-PowerShell her, führt das Cmdlet **Get-MailboxFolderStatisics** aus und zeigt dann die Liste der Ordner aus dem angegebenen Postfach an. Für jeden Ordner im Postfach zeigt das Skript den Namen des Ordners in der Spalte **folderPath** und die Ordner-ID in der Spalte **FolderQuery** an. Darüber hinaus fügt das Skript das Präfix von **Folder** ID (dem Namen der Postfacheigenschaft) zur Ordner-ID hinzu. Da es sich bei der **Folder** -Eigenschaft um eine durchsuchbare Eigenschaft `folderid:<folderid>` handelt, verwenden Sie in Schritt 2 eine Suchabfrage, um diesen Ordner zu durchsuchen. Das Skript zeigt maximal 100 Postfachordner an.

> [!IMPORTANT]
> Das Skript in diesem Artikel enthält Codierungslogik, mit der die von **Get-MailboxFolderStatistics** zurückgegebenen 64-character-Ordner-ID-Werte in dasselbe 48-Zeichenformat konvertiert werden, das für die Suche indiziert ist. Wenn Sie einfach das Cmdlet **Get-MailboxFolderStatistics** in PowerShell ausführen, um eine Ordner-ID zu erhalten (anstatt das Skript in diesem Artikel auszuführen), schlägt eine Suchabfrage, die diesen Wert für die Ordner-ID verwendet, fehl. Sie müssen das Skript ausführen, um die ordnungsgemäß formatierten Ordner-IDs abzurufen, die in einer Inhaltssuche verwendet werden können.
  
Im folgenden finden Sie ein Beispiel für die vom Skript für Postfachordner zurückgegebene Ausgabe.
  
![Beispiel für die Liste der Postfachordner und Ordner-IDs, die vom Skript zurückgegeben werden](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
Das Beispiel in Schritt 2 zeigt die Abfrage, die zum Durchsuchen des Ordners "purges" im Ordner "Wiederherstellbare Elemente" des Benutzers verwendet wird.
  
### <a name="script-output-for-site-folders"></a>Skriptausgabe für Websiteordner

Wenn Sie den Pfad der **documentlink** -Eigenschaft von SharePoint oder OneDrive für Unternehmen-Websites erhalten, stellt das Skript eine Verbindung mit dem Security & Compliance Center mithilfe von Remote-PowerShell her, erstellt eine neue Inhaltssuche, die die Website nach Ordnern durchsucht, und zeigt dann eine Liste der Ordner an, die sich in der angegebenen Website befinden. Das Skript zeigt den Namen jedes Ordners an und fügt das Präfix **documentlink** der Ordner-URL hinzu. Da es sich bei der **documentlink** -Eigenschaft um eine durchsuchbare `documentlink:<path>` Eigenschaft handelt, verwenden Sie in einer Suchabfrage in Schritt 2 die Eigenschaft: Wert-Paar, um diesen Ordner zu durchsuchen. Das Skript zeigt maximal 200 Websiteordner an. Wenn mehr als 200 Websiteordner vorhanden sind, werden die neuesten angezeigt.
  
Im folgenden finden Sie ein Beispiel für die vom Skript für Websiteordner zurückgegebene Ausgabe.
  
![Beispiel für die Liste der documentlink Namen für Websiteordner, die vom Skript zurückgegeben werden](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Schritt 2: Verwenden einer Ordner-ID oder documentlink zum Durchführen einer zielgerichteten Sammlung

Nachdem Sie das Skript ausgeführt haben, um eine Liste der Ordner-IDs oder documentlinks für einen bestimmten Benutzer zu sammeln, gehen Sie im nächsten Schritt zum Security & Compliance Center, und erstellen Sie eine neue Inhaltssuche, um einen bestimmten Ordner zu durchsuchen. Sie verwenden das `folderid:<folderid>` -oder `documentlink:<path>` -Eigenschaft: Value-Paar in der Suchabfrage, die Sie im Feld Schlüsselwort für die Inhaltssuche konfigurieren (oder als Wert für den Parameter *ContentMatchQuery* , wenn Sie das Cmdlet **New-ComplianceSearch** verwenden). Sie können die `folderid` Eigenschaft oder `documentlink` mit anderen Suchparametern oder Suchbedingungen kombinieren. Wenn Sie nur die `folderid` oder `documentlink` -Eigenschaft in die Abfrage einbeziehen, gibt die Suche alle Elemente zurück, die sich im angegebenen Ordner befinden. 
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit dem Konto und den Anmeldeinformationen an, die Sie zum Ausführen des Skripts in Schritt 1 verwendet haben.
    
3. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Such** \> **Inhaltssuche**, und klicken Sie **** ![dann auf neues](../media/O365-MDM-CreatePolicy-AddIcon.gif)Symbol hinzufügen.
    
4. Geben Sie auf der Seite **Neue Suche** einen Namen für die Inhaltssuche ein. Dieser Name muss in der Organisation eindeutig sein. 
    
5. Führen Sie einen der folgenden Schritte aus, je nachdem, ob Sie einen Postfachordner oder einen Websiteordner **durch**suchen:
    
    - Klicken Sie auf **bestimmte Postfächer für die Suche auswählen** , und fügen Sie dann das gleiche Postfach hinzu, das Sie beim Ausführen des Skripts in Schritt 1 angegeben haben. 
    
      Oder:
    
    - Klicken Sie auf **bestimmte Websites für** die Suche auswählen, und fügen Sie dann die gleiche Website-URL hinzu, die Sie beim Ausführen des Skripts in Schritt 1 angegeben haben. 
    
6. Klicken Sie auf **Weiter**.
    
7. Fügen Sie in das Feld Stichwort auf der Seite **Was möchten Sie** , dass wir nach Seiten suchen `folderid:<folderid>` die `documentlink:<path>` oder-Werte ein, die von dem Skript in Schritt 1 zurückgegeben wurden. 
    
    Die Abfrage im folgenden Screenshot sucht beispielsweise im Ordner "Wiederherstellbare Elemente" des Benutzers nach einem beliebigen Element im Ordner "purges" (der Wert der `folderid` Eigenschaft für den Ordner "purges" ist im Screenshot in Schritt 1 dargestellt):
    
    ![Fügen Sie die Ordner-oder documentlink in das Feld Stichwort der Suchabfrage ein.](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Klicken Sie auf **Suchen** , um die gezielte Sammlungs Suche zu starten. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Beispiele für Suchabfragen für gezielte Auflistungen

Im folgenden finden Sie einige Beispiele für `folderid` die `documentlink` Verwendung der and-Eigenschaften in einer Suchabfrage, um eine gezielte Sammlung auszuführen. Beachten Sie, dass Platzhalter verwendet `folderid:<folderid>` werden `documentlink:<path>` und um Platz zu sparen. 
  
- In diesem Beispiel werden drei verschiedene Postfachordner durchsucht. Sie können ähnliche Abfragesyntax verwenden, um die ausgeblendeten Ordner im Ordner "refundable Items" eines Benutzers zu durchsuchen.
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In diesem Beispiel wird ein Postfachordner nach Elementen durchsucht, die einen genauen Ausdruck enthalten.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- In diesem Beispiel wird ein Websiteordner (und alle Unterordner) nach Dokumenten durchsucht, die die Buchstaben "NDA" im Titel enthalten.
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- In diesem Beispiel wird ein Websiteordner (und ein beliebiger Unterordner) nach Dokumenten durchsucht, die innerhalb eines Datumsbereichs geändert wurden.
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Weitere Informationen

Beachten Sie Folgendes, wenn Sie das Skript in diesem Artikel verwenden, um gezielte Sammlungen durchzuführen.
  
- Das Skript entfernt keine Ordner aus den Ergebnissen. Einige in den Ergebnissen aufgeführte Ordner sind möglicherweise nicht durchsuchbar (oder geben keine Elemente zurück), da Sie vom System generierte Inhalte enthalten.
    
- Dieses Skript gibt nur Ordnerinformationen für das primäre Postfach des Benutzers zurück. Es werden keine Informationen zu Ordnern im Archivpostfach des Benutzers zurückgegeben.
    
- Beim Durchsuchen von Postfachordnern wird nur der angegebene Ordner durch `folderid` sucht, der durch seine Eigenschaft identifiziert wird. Unterordner werden nicht durchsucht. Zum Durchsuchen von Unterordnern müssen Sie die Ordner-ID für den Unterordner verwenden, den Sie durchsuchen möchten. 
    
- Beim Durchsuchen von Websiteordnern wird der Ordner (identifiziert `documentlink` durch seine Eigenschaft) und alle Unterordner durchsucht. 
    
- Wenn Sie die Ergebnisse einer Suche exportieren, in der Sie die `folderid` Eigenschaft nur in der Suchabfrage angegeben haben, können Sie die erste Exportoption auswählen: "alle Elemente, ausgenommen diejenigen, die ein nicht erkanntes Format haben, werden verschlüsselt oder aus anderen Gründen nicht indiziert." Alle Elemente im Ordner werden unabhängig von Ihrem Indizierungsstatus immer exportiert, da die Ordner-ID immer indiziert ist.
