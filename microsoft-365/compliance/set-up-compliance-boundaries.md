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
description: Erfahren Sie, wie Sie mithilfe von Compliancegrenzen logische Grenzen erstellen, die die Speicherorte von Benutzerinhalten steuern, die ein eDiscovery-Manager in Microsoft 365 durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28e61665d286292f8ba301c313fc3d9bb13065c1
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233192"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen

Die Anleitungen in diesem Artikel können bei der Verwendung von Core eDiscovery oder Advanced eDiscovery zum Verwalten von Untersuchungen angewendet werden.

#A0 erstellen logische Grenzen innerhalb einer Organisation, die die Inhaltsspeicherorte von Benutzern (z. B. Postfächer, #A1 und SharePoint-Websites) steuern, die eDiscovery-Manager durchsuchen können. Darüber hinaus steuern Compliancegrenzen, wer auf eDiscovery-Fälle zugreifen kann, die zum Verwalten der Rechts-, Personal- oder anderen Untersuchungen innerhalb Ihrer Organisation verwendet werden. Die Notwendigkeit von Compliancegrenzen ist häufig für multinationale Unternehmen erforderlich, die geografische Boarder und Vorschriften einhalten müssen, sowie für Behörden, die häufig in verschiedene Behörden unterteilt sind. In Microsoft 365 helfen Ihnen Compliancegrenzen, diese Anforderungen zu erfüllen, wenn Sie Inhaltssuchen durchführen und Untersuchungen mit eDiscovery-Fällen verwalten.
  
Wir verwenden das Beispiel in der folgenden Abbildung, um zu erläutern, wie Compliancegrenzen funktionieren.
  
![Compliancegrenzen bestehen aus Suchberechtigungsfiltern, die den Zugriff auf Behörden und Administrator-Rollengruppen steuern, die den Zugriff auf eDiscovery-Fälle steuern.](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In diesem Beispiel ist Contoso LTD eine Organisation, die aus zwei Niederlassungen besteht: Fourth Coffee und Coho Winery. Das Unternehmen erfordert, dass eDiscovery-Manger und Ermittler nur die Exchange-Postfächer, #A0 und #A1 in ihrer Agentur durchsuchen können. Außerdem können eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Agentur sehen, und sie können nur auf die Fälle zugreifen, bei denen sie Mitglied sind. Darüber hinaus können Ermittler in diesem Szenario keine Speicherorte für Inhalte in der Warteschleife platzieren oder Inhalte aus einem Fall exportieren. Im Folgenden erfahren Sie, wie Compliancegrenzen diese Anforderungen erfüllen.
  
- Die Filterfunktion für Suchberechtigungen in der Inhaltssuche steuert die Inhaltsorte, die eDiscovery-Manager und Ermittler durchsuchen können. Dies bedeutet, dass eDiscovery-Manager und -Ermittler in der Fourth Coffee-Organisation nur Inhaltsspeicherorte in der Fourth Coffee-Niederlassung durchsuchen können. Die gleiche Einschränkung gilt für die Coho Winery-Tochtergesellschaft.

- Rollengruppen stellen die folgenden Funktionen für Compliancegrenzen zur Verfügung:

  - Steuern, wer die eDiscovery-Fälle im Security & Compliance Center sehen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation anzeigen können.

  - Steuern, wer einem eDiscovery-Fall Mitglieder zuweisen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur den Fällen, von denen sie Mitglied sind, Mitglieder zuordnen können.

  - Steuern Sie die eDiscovery-bezogenen Aufgaben, die Mitglieder ausführen können, indem Sie Rollen hinzufügen oder entfernen, die bestimmte Berechtigungen zuweisen.

Hier ist der Prozess zum Einrichten von Compliancegrenzen:
  
[Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Schritt 2: Senden einer Anforderung an den #A0 zum Synchronisieren des Benutzerattributs mit #A1](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Schritt 3: Erstellen einer Rollengruppe für jede Agentur](#step-3-create-a-role-group-for-each-agency)

[Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Schritt 5: Erstellen eines eDiscovery-Falls für eine untersuchungen innerhalb der Agentur](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Vor dem Einrichten von Compliancegrenzen

Sie müssen die folgenden Voraussetzungen erfüllen, bevor das Azure Active Directory (Azure AD)-Attribut, das Sie (in Schritt 1) angeben, erfolgreich mit dem #A0 eines Benutzers synchronisiert werden kann (in Schritt 2):

- Benutzern müssen eine Exchange Online- und eine SharePoint Online-Lizenz zugewiesen sein.

- Benutzerpostfächer müssen mindestens 10 MB groß sein. Wenn das Postfach eines Benutzers kleiner als 10 MB ist, wird das Attribut, das zum Definieren Ihrer Behörden verwendet wird, nicht mit dem #A0 des Benutzers synchronisiert.

- Kompatibilitätsgrenzen und die Attribute zum Erstellen von Suchberechtigungsfiltern erfordern, dass Azure Active Directory (Azure AD)-Attribute mit Benutzerpostfächern synchronisiert werden. Führen Sie das [Cmdlet "Get-User"](https://docs.microsoft.com/powershell/module/exchange/get-user) in Exchange Online PowerShell aus, um zu überprüfen, ob die attribute, die Sie verwenden möchten, synchronisiert wurden. Die Ausgabe dieses Cmdlets zeigt die Azure AD-Attribute an, die mit Exchange Online synchronisiert sind.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Behörden

Der erste Schritt besteht in der Auswahl eines Azure AD-Attributs, das Ihre Behörden definiert. Dieses Attribut wird verwendet, um den Suchberechtigungsfilter zu erstellen, der einen eDiscovery-Manager so einschränkt, dass er nur die Inhaltsorte von Benutzern durchsucht, denen ein bestimmter Wert für dieses Attribut zugewiesen ist. Angenommen, Contoso entscheidet sich für die Verwendung des Attributs **"Department".** Der Wert für dieses Attribut für Benutzer in der Fourth Coffee-Niederlassung wäre und der Wert für Benutzer in der  `FourthCoffee`  Coho Winery-Niederlassung `CohoWinery` . In Schritt 4 verwenden Sie dieses Paar (z. B. Department:FourthCoffee), um die Speicherorte für Benutzerinhalte zu begrenzen, die `attribute:value` eDiscovery-Manager durchsuchen können.  
  
Hier ist eine Liste der Azure AD-Benutzerattribute, die Sie für Compliancegrenzen verwenden können:
  
- Company

- CustomAttribute1 - CustomAttribute15

- Abteilung

- Büro

- C (aus zwei Buchstaben) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> Dieses Attribut ist der Eigenschaft "CountryOrRegion" zu, die durch Ausführen des **Cmdlets "Get-User"** in Exchange Online PowerShell zurückgegeben wird. Das Cmdlet gibt den lokalisierten Ländernamen zurück, der aus dem aus zwei Buchstaben großen Ländercode übersetzt wird. Weitere Informationen finden Sie in der Beschreibung des Parameters "CountryOrRegion" im Referenzartikel zum [Set-User-Cmdlet.](https://docs.microsoft.com/powershell/module/exchange/set-user)

Obwohl mehr Benutzerattribute verfügbar sind, insbesondere für Exchange-Postfächer, sind die oben aufgeführten Attribute die einzigen, die derzeit von OneDrive unterstützt werden.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Schritt 2: Senden einer Anforderung an den #A0 zum Synchronisieren des Benutzerattributs mit #A1

Im nächsten Schritt wird eine Anforderung an den #A0 gesendet, um das Azure AD-Attribut, das Sie in Schritt 1 ausgewählt haben, mit allen #A1 in Ihrer Organisation zu synchronisieren. Nach dieser Synchronisierung wird das Attribut (und dessen Wert), das Sie in Schritt 1 ausgewählt haben, einer ausgeblendeten verwalteten Eigenschaft namens `ComplianceAttribute` zugeordnet. Verwenden Sie dieses Attribut, um den Suchberechtigungsfilter für OneDrive in Schritt 4 zu erstellen.
  
Schließen Sie die folgenden Informationen ein, wenn Sie die Anforderung an den Support von Microsoft senden:
  
- Der Standarddomänenname Ihrer Organisation

- Der Name des Azure AD-Attributs (aus Schritt 1)

- Der folgende Titel oder eine Beschreibung des Zwecks der Supportanfrage: "Aktivieren der OneDrive for #A0 mit Azure AD für Compliancesicherheitsfilter". Dadurch wird die Anforderung an das eDiscovery-Engineering-Team, das die Anforderung implementiert, um die Anforderung weiter geroutet.

Nachdem die technische Änderung vorgenommen und das Attribut mit OneDrive synchronisiert wurde, sendet Ihnen der #A0 die Buildnummer, in der die Änderung vorgenommen wurde, sowie ein geschätztes Bereitstellungsdatum. Der Bereitstellungsprozess dauert in der Regel 4 bis 6 Wochen, nachdem Sie die Supportanfrage übermittelt haben.
  
> [!IMPORTANT]
> Sie können Die Schritte 3 bis 5 abschließen, bevor diese Attributänderung bereitgestellt wird. Beim Ausführen von Inhaltssuchen werden jedoch erst Dokumente aus #A0 zurück, die in einem Suchberechtigungsfilter angegeben sind, nachdem die Attributsynchronisierung bereitgestellt wurde.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Schritt 3: Erstellen einer Rollengruppe für jede Agentur

Der nächste Schritt besteht im Erstellen der Rollengruppen im Security & Compliance Center, die sich an Ihren Behörden ausrichten. Es wird empfohlen, eine Rollengruppe zu erstellen, indem Sie die integrierte Gruppe der eDiscovery-Manager kopieren, die entsprechenden Mitglieder hinzufügen und Rollen entfernen, die möglicherweise nicht Ihren Anforderungen entsprechen. Weitere Informationen zu eDiscovery-bezogenen Rollen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security & Compliance Center.](assign-ediscovery-permissions.md)
  
Um die Rollengruppen zu erstellen, wechseln Sie im Security & Compliance Center zur Seite **Berechtigungen**, und erstellen Sie eine Rollengruppe für jedes Team in jeder Organisation, die Compliance-Begrenzungen sowie eDiscovery-Fälle zum Verwalten von Untersuchungen verwendet.
  
Mithilfe des Contoso-Compliance-Begrenzungsszenarios müssen vier Rollengruppen erstellt und die entsprechenden Mitglieder jeder Hinzugefügt werden.
  
- eDiscovery-Manager von Fourth Coffee

- Fourth Coffee-Ermittler

- eDiscovery-Manager von Coho Winery

- Coho Winery-Ermittler
  
Um die Anforderungen des Contoso-Compliance-Begrenzungsszenarios  zu  erfüllen, entfernen Sie auch die Rollen "Halte- und Export" aus den Rollengruppen "Ermittler", um zu verhindern, dass Ermittler Speicherorte für Inhalte platzieren und Inhalte aus einem Fall exportieren.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze

Nachdem Sie Rollengruppen für jede Agentur erstellt haben, besteht der nächste Schritt im Erstellen der Suchberechtigungsfilter, die jede Rollengruppe der jeweiligen Agentur zuordnen und die Compliancegrenze selbst definieren. Sie müssen einen Suchberechtigungsfilter für jede Agentur erstellen. Weitere Informationen zum Erstellen von Sicherheitsberechtigungsfiltern finden Sie unter [Konfigurieren der Berechtigungsfilterung für die Inhaltssuche.](permissions-filtering-for-content-search.md)
  
Hier ist die Syntax, die zum Erstellen eines Suchberechtigungsfilters verwendet wird, der für #A0 verwendet wird.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Im Folgenden finden Sie eine Beschreibung der einzelnen Parameter im Befehl:
  
- `FilterName`: Gibt den Namen des Filters an. Verwenden Sie einen Namen, der die Agentur beschreibt oder identifiziert, in der der Filter verwendet wird.

- `Users`: Gibt die Benutzer oder Gruppen an, die diesen Filter auf die von ihnen angewendeten Inhaltssuchaktionen anwenden. Für Kompatibilitätsgrenzen gibt dieser Parameter die Rollengruppen an (die Sie in Schritt 3 erstellt haben) in der Agentur, für die Sie den Filter erstellen. Beachten Sie, dass es sich um einen mehrwertigen Parameter handelt, sodass Sie eine oder mehrere Rollengruppen, getrennt durch Kommas, verwenden können.

- `Filters`: Gibt die Suchkriterien für den Filter an. Für die Compliancegrenzen definieren Sie die folgenden Filter. Jedes gilt für einen Inhaltsspeicherort. 

    - `Mailbox`: Gibt die Postfächer an, die von den im Parameter definierten  `Users` Rollengruppen durchsucht werden können. Für Compliancegrenzen ist  *ComplianceAttribute*  das gleiche Attribut, das Sie in Schritt 1 identifiziert haben, und  *AttributeValue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die Postfächer in einer bestimmten Agentur durchsuchen. Beispiel: `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: Gibt die #A0 an, die von den im Parameter definierten `Users` Rollengruppen durchsucht werden können. Verwenden Sie für den #A0 die tatsächliche  `ComplianceAttribute` Zeichenfolge. Dies ist dem attribut, das Sie in Schritt 1 identifiziert haben und das als Ergebnis der in Schritt 2 übermittelten Supportanfrage mit #A0 synchronisiert wird. *AttributeValue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die #A0 in einer bestimmten Agentur durchsuchen. Beispiel:  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: Gibt die SharePoint-Websites an, die von den im Parameter definierten  `Users` Rollengruppen durchsucht werden können. Die  *SharePointURL*  gibt die Websites in der Agentur an, die Mitglieder der Rollengruppe durchsuchen können. Zum Beispiel: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Beachten `Site` Sie, dass `Site_Path` die Filter durch einen **-or-Operator verbunden** sind.

     > [!NOTE]
     > Die Syntax für den `Filters` Parameter enthält eine *Filterliste.* Eine Filterliste ist ein Filter, der einen Postfachfilter und einen Standortfilter enthält, die durch ein Komma getrennt sind. Beachten Sie im vorherigen Beispiel, dass ein Komma Mailbox_ComplianceAttribute **und** **Site_ComplianceAttribute** `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` trennt. Wenn dieser Filter während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Filter für Suchberechtigungen aus der Filterliste erstellt: ein Postfachfilter und ein Websitefilter. Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern für jede Agentur: ein Suchberechtigungsfilter für das Postfachattribut und ein Filter für die Websiteattribute. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine bevorzugte Frage.

- `Action`: Gibt den Typ der Compliancesuchaktion an, auf die der Filter angewendet wird. Der Filter wird beispielsweise nur angewendet, wenn Mitglieder der im Parameter definierten Rollengruppe  `-Action Search` `Users` eine Inhaltssuche ausführen. In diesem Fall würde der Filter beim Exportieren von Suchergebnissen nicht angewendet. Verwenden Sie für Kompatibilitätsgrenzen,  `-Action All` damit der Filter auf alle Suchaktionen angewendet wird. 

    Eine Liste der Aktionen für die Inhaltssuche finden Sie im Abschnitt "New-ComplianceSecurityFilter" in "Konfigurieren der Berechtigungsfilterung [für die Inhaltssuche".](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Nachfolgend finden Sie Beispiele für die beiden Suchberechtigungsfilter, die zur Unterstützung des Szenarios mit den Compliance-Begrenzungen bei Contoso erstellt werden würden. Beide Beispiele umfassen eine durch Trennzeichen getrennte Filterliste, bei der die Postfach- und Websitefilter in den gleichen Suchberechtigungsfilter eingeschlossen sind und durch ein Komma getrennt sind.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Schritt 5: Erstellen eines eDiscovery-Falls für unternehmensinterne Untersuchungen

Im letzten Schritt erstellen Sie einen Core eDiscovery- oder Advanced eDiscovery-Fall im Microsoft 365 Compliance Center und fügen dann die Rollengruppe, die Sie in Schritt 3 erstellt haben, als Mitglied des Falls hinzu. Dies führt zu zwei wichtigen Merkmalen der Verwendung von Compliancegrenzen:
  
- Nur Mitglieder der Rollengruppe, die dem Fall hinzugefügt wurden, können den Fall im Security & Compliance Center sehen und darauf zugreifen. Wenn beispielsweise die Rollengruppe "Fourth Coffee Investigators" das einzige Mitglied eines Falls ist, können Mitglieder der Rollengruppe "Fourth Coffee eDiscovery Managers" (oder Mitglieder einer anderen Rollengruppe) den Fall nicht sehen oder darauf zugreifen.

- Wenn ein Mitglied der Rollengruppe, die einem Fall zugewiesen ist, eine dem Fall zugeordnete Suche ausgeführt, kann es nur die Inhaltsorte innerhalb ihrer Agentur durchsuchen (definiert durch den Suchberechtigungsfilter, den Sie in Schritt 4 erstellt haben).

So erstellen Sie einen Fall und weisen Mitglieder zu

1. Wechseln Sie zur **Core eDiscovery-** oder **Advanced eDiscovery-Seite** im Microsoft 365 Compliance Center, und erstellen Sie einen Fall.

2. Klicken Sie in der Liste der Fälle auf den Namen des erstellten Falls.

3. Klicken Sie **auf der Flyoutseite "Diesen** Fall verwalten" unter **"Rollengruppen verwalten"** auf ![ "Hinzufügen" (Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **).**

    ![Hinzufügen einer Rollengruppe als Mitglied eines eDiscovery-Falls](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Wählen Sie in der Liste der Rollengruppen eine der Rollengruppen aus, die Sie in Schritt 3 erstellt haben, und klicken Sie auf **"Hinzufügen".**

5. Klicken **Sie auf "Speichern"** **im Flyout "Diesen Fall** verwalten", um die Änderung zu speichern.

> [!NOTE]
Beim Hinzufügen einer Rollengruppe zu einem Fall können Sie nur die Rollengruppen hinzufügen, bei denen Sie Mitglied sind.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen

Mithilfe von Suchberechtigungsfiltern können Sie auch steuern, wohin Inhalte für den Export geroutet werden und welches Datencenter beim Durchsuchen von Inhaltsspeicherorten in einer [SharePoint Multi-Geo-Umgebung durchsucht werden kann.](https://go.microsoft.com/fwlink/?linkid=860840)
  
- **Exportieren von Suchergebnissen:** Sie können die Suchergebnisse aus Exchange-Postfächern, #A0 und #A1 aus einem bestimmten Rechenzentrum exportieren. Dies bedeutet, dass Sie den Rechenzentrumsspeicherort angeben können, aus dem Suchergebnisse exportiert werden.

    Verwenden Sie **den Parameter "Region"** für **Cmdlets "New-ComplianceSecurityFilter"** oder **"Set-ComplianceSecurityFilter",** um zu erstellen oder zu ändern, über welches Datencenter der Export geroutet wird.
  
    |**Übergebener Wert**|**Rechenzentrumsstandort**|
    |:-----|:-----|
    |NAM  <br/> |Nordamerikanisch (Rechenzentren befinden sich in den USA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN <br/> |Kanada|
    |||

- **Routen von Inhaltssuchen:** Sie können die Inhaltssuchen von #A0 und #A1 an ein Satellitendatencenter routen. Dies bedeutet, dass Sie den Rechenzentrumsspeicherort angeben können, in dem Suchen ausgeführt werden.

    Verwenden Sie einen der folgenden Werte für den Parameter **"Region",** um den Standort des Datencenters zu steuern, in dem die Suche beim Durchsuchen von #A0 und #A1 ausgeführt wird. 
  
    |**Übergebener Wert**|**Routingstandorte für Rechenzentren für SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |USA  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN  <br/> |USA  <br/> |
    |AUS  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |KOR  <br/> |Das Standarddatencenter der Organisation  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |IND  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |EINES DER  <br/> |USA  <br/> |
    |NOR  <br/> |Europa |
    |BRA  <br/> |Nordamerikanische Rechenzentren |
    |||

   Wenn Sie den Parameter **"Region"** für einen Suchberechtigungsfilter nicht angeben, wird die primäre SharePoint-Region der Organisation durchsucht. Suchergebnisse werden in das nächste Datencenter exportiert.

   Zur Vereinfachung des Konzepts steuert der Parameter **"Region"** das Datencenter, das zum Suchen nach Inhalten in SharePoint und OneDrive verwendet wird. Dies gilt nicht für die Suche nach Inhalten in Exchange, da die Suche nach Inhalten in Exchange nicht an den geografischen Standort von Rechenzentren gebunden ist. Außerdem kann der gleiche **Wert des Parameters "Region"** auch das Datencenter bestimmen, über das Exporte geroutet werden. Dies ist häufig erforderlich, um die Bewegung von Daten über geografische Boarder hinweg zu steuern.

> [!NOTE]
> Wenn Sie Advanced eDiscovery verwenden, bestimmt der Parameter **"Region"** nicht die Region, aus der Daten exportiert werden. Daten werden aus dem primären Datencenter der Organisation exportiert. Außerdem ist die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort von Rechenzentren gebunden. Alle Rechenzentren werden durchsucht. Weitere Informationen zu Advanced eDiscovery finden Sie unter Übersicht über die [Advanced eDiscovery-Lösung in Microsoft 365.](overview-ediscovery-20.md)

Hier sind Beispiele für die Verwendung des Parameters **"Region"** beim Erstellen von Suchberechtigungsfiltern für Compliance-Grenzen. Dabei wird davon ausgegangen, dass sich die Fourth Coffee-Niederlassung in Nordamerika und Coho Winery in Europa befindet. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Beachten Sie die folgenden Punkte beim Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen.
  
- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Alle Rechenzentren werden durchsucht, wenn Sie Postfächer durchsuchen. Um den Umfang der durchsuchten Exchange-Postfächer zu beschränken, verwenden Sie den Parameter **"Filters"** beim Erstellen oder Ändern eines Suchberechtigungsfilters. 

- Wenn ein eDiscovery-Manager in mehreren #A0 suchen muss, müssen Sie ein anderes Benutzerkonto für diesen eDiscovery-Manager erstellen, das im Suchberechtigungsfilter verwendet wird, um die Region anzugeben, in der sich die #A1 oder #A2 befinden. Weitere Informationen zum Einrichten finden Sie im Abschnitt "Suchen nach Inhalten in einer SharePoint Multi-Geo-Umgebung" in [der Inhaltssuche.](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Bei der Suche nach Inhalten in SharePoint und OneDrive leitet der Parameter **"Region"** Suchen entweder an den primären oder satellitenstandort weiter, an dem der eDiscovery-Manager eDiscovery-Untersuchungen durchführen wird. Wenn ein eDiscovery-Manager SharePoint- und #A0 außerhalb der Region durchsucht, die im Suchberechtigungsfilter angegeben ist, werden keine Suchergebnisse zurückgegeben.

- Beim Exportieren von Suchergebnissen werden Inhalte aus allen Inhaltsspeicherorten (einschließlich Exchange, Skype for Business, SharePoint, OneDrive und anderen Diensten, die Sie mit dem Tool für die Inhaltssuche durchsuchen können) in den #A0 im Datencenter hochgeladen, das durch den Parameter **"Region"** angegeben wird. Dies hilft Organisationen dabei, die Compliance zu gewährleisten, da inhalte nicht über kontrollierte Grenzen hinweg exportiert werden dürfen. Wenn im Suchberechtigungsfilter keine Region angegeben ist, werden Inhalte in das primäre Datencenter der Organisation hochgeladen.

- Sie können einen vorhandenen Suchberechtigungsfilter bearbeiten, um die Region hinzuzufügen oder zu ändern, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Verwenden von Kompatibilitätsgrenzen für SharePoint-Hubwebsites

[SharePoint-Hubwebsites](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) richten sich häufig an die gleichen geografischen oder Agenturgrenzen, die eDiscovery-Compliance-Grenzen folgen. Das bedeutet, dass Sie die Website-ID-Eigenschaft der Hubwebsite verwenden können, um eine Compliancegrenze zu erstellen. Verwenden Sie dazu das [Cmdlet "Get-SPOHubSite"](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) in SharePoint Online PowerShell, um die SiteId für die Hubwebsite zu erhalten, und verwenden Sie dann diesen Wert für die Abteilungs-ID-Eigenschaft, um einen Suchberechtigungsfilter zu erstellen.

Verwenden Sie die folgende Syntax, um einen Suchberechtigungsfilter für eine #A0 zu erstellen:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Hier ist ein Beispiel für das Erstellen eines Suchberechtigungsfilters für eine Hubwebsite für die Coho Winery-Agentur:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Beschränkungen der Richtlinienkonformität

Beachten Sie die folgenden Einschränkungen beim Verwalten von eDiscovery-Fällen und -Untersuchungen, bei denen Compliancebeschränkungen verwendet werden.
  
- Beim Erstellen und Ausführen einer Suche können Sie Inhaltsspeicherorte auswählen, die sich außerhalb Ihrer Organisation befinden. Aufgrund des Filters für Suchberechtigungen sind Inhalte aus diesen Speicherorten jedoch nicht in den Suchergebnissen enthalten.

- Compliancegrenzen gelten nicht für Haltefälle in eDiscovery-Fällen. Dies bedeutet, dass ein eDiscovery-Manager in einer Organisation einen Benutzer in einer anderen Organisation im Haltebereich platzieren kann. Die Compliance-Begrenzung wird jedoch erzwungen, wenn der eDiscovery-Manager die Inhaltsspeicherorte des Benutzers durchsucht, der in den Haltebereich gesetzt wurde. Dies bedeutet, dass der eDiscovery-Manager nicht in der Lage ist, die Inhaltsspeicherorte des Benutzers zu durchsuchen, auch wenn er den Benutzer im Haltebereich platzieren konnte.

    Außerdem gelten Haltestatistiken nur für Inhaltsspeicherorte in der Organisation.

- Suchberechtigungsfilter werden nicht auf öffentliche Exchange-Ordner angewendet.

## <a name="more-information"></a>Weitere Informationen

- Wenn ein Postfach nicht mehr lizenziert oder soft-deleted ist, werden Azure AD-Attribute nicht mehr mit dem Postfach synchronisiert. Wenn ein Haltebereich für das Postfach aktiviert wurde, als es gelöscht wurde, unterliegt der im Postfach beibehaltene Inhalt weiterhin einer Compliancegrenze oder einem Suchberechtigungsfilter basierend auf dem Zeitpunkt, zu dem die Azure AD-Attribute zuletzt synchronisiert wurden, bevor das Postfach gelöscht wurde. 

    Darüber hinaus wird die Synchronisierung zwischen dem Postfach des Benutzers und dem #A0 beendet, wenn das Postfach nicht mehr lizenziert oder soft-deleted ist. Der letzte gestempelten Wert des #A0 für das #A1 bleibt in Kraft.

- Das #A0 wird alle sieben Tage vom #A1 eines Benutzers mit dem #A2 synchronisiert. Wie bereits erwähnt, erfolgt diese Synchronisierung nur, wenn dem Benutzer sowohl eine Exchange Online- als auch eine SharePoint Online-Lizenz zugewiesen ist und das Postfach des Benutzers mindestens 10 MB groß ist.

- Wenn Kompatibilitätsgrenzen und Suchberechtigungsfilter sowohl für das Postfach eines Benutzers als auch für das #A0 implementiert sind, wird empfohlen, dass Sie nicht das Postfach eines Benutzers und nicht sein #A1 löschen. Anders ausgedrückt: Wenn Sie das Postfach eines Benutzers löschen, sollten Sie auch das #A0 des Benutzers entfernen.

- Es gibt Situationen (z. B. einen zurückkehrenden Mitarbeiter), in denen ein Benutzer möglicherweise zwei oder mehr #A0 hat. In diesen Fällen wird nur das primäre OneDrive-Konto synchronisiert, das dem Benutzer in Azure AD zugeordnet ist.

- Kompatibilitätsgrenzen und Suchberechtigungsfilter hängen von Attributen ab, die auf Inhalten in Exchange, OneDrive und SharePoint gestempelt werden, sowie von der nachfolgenden Indizierung dieses gestempelten Inhalts. 

- Es wird nicht empfohlen, Ausschlussfilter (z. B. die Verwendung in einem Suchberechtigungsfilter) für eine `-not()` inhaltsbasierte Compliancegrenze zu verwenden. Die Verwendung eines Ausschlussfilters kann unerwartete Ergebnisse haben, wenn Inhalte mit kürzlich aktualisierten Attributen nicht indiziert wurden. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer kann Suchberechtigungsfilter erstellen und verwalten (mithilfe New-ComplianceSecurityFilter und Set-ComplianceSecurityFilter Cmdlets)?**
  
Zum Erstellen, Anzeigen und Ändern von Suchberechtigungsfiltern müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein.
  
**Wenn ein eDiscovery-Manager mehreren Rollengruppen zugewiesen ist, die sich über mehrere Behörden erstreckt, wie wird in der einen oder anderen Agentur nach Inhalten gesucht?**
  
Der eDiscovery-Manager kann seiner Suchabfrage Parameter hinzufügen, die die Suche auf eine bestimmte Agentur beschränken. Wenn eine Organisation beispielsweise die Eigenschaft **"CustomAttribute10"** angegeben hat, um Behörden zu unterscheiden, kann sie Folgendes an ihre Suchabfrage anfügen, um Postfächer und #A0 in einer bestimmten Agentur zu  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` durchsuchen:
  
**Was geschieht, wenn der Wert des Attributs, das als Complianceattribut in einem Suchberechtigungsfilter verwendet wird, geändert wird?**
  
Es dauert bis zu drei Tage, bis ein Suchberechtigungsfilter die Compliancegrenze erzwingt, wenn der Wert des attributs geändert wird, das im Filter verwendet wird. Nehmen wir beispielsweise an, dass im Szenario von Contoso ein Benutzer der Fourth Coffee-Agentur zur Coho Winery-Agentur übertragen wird. Der Wert des Attributs **"Department"** für das Benutzerobjekt wird also von *"FourthCoffee"* in *"CohoWinery" geändert.* In dieser Situation erhalten Fourth Coffee eDiscovery und Investoren suchergebnisse für diesen Benutzer für bis zu drei Tage, nachdem das Attribut geändert wurde. Entsprechend dauert es bis zu drei Tage, bis Coho Winery eDiscovery-Manager und -Ermittler Suchergebnisse für den Benutzer erhalten.
  
**Kann ein eDiscovery-Manager Inhalte aus zwei separaten Compliancegrenzen anzeigen?**
  
Ja, dies kann beim Durchsuchen von Exchange-Postfächern durch Hinzufügen des eDiscovery-Managers zu Rollengruppen mit Sichtbarkeit für beide Behörden geschehen. Beim Durchsuchen von #A0 und #A1 kann ein eDiscovery-Manager jedoch nur dann nach Inhalten an unterschiedlichen #A2 suchen, wenn sich die Behörden in derselben Region oder an demselben geografischen Standort befinden. **Hinweis:** Diese Einschränkung für Websites gilt in Advanced eDiscovery nicht, da die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort gebunden ist.
  
**Funktionieren Suchberechtigungsfilter für eDiscovery-Fallspeicher, Microsoft 365-Aufbewahrungsrichtlinien oder DLP?**
  
Nein, derzeit nicht.
  
**Wenn ich eine Region zum Steuern des Exportbereichs von Inhalten angeben möchte, aber ich keine SharePoint-Organisation in dieser Region habe, kann ich sharePoint trotzdem durchsuchen?**
  
Wenn die im Suchberechtigungsfilter angegebene Region in Ihrer Organisation nicht vorhanden ist, wird die Standardregion durchsucht.
  
**Wie viele Suchberechtigungsfilter können maximal in einer Organisation erstellt werden?**
  
Die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können, ist nicht begrenzt. Die Suchleistung wird jedoch bei mehr als 100 Suchberechtigungsfiltern beeinträchtigen. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive nach Möglichkeit in einem einzigen Suchberechtigungsfilter kombinieren.
