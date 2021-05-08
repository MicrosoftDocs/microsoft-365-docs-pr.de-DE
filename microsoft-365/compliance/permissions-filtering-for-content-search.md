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
description: Verwenden Sie die Inhaltssuchberechtigungsfilterung, damit ein eDiscovery-Manager nur eine Teilmenge der Postfächer und Websites in Ihrer Organisation durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c36263466e103c0401e51b42b5d7ec3f6e2b4f9c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245348"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Konfigurieren der Berechtigungsfilterung für die Compliancesuche

Sie können die Filterung von Suchberechtigungen verwenden, damit ein eDiscovery-Manager nur eine Teilmenge der Postfächer und Websites in Ihrer Organisation durchsuchen kann. Sie können Berechtigungsfilter auch verwenden, um demselben eDiscovery-Managers zu ermöglichen, nur nach Postfach- oder Websiteinhalt zu suchen, der bestimmten Suchkriterien entspricht. Sie können einem Discovery-Manager beispielsweise ermöglichen, nur die Postfächer der Benutzer an einem bestimmten Standort oder in einer bestimmten Abteilung zu durchsuchen. Dazu erstellen Sie einen Filter, der einen unterstützten Empfängerfilter verwendet, um zu begrenzen, welche Postfächer ein bestimmter Benutzer oder eine bestimmte Benutzergruppe durchsuchen kann. Sie können auch einen Filter erstellen, der angibt, nach welchem Postfachinhalt ein Benutzer suchen kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Nachrichteneigenschaft verwendet. Ebenso können Sie es einem eDiscovery-Manager gestatten, nur bestimmte websites SharePoint in Ihrer Organisation zu durchsuchen. Hierzu erstellen Sie einen Filter, der einschränkt, welche Website durchsucht werden kann. Sie können auch einen Filter erstellen, der angibt, welcher Websiteinhalt durchsucht werden kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Website-Eigenschaft verwendet.

Sie können die Filterung von Suchberechtigungen auch verwenden, um logische Grenzen (compliance *boundaries)* innerhalb einer Organisation zu erstellen, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, SharePoint-Websites und OneDrive-Konten) steuern, die von bestimmten eDiscovery-Managern durchsucht werden können. Weitere Informationen finden Sie unter [Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen in Office 365](tagging-and-assessment-in-advanced-ediscovery.md).
  
Die Filterung von Suchberechtigungen wird vom Feature "Inhaltssuche" im Security & Compliance Center unterstützt. Mit diesen vier Cmdlets können Sie Suchberechtigungsfilter konfigurieren und verwalten:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Anforderungen zum Konfigurieren der Berechtigungsfilterung

- Zum Ausführen der Cmdlets für den Compliancesicherheitsfilter müssen Sie Mitglied der Rollengruppe Organisationsverwaltung im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Sie müssen eine Verbindung mit Exchange Online und Security & Compliance Center PowerShell herstellen, um die Cmdlets für den Compliancesicherheitsfilter zu verwenden. Dies ist erforderlich, da diese Cmdlets Zugriff auf Postfacheigenschaften benötigen, weshalb Sie eine Verbindung mit Exchange Online PowerShell herstellen müssen. Sehen Sie sich die Schritte im nächsten Abschnitt an.

- Weitere Informationen über Berechtigungsfilter für die Suche finden Sie im Abschnitt [More information](#more-information).

- Die Filterung von Suchberechtigungen gilt für inaktive Postfächer, d. h. Sie können die Postfach- und Postfachinhaltsfilterung verwenden, um zu begrenzen, wer ein inaktives Postfach durchsuchen kann. Weitere Informationen [finden Sie im](#more-information) Abschnitt Weitere Informationen zur Berechtigungsfilterung und zu inaktiven Postfächern.

- Die Filterung von Suchberechtigungen kann nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in öffentlichen Exchange.

- Die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können, ist nicht begrenzt. Die Suchleistung wird sich jedoch auswirken, wenn mehr als 100 Filter für Suchberechtigungen verwendet werden. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzigen Filter kombinieren, wann immer möglich.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Verbinden, Exchange Online und & Compliance Center PowerShell in einer einzigen Sitzung zu verwenden

Bevor Sie das Skript in diesem Abschnitt erfolgreich ausführen können, müssen Sie das Exchange Online PowerShell V2-Modul herunterladen und installieren. Weitere Informationen finden Sie [unter Informationen zum Exchange Online PowerShell V2-Modul](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie ein Dateinamensuffix von **.ps1.** Sie könnten sie beispielsweise in einer Datei mit dem Namen **ConnectEXO-SCC.ps1.**

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, wechseln Sie zu dem Ordner, in dem sich das skript befindet, das Sie im vorherigen Schritt erstellt haben, und führen Sie das Skript aus. Zum Beispiel:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Woher wissen Sie, dass dieses Verfahren erfolgreich war? Nachdem Sie das Skript ausgeführt haben, werden Cmdlets aus Exchange Online und Security & Compliance PowerShell in Ihre lokale Windows PowerShell importiert. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein Schnelltest ist das Ausführen eines cmdlets Exchange Online und & Compliance Center. Sie können z. B. ausführen und **Get-Mailbox und** **Get-ComplianceSearch ausführen.**

Informationen zur Problembehandlung bei PowerShell-Verbindungsfehlern finden Sie unter:

- [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Der **New-ComplianceSecurityFilter** wird zum Erstellen eines Suchberechtigungsfilters verwendet. In der folgenden Tabelle werden die Parameter für dieses Cmdlet beschrieben. Alle Parameter sind erforderlich, um einen Compliancesicherheitsfilter zu erstellen.
  
| Parameter | Beschreibung |
|:-----|:-----|
| _Action_ <br/> | Der  _Parameter Action_ gibt an, auf welche Art von Suchaktion der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich:  <br/><br/> **Exportieren:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird angewendet, wenn die Suchergebnisse in der Vorschau angezeigt werden.  <br/> **Bereinigen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_ <br/> |Der  _Parameter FilterName_ gibt den Namen des Berechtigungsfilters an. Dieser Name wird verwendet, um bei Verwendung der Cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** und **Remove-ComplianceSecurityFilter** einen Filter zu identifizieren.  <br/> |
| _Filters_ <br/> | Der  _Parameter Filters_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können drei unterschiedliche Filtertypen erstellen:  <br/><br/> **Postfachfilterung:** Dieser Filtertyp gibt die Postfächer an, die die zugewiesenen Benutzer durchsuchen können (angegeben durch den _Parameter Users)._ Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei  _MailboxPropertyName_ eine Postfacheigenschaft angibt, die zum Bereich der Postfächer verwendet wird, die durchsucht werden können. Der Postfachfilter ermöglicht beispielsweise dem Benutzer, dem dieser Filter zugewiesen ist, nur die Postfächer zu durchsuchen, die den Wert  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" in der CustomAttribute10-Eigenschaft haben.  <br/>  Jede unterstützte filterbare Empfängereigenschaft kann für die  _MailboxPropertyName-Eigenschaft verwendet_ werden. Eine Liste der unterstützten Eigenschaften finden Sie unter [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties).  <br/><br/> **Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName: value_, wobei  _SearchablePropertyName_ eine Keyword Query Language (KQL)-Eigenschaft angibt, die in einer Inhaltssuche angegeben werden kann. Mit dem Postfachinhaltsfilter kann der diesem Filter zugewiesene Benutzer beispielsweise nur nach Nachrichten suchen, die an Empfänger in der contoso.com  `MailboxContent_recipients:contoso.com` werden.  <br/>  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md). <br/> <br/> **Wichtig:**  Ein einzelner Suchfilter kann keinen Postfachfilter und keinen Postfachinhaltsfilter enthalten. Um diese in einem einzigen Filter zu kombinieren, müssen Sie eine [Filterliste verwenden.](#using-a-filters-list-to-combine-filter-types)  Ein Filter kann jedoch eine komplexere Abfrage desselben Typs enthalten. Zum Beispiel  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`.  <br/><br/> **Filterung von Website- und Websiteinhalten:** Es gibt zwei SharePoint und OneDrive for Business, die Sie verwenden können, um anzugeben, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Diese beiden Filter sind austauschbar. Geben Sie  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` beispielsweise dieselben Ergebnisse  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` zurück. Damit Sie jedoch ermitteln können, was ein Filter macht, können Sie websitebezogene Eigenschaften (z. B. eine Website-URL) angeben und inhaltsbezogene Eigenschaften (z. B.  `Site_`  `SiteContent_` Dokumenttypen) angeben. Der Filter ermöglicht beispielsweise dem Benutzer, dem dieser Filter zugewiesen ist, nur nach  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` Inhalten in der https://contoso.sharepoint.com/sites/doctors Websitesammlung zu suchen. Der Filter ermöglicht es dem Benutzer, dem dieser Filter zugewiesen ist, nur nach  `"SiteContent_FileExtension -eq 'docx'"` Word-Dokumenten (Word 2007 und höher) zu suchen.  <br/><br/>  Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Overview of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Eigenschaften, die **in** der Spalte "Abfragebar" mit "Ja" gekennzeichnet **sind,** können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden.  <br/><br/> **Wichtig:** Sie müssen einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer ein Exchange-Postfach oder eine SharePoint durchsucht). Anders ausgedrückt: Das Erstellen eines Suchberechtigungsfilters, mit dem ein Benutzer alle SharePoint in der Organisation durchsuchen kann, verhindert nicht, dass dieser Benutzer Postfächer durchsucht. Um z. B. SharePoint Administratoren nur die Suche SharePoint Websites zu ermöglichen, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um es administratoren Exchange, nur Postfächer zu durchsuchen, müssen Sie einen Filter erstellen, der verhindert, dass sie Websites durchsuchen.           |
| _Benutzer_ <br/> |Der  _Parameter Users_ gibt die Benutzer an, denen dieser Filter auf die Inhaltssuche angewendet wird. Identifizieren Sie die Benutzer durch ihren Aliasnamen oder die primäre SMTP-Adresse. Sie können mehrere durch Kommas getrennte Werte angeben, oder Sie können den Filter allen Benutzern zuweisen, indem Sie den Wert **Alle** angeben.  <br/> Sie können auch den  _Parameter Users_ verwenden, um eine Rollengruppe "Security & Compliance Center" anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den  _Parameter Users_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Name-Eigenschaft der Rollengruppe), und dann den  _Parameter Filter_ verwenden, um nur Postfächer in den USA zu durchsuchen.  <br/> Sie können mit diesem Parameter keine Verteilergruppen angeben.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Verwenden einer Filterliste zum Kombinieren von Filtertypen

Eine *Filterliste* ist ein Filter, der einen Postfachfilter und einen Standortfilter enthält, der durch ein Komma getrennt ist. Die Verwendung einer Filterliste ist die einzige unterstützte Methode zum Kombinieren verschiedener Filtertypen. Beachten Sie im folgenden Beispiel, dass ein Komma die **Filter Mailbox** und **Site** trennt:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Wenn ein Filter, der eine Filterliste enthält, während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Filter für Suchberechtigungen aus der Filterliste erstellt: einer für jeden Filter, der durch ein Komma getrennt ist. Im vorherigen Beispiel würden daher ein Filter für Postfachsuchberechtigungen und ein Filter für Websitesuchberechtigungen erstellt. 

Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern. Im vorherigen Beispiel würden Sie also einen Filter für das Postfachattribut und einen Filter für das Websiteattribut erstellen. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine Bevorzugte Frage.

Beachten Sie die folgenden Punkte bei der Verwendung einer Filterliste:

- Sie müssen eine Filterliste verwenden, um einen Filter zu erstellen, der einen **Postfachfilter** und einen **MailboxContent-Filter** enthält. 

- Wie bereits vorgeschlagen, müssen Sie keine Filterliste verwenden, um einen **Site-** und einen **SiteContent-Filter** in einen einzelnen Suchberechtigungsfilter zu verwenden. Sie können z. B. **Website-** und **SiteContent-Filter** mit einem **-oder-Operator** kombinieren.

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Jede Komponente einer Filterliste kann eine komplexe Filtersyntax enthalten. Die Postfach- und Standortfilter können beispielsweise mehrere Filter enthalten, die durch einen **-or-Operator getrennt** sind:

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Beispiele zum Erstellen von Suchberechtigungsfiltern

Nachfolgend finden Sie Beispiele für die Verwendung des **New-ComplianceSecurityFilter**-Cmdlets zum Erstellen eines Berechtigungsfilters für die Suche. 
  
In diesem Beispiel kann annb@contoso.com alle Inhaltssuchaktionen nur für Postfächer in Kanada ausführen. Dieser Filter enthält die dreistellige Landeskennzahl für Kanada gemäß ISO 3166-1.

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

In diesem Beispiel können Mitglieder der Rollengruppe eDiscovery Manager nur die Postfächer von Mitgliedern der Verteilergruppe Ottawa Users durchsuchen. Das Get-DistributionGroup cmdlet in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Ottawa Users" zu finden.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In diesem Beispiel wird verhindert, dass Benutzer Inhalt aus den Postfächern der Mitglieder der Verteilergruppe „Executive Team“ löschen. Das Get-DistributionGroup cmdlet in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Executive Team" zu finden.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In diesem Beispiel können Mitglieder der benutzerdefinierten OneDrive eDiscovery Managers nur an OneDrive for Business in der Organisation nach Inhalten suchen.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Verwenden Sie den Filter, wie im vorherigen Beispiel gezeigt, um Benutzer auf die Suche nach bestimmten Websites  `Site_Path` zu beschränken. Die  `Site_Site` Verwendung funktioniert nicht. 
  
In diesem Beispiel kann der Benutzer Inhaltssuchvorgänge nur für E-Mail-Nachrichten durchführen, die während des Kalenderjahres 2015 gesendet wurden.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Ähnlich wie im vorherigen Beispiel kann der Benutzer in diesem Beispiel die Inhaltssuchvorgänge nur für Dokumente durchführen, die zuletzt im Kalenderjahr 2015 geändert wurden.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

In diesem Beispiel wird verhindert, dass Mitglieder der Rollengruppe "OneDrive Discovery Managers" Inhaltssuchaktionen für jedes Postfach in der Organisation ausführen. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In diesem Beispiel wird verhindert, dass benutzer in der Organisation nach E-Mail-Nachrichten suchen, die von Janets oder Sarad gesendet oder empfangen wurden.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In diesem Beispiel wird eine Filterliste verwendet, um Postfach- und Websitefilter zu kombinieren.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

Der **Get-ComplianceSecurityFilter** wird verwendet, um eine Liste von Suchberechtigungsfiltern zurück zu geben. Verwenden Sie den  _Parameter FilterName,_ um Informationen für einen bestimmten Suchfilter zurückzukehren. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

Der **Set-ComplianceSecurityFilter** wird verwendet, um einen vorhandenen Suchberechtigungsfilter zu ändern. Der einzige erforderliche Parameter ist  _FilterName_. 
  
| Parameter | Beschreibung |
|:-----|:-----|
| _Action_| Der  _Parameter Action_ gibt an, auf welche Art von Suchaktion der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich: <br/><br/> **Exportieren:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird angewendet, wenn die Suchergebnisse in der Vorschau angezeigt werden.  <br/> **Bereinigen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird angewendet, wenn eine Suche ausgeführt wird.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_|Der  _Parameter FilterName_ gibt den Namen des Berechtigungsfilters an. |
| _Filters_| Der  _Parameter Filters_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können zwei verschiedene Filtertypen erstellen: <br/><br/>**Postfachfilterung:** Dieser Filtertyp gibt die Postfächer an, die die zugewiesenen Benutzer durchsuchen können (angegeben durch den _Parameter Users)._ Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei  _MailboxPropertyName_ eine Postfacheigenschaft angibt, die zum Bereich der Postfächer verwendet wird, die durchsucht werden können. Der Postfachfilter ermöglicht beispielsweise dem Benutzer, dem dieser Filter zugewiesen ist, nur die Postfächer zu durchsuchen, die den Wert  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" in der CustomAttribute10-Eigenschaft haben.  Jede unterstützte filterbare Empfängereigenschaft kann für die  _MailboxPropertyName-Eigenschaft verwendet_ werden. Eine Liste der unterstützten Eigenschaften finden Sie unter [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties). <br/><br/>**Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName:value_, wobei  _SearchablePropertyName_ eine Keyword Query Language (KQL)-Eigenschaft angibt, die in einer Inhaltssuche angegeben werden kann. Mit dem Postfachinhaltsfilter kann der diesem Filter zugewiesene Benutzer beispielsweise nur nach Nachrichten suchen, die an Empfänger in der contoso.com  `MailboxContent_recipients:contoso.com` werden.  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Keyword queries for Content Search](keyword-queries-and-search-conditions.md). <br/><br/>**Filterung von Website- und Websiteinhalten:** Es gibt zwei SharePoint und OneDrive for Business, die Sie verwenden können, um anzugeben, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Diese beiden Filter sind austauschbar. Gibt beispielsweise  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` dieselben  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` Ergebnisse zurück. Damit Sie jedoch ermitteln können, was ein Filter macht, können Sie websitebezogene Eigenschaften (z. B. eine Website-URL) angeben und inhaltsbezogene Eigenschaften (z. B.  `Site_`  `SiteContent_` Dokumenttypen) angeben. Der Filter ermöglicht beispielsweise dem Benutzer, dem dieser Filter zugewiesen ist, nur nach  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` Inhalten in der https://contoso.spoppe.com/sites/doctors Websitesammlung zu suchen. Der Filter ermöglicht es dem Benutzer, dem dieser Filter zugewiesen ist, nur nach  `"SiteContent_FileExtension -eq 'docx'"` Word-Dokumenten (Word 2007 und höher) zu suchen.  <br/><br/>Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Overview of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Eigenschaften, die **in** der Spalte "Abfragebar" mit "Ja" gekennzeichnet **sind,** können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden. <br/><br/>          |
| _Benutzer_|Der  _Parameter Users_ gibt die Benutzer an, denen dieser Filter auf die Inhaltssuche angewendet wird. Da es sich um eine Mehrwerteigenschaft handelt, überschreibt das Angeben eines Benutzers oder einer Gruppe von Benutzern mit diesem Parameter die vorhandene Benutzerliste. In den folgenden Beispielen finden Sie die Syntax zum Hinzufügen und Entfernen ausgewählter Benutzer. <br/><br/>Sie können auch den  _Parameter Users_ verwenden, um eine Rollengruppe "Security & Compliance Center" anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den  _Parameter Users_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Name-Eigenschaft der Rollengruppe), und dann den  _Parameter Filter_ verwenden, um nur Postfächer in den USA zu durchsuchen. <br/><br/>Sie können mit diesem Parameter keine Verteilergruppen angeben. |

## <a name="examples-of-changing-search-permissions-filters"></a>Beispiele für das Ändern von Suchberechtigungsfiltern

In diesen Beispielen wird gezeigt, wie Sie die **Cmdlets Get-ComplianceSecurityFilter** und **Set-ComplianceSecurityFilter** verwenden, um der vorhandenen Liste der Benutzer, denen der Filter zugewiesen ist, einen Benutzer hinzuzufügen oder zu entfernen. Wenn Sie einem Filter Benutzer hinzufügen oder Benutzer daraus entfernen, geben Sie den Benutzer durch seine SMTP-Adresse an. 
  
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

Der **Remove-ComplianceSecurityFilter** wird zum Löschen eines Suchfilters verwendet. Verwenden Sie  _den Parameter FilterName,_ um den filter anzugeben, den Sie löschen möchten. 
  
## <a name="more-information"></a>Weitere Informationen

- **Wie funktionieren Berechtigungsfilter für die Suche?** Der Berechtigungsfilter wird der Suchabfrage hinzugefügt, wenn eine Inhaltssuche ausgeführt wird. Der Berechtigungsfilter wird mit der Suchabfrage durch den **AND** Boolean-Operator verbunden. Beispielsweise verfügen Sie über einen Berechtigungsfilter, mit dem Bob alle Suchaktionen für die Postfächer von Mitgliedern der Verteilergruppe Workers ausführen kann. Anschließend führt Bob eine Inhaltssuche für alle Postfächer in der Organisation mit der Suchabfrage  `sender:jerry@adatum.com` aus. Da der Berechtigungsfilter und die Suchabfrage logisch von einem **AND-Operator** kombiniert werden, gibt die Suche alle Nachrichten zurück, die von jerry@adatum.com an ein beliebiges Mitglied der Verteilergruppe Workers gesendet werden. 
    
- **Was passiert, wenn Sie über mehrere Berechtigungsfilter für die Suche verfügen?** Bei einer Inhaltssuchabfrage werden mehrere Berechtigungsfilter durch den booleschen Operator **ODER** miteinander verknüpft. Daher werden Ergebnisse zurückgegeben, wenn nur einer der Filter zutrifft. Bei einer Inhaltssuche werden dann alle (mit den **ODER**-Operatoren verknüpften) Filter durch den Operator **UND** mit der Suchabfrage kombiniert. Nehmen wir das vorherige Beispiel, in dem bob mit einem Suchfilter nur die Postfächer der Mitglieder der Verteilergruppe Workers durchsuchen kann. Wir erstellen dann einen weiteren Filter, der verhindert, dass Bob das Postfach von Phil („Mailbox_Alias - ne 'Phil'“) durchsuchen kann. Außerdem nehmen wir an, dass Phil ein Mitglied der Gruppe „Worker“ ist. Wenn Bob eine Inhaltssuche (aus dem vorherigen Beispiel) für alle Postfächer in der Organisation führt, werden Suchergebnisse für Phils Postfach zurückgegeben, obwohl Sie filter angewendet haben, um zu verhindern, dass Bob das Postfach von Phil durchsucht. Dies liegt daran, dass der erste Filter, der Bob erlaubt, die Gruppe „Worker“ zu durchsuchen „wahr“ ist. Da Phil Mitglied der Gruppe „Worker“ ist, kann Bob das Postfach von Phil durchsuchen. 
    
- **Funktioniert die Filterung von Suchberechtigungen für inaktive Postfächer?** Ja, Sie können Postfach- und Postfachinhaltsfilter verwenden, um zu begrenzen, wer inaktive Postfächer in Ihrer Organisation durchsuchen kann. Wie bei einem regulären Postfach muss ein inaktives Postfach mit der Empfängereigenschaft konfiguriert werden, die zum Erstellen eines Berechtigungsfilters verwendet wird. Bei Bedarf können Sie mit dem **Befehl Get-Mailbox -InactiveMailboxOnly** die Eigenschaften inaktiver Postfächer anzeigen. Weitere Informationen finden Sie unter [Create and manage inactive mailboxes in Office 365](create-and-manage-inactive-mailboxes.md).
    
- **Funktioniert die Filterung von Suchberechtigungen für öffentliche Ordner?** Nein. Wie bereits erläutert, kann die Filterung von Suchberechtigungen nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in öffentlichen Exchange. Beispielsweise können Elemente an Speicherorten öffentlicher Ordner nicht von einem Berechtigungsfilter aus den Suchergebnissen ausgeschlossen werden. 

- **Kann ein Benutzer alle Inhaltsstandorte in einem bestimmten Dienst durchsuchen, und verhindert er auch das Durchsuchen von Inhaltsstandorten in einem anderen Dienst?** Nein. Wie bereits erläutert, müssen Sie einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer ein Exchange-Postfach oder eine SharePoint durchsucht). Anders ausgedrückt: Das Erstellen eines Suchberechtigungsfilters, mit dem ein Benutzer alle SharePoint in der Organisation durchsuchen kann, verhindert nicht, dass dieser Benutzer Postfächer durchsucht. Um z. B. SharePoint Administratoren nur die Suche SharePoint Websites zu ermöglichen, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um es administratoren Exchange, nur Postfächer zu durchsuchen, müssen Sie einen Filter erstellen, der verhindert, dass sie Websites durchsuchen.

- **Zählen Suchberechtigungsfilter auf Die Grenzwerte für Suchabfragezeichen?** Ja. Suchberechtigungsfilter werden mit dem Zeichenlimit für Suchabfragen gezählt. Weitere Informationen finden Sie unter [Limits in Advanced eDiscovery](limits-ediscovery20.md).

