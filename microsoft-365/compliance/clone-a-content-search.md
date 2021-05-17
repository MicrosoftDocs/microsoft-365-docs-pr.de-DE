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
description: Verwenden Sie das PowerShell-Skript in diesem Artikel, um eine vorhandene Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918061"
---
# <a name="clone-a-content-search"></a>Klonen einer Inhaltssuche

Das Erstellen einer Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365, die viele Postfächer oder SharePoint- und OneDrive for Business-Websites durchsucht, kann eine Weile dauern. Das Angeben der zu durchsuchenden Websites kann auch fehleranfällig sein, wenn Sie eine URL falsch eingeben. Um diese Probleme zu vermeiden, können Sie das Windows PowerShell in diesem Artikel verwenden, um eine vorhandene Inhaltssuche schnell zu klonen. Wenn Sie eine Suche klonen, wird eine neue Suche (mit einem anderen Namen) erstellt, die die gleichen Eigenschaften (z. B. die Inhaltsorte und die Suchabfrage) wie die ursprüngliche Suche enthält. Anschließend können Sie die neue Suche bearbeiten, indem Sie die Stichwortabfrage oder den Datumsbereich ändern und ausführen.
  
Warum Inhaltssuchen klonen?
  
- Zum Vergleichen der Ergebnisse verschiedener Schlüsselwortsuchabfragen werden an denselben Inhaltsstandorten ausgeführt.
    
- Um zu sparen, dass Sie beim Erstellen einer neuen Suche eine große Anzahl von Inhaltsstandorten erneut einsenken müssen.
    
- So verringern Sie die Größe der Suchergebnisse. Wenn Sie beispielsweise über eine Suche verfügen, die zu viele Zu exportierende Ergebnisse zurückgibt, können Sie die Suche klonen und dann eine Suchbedingung basierend auf einem Datumsbereich hinzufügen, um die Anzahl der Suchergebnisse zu reduzieren.
  
## <a name="script-information"></a>Skriptinformationen

- Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center sein, um das in diesem Thema beschriebene Skript auszuführen.
    
- Das Skript enthält eine minimale Fehlerbehandlung. Der Hauptzweck des Skripts besteht im schnellen Klonen einer Inhaltssuche.
    
- Das Skript erstellt eine neue Inhaltssuche, startet sie jedoch nicht.
    
- Dieses Skript berücksichtigt, ob die Inhaltssuche, die Sie klonen, einem eDiscovery-Fall zugeordnet ist. Wenn die Suche einem Fall zugeordnet ist, wird die neue Suche auch demselben Fall zugeordnet. Wenn die vorhandene Suche keinem Fall zugeordnet ist, wird die  neue Suche auf der Seite Inhaltssuche im Compliance Center aufgeführt. 
    
- Das in diesem Thema bereitgestellte Beispielskript wird in keinem Standardsupportprogramm oder -dienst von Microsoft unterstützt. Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen. In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Schritt 1: Ausführen des Skripts zum Klonen einer Suche

Das Skript in diesem Schritt erstellt eine neue Inhaltssuche durch Klonen eines vorhandenen. Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert:
  
- **Ihre Benutzeranmeldeinformationen** – Das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit dem Security & Compliance Center für Ihre Organisation mit Windows PowerShell. Wie bereits erwähnt, müssen Sie Mitglied der Rollengruppe eDiscovery Manager im Security & compCompliance Center sein, um das Skript ausführen zu können. 
    
- **Der Name der vorhandenen Suche** – Dies ist die Inhaltssuche, die Sie klonen möchten. 
    
- **Der** Name der neuen Suche, die erstellt wird: Wenn Sie diesen Wert leer lassen, erstellt das Skript einen Namen für die neue Suche, der auf dem Namen der Suche basiert, die Sie klonen. 
    
So klonen Sie eine Suche:
  
1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie ein Dateinamensuffix von .ps1; Beispiel: `CloneSearch.ps1` .
    
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

2. Öffnen Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.
    
3. Führen Sie das Skript aus. Zum Beispiel:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre E-Mail-Adresse und Ihr Kennwort ein, und klicken Sie dann auf **OK**.
    
5. Geben Sie die folgenden Informationen ein, wenn Sie vom Skript dazu aufgefordert werden. Geben Sie alle Informationen ein, und drücken Sie dann die **EINGABETASTE.**
    
    - Der Name der vorhandenen Suche.
    
    - Der Name der neuen Suche.
    
    Das Skript erstellt die neue Inhaltssuche, startet sie jedoch nicht. Dadurch haben Sie die Möglichkeit, die Suche im nächsten Schritt zu bearbeiten und ausführen. Sie können die Eigenschaften der neuen Suche anzeigen, indem Sie das **Cmdlet Get-ComplianceSearch** ausführen oder zur Seite Inhaltssuche oder **eDiscovery** im Compliance Center gehen, je nachdem, ob die neue Suche einem Fall zugeordnet ist.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Schritt 2: Bearbeiten und Ausführen der geklonten Suche im Compliance Center

Nachdem Sie das Skript zum Klonen einer vorhandenen Inhaltssuche ausgeführt haben, gehen Sie im nächsten Schritt zum Compliance Center, um die neue Suche zu bearbeiten und auszuführen. Wie bereits erwähnt, können Sie eine Suche bearbeiten, indem Sie die Schlüsselwortsuchabfrage ändern und Suchbedingungen hinzufügen oder entfernen. Weitere Informationen finden Sie unter:
  
- [Inhaltssuche in Office 365](content-search.md)
    
- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
    
- [eDiscovery-Fälle](./get-started-core-ediscovery.md)