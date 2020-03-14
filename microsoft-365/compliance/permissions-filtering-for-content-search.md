---
title: Konfigurieren der Berechtigungsfilterung für die Compliancesuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Verwenden Sie die Inhaltssuche-Berechtigungs Filterung, um einem eDiscovery-Manager nur eine Teilmenge von Postfächern und Websites in Ihrer Office 365 Organisation suchen zu lassen.
ms.openlocfilehash: 670dd2e5d0c88c520234cd7e71805cfa97ad9ec9
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634263"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Konfigurieren der Berechtigungsfilterung für die Compliancesuche

Sie können die Such Berechtigungs Filterung verwenden, um einem eDiscovery-Manager nur eine Teilmenge von Postfächern und Websites in Ihrer Office 365 Organisation suchen zu lassen. Sie können Berechtigungsfilter auch verwenden, um demselben eDiscovery-Managers zu ermöglichen, nur nach Postfach- oder Websiteinhalt zu suchen, der bestimmten Suchkriterien entspricht. Sie können einem Discovery-Manager beispielsweise ermöglichen, nur die Postfächer der Benutzer an einem bestimmten Standort oder in einer bestimmten Abteilung zu durchsuchen. Hierzu erstellen Sie einen Filter, der einen unterstützten Empfängerfilter verwendet, um die Postfächer zu begrenzen, die ein bestimmter Benutzer oder eine bestimmte Gruppe von Benutzern durchsuchen kann. Sie können auch einen Filter erstellen, der angibt, nach welchen Postfachinhalten ein Benutzer suchen kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Nachrichteneigenschaft verwendet. Auf ähnliche Weise können Sie es einem eDiscovery-Manager ermöglichen, nur bestimmte SharePoint-Websites in Ihrer Organisation zu durchsuchen. Hierzu erstellen Sie einen Filter, der einschränkt, welche Website durchsucht werden kann. Sie können auch einen Filter erstellen, der angibt, welcher Websiteinhalt durchsucht werden kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Website-Eigenschaft verwendet.

Sie können auch die Such Berechtigungs Filterung verwenden, um logische Grenzen (sogenannte *Compliance-Grenzen*) in einer Office 365 Organisation zu erstellen, die die Benutzerinhalts Speicherorte (wie Postfächer, SharePoint-Websites und OneDrive-Konten) steuert, die von bestimmten eDiscovery-Managern durchsucht werden können. Weitere Informationen finden Sie unter [Einrichten von Compliance-Grenzen für eDiscovery-Untersuchungen in Office 365](tagging-and-assessment-in-advanced-ediscovery.md).
  
Die Such Berechtigungs Filterung wird von der Inhalts Suchfunktion im Security & Compliance Center unterstützt. Mit diesen vier Cmdlets können Sie Such Berechtigungsfilter konfigurieren und verwalten:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Gruppe-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Ausführen der Cmdlets für den Compliance-Sicherheitsfilter müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).
    
- Sie müssen Windows PowerShell sowohl mit dem Security & Compliance Center als auch mit Ihrer Exchange Online Organisation verbinden, um die Compliance Security Filter-Cmdlets zu verwenden. Dies ist erforderlich, da diese Cmdlets Zugriff auf Postfacheigenschaften benötigen, weshalb Sie eine Verbindung mit Exchange Online herstellen müssen. Lesen Sie die Schritte im nächsten Abschnitt. 
    
- Weitere Informationen über Berechtigungsfilter für die Suche finden Sie im Abschnitt [More information](#more-information). 
    
- Die Such Berechtigungs Filterung gilt für inaktive Postfächer, was bedeutet, dass Sie die Post Fach-und Postfachinhalts Filterung verwenden können, um zu begrenzen, wer ein inaktives Postfach durchsuchen kann Weitere Informationen zur Filterung von Berechtigungen und inaktiven Postfächern finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
    
-  Die Such Berechtigungs Filterung kann nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in Exchange durchsuchen kann. 
    
- Es gibt keine Beschränkung für die Anzahl der Such Berechtigungsfilter, die in einer Organisation erstellt werden können. Die Suchleistung wird jedoch beeinträchtigt, wenn mehr als 100 Such Berechtigungsfilter vorhanden sind. Wenn Sie die Anzahl der Such Berechtigungsfilter in Ihrer Organisation so klein wie möglich halten möchten, erstellen Sie nach Möglichkeit Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzelnen Filter kombinieren.
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Herstellen einer Verbindung mit dem Security & Compliance Center und Exchange Online in einer einzelnen Remote-PowerShell-Sitzung

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung des Datei namens Suffixes " **. ps1**". Sie können es beispielsweise in einer Datei mit dem Namen " **ConnectEXO-cc. ps1**" speichern.
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, wechseln Sie zu dem Ordner, in dem sich das Skript befindet, das Sie im vorherigen Schritt erstellt haben, und führen Sie dann das Skript aus. Zum Beispiel:
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

Woher wissen Sie, dass dieses Verfahren erfolgreich war? Nachdem Sie das Skript ausgeführt haben, werden Cmdlets aus dem Security & Compliance Center und Exchange Online in Ihre lokale Windows PowerShell Sitzung importiert. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein Schnelltest besteht darin, ein Security &-Compliance Center-Cmdlet und ein Exchange Online-Cmdlet auszuführen. Beispielsweise können Sie **install-UnifiedCompliancePrerequisite** und **Get-Mailbox**ausführen. 
  
Wenn Sie Fehlermeldungen erhalten, überprüfen Sie die folgenden Anforderungen:
  
- Ein häufig auftretendes Problem ist ein falsches Kennwort. Führen Sie die beiden Schritte erneut durch, und achten Sie besonders auf die korrekte Eingabe des Benutzernamens und Kennworts in Schritt 1.
    
- Stellen Sie sicher, dass Ihr Konto über die Berechtigung zum Zugriff auf das Sicherheits & Compliance Center verfügt. Ausführliche Informationen finden Sie unter [Gewähren von Benutzern Zugriff auf das Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Um die Abwehr von DOS-Angriffen (Denial of Service) zu unterstützen, sind Sie auf drei offene Remote-PowerShell-Verbindungen mit dem Security & Compliance Center limitiert.
    
- Windows PowerShell müssen für die Ausführung von Skripts konfiguriert sein. Dies muss nur einmal ausgeführt werden, und nicht jedes Mal, wenn Sie eine Verbindung herstellen. Um Windows PowerShell für das Ausführen von signierten Skripts zu aktivieren, müssen Sie den folgenden Befehl in einem Windows PowerShell-Fenster mit erhöhten Rechten ausführen (ein Windows PowerShell-Fenster, das Sie durch Auswahl von **Als Administrator ausführen**) geöffnet haben.

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

- Der TCP-Port 80 muss für den Datenverkehr zwischen Ihrem lokalen Computer und Office 365 geöffnet sein. Er ist wahrscheinlich offen, es kann jedoch vorkommen, dass Ihre Organisation eine eingeschränkte Internetzugriffsrichtlinie verfolgt.

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Der **New-ComplianceSecurityFilter** wird verwendet, um einen Such Berechtigungsfilter zu erstellen. In der folgenden Tabelle werden die Parameter für dieses Cmdlet beschrieben. Alle Parameter sind erforderlich, um einen Compliancesicherheitsfilter zu erstellen. 
  
|**Parameter**|**Beschreibung**|
|:-----|:-----|
| _Action_ <br/> | Der Parameter _Action_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich:  <br/><br/> **Export:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird bei der Vorschau der Suchergebnisse angewendet.  <br/> **Säuberung:** Der Filter wird angewendet, wenn Suchergebnisse bereinigt werden.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **All:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_ <br/> |Der Parameter _Filter_ Name gibt den Namen des Berechtigungs Filters an. Dieser Name wird verwendet, um bei Verwendung der Cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** und **Remove-ComplianceSecurityFilter** einen Filter zu identifizieren.  <br/> |
| _Filter_ <br/> | Der Parameter _Filters_ gibt die Suchkriterien für den Compliance-Sicherheitsfilter an. Sie können drei unterschiedliche Filtertypen erstellen:  <br/><br/> **Post Fach Filterung:** Dieser Filtertyp gibt die Postfächer an, die die zugeordneten Benutzer (durch den Parameter _Users_ angegeben) durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei _MailboxPropertyName_ eine Postfacheigenschaft angibt, die zum Bereich der Postfächer verwendet wird, die durchsucht werden können. Beispielsweise würde der Post Fach `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` Filter dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Postfächer durchsuchen, deren Wert "OttawaUsers" in der CustomAttribute10-Eigenschaft aufweist.  <br/>  Jede unterstützte filterbare Empfänger Eigenschaft kann für die _MailboxPropertyName_ -Eigenschaft verwendet werden. Eine Liste der unterstützten Eigenschaften finden Sie unter [Filterbare Eigenschaften für den Parameter "-RecipientFilter"](https://go.microsoft.com/fwlink/p/?LinkId=784903).  <br/><br/> **Filterung von Postfachinhalten:** Diese Art von Filter wird auf die Inhalte angewendet, die durchsucht werden können. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName: Value_, wobei _SearchablePropertyName_ eine KQL-Eigenschaft (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Beispielsweise würde der Filter `MailboxContent_recipients:contoso.com` für den Postfachinhalt dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Nachrichten ermöglichen, die an Empfänger in der contoso.com-Domäne gesendet wurden.  <br/>  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md). <br/> <br/> **Wichtig:**  Ein einzelner Suchfilter kann keinen Post Fach Filter und keinen Filter für den Postfachinhalt enthalten. Um diese in einem einzelnen Filter zu kombinieren, müssen Sie eine [Filterliste](#using-a-filters-list-to-combine-filter-types)verwenden.  Ein Filter kann jedoch eine komplexere Abfrage desselben Typs enthalten. Zum Beispiel  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`.  <br/><br/> **Filterung von Website-und Websiteinhalten:** Es gibt zwei SharePoint-und OneDrive für Unternehmen-Website bezogene Filter, die Sie verwenden können, um anzugeben, welche Website-oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Diese beiden Filter sind austauschbar. `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` Geben Sie beispielsweise `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` die gleichen Ergebnisse zurück. Um Sie bei der Identifizierung eines Filters zu unterstützen, können Sie `Site_` zum Angeben von Website bezogenen Eigenschaften (beispielsweise eine Website-URL) `SiteContent_` und zum Angeben von inhaltsbezogenen Eigenschaften (beispielsweise Dokumenttypen) verwenden. Beispielsweise würde der Filter `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Inhalten https://contoso.sharepoint.com/sites/doctors in der Websitesammlung ermöglichen. Der Filter `"SiteContent_FileExtension -eq 'docx'"` würde dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Word-Dokumenten (Word 2007 und höher) ermöglichen.  <br/><br/>  Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Eigenschaften, die mit einem **Ja** in der Spalte **abgefragt** markiert sind, können zum Erstellen eines Website-oder Websiteinhalts Filters verwendet werden.  <br/><br/> **Wichtig:** Sie müssen einen Such Berechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzerinhalts Speicherorte in einem bestimmten Office 365 Dienst durchsuchen (beispielsweise verhindern, dass ein Benutzer ein beliebiges Exchange-Postfach oder eine SharePoint-Website durchsucht). Mit anderen Worten: das Erstellen eines Such Berechtigungs Filters, mit dem ein Benutzer alle SharePoint-Websites in der Organisation durchsuchen kann, hindert diesen Benutzer nicht daran, Postfächer zu durchsuchen. Damit SharePoint-Administratoren nur SharePoint-Websites durchsuchen können, müssen Sie beispielsweise einen Filter erstellen, der verhindert, dass die Postfächer durchsucht werden. Um Exchange-Administratoren nur das Durchsuchen von Postfächern zu gestatten, müssen Sie einen Filter erstellen, der verhindert, dass diese Websites durchsuchen.           |
| _Benutzer_ <br/> |Der Parameter _Users_ gibt die Benutzer an, die diesen Filter auf Ihre Inhaltssuche angewendet bekommen. Identifizieren Sie die Benutzer durch ihren Aliasnamen oder die primäre SMTP-Adresse. Sie können mehrere durch Kommas getrennte Werte angeben, oder Sie können den Filter allen Benutzern zuweisen, indem Sie den Wert **Alle** angeben.  <br/> Sie können auch den Parameter _Users_ verwenden, um eine Sicherheits & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können mithilfe des Parameters _Users_ diese Rollengruppe angeben (mithilfe der Name-Eigenschaft der Rollengruppe) und dann mithilfe des Parameters _Filter_ zulassen, dass nur Postfächer in den USA durchsucht werden.  <br/> Sie können mit diesem Parameter keine Verteilergruppen angeben.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Verwenden einer Filterliste zum Kombinieren von Filtertypen

Eine *Filterliste* ist ein Filter, der einen Post Fach Filter und einen Website Filter enthält, der durch ein Komma getrennt ist. Die Verwendung einer Filterliste ist die einzige unterstützte Methode zum Kombinieren verschiedener Filtertypen. Beachten Sie im folgenden Beispiel, dass das **Postfach** und die **Website** Filter durch ein Komma getrennt werden:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Wenn ein Filter, der eine Filterliste enthält, während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Such Berechtigungsfilter aus der Liste Filter erstellt: eine für jeden Filter, der durch ein Komma getrennt ist. Im vorherigen Beispiel würde also ein Post Fach Such Berechtigungsfilter und ein Website Such Berechtigungsfilter erstellt. 

Eine Alternative zur Verwendung einer Filterliste besteht darin, zwei separate Such Berechtigungsfilter zu erstellen. Im vorherigen Beispiel würden Sie also einen Filter für das Postfachattribut und einen Filter für das Website Attribut erstellen. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Such Berechtigungsfilter ist eine Frage der Präferenz.

Beachten Sie die folgenden Aspekte bei der Verwendung einer Filterliste:

- Sie müssen eine Filterliste verwenden, um einen Filter zu erstellen, der einen **Post Fach** Filter und einen **MailboxContent** -Filter enthält. 

- Wie bereits erwähnt, müssen Sie keine Filterliste verwenden, um eine **Website** und einen **SiteContent** -Filter in einen einzelnen Such Berechtigungsfilter einzuschließen. Sie können beispielsweise **Standort** -und **SiteContent** -Filter mit einem **-oder-** Operator kombinieren.

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Jede Komponente einer Filterliste kann eine komplexe Filtersyntax enthalten. Die Filter "Postfach" und "Website" können beispielsweise mehrere Filter enthalten, die durch einen **-oder-** Operator getrennt sind:

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Beispiele für das Erstellen von Such Berechtigungs Filtern

Nachfolgend finden Sie Beispiele für die Verwendung des **New-ComplianceSecurityFilter**-Cmdlets zum Erstellen eines Berechtigungsfilters für die Suche. 
  
In diesem Beispiel kann der Benutzer annb@contoso.com nur für Postfächer in Kanada alle Inhalts Suchaktionen ausführen. Dieser Filter enthält die dreistellige Landeskennzahl für Kanada gemäß ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In diesem Beispiel können die "donh"-und "suzanf"-Benutzer nur die Postfächer durchsuchen, die den Wert "Marketing" für die CustomAttribute1-Postfacheigenschaft aufweisen.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

In diesem Beispiel können Mitglieder der Rollengruppe „US Discovery Managers“ alle Inhaltssuchvorgänge nur für Postfächer in den USA durchführen. Dieser Filter enthält die dreistellige Landeskennzahl für die USA gemäß ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

In diesem Beispiel können Mitglieder der Rollengruppe "eDiscovery-Manager" nur die Postfächer der Mitglieder der Verteilergruppe "Ottawa Users" Durchsuchen. 
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In diesem Beispiel wird verhindert, dass Benutzer Inhalt aus den Postfächern der Mitglieder der Verteilergruppe „Executive Team“ löschen.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In diesem Beispiel können Mitglieder der benutzerdefinierten Rollengruppe OneDrive eDiscovery Managers nur nach Inhalten in OneDrive für Unternehmen Speicherorten in der Organisation suchen.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Um Benutzer auf die Suche bestimmter Websites einzuschränken, `Site_Path`verwenden Sie den Filter, wie im vorherigen Beispiel gezeigt. Die `Site_Site` Verwendung von funktioniert nicht. 
  
In diesem Beispiel kann der Benutzer Inhaltssuchvorgänge nur für E-Mail-Nachrichten durchführen, die während des Kalenderjahres 2015 gesendet wurden.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Ähnlich wie im vorherigen Beispiel kann der Benutzer in diesem Beispiel die Inhaltssuchvorgänge nur für Dokumente durchführen, die zuletzt im Kalenderjahr 2015 geändert wurden.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

In diesem Beispiel wird verhindert, dass Mitglieder der Rollengruppe "OneDrive Discovery Managers" Inhalts Suchaktionen für ein beliebiges Postfach in der Organisation ausführen. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In diesem Beispiel wird verhindert, dass Personen in der Organisation nach e-Mail-Nachrichten suchen, die von Janets oder Sarad gesendet oder empfangen wurden.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In diesem Beispiel wird eine Filterliste verwendet, um Post Fach-und Website Filter zu kombinieren.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

Das **Get-ComplianceSecurityFilter** wird verwendet, um eine Liste von Such Berechtigungs Filtern zurückzugeben. Verwenden Sie den _Filter_ Name-Parameter, um Informationen für einen bestimmten Suchfilter zurückzugeben. 
  
## <a name="set-compliancesecurityfilter"></a>Gruppe-ComplianceSecurityFilter

Das **ComplianceSecurityFilter-Feature** wird verwendet, um einen vorhandenen Such Berechtigungsfilter zu ändern. Der einzige erforderliche Parameter ist _Filter_Name. 
  
|**Parameter**|**Beschreibung**|
|:-----|:-----|
| _Action_| Der Parameter _Action_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich: <br/><br/> **Export:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird bei der Vorschau der Suchergebnisse angewendet.  <br/> **Säuberung:** Der Filter wird angewendet, wenn Suchergebnisse bereinigt werden.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **All:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_|Der Parameter _Filter_ Name gibt den Namen des Berechtigungs Filters an. |
| _Filter_| Der Parameter _Filters_ gibt die Suchkriterien für den Compliance-Sicherheitsfilter an. Sie können zwei verschiedene Arten von Filtern erstellen: <br/><br/>**Post Fach Filterung:** Dieser Filtertyp gibt die Postfächer an, die die zugeordneten Benutzer (durch den Parameter _Users_ angegeben) durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei _MailboxPropertyName_ eine Postfacheigenschaft angibt, die zum Bereich der Postfächer verwendet wird, die durchsucht werden können. Beispielsweise würde der Post Fach `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` Filter dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Postfächer durchsuchen, deren Wert "OttawaUsers" in der CustomAttribute10-Eigenschaft aufweist.  Jede unterstützte filterbare Empfänger Eigenschaft kann für die _MailboxPropertyName_ -Eigenschaft verwendet werden. Eine Liste der unterstützten Eigenschaften finden Sie unter [Filterbare Eigenschaften für den Parameter "-RecipientFilter"](https://go.microsoft.com/fwlink/p/?LinkId=784903). <br/><br/>**Filterung von Postfachinhalten:** Diese Art von Filter wird auf die Inhalte angewendet, die durchsucht werden können. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName: Value_, wobei _SearchablePropertyName_ eine KQL-Eigenschaft (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Beispielsweise würde der Filter `MailboxContent_recipients:contoso.com` für den Postfachinhalt dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Nachrichten ermöglichen, die an Empfänger in der contoso.com-Domäne gesendet wurden.  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Keyword-Abfragen für die Inhaltssuche](keyword-queries-and-search-conditions.md). <br/><br/>**Filterung von Website-und Websiteinhalten:** Es gibt zwei SharePoint-und OneDrive für Unternehmen-Website bezogene Filter, die Sie verwenden können, um anzugeben, welche Website-oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>Diese beiden Filter sind austauschbar. Zum Beispiel `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` und `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` gibt dieselben Ergebnisse zurück. Um Sie bei der Identifizierung eines Filters zu unterstützen, können Sie `Site_` zum Angeben von Website bezogenen Eigenschaften (beispielsweise eine Website-URL) `SiteContent_` und zum Angeben von inhaltsbezogenen Eigenschaften (beispielsweise Dokumenttypen) verwenden. Beispielsweise würde der Filter `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Inhalten https://contoso.spoppe.com/sites/doctors in der Websitesammlung ermöglichen. Der Filter `"SiteContent_FileExtension -eq 'docx'"` würde dem Benutzer, dem dieser Filter zugewiesen wurde, nur die Suche nach Word-Dokumenten (Word 2007 und höher) ermöglichen.  <br/><br/>Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Eigenschaften, die mit einem **Ja** in der Spalte **abgefragt** markiert sind, können zum Erstellen eines Website-oder Websiteinhalts Filters verwendet werden. <br/><br/>          |
| _Benutzer_|Der Parameter _Users_ gibt die Benutzer an, die diesen Filter auf Ihre Inhaltssuche angewendet bekommen. Da es sich um eine mehrwertige Eigenschaft handelt, wird durch Angeben eines Benutzers oder einer Benutzergruppe mit diesem Parameter die vorhandene Liste der Benutzer überschrieben. In den folgenden Beispielen finden Sie die Syntax zum Hinzufügen und Entfernen ausgewählter Benutzer. <br/><br/>Sie können auch den Parameter _Users_ verwenden, um eine Sicherheits & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können mithilfe des Parameters _Users_ diese Rollengruppe angeben (mithilfe der Name-Eigenschaft der Rollengruppe) und dann mithilfe des Parameters _Filter_ zulassen, dass nur Postfächer in den USA durchsucht werden. <br/><br/>Sie können mit diesem Parameter keine Verteilergruppen angeben. |

## <a name="examples-of-changing-search-permissions-filters"></a>Beispiele für das Ändern von Such Berechtigungs Filtern

In diesen Beispielen wird gezeigt, wie Sie mithilfe der Cmdlets **Get-ComplianceSecurityFilter** und **setComplianceSecurityFilter** einen Benutzer der vorhandenen Liste der Benutzer hinzufügen oder daraus entfernen, denen der Filter zugewiesen ist. Wenn Sie einem Filter Benutzer hinzufügen oder Benutzer daraus entfernen, geben Sie den Benutzer durch seine SMTP-Adresse an. 
  
In diesem Beispiel wird dem Filter ein Benutzer hinzugefügt.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

In diesem Beispiel wird ein Benutzer aus dem Filter entfernt.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

Die **Remove-ComplianceSecurityFilter** wird verwendet, um einen Suchfilter zu löschen. Verwenden Sie den _Filter_ Name-Parameter, um den Filter anzugeben, den Sie löschen möchten. 
  
## <a name="more-information"></a>Weitere Informationen

- **Wie funktionieren Berechtigungsfilter für die Suche?** Der Berechtigungsfilter wird der Suchabfrage hinzugefügt, wenn eine Inhaltssuche ausgeführt wird. Der Berechtigungsfilter wird durch den booleschen Operator **und** mit der Suchabfrage verknüpft. Beispielsweise verfügen Sie über einen Berechtigungsfilter, mit dem Bob alle Suchaktionen für die Postfächer von Mitgliedern der Arbeits Verteilungsgruppe durchführen kann. Anschließend führt Bob eine Inhaltssuche für alle Postfächer in der Organisation mit der Such `sender:jerry@adatum.com`Abfrage aus. Da der Berechtigungsfilter und die Suchabfrage logischerweise durch einen **and-** Operator kombiniert werden, gibt die Suche alle Nachrichten zurück, die von Jerry@adatum.com an ein beliebiges Mitglied der Verteilergruppe "Arbeiter" gesendet wurden. 
    
- **Was passiert, wenn Sie über mehrere Berechtigungsfilter für die Suche verfügen? ** Bei einer Inhaltssuchabfrage werden mehrere Berechtigungsfilter durch den booleschen Operator **ODER** miteinander verknüpft. Daher werden Ergebnisse zurückgegeben, wenn nur einer der Filter zutrifft. Bei einer Inhaltssuche werden dann alle (mit den **ODER**-Operatoren verknüpften) Filter durch den Operator **UND** mit der Suchabfrage kombiniert. Nehmen wir das vorherige Beispiel, in dem Bob durch einen Suchfilter nur die Postfächer der Mitglieder der Verteilergruppe "Arbeiter" durchsuchen kann. Wir erstellen dann einen weiteren Filter, der verhindert, dass Bob das Postfach von Phil („Mailbox_Alias - ne 'Phil'“) durchsuchen kann. Außerdem nehmen wir an, dass Phil ein Mitglied der Gruppe „Worker“ ist. Wenn Bob eine Inhaltssuche (aus dem vorherigen Beispiel) für alle Postfächer in der Organisation ausführt, werden Suchergebnisse für das Postfach von Phil zurückgegeben, obwohl Sie Filter angewendet haben, um zu verhindern, dass Bob Phils Postfach durchsucht. Dies liegt daran, dass der erste Filter, der Bob erlaubt, die Gruppe „Worker“ zu durchsuchen „wahr“ ist. Da Phil Mitglied der Gruppe „Worker“ ist, kann Bob das Postfach von Phil durchsuchen. 
    
- **Funktioniert die Filterung der Suchberechtigungen für inaktive Postfächer?** Ja, Sie können mithilfe von Postfach-und Postfachinhalts Filtern einschränken, wer inaktive Postfächer in Ihrer Organisation durchsuchen kann. Wie ein reguläres Postfach muss ein inaktives Postfach mit der Recipient-Eigenschaft konfiguriert werden, die zum Erstellen eines Berechtigungs Filters verwendet wird. Bei Bedarf können Sie den Befehl **Get-Mailbox-InactiveMailboxOnly** verwenden, um die Eigenschaften inaktiver Postfächer anzuzeigen. Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Office 365](create-and-manage-inactive-mailboxes.md).
    
- **Funktioniert die Filterung der Suchberechtigungen für Öffentliche Ordner?** Nein. Wie bereits erläutert, kann die Such Berechtigungs Filterung nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in Exchange durchsuchen kann. Beispielsweise können Elemente an öffentlichen Ordner Standorten nicht von den Suchergebnissen durch einen Berechtigungsfilter ausgeschlossen werden. 
    
- **Verhindert das Durchsuchen von Benutzern, dass alle inhaltsspeicherorte in einem bestimmten Dienst durchsucht werden, auch das Durchsuchen von Inhaltsspeicherorten in einem anderen Dienst?** Nein. Wie bereits erläutert, müssen Sie einen Such Berechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzerinhalts Speicherorte in einem bestimmten Office 365 Dienst durchsuchen (beispielsweise verhindern, dass ein Benutzer ein beliebiges Exchange-Postfach oder eine SharePoint-Website durchsucht). Mit anderen Worten: das Erstellen eines Such Berechtigungs Filters, mit dem ein Benutzer alle SharePoint-Websites in der Organisation durchsuchen kann, hindert diesen Benutzer nicht daran, Postfächer zu durchsuchen. Damit SharePoint-Administratoren nur SharePoint-Websites durchsuchen können, müssen Sie beispielsweise einen Filter erstellen, der verhindert, dass die Postfächer durchsucht werden. Um Exchange-Administratoren nur das Durchsuchen von Postfächern zu gestatten, müssen Sie einen Filter erstellen, der verhindert, dass diese Websites durchsuchen.
