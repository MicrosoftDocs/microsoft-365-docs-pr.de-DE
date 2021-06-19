---
title: Konfigurieren der Berechtigungsfilterung für die Compliancesuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
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
description: Verwenden Sie die Inhaltssuche-Berechtigungsfilterung, damit ein eDiscovery-Manager nur eine Teilmenge von Postfächern und Websites in Ihrer Organisation durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 654df250fb6816c215a3a3e28bd6456c6f88ab6e
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022474"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Konfigurieren der Berechtigungsfilterung für die Compliancesuche

Sie können die Suchberechtigungsfilterung verwenden, damit ein eDiscovery-Manager nur eine Teilmenge von Postfächern und Websites in Ihrer Organisation durchsuchen kann. Sie können Berechtigungsfilter auch verwenden, um demselben eDiscovery-Managers zu ermöglichen, nur nach Postfach- oder Websiteinhalt zu suchen, der bestimmten Suchkriterien entspricht. Sie können einem Discovery-Manager beispielsweise ermöglichen, nur die Postfächer der Benutzer an einem bestimmten Standort oder in einer bestimmten Abteilung zu durchsuchen. Dazu erstellen Sie einen Filter, der einen unterstützten Empfängerfilter verwendet, um zu begrenzen, welche Postfächer ein bestimmter Benutzer oder eine Gruppe von Benutzern durchsuchen kann. Sie können auch einen Filter erstellen, der angibt, nach welchem Postfachinhalt ein Benutzer suchen kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Nachrichteneigenschaft verwendet. Auf ähnliche Weise können Sie zulassen, dass ein eDiscovery-Manager nur bestimmte SharePoint Websites in Ihrer Organisation durchsucht. Hierzu erstellen Sie einen Filter, der einschränkt, welche Website durchsucht werden kann. Sie können auch einen Filter erstellen, der angibt, welcher Websiteinhalt durchsucht werden kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Website-Eigenschaft verwendet.

Sie können die Suchberechtigungsfilterung auch verwenden, um logische Grenzen (als *Compliancegrenzen* bezeichnet) innerhalb einer Organisation zu erstellen, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, SharePoint Websites und OneDrive Konten) steuern, die bestimmte eDiscovery-Manager durchsuchen können. Weitere Informationen finden Sie unter [Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen in Office 365.](tagging-and-assessment-in-advanced-ediscovery.md)
  
Die Filterung von Suchberechtigungen wird von der Inhaltssuche im Security & Compliance Center unterstützt. Mit diesen vier Cmdlets können Sie Suchberechtigungsfilter konfigurieren und verwalten:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Anforderungen zum Konfigurieren der Berechtigungsfilterung

- Um die Compliancesicherheitsfilter-Cmdlets auszuführen, müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Sie müssen eine Verbindung mit Exchange Online und Security & Compliance Center PowerShell herstellen, um die Cmdlets für compliancesicherheitsfilter zu verwenden. Dies ist erforderlich, da diese Cmdlets Zugriff auf Postfacheigenschaften erfordern, weshalb Sie eine Verbindung mit Exchange Online PowerShell herstellen müssen. Sehen Sie sich die Schritte im nächsten Abschnitt an.

- Weitere Informationen über Berechtigungsfilter für die Suche finden Sie im Abschnitt [More information](#more-information).

- Die Filterung von Suchberechtigungen gilt für inaktive Postfächer, was bedeutet, dass Sie die Postfach- und Postfachinhaltsfilterung verwenden können, um zu beschränken, wer ein inaktives Postfach durchsuchen kann. Weitere Informationen zum Filtern von Berechtigungen und inaktiven Postfächern finden Sie im Abschnitt ["Weitere Informationen".](#more-information)

- Die Suchberechtigungsfilterung kann nicht verwendet werden, um zu beschränken, wer öffentliche Ordner in Exchange durchsuchen kann.

- Es gibt keine Beschränkung für die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können. Die Suchleistung wird jedoch beeinträchtigt, wenn mehr als 100 Suchberechtigungsfilter vorhanden sind. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzigen Filter kombinieren, wann immer möglich.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Verbinden zu Exchange Online und Security & Compliance Center PowerShell in einer einzigen Sitzung

Bevor Sie das Skript in diesem Abschnitt erfolgreich ausführen können, müssen Sie das Exchange Online PowerShell V2-Modul herunterladen und installieren. Weitere Informationen finden Sie unter ["Informationen zum Exchange Online PowerShell V2-Moduls".](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix **.ps1** verwenden. Sie können sie beispielsweise in einer Datei mit dem Namen **ConnectEXO-SCC.ps1** speichern.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öffnen Sie auf Ihrem lokalen Computer Windows PowerShell, wechseln Sie zu dem Ordner, in dem sich das Skript befindet, das Sie im vorherigen Schritt erstellt haben, und führen Sie das Skript aus. Zum Beispiel:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Woher wissen Sie, dass dieses Verfahren erfolgreich war? Nachdem Sie das Skript ausgeführt haben, werden Cmdlets aus Exchange Online und Security & Compliance PowerShell in Ihre lokale Windows PowerShell Sitzung importiert. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein schneller Test besteht darin, ein Cmdlet für Exchange Online und Security & Compliance Center auszuführen. Sie können z. B. **"Get-Mailbox"** und **"Get-ComplianceSearch"** ausführen.

Informationen zur Problembehandlung von PowerShell-Verbindungsfehlern finden Sie unter:

- [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Der **New-ComplianceSecurityFilter** wird verwendet, um einen Suchberechtigungsfilter zu erstellen. In der folgenden Tabelle werden die Parameter für dieses Cmdlet beschrieben. Alle Parameter sind erforderlich, um einen Compliancesicherheitsfilter zu erstellen.
  
| Parameter | Beschreibung |
|:-----|:-----|
| _Action_ <br/> | Der  _Parameter Action_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich:  <br/><br/> **Exportieren Sie:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird bei der Vorschau der Suchergebnisse angewendet.  <br/> **Löschen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_ <br/> |Der  _Parameter FilterName_ gibt den Namen des Berechtigungsfilters an. Dieser Name wird verwendet, um bei Verwendung der Cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** und **Remove-ComplianceSecurityFilter** einen Filter zu identifizieren.  <br/> |
| _Filters_ <br/> | Der Parameter  _Filters_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können drei unterschiedliche Filtertypen erstellen:  <br/><br/> **Postfach- oder OneDrive filterung:** Dieser Filtertyp gibt die Postfächer und OneDrive Konten an, die die zugewiesenen Benutzer (angegeben durch den Parameter _"Users")_ durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei _MailboxPropertyName_ eine Postfacheigenschaft angibt, die für den Bereich der Postfächer und OneDrive Konten verwendet wird, die durchsucht werden können. Beispielsweise ermöglicht der Postfachfilter `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` dem Benutzer, dem dieser Filter zugewiesen ist, nur die Postfächer und OneDrive Konten zu durchsuchen, die den Wert "OneDrive Users" in der CustomAttribute10-Eigenschaft aufweisen.  <br/>  Jede unterstützte filterbare Empfängereigenschaft kann für die  _MailboxPropertyName-Eigenschaft_ verwendet werden. Eine Liste der unterstützten Eigenschaften finden Sie unter ["Filterbare Eigenschaften" für den Parameter "-RecipientFilter".](/powershell/exchange/recipientfilter-properties)  <br/><br/> **Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName:-Wert,_ wobei  _SearchablePropertyName_ eine KQL-Eigenschaft (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Beispielsweise würde der Postfachinhaltsfilter  `MailboxContent_recipients:contoso.com` dem Benutzer, dem dieser Filter zugewiesen ist, erlauben, nur nach Nachrichten zu suchen, die an Empfänger in der contoso.com Domäne gesendet werden.  <br/>  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche.](keyword-queries-and-search-conditions.md) <br/> <br/> **Wichtig:**  Ein einzelner Suchfilter kann keinen Postfachfilter und keinen Postfachinhaltsfilter enthalten. Um diese in einem einzigen Filter zu kombinieren, müssen Sie eine [Filterliste](#using-a-filters-list-to-combine-filter-types)verwenden.  Ein Filter kann jedoch eine komplexere Abfrage desselben Typs enthalten. Zum Beispiel  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`.  <br/><br/> **Website- und Websiteinhaltsfilterung:** Es gibt zwei SharePoint und OneDrive for Business websitebezogenen Filter, mit denen Sie angeben können, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Diese beiden Filter sind austauschbar. Geben Sie beispielsweise  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` dieselben Ergebnisse zurück. Um jedoch zu ermitteln, was ein Filter bewirkt, können Sie  `Site_` websitebezogene Eigenschaften (z. B. eine Website-URL) und  `SiteContent_` inhaltsbezogene Eigenschaften (z. B. Dokumenttypen) angeben. Der Filter würde beispielsweise  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` zulassen, dass der diesem Filter zugewiesene Benutzer nur nach Inhalten in der https://contoso.sharepoint.com/sites/doctors Websitesammlung sucht. Mit dem Filter  `"SiteContent_FileExtension -eq 'docx'"` kann der diesem Filter zugewiesene Benutzer nur nach Word-Dokumenten (Word 2007 und höher) suchen.  <br/><br/>  Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint.](/SharePoint/technical-reference/crawled-and-managed-properties-overview) Eigenschaften, die in der Spalte **Abfragbar** mit dem Wert **Ja** gekennzeichnet sind, können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden.  <br/><br/> **Wichtig:** Sie müssen einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer Exchange Postfach oder eine SharePoint Website durchsucht). Mit anderen Worten: Das Erstellen eines Suchberechtigungsfilters, der es einem Benutzer ermöglicht, alle SharePoint Websites in der Organisation zu durchsuchen, hindert diesen Benutzer nicht daran, Postfächer zu durchsuchen. Damit SharePoint Administratoren beispielsweise nur SharePoint Websites durchsuchen können, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um Exchange Administratoren nur das Durchsuchen von Postfächern zu gestatten, müssen Sie einen Filter erstellen, der sie daran hindert, Websites zu durchsuchen.           |
| _Users_ <br/> |Der Parameter  _"Users"_ gibt die Benutzer an, die diesen Filter auf ihre Inhaltssuchen anwenden. Identifizieren Sie die Benutzer durch ihren Aliasnamen oder die primäre SMTP-Adresse. Sie können mehrere durch Kommas getrennte Werte angeben, oder Sie können den Filter allen Benutzern zuweisen, indem Sie den Wert **Alle** angeben.  <br/> Sie können auch den Parameter  _"Users"_ verwenden, um eine Sicherheits- & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den Parameter  _"Users"_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Name-Eigenschaft der Rollengruppe) und dann den Parameter  _"Filter"_ verwenden, um nur Postfächer in den USA zu durchsuchen.  <br/> Sie können mit diesem Parameter keine Verteilergruppen angeben.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Verwenden einer Filterliste zum Kombinieren von Filtertypen

Eine *Filterliste* ist ein Filter, der einen Postfachfilter und einen durch ein Komma getrennten Websitefilter enthält. Die Verwendung einer Filterliste ist die einzige unterstützte Methode zum Kombinieren verschiedener Filtertypen. Beachten Sie im folgenden Beispiel, dass ein Komma die **Postfach-** und **Websitefilter** trennt:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Wenn ein Filter, der eine Filterliste enthält, während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Suchberechtigungsfilter aus der Filterliste erstellt: einer für jeden Filter, der durch ein Komma getrennt ist. Im vorherigen Beispiel wurden also ein Filter für Postfachsuchberechtigungen und ein Suchberechtigungsfilter für die Website erstellt. 

Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern. Im vorherigen Beispiel haben Sie also einen Filter für das Postfachattribut und einen Filter für das Websiteattribut erstellt. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine Frage der Präferenz.

Beachten Sie bei der Verwendung einer Filterliste folgende Punkte:

- Sie müssen eine Filterliste verwenden, um einen Filter zu erstellen, der einen **Postfachfilter** und einen **MailboxContent-Filter** enthält.

- Jede Komponente einer Filterliste kann eine komplexe Filtersyntax enthalten. Beispielsweise können die Postfach- und Websitefilter mehrere Filter enthalten, die durch einen **-or-Operator** getrennt sind:

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Beispiele für das Erstellen von Suchberechtigungsfiltern

Nachfolgend finden Sie Beispiele für die Verwendung des **New-ComplianceSecurityFilter**-Cmdlets zum Erstellen eines Berechtigungsfilters für die Suche. 
  
In diesem Beispiel kann der Benutzer annb@contoso.com alle Inhaltssuchaktionen nur für Postfächer in Kanada ausführen. Dieser Filter enthält die dreistellige Landeskennzahl für Kanada gemäß ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In diesem Beispiel können die Benutzer „donh“ und „suzanf“ nur die Postfächer durchsuchen, die den Wert „Marketing“ für die Postfacheigenschaft „CustomAttribute1“ aufweisen.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

In diesem Beispiel können Mitglieder der Rollengruppe „US Discovery Managers“ alle Inhaltssuchvorgänge nur für Postfächer in den USA durchführen. Dieser Filter enthält die dreistellige Landeskennzahl für die USA gemäß ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

In diesem Beispiel können Mitglieder der Rollengruppe "eDiscovery-Manager" nur die Postfächer der Mitglieder der Verteilergruppe "Benutzer" durchsuchen. Das Cmdlet Get-DistributionGroup in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Benutzer" zu finden.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In diesem Beispiel wird verhindert, dass Benutzer Inhalt aus den Postfächern der Mitglieder der Verteilergruppe „Executive Team“ löschen. Das Cmdlet Get-DistributionGroup in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Executive Team" zu finden.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In diesem Beispiel können Mitglieder der benutzerdefinierten Rollengruppe OneDrive eDiscovery-Manager nur an OneDrive for Business Speicherorten in der Organisation nach Inhalten suchen.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Um Benutzer auf die Suche nach bestimmten Websites zu beschränken, verwenden Sie den Filter  `Site_Path` , wie im vorherigen Beispiel gezeigt. Die Verwendung  `Site_Site` funktioniert nicht. 
  
In diesem Beispiel kann der Benutzer Inhaltssuchvorgänge nur für E-Mail-Nachrichten durchführen, die während des Kalenderjahres 2015 gesendet wurden.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Ähnlich wie im vorherigen Beispiel kann der Benutzer in diesem Beispiel die Inhaltssuchvorgänge nur für Dokumente durchführen, die zuletzt im Kalenderjahr 2015 geändert wurden.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

In diesem Beispiel wird verhindert, dass Mitglieder der Rollengruppe "OneDrive-Discovery-Manager" Inhaltssuchaktionen für ein beliebiges Postfach in der Organisation ausführen. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In diesem Beispiel wird verhindert, dass jemand in der Organisation nach E-Mail-Nachrichten sucht, die von Janets oder Sarad gesendet oder empfangen wurden.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In diesem Beispiel wird eine Filterliste verwendet, um Postfach- und Websitefilter zu kombinieren.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

Der **Get-ComplianceSecurityFilter** wird verwendet, um eine Liste von Suchberechtigungsfiltern zurückzugeben. Verwenden Sie den  _Parameter FilterName,_ um Informationen für einen bestimmten Suchfilter zurückzugeben. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

Der **Set-ComplianceSecurityFilter** wird verwendet, um einen vorhandenen Suchberechtigungsfilter zu ändern. Der einzige erforderliche Parameter ist  _FilterName_. 
  
| Parameter | Beschreibung |
|:-----|:-----|
| _Action_| Der  _Parameter Action_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich: <br/><br/> **Exportieren Sie:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird bei der Vorschau der Suchergebnisse angewendet.  <br/> **Löschen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_|Der  _Parameter FilterName_ gibt den Namen des Berechtigungsfilters an. |
| _Filters_| Der Parameter  _Filters_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können zwei verschiedene Filtertypen erstellen: <br/><br/>**Postfach- und OneDrive filterung:** Dieser Filtertyp gibt die Postfächer und OneDrive Konten an, die die zugewiesenen Benutzer (angegeben durch den Parameter _"Users")_ durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei  _MailboxPropertyName_ eine Postfacheigenschaft angibt, die für den Bereich der Postfächer verwendet wird, die durchsucht werden können. Beispielsweise würde der Postfachfilter  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` dem Benutzer, dem dieser Filter zugewiesen wurde, erlauben, nur die Postfächer zu durchsuchen, die den Wert "CsvUsers" in der CustomAttribute10-Eigenschaft aufweisen.  Jede unterstützte filterbare Empfängereigenschaft kann für die  _MailboxPropertyName-Eigenschaft_ verwendet werden. Eine Liste der unterstützten Eigenschaften finden Sie unter ["Filterbare Eigenschaften" für den Parameter "-RecipientFilter".](/powershell/exchange/recipientfilter-properties) <br/><br/>**Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName:value_, wobei  _SearchablePropertyName_ eine KQL-Eigenschaft (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Beispielsweise würde der Postfachinhaltsfilter  `MailboxContent_recipients:contoso.com` dem Diesem Filter zugewiesenen Benutzer erlauben, nur nach Nachrichten zu suchen, die an Empfänger in der contoso.com Domäne gesendet wurden.  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Stichwortabfragen für die Inhaltssuche.](keyword-queries-and-search-conditions.md) <br/><br/>**Website- und Websiteinhaltsfilterung:** Es gibt zwei SharePoint und OneDrive for Business websitebezogene Filter, mit denen Sie angeben können, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Diese beiden Filter sind austauschbar. Gibt beispielsweise  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` dieselben Ergebnisse zurück. Um jedoch zu ermitteln, was ein Filter bewirkt, können Sie  `Site_` websitebezogene Eigenschaften (z. B. eine Website-URL) und  `SiteContent_` inhaltsbezogene Eigenschaften (z. B. Dokumenttypen) angeben. Der Filter würde beispielsweise  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` zulassen, dass der diesem Filter zugewiesene Benutzer nur nach Inhalten in der https://contoso.spoppe.com/sites/doctors Websitesammlung sucht. Mit dem Filter  `"SiteContent_FileExtension -eq 'docx'"` kann der diesem Filter zugewiesene Benutzer nur nach Word-Dokumenten (Word 2007 und höher) suchen.  <br/><br/>Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint.](/SharePoint/technical-reference/crawled-and-managed-properties-overview) Eigenschaften, die in der Spalte **Abfragbar** mit dem Wert **Ja** gekennzeichnet sind, können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden. <br/><br/>          |
| _Users_|Der Parameter  _"Users"_ gibt die Benutzer an, die diesen Filter auf ihre Inhaltssuchen anwenden. Da es sich um eine Mehrwerteigenschaft handelt, wird durch Angeben eines Benutzers oder einer Benutzergruppe mit diesem Parameter die vorhandene Benutzerliste überschrieben. In den folgenden Beispielen finden Sie die Syntax zum Hinzufügen und Entfernen ausgewählter Benutzer. <br/><br/>Sie können auch den Parameter  _"Users"_ verwenden, um eine Sicherheits- & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den Parameter  _"Users"_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Name-Eigenschaft der Rollengruppe) und dann den Parameter  _"Filter"_ verwenden, um nur Postfächer in den USA zu durchsuchen. <br/><br/>Sie können mit diesem Parameter keine Verteilergruppen angeben. |

## <a name="examples-of-changing-search-permissions-filters"></a>Beispiele für das Ändern von Suchberechtigungsfiltern

In diesen Beispielen wird gezeigt, wie Sie die Cmdlets **"Get-ComplianceSecurityFilter"** und **"Set-ComplianceSecurityFilter"** verwenden, um einen Benutzer zur vorhandenen Liste der Benutzer hinzuzufügen oder zu entfernen, denen der Filter zugewiesen ist. Wenn Sie einem Filter Benutzer hinzufügen oder Benutzer daraus entfernen, geben Sie den Benutzer durch seine SMTP-Adresse an. 
  
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

**Der Remove-ComplianceSecurityFilter** wird verwendet, um einen Suchfilter zu löschen. Verwenden Sie den  _Parameter FilterName,_ um den Filter anzugeben, den Sie löschen möchten. 
  
## <a name="more-information"></a>Weitere Informationen

- **Wie funktionieren Berechtigungsfilter für die Suche?** Der Berechtigungsfilter wird der Suchabfrage hinzugefügt, wenn eine Inhaltssuche ausgeführt wird. Der Berechtigungsfilter wird mit der Suchabfrage durch den Operator **AND** Boolean verknüpft. Sie verfügen beispielsweise über einen Berechtigungsfilter, mit dem Bob alle Suchaktionen für die Postfächer von Mitgliedern der Verteilergruppe "Worker" ausführen kann. Anschließend führt Bob mit der Suchabfrage eine Inhaltssuche für alle Postfächer in der Organisation  `sender:jerry@adatum.com` aus. Da der Berechtigungsfilter und die Suchabfrage logisch durch einen **AND-Operator** kombiniert werden, gibt die Suche alle Nachrichten zurück, die von jerry@adatum.com an ein beliebiges Mitglied der Verteilergruppe "Worker" gesendet wurden. 
    
- **Was passiert, wenn Sie über mehrere Berechtigungsfilter für die Suche verfügen?** Bei einer Inhaltssuchabfrage werden mehrere Berechtigungsfilter durch den booleschen Operator **ODER** miteinander verknüpft. Daher werden Ergebnisse zurückgegeben, wenn nur einer der Filter zutrifft. Bei einer Inhaltssuche werden dann alle (mit den **ODER**-Operatoren verknüpften) Filter durch den Operator **UND** mit der Suchabfrage kombiniert. Nehmen wir das vorherige Beispiel, in dem bob mit einem Suchfilter nur die Postfächer der Mitglieder der Verteilergruppe "Worker" durchsuchen kann. Wir erstellen dann einen weiteren Filter, der verhindert, dass Bob das Postfach von Phil („Mailbox_Alias - ne 'Phil'“) durchsuchen kann. Außerdem nehmen wir an, dass Phil ein Mitglied der Gruppe „Worker“ ist. Wenn Bob eine Inhaltssuche (aus dem vorherigen Beispiel) für alle Postfächer in der Organisation ausführt, werden Suchergebnisse für Das Postfach von Sven zurückgegeben, obwohl Sie Filter angewendet haben, um bob daran zu hindern, das Postfach von Bob zu durchsuchen. Dies liegt daran, dass der erste Filter, der Bob erlaubt, die Gruppe „Worker“ zu durchsuchen „wahr“ ist. Da Phil Mitglied der Gruppe „Worker“ ist, kann Bob das Postfach von Phil durchsuchen. 
    
- **Funktioniert die Filterung von Suchberechtigungen für inaktive Postfächer?** Ja, Sie können Postfach- und Postfachinhaltsfilter verwenden, um zu begrenzen, wer inaktive Postfächer in Ihrer Organisation durchsuchen kann. Wie bei einem regulären Postfach muss ein inaktives Postfach mit der Empfängereigenschaft konfiguriert werden, die zum Erstellen eines Berechtigungsfilters verwendet wird. Bei Bedarf können Sie den Befehl **"Get-Mailbox -InactiveMailboxOnly"** verwenden, um die Eigenschaften inaktiver Postfächer anzuzeigen. Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Office 365.](create-and-manage-inactive-mailboxes.md)
    
- **Funktioniert die Filterung von Suchberechtigungen für öffentliche Ordner?** Nein. Wie zuvor erläutert, kann die Suchberechtigungsfilterung nicht verwendet werden, um zu beschränken, wer öffentliche Ordner in Exchange durchsuchen kann. Beispielsweise können Elemente an Speicherorten öffentlicher Ordner nicht durch einen Berechtigungsfilter aus den Suchergebnissen ausgeschlossen werden. 

- **Verhindert dies, dass ein Benutzer alle Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen kann, auch die Suche nach Inhaltsspeicherorten in einem anderen Dienst?** Nein. Wie zuvor erläutert, müssen Sie einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer Exchange Postfach oder eine SharePoint Website durchsucht). Mit anderen Worten: Das Erstellen eines Suchberechtigungsfilters, der es einem Benutzer ermöglicht, alle SharePoint Websites in der Organisation zu durchsuchen, hindert diesen Benutzer nicht daran, Postfächer zu durchsuchen. Damit SharePoint Administratoren beispielsweise nur SharePoint Websites durchsuchen können, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um Exchange Administratoren nur das Durchsuchen von Postfächern zu gestatten, müssen Sie einen Filter erstellen, der sie daran hindert, Websites zu durchsuchen.

- **Zählen Suchberechtigungsfilter für Suchabfragezeichenbeschränkungen?** Ja. Suchberechtigungsfilter zählen nach dem Zeichenlimit für Suchabfragen. Weitere Informationen finden Sie unter [Grenzwerte in Advanced eDiscovery](limits-ediscovery20.md).

