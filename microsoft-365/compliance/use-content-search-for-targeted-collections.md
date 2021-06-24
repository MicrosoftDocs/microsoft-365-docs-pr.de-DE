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
# <a name="use-content-search-for-targeted-collections"></a>Verwenden der Inhaltssuche für gezielte Sammlungen

Das Tool für die Inhaltssuche im Microsoft 365 Compliance Center bietet keine direkte Möglichkeit in der Benutzeroberfläche, bestimmte Ordner in Exchange Postfächern oder SharePoint und OneDrive for Business Websites zu durchsuchen. Es ist jedoch möglich, bestimmte Ordner (als *gezielte Sammlung* bezeichnet) zu durchsuchen, indem Sie die Ordner-ID-Eigenschaft für E-Mail- oder Pfadeigenschaft (DocumentLink) für Websites in der tatsächlichen Suchabfragesyntax angeben. Die Verwendung der Inhaltssuche zum Ausführen einer gezielten Sammlung ist hilfreich, wenn Sie sicher sind, dass sich Elemente, die auf einen Fall reagieren, oder privilegierte Elemente in einem bestimmten Postfach oder Websiteordner befinden. Sie können das Skript in diesem Artikel verwenden, um die Ordner-ID für Postfachordner oder den Pfad (DocumentLink) für Ordner auf einer SharePoint und OneDrive for Business Website abzurufen. Anschließend können Sie die Ordner-ID oder den Pfad in einer Suchabfrage verwenden, um Elemente zurückzugeben, die sich im Ordner befinden.

> [!NOTE]
> Um Inhalte in einem Ordner in einer SharePoint oder OneDrive for Business Website zurückzugeben, verwendet das Skript in diesem Thema die verwaltete DocumentLink-Eigenschaft anstelle der Path-Eigenschaft. Die DocumentLink-Eigenschaft ist robuster als die Path-Eigenschaft, da sie alle Inhalte in einem Ordner zurückgibt, während die Path-Eigenschaft keine Mediendateien zurückgibt.

## <a name="before-you-run-a-targeted-collection"></a>Vor dem Ausführen einer zielgerichteten Sammlung

- Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein, um das Skript in Schritt 1 ausführen zu können. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

- Außerdem muss Ihnen die Rolle "E-Mail-Empfänger" in Ihrer Exchange Online Organisation zugewiesen werden. Dies ist erforderlich, um das Cmdlet **"Get-MailboxFolderStatistics"** auszuführen, das im Skript enthalten ist. Standardmäßig wird die Rolle "E-Mail-Empfänger" den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" in Exchange Online zugewiesen. Weitere Informationen zum Zuweisen von Berechtigungen in Exchange Online finden Sie unter [Verwalten von Rollengruppenmitgliedern.](/exchange/manage-role-group-members-exchange-2013-help) Sie können auch eine benutzerdefinierte Rollengruppe erstellen, ihr die Rolle "E-Mail-Empfänger" zuweisen und dann die Mitglieder hinzufügen, die das Skript in Schritt 1 ausführen müssen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen.](/Exchange/permissions-exo/role-groups)

- Das Skript in diesem Artikel unterstützt die moderne Authentifizierung. Sie können das Skript wie besehen verwenden, wenn Sie ein Microsoft 365 oder eine Microsoft 365 GCC Organisation sind. Wenn Sie eine Office 365 Deutschland-Organisation, eine Microsoft 365 GCC High-Organisation oder eine Microsoft 365 DoD-Organisation sind, müssen Sie das Skript bearbeiten, um es erfolgreich auszuführen. Insbesondere müssen Sie die Zeile bearbeiten `Connect-ExchangeOnline` und den *Parameter ExchangeEnvironmentName* (und den entsprechenden Wert für Ihren Organisationstyp) verwenden, um eine Verbindung mit Exchange Online PowerShell herzustellen.  Außerdem müssen Sie die Zeile bearbeiten `Connect-IPPSSession` und die Parameter *ConnectionUri* und *AzureADAuthorizationEndpointUri* (und die entsprechenden Werte für Ihren Organisationstyp) verwenden, um eine Verbindung mit Security & Compliance Center PowerShell herzustellen. Weitere Informationen finden Sie in den Beispielen in [Verbinden zu Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) und [Verbinden zu Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Jedes Mal, wenn Sie das Skript ausführen, wird eine neue PowerShell-Remotesitzung erstellt. Das bedeutet, dass Sie alle verfügbaren Remote-PowerShell-Sitzungen nutzen können. Um dies zu verhindern, führen Sie den folgenden Befehl aus, um ihre aktiven PowerShell-Remotesitzungen zu trennen.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Das Skript enthält eine minimale Fehlerbehandlung. Der Hauptzweck des Skripts besteht darin, schnell eine Liste der Postfachordner-IDs oder Websitepfade anzuzeigen, die in der Suchabfragesyntax einer Inhaltssuche zum Ausführen einer Zielsammlung verwendet werden können.

- Das in diesem Thema bereitgestellte Beispielskript wird unter keinem Microsoft-Standardsupportprogramm oder -dienst unterstützt. Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen. In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Schritt 1: Ausführen des Skripts zum Abrufen einer Liste von Ordnern für ein Postfach oder eine Website

Das Skript, das Sie in diesem ersten Schritt ausführen, gibt eine Liste der Postfachordner oder SharePoint und OneDrive for Business Ordner sowie die entsprechende Ordner-ID oder den Pfad für jeden Ordner zurück. Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert.

- **E-Mail-Adresse oder Website-URL:** Geben Sie eine E-Mail-Adresse des Verwalters ein, um eine Liste Exchange Postfachordner und Ordner-IDs zurückzugeben. Oder geben Sie die URL für eine SharePoint-Website oder eine OneDrive for Business-Website ein, um eine Liste der Pfade für die angegebene Website zurückzugeben. Im Folgenden finden Sie einige Beispiele:

  - **Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com

  - **SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing

  - **OneDrive for Business**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com

- **Ihre Benutzeranmeldeinformationen:** Das Skript verwendet Ihre Anmeldeinformationen, um mithilfe der modernen Authentifizierung eine Verbindung mit Exchange Online PowerShell oder Security & Compliance Center PowerShell herzustellen. Wie zuvor erläutert, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden, um dieses Skript erfolgreich ausführen zu können.

So zeigen Sie eine Liste von Postfachordnern oder Websitedokumentlinknamen (Pfadnamen) an:

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: `GetFolderSearchParameters.ps1` .

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

2. Öffnen Sie auf Ihrem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.

3. Führen Sie das Skript aus. Zum Beispiel:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Geben Sie die Informationen ein, nach denen Sie vom Skript aufgefordert werden.

    Das Skript zeigt eine Liste der Postfachordner oder Websiteordner für den angegebenen Benutzer an. Lassen Sie dieses Fenster geöffnet, damit Sie eine Ordner-ID oder einen Documentlink-Namen kopieren und in eine Suchabfrage in Schritt 2 einfügen können.

    > [!TIP]
    > Anstatt eine Liste der Ordner auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Skripts erneut an eine Textdatei weiterleiten. Diese Datei wird in dem Ordner gespeichert, in dem sich das Skript befindet. Um die Skriptausgabe beispielsweise an eine Textdatei umzuleiten, führen Sie den folgenden Befehl in Schritt 3 aus:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Anschließend können Sie eine Ordner-ID oder einen Dokumentlink aus der Datei kopieren, um sie in einer Suchabfrage zu verwenden.

### <a name="script-output-for-mailbox-folders"></a>Skriptausgabe für Postfachordner

Wenn Sie Postfachordner-IDs abrufen, stellt das Skript eine Verbindung mit Exchange Online PowerShell her, führt das Cmdlet **"Get-MailboxFolderStatisics"** aus und zeigt dann die Liste der Ordner aus dem angegebenen Postfach an. Für jeden Ordner im Postfach zeigt das Skript den Namen des Ordners in der **FolderPath-Spalte** und die Ordner-ID in der **FolderQuery-Spalte** an. Darüber hinaus fügt das Skript der Ordner-ID das Präfix **folderId** (d. h. den Namen der Postfacheigenschaft) hinzu. Da es sich bei der **FolderID-Eigenschaft** um eine durchsuchbare Eigenschaft handelt, verwenden Sie  `folderid:<folderid>` in einer Suchabfrage in Schritt 2, um diesen Ordner zu durchsuchen. Das Skript zeigt maximal 100 Postfachordner an.

> [!IMPORTANT]
> Das Skript in diesem Artikel enthält Codierungslogik, die die 64-Zeichen-Ordner-ID-Werte konvertiert, die von **Get-MailboxFolderStatistics** in dasselbe 48-Zeichen-Format zurückgegeben werden, das für die Suche indiziert ist. Wenn Sie einfach das Cmdlet **"Get-MailboxFolderStatistics"** in PowerShell ausführen, um eine Ordner-ID abzurufen (anstatt das Skript in diesem Artikel auszuführen), schlägt eine Suchabfrage fehl, die diesen Ordner-ID-Wert verwendet. Sie müssen das Skript ausführen, um die richtig formatierten Ordner-IDs abzurufen, die in einer Inhaltssuche verwendet werden können.

Hier ist ein Beispiel für die Ausgabe, die vom Skript für Postfachordner zurückgegeben wird.

![Beispiel für die Liste der Postfachordner und Ordner-IDs, die vom Skript zurückgegeben werden](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

Das Beispiel in Schritt 2 zeigt die Abfrage, die zum Durchsuchen des Unterordners "Löschelemente" im Ordner "Wiederherstellbare Elemente" des Benutzers verwendet wird.

### <a name="script-output-for-site-folders"></a>Skriptausgabe für Websiteordner

Wenn Sie den Pfad der **documentlink-Eigenschaft** von SharePoint oder OneDrive for Business Websites abrufen, stellt das Skript eine Verbindung mit Security & Compliance PowerShell her, erstellt eine neue Inhaltssuche, die die Website nach Ordnern durchsucht, und zeigt dann eine Liste der Ordner an, die sich auf der angegebenen Website befinden. Das Skript zeigt den Namen der einzelnen Ordner an und fügt der Ordner-URL das Präfix **"documentlink"** hinzu. Da es sich bei der **documentlink-Eigenschaft** um eine durchsuchbare Eigenschaft handelt, verwenden Sie `documentlink:<path>` das Eigenschaften-Wert-Paar in einer Suchabfrage in Schritt 2, um diesen Ordner zu durchsuchen. Das Skript zeigt maximal 200 Websiteordner an. Wenn mehr als 200 Websiteordner vorhanden sind, werden die neuesten angezeigt.

Hier ist ein Beispiel für die Ausgabe, die vom Skript für Websiteordner zurückgegeben wird.

![Beispiel für die Liste der documentlink-Namen für Websiteordner, die vom Skript zurückgegeben werden](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Schritt 2: Verwenden einer Ordner-ID oder eines Dokumentlinks zum Ausführen einer zielgerichteten Sammlung

Nachdem Sie das Skript ausgeführt haben, um eine Liste der Ordner-IDs oder Dokumentlinks für einen bestimmten Benutzer zu sammeln, fahren Sie im nächsten Schritt mit dem Microsoft 365 Compliance Center fort und erstellen eine neue Inhaltssuche, um einen bestimmten Ordner zu durchsuchen. You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). Sie können die  `folderid`  `documentlink` Eigenschaft mit anderen Suchparametern oder Suchbedingungen kombinieren. Wenn Sie nur die  `folderid`  `documentlink` Oder-Eigenschaft in die Abfrage einschließen, gibt die Suche alle Elemente zurück, die sich im angegebenen Ordner befinden.

1. Wechseln Sie zu <https://compliance.microsoft.com> und melden Sie sich mit dem Konto und den Anmeldeinformationen an, die Sie zum Ausführen des Skripts in Schritt 1 verwendet haben.

2. Klicken Sie im linken Bereich des Compliance Centers auf **"Alle**  >  **Inhaltssuche** anzeigen", und klicken Sie dann auf **"Neue Suche".**

3. Fügen Sie in das Feld **Schlüsselwörter** den `folderid:<folderid>` wert ein, der vom Skript in Schritt  `documentlink:<path>/*` 1 zurückgegeben wurde.

    Die Abfrage im folgenden Screenshot sucht beispielsweise nach einem beliebigen Element im Unterordner "Löschungen" im Ordner "Wiederherstellbare Elemente" des Benutzers (der Wert der `folderid` Eigenschaft für den Unterordner "Löschungen" wird im Screenshot in Schritt 1 angezeigt):

    ![Einfügen der Ordner-ID oder des Documentlinks in das Schlüsselwortfeld der Suchabfrage](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > Für dokumentlinksuchvorgänge ist die Verwendung einer nachgestellten  `asterisk '/*'` .  

4. Wählen Sie unter **"Speicherorte"** **bestimmte Speicherorte aus,** und klicken Sie dann auf **"Ändern".**

5. Führen Sie eine der folgenden Aktionen aus, je nachdem, ob Sie einen Postfachordner oder einen Websiteordner durchsuchen:

    - Klicken Sie neben **Exchange E-Mail** auf **Benutzer, Gruppen oder Teams auswählen,** und fügen Sie dann dasselbe Postfach hinzu, das Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.

      Oder

    - Klicken Sie neben **SharePoint Websites** auf **"Websites auswählen",** und fügen Sie dann dieselbe Website-URL hinzu, die Sie beim Ausführen des Skripts in Schritt 1 angegeben haben.

6. Klicken Sie nach dem Speichern des zu durchsuchenden Inhaltsspeicherorts auf **"Speichern & ausführen",** geben Sie einen Namen für die Inhaltssuche ein, und klicken Sie dann auf **"Speichern",** um die Zielsammlungssuche zu starten.

### <a name="examples-of-search-queries-for-targeted-collections"></a>Beispiele für Suchabfragen für gezielte Sammlungen

Hier sind einige Beispiele für die Verwendung der Eigenschaften und der  `folderid`  `documentlink` Eigenschaften in einer Suchabfrage zum Ausführen einer Zielsammlung. Platzhalter werden  `folderid:<folderid>`  `documentlink:<path>` verwendet, um Platz zu sparen.

- In diesem Beispiel werden drei verschiedene Postfachordner durchsucht. Sie können eine ähnliche Abfragesyntax verwenden, um die ausgeblendeten Ordner im Ordner "Wiederherstellbare Elemente" eines Benutzers zu durchsuchen.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In diesem Beispiel wird ein Postfachordner nach Elementen durchsucht, die einen genauen Ausdruck enthalten.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- In diesem Beispiel wird ein Websiteordner (und alle Unterordner) nach Dokumenten durchsucht, die die Buchstaben "NDA" im Titel enthalten.

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- In diesem Beispiel wird ein Websiteordner (und ein beliebiger Unterordner) nach Dokumenten durchsucht, die innerhalb eines Datumsbereichs geändert wurden.

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Weitere Informationen

Beachten Sie bei der Verwendung des Skripts in diesem Artikel die folgenden Punkte, um gezielte Sammlungen auszuführen.

- Das Skript entfernt keine Ordner aus den Ergebnissen. Einige Ordner, die in den Ergebnissen aufgeführt sind, sind möglicherweise nicht durchsuchbar (oder geben Nullelemente zurück), da sie vom System generierte Inhalte enthalten oder weil sie nur Unterordner und keine Postfachelemente enthalten.

- Dieses Skript gibt nur Ordnerinformationen für das primäre Postfach des Benutzers zurück. Es werden keine Informationen zu Ordnern im Archivpostfach des Benutzers zurückgegeben. Um Informationen zu Ordnern im Archivpostfach des Benutzers zurückzugeben, können Sie das Skript bearbeiten. Ändern Sie dazu die Zeile in das `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` bearbeitete Skript, speichern und führen Sie es aus. Diese Änderung gibt die Ordner-IDs für Ordner und Unterordner im Archivpostfach des Benutzers zurück. Um das gesamte Archivpostfach zu durchsuchen, können Sie alle Ordner-ID-Eigenschaft:Wert-Paare mit einem `OR` Operator in einer Suchabfrage verbinden.

- Beim Durchsuchen von Postfachordnern wird nur der angegebene Ordner (durch seine `folderid` Eigenschaft identifiziert) durchsucht. Unterordner werden nicht durchsucht. Um Unterordner zu durchsuchen, müssen Sie die Ordner-ID für den Unterordner verwenden, den Sie durchsuchen möchten.

- Beim Durchsuchen von Websiteordnern werden der Ordner (durch seine `documentlink` Eigenschaft identifiziert) und alle Unterordner durchsucht.

- Beim Exportieren der Ergebnisse einer Suche, in der Sie nur die Eigenschaft in der Suchabfrage angegeben `folderid` haben, können Sie die erste Exportoption auswählen: "Alle Elemente, mit Ausnahme von Elementen mit einem nicht erkannten Format, werden verschlüsselt oder wurden aus anderen Gründen nicht indiziert." Alle Elemente im Ordner werden unabhängig von ihrem Indizierungsstatus immer exportiert, da die Ordner-ID immer indiziert ist.
