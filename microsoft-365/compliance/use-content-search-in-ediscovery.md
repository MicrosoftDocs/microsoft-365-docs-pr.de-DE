---
title: Verwenden der Inhaltssuche im eDiscovery-Workflow
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Verwenden Sie ein PowerShell-Skript, um eine Compliance-eDiscovery-Suche in Exchange Online basierend auf einer im Security #a0 Compliance Center erstellten Suche zu erstellen. '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081861"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Verwenden der Inhaltssuche im eDiscovery-Workflow

Mit der Funktion für die Inhaltssuche im Security #a0 Compliance Center können Sie alle Postfächer in Ihrer Organisation durchsuchen. Im Gegensatz zur Compliance-eDiscovery in Exchange Online (in der Sie bis zu 10.000 Postfächer durchsuchen können) gibt es keine Beschränkungen für die Anzahl der Zielpostfächer in einer einzigen Suche. Für Szenarien, in denen organisationsweite Suchen erforderlich sind, können Sie die Inhaltssuche zum Durchsuchen aller Postfächer verwenden. Anschließend können Sie die Workflowfunktionen von in-situ-eDiscovery verwenden, um andere eDiscovery-bezogene Aufgaben auszuführen, beispielsweise das Platzieren von Postfächern in der Warteschleife und das Exportieren von Suchergebnissen. Angenommen, Sie müssen alle Postfächer durchsuchen, um bestimmte Verwalter zu identifizieren, die auf einen Rechtsfall reagieren. Sie können die Inhaltssuche im Security #a0 Compliance Center verwenden, um alle Postfächer in Ihrer Organisation zu durchsuchen, um diejenigen zu identifizieren, die auf den Fall reagieren. Anschließend können Sie diese Liste von Depot Postfächern als Quellpostfächer für eine in-Place-eDiscovery-Suche in Exchange Online verwenden. Mithilfe von in-situ-eDiscovery können Sie auch diese Quellpostfächer speichern, Suchergebnisse in ein Discovery-Postfach kopieren und die Suchergebnisse exportieren.
  
Dieses Thema enthält ein Skript, das Sie ausführen können, um eine Compliance-eDiscovery-Suche in Exchange Online zu erstellen, indem Sie die Liste der Quellpostfächer und die Suchabfrage aus einer im Security #a0 Compliance Center erstellten Suche verwenden. Im Folgenden finden Sie eine Übersicht über den Vorgang:
  
[Schritt 1: Erstellen einer Inhaltssuche zum Durchsuchen aller Postfach in Ihrer Organisation](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Schritt 2: Herstellen einer Verbindung mit \& dem Security Compliance Center und Exchange Online in einer einzelnen Remote-PowerShell-Sitzung](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Schritt 3: Ausführen des Skripts zum Erstellen einer In-Situ-eDiscovery-Suche aus der Inhaltssuche](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Schritt 1: Erstellen einer Inhaltssuche zum Durchsuchen aller Postfächer in Ihrer Organisation

Der erste Schritt besteht in der Verwendung des Security #a0 Compliance Center (oder der Security #a1 Compliance Center PowerShell), um eine Inhaltssuche zu erstellen, die alle Postfächer in Ihrer Organisation durchsucht. Es gibt keine Begrenzung für die Anzahl der Postfächer für eine einzelne Inhaltssuche. Geben Sie eine geeignete Stichwortabfrage (oder eine Abfrage für vertrauliche Informationstypen) an, damit die Suche nur die Quellpostfächer zurückgibt, die für Ihre Untersuchung relevant sind. Verfeinern Sie bei Bedarf die Suchabfrage, um den Umfang der zurückgegebenen Suchergebnisse und Quellpostfächer einzuschränken.
  
> [!NOTE]
> Wenn die Quellinhaltssuche keine Ergebnisse liefert, wird In-Situ-eDiscovery nicht erstellt, wenn Sie das Skript in Schritt 3 ausführen. Sie müssen die Suchabfrage möglicherweise überarbeiten und die Inhaltssuche erneut ausführen, damit Suchergebnisse zurückgegeben werden. 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>Verwenden des Security & Compliance Center zum Durchsuchen aller Postfächer

1. [Wechseln Sie zum Security #a0 Compliance Center](go-to-the-securitycompliance-center.md). 
    
2. Klicken Sie auf **Such** > **Inhaltssuche**, und klicken Sie dann auf](media/O365-MDM-CreatePolicy-AddIcon.gif)neues Symbol für die **Suche** ![hinzufügen.
    
3. Geben Sie auf der Seite **Neue Suche** einen Namen für die Inhaltssuche ein. 
    
4. Klicken Sie unter **Wo sollen wir suchen?** auf **Alle Postfächer durchsuchen**, und klicken Sie dann auf **Weiter**.
    
5. Geben Sie im Feld unter **Wonach sollen wir für Sie suchen?** eine Suchabfrage ein. Sie können Schlüsselwörter, Nachrichteneigenschaften , z. B. Sende- und Empfangsdatum, oder Dokumenteigenschaften angeben, z. B. Dateinamen oder das Datum der letzten Dokumentänderung. Sie können komplexere Abfragen verwenden, die einen booleschen Operator wie and, or, Not oder near verwenden, oder Sie können auch nach vertraulichen Informationen (beispielsweise Sozialversicherungsnummern) in Nachrichten suchen. Weitere Informationen zum Erstellen von Suchabfragen finden Sie unter [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
6. Klicken Sie auf **Suche**, um die Sucheinstellungen zu speichern und die Suche zu starten. 
    
    Nach einer Weile eine Schätzung der Suchergebnisse, die im Detailbereich angezeigt werden. Dieser umfasst die Gesamtgröße und die Gesamtanzahl der in den Suchergebnissen zurückgegebenen Elemente. Wenn die Suche abgeschlossen ist, können Sie eine Vorschau der Suchergebnisse anzeigen. Klicken Sie bei Bedarf ****![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren, um die Informationen im Detailbereich zu aktualisieren. 
    
7.  Verfeinern Sie ggf. die Suchabfrage, um die Suchergebnisse einzugrenzen, und starten Sie die Suche neu. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Verwenden von Security #a0 Compliance Center PowerShell zum Durchsuchen aller Postfächer

Sie können auch das **New-ComplianceSearch**-Cmdlet zum Durchsuchen aller Postfächer in Ihrer Organisation verwenden. Der erste Schritt besteht darin, [eine Verbindung mit Security #a0 Compliance Center PowerShell herzustellen](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Im folgenden finden Sie ein Beispiel für die Verwendung von PowerShell zum Durchsuchen aller Postfächer in Ihrer Organisation. Die Suchabfrage gibt alle zwischen dem 1. Januar 2015 und dem 30. Juni 2015 gesendeten Nachrichten zurück, die den Ausdruck "Finanzbericht" in der Betreffzeile enthalten. Der erste Befehl erstellt die Suche, und der zweite Befehl führt die Suche aus. 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Weitere Informationen finden Sie unter [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Überprüfen der Anzahl der Quellpostfächer in der Inhaltssuche

Bei einer Inhaltssuche werden maximal 1.000 Quellpostfächer zurückgegeben, die Suchergebnisse enthalten. Wenn mehr als 1.000 Postfächer vorhanden sind, die Inhalte enthalten, die mit der Suchabfrage übereinstimmen, werden nur die obersten 1.000-Postfächer mit den meisten Suchergebnissen in die Inhaltssuche einbezogen, die Sie im vorherigen Schritt erstellt haben. Wenn also mehr als 1.000 Postfächer Suchergebnisse enthalten, werden einige dieser Postfächer nicht in die Liste der Quellpostfächer aufgenommen, die in die neue in-Place-eDiscovery-Suche kopiert wurden, die in Schritt 3 erstellt wurde. 
  
Wenn Sie eine Inhaltssuche mit nicht mehr als 1.000 Quellpostfächern unterstützen möchten, führen Sie die folgenden Schritte aus, um ein Skript auszuführen, mit dem die Anzahl der Quellpostfächer (die Suchergebnisse enthält), die von der in Schritt 1 erstellten Inhaltssuche zurückgegeben werden, angezeigt wird. 
  
1. Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei unter Verwendung des filename-Suffixes ". ps1". Sie können es beispielsweise in einer Datei mit dem Namen `SourceMailboxes.ps1`speichern.
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. Wechseln Sie in Security #a0 Compliance Center PowerShell zu dem Ordner, in dem sich das im vorherigen Schritt erstellte Skript befindet, und führen Sie dann das Skript aus. Zum Beispiel:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. Geben Sie, wenn Sie vom Skript dazu aufgefordert werden, die in Schritt 1 erstellte Inhaltssuche ein.
    
    Das Skript zeigt die Anzahl der Quellpostfächer, die Suchergebnisse enthalten.
    
Wenn mehr als 1.000 Quellpostfächer vorhanden sind, versuchen Sie, zwei (oder mehr) Inhalts suchen zu erstellen. Suchen Sie beispielsweise die Hälfte der Postfächer Ihrer Organisation in einer Inhaltssuche und die andere Hälfte in einer anderen Inhaltssuche. Sie können auch die Suchkriterien ändern, um die Anzahl der Postfächer zu verringern, die Suchergebnisse enthalten. Beispielsweise können Sie einen Datumsbereich einschließen oder die Stichwortabfrage verfeinern.
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Schritt 2: Herstellen einer Verbindung mit \& dem Security Compliance Center und Exchange Online in einer einzelnen Remote-PowerShell-Sitzung

Der nächste Schritt besteht darin, eine Verbindung zwischen Windows PowerShell sowohl mit dem Security #a0 Compliance Center als auch mit Ihrer Exchange Online Organisation herzustellen. Dies ist erforderlich, da das in Schritt 3 ausgeführte Skript Zugriff auf die Cmdlets für die Inhaltssuche im Security #a0 Compliance Center und in den in-Place-eDiscovery-Cmdlets in Exchange Online erfordert.
  
1. Speichern Sie den folgenden Text in einer Windows PowerShell-Skriptdatei mithilfe des Dateinamensuffixes „.ps1". Sie können es beispielsweise in einer Datei mit dem Namen `ConnectEXO-CC.ps1`speichern.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, wechseln Sie zu dem Ordner, in dem sich das Skript befindet, das Sie im vorherigen Schritt erstellt haben, und führen Sie dann das Skript aus. Zum Beispiel:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

Woher wissen Sie, dass dieses Verfahren erfolgreich war? Nachdem Sie das Skript ausgeführt haben, werden Cmdlets aus dem Security #a0 Compliance Center und Exchange Online in Ihre lokale PowerShell-Sitzung importiert. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein Schnelltest besteht darin, ein Security #a0 Compliance Center-Cmdlet (beispielsweise **install-UnifiedCompliancePrerequisite** ) und ein Exchange Online-Cmdlet wie **Get-Mailbox**auszuführen. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Schritt 3: Ausführen des Skripts zum Erstellen einer In-Situ-eDiscovery-Suche aus der Inhaltssuche

Nachdem Sie die duale PowerShell-Sitzung in Schritt 2 erstellt haben, besteht der nächste Schritt darin, ein Skript auszuführen, mit dem eine vorhandene Inhaltssuche in eine Compliance-eDiscovery-Suche konvertiert wird. Das Skript führt Folgendes aus:
  
- Es fordert Sie auf, den Namen der zu konvertierenden Inhaltssuche anzugeben.
    
- Es stellt sicher, dass die Inhaltssuche abgeschlossen wird. Wenn die Compliancesuche keine Ergebnisse zurückgibt, wird In-Situ-eDiscovery nicht erstellt.
    
- Speichert eine Liste der Quellpostfächer aus der Inhaltssuche mit den Suchergebnissen in einer Variablen.
    
- Erstellt eine neue In-Situ-eDiscovery-Suche mit den folgenden Eigenschaften. Beachten Sie, dass die neue Suche noch nicht gestartet wurde. Sie werden diese in Schritt 4 starten.
    
  - **Name** – der Name der neuen Suche verwendet dieses Format: \<Name der Inhaltssuche\>_MBSearch1. Wenn Sie das Skript erneut ausführen und dieselbe Quellinhalts Suche verwenden, wird die Suche mit \<dem Namen Name der Inhaltssuche\>_MBSearch2.
    
  - **Quellpostfächer** – alle Postfächer aus der Inhaltssuche, die Suchergebnisse enthalten. 
    
  - **Suchabfrage** – die neue Suche verwendet die Suchabfrage aus der Inhaltssuche. Berücksichtigt die Inhaltssuche alle Inhalte (leere Suchabfrage), so ist in der neuen Suche die Suchabfrage leer und es werden alle in den Quellpostfächern enthaltenen Inhalte berücksichtigt. 
    
  - **Nur Suche bewerten** – die neue Suche wird als reine schätzungs Suche markiert. Die Suchergebnisse werden nicht in ein Discoverypostfach kopiert, nachdem Sie es starten. 
    
1. Speichern Sie den folgenden Text in einer Windows PowerShell-Skriptdatei mithilfe des Dateinamensuffixes „.ps1". Sie können es beispielsweise in einer Datei mit dem Namen `CreateMBSearchFromComplianceSearch.ps1`speichern.
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. Wechseln Sie in der Windows PowerShell-Sitzung, die Sie in Schritt 2 erstellt haben, zu dem Ordner, in dem sich das Skript befindet, das Sie im vorherigen Schritt erstellt haben, und führen Sie dann das Skript aus. Zum Beispiel:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Wenn Sie vom Skript dazu aufgefordert werden, geben Sie den Namen der Inhaltssuche ein, die Sie in einer Compliance-eDiscovery-Suche abdecken möchten (beispielsweise die Suche, die Sie in Schritt 1 erstellt haben), und drücken Sie dann die **Eingabe**Taste.
    
    Wenn das Skript erfolgreich ausgeführt wird, wird eine neue In-Situ-eDiscovery-Suche mit dem Status **NotStarted** erstellt. Führen Sie den Befehl  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` aus, um die Eigenschaften der neuen Suche anzuzeigen. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Schritt 4: Starten der In-Situ-eDiscovery-Suche

Das Skript, das Sie in Schritt 3 ausführen, erstellt eine neue Compliance-eDiscovery-Suche, startet diese aber nicht. Der nächste Schritt ist das Starten der Suche, damit Sie eine Schätzung der Suchergebnisse abrufen können.
  
1. Navigieren Sie in Exchange-Verwaltungskonsole (EAC) zu **Verwaltung der Compliance** \> **Compliance-eDiscovery &amp; Compliance-Archive**.
    
2. Wählen Sie in der Listenansicht die Compliance-eDiscovery-Suche aus, die Sie in Schritt 3 erstellt haben.
    
3. ![](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> Klicken **Sie auf Such Suchsymbol** -Such **Ergebnisse schätzen** , um die Suche zu starten und eine Schätzung der Gesamtgröße und der Anzahl der Elemente zurückzugeben, die von der Suche zurückgegeben werden. 
    
    Die Schätzungen werden im Detailbereich angezeigt. Klicken Sie auf Aktualisierungs](media/O365-MDM-Policy-RefreshIcon.gif) Symbol aktualisieren, um die im Detailbereich angezeigten Informationen zu aktualisieren. **** ![ 
    
4. Um eine Vorschau der Ergebnisse anzuzeigen, nachdem die Suche abgeschlossen ist, klicken Sie im Detailbereich auf **Vorschau der Suchergebnisse anzeigen**.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Nächste Schritte nach dem Erstellen und Ausführen der In-Situ-eDiscovery-Suche

Nach dem Erstellen und Starten der In-Situ-eDiscovery-Suche, die mit dem Skript in Schritt 3 erstellt wurde, können Sie den normalen In-Situ-eDiscovery-Workflow zum Durchführen verschiedener eDiscovery-Aktionen an den Suchergebnissen verwenden.
  
### <a name="create-an-in-place-hold"></a>Erstellen eines In-Situ-Archivs

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Wählen Sie in der Listenansicht die in-Place-eDiscovery-Suche aus, die Sie in Schritt 3 erstellt **** ![haben, und](media/O365-MDM-CreatePolicy-EditIcon.gif)klicken Sie dann auf Bearbeitungssymbol bearbeiten.
    
3. Aktivieren Sie auf der Seite **Compliance-Archive** das Kontrollkästchen **Inhalt, der in ausgewählten Postfächern mit der Suchabfrage übereinstimmt, aufbewahren**, und wählen Sie eine der folgenden Optionen: 
    
  - Auf unbestimmte Zeit **halten** – wählen Sie diese Option aus, um von der Suche zurückgegebene Elemente auf einem unbefristeten Haltestatus zu platzieren. Aufbewahrte Elemente werden solange beibehalten, bis Sie das Postfach aus der Suche entfernt oder die Suche entfernt haben. 
    
  - **Geben Sie die Anzahl der Tage an, die Elemente im Verhältnis zum Empfangsdatum aufbewahrt** werden sollen: Wählen Sie diese Option aus, um Elemente für einen bestimmten Zeitraum zu speichern. Der Zeitraum beginnt mit dem Datum, an dem das Postfachelement empfangen oder erstellt wurde. 
    
4. Klicken Sie auf **Speichern**, um das Compliance-Archiv zu erstellen und die Suche neu zu starten. 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Kopieren der Suchergebnisse

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. Wählen Sie in der Listenansicht die In-Situ-eDiscovery-Suche aus, die Sie in Schritt 3 erstellt haben.
    
3. Klicken **Sie auf** ![Such](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)Suchsymbol, und klicken Sie dann in der Dropdownliste auf **Suchergebnisse kopieren** . 
    
4. Wählen Sie unter **Suchergebnisse kopieren** aus den folgenden Optionen:
    
    - Nicht durch **Such Bare Elemente einschließen** : Aktivieren Sie dieses Kontrollkästchen, um Postfachelemente einzubeziehen, die nicht durchsucht werden konnten (beispielsweise Nachrichten mit Anlagen von Dateitypen, die nicht von der Exchange-Suche indiziert werden konnten). 
    
    - **Deduplizierung aktivieren** -aktivieren Sie dieses Kontrollkästchen, um doppelte Nachrichten auszuschließen. Es wird nur eine einzelne Instanz einer Nachricht in das Discovery-Postfach kopiert. 
    
    - **Vollständige Protokollierung aktivieren** : Aktivieren Sie dieses Kontrollkästchen, um ein vollständiges Protokoll in Suchergebnissen einzuschließen. 
    
    - **E-Mail senden, wenn die Kopie abgeschlossen ist** : Aktivieren Sie dieses Kontrollkästchen, um eine e-Mail-Benachrichtigung zu erhalten, wenn die Suche abgeschlossen ist. 
    
    - **Ergebnisse in dieses Ermittlungspostfach kopieren** – klicken Sie auf **Durchsuchen** , um das Ermittlungspostfach auszuwählen, in das die Suchergebnisse kopiert werden sollen. 
    
5. Klicken Sie auf **Kopieren**, um den Prozess zum Kopieren der Suchergebnisse in das angegebene Discoverypostfach zu starten. 
    
6. Klicken Sie auf Aktualisierungs](media/O365-MDM-Policy-RefreshIcon.gif) Symbol aktualisieren, um die Informationen zum Kopierstatus zu aktualisieren, die im Detailbereich angezeigt werden. **** ![ 
    
7. Wenn der Kopiervorgang abgeschlossen ist, klicken Sie auf **Öffnen**, um das Discoverypostfach zu öffnen und die Suchergebnisse anzuzeigen. 
  
### <a name="export-the-search-results"></a>Exportieren der Suchergebnisse

1. Navigieren Sie in EAC zu **Verwaltung der Richtlinientreue** \> **In-Situ-eDiscovery &amp; Haltebereich**.
    
2. Wählen Sie in der Listenansicht die Compliance-eDiscovery-Suche aus, die Sie in Schritt 3 erstellt haben, und klicken Sie anschließend auf **In eine PST-Datei exportieren**.
    
3. Gehen Sie im Fenster **eDiscovery-PST-Exporttool** folgendermaßen vor: 
    
    - Klicken Sie auf **Durchsuchen**, und geben Sie das Verzeichnis an, in das die PST-Datei heruntergeladen werden soll. 
    
    - Klicken Sie auf das Kontrollkästchen **Entfernung von Duplikaten aktivieren**, um doppelte Nachrichten auszuschließen. Es wird nur eine einzelne Instanz einer Nachricht in die PST-Datei aufgenommen. 
    
    - Wählen Sie das Kontrollkästchen **Nicht durchsuchbare Elemente einschließen** aus, um Postfachelemente zu berücksichtigen, die nicht durchsucht werden konnten (z. B. Nachrichten mit Anhängen, die Dateitypen enthalten, die von der Exchange-Suche nicht indiziert werden konnten). Nicht durchsuchbare Elemente werden in eine separate PST-Datei exportiert. 
    
4. Klicken Sie auf **Start**, um die Suchergebnisse in eine PST-Datei zu exportieren. 
    
    Es wird ein Fenster angezeigt, das Statusinformationen über den Exportvorgang anzeigt.
