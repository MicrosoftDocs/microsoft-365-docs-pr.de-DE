---
title: Einrichten von Compliance-Grenzen für eDiscovery-Untersuchungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Erfahren Sie, wie Sie mithilfe von Kompatibilitäts Grenzen logische Grenzen erstellen, die die Benutzerinhalts Speicherorte steuern, die ein eDiscovery-Manager in Microsoft 365 durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c57689cc6e626b62ae976bac9f9771205431bc8a
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370401"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Einrichten von Compliance-Grenzen für eDiscovery-Untersuchungen

Die Anleitungen in diesem Artikel können angewendet werden, wenn Sie entweder die Kern-eDiscovery oder die erweiterte eDiscovery zum Verwalten von Untersuchungen verwenden.

Compliance-Grenzen erstellen logische Grenzen in einer Organisation, die die Benutzerinhalts Speicherorte (wie Postfächer, OneDrive-Konten und SharePoint-Websites) steuern, die eDiscovery-Manager durchsuchen können. Außerdem steuern Compliance-Grenzen, wer auf eDiscovery-Fälle zugreifen kann, die zur Verwaltung der rechtlichen, personellen oder sonstigen Untersuchungen in Ihrer Organisation verwendet werden. Die Notwendigkeit von Compliance-Grenzen ist häufig für multinationale Unternehmen erforderlich, die geografische und behördliche Bestimmungen respektieren müssen, und für Regierungen, die häufig in verschiedene Agenturen aufgeteilt sind. In Microsoft 365 unterstützen Compliance-Grenzen Sie bei der Durchführung von Inhalts suchen und der Verwaltung von Untersuchungen mit eDiscovery-Fällen bei der Erfüllung dieser Anforderungen.
  
Wir verwenden das Beispiel in der folgenden Abbildung, um zu erläutern, wie Kompatibilitäts Grenzen funktionieren.
  
![Compliance-Grenzen bestehen aus Such Berechtigungs filtern, die den Zugriff auf Agenturen und Administratorrollengruppen steuern, mit denen der Zugriff auf eDiscovery-Fälle gesteuert wird](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In diesem Beispiel handelt es sich bei Contoso Ltd um eine Organisation, die aus zwei Niederlassungen, Fourth Coffee und dem Weingut Winery besteht. Das Unternehmen erfordert, dass eDiscovery-Manager und Ermittler nur die Exchange-Postfächer, OneDrive-Konten und SharePoint-Websites in Ihrer Agentur durchsuchen können. Außerdem können eDiscovery-Manager und Ermittler nur eDiscovery-Fälle in Ihrer Agentur anzeigen, und Sie können nur auf die Fälle zugreifen, in denen Sie Mitglied sind. Hier erfahren Sie, wie Compliance-Grenzen diese Anforderungen erfüllen.
  
- Die Suchberechtigungen-Filterfunktion in der Inhaltssuche steuert die inhaltsspeicherorte, die eDiscovery-Manager und-Prüfer durchsuchen können. Dies bedeutet, dass eDiscovery-Manager und -Ermittler in der Fourth Coffee-Organisation nur Inhaltsspeicherorte in der Fourth Coffee-Niederlassung durchsuchen können. Die gleiche Einschränkung gilt für die Coho Winery-Tochtergesellschaft.

    Rollengruppen steuern, wer die eDiscovery-Fälle im Security & Compliance Center anzeigen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation anzeigen können.

- Rollengruppen steuern auch, wer einem eDiscovery-Fall Mitglieder zuweisen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur den Fällen, von denen sie Mitglied sind, Mitglieder zuordnen können.

Hier ist der Prozess zum Einrichten von Kompatibilitäts Grenzen:
  
[Schritt 1: Identifizieren eines Benutzer Attributs zur Definition ihrer Agenturen](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Schritt 2: Datei eine Anforderung mit dem Microsoft-Support, um das Benutzerattribut mit OneDrive-Konten zu synchronisieren](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Schritt 3: Erstellen einer Rollengruppe für jede Agentur](#step-3-create-a-role-group-for-each-agency)

[Schritt 4: Erstellen eines Such Berechtigungs Filters zum Erzwingen der Konformitäts Grenze](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Schritt 5: Erstellen eines eDiscovery-Falls für eine Intra-Agency-Untersuchung](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Vor dem Einrichten von Compliance-Grenzen

Sie müssen die folgenden Voraussetzungen erfüllen, bevor das Azure Active Directory (Azure AD)-Attribut, das Sie (in Schritt 1) identifizieren, erfolgreich mit dem OneDrive-Konto eines Benutzers synchronisiert werden kann (in Schritt 2):

- Benutzern muss eine Exchange Online Lizenz und eine SharePoint Online Lizenz zugewiesen sein.

- Benutzerpostfächer müssen mindestens 10 MB groß sein. Wenn das Postfach eines Benutzers kleiner als 10 MB ist, wird das zum Definieren Ihrer Agenturen verwendete Attribut nicht mit dem OneDrive-Konto des Benutzers synchronisiert.

- Compliance-Grenzen und die Attribute, die zum Erstellen von Such Berechtigungs Filtern verwendet werden, erfordern, dass Azure Active Directory (Azure AD)-Attribute mit Benutzerpostfächern synchronisiert werden. Um zu überprüfen, ob die Attribute, die Sie verwenden möchten, synchronisiert wurden, führen Sie das Cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) in Exchange Online PowerShell aus. Die Ausgabe dieses Cmdlets zeigt die Azure AD Attribute an, die mit Exchange Online synchronisiert wurden.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Schritt 1: Identifizieren eines Benutzer Attributs zur Definition ihrer Agenturen

Der erste Schritt besteht darin, ein Azure AD zu verwendender Attribut auszuwählen, mit dem Ihre Agenturen definiert werden. Dieses Attribut wird verwendet, um den Such Berechtigungsfilter zu erstellen, mit dem ein eDiscovery-Manager so eingeschränkt wird, dass nur die inhaltsspeicherorte von Benutzern durchsucht werden, denen ein bestimmter Wert für dieses Attribut zugewiesen ist. Angenommen, Contoso entscheidet, das **Department** -Attribut zu verwenden. Der Wert für dieses Attribut für Benutzer in der vierten Coffee-Tochtergesellschaft wäre  `FourthCoffee`  und der Wert für die Benutzer in der Weingut-Tochtergesellschaft `CohoWinery` . In Schritt 4 verwenden Sie dieses  `attribute:value`  Paar (beispielsweise *Department: fourthcoffee*), um die Benutzerinhalts Speicherorte zu begrenzen, die eDiscovery-Manager durchsuchen können. 
  
Im folgenden finden Sie eine Liste der Azure AD Benutzerattribute, die Sie für Kompatibilitäts Grenzen verwenden können:
  
- Company

- CustomAttribute1-CustomAttribute15

- Abteilung

- Büro

- C (Ländervorwahl mit zwei Buchstaben) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> Dieses Attribut wird der CountryOrRegion-Eigenschaft zugeordnet, die durch Ausführen des Cmdlets **Get-User** in Exchange Online PowerShell zurückgegeben wird. Das Cmdlet gibt den lokalisierten Ländernamen zurück, der aus dem aus zwei Buchstaben bestehenden Ländercode übersetzt wird. Weitere Informationen finden Sie in der Beschreibung des CountryOrRegion-Parameters im Referenzartikel zum Cmdlet " [Sets-User](https://docs.microsoft.com/powershell/module/exchange/set-user) ".

Obwohl mehr Benutzerattribute verfügbar sind, insbesondere für Exchange-Postfächer, sind die oben aufgeführten Attribute die einzigen, die derzeit von OneDrive unterstützt werden.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Schritt 2: Datei eine Anforderung mit dem Microsoft-Support, um das Benutzerattribut mit OneDrive-Konten zu synchronisieren

Im nächsten Schritt wird eine Anforderung mit dem Microsoft-Support gespeichert, um das Azure AD Attribut zu synchronisieren, das Sie in Schritt 1 für alle OneDrive-Konten in Ihrer Organisation ausgewählt haben. Nach dieser Synchronisierung wird das Attribut (und sein Wert), das Sie in Schritt 1 ausgewählt haben, einer ausgeblendeten verwalteten Eigenschaft mit dem Namen zugeordnet `ComplianceAttribute` . Sie verwenden dieses Attribut, um den Such Berechtigungsfilter für OneDrive in Schritt 4 zu erstellen.
  
Schließen Sie die folgenden Informationen ein, wenn Sie die Anforderung an den Microsoft-Support übermitteln:
  
- Der Standarddomänenname Ihrer Organisation

- Der Name des Azure AD-Attributs (aus Schritt 1)

- Der folgende Titel oder die Beschreibung des Zwecks der Supportanforderung: "aktivieren OneDrive für Unternehmen Synchronisierung mit Azure AD für Compliance-Sicherheitsfilter". Dadurch wird die Anforderung an das eDiscovery-Entwicklungsteam weitergeleitet, das die Anforderung implementiert.

Nachdem die technische Änderung vorgenommen wurde und das Attribut mit OneDrive synchronisiert wurde, sendet der Microsoft-Support Ihnen die Buildnummer, in der die Änderung vorgenommen wurde, und ein geschätztes Bereitstellungsdatum. Der Bereitstellungsprozess dauert in der Regel 4 bis 6 Wochen, nachdem Sie die Supportanfrage gesendet haben.
  
> [!IMPORTANT]
> Sie können Schritt 3 bis Schritt 5 abschließen, bevor diese Attributänderung bereitgestellt wird. Durch die Ausführung von Inhalts suchen werden jedoch keine Dokumente aus OneDrive-Konten zurückgegeben, die in einem Such Berechtigungsfilter angegeben sind, bis die Attribut Synchronisierung bereitgestellt wurde.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Schritt 3: Erstellen einer Rollengruppe für jede Agentur

Der nächste Schritt besteht darin, die Rollengruppen im Security & Compliance Center zu erstellen, das mit ihren Agenturen in Einklang steht. Es wird empfohlen, eine Rollengruppe zu erstellen, indem Sie die integrierte Gruppe der eDiscovery-Manager kopieren, die entsprechenden Mitglieder hinzufügen und Rollen entfernen, die möglicherweise nicht Ihren Anforderungen entsprechen. Weitere Informationen zu eDiscovery-bezogenen Rollen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).
  
Um die Rollengruppen zu erstellen, wechseln Sie im Security & Compliance Center zur Seite **Berechtigungen**, und erstellen Sie eine Rollengruppe für jedes Team in jeder Organisation, die Compliance-Begrenzungen sowie eDiscovery-Fälle zum Verwalten von Untersuchungen verwendet. 
  
Im Szenario Contoso-Konformitäts Grenzen müssen vier Rollengruppen erstellt werden, denen jeweils die entsprechenden Mitglieder hinzugefügt werden.
  
- eDiscovery-Manager von Fourth Coffee

- Fourth Coffee-Ermittler

- eDiscovery-Manager von Coho Winery

- Coho Winery-Ermittler
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Schritt 4: Erstellen eines Such Berechtigungs Filters zum Erzwingen der Konformitäts Grenze

Nachdem Sie für jede Agentur Rollengruppen erstellt haben, besteht der nächste Schritt darin, die Such Berechtigungsfilter zu erstellen, die jede Rollengruppe ihrer spezifischen Agentur zuordnen und die Konformitäts Grenze selbst definiert. Sie müssen für jede Agentur einen Such Berechtigungsfilter erstellen. Weitere Informationen zum Erstellen von Sicherheits Berechtigungs Filtern finden Sie unter [Konfigurieren der Berechtigungs Filterung für die Inhaltssuche](permissions-filtering-for-content-search.md).
  
Hier ist die Syntax, die verwendet wird, um einen Such Berechtigungsfilter zu erstellen, der für Kompatibilitäts Grenzen verwendet wird.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Im folgenden finden Sie eine Beschreibung der einzelnen Parameter im Befehl:
  
- `FilterName`: Gibt den Namen des Filters an. Verwenden Sie einen Namen, der die Agentur beschreibt oder identifiziert, in der der Filter verwendet wird.

- `Users`: Gibt die Benutzer oder Gruppen an, die diesen Filter auf die durchgeführten Inhalts Suchaktionen anwenden. Für Kompatibilitäts Grenzen gibt dieser Parameter die Rollengruppen (die Sie in Schritt 3 erstellt haben) in der Agentur an, für die Sie den Filter erstellen. Hinweis Hierbei handelt es sich um einen mehrwertigen Parameter, mit dem Sie eine oder mehrere Rollengruppen, getrennt durch Kommas, einbinden können.

- `Filters`: Gibt die Suchkriterien für den Filter an. Für die Konformitäts Grenzen definieren Sie die folgenden Filter. Jeder wird auf einen Inhaltsspeicherort angewendet. 

    - `Mailbox`: Gibt die Postfächer an, die die im Parameter definierten Rollengruppen  `Users` Durchsuchen können. Für Kompatibilitäts Grenzen ist  *complianceattribute*  das gleiche Attribut, das Sie in Schritt 1 identifiziert haben, und  *Attribut*  Wert gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die Postfächer in einer bestimmten Agentur durchsuchen. Beispiel: `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: Gibt die OneDrive-Konten an, die die im Parameter definierten Rollengruppen `Users` Durchsuchen können. Verwenden Sie für den OneDrive-Filter die tatsächliche Zeichenfolge  `ComplianceAttribute` . Dies entspricht dem Attribut, das Sie in Schritt 1 identifiziert haben und das mit OneDrive-Konten als Ergebnis der in Schritt 2 übermittelten Supportanforderung synchronisiert wird. *Attributvalue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die OneDrive-Konten in einer bestimmten Agentur durchsuchen. Beispiel:  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: Gibt die SharePoint-Websites an, die die im Parameter definierten Rollengruppen  `Users` Durchsuchen können. Die  *SharePointURL*  gibt die Websites in der Agentur an, die Mitglieder der Rollengruppe durchsuchen können. Zum Beispiel: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Beachten Sie `Site` , dass die und `Site_Path` -Filter durch einen **-oder-** Operator verbunden sind.

     > [!NOTE]
     > Die Syntax für den `Filters` Parameter enthält eine *Filterliste*. Eine Filterliste ist ein Filter, der einen Post Fach Filter und einen Website Filter enthält, der durch ein Komma getrennt ist. Beachten Sie im vorherigen Beispiel, dass ein Komma **Mailbox_ComplianceAttribute** und **Site_ComplianceAttribute**trennt: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` . Wenn dieser Filter während der Ausführung einer Inhaltssuche verarbeitet wird, werden zwei Such Berechtigungsfilter aus der Liste Filter erstellt: ein Post Fach Filter und ein Website Filter. Eine Alternative zur Verwendung einer Filterliste besteht darin, zwei separate Such Berechtigungsfilter für jede Agentur zu erstellen: einen Such Berechtigungsfilter für das Postfachattribut und einen Filter für die Website Attribute. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Such Berechtigungsfilter ist eine Frage der Präferenz.

- `Action`: Gibt die Art der Konformitäts Suchaktion an, auf die der Filter angewendet wird. Beispielsweise  `-Action Search` würde der Filter nur angewendet, wenn Mitglieder der Rollengruppe, die im Parameter definiert sind, `Users` eine Inhaltssuche ausführen. In diesem Fall würde der Filter beim Exportieren von Suchergebnissen nicht angewendet. Verwenden Sie für Kompatibilitäts Grenzen  `-Action All` den Filter, damit dieser auf alle Suchaktionen angewendet wird. 

    Eine Liste der Inhalts Suchaktionen finden Sie im Abschnitt "New-ComplianceSecurityFilter" unter Konfigurieren der [Berechtigungs Filterung für die Inhaltssuche](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

Nachfolgend finden Sie Beispiele für die beiden Suchberechtigungsfilter, die zur Unterstützung des Szenarios mit den Compliance-Begrenzungen bei Contoso erstellt werden würden. Beide Beispiele umfassen eine durch Trennzeichen getrennte Filterliste, bei der die Postfach- und Websitefilter in den gleichen Suchberechtigungsfilter eingeschlossen sind und durch ein Komma getrennt sind.
  
### <a name="fourth-coffee"></a>Vierter Kaffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Weingut Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Schritt 5: Erstellen eines eDiscovery-Falls für Intra-Agency-Untersuchungen

Der letzte Schritt besteht darin, einen eDiscovery-Fall im Security & Compliance Center zu erstellen und dann die Rollengruppe hinzuzufügen, die Sie in Schritt 3 als Mitglied der Anfrage erstellt haben. Dies führt zu zwei wichtigen Merkmalen der Verwendung von Kompatibilitäts Grenzen:
  
- Nur Mitglieder der Rollengruppe, die dem Fall hinzugefügt werden, können den Fall im Security & Compliance Center anzeigen und darauf zugreifen. Wenn beispielsweise die Fourth Coffee Investigators-Rollengruppe das einzige Mitglied eines Falles ist, können Mitglieder der vierten Coffee-eDiscovery-Manager-Rollengruppe (oder Mitglieder einer anderen Rollengruppe) den Fall nicht sehen oder auf diese zugreifen.

- Wenn ein Mitglied der Rollengruppe, das einem Fall zugewiesen ist, eine mit dem Fall verknüpfte Suche ausführt, können die inhaltsspeicherorte in Ihrer Agentur nur durchsucht werden (Dies ist durch den Such Berechtigungsfilter definiert, den Sie in Schritt 4 erstellt haben).

So erstellen Sie eine Anfrage und weisen Mitglieder zu:

1. Wechseln Sie zur **eDiscovery-oder** **Advanced eDiscovery** -Seite im Security & Compliance Center, und erstellen Sie einen Fall.

2. Klicken Sie in der Liste der eDiscovery-Fälle auf den Namen des von Ihnen erstellten Falls.

3. Klicken Sie auf der Seite **diesen Fall Flyout verwalten** unter **Rollengruppen verwalten**auf ![ Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **hinzu**fügen.

    ![Hinzufügen einer Rollengruppe als Mitglied eines eDiscovery-Falls](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Wählen Sie in der Liste der Rollengruppen eine der Rollengruppen aus, die Sie in Schritt 3 erstellt haben, und klicken Sie auf **Hinzufügen**.

5. Klicken Sie im Flyout **dieses Fall verwalten** auf **Speichern** , um die Änderung zu speichern.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen

Mit Such Berechtigungs filtern können Sie auch steuern, wohin Inhalte für den Export weitergeleitet werden und welches Rechenzentrum beim Durchsuchen von Inhaltsspeicherorten in einer [SharePoint-Multi-Geo-Umgebung](https://go.microsoft.com/fwlink/?linkid=860840)durchsucht werden kann.
  
- **Exportieren von Suchergebnissen:** Sie können die Suchergebnisse aus Exchange-Postfächern, SharePoint-Websites und OneDrive-Konten aus einem bestimmten Datencenter exportieren. Dies bedeutet, dass Sie den Speicherort des Rechenzentrums angeben können, aus dem Suchergebnisse exportiert werden.

    Verwenden Sie den Parameter **Region** für **New-ComplianceSecurityFilter** oder **ComplianceSecurityFilter** Cmdlets, um zu erstellen oder zu ändern, durch welche Datencenter der Export weitergeleitet wird.
  
    |**Übergebener Wert**|**Speicherort des Datencenters**|
    |:-----|:-----|
    |NAM  <br/> |Nordamerika (Rechenzentren befinden sich in den USA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN <br/> |Kanada|
    |||

- **Routen von Inhalts suchen:** Sie können die Inhaltssuche von SharePoint-Websites und OneDrive-Konten an ein Satellitendaten Center weiterleiten. Dies bedeutet, dass Sie den Speicherort des Rechenzentrums angeben können, in dem Suchvorgänge ausgeführt werden.

    Verwenden Sie einen der folgenden Werte für den Parameter **Region** , um den Speicherort des Datencenters zu steuern, in dem Suchvorgänge beim Durchsuchen von SharePoint-Websites und OneDrive-Konten ausgeführt werden. 
  
    |**Übergebener Wert**|**Rechenzentrums-Routing Speicherorte für SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |Uns  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN  <br/> |Uns  <br/> |
    |AUS  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |KOR  <br/> |Das standardmäßige Rechenzentrum der Organisation  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |IND  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |Lam  <br/> |Uns  <br/> |
    |||

   Wenn Sie den **Region** -Parameter nicht für einen Such Berechtigungsfilter angeben, wird die primäre SharePoint-Region der Organisation durchsucht. Suchergebnisse werden in das nächstgelegene Datencenter exportiert.

   Zur Vereinfachung des Konzepts steuert der **Region** -Parameter das Rechenzentrum, das zum Suchen von Inhalten in SharePoint und OneDrive verwendet wird. Dies gilt nicht für die Suche nach Inhalten in Exchange, da Exchange-Inhalts suchen nicht an den geografischen Standort von Rechenzentren gebunden sind. Außerdem kann der gleiche **Regions** Parameterwert auch das Rechenzentrum diktieren, durch das die Exporte weitergeleitet werden. Dies ist häufig erforderlich, um die Verlagerung von Daten über geografische Grenzen hinweg zu steuern.

> [!NOTE]
> Wenn Sie Advanced eDiscovery verwenden, steuert der **Region** -Parameter nicht die Region, aus der Daten exportiert werden. Daten werden aus dem primären Datencenter der Organisation exportiert. Außerdem ist die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort von Rechenzentren gebunden. Alle Rechenzentren werden durchsucht. Weitere Informationen zu Advanced eDiscovery finden Sie unter [Übersicht über die erweiterte eDiscovery-Lösung in Microsoft 365](overview-ediscovery-20.md).

Im folgenden finden Sie Beispiele für die Verwendung des **Region** -Parameters beim Erstellen von Such Berechtigungs Filtern nach Kompatibilitäts Grenzen. Dabei wird davon ausgegangen, dass sich die Fourth Coffee-Tochtergesellschaft in Nordamerika befindet und dass sich die Weinkellerei in Europa befindet. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Beachten Sie beim Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen die folgenden Aspekte.
  
- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Alle Rechenzentren werden durchsucht, wenn Sie Postfächer durchsuchen. Verwenden Sie zum Begrenzen des Bereichs, in dem Exchange-Postfächer durchsucht werden, den Parameter **Filters** beim Erstellen oder Ändern eines Such Berechtigungs Filters. 

- Wenn ein eDiscovery-Manager in mehreren SharePoint-Regionen durchsuchen muss, müssen Sie ein anderes Benutzerkonto erstellen, mit dem der eDiscovery-Manager im Such Berechtigungsfilter die Region angibt, in der sich die SharePoint-Websites oder OneDrive-Konten befinden. Weitere Informationen zum Einrichten dieser Einstellung finden Sie im Abschnitt "Suchen nach Inhalten in einer SharePoint-Umgebung mit mehreren geografischen Inhalten" in der [Inhaltssuche](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment).

- Bei der Suche nach Inhalten in SharePoint und OneDrive leitet der Parameter **Region** die Suche entweder an den primären oder den Satelliten Speicherort, an dem der eDiscovery-Manager eDiscovery-Untersuchungen durchführt. Wenn ein eDiscovery-Manager SharePoint-und OneDrive-Websites außerhalb der Region durchsucht, die im Such Berechtigungsfilter angegeben ist, werden keine Suchergebnisse zurückgegeben.

- Beim Exportieren von Suchergebnissen werden Inhalte aus allen Inhaltsspeicherorten (einschließlich Exchange, Skype for Business, SharePoint, OneDrive und anderen Diensten, die Sie mithilfe des Inhalts Such Tools suchen können) in den Azure-Speicherort im Rechenzentrum hochgeladen, das durch den **Region** -Parameter angegeben wird. Auf diese Weise können Organisationen innerhalb der Compliance-Richtlinien bleiben, da Inhalte nicht über kontrollierte Grenzen hinweg exportiert werden können. Wenn im Such Berechtigungsfilter kein Bereich angegeben ist, wird der Inhalt in das primäre Datencenter der Organisation hochgeladen.

- Sie können einen vorhandenen Such Berechtigungsfilter bearbeiten, um den Bereich hinzuzufügen oder zu ändern, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Verwenden von Kompatibilitäts Grenzen für SharePoint-Hub-Websites

[SharePoint-Hub-Websites](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) richten sich häufig nach den gleichen geografischen oder behördlichen Grenzen, denen eDiscovery-Konformitäts Grenzen folgen. Das bedeutet, dass Sie die Website-ID-Eigenschaft des Hub-Standorts verwenden können, um eine Konformitäts Grenze zu erstellen. Verwenden Sie dazu das Cmdlet [Get-SPOHubSite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) in SharePoint Online PowerShell, um die Website-ID für den Hub-Standort abzurufen, und verwenden Sie dann diesen Wert für die Abteilungs-ID-Eigenschaft, um einen Such Berechtigungsfilter zu erstellen.

Verwenden Sie die folgende Syntax, um einen Such Berechtigungsfilter für eine SharePoint-Hub-Website zu erstellen:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Im folgenden finden Sie ein Beispiel für das Erstellen eines Such Berechtigungs Filters für einen Hub-Standort für die Weingut-Agentur "Winery":

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Einschränkungen bei der Konformitäts Begrenzung

Beachten Sie beim Verwalten von eDiscovery-Fällen und Untersuchungen zur Verwendung von Compliance-Grenzen die folgenden Einschränkungen.
  
- Beim Erstellen und Ausführen einer Suche können Sie Inhaltsspeicherorte auswählen, die sich außerhalb Ihrer Organisation befinden. Aufgrund des Filters für Suchberechtigungen sind Inhalte aus diesen Speicherorten jedoch nicht in den Suchergebnissen enthalten.

- Compliance-Grenzen gelten nicht für Aufbewahrungen in eDiscovery-Fällen. Dies bedeutet, dass ein eDiscovery-Manager in einer Organisation einen Benutzer in einer anderen Organisation im Haltebereich platzieren kann. Die Compliance-Begrenzung wird jedoch erzwungen, wenn der eDiscovery-Manager die Inhaltsspeicherorte des Benutzers durchsucht, der in den Haltebereich gesetzt wurde. Dies bedeutet, dass der eDiscovery-Manager nicht in der Lage ist, die Inhaltsspeicherorte des Benutzers zu durchsuchen, auch wenn er den Benutzer im Haltebereich platzieren konnte.

    Außerdem gelten Haltestatistiken nur für Inhaltsspeicherorte in der Organisation.

- Suchberechtigungsfilter werden nicht auf öffentliche Exchange-Ordner angewendet.

## <a name="more-information"></a>Weitere Informationen

- Wenn ein Postfach delizensiert oder vorläufig gelöscht wird, werden Azure AD Attribute nicht mehr mit dem Postfach synchronisiert. Wenn das Postfach beim Löschen eines Haltestatus gespeichert wurde, werden die im Postfach aufbewahrten Inhalte weiterhin einer Kompatibilitäts Grenze oder einem Such Berechtigungsfilter unterworfen, basierend auf dem Zeitpunkt, zu dem die Azure AD Attribute zuletzt synchronisiert wurden, bevor das Postfach gelöscht wurde. 

    Darüber hinaus wird die Synchronisierung zwischen dem Postfach des Benutzers und dem OneDrive-Konto beendet, wenn das Postfach delizensiert oder vorläufig gelöscht wird. Der zuletzt gestempelte Wert des Compliance-Attributs für das OneDrive-Konto bleibt erhalten.

- Das Attribut Compliance wird alle sieben Tage vom Exchange-Postfach eines Benutzers auf sein OneDrive-Konto synchronisiert. Wie bereits erwähnt, tritt diese Synchronisierung nur auf, wenn dem Benutzer eine Exchange Online und SharePoint Online Lizenz zugewiesen ist und das Postfach des Benutzers mindestens 10 MB beträgt.

- Wenn Kompatibilitäts Grenzen und Such Berechtigungsfilter sowohl für das Postfach eines Benutzers als auch für das OneDrive-Konto implementiert werden, wird empfohlen, das Postfach eines Benutzers und nicht das OneDrive-Konto zu löschen. Das heißt, wenn Sie das Postfach eines Benutzers löschen, sollten Sie auch das OneDrive-Konto des Benutzers entfernen.

- Es gibt Situationen (beispielsweise ein zurückkehrender Mitarbeiter), bei denen ein Benutzer über zwei oder mehr OneDrive-Konten verfügen kann. In diesen Fällen wird nur das primäre OneDrive-Konto, das dem Benutzer in Azure AD zugeordnet ist, synchronisiert.

- Compliance-Grenzen und Such Berechtigungsfilter hängen von Attributen ab, die auf Inhalten in Exchange, OneDrive und SharePoint und der nachfolgenden Indizierung dieses gestempelten Inhalts gestempelt werden. 

- Es wird nicht empfohlen, Ausschlussfilter (beispielsweise `-not()` die Verwendung in einem Such Berechtigungsfilter) für eine inhaltsbasierte Konformitäts Grenze zu verwenden. Die Verwendung eines Ausschluss Filters kann unerwartete Ergebnisse haben, wenn Inhalte mit kürzlich aktualisierten Attributen nicht indiziert wurden. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer kann Such Berechtigungsfilter erstellen und verwalten (mithilfe von New-ComplianceSecurityFilter-und ComplianceSecurityFilter-Cmdlets)?**
  
Zum Erstellen, anzeigen und Ändern von Such Berechtigungs filtern müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center sein.
  
**Wenn ein eDiscovery-Manager mehreren Rollengruppen zugewiesen ist, die sich über mehrere Agenturen erstrecken, suchen Sie nach Inhalten in einer oder einer Agentur?**
  
Der eDiscovery-Manager kann der Suchabfrage Parameter hinzufügen, die die Suche auf eine bestimmte Agentur einschränken. Wenn beispielsweise eine Organisation die **CustomAttribute10** -Eigenschaft für die Unterscheidung von Agenturen angegeben hat, können Sie die folgenden Informationen an Ihre Suchabfrage anfügen, um Postfächer und OneDrive-Konten in einer bestimmten Agentur zu suchen:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**Was geschieht, wenn der Wert des Attributs, das als Kompatibilitätsattribut in einem Such Berechtigungsfilter verwendet wird, geändert wird?**
  
Es dauert bis zu drei Tage, bis ein Such Berechtigungsfilter zum Erzwingen der Konformitäts Grenze verwendet wird, wenn der Wert des im Filter verwendeten Attributs geändert wird. Beispielsweise wird im Contoso-Szenario angenommen, dass ein Benutzer in der Fourth Coffee-Agentur an die Weingut-Agentur von Winery übergeben wird. Daher wird der Wert des **Department** -Attributs für das User-Objekt von *fourthcoffee* in *cohowinery*geändert. In dieser Situation erhalten vierter Kaffee eDiscovery und Investoren Suchergebnisse für diesen Benutzer für drei Tage nach dem Ändern des Attributs. In ähnlicher Weise dauert es bis zu drei Tage, bis die Weingut eDiscovery-Manager und Ermittler Suchergebnisse für den Benutzer erhalten.
  
**Kann ein eDiscovery-Manager Inhalte aus zwei separaten Kompatibilitäts Grenzen anzeigen?**
  
Ja, dies kann beim Durchsuchen von Exchange-Postfächern geschehen, indem der eDiscovery-Manager Rollengruppen hinzugefügt wird, die eine Sichtbarkeit für beide Agenturen haben. Beim Durchsuchen von SharePoint-Websites und OneDrive-Konten kann ein eDiscovery-Manager jedoch nur dann nach Inhalten in unterschiedlichen Kompatibilitäts Grenzen suchen, wenn sich die Agenturen in derselben Region oder an einem geografischen Standort befinden. **Hinweis:** Diese Einschränkung für Websites gilt nicht für Advanced eDiscovery, da die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort gebunden ist.
  
**Funktionieren Such Berechtigungsfilter für eDiscovery Case holdes, Microsoft 365-Aufbewahrungsrichtlinien oder DLP?**
  
Nein, diesmal nicht.
  
**Wenn ich einen Bereich zum Steuern der Inhaltsangabe, aber keine SharePoint-Organisation in dieser Region habe, kann ich dennoch SharePoint durchsuchen?**
  
Wenn der im Such Berechtigungsfilter angegebene Bereich nicht in Ihrer Organisation vorhanden ist, wird der Standardbereich durchsucht.
  
**Wie hoch ist die maximale Anzahl von Such Berechtigungs filtern, die in einer Organisation erstellt werden können?**
  
Es gibt keine Beschränkung für die Anzahl der Such Berechtigungsfilter, die in einer Organisation erstellt werden können. Die Suchleistung wird jedoch beeinträchtigt, wenn mehr als 100 Such Berechtigungsfilter vorhanden sind. Um die Anzahl der Such Berechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive in einem einzigen Such Berechtigungsfilter kombinieren, wenn möglich.
