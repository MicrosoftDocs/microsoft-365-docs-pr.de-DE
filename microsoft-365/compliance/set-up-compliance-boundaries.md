---
title: Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Erfahren Sie, wie Sie Compliance-Begrenzungen verwenden, um logische Grenzen zu erstellen, die die Speicherorte von Benutzerinhalten steuern, die ein eDiscovery-Manager in Microsoft 365 durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be857277d36d95ac1cd974ccb0c87f2048798450
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194709"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen

Die Anleitungen in diesem Artikel können angewendet werden, wenn Sie entweder Core eDiscovery oder Advanced eDiscovery verwenden, um Untersuchungen zu verwalten.

Compliancegrenzen erstellen logische Grenzen innerhalb einer Organisation, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, OneDrive Konten und SharePoint Websites) steuern, die eDiscovery-Manager durchsuchen können. Außerdem steuern Compliance-Begrenzungen, wer auf eDiscovery-Fälle zugreifen kann, die zur Verwaltung der Rechts-, Personal- oder anderen Untersuchungen in Ihrer Organisation verwendet werden. Die Notwendigkeit von Compliance-Begrenzungen ist häufig für multinationale Unternehmen erforderlich, die geografische Aufsichtsbereiche und Vorschriften berücksichtigen müssen, und für Behörden, die häufig in verschiedene Behörden unterteilt sind. In Microsoft 365 helfen Ihnen Compliance-Begrenzungen, diese Anforderungen zu erfüllen, wenn Sie Inhaltssuchen durchführen und Untersuchungen mit eDiscovery-Fällen verwalten.
  
Wir verwenden das Beispiel in der folgenden Abbildung, um zu erläutern, wie Compliance-Grenzen funktionieren.
  
![Compliancegrenzen bestehen aus Suchberechtigungsfiltern, die den Zugriff auf Behörden und Administratorrollengruppen steuern, die den Zugriff auf eDiscovery-Fälle steuern](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In diesem Beispiel ist Contoso LTD eine Organisation, die aus zwei Tochtergesellschaften besteht: Fourth Coffee und Coho Winery. Das Unternehmen erfordert, dass eDiscovery-Manager und Ermittler nur die Exchange Postfächer, OneDrive Konten und SharePoint Websites in ihrer Organisation durchsuchen können. Darüber hinaus können eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation sehen und nur auf die Fälle zugreifen, in denen sie Mitglied sind. Darüber hinaus können Ermittler in diesem Szenario keine Inhaltsspeicherorte in die Warteschleife setzen oder Inhalte aus einem Fall exportieren. Im Folgenden erfahren Sie, wie Compliance-Begrenzungen diese Anforderungen erfüllen.
  
- Die Suchberechtigungsfilterfunktion in der Inhaltssuche steuert die Inhaltsspeicherorte, die eDiscovery-Manager und Ermittler durchsuchen können. Dies bedeutet, dass eDiscovery-Manager und -Ermittler in der Fourth Coffee-Organisation nur Inhaltsspeicherorte in der Fourth Coffee-Niederlassung durchsuchen können. Die gleiche Einschränkung gilt für die Coho Winery-Tochtergesellschaft.

- [Rollengruppen](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) stellen die folgenden Funktionen für Compliancegrenzen bereit:

  - Steuern, wer die eDiscovery-Fälle im Microsoft 365 Compliance Center sehen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation anzeigen können.

  - Steuern, wer Einem eDiscovery-Fall Mitglieder zuweisen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur den Fällen, von denen sie Mitglied sind, Mitglieder zuordnen können.

  - Steuern Sie die eDiscovery-bezogenen Aufgaben, die Mitglieder ausführen können, indem Sie Rollen hinzufügen oder entfernen, die bestimmte Berechtigungen zuweisen.

Hier sehen Sie den Prozess zum Einrichten von Compliance-Begrenzungen:
  
[Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Schritt 2: Erstellen einer Rollengruppe für jede Organisation](#step-2-create-a-role-group-for-each-agency)

[Schritt 3: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Schritt 4: Erstellen eines eDiscovery-Falls für organisationsinterne Untersuchungen](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Vor dem Einrichten von Compliance-Begrenzungen

- Benutzern muss eine Exchange Online Lizenz zugewiesen werden. Um dies zu überprüfen, verwenden Sie das Cmdlet ["Get-User"](/powershell/module/exchange/get-user) in Exchange Online PowerShell.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden

Der erste Schritt besteht darin, ein Attribut auszuwählen, das Ihre Behörden definiert. Dieses Attribut wird verwendet, um den Suchberechtigungsfilter zu erstellen, der einen eDiscovery-Manager so einschränkt, dass er nur die Inhaltsspeicherorte von Benutzern durchsucht, denen ein bestimmter Wert für dieses Attribut zugewiesen ist. Nehmen wir beispielsweise an, Contoso entscheidet sich für die Verwendung des **Department-Attributs.** Der Wert für dieses Attribut für Benutzer in der Fourth Coffee-Niederlassung wäre  `FourthCoffee`  und der Wert für Benutzer in der Coho-Niederlassung wäre `CohoWinery` . In Schritt 3 verwenden Sie dieses  `attribute:value`  Paar (z. B. *Department:FourthCoffee),* um die Speicherorte von Benutzerinhalten einzuschränken, die eDiscovery-Manager durchsuchen können. 
  
Hier sind einige Beispiele für Benutzerattribute, die Sie für Compliance-Begrenzungen verwenden können:
  
- Unternehmen

- CustomAttribute1 – CustomAttribute15

- Abteilung

- Büro

- CountryOrRegion (aus zwei Buchstaben bestehender Ländercode)

Eine vollständige Liste finden Sie in der vollständigen Liste der unterstützten [Postfachfilter.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>Schritt 2: Erstellen einer Rollengruppe für jede Organisation

Der nächste Schritt besteht darin, die Rollengruppen im Security & Compliance Center zu erstellen, die mit Ihren Behörden abgestimmt sind. Es wird empfohlen, eine Rollengruppe zu erstellen, indem Sie die integrierte Gruppe der eDiscovery-Manager kopieren, die entsprechenden Mitglieder hinzufügen und Rollen entfernen, die möglicherweise nicht Ihren Anforderungen entsprechen. Weitere Informationen zu eDiscovery-bezogenen Rollen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen.](assign-ediscovery-permissions.md)
  
Um die Rollengruppen zu erstellen, wechseln Sie im Security & Compliance Center zur Seite **Berechtigungen**, und erstellen Sie eine Rollengruppe für jedes Team in jeder Organisation, die Compliance-Begrenzungen sowie eDiscovery-Fälle zum Verwalten von Untersuchungen verwendet.
  
Mithilfe des Contoso Compliance-Begrenzungsszenarios müssen vier Rollengruppen erstellt und die entsprechenden Mitglieder hinzugefügt werden.
  
- eDiscovery-Manager von Fourth Coffee

- Fourth Coffee-Ermittler

- eDiscovery-Manager von Coho Winery

- Coho Winery-Ermittler
  
Um die Anforderungen des Contoso Compliance-Begrenzungsszenarios zu erfüllen, würden Sie auch **die** Halte- und **Exportrollen** aus den Rollengruppen der Ermittler entfernen, um zu verhindern, dass Ermittler Haltebereiche für Inhaltsspeicherorte platzieren und Inhalte aus einem Fall exportieren.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Schritt 3: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze

Nachdem Sie Rollengruppen für jede Organisation erstellt haben, besteht der nächste Schritt darin, die Suchberechtigungsfilter zu erstellen, die jede Rollengruppe der jeweiligen Organisation zuordnen und die Compliancegrenze selbst definieren. Sie müssen einen Suchberechtigungsfilter für jede Organisation erstellen. Weitere Informationen zum Erstellen von Sicherheitsberechtigungsfiltern finden Sie unter [Konfigurieren der Berechtigungsfilterung für die Inhaltssuche.](permissions-filtering-for-content-search.md)
  
Dies ist die Syntax, die zum Erstellen eines Suchberechtigungsfilters verwendet wird, der für Compliancegrenzen verwendet wird.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

Nachfolgend finden Sie eine Beschreibung der einzelnen Parameter im Befehl:
  
- `FilterName`: Gibt den Namen des Filters an. Verwenden Sie einen Namen, der die Agentur beschreibt oder identifiziert, in der der Filter verwendet wird.

- `Users`: Gibt die Benutzer oder Gruppen an, die diesen Filter auf die von ihnen ausgeführten Suchaktionen anwenden. Für Compliancegrenzen gibt dieser Parameter die Rollengruppen (die Sie in Schritt 3 erstellt haben) in der Agentur an, für die Sie den Filter erstellen. Beachten Sie, dass es sich um einen mehrwertigen Parameter handelt, sodass Sie eine oder mehrere Rollengruppen durch Kommas getrennt einschließen können.

- `Filters`: Gibt die Suchkriterien für den Filter an. Für die Compliancegrenzen definieren Sie die folgenden Filter. Jeder gilt für einen Inhaltsspeicherort.

    - `Mailbox`: Gibt die Postfächer oder OneDrive Konten an, die die im Parameter definierten Rollengruppen `Users` durchsuchen können. Mit diesem Filter können Mitglieder der Rollengruppe nur die Postfächer oder OneDrive Konten in einer bestimmten Organisation durchsuchen. Beispiel: `"Mailbox_Department -eq 'FourthCoffee'"` .

    - `Site_Path`: Gibt die SharePoint Websites an, die von den im Parameter definierten Rollengruppen `Users` durchsucht werden können. Die  *SharePointURL*  gibt die Websites in der Agentur an, die Mitglieder der Rollengruppe durchsuchen können. Zum Beispiel: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Beachten Sie, dass die `Site` `Site_Path` Und-Filter durch einen **-or-Operator** verbunden sind.

     > [!NOTE]
     > Die Syntax für den `Filters` Parameter enthält eine *Filterliste.* Eine Filterliste ist ein Filter, der einen Postfachfilter und einen durch ein Komma getrennten Websitepfadfilter enthält. Beachten Sie im vorherigen Beispiel, dass ein Komma **Mailbox_MailboxPropertyName** und **Site_Path** trennt: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` . Wenn dieser Filter während der Ausführung einer Inhaltssuche verarbeitet wird, werden aus der Filterliste zwei Suchberechtigungsfilter erstellt: ein Postfachfilter und ein SharePoint Filter. Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern für jede Organisation: ein Suchberechtigungsfilter für das Postfachattribut und ein Filter für die SharePoint Websiteattribute. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine Frage der Präferenz.

- `Action`: Gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Würde beispielsweise  `-Action Search` den Filter nur anwenden, wenn Mitglieder der im Parameter definierten Rollengruppe eine Suche `Users` ausführen. In diesem Fall würde der Filter beim Exportieren von Suchergebnissen nicht angewendet. Verwenden Sie für Compliance-Begrenzungen,  `-Action All` dass der Filter auf alle Suchaktionen angewendet wird. 

    Eine Liste der Suchaktionen finden Sie im Abschnitt "New-ComplianceSecurityFilter" unter Konfigurieren der [Berechtigungsfilterung für die Inhaltssuche.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Nachfolgend finden Sie Beispiele für die beiden Suchberechtigungsfilter, die zur Unterstützung des Szenarios mit den Compliance-Begrenzungen bei Contoso erstellt werden würden. Beide Beispiele umfassen eine durch Trennzeichen getrennte Filterliste, bei der die Postfach- und Websitefilter in den gleichen Suchberechtigungsfilter eingeschlossen sind und durch ein Komma getrennt sind.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho-Weinfass

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>Schritt 4: Erstellen eines eDiscovery-Falls für organisationsinterne Untersuchungen

Der letzte Schritt besteht darin, einen Core eDiscovery-Fall oder Advanced eDiscovery Fall im Microsoft 365 Compliance Center zu erstellen und dann die Rollengruppe hinzuzufügen, die Sie in Schritt 2 als Mitglied des Falls erstellt haben. Dies führt zu zwei wichtigen Merkmalen der Verwendung von Compliance-Begrenzungen:
  
- Nur Mitglieder der Rollengruppe, die dem Fall hinzugefügt wurden, können den Fall im Security & Compliance Center anzeigen und darauf zugreifen. Wenn beispielsweise die Rollengruppe "Fourth Coffee Investigators" das einzige Mitglied eines Falls ist, können Mitglieder der Rollengruppe "Fourth Coffee eDiscovery-Manager" (oder Mitglieder einer anderen Rollengruppe) den Fall nicht sehen oder darauf zugreifen.

- Wenn ein Mitglied der Rollengruppe, die einem Fall zugewiesen ist, eine dem Fall zugeordnete Suche ausführt, kann er nur die Inhaltsspeicherorte in ihrer Organisation durchsuchen (die durch den Suchberechtigungsfilter definiert wird, den Sie in Schritt 3 erstellt haben).

So erstellen Sie einen Fall und weisen Mitglieder zu:

1. Wechseln Sie zur **Core eDiscovery-** oder **Advanced eDiscovery-Seite** im Microsoft 365 Compliance Center, und erstellen Sie einen Fall.

2. Klicken Sie in der Liste der Fälle auf den Namen des erstellten Falls.

3. Fügen Sie dem Fall Rollengruppen als Mitglieder hinzu. Anweisungen finden Sie in einem der folgenden Artikel:

   - [Hinzufügen von Mitgliedern zu einem Core eDiscovery-Fall](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Hinzufügen von Mitgliedern zu einem Advanced eDiscovery Fall](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> Beim Hinzufügen einer Rollengruppe zu einem Fall können Sie nur die Rollengruppen hinzufügen, in denen Sie Mitglied sind.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen

MitHilfe von Suchberechtigungsfiltern können Sie auch steuern, wo Inhalte für den Export weitergeleitet werden und welches Rechenzentrum beim Durchsuchen von Inhaltsspeicherorten in einer [SharePoint Multi-Geo Umgebung](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)durchsucht werden kann.
  
- **Exportieren von Suchergebnissen:** Sie können die Suchergebnisse aus Exchange Postfächern, SharePoint Websites und OneDrive Konten aus einem bestimmten Rechenzentrum exportieren. Dies bedeutet, dass Sie den Rechenzentrumsspeicherort angeben können, aus dem suchergebnisse exportiert werden.

    Verwenden Sie den Parameter **Region** für **New-ComplianceSecurityFilter-** oder **Set-ComplianceSecurityFilter-Cmdlets,** um zu erstellen oder zu ändern, welches Rechenzentrum der Export durchläuft.
  
    |**Übergebener Wert**|**Standort des Rechenzentrums**|
    |:-----|:-----|
    |NAM  <br/> |Nordamerika (Rechenzentren befinden sich in den USA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN <br/> |Kanada|
    |||

- **Inhaltssuchen weiterleiten:** Sie können die Inhaltssuchen von SharePoint Websites und OneDrive-Konten an ein Satellitendatencenter weiterleiten. Dies bedeutet, dass Sie den Rechenzentrumsspeicherort angeben können, an dem Suchvorgänge ausgeführt werden.

    Verwenden Sie einen der folgenden Werte für den Parameter **Region,** um den Rechenzentrumsspeicherort zu steuern, in dem suchvorgänge ausgeführt werden, wenn sie SharePoint Websites und OneDrive Konten durchsuchen. 
  
    |**Übergebener Wert**|**Rechenzentrumsroutingstandorte für SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |Uns  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN  <br/> |Uns  <br/> |
    |AUS  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |KOR  <br/> |Das Standarddatencenter der Organisation  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |IND  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |Lam  <br/> |Uns  <br/> |
    |Noch  <br/> |Europa |
    |Bh  <br/> |Nordamerikanische Rechenzentren |
    |||

   Wenn Sie den Parameter **Region** für einen Suchberechtigungsfilter nicht angeben, wird die primäre SharePoint Region der Organisation durchsucht. Suchergebnisse werden in das nächstgelegene Rechenzentrum exportiert.

   Zur Vereinfachung des Konzepts steuert der Parameter **Region** das Datencenter, das zum Suchen nach Inhalten in SharePoint und OneDrive verwendet wird. Dies gilt nicht für die Suche nach Inhalten in Exchange, da Exchange Inhaltssuchen nicht an den geografischen Standort von Rechenzentren gebunden sind. Außerdem kann derselbe Wert des **Regionsparameters** auch das Rechenzentrum bestimmen, durch das Exporte weitergeleitet werden. Dies ist häufig erforderlich, um die Verschiebung von Daten über geografische Grenzen hinweg zu steuern.

> [!NOTE]
> Wenn Sie Advanced eDiscovery verwenden, steuert der Parameter **Region** nicht den Bereich, aus dem Daten exportiert werden. Die Daten werden vom zentralen Standort der Organisation exportiert. Außerdem ist die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort von Rechenzentren gebunden. Alle Rechenzentren werden durchsucht. Weitere Informationen zu Advanced eDiscovery finden Sie unter [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Hier sind Beispiele für die Verwendung des Parameters **Region** beim Erstellen von Suchberechtigungsfiltern für Compliancegrenzen. Dabei wird davon ausgegangen, dass sich die Vierte Coffee-Tochtergesellschaft in Nordamerika befindet und dass sich coho-Cafés in Europa befinden. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Beachten Sie beim Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen die folgenden Punkte.
  
- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Alle Rechenzentren werden durchsucht, wenn Sie Postfächer durchsuchen. Verwenden Sie zum Einschränken des Bereichs, in dem Exchange Postfächer durchsucht werden, den Parameter **Filters** beim Erstellen oder Ändern eines Suchberechtigungsfilters.

- Wenn es für einen eDiscovery-Manager erforderlich ist, in mehreren SharePoint Regionen zu suchen, müssen Sie ein anderes Benutzerkonto für diesen eDiscovery-Manager erstellen, das im Suchberechtigungsfilter verwendet werden kann, um die Region anzugeben, in der sich die SharePoint Websites oder OneDrive-Konten befinden. Weitere Informationen zum Einrichten finden Sie im Abschnitt "Suchen nach Inhalten in einer SharePoint Multi-Geo Umgebung" in der [Inhaltssuche.](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Bei der Suche nach Inhalten in SharePoint und OneDrive leitet der **Parameter "Region"** Suchvorgänge an den primären oder Satellitenstandort weiter, an dem der eDiscovery-Manager eDiscovery-Untersuchungen durchführt. Wenn ein eDiscovery-Manager SharePoint sucht und Websites außerhalb der Region OneDrive, die im Suchberechtigungsfilter angegeben ist, werden keine Suchergebnisse zurückgegeben.

- Beim Exportieren von Suchergebnissen aus Core eDiscovery werden Inhalte aus allen Inhaltsspeicherorten (einschließlich Exchange, Skype for Business, SharePoint, OneDrive und anderen Diensten, die Sie mithilfe des Inhaltssuche-Tools durchsuchen können) in den Azure Storage Speicherort im Rechenzentrum hochgeladen, der vom Parameter **Region** angegeben wird. Dies hilft Organisationen, die Compliance zu halten, indem inhalte nicht über kontrollierte Grenzen exportiert werden dürfen. Wenn im Suchberechtigungsfilter keine Region angegeben ist, werden Inhalte in das primäre Rechenzentrum der Organisation hochgeladen.

  Beim Exportieren von Inhalten aus Advanced eDiscovery können Sie nicht steuern, wo Inhalte hochgeladen werden, indem Sie den Parameter **Region** verwenden. Inhalte werden an einen Azure Storage Speicherort in einem Rechenzentrum am zentralen Standort Ihrer Organisation hochgeladen. Eine Liste der geografischen Standorte basierend auf Ihrem zentralen Standort finden Sie unter [Microsoft 365 Multi-Geo eDiscovery-Konfiguration.](../enterprise/multi-geo-ediscovery-configuration.md)

- Sie können einen vorhandenen Suchberechtigungsfilter bearbeiten, um die Region hinzuzufügen oder zu ändern, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Verwenden von Compliancegrenzen für SharePoint Hubwebsites

[SharePoint Hubwebsites](/sharepoint/dev/features/hub-site/hub-site-overview) entsprechen häufig denselben geografischen oder Agenturgrenzen wie eDiscovery-Compliance-Grenzen. Das bedeutet, dass Sie die Website-ID-Eigenschaft der Hubwebsite verwenden können, um eine Compliance-Grenze zu erstellen. Verwenden Sie dazu das Cmdlet ["Get-SPOHubSite"](/powershell/module/sharepoint-online/get-spohubsite#examples) in SharePoint Online-PowerShell, um die SiteId für die Hubwebsite abzurufen, und verwenden Sie dann diesen Wert für die Abteilungs-ID-Eigenschaft, um einen Suchberechtigungsfilter zu erstellen.

Verwenden Sie die folgende Syntax, um einen Suchberechtigungsfilter für eine SharePoint Hubwebsite zu erstellen:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Hier sehen Sie ein Beispiel für das Erstellen eines Suchberechtigungsfilters für eine Hubwebsite für die Coho-Einrichtung:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Compliance-Begrenzungseinschränkungen

Beachten Sie beim Verwalten von eDiscovery-Fällen und -Untersuchungen, die Compliance-Grenzen verwenden, die folgenden Einschränkungen.
  
- Beim Erstellen und Ausführen einer Suche können Sie Inhaltsspeicherorte auswählen, die sich außerhalb Ihrer Organisation befinden. Aufgrund des Filters für Suchberechtigungen sind Inhalte aus diesen Speicherorten jedoch nicht in den Suchergebnissen enthalten.

- Compliance-Begrenzungen gelten nicht für Haltebereiche in eDiscovery-Fällen. Dies bedeutet, dass ein eDiscovery-Manager in einer Organisation einen Benutzer in einer anderen Organisation im Haltebereich platzieren kann. Die Compliance-Begrenzung wird jedoch erzwungen, wenn der eDiscovery-Manager die Inhaltsspeicherorte des Benutzers durchsucht, der in den Haltebereich gesetzt wurde. Dies bedeutet, dass der eDiscovery-Manager nicht in der Lage ist, die Inhaltsspeicherorte des Benutzers zu durchsuchen, auch wenn er den Benutzer im Haltebereich platzieren konnte.

    Außerdem gelten Haltestatistiken nur für Inhaltsspeicherorte in der Organisation.

- Wenn Ihnen ein Suchberechtigungsfilter (ein Postfach oder ein Websitefilter) zugewiesen ist und Sie versuchen, nicht indizierte Elemente für eine Suche zu exportieren, die alle SharePoint Websites in Ihrer Organisation enthält, wird die folgende Fehlermeldung angezeigt: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Wenn Ihnen ein Suchberechtigungsfilter zugewiesen ist und Sie nicht indizierte Elemente aus SharePoint exportieren möchten, müssen Sie die Suche erneut ausführen und bestimmte SharePoint zu durchsuchende Websites einschließen. Andernfalls können Sie nur indizierte Elemente aus einer Suche exportieren, die alle SharePoint Websites enthält. Weitere Informationen zu den Optionen beim Exportieren von Suchergebnissen finden Sie unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md#step-1-prepare-search-results-for-export)

- Suchberechtigungsfilter werden nicht auf öffentliche Exchange-Ordner angewendet.

## <a name="more-information"></a>Weitere Informationen

- Wenn ein Postfach nicht mehr lizenziert oder vorläufig gelöscht wird, wird der Benutzer nicht mehr innerhalb der Compliance-Grenze berücksichtigt. Wenn beim Löschen des Postfachs eine Aufbewahrung aufgehoben wurde, unterliegt der im Postfach aufbewahrte Inhalt weiterhin einer Compliance-Grenze oder einem Suchberechtigungsfilter.

- Wenn Compliance-Begrenzungen und Suchberechtigungsfilter für einen Benutzer implementiert sind, wird empfohlen, das Postfach eines Benutzers und nicht dessen OneDrive Konto nicht zu löschen. Mit anderen Worten: Wenn Sie das Postfach eines Benutzers löschen, sollten Sie auch das OneDrive Konto des Benutzers entfernen, da mailbox_RecipientFilter zum Erzwingen des Suchberechtigungsfilters für OneDrive verwendet wird.

- Compliancegrenzen und Suchberechtigungsfilter hängen von Attributen ab, die für Inhalte in Exchange, OneDrive und SharePoint gestempelt werden, sowie von der nachfolgenden Indizierung dieses stempelten Inhalts.

- Es wird nicht empfohlen, Ausschlussfilter (z. B. die Verwendung `-not()` in einem Suchberechtigungsfilter) für eine inhaltsbasierte Compliancegrenze zu verwenden. Die Verwendung eines Ausschlussfilters kann unerwartete Ergebnisse haben, wenn Inhalte mit kürzlich aktualisierten Attributen nicht indiziert wurden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer können Suchberechtigungsfilter erstellen und verwalten (mit New-ComplianceSecurityFilter und Set-ComplianceSecurityFilter Cmdlets)?**
  
Zum Erstellen, Anzeigen und Ändern von Suchberechtigungsfiltern müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Microsoft 365 Compliance Center sein.
  
**Wenn ein eDiscovery-Manager mehr als einer Rollengruppe zugewiesen ist, die mehrere Behörden umfasst, wie wird nach Inhalten in einer Oder der anderen Agentur gesucht?**
  
Der eDiscovery-Manager kann der Suchabfrage Parameter hinzufügen, die die Suche auf eine bestimmte Agentur beschränken. Wenn eine Organisation beispielsweise die **Eigenschaft CustomAttribute10** angegeben hat, um Behörden zu unterscheiden, können sie Folgendes an ihre Suchabfrage anhängen, um Postfächer und OneDrive Konten in einer bestimmten Organisation zu durchsuchen: `CustomAttribute10:<value>` .
  
**Was geschieht, wenn der Wert des Attributs, das als Complianceattribut in einem Suchberechtigungsfilter verwendet wird, geändert wird?**
  
Es dauert bis zu drei Tage, bis ein Suchberechtigungsfilter die Compliancegrenze erzwingt, wenn der Wert des im Filter verwendeten Attributs geändert wird. Nehmen wir beispielsweise im Contoso-Szenario an, dass ein Benutzer in der Fourth Coffee-Agentur an die Coho-Einrichtung weitergeleitet wird. Daher wird der Wert des **Department-Attributs** für das Benutzerobjekt von *FourthCoffee* in *CohoWinery* geändert. In dieser Situation erhalten Fourth Coffee eDiscovery und Dies Suchergebnisse für diesen Benutzer für bis zu drei Tage, nachdem das Attribut geändert wurde. Ebenso dauert es bis zu drei Tage, bis eDiscovery-Manager und Ermittler von CohoDiscovery Suchergebnisse für den Benutzer erhalten.
  
**Kann ein eDiscovery-Manager Inhalte von zwei separaten Compliance-Grenzen anzeigen?**
  
Ja, dies kann beim Durchsuchen von Exchange Postfächern durch Hinzufügen des eDiscovery-Managers zu Rollengruppen erfolgen, die für beide Behörden sichtbar sind. Beim Durchsuchen SharePoint Websites und OneDrive Konten kann ein eDiscovery-Manager jedoch nur dann nach Inhalten in unterschiedlichen Compliancegrenzen suchen, wenn sich die Behörden am selben Geografischen Standort befinden. **Hinweis:** Diese Einschränkung für Websites gilt nicht in Advanced eDiscovery, da die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort gebunden ist.
  
**Funktionieren Suchberechtigungsfilter für eDiscovery-Fallarchive, Microsoft 365 Aufbewahrungsrichtlinien oder DLP?**
  
Nein, nicht zu diesem Zeitpunkt.
  
**Kann ich weiterhin nach SharePoint suchen, wenn ich eine Region zum Steuern des Inhaltsexports angibt, aber keine SharePoint Organisation in dieser Region habe?**
  
Wenn die im Suchberechtigungsfilter angegebene Region in Ihrer Organisation nicht vorhanden ist, wird die Standardregion durchsucht.
  
**Wie viele Suchberechtigungsfilter können maximal in einer Organisation erstellt werden?**
  
Es gibt keine Beschränkung für die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können. Die Suchleistung wird jedoch beeinträchtigt, wenn mehr als 100 Suchberechtigungsfilter vorhanden sind. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzigen Suchberechtigungsfilter kombinieren, wann immer möglich.
