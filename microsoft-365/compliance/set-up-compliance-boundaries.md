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
description: Erfahren Sie, wie Sie Compliancegrenzen verwenden, um logische Grenzen zu erstellen, die die Speicherorte von Benutzerinhalten steuern, die ein eDiscovery-Manager in Microsoft 365 durchsuchen kann.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80f1c6705550d21ac54a0fb4dda2b605b497adbc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919501"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Einrichten von Compliancegrenzen für eDiscovery-Untersuchungen

Die Anleitungen in diesem Artikel können bei verwendung von Core eDiscovery oder Advanced eDiscovery zum Verwalten von Untersuchungen angewendet werden.

Compliancegrenzen erstellen logische Grenzen in einer Organisation, die die Speicherorte von Benutzerinhalten (z. B. Postfächer, #A0 und #A1) steuern, die eDiscovery-Manager durchsuchen können. Außerdem steuern Compliancegrenzen, wer auf eDiscovery-Fälle zugreifen kann, die zum Verwalten der rechts-, personal- oder sonstigen Untersuchungen in Ihrer Organisation verwendet werden. Die Notwendigkeit von Compliancegrenzen ist häufig für multinationale Unternehmen erforderlich, die geografische Boarder und Vorschriften einhalten müssen, sowie für Regierungen, die häufig in verschiedene Behörden unterteilt sind. In Microsoft 365 helfen Ihnen Compliancegrenzen, diese Anforderungen zu erfüllen, wenn Sie Inhaltssuchen durchführen und Untersuchungen mit eDiscovery-Fällen verwalten.
  
Wir verwenden das Beispiel in der folgenden Abbildung, um zu erläutern, wie Compliancegrenzen funktionieren.
  
![Compliancegrenzen bestehen aus Suchberechtigungsfiltern, die den Zugriff auf Behörden und Administratorrollegruppen steuern, die den Zugriff auf eDiscovery-Fälle steuern.](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In diesem Beispiel ist Contoso LTD eine Organisation, die aus zwei Niederlassungen besteht, Fourth Coffee und Coho Winery. Das Unternehmen erfordert, dass eDiscovery- Manger und Ermittler nur die #A0, #A1 und #A1 in ihrer Agentur durchsuchen können. Außerdem können eDiscovery-Manager und Ermittler nur eDiscovery-Fälle in ihrer Agentur sehen, und sie können nur auf die Fälle zugreifen, bei denen sie Mitglied sind. Darüber hinaus können Ermittler in diesem Szenario keine Inhaltsstandorte in einem Fall platzieren oder Inhalte aus einem Fall exportieren. Hier sehen Sie, wie Compliancegrenzen diese Anforderungen erfüllen.
  
- Die Filterfunktion für Suchberechtigungen in der Inhaltssuche steuert die Inhaltsorte, die eDiscovery-Manager und Ermittler durchsuchen können. Dies bedeutet, dass eDiscovery-Manager und -Ermittler in der Fourth Coffee-Organisation nur Inhaltsspeicherorte in der Fourth Coffee-Niederlassung durchsuchen können. Die gleiche Einschränkung gilt für die Coho Winery-Tochtergesellschaft.

- Rollengruppen bieten die folgenden Funktionen für Compliancegrenzen:

  - Steuern, wer die eDiscovery-Fälle im Security & Compliance Center sehen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur eDiscovery-Fälle in ihrer Organisation anzeigen können.

  - Steuern, wer Einem eDiscovery-Fall Mitglieder zuweisen kann. Dies bedeutet, dass eDiscovery-Manager und -Ermittler nur den Fällen, von denen sie Mitglied sind, Mitglieder zuordnen können.

  - Steuern Sie die eDiscovery-bezogenen Aufgaben, die Mitglieder ausführen können, indem Sie Rollen hinzufügen oder entfernen, die bestimmte Berechtigungen zuweisen.

Hier sehen Sie den Prozess zum Einrichten von Compliancegrenzen:
  
[Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Agenturen](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Schritt 2: Senden einer Anforderung beim #A0 zum Synchronisieren des Benutzerattributs mit #A1](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Schritt 3: Erstellen einer Rollengruppe für jede Agentur](#step-3-create-a-role-group-for-each-agency)

[Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Schritt 5: Erstellen eines eDiscovery-Falls für eine agenturinterne Untersuchung](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Vor dem Einrichten von Compliancegrenzen

Sie müssen die folgenden Voraussetzungen erfüllen, bevor das Azure Active Directory (Azure AD)-Attribut, das Sie ausweisen (in Schritt 1), erfolgreich mit dem #A0 eines Benutzers synchronisiert werden kann (in Schritt 2):

- Benutzern muss eine Exchange Online-Lizenz und eine SharePoint Online-Lizenz zugewiesen sein.

- Benutzerpostfächer müssen mindestens 10 MB groß sein. Wenn das Postfach eines Benutzers weniger als 10 MB beträgt, wird das Attribut, das zum Definieren Ihrer Agenturen verwendet wird, nicht mit dem #A0 des Benutzers synchronisiert.

- Kompatibilitätsgrenzen und die Attribute zum Erstellen von Suchberechtigungsfiltern erfordern, dass Azure Active Directory (Azure AD)-Attribute mit Benutzerpostfächern synchronisiert werden. Führen Sie das [Cmdlet Get-User](/powershell/module/exchange/get-user) in Exchange Online PowerShell aus, um zu überprüfen, ob die zu verwendenden Attribute synchronisiert wurden. In der Ausgabe dieses Cmdlets werden die Azure AD-Attribute angezeigt, die mit Exchange Online synchronisiert wurden.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Schritt 1: Identifizieren eines Benutzerattributs zum Definieren Ihrer Agenturen

Der erste Schritt besteht in der Auswahl eines Azure AD-Attributs, das Ihre Agenturen definiert. Dieses Attribut wird verwendet, um den Suchberechtigungsfilter zu erstellen, der einen eDiscovery-Manager beschränkt, nur die Inhaltspositionen von Benutzern zu durchsuchen, denen ein bestimmter Wert für dieses Attribut zugewiesen ist. Angenommen, Contoso entscheidet sich für die Verwendung des **Department-Attributs.** Der Wert für dieses Attribut für Benutzer in der Fourth Coffee-Niederlassung wäre und der Wert für Benutzer  `FourthCoffee`  in der Coho Winery-Niederlassung `CohoWinery` . In Schritt 4 verwenden Sie dieses Paar (z. B. Department:FourthCoffee ), um die Speicherorte von Benutzerinhalten zu begrenzen, die `attribute:value` eDiscovery-Manager durchsuchen können.  
  
Hier ist eine Liste der Azure AD-Benutzerattribute, die Sie für Compliancegrenzen verwenden können:
  
- Company

- CustomAttribute1 - CustomAttribute15

- Abteilung

- Büro

- C (Zwei-Buchstaben-Ländercode) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> Dieses Attribut ordnet der CountryOrRegion-Eigenschaft zu, die durch Ausführen des **Cmdlets Get-User** in Exchange Online PowerShell zurückgegeben wird. Das Cmdlet gibt den lokalisierten Ländernamen zurück, der aus dem zweibuchstabenigen Ländercode übersetzt wird. Weitere Informationen finden Sie in der Beschreibung des CountryOrRegion-Parameters im [Cmdlet-Referenzartikel Set-User.](/powershell/module/exchange/set-user)

Obwohl mehr Benutzerattribute verfügbar sind, insbesondere für #A0 sind die oben aufgeführten Attribute die einzigen, die derzeit von OneDrive unterstützt werden.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Schritt 2: Senden einer Anforderung beim #A0 zum Synchronisieren des Benutzerattributs mit #A1

Im nächsten Schritt wird eine Anforderung beim #A0 gestellt, um das Azure AD-Attribut, das Sie in Schritt 1 ausgewählt haben, mit allen #A1 in Ihrer Organisation zu synchronisieren. Nach dieser Synchronisierung wird das Attribut (und sein Wert), das Sie in Schritt 1 ausgewählt haben, einer ausgeblendeten verwalteten Eigenschaft namens `ComplianceAttribute` zugeordnet. Verwenden Sie dieses Attribut, um den Suchberechtigungsfilter für OneDrive in Schritt 4 zu erstellen.
  
Fügen Sie die folgenden Informationen ein, wenn Sie die Anforderung an den Microsoft-Support übermitteln:
  
- Der Standarddomänenname Ihrer Organisation

- Der Name des Azure AD-Attributs (aus Schritt 1)

- Der folgende Titel oder eine Beschreibung des Zwecks der Supportanfrage: "Aktivieren der OneDrive for Business-Synchronisierung mit Azure AD für Compliancesicherheitsfilter". Dadurch wird die Anforderung an das eDiscovery-Engineeringteam weiter geroutet, das die Anforderung implementiert.

Nachdem die technische Änderung vorgenommen wurde und das Attribut mit OneDrive synchronisiert wurde, sendet Ihnen der #A0 die Buildnummer, in der die Änderung vorgenommen wurde, sowie ein geschätztes Bereitstellungsdatum. Der Bereitstellungsprozess dauert in der Regel 4 bis 6 Wochen, nachdem Sie die Supportanfrage übermittelt haben.
  
> [!IMPORTANT]
> Sie können Schritt 3 bis Schritt 5 abschließen, bevor diese Attributänderung bereitgestellt wird. Beim Ausführen von Inhaltssuchen werden jedoch erst nach der Bereitstellung der Attributsynchronisierung Dokumente von #A0 zurück, die in einem Suchberechtigungsfilter angegeben sind.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Schritt 3: Erstellen einer Rollengruppe für jede Agentur

Im nächsten Schritt erstellen Sie die Rollengruppen im Security & Compliance Center, die sich an Ihren Behörden ausrichten. Es wird empfohlen, eine Rollengruppe zu erstellen, indem Sie die integrierte Gruppe der eDiscovery-Manager kopieren, die entsprechenden Mitglieder hinzufügen und Rollen entfernen, die möglicherweise nicht Ihren Anforderungen entsprechen. Weitere Informationen zu eDiscovery-bezogenen Rollen finden Sie unter [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).
  
Um die Rollengruppen zu erstellen, wechseln Sie im Security & Compliance Center zur Seite **Berechtigungen**, und erstellen Sie eine Rollengruppe für jedes Team in jeder Organisation, die Compliance-Begrenzungen sowie eDiscovery-Fälle zum Verwalten von Untersuchungen verwendet.
  
Mithilfe des Contoso-Compliance-Begrenzungsszenarios müssen vier Rollengruppen erstellt und die entsprechenden Mitglieder hinzugefügt werden.
  
- eDiscovery-Manager von Fourth Coffee

- Fourth Coffee-Ermittler

- eDiscovery-Manager von Coho Winery

- Coho Winery-Ermittler
  
Um die Anforderungen des Contoso-Compliance-Begrenzungsszenarios  zu erfüllen, würden Sie auch die Rollen "Hold" und **"Export"** aus den Rollengruppen "Ermittler" entfernen, um zu verhindern, dass Ermittler Halteplätze für Inhaltsstandorte platzieren und Inhalte aus einem Fall exportieren.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Schritt 4: Erstellen eines Suchberechtigungsfilters zum Erzwingen der Compliancegrenze

Nachdem Sie Rollengruppen für jede Agentur erstellt haben, besteht der nächste Schritt im Erstellen der Suchberechtigungsfilter, die jede Rollengruppe der jeweiligen Agentur zuordnen, und definiert die Compliancegrenze selbst. Sie müssen einen Suchberechtigungsfilter für jede Agentur erstellen. Weitere Informationen zum Erstellen von Sicherheitsberechtigungsfiltern finden Sie unter [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).
  
Hier ist die Syntax, die zum Erstellen eines Suchberechtigungsfilters verwendet wird, der für Compliancegrenzen verwendet wird.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Im Folgenden finden Sie eine Beschreibung der einzelnen Parameter im Befehl:
  
- `FilterName`: Gibt den Namen des Filters an. Verwenden Sie einen Namen, der die Agentur beschreibt oder identifiziert, in der der Filter verwendet wird.

- `Users`: Gibt die Benutzer oder Gruppen an, die diesen Filter auf die von ihnen durchzuführenden Inhaltssuchaktionen angewendet bekommen. Für Compliancegrenzen gibt dieser Parameter die Rollengruppen an (die Sie in Schritt 3 erstellt haben) in der Agentur, für die Sie den Filter erstellen. Beachten Sie, dass es sich um einen mehrwertigen Parameter handelt, sodass Sie eine oder mehrere Rollengruppen, getrennt durch Kommas, angeben können.

- `Filters`: Gibt die Suchkriterien für den Filter an. Für die Compliancegrenzen definieren Sie die folgenden Filter. Jeder gilt für einen Inhaltsspeicherort. 

    - `Mailbox`: Gibt die Postfächer an, die von den im Parameter definierten  `Users` Rollengruppen durchsucht werden können. Für Compliancegrenzen ist  *ComplianceAttribute*  das gleiche Attribut, das Sie in Schritt 1 identifiziert haben, und  *AttributeValue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die Postfächer in einer bestimmten Agentur durchsuchen. Beispiel: `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: Gibt die #A0 an, die von den im Parameter definierten Rollengruppen `Users` durchsucht werden können. Verwenden Sie für den #A0 die tatsächliche Zeichenfolge  `ComplianceAttribute` . Dadurch wird dasselbe Attribut wie in Schritt 1 identifiziert, das als Ergebnis der in Schritt 2 übermittelten Supportanfrage mit #A0 synchronisiert wurde. *AttributValue*  gibt die Agentur an. Mit diesem Filter können Mitglieder der Rollengruppe nur die #A0 in einer bestimmten Agentur durchsuchen. Beispiel:  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: Gibt die SharePoint-Websites an, die von den im Parameter definierten  `Users` Rollengruppen durchsucht werden können. *SharePointURL* gibt die Websites in der Agentur an, die Mitglieder der Rollengruppe durchsuchen können. Zum Beispiel: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Beachten `Site` `Site_Path` Sie, dass die Filter über einen **-oder-Operator verbunden** sind.

     > [!NOTE]
     > Die Syntax für den `Filters` Parameter enthält eine *Filterliste*. Eine Filterliste ist ein Filter, der einen Postfachfilter und einen Standortfilter enthält, der durch ein Komma getrennt ist. Beachten Sie im vorherigen Beispiel, dass ein Komma Mailbox_ComplianceAttribute **und** **Site_ComplianceAttribute** `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` trennt. Wenn dieser Filter während der Ausführung einer Inhaltssuche verarbeitet wird, werden aus der Filterliste zwei Filter für Suchberechtigungen erstellt: ein Postfachfilter und ein Websitefilter. Eine Alternative zur Verwendung einer Filterliste wäre das Erstellen von zwei separaten Suchberechtigungsfiltern für jede Agentur: ein Suchberechtigungsfilter für das Postfachattribut und ein Filter für die Websiteattribute. In beiden Fällen sind die Ergebnisse identisch. Die Verwendung einer Filterliste oder das Erstellen separater Suchberechtigungsfilter ist eine Bevorzugte Frage.

- `Action`: Gibt den Typ der Compliancesuchaktion an, auf die der Filter angewendet wird. Würde beispielsweise den Filter nur anwenden, wenn Mitglieder der im Parameter definierten Rollengruppe  `-Action Search` `Users` eine Inhaltssuche ausführen. In diesem Fall wird der Filter beim Exportieren von Suchergebnissen nicht angewendet. Verwenden Sie für Compliancegrenzen,  `-Action All` damit der Filter auf alle Suchaktionen angewendet wird. 

    Eine Liste der Aktionen für die Inhaltssuche finden Sie im Abschnitt "New-ComplianceSecurityFilter" unter [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

Nachfolgend finden Sie Beispiele für die beiden Suchberechtigungsfilter, die zur Unterstützung des Szenarios mit den Compliance-Begrenzungen bei Contoso erstellt werden würden. Beide Beispiele umfassen eine durch Trennzeichen getrennte Filterliste, bei der die Postfach- und Websitefilter in den gleichen Suchberechtigungsfilter eingeschlossen sind und durch ein Komma getrennt sind.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Schritt 5: Erstellen eines eDiscovery-Falls für agenturinterne Untersuchungen

Der letzte Schritt besteht im Erstellen eines Core eDiscovery- oder Advanced eDiscovery-Falls im Microsoft 365 Compliance Center, und fügen Sie dann die Rollengruppe hinzu, die Sie in Schritt 3 als Mitglied des Falls erstellt haben. Dies führt zu zwei wichtigen Merkmalen der Verwendung von Compliancegrenzen:
  
- Nur Mitglieder der Rollengruppe, die dem Fall hinzugefügt wurden, können den Fall im Security & Compliance Center sehen und darauf zugreifen. Wenn beispielsweise die Rollengruppe "Fourth Coffee Investigators" das einzige Mitglied eines Falls ist, können Mitglieder der Rollengruppe "Fourth Coffee eDiscovery Managers" (oder Mitglieder einer anderen Rollengruppe) den Fall nicht sehen oder darauf zugreifen.

- Wenn ein Mitglied der Rollengruppe, die einem Fall zugewiesen ist, eine dem Fall zugeordnete Suche ausgeführt, kann es nur die Inhaltsstandorte innerhalb ihrer Agentur durchsuchen (dies wird durch den in Schritt 4 erstellten Suchberechtigungsfilter definiert).)

So erstellen Sie einen Fall und weisen Mitglieder zu:

1. Wechseln Sie zur **Seite Core eDiscovery** oder **Advanced eDiscovery** im Microsoft 365 Compliance Center, und erstellen Sie einen Fall.

2. Klicken Sie in der Liste der Fälle auf den Namen des von Ihnen erstellten Falls.

3. Klicken Sie **auf der Seite** Flyout in diesem Fall verwalten unter **Rollengruppen** verwalten auf ![ Hinzufügen (Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **hinzufügen).**

    ![Hinzufügen einer Rollengruppe als Mitglied eines eDiscovery-Falls](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Wählen Sie in der Liste der Rollengruppen eine der Rollengruppen aus, die Sie in Schritt 3 erstellt haben, und klicken Sie auf **Hinzufügen**.

5. Klicken **Sie im** **Flyout Für** diesen Fall verwalten auf Speichern, um die Änderung zu speichern.

> [!NOTE]
> Beim Hinzufügen einer Rollengruppe zu einem Fall können Sie nur die Rollengruppen hinzufügen, in denen Sie Mitglied sind.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen

Mithilfe von Suchberechtigungsfiltern können Sie auch steuern, wo Inhalte für den Export geroutet werden und welches Datencenter beim Durchsuchen von Inhaltsspeicherorten in einer [SharePoint Multi-Geo-Umgebung durchsucht werden kann.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Exportieren von Suchergebnissen:** Sie können die Suchergebnisse aus #A0, #A1 und #A1 aus einem bestimmten Datencenter exportieren. Dies bedeutet, dass Sie den Speicherort des Datencenters angeben können, aus dem Suchergebnisse exportiert werden.

    Verwenden Sie **den Parameter Region** für Cmdlets **New-ComplianceSecurityFilter** oder **Set-ComplianceSecurityFilter,** um zu erstellen oder zu ändern, welches Datencenter der Export durchgeroutet wird.
  
    |**Übergebener Wert**|**Rechenzentrumsspeicherort**|
    |:-----|:-----|
    |NAM  <br/> |Nordamerika (Rechenzentren befinden sich in den USA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN <br/> |Kanada|
    |||

- **Routen von Inhaltssuchen:** Sie können die Inhaltssuchen von #A0 und #A1 an ein Satellitendatencenter weiter routen. Dies bedeutet, dass Sie den Rechenzentrumsspeicherort angeben können, an dem die Suche ausgeführt wird.

    Verwenden Sie einen der folgenden Werte für den **Parameter Region,** um den Speicherort des Datencenters zu steuern, in dem die Suche beim Durchsuchen von #A0 und #A1 ausgeführt wird. 
  
    |**Übergebener Wert**|**Datencenterroutingspeicherorte für SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |USA  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |CAN  <br/> |USA  <br/> |
    |AUS  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |KOR  <br/> |Standarddatencenter der Organisation  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |IND  <br/> |Asiatisch-pazifischer Raum  <br/> |
    |"LAM"  <br/> |USA  <br/> |
    |NOR  <br/> |Europa |
    |BRA  <br/> |Nordamerikanische Rechenzentren |
    |||

   Wenn Sie den Parameter **Region** für einen Suchberechtigungsfilter nicht angeben, wird die primäre SharePoint-Region der Organisation durchsucht. Suchergebnisse werden in das nächstgelegene Datencenter exportiert.

   Um das Konzept zu vereinfachen, steuert der **Parameter Region** das Datencenter, das zum Suchen nach Inhalten in SharePoint und OneDrive verwendet wird. Dies gilt nicht für die Suche nach Inhalten in Exchange, da Die Suche nach Exchange-Inhalten nicht an den geografischen Standort von Rechenzentren gebunden ist. Darüber hinaus kann der gleiche **Parameterwert Region** auch das Datencenter bestimmen, durch das Exporte geroutet werden. Dies ist häufig erforderlich, um die Bewegung von Daten über geografische Boarder hinweg zu steuern.

> [!NOTE]
> Wenn Sie Advanced eDiscovery verwenden, kontrolliert der **Parameter Region** nicht die Region, aus der Daten exportiert werden. Daten werden aus dem primären Datencenter der Organisation exportiert. Außerdem ist die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort von Rechenzentren gebunden. Alle Rechenzentren werden durchsucht. Weitere Informationen zu Advanced eDiscovery finden Sie [unter Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Im Folgenden finden Sie Beispiele für die Verwendung des **Parameters Region** beim Erstellen von Suchberechtigungsfiltern für Compliancegrenzen. Dies setzt voraus, dass sich die Fourth Coffee-Niederlassung in Nordamerika und Coho Winery in Europa befindet. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Beachten Sie die folgenden Punkte beim Suchen und Exportieren von Inhalten in Multi-Geo-Umgebungen.
  
- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Alle Rechenzentren werden durchsucht, wenn Sie Postfächer durchsuchen. Verwenden Sie zum Einschränken des Bereichs, in dem Exchange-Postfächer durchsucht werden, den **Parameter Filters,** wenn Sie einen Filter für Suchberechtigungen erstellen oder ändern. 

- Wenn ein eDiscovery-Manager in mehreren #A0 suchen muss, müssen Sie ein anderes Benutzerkonto für diesen eDiscovery-Manager erstellen, das im Suchberechtigungsfilter verwendet werden soll, um die Region anzugeben, in der sich die #A1 oder #A2 befinden. Weitere Informationen zum Einrichten dieser Einrichtung finden Sie im Abschnitt "Suchen nach Inhalten in einer SharePoint Multi-Geo-Umgebung" unter [Inhaltssuche](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment).

- Bei der Suche nach Inhalten in SharePoint und OneDrive leitet der **Parameter Region** die Suche entweder an den primären Oder Satellitenspeicherort weiter, an dem der eDiscovery-Manager eDiscovery-Untersuchungen durchführen wird. Wenn ein eDiscovery-Manager SharePoint- und #A0 außerhalb der Region durchsucht, die im Filter für Suchberechtigungen angegeben ist, werden keine Suchergebnisse zurückgegeben.

- Beim Exportieren von Suchergebnissen werden Inhalte aus allen Inhaltsspeicherorten (einschließlich Exchange, Skype for Business, SharePoint, OneDrive und anderen Diensten, die Sie mithilfe des Inhaltssuchtools durchsuchen können) in den Azure Storage-Speicherort im Datencenter hochgeladen, das durch den Parameter **Region** angegeben wird. Dies hilft Organisationen, die Einhaltung der Vorschriften zu gewährleisten, da inhalte nicht über kontrollierte Grenzen hinweg exportiert werden dürfen. Wenn im Suchberechtigungsfilter keine Region angegeben ist, werden Inhalte in das primäre Datencenter der Organisation hochgeladen.

- Sie können einen vorhandenen Suchberechtigungsfilter bearbeiten, um die Region hinzuzufügen oder zu ändern, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Verwenden von Compliancegrenzen für SharePoint-Hubwebsites

[SharePoint-Hubwebsites](/sharepoint/dev/features/hub-site/hub-site-overview) richten sich häufig nach den gleichen geografischen oder Agenturgrenzen wie eDiscovery-Compliancegrenzen. Das bedeutet, dass Sie die Website-ID-Eigenschaft des Hubstandorts verwenden können, um eine Compliancegrenze zu erstellen. Verwenden Sie dazu das [Cmdlet Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) in SharePoint Online PowerShell, um die SiteId für die Hubwebsite zu erhalten, und verwenden Sie dann diesen Wert für die Department ID-Eigenschaft, um einen Suchberechtigungsfilter zu erstellen.

Verwenden Sie die folgende Syntax, um einen Suchberechtigungsfilter für eine #A0 zu erstellen:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Hier ist ein Beispiel für das Erstellen eines Suchberechtigungsfilters für eine Hubwebsite für die Coho Winery-Agentur:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Einschränkungen bei der Einhaltung von Grenzen

Beachten Sie die folgenden Einschränkungen bei der Verwaltung von eDiscovery-Fällen und Untersuchungen, bei denen Compliancegrenzen verwendet werden.
  
- Beim Erstellen und Ausführen einer Suche können Sie Inhaltsspeicherorte auswählen, die sich außerhalb Ihrer Organisation befinden. Aufgrund des Filters für Suchberechtigungen sind Inhalte aus diesen Speicherorten jedoch nicht in den Suchergebnissen enthalten.

- Compliancegrenzen gelten nicht für halte in eDiscovery-Fällen. Dies bedeutet, dass ein eDiscovery-Manager in einer Organisation einen Benutzer in einer anderen Organisation im Haltebereich platzieren kann. Die Compliance-Begrenzung wird jedoch erzwungen, wenn der eDiscovery-Manager die Inhaltsspeicherorte des Benutzers durchsucht, der in den Haltebereich gesetzt wurde. Dies bedeutet, dass der eDiscovery-Manager nicht in der Lage ist, die Inhaltsspeicherorte des Benutzers zu durchsuchen, auch wenn er den Benutzer im Haltebereich platzieren konnte.

    Außerdem gelten Haltestatistiken nur für Inhaltsspeicherorte in der Organisation.

- Suchberechtigungsfilter werden nicht auf öffentliche Exchange-Ordner angewendet.

## <a name="more-information"></a>Weitere Informationen

- Wenn ein Postfach nicht lizenziert oder als soft gelöscht wird, werden Azure AD-Attribute nicht mehr mit dem Postfach synchronisiert. Wenn beim Löschen des Postfachs ein Haltebereich aktiviert wurde, unterliegt der im Postfach aufbewahrte Inhalt weiterhin einer Compliancegrenze oder einem Filter für Suchberechtigungen, basierend auf dem Zeitpunkt, zu dem die Azure AD-Attribute zuletzt synchronisiert wurden, bevor das Postfach gelöscht wurde. 

    Darüber hinaus wird die Synchronisierung zwischen dem Postfach des Benutzers und dem #A0 beendet, wenn das Postfach nicht lizenziert oder als soft gelöscht wird. Der letzte Gestempelwert des Complianceattributs für das #A0 bleibt in Kraft.

- Das Complianceattribut wird alle sieben Tage aus dem #A0 eines Benutzers mit dem #A1 synchronisiert. Wie bereits erwähnt, erfolgt diese Synchronisierung nur, wenn dem Benutzer sowohl eine Exchange Online- als auch eine SharePoint Online-Lizenz zugewiesen ist und das Postfach des Benutzers mindestens 10 MB beträgt.

- Wenn Kompatibilitätsgrenzen und Suchberechtigungsfilter sowohl für das Postfach eines Benutzers als auch für das #A0 implementiert werden, wird empfohlen, das Postfach eines Benutzers und nicht sein #A1 nicht zu löschen. Anders ausgedrückt: Wenn Sie das Postfach eines Benutzers löschen, sollten Sie auch das #A0 des Benutzers entfernen.

- Es gibt Situationen (z. B. einen zurückkehrenden Mitarbeiter), in denen ein Benutzer möglicherweise über zwei oder mehr #A0 verfügen kann. In diesen Fällen wird nur das primäre #A0 synchronisiert, das dem Benutzer in Azure AD zugeordnet ist.

- Kompatibilitätsgrenzen und Suchberechtigungsfilter hängen von Attributen ab, die für Inhalte in Exchange, OneDrive und SharePoint gestempelt werden, und von der nachfolgenden Indizierung dieses gestempelten Inhalts. 

- Es wird nicht empfohlen, Ausschlussfilter (z. B. die Verwendung in einem Suchberechtigungsfilter) für eine `-not()` inhaltsbasierte Compliancegrenze zu verwenden. Die Verwendung eines Ausschlussfilters kann unerwartete Ergebnisse haben, wenn Inhalte mit kürzlich aktualisierten Attributen nicht indiziert wurden. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer kann Suchberechtigungsfilter erstellen und verwalten (mithilfe New-ComplianceSecurityFilter und Set-ComplianceSecurityFilter Cmdlets)?**
  
Zum Erstellen, Anzeigen und Ändern von Suchberechtigungsfiltern müssen Sie Mitglied der Rollengruppe Organisationsverwaltung im Security & Compliance Center sein.
  
**Wenn ein eDiscovery-Manager mehreren Rollengruppen zugewiesen ist, die mehrere Agenturen umfassen, wie wird dann in der einen oder anderen Agentur nach Inhalten gesucht?**
  
Der eDiscovery-Manager kann seiner Suchabfrage Parameter hinzufügen, die die Suche auf eine bestimmte Agentur beschränken. Wenn z. B. eine Organisation die **CustomAttribute10-Eigenschaft** angegeben hat, um Agenturen zu unterscheiden, kann sie ihrer Suchabfrage Folgendes an die Suche von Postfächern und #A0 in einer bestimmten Agentur anfügen:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**Was geschieht, wenn der Wert des Attributs, das als Complianceattribut in einem Suchberechtigungsfilter verwendet wird, geändert wird?**
  
Es dauert bis zu drei Tage, bis ein Suchberechtigungsfilter die Compliancegrenze erzwingt, wenn der Wert des Attributs geändert wird, das im Filter verwendet wird. Angenommen, im Contoso-Szenario wird ein Benutzer der Fourth Coffee-Agentur an die Coho Winery-Agentur übertragen. Aus diesem Grund wird  der Wert des Department-Attributs für das Benutzerobjekt von *FourthCoffee* in *CohoWinery geändert.* In dieser Situation erhalten Fourth Coffee eDiscovery und Investoren suchergebnisse für diesen Benutzer für bis zu drei Tage, nachdem das Attribut geändert wurde. Ebenso dauert es bis zu drei Tage, bis Coho Winery eDiscovery-Manager und Ermittler Suchergebnisse für den Benutzer erhalten.
  
**Kann ein eDiscovery-Manager Inhalte aus zwei separaten Compliancegrenzen sehen?**
  
Ja, dies kann beim Durchsuchen von Exchange-Postfächern durch Hinzufügen des eDiscovery-Managers zu Rollengruppen mit Sichtbarkeit für beide Behörden geschehen. Beim Durchsuchen von #A0 und #A1 kann ein eDiscovery-Manager jedoch nur dann nach Inhalten in unterschiedlichen Compliancegrenzen suchen, wenn sich die Behörden in derselben Region oder am gleichen geografischen Standort befinden. **Hinweis:** Diese Einschränkung für Websites gilt in Advanced eDiscovery nicht, da die Suche nach Inhalten in SharePoint und OneDrive nicht an den geografischen Standort gebunden ist.
  
**Funktionieren Suchberechtigungsfilter für eDiscovery-Fallspeicher, Microsoft 365-Aufbewahrungsrichtlinien oder DLP?**
  
Nein, derzeit nicht.
  
**Wenn ich eine Region an angabe, die steuern soll, wo Inhalte exportiert werden, aber ich habe keine SharePoint-Organisation in dieser Region, kann ich sharePoint trotzdem durchsuchen?**
  
Wenn die im Filter für Suchberechtigungen angegebene Region in Ihrer Organisation nicht vorhanden ist, wird die Standardregion durchsucht.
  
**Wie viele Suchberechtigungsfilter können maximal in einer Organisation erstellt werden?**
  
Die Anzahl der Suchberechtigungsfilter, die in einer Organisation erstellt werden können, ist nicht begrenzt. Die Suchleistung wirkt sich jedoch auf mehr als 100 Filter für Suchberechtigungen aus. Um die Anzahl der Suchberechtigungsfilter in Ihrer Organisation so klein wie möglich zu halten, erstellen Sie Filter, die Regeln für Exchange, SharePoint und OneDrive nach Möglichkeit in einem einzelnen Suchberechtigungsfilter kombinieren.