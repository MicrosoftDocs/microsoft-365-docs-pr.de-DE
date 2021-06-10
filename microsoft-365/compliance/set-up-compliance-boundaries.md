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
ms.openlocfilehash: 1a84bc77cb78a9da3cfe873849a4148e55501137
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878028"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen

Die Anleitungen in diesem Artikel können angewendet werden, wenn Sie entweder Core eDiscovery oder Advanced eDiscovery verwenden, um Untersuchungen zu verwalten.

Compliance-Begrenzungen erstellen logische Grenzen innerhalb einer Organisation, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, OneDrive Konten und SharePoint Websites) steuern, die eDiscovery-Manager durchsuchen können. Außerdem steuern Compliance-Begrenzungen, wer auf eDiscovery-Fälle zugreifen kann, die zur Verwaltung der Rechts-, Personal- oder anderen Untersuchungen in Ihrer Organisation verwendet werden. Die Notwendigkeit von Compliance-Begrenzungen ist häufig für multinationale Unternehmen erforderlich, die geografische Aufsichtsbereiche und Vorschriften berücksichtigen müssen, und für Behörden, die häufig in verschiedene Behörden unterteilt sind. In Microsoft 365 helfen Ihnen Compliance-Grenzen, diese Anforderungen zu erfüllen, wenn Sie Inhaltssuchen durchführen und Untersuchungen mit eDiscovery-Fällen verwalten.
  
Wir verwenden das Beispiel in der folgenden Abbildung, um zu erläutern, wie Compliance-Grenzen funktionieren.
  
![Compliancegrenzen bestehen aus Suchberechtigungsfiltern, die den Zugriff auf Behörden und Administratorrollengruppen steuern, die den Zugriff auf eDiscovery-Fälle steuern](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In diesem Beispiel ist Contoso LTD eine Organisation, die aus zwei Tochtergesellschaften besteht: Fourth Coffee und Coho Winery. Das Unternehmen erfordert, dass eDiscovery-Manager und Ermittler nur die Exchange Postfächer, OneDrive Konten und SharePoint Websites in ihrer Organisation durchsuchen können. Darüber hinaus können eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation sehen und nur auf die Fälle zugreifen, in denen sie Mitglied sind. Darüber hinaus können Ermittler in diesem Szenario keine Inhaltsspeicherorte in die Warteschleife setzen oder Inhalte aus einem Fall exportieren. Im Folgenden erfahren Sie, wie Compliance-Begrenzungen diese Anforderungen erfüllen.
  
- Die Suchberechtigungsfilterfunktion in der Inhaltssuche steuert die Inhaltsspeicherorte, die eDiscovery-Manager und Ermittler durchsuchen können. Dies bedeutet, dass eDiscovery-Manager und -Ermittler in der Fourth Coffee-Organisation nur Inhaltsspeicherorte in der Fourth Coffee-Niederlassung durchsuchen können. Die gleiche Einschränkung gilt für die Coho Winery-Tochtergesellschaft.

- Rollengruppen stellen die folgenden Funktionen für Compliancegrenzen bereit:

  - Steuern, wer die eDiscovery-Fälle im Security & Compliance Center sehen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation anzeigen können.

  - Steuern, wer Einem eDiscovery-Fall Mitglieder zuweisen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur den Fällen, von denen sie Mitglied sind, Mitglieder zuordnen können.

  - Steuern Sie die eDiscovery-bezogenen Aufgaben, die Mitglieder ausführen können, indem Sie Rollen hinzufügen oder entfernen, die bestimmte Berechtigungen zuweisen.

Hier sehen Sie den Prozess zum Einrichten von Compliance-Begrenzungen:
  
[Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Schritt 2: Senden einer Anforderung an den Microsoft-Support zum Synchronisieren des Benutzerattributs mit OneDrive Konten](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Schritt 3: Erstellen einer Rollengruppe für jede Organisation](#step-3-create-a-role-group-for-each-agency)

[Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Schritt 5: Erstellen eines eDiscovery-Falls für organisationsinterne Untersuchungen](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Vor dem Einrichten von Compliance-Begrenzungen

Sie müssen die folgenden Voraussetzungen erfüllen, bevor das Azure Active Directory (Azure AD)-Attribut, das Sie (in Schritt 1) identifizieren, erfolgreich mit dem OneDrive Konto eines Benutzers (in Schritt 2) synchronisiert werden kann:

- Benutzern müssen eine Exchange Online-Lizenz und eine SharePoint Onlinelizenz zugewiesen werden.

- Benutzerpostfächer müssen mindestens 10 MB groß sein. Wenn das Postfach eines Benutzers weniger als 10 MB beträgt, wird das Attribut, das zum Definieren Ihrer Behörden verwendet wird, nicht mit dem OneDrive Konto des Benutzers synchronisiert.

- Compliancegrenzen und die Zum Erstellen von Suchberechtigungsfiltern verwendeten Attribute erfordern, dass Azure Active Directory (Azure AD)-Attribute mit Benutzerpostfächern synchronisiert werden. Um zu überprüfen, ob die attribute, die Sie verwenden möchten, synchronisiert wurden, führen Sie das Cmdlet ["Get-User"](/powershell/module/exchange/get-user) in Exchange Online PowerShell aus. Die Ausgabe dieses Cmdlets zeigt die Azure AD-Attribute an, die mit Exchange Online synchronisiert sind.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden

Der erste Schritt besteht darin, ein Azure AD-Attribut auszuwählen, das Ihre Behörden definiert. Dieses Attribut wird verwendet, um den Suchberechtigungsfilter zu erstellen, der einen eDiscovery-Manager so einschränkt, dass er nur die Inhaltsspeicherorte von Benutzern durchsucht, denen ein bestimmter Wert für dieses Attribut zugewiesen ist. Nehmen wir beispielsweise an, Contoso entscheidet sich für die Verwendung des **Department-Attributs.** Der Wert für dieses Attribut für Benutzer in der Fourth Coffee-Niederlassung wäre  `FourthCoffee`  und der Wert für Benutzer in der Coho-Niederlassung wäre `CohoWinery` . In Schritt 4 verwenden Sie dieses  `attribute:value`  Paar (z. B. *Department:FourthCoffee),* um die Speicherorte von Benutzerinhalten einzuschränken, die eDiscovery-Manager durchsuchen können. 
  
Hier ist eine Liste der Azure AD-Benutzerattribute, die Sie für Compliance-Grenzen verwenden können:
  
- Unternehmen

- CustomAttribute1 – CustomAttribute15

- Abteilung

- Büro

- C (Aus zwei Buchstaben bestehender Ländercode) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup>Dieses Attribut ist der CountryOrRegion-Eigenschaft zugeordnet, die durch Ausführen des Cmdlets **"Get-User"** in Exchange Online PowerShell zurückgegeben wird. Das Cmdlet gibt den lokalisierten Ländernamen zurück, der aus dem aus zwei Buchstaben bestehendem Ländercode übersetzt wird. Weitere Informationen finden Sie in der Beschreibung der Parameter "CountryOrRegion" im Referenzartikel zum [Cmdlet "Set-User".](/powershell/module/exchange/set-user)

Obwohl mehr Benutzerattribute verfügbar sind, insbesondere für Exchange Postfächer, sind die oben aufgeführten Attribute die einzigen, die derzeit von OneDrive unterstützt werden.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Schritt 2: Senden einer Anforderung an den Microsoft-Support zum Synchronisieren des Benutzerattributs mit OneDrive Konten

> [!IMPORTANT]
> Dieser Schritt ist nicht mehr erforderlich. Ab Juni 2021 gelten Postfachfilter für OneDrive for Business. Supportanfragen zum Synchronisieren des Attributs mit OneDrive werden abgelehnt, da dies nicht mehr erforderlich ist. Dieser Artikel wird in kürze aktualisiert.

Der nächste Schritt besteht darin, eine Anforderung an den Microsoft-Support zu senden, um das azure AD-Attribut, das Sie in Schritt 1 ausgewählt haben, mit allen OneDrive Konten in Ihrer Organisation zu synchronisieren. Nach dieser Synchronisierung wird das Attribut (und sein Wert), das Sie in Schritt 1 ausgewählt haben, einer ausgeblendeten verwalteten Eigenschaft namens `ComplianceAttribute` zugeordnet. Mit diesem Attribut erstellen Sie den Suchberechtigungsfilter für OneDrive in Schritt 4.
  
Geben Sie die folgenden Informationen ein, wenn Sie die Anforderung an den Microsoft-Support senden:
  
- Der Standarddomänenname Ihrer Organisation

- Der Name des Azure AD-Attributs (aus Schritt 1)

- Der folgende Titel oder die Beschreibung des Zwecks der Supportanfrage: "Aktivieren OneDrive for Business Synchronisierung mit Azure AD für Compliancesicherheitsfilter". Dadurch wird die Anforderung an das eDiscovery-Entwicklungsteam weitergeleitet, das die Anforderung implementiert.

Nachdem die Technische Änderung vorgenommen und das Attribut mit OneDrive synchronisiert wurde, sendet Ihnen der Microsoft-Support die Buildnummer, in der die Änderung vorgenommen wurde, und ein geschätztes Bereitstellungsdatum. Der Bereitstellungsprozess dauert in der Regel 4 bis 6 Wochen, nachdem Sie die Supportanfrage übermittelt haben.
  
> [!IMPORTANT]
> Sie können die Schritte 3 bis 5 abschließen, bevor diese Attributänderung bereitgestellt wird. Beim Ausführen von Inhaltssuchen werden jedoch erst Dokumente aus OneDrive Konten zurückgegeben, die in einem Suchberechtigungsfilter angegeben sind, nachdem die Attributsynchronisierung bereitgestellt wurde.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Schritt 3: Erstellen einer Rollengruppe für jede Organisation

Der nächste Schritt besteht darin, die Rollengruppen im Security & Compliance Center zu erstellen, die mit Ihren Behörden abgestimmt sind. Es wird empfohlen, eine Rollengruppe zu erstellen, indem Sie die integrierte Gruppe der eDiscovery-Manager kopieren, die entsprechenden Mitglieder hinzufügen und Rollen entfernen, die möglicherweise nicht Ihren Anforderungen entsprechen. Weitere Informationen zu eDiscovery-bezogenen Rollen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen.](assign-ediscovery-permissions.md)
  
Um die Rollengruppen zu erstellen, wechseln Sie im Security & Compliance Center zur Seite **Berechtigungen**, und erstellen Sie eine Rollengruppe für jedes Team in jeder Organisation, die Compliance-Begrenzungen sowie eDiscovery-Fälle zum Verwalten von Untersuchungen verwendet.
  
Mithilfe des Contoso Compliance-Begrenzungsszenarios müssen vier Rollengruppen erstellt und die entsprechenden Mitglieder hinzugefügt werden.
  
- eDiscovery-Manager von Fourth Coffee

- Fourth Coffee-Ermittler

- eDiscovery-Manager von Coho Winery

- Coho Winery-Ermittler
  
Um die Anforderungen des Contoso Compliance-Begrenzungsszenarios zu erfüllen, würden Sie auch **die** Halte- und **Exportrollen** aus den Rollengruppen der Ermittler entfernen, um zu verhindern, dass Ermittler Haltebereiche für Inhaltsspeicherorte platzieren und Inhalte aus einem Fall exportieren.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze

Nachdem Sie Rollengruppen für jede Organisation erstellt haben, besteht der nächste Schritt darin, die Suchberechtigungsfilter zu erstellen, die jede Rollengruppe der jeweiligen Organisation zuordnen und die Compliancegrenze selbst definieren. Sie müssen einen Suchberechtigungsfilter für jede Organisation erstellen. Weitere Informationen zum Erstellen von Sicherheitsberechtigungsfiltern finden Sie unter [Konfigurieren der Berechtigungsfilterung für die Inhaltssuche.](permissions-filtering-for-content-search.md)
  
Dies ist die Syntax, die zum Erstellen eines Suchberechtigungsfilters verwendet wird, der für Compliancegrenzen verwendet wird.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Nachfolgend finden Sie eine Beschreibung der einzelnen Parameter im Befehl:
  
- `FilterName`: Gibt den Namen des Filters an. Verwenden Sie einen Namen, der die Agentur beschreibt oder identifiziert, in der der Filter verwendet wird.

- `Users`: Gibt die Benutzer oder Gruppen an, die diesen Filter auf die von ihnen ausgeführten Suchaktionen anwenden. Für Compliancegrenzen gibt dieser Parameter die Rollengruppen (die Sie in Schritt 3 erstellt haben) in der Agentur an, für die Sie den Filter erstellen. Beachten Sie, dass es sich um einen mehrwertigen Parameter handelt, sodass Sie eine oder mehrere Rollengruppen durch Kommas getrennt einschließen können.

- `Filters`: Gibt die Suchkriterien für den Filter an. Für die Compliancegrenzen definieren Sie die folgenden Filter. Jeder gilt für einen Inhaltsspeicherort. 

    - `Mailbox`: Gibt die Postfächer an, die von den im Parameter definierten Rollengruppen  `Users` durchsucht werden können. Für Compliance-Grenzen ist  *ComplianceAttribute*  dasselbe Attribut, das Sie in Schritt 1 identifiziert haben, und  *AttributeValue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die Postfächer in einer bestimmten Organisation durchsuchen. Beispiel: `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: Gibt die OneDrive Konten an, die von den im Parameter definierten Rollengruppen `Users` durchsucht werden können. Verwenden Sie für den OneDrive Filter die tatsächliche `ComplianceAttribute` Zeichenfolge. Dies ist demselben Attribut zugeordnet, das Sie in Schritt 1 identifiziert haben und das aufgrund der Supportanfrage, die Sie in Schritt 2 übermittelt haben, mit OneDrive Konten synchronisiert wird. *AttributeValue* gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die OneDrive Konten in einer bestimmten Organisation durchsuchen. Beispiel: `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: Gibt die SharePoint Websites an, die von den im Parameter definierten Rollengruppen `Users` durchsucht werden können. Die  *SharePointURL*  gibt die Websites in der Agentur an, die Mitglieder der Rollengruppe durchsuchen können. Zum Beispiel: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Beachten Sie, dass die `Site` `Site_Path` Und-Filter durch einen **-or-Operator** verbunden sind.

     > [!NOTE]
     > Die Syntax für den `Filters` Parameter enthält eine *Filterliste.* Eine Filterliste ist ein Filter, der einen Postfachfilter und einen durch ein Komma getrennten Websitefilter enthält. Beachten Sie im vorherigen Beispiel, dass ein Komma **Mailbox_ComplianceAttribute** und **Site_ComplianceAttribute** trennt: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` . Wenn dieser Filter während der Ausführung einer Inhaltssuche verarbeitet wird, werden aus der Filterliste zwei Suchberechtigungsfilter erstellt: ein Postfachfilter und ein Websitefilter. Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern für jede Organisation: ein Suchberechtigungsfilter für das Postfachattribut und ein Filter für die Websiteattribute. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine Frage der Präferenz.

- `Action`: Gibt den Typ der Suchaktion an, auf die der Filter angewendet wird. Würde beispielsweise  `-Action Search` den Filter nur anwenden, wenn Mitglieder der im Parameter definierten Rollengruppe eine Suche `Users` ausführen. In diesem Fall würde der Filter beim Exportieren von Suchergebnissen nicht angewendet. Verwenden Sie für Compliance-Begrenzungen,  `-Action All` dass der Filter auf alle Suchaktionen angewendet wird. 

    Eine Liste der Suchaktionen finden Sie im Abschnitt "New-ComplianceSecurityFilter" unter Konfigurieren der [Berechtigungsfilterung für die Inhaltssuche.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Nachfolgend finden Sie Beispiele für die beiden Suchberechtigungsfilter, die zur Unterstützung des Szenarios mit den Compliance-Begrenzungen bei Contoso erstellt werden würden. Beide Beispiele umfassen eine durch Trennzeichen getrennte Filterliste, bei der die Postfach- und Websitefilter in den gleichen Suchberechtigungsfilter eingeschlossen sind und durch ein Komma getrennt sind.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho-Weinfass

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Schritt 5: Erstellen eines eDiscovery-Falls für organisationsinterne Untersuchungen

Der letzte Schritt besteht darin, einen Core eDiscovery-Fall oder Advanced eDiscovery Fall im Microsoft 365 Compliance Center zu erstellen und dann die Rollengruppe hinzuzufügen, die Sie in Schritt 3 als Mitglied des Falls erstellt haben. Dies führt zu zwei wichtigen Merkmalen der Verwendung von Compliance-Begrenzungen:
  
- Nur Mitglieder der Rollengruppe, die dem Fall hinzugefügt wurden, können den Fall im Security & Compliance Center anzeigen und darauf zugreifen. Wenn beispielsweise die Rollengruppe "Fourth Coffee Investigators" das einzige Mitglied eines Falls ist, können Mitglieder der Rollengruppe "Fourth Coffee eDiscovery-Manager" (oder Mitglieder einer anderen Rollengruppe) den Fall nicht sehen oder darauf zugreifen.

- Wenn ein Mitglied der Rollengruppe, die einem Fall zugewiesen ist, eine dem Fall zugeordnete Suche ausführt, kann er nur die Inhaltsspeicherorte in ihrer Organisation durchsuchen (die durch den Suchberechtigungsfilter definiert ist, den Sie in Schritt 4 erstellt haben).

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
  
    |**Übergebener Wert**|**Routingspeicherorte für Rechenzentren für SharePoint**|
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
> Wenn Sie Advanced eDiscovery verwenden, steuert der Parameter **Region** nicht den Bereich, aus dem Daten exportiert werden. Daten werden aus dem primären Rechenzentrum der Organisation exportiert. Außerdem ist die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort von Rechenzentren gebunden. Alle Rechenzentren werden durchsucht. Weitere Informationen zu Advanced eDiscovery finden Sie unter [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Hier sind Beispiele für die Verwendung des Parameters **Region** beim Erstellen von Suchberechtigungsfiltern für Compliancegrenzen. Dabei wird davon ausgegangen, dass sich die vierte Coffee-Tochtergesellschaft in Nordamerika befindet und dass sich Coho Coffee in Europa befindet. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Beachten Sie beim Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen die folgenden Punkte.
  
- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Alle Rechenzentren werden durchsucht, wenn Sie Postfächer durchsuchen. Um den Umfang zu beschränken, in dem Exchange Postfächer durchsucht werden, verwenden Sie **den** Filterparameter beim Erstellen oder Ändern eines Suchberechtigungsfilters. 

- Wenn es für einen eDiscovery-Manager erforderlich ist, in mehreren SharePoint Regionen zu suchen, müssen Sie ein anderes Benutzerkonto für diesen eDiscovery-Manager erstellen, das im Suchberechtigungsfilter verwendet werden kann, um die Region anzugeben, in der sich die SharePoint Websites oder OneDrive-Konten befinden. Weitere Informationen zum Einrichten finden Sie im Abschnitt "Suchen nach Inhalten in einer SharePoint Multi-Geo Umgebung" in der [Inhaltssuche.](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Bei der Suche nach Inhalten in SharePoint und OneDrive leitet der **Parameter** Region Suchvorgänge entweder an den primären oder Satellitenstandort weiter, an dem der eDiscovery-Manager eDiscovery-Untersuchungen durchführt. Wenn ein eDiscovery-Manager SharePoint sucht und Websites außerhalb der Region OneDrive, die im Suchberechtigungsfilter angegeben ist, werden keine Suchergebnisse zurückgegeben.

- Beim Exportieren von Suchergebnissen werden Inhalte aus allen Inhaltsspeicherorten (einschließlich Exchange, Skype for Business, SharePoint, OneDrive und anderen Diensten, die Sie mit dem Tool für die Inhaltssuche durchsuchen können) in den Azure Storage Speicherort im Rechenzentrum hochgeladen, der durch den Parameter **Region** angegeben wird. Dies hilft Organisationen, die Compliance zu halten, indem inhalte nicht über kontrollierte Grenzen exportiert werden dürfen. Wenn im Suchberechtigungsfilter keine Region angegeben ist, werden Inhalte in das primäre Rechenzentrum der Organisation hochgeladen.

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

- Wenn Ihnen ein Suchberechtigungsfilter (ein Postfach oder ein Websitefilter) zugewiesen ist und Sie versuchen, nicht indizierte Elemente für eine Suche zu exportieren, die alle SharePoint Websites in Ihrer Organisation enthält, wird die folgende Fehlermeldung angezeigt: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Wenn Ihnen ein Suchberechtigungsfilter zugewiesen ist und Sie nicht indizierte Elemente aus SharePoint exportieren möchten, müssen Sie die Suche erneut ausführen und bestimmte SharePoint Websites für die Suche einschließen. Andernfalls können Sie nur indizierte Elemente aus einer Suche exportieren, die alle SharePoint Websites enthält. Weitere Informationen zu den Optionen beim Exportieren von Suchergebnissen finden Sie unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md#step-1-prepare-search-results-for-export)

- Suchberechtigungsfilter werden nicht auf öffentliche Exchange-Ordner angewendet.

## <a name="more-information"></a>Weitere Informationen

- Wenn ein Postfach nicht mehr lizenziert oder vorläufig gelöscht wird, werden Azure AD-Attribute nicht mehr mit dem Postfach synchronisiert. Wenn beim Löschen des Postfachs eine Aufbewahrung aufgehoben wurde, unterliegt der im Postfach beibehaltene Inhalt weiterhin einer Compliance-Grenze oder einem Suchberechtigungsfilter basierend auf dem Zeitpunkt, zu dem die Azure AD-Attribute zuletzt synchronisiert wurden, bevor das Postfach gelöscht wurde. 

    Darüber hinaus wird die Synchronisierung zwischen dem Postfach des Benutzers und OneDrive Konto eingestellt, wenn das Postfach nicht mehr lizenziert oder vorläufig gelöscht wird. Der letzte stempelte Wert des Complianceattributs für das OneDrive Konto bleibt in Kraft.

- Das Complianceattribut wird alle sieben Tage vom Exchange Postfach eines Benutzers mit dem OneDrive Konto synchronisiert. Wie bereits erwähnt, erfolgt diese Synchronisierung nur, wenn dem Benutzer eine Exchange Online und SharePoint Onlinelizenz zugewiesen ist und das Postfach des Benutzers mindestens 10 MB beträgt.

- Wenn Compliancegrenzen und Suchberechtigungsfilter sowohl für das Postfach eines Benutzers als auch für OneDrive Konto implementiert werden, wird empfohlen, das Postfach eines Benutzers nicht zu löschen und nicht das OneDrive Konto. Mit anderen Worten: Wenn Sie das Postfach eines Benutzers löschen, sollten Sie auch das OneDrive Konto des Benutzers entfernen.

- Es gibt Situationen (z. B. einen zurückkehrenden Mitarbeiter), in denen ein Benutzer möglicherweise über zwei oder mehr OneDrive Konten verfügt. In diesen Fällen wird nur das primäre OneDrive Konto synchronisiert, das dem Benutzer in Azure AD zugeordnet ist.

- Compliancegrenzen und Suchberechtigungsfilter hängen davon ab, dass Attribute für Inhalte in Exchange, OneDrive und SharePoint und die nachfolgende Indizierung dieses stempelten Inhalts gestempelt werden. 

- Es wird nicht empfohlen, Ausschlussfilter (z. B. die Verwendung `-not()` in einem Suchberechtigungsfilter) für eine inhaltsbasierte Compliancegrenze zu verwenden. Die Verwendung eines Ausschlussfilters kann unerwartete Ergebnisse haben, wenn Inhalte mit kürzlich aktualisierten Attributen nicht indiziert wurden. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer können Suchberechtigungsfilter erstellen und verwalten (mit New-ComplianceSecurityFilter und Set-ComplianceSecurityFilter Cmdlets)?**
  
Zum Erstellen, Anzeigen und Ändern von Suchberechtigungsfiltern müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein.
  
**Wenn ein eDiscovery-Manager mehr als einer Rollengruppe zugewiesen ist, die mehrere Behörden umfasst, wie wird nach Inhalten in einer Oder der anderen Agentur gesucht?**
  
Der eDiscovery-Manager kann der Suchabfrage Parameter hinzufügen, die die Suche auf eine bestimmte Agentur beschränken. Wenn eine Organisation beispielsweise die **Eigenschaft CustomAttribute10** angegeben hat, um Behörden zu unterscheiden, können sie Folgendes an ihre Suchabfrage anfügen, um Postfächer und OneDrive Konten in einer bestimmten Organisation zu durchsuchen: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**Was geschieht, wenn der Wert des Attributs, das als Complianceattribut in einem Suchberechtigungsfilter verwendet wird, geändert wird?**
  
Es dauert bis zu drei Tage, bis ein Suchberechtigungsfilter die Compliancegrenze erzwingt, wenn der Wert des im Filter verwendeten Attributs geändert wird. Nehmen wir beispielsweise im Contoso-Szenario an, dass ein Benutzer in der Fourth Coffee-Agentur in die Coho-Einrichtung übertragen wird. Daher wird der Wert des **Department-Attributs** für das Benutzerobjekt von *FourthCoffee* in *CohoWinery* geändert. In dieser Situation erhalten Fourth Coffee eDiscovery und Dies Suchergebnisse für diesen Benutzer für bis zu drei Tage, nachdem das Attribut geändert wurde. Ebenso dauert es bis zu drei Tage, bis eDiscovery-Manager und Ermittler von CohoDiscovery Suchergebnisse für den Benutzer erhalten.
  
**Kann ein eDiscovery-Manager Inhalte von zwei separaten Compliance-Grenzen anzeigen?**
  
Ja, dies kann beim Durchsuchen von Exchange Postfächern durch Hinzufügen des eDiscovery-Managers zu Rollengruppen erfolgen, die für beide Behörden sichtbar sind. Beim Durchsuchen SharePoint Websites und OneDrive Konten kann ein eDiscovery-Manager jedoch nur dann nach Inhalten in unterschiedlichen Compliance-Grenzen suchen, wenn sich die Behörden am selben Geografischen Standort befinden. **Hinweis:** Diese Einschränkung für Websites gilt nicht in Advanced eDiscovery, da die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort gebunden ist.
  
**Funktionieren Suchberechtigungsfilter für eDiscovery-Fallarchive, Microsoft 365 Aufbewahrungsrichtlinien oder DLP?**
  
Nein, nicht zu diesem Zeitpunkt.
  
**Kann ich, wenn ich eine Region zum Steuern des Inhaltsexports angibt, aber keine SharePoint Organisation in dieser Region habe, weiterhin nach SharePoint suchen?**
  
Wenn die im Suchberechtigungsfilter angegebene Region in Ihrer Organisation nicht vorhanden ist, wird die Standardregion durchsucht.
  
**Wie viele Suchberechtigungsfilter können maximal in einer Organisation erstellt werden?**
  
Es gibt keine Beschränkung für die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können. Die Suchleistung wird jedoch beeinträchtigt, wenn mehr als 100 Suchberechtigungsfilter vorhanden sind. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzigen Suchberechtigungsfilter kombinieren, wann immer möglich.
