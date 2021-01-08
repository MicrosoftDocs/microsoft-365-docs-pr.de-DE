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
description: Verwenden Sie die Berechtigungsfilterung für die Inhaltssuche, damit ein eDiscovery-Manager nur eine Teilmenge der Postfächer und Websites in Ihrer Organisation durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ac09b35a4487ad836b48ba0cf7fee765e758ec4
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780473"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Konfigurieren der Berechtigungsfilterung für die Compliancesuche

Sie können die Filterung von Suchberechtigungen verwenden, damit ein eDiscovery-Manager nur eine Teilmenge der Postfächer und Websites in Ihrer Organisation durchsuchen kann. Sie können Berechtigungsfilter auch verwenden, um demselben eDiscovery-Managers zu ermöglichen, nur nach Postfach- oder Websiteinhalt zu suchen, der bestimmten Suchkriterien entspricht. Sie können einem Discovery-Manager beispielsweise ermöglichen, nur die Postfächer der Benutzer an einem bestimmten Standort oder in einer bestimmten Abteilung zu durchsuchen. Erstellen Sie dazu einen Filter, der einen unterstützten Empfängerfilter verwendet, um zu begrenzen, welche Postfächer ein bestimmter Benutzer oder eine Bestimmte Benutzergruppe durchsuchen kann. Sie können auch einen Filter erstellen, der angibt, nach welchem Postfachinhalt ein Benutzer suchen kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Nachrichteneigenschaft verwendet. Ebenso können Sie es einem eDiscovery-Manager gestatten, nur bestimmte SharePoint-Websites in Ihrer Organisation zu durchsuchen. Hierzu erstellen Sie einen Filter, der einschränkt, welche Website durchsucht werden kann. Sie können auch einen Filter erstellen, der angibt, welcher Websiteinhalt durchsucht werden kann. Dies erfolgt durch das Erstellen eines Filters, der eine durchsuchbare Website-Eigenschaft verwendet.

Sie können die Suchberechtigungsfilterung auch verwenden, um logische Grenzen (so genannte Compliancegrenzen) in einer Organisation zu erstellen, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, #A0 und OneDrive-Konten) steuern, die von bestimmten eDiscovery-Managern durchsucht werden können. Weitere Informationen finden Sie unter [Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen in Office 365.](tagging-and-assessment-in-advanced-ediscovery.md)
  
Die Filterung von Suchberechtigungen wird vom Feature "Inhaltssuche" im Security & Compliance Center unterstützt. Mit diesen vier Cmdlets können Sie Suchberechtigungsfilter konfigurieren und verwalten:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Anforderungen zum Konfigurieren der Berechtigungsfilterung

- Zum Ausführen der Cmdlets für den Compliancesicherheitsfilter müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Sie müssen eine Verbindung mit Exchange Online und Security & Compliance Center PowerShell herstellen, um die Cmdlets für Compliancesicherheitsfilter zu verwenden. Dies ist erforderlich, da diese Cmdlets Zugriff auf Postfacheigenschaften benötigen, weshalb Sie eine Verbindung mit Exchange Online PowerShell herstellen müssen. Siehe die Schritte im nächsten Abschnitt.

- Weitere Informationen über Berechtigungsfilter für die Suche finden Sie im Abschnitt [More information](#more-information).

- Die Filterung von Suchberechtigungen gilt für inaktive Postfächer, was bedeutet, dass Sie die Postfach- und Postfachinhaltsfilterung verwenden können, um zu begrenzen, wer ein inaktives Postfach durchsuchen kann. Weitere Informationen [zur Berechtigungsfilterung](#more-information) und zu inaktiven Postfächern finden Sie im Abschnitt "Weitere Informationen".

- Die Filterung von Suchberechtigungen kann nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in Exchange durchsuchen kann.

- Die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können, ist nicht begrenzt. Die Suchleistung wird jedoch bei mehr als 100 Suchberechtigungsfiltern beeinträchtigen. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive nach Möglichkeit in einem einzigen Filter kombinieren.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Herstellen einer Verbindung mit Exchange Online und Security & Compliance Center PowerShell in einer einzigen Sitzung

Bevor Sie das Skript in diesem Abschnitt erfolgreich ausführen können, müssen Sie das Exchange Online PowerShell V2-Modul herunterladen und installieren. Weitere Informationen finden Sie [unter Informationen zum Exchange Online PowerShell V2-Modul.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix **PS1 verwenden.** Sie können sie beispielsweise in einer Datei mit dem Namen **ConnectEXO-SCC.ps1.**

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, wechseln Sie zu dem Ordner, in dem sich das im vorherigen Schritt erstellte Skript befindet, und führen Sie das Skript aus. Zum Beispiel:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Woher wissen Sie, dass dieses Verfahren erfolgreich war? Nachdem Sie das Skript ausgeführt haben, werden Cmdlets aus Exchange Online und Security & Compliance PowerShell in Ihre lokale Windows PowerShell importiert. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein schneller Test ist das Ausführen eines Exchange Online- und Security & Compliance Center-Cmdlets. Sie können z. B. **"Get-Mailbox" und** **"Get-ComplianceSearch" ausführen.**

Informationen zur Problembehandlung von PowerShell-Verbindungsfehlern finden Sie unter:

- [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Der **New-ComplianceSecurityFilter** wird zum Erstellen eines Suchberechtigungsfilters verwendet. In der folgenden Tabelle werden die Parameter für dieses Cmdlet beschrieben. Alle Parameter sind erforderlich, um einen Compliancesicherheitsfilter zu erstellen.
  
|**Parameter**|**Beschreibung**|
|:-----|:-----|
| _Action_ <br/> | Der  _Parameter "Action"_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich:  <br/><br/> **Exportieren:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird angewendet, wenn eine Vorschau der Suchergebnisse angezeigt wird.  <br/> **Löschen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird beim Ausführen einer Suche angewendet.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_ <br/> |Der  _Parameter "FilterName"_ gibt den Namen des Berechtigungsfilters an. Dieser Name wird verwendet, um bei Verwendung der Cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** und **Remove-ComplianceSecurityFilter** einen Filter zu identifizieren.  <br/> |
| _Filters_ <br/> | Der  _Parameter "Filters"_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können drei unterschiedliche Filtertypen erstellen:  <br/><br/> **Postfachfilterung:** Dieser Filtertyp gibt die Postfächer an, die die zugewiesenen Benutzer (angegeben durch den Parameter  _"Users")_ durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei  _MailboxPropertyName_ eine Postfacheigenschaft angibt, die verwendet wird, um den Bereich der Postfächer zu aktivieren, die durchsucht werden können. Beispielsweise würde der Postfachfilter dem diesem Filter zugewiesenen Benutzer erlauben, nur die Postfächer zu durchsuchen, die den Wert  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" in der Eigenschaft "CustomAttribute10" haben.  <br/>  Jede unterstützte filterbare Empfängereigenschaft kann für die Eigenschaft  _"MailboxPropertyName" verwendet_ werden. Eine Liste der unterstützten Eigenschaften finden Sie unter ["Filterable"-Eigenschaften für den Parameter "-RecipientFilter".](https://go.microsoft.com/fwlink/p/?LinkId=784903)  <br/><br/> **Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName: value_, wobei  _SearchablePropertyName_ eine #A0 (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Der Postfachinhaltsfilter würde beispielsweise zulassen, dass der diesem Filter zugewiesene Benutzer nur nach Nachrichten sucht, die an Empfänger in der contoso.com  `MailboxContent_recipients:contoso.com` werden.  <br/>  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche.](keyword-queries-and-search-conditions.md) <br/> <br/> **Wichtig:**  Ein einzelner Suchfilter darf keinen Postfachfilter und keinen Postfachinhaltsfilter enthalten. Um diese in einem einzigen Filter zu kombinieren, müssen Sie eine [Filterliste verwenden.](#using-a-filters-list-to-combine-filter-types)  Ein Filter kann jedoch eine komplexere Abfrage desselben Typs enthalten. Zum Beispiel  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`.  <br/><br/> **Filterung von Website- und Websiteinhalten:** Es gibt zwei SharePoint- und OneDrive for Business-websitebezogene Filter, mit denen Sie angeben können, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Diese beiden Filter sind austauschbar. Geben Sie beispielsweise  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` dieselben Ergebnisse zurück. Damit Sie jedoch ermitteln können, was ein Filter macht, können Sie websitebezogene Eigenschaften (z. B. eine Website-URL) und inhaltsbezogene Eigenschaften (z. B.  `Site_`  `SiteContent_` Dokumenttypen) angeben. Der Filter würde beispielsweise zulassen, dass der diesem Filter zugewiesene Benutzer nur nach  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` Inhalten in der https://contoso.sharepoint.com/sites/doctors Websitesammlung sucht. Mit dem Filter kann der diesem Filter zugewiesene Benutzer nur nach Word-Dokumenten  `"SiteContent_FileExtension -eq 'docx'"` (Word 2007 und höher) suchen.  <br/><br/>  Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforste und verwaltete Eigenschaften in SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) Eigenschaften, die **in**  der Spalte "Abfragebar" mit "Ja" gekennzeichnet sind, können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden.  <br/><br/> **Wichtig:** Sie müssen einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer ein beliebiges Exchange-Postfach oder eine beliebige SharePoint-Website durchsucht). Anders ausgedrückt: Das Erstellen eines Suchberechtigungsfilters, mit dem ein Benutzer alle SharePoint-Websites in der Organisation durchsuchen kann, verhindert nicht, dass dieser Benutzer Postfächer durchsucht. Um beispielsweise SharePoint-Administratoren nur das Durchsuchen von SharePoint-Websites zu ermöglichen, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um exchange-Administratoren nur das Durchsuchen von Postfächern zu ermöglichen, müssen Sie einen Filter erstellen, der sie daran hindert, Websites zu durchsuchen.           |
| _Benutzer_ <br/> |Der  _Parameter "Users"_ gibt die Benutzer an, denen dieser Filter auf die Inhaltssuche angewendet wird. Identifizieren Sie die Benutzer durch ihren Aliasnamen oder die primäre SMTP-Adresse. Sie können mehrere durch Kommas getrennte Werte angeben, oder Sie können den Filter allen Benutzern zuweisen, indem Sie den Wert **Alle** angeben.  <br/> Sie können auch den Parameter  _"Users"_ verwenden, um eine & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den Parameter  _"Users"_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Eigenschaft "Name" der Rollengruppe), und dann den Parameter  _"Filter"_ verwenden, damit nur Postfächer in den USA durchsucht werden können.  <br/> Sie können mit diesem Parameter keine Verteilergruppen angeben.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Verwenden einer Filterliste zum Kombinieren von Filtertypen

Eine *Filterliste* ist ein Filter, der einen Postfachfilter und einen Standortfilter enthält, die durch ein Komma getrennt sind. Die Verwendung einer Filterliste ist die einzige unterstützte Methode zum Kombinieren verschiedener Filtertypen. Beachten Sie im folgenden Beispiel, dass die Filter **"Mailbox"** und **"Site"** durch ein Komma getrennt werden:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Wenn ein Filter, der eine Filterliste enthält, während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Filter für Suchberechtigungen aus der Filterliste erstellt: einer für jeden Filter, der durch ein Komma getrennt ist. Im vorherigen Beispiel würden also ein Berechtigungsfilter für die Postfachsuche und ein Filter für Websitesuchberechtigungen erstellt. 

Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern. Im vorherigen Beispiel würden Sie also einen Filter für das Postfachattribut und einen Filter für das Websiteattribut erstellen. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine bevorzugte Frage.

Beachten Sie bei der Verwendung einer Filterliste Folgendes:

- Sie müssen eine Filterliste verwenden, um einen Filter zu erstellen, der einen **Postfachfilter** und einen **Filter "MailboxContent"** enthält. 

- Wie bereits erwähnt, müssen Sie keine Filterliste verwenden, um einen Filter **"Site"** und **"SiteContent"** in einen einzelnen Suchberechtigungsfilter zu verwenden. Sie können z. B. **"Site"** und einen **"SiteContent"-Filter** mithilfe eines **-- oder -Operators** kombinieren.

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Jede Komponente einer Filterliste kann eine komplexe Filtersyntax enthalten. Beispielsweise können die Postfach- und Standortfilter mehrere Filter enthalten, die durch einen **-oder Operator getrennt** sind:

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Beispiele für das Erstellen von Suchberechtigungsfiltern

Nachfolgend finden Sie Beispiele für die Verwendung des **New-ComplianceSecurityFilter**-Cmdlets zum Erstellen eines Berechtigungsfilters für die Suche. 
  
In diesem Beispiel kann der annb@contoso.com alle Inhaltssuchaktionen nur für Postfächer in Kanada ausführen. Dieser Filter enthält die dreistellige Landeskennzahl für Kanada gemäß ISO 3166-1.

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

In diesem Beispiel können Mitglieder der Rollengruppe "eDiscovery-Manager" nur die Postfächer von Mitgliedern der Verteilergruppe "Ottawa Users" durchsuchen. Das Get-DistributionGroup in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Ottawa-Benutzer" zu finden.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In diesem Beispiel wird verhindert, dass Benutzer Inhalt aus den Postfächern der Mitglieder der Verteilergruppe „Executive Team“ löschen. Das Get-DistributionGroup cmdlet in Exchange Online PowerShell wird verwendet, um die Mitglieder der Gruppe "Führungskräfteteam" zu finden.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In diesem Beispiel können Mitglieder der benutzerdefinierten Rollengruppe "OneDrive eDiscovery Managers" nur nach Inhalten an OneDrive for #A0 in der Organisation suchen.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Verwenden Sie den Filter, wie im vorherigen Beispiel gezeigt, um die Suche nach bestimmten Websites  `Site_Path` für Benutzer einzuschränken. Die  `Site_Site` Verwendung funktioniert nicht. 
  
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

Der **Get-ComplianceSecurityFilter** wird verwendet, um eine Liste von Suchberechtigungsfiltern zurückzukehren. Verwenden Sie den  _Parameter "FilterName",_ um Informationen für einen bestimmten Suchfilter zurückzukehren. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

Der **Parameter "Set-ComplianceSecurityFilter"** wird verwendet, um einen vorhandenen Suchberechtigungsfilter zu ändern. Der einzige erforderliche Parameter ist  _FilterName_. 
  
|**Parameter**|**Beschreibung**|
|:-----|:-----|
| _Action_| Der  _Parameter "Action"_ gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Folgende Aktionen für die Inhaltssuche sind möglich: <br/><br/> **Exportieren:** Der Filter wird beim Exportieren von Suchergebnissen angewendet.  <br/> **Vorschau:** Der Filter wird angewendet, wenn eine Vorschau der Suchergebnisse angezeigt wird.  <br/> **Löschen:** Der Filter wird beim Löschen von Suchergebnissen angewendet.  <br/> **Suche:** Der Filter wird beim Ausführen einer Suche angewendet.  <br/> **Alle:** Der Filter wird auf alle Suchaktionen angewendet.  <br/> |
| _FilterName_|Der  _Parameter "FilterName"_ gibt den Namen des Berechtigungsfilters an. |
| _Filters_| Der  _Parameter "Filters"_ gibt die Suchkriterien für den Compliancesicherheitsfilter an. Sie können zwei verschiedene Filtertypen erstellen: <br/><br/>**Postfachfilterung:** Dieser Filtertyp gibt die Postfächer an, die die zugewiesenen Benutzer (angegeben durch den Parameter  _"Users")_ durchsuchen können. Die Syntax für diesen Filtertyp ist **Mailbox_** _MailboxPropertyName_, wobei  _MailboxPropertyName_ eine Postfacheigenschaft angibt, die verwendet wird, um den Bereich der Postfächer zu aktivieren, die durchsucht werden können. Beispielsweise würde der Postfachfilter dem diesem Filter zugewiesenen Benutzer erlauben, nur die Postfächer zu durchsuchen, die den Wert  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" in der Eigenschaft "CustomAttribute10" haben.  Jede unterstützte filterbare Empfängereigenschaft kann für die Eigenschaft  _"MailboxPropertyName" verwendet_ werden. Eine Liste der unterstützten Eigenschaften finden Sie unter ["Filterable"-Eigenschaften für den Parameter "-RecipientFilter".](https://go.microsoft.com/fwlink/p/?LinkId=784903) <br/><br/>**Postfachinhaltsfilterung:** Dieser Filtertyp wird auf den Inhalt angewendet, der durchsucht werden kann. Es gibt den Postfachinhalt an, nach dem die zugewiesenen Benutzer suchen können. Die Syntax für diesen Filtertyp ist **MailboxContent_** _SearchablePropertyName:value_, wobei  _SearchablePropertyName_ eine #A0 (Keyword Query Language) angibt, die in einer Inhaltssuche angegeben werden kann. Der Postfachinhaltsfilter würde beispielsweise zulassen, dass der diesem Filter zugewiesene Benutzer nur nach Nachrichten sucht, die an Empfänger in der contoso.com  `MailboxContent_recipients:contoso.com` werden.  Eine Liste der durchsuchbaren Nachrichteneigenschaften finden Sie unter [Schlüsselwortabfragen für die Inhaltssuche.](keyword-queries-and-search-conditions.md) <br/><br/>**Filterung von Website- und Websiteinhalten:** Es gibt zwei SharePoint- und OneDrive for Business-websitebezogene Filter, mit denen Sie angeben können, welche Website- oder Websiteinhalte die zugewiesenen Benutzer durchsuchen können: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Diese beiden Filter sind austauschbar. Gibt beispielsweise  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` dieselben  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` Ergebnisse zurück. Damit Sie jedoch ermitteln können, was ein Filter macht, können Sie websitebezogene Eigenschaften (z. B. eine Website-URL) und inhaltsbezogene Eigenschaften (z. B.  `Site_`  `SiteContent_` Dokumenttypen) angeben. Der Filter würde beispielsweise zulassen, dass der diesem Filter zugewiesene Benutzer nur nach  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` Inhalten in der https://contoso.spoppe.com/sites/doctors Websitesammlung sucht. Mit dem Filter kann der diesem Filter zugewiesene Benutzer nur nach Word-Dokumenten  `"SiteContent_FileExtension -eq 'docx'"` (Word 2007 und höher) suchen.  <br/><br/>Eine Liste der durchsuchbaren Websiteeigenschaften finden Sie unter [Übersicht über durchforste und verwaltete Eigenschaften in SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) Eigenschaften, die **in**  der Spalte "Abfragebar" mit "Ja" gekennzeichnet sind, können zum Erstellen eines Website- oder Websiteinhaltsfilters verwendet werden. <br/><br/>          |
| _Benutzer_|Der  _Parameter "Users"_ gibt die Benutzer an, denen dieser Filter auf die Inhaltssuche angewendet wird. Da es sich um eine mehrwertige Eigenschaft handelt, überschreibt die Angabe eines Benutzers oder einer Benutzergruppe mit diesem Parameter die vorhandene Benutzerliste. In den folgenden Beispielen finden Sie die Syntax zum Hinzufügen und Entfernen ausgewählter Benutzer. <br/><br/>Sie können auch den Parameter  _"Users"_ verwenden, um eine & Compliance Center-Rollengruppe anzugeben. Auf diese Weise können Sie eine benutzerdefinierte Rollengruppe erstellen und diese Rollengruppe als Berechtigungsfilter für die Suche zuweisen. Nehmen Sie zum Beispiel einmal an, dass Sie eine benutzerdefinierte Rollengruppe für eDiscovery-Manager in der US-Niederlassung eines internationalen Unternehmens haben. Sie können den Parameter  _"Users"_ verwenden, um diese Rollengruppe anzugeben (mithilfe der Eigenschaft "Name" der Rollengruppe), und dann den Parameter  _"Filter"_ verwenden, damit nur Postfächer in den USA durchsucht werden können. <br/><br/>Sie können mit diesem Parameter keine Verteilergruppen angeben. |

## <a name="examples-of-changing-search-permissions-filters"></a>Beispiele für das Ändern von Suchberechtigungsfiltern

In diesen Beispielen wird gezeigt, wie Sie die **Cmdlets "Get-ComplianceSecurityFilter"** und **"Set-ComplianceSecurityFilter"** verwenden, um der vorhandenen Liste der Benutzer, denen der Filter zugewiesen ist, einen Benutzer hinzuzufügen oder zu entfernen. Wenn Sie einem Filter Benutzer hinzufügen oder Benutzer daraus entfernen, geben Sie den Benutzer durch seine SMTP-Adresse an. 
  
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

Der **Remove-ComplianceSecurityFilter** wird zum Löschen eines Suchfilters verwendet. Verwenden Sie den  _Parameter "FilterName",_ um den filter anzugeben, den Sie löschen möchten. 
  
## <a name="more-information"></a>Weitere Informationen

- **Wie funktionieren Berechtigungsfilter für die Suche?** Der Berechtigungsfilter wird der Suchabfrage hinzugefügt, wenn eine Inhaltssuche ausgeführt wird. Der Berechtigungsfilter wird durch den Operator **AND** Boolean mit der Suchabfrage verbunden. Sie verfügen beispielsweise über einen Berechtigungsfilter, mit dem Bob alle Suchaktionen für die Postfächer von Mitgliedern der Verteilergruppe "Workers" ausführen kann. Anschließend führt Bob eine Inhaltssuche für alle Postfächer in der Organisation mit der Suchabfrage  `sender:jerry@adatum.com` aus. Da der Berechtigungsfilter und die Suchabfrage logisch durch einen Operator **AND** kombiniert werden, gibt die Suche alle Nachrichten zurück, die von jerry@adatum.com an ein beliebiges Mitglied der Verteilergruppe "Workers" gesendet werden. 
    
- **Was passiert, wenn Sie über mehrere Berechtigungsfilter für die Suche verfügen?** Bei einer Inhaltssuchabfrage werden mehrere Berechtigungsfilter durch den booleschen Operator **ODER** miteinander verknüpft. Daher werden Ergebnisse zurückgegeben, wenn nur einer der Filter zutrifft. Bei einer Inhaltssuche werden dann alle (mit den **ODER**-Operatoren verknüpften) Filter durch den Operator **UND** mit der Suchabfrage kombiniert. Nehmen wir das vorherige Beispiel, in dem bob mit einem Suchfilter nur die Postfächer der Mitglieder der Verteilergruppe "Workers" durchsuchen kann. Wir erstellen dann einen weiteren Filter, der verhindert, dass Bob das Postfach von Phil („Mailbox_Alias - ne 'Phil'“) durchsuchen kann. Außerdem nehmen wir an, dass Phil ein Mitglied der Gruppe „Worker“ ist. Wenn Bob eine Inhaltssuche (aus dem vorherigen Beispiel) für alle Postfächer in der Organisation ausgeführt, werden Suchergebnisse für Phils Postfach zurückgegeben, obwohl Sie filter angewendet haben, um zu verhindern, dass Bob das Postfach von Phil durchsucht. Dies liegt daran, dass der erste Filter, der Bob erlaubt, die Gruppe „Worker“ zu durchsuchen „wahr“ ist. Da Phil Mitglied der Gruppe „Worker“ ist, kann Bob das Postfach von Phil durchsuchen. 
    
- **Funktioniert die Filterung von Suchberechtigungen für inaktive Postfächer?** Ja, Sie können Postfach- und Postfachinhaltsfilter verwenden, um zu begrenzen, wer inaktive Postfächer in Ihrer Organisation durchsuchen kann. Wie bei einem normalen Postfach muss ein inaktives Postfach mit der Empfängereigenschaft konfiguriert werden, die zum Erstellen eines Berechtigungsfilters verwendet wird. Bei Bedarf können Sie mit dem Befehl **"Get-Mailbox -InactiveMailboxOnly"** die Eigenschaften inaktiver Postfächer anzeigen. Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Office 365.](create-and-manage-inactive-mailboxes.md)
    
- **Funktioniert die Filterung von Suchberechtigungen für öffentliche Ordner?** Nein. Wie bereits erläutert, kann die Filterung von Suchberechtigungen nicht verwendet werden, um zu begrenzen, wer öffentliche Ordner in Exchange durchsuchen kann. Beispielsweise können Elemente an Speicherorten für öffentliche Ordner nicht von einem Berechtigungsfilter aus den Suchergebnissen ausgeschlossen werden. 
    
- **Verhindert dies, dass ein Benutzer alle Inhaltsorte in einem bestimmten Dienst durchsuchen kann, auch die Suche nach Inhaltsstandorten in einem anderen Dienst?** Nein. Wie bereits erläutert, müssen Sie einen Suchberechtigungsfilter erstellen, um explizit zu verhindern, dass Benutzer Inhaltsspeicherorte in einem bestimmten Dienst durchsuchen (z. B. verhindern, dass ein Benutzer ein beliebiges Exchange-Postfach oder eine beliebige SharePoint-Website durchsucht). Anders ausgedrückt: Das Erstellen eines Suchberechtigungsfilters, mit dem ein Benutzer alle SharePoint-Websites in der Organisation durchsuchen kann, verhindert nicht, dass dieser Benutzer Postfächer durchsucht. Um beispielsweise SharePoint-Administratoren nur das Durchsuchen von SharePoint-Websites zu ermöglichen, müssen Sie einen Filter erstellen, der verhindert, dass sie Postfächer durchsuchen. Um exchange-Administratoren nur das Durchsuchen von Postfächern zu ermöglichen, müssen Sie einen Filter erstellen, der sie daran hindert, Websites zu durchsuchen.
