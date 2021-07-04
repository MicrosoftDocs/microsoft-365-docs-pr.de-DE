---
title: Stichwortabfragen und Suchbedingungen für eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über E-Mail- und Dokumenteigenschaften, die Sie mithilfe der eDiscovery-Suchtools in Microsoft 365 durchsuchen können.
ms.openlocfilehash: b274b185c7fb0d2cd6dfa4aca0e8d8429664fe61
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288815"
---
# <a name="keyword-queries-and-search-conditions-for-ediscovery"></a>Stichwortabfragen und Suchbedingungen für eDiscovery

In diesem Thema werden die E-Mail- und Dokumenteigenschaften beschrieben, nach denen Sie in E-Mail-Elementen und Microsoft Teams Chatunterhaltungen in Exchange Online suchen können, sowie Dokumente, die auf SharePoint und OneDrive for Business Websites mithilfe der eDiscovery-Suchtools im Microsoft 365 Compliance Center gespeichert sind. Dazu gehören die Inhaltssuche, Core eDiscovery und Advanced eDiscovery (eDiscovery-Suchvorgänge in Advanced eDiscovery als *Sammlungen* bezeichnet werden). Sie können auch die Cmdlets **\* "-ComplianceSearch"** in Security & Compliance Center PowerShell verwenden, um nach diesen Eigenschaften zu suchen. In diesem Thema wird außerdem Folgendes beschrieben:

- Verwenden von booleschen Suchoperatoren, Suchbedingungen und anderen Suchabfragetechniken, um Ihre Suchergebnisse zu verfeinern.
- Suchen nach vertraulichen Datentypen und benutzerdefinierten vertraulichen Datentypen in SharePoint und OneDrive for Business.
- Suchen nach Websiteinhalten, die für Benutzer außerhalb Ihrer Organisation freigegeben sind

Schritt-für-Schritt-Anleitungen zum Erstellen verschiedener eDiscovery-Suchvorgänge finden Sie unter:

- [Inhaltssuche](content-search.md)
- [Suchen nach Inhalten in Core eDiscovery](search-for-content-in-core-ediscovery.md)
- [Erstellen einer Entwurfssammlung in Advanced eDiscovery](create-draft-collection.md)

> [!NOTE]
> eDiscovery-Suchvorgänge im Microsoft 365 Compliance Center und die entsprechenden **\* -ComplianceSearch-Cmdlets** in Security & Compliance Center PowerShell verwenden die Keyword Query Language (KQL). Ausführlichere Informationen finden Sie unter [Keyword Query Language Syntax Reference.](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

## <a name="searchable-email-properties"></a>Durchsuchbare E-Mail-Eigenschaften

In der folgenden Tabelle sind die Eigenschaften von E-Mail-Nachrichten aufgeführt, die mithilfe der eDiscovery-Suchtools im Microsoft 365 Compliance Center oder mithilfe der **New-ComplianceSearch** oder des **Cmdlets "Set-ComplianceSearch"** durchsucht werden können. Die Tabelle enthält ein Beispiel für die  _property:value_-Syntax für jede Eigenschaft und eine Beschreibung der für jedes Beispiel zurückgegebenen Suchergebnisse. Sie können diese  `property:value` Paare in das Schlüsselwörterfeld für eine eDiscovery-Suche eingeben.

> [!NOTE]
> Beim Durchsuchen von E-Mail-Eigenschaften ist es nicht möglich, nach Elementen zu suchen, in denen die angegebene Eigenschaft leer oder leer ist. Wenn Sie z. B. das *"property:value"-Paar* **"betreff:""** verwenden, um nach E-Mail-Nachrichten mit einer leeren Betreffzeile zu suchen, werden keine Ergebnisse zurückgegeben. Dies gilt auch beim Durchsuchen von Website- und Kontakteigenschaften.

<br>

****

|Eigenschaft|Beschreibung der Eigenschaft|Beispiele|Von den Beispielen zurückgegebene Suchergebnisse|
|---|---|---|---|
|AttachmentNames|Die Namen der an eine E-Mail angefügten Dateien.|`attachmentnames:annualreport.ppt` <p> `attachmentnames:annual*` <br/> `attachmentnames:.pptx`|Nachrichten, an die eine Datei namens Jahresbericht.ppt angehängt ist. Im zweiten Beispiel werden mithilfe des Platzhalterzeichens ( * ) Nachrichten mit dem Wort "annual" im Dateinamen einer Anlage zurückgegeben. Im dritten Beispiel werden alle Anlagen mit der Dateinamenerweiterung pptx zurückgegeben.|
|Bcc|Das Bcc-Feld einer E-Mail-Nachricht. <sup>1</sup>|`bcc:pilarp@contoso.com` <p> `bcc:pilarp` <p> `bcc:"Pilar Pinilla"`|In allen Beispielen werden Nachrichten mit dem Namen "Pilar Pinilla" im Bcc-Feld zurückgegeben.|
|Kategorie|Die Kategorien, nach denen gesucht wird. Kategorien können von Benutzern mithilfe von Outlook oder Outlook im Web (früher als Outlook Web App bezeichnet) definiert werden. Die folgenden Werte sind möglich: <ul><li>blau<li></li>grün<li></li>orange<li></li>violett<li></li>rot<li></li>gelb</li></ul>|`category:"Red Category"`|Nachrichten, denen in den Quellpostfächern die rote Kategorie zugewiesen wurde.|
|Cc|Das Feld "Cc" einer E-Mail-Nachricht. <sup>1</sup>|`cc:pilarp@contoso.com` <p> `cc:"Pilar Pinilla"`|In beiden Beispielen werden Nachrichten mit Pilar Pinilla im Feld "Cc" angegeben.|
|Folderid|Die Ordner-ID (GUID) eines bestimmten Postfachordners. Wenn Sie diese Eigenschaft verwenden, müssen Sie das Postfach durchsuchen, in dem sich der angegebene Ordner befindet. Nur der angegebene Ordner wird durchsucht. Alle Unterordner im Ordner werden nicht durchsucht. Zum Durchsuchen von Unterordnern müssen Sie die Folderid-Eigenschaft für den Unterordner verwenden, den Sie durchsuchen möchten. <p> Weitere Informationen zum Suchen nach der Folderid-Eigenschaft und zum Verwenden eines Skripts zum Abrufen der Ordner-IDs für ein bestimmtes Postfach finden Sie unter Verwenden der [Inhaltssuche für gezielte Sammlungen.](use-content-search-for-targeted-collections.md)|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000` <p> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|Im ersten Beispiel werden alle Elemente im angegebenen Postfachordner zurückgegeben. Im zweiten Beispiel werden alle Elemente im angegebenen Postfachordner zurückgegeben, die von garthf@contoso.com gesendet oder empfangen wurden.|
|Von|Der Absender einer E-Mail-Nachricht.<sup>1</sup>|`from:pilarp@contoso.com` <p> `from:contoso.com`|Nachrichten, die vom angegebenen Benutzer oder einer bestimmten Domäne gesendet wurden.|
|HasAttachment|Gibt an, ob eine Nachricht über eine Anlage verfügt. Verwenden Sie die Werte **"true"** oder **"false".**|`from:pilar@contoso.com AND hasattachment:true`|Nachrichten, die vom angegebenen Benutzer mit Anlagen gesendet wurden.|
|Wichtigkeit|Die Wichtigkeit einer E-Mail-Nachricht, die ein Absender festlegen kann, wenn er eine Nachricht sendet. Standardmäßig werden Nachrichten mit normaler Wichtigkeit gesendet, außer wenn der Absender die Wichtigkeit auf **Hoch** oder **Niedrig** setzt.  |`importance:high` <p> `importance:medium` <p> `importance:low`|Nachrichten, deren Wichtigkeit auf "Hoch", "Mittel" bzw. "Niedrig" eingestellt ist.|
|IsRead|Gibt an, ob Nachrichten gelesen wurden. Verwenden Sie die Werte **"true"** oder **"false".**|`isread:true` <p> `isread:false`|Im ersten Beispiel werden Nachrichten zurückgegeben, bei denen die IsRead-Eigenschaft auf **"True"** festgelegt ist. Im zweiten Beispiel werden Nachrichten zurückgegeben, bei denen die IsRead-Eigenschaft auf **"False"** festgelegt ist.|
|ItemClass|Verwenden Sie diese Eigenschaft, um bestimmte Datentypen von Drittanbietern zu durchsuchen, die Ihre Organisation in Office 365 importiert hat. Verwenden Sie die folgende Syntax für diese Eigenschaft:  `itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso` <p> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|Im ersten Beispiel werden Facebook-Elemente zurückgegeben, die das Wort "contoso" in der Subject-Eigenschaft enthalten. Das zweite Beispiel gibt Twitter-Elemente zurück, die von Ann Beebe gepostet wurden und den Schlüsselwortsatz "Northwind-Händler" enthalten. <p> Eine vollständige Liste der Werte, die für Datentypen von Drittanbietern für die ItemClass-Eigenschaft verwendet werden sollen, finden Sie unter Verwenden der [Inhaltssuche, um Daten von Drittanbietern zu durchsuchen, die in Office 365 importiert wurden.](use-content-search-to-search-third-party-data-that-was-imported.md)|
|Art|Der Typ der E-Mail-Nachricht, nach der gesucht werden soll. Mögliche Werte: <p>  contacts <p>  docs <p>  email <p>  Externe Daten <p>  faxes <p>  im <p>  journals <p>  meetings <p>  microsoftteams (gibt Elemente aus Chats, Besprechungen und Anrufen in Microsoft Teams zurück) <p>  notes <p>  posts <p>  rssfeeds <p>  tasks <p>  voicemail|`kind:email` <p> `kind:email OR kind:im OR kind:voicemail` <p> `kind:externaldata`|Im ersten Beispiel werden E-Mail-Nachrichten zurückgegeben, die den Suchkriterien entsprechen. Im zweiten Beispiel werden E-Mail-Nachrichten, Chatunterhaltungen (einschließlich Skype for Business Unterhaltungen und Chats in Microsoft Teams) und Sprachnachrichten zurückgegeben, die die Suchkriterien erfüllen. Im dritten Beispiel werden Elemente zurückgegeben, die in Postfächer in Microsoft 365 aus Datenquellen von Drittanbietern importiert wurden, z. B. Twitter, Facebook und Cisco Jabber, die die Suchkriterien erfüllen. Weitere Informationen finden Sie unter Archivierung von [Drittanbieterdaten in Office 365.](https://www.microsoft.com/?ref=go)|
|Teilnehmer|Alle Personenfelder in einer E-Mail-Nachricht. Diese Felder sind From, To, Cc und Bcc.<sup>1</sup>|`participants:garthf@contoso.com` <p> `participants:contoso.com`|Nachrichten, die von oder an garthf@contoso.com gesendet wurden. Im zweiten Beispiel werden alle Nachrichten zurückgegeben, die von oder an einen Benutzer in der Domäne contoso.com gesendet wurden.|
|Empfangen|Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde.|`received:04/15/2016` <p> `received>=01/01/2016 AND received<=03/31/2016`|Nachrichten, die am 15. April 2016 empfangen wurden. Im zweiten Beispiel werden alle Nachrichten zurückgegeben, die zwischen dem 1. Januar 2016 und dem 31. März 2016 empfangen wurden.|
|Empfänger|Alle Empfängerfelder in einer E-Mail-Nachricht. Diese Felder sind "An", "Cc" und "Bcc".<sup>1</sup>|`recipients:garthf@contoso.com` <p> `recipients:contoso.com`|Nachrichten, die an garthf@contoso.com gesendet wurden. Im zweiten Beispiel werden Nachrichten zurückgegeben, die an einen Empfänger in der Domäne contoso.com gesendet wurden.|
|Gesendet|Das Datum, an dem eine E-Mail vom Absender gesendet wurde.|`sent:07/01/2016` <p> `sent>=06/01/2016 AND sent<=07/01/2016`|Nachrichten, die am angegebenen Tag oder im angegebenen Datumsbereich gesendet wurden.|
|Größe|Die Größe eines Elements in Byte.|`size>26214400` <p> `size:1..1048567`|Nachrichten mit mehr als 25 MB. Im zweiten Beispiel werden Nachrichten zwischen 1 und 1.048.567 Bytes (1 MB) zurückgegeben.|
|Betreff|Der Text in der Betreffzeile einer E-Mail. <p> **Hinweis:** Wenn Sie die Subject-Eigenschaft in einer Abfrage verwenden, gibt die Suche alle Nachrichten zurück, in denen die Betreffzeile den gesuchten Text enthält. Mit anderen Worten, die Abfrage gibt nicht nur die Nachrichten zurück, die eine genaue Übereinstimmung aufweisen. Wenn Sie beispielsweise  `subject:"Quarterly Financials"` suchen, enthalten Ihre Ergebnisse Nachrichten mit dem Betreff "Vierteljährliche Finanzen 2018".|`subject:"Quarterly Financials"` <p> `subject:northwind`|Nachrichten, die den Ausdruck "Vierteljährliche Finanzen" an einer beliebigen Stelle im Text der Betreffzeile enthalten. Im zweiten Beispiel werden alle Nachrichten mit dem Wort "northwind" in der Betreffzeile zurückgegeben.|
|An|Das Feld „An" einer E-Mail-Nachricht.<sup>1</sup>|`to:annb@contoso.com` <p> `to:annb ` <br/> `to:"Ann Beebe"`|In allen Beispielen wegen Nachrichten zurückgegeben, in deren Zeile "An" der Name "Ann Beebe" angegeben ist.|
|

> [!NOTE]
> <sup>1</sup> Für den Wert einer Empfängereigenschaft können Sie die E-Mail-Adresse (auch *benutzerprinzipalname* oder UPN genannt), den Anzeigenamen oder den Alias verwenden, um einen Benutzer anzugeben. Sie können z. B. annb@contoso.com, Annb oder „Ann Beebe“ verwenden, um den Benutzer Ann Beebe anzugeben.

### <a name="recipient-expansion"></a>Empfängererweiterung

Beim Durchsuchen einer der Empfängereigenschaften (From, To, Cc, Bcc, Participants und Recipients) versucht Microsoft 365, die Identität der einzelnen Benutzer zu erweitern, indem sie sie in Azure Active Directory (Azure AD) nachschlagen.  Wenn der Benutzer in Azure AD gefunden wird, wird die Abfrage erweitert, um die E-Mail-Adresse (oder UPN), den Alias, den Anzeigenamen und legacyExchangeDN des Benutzers einzuschließen. Eine Abfrage wie z. B. wird z. `participants:ronnie@contoso.com` B. bis `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` erweitert.

Um eine Empfängererweiterung zu verhindern, fügen Sie am Ende der E-Mail-Adresse ein Platzhalterzeichen (Sternchen) hinzu, und verwenden Sie einen reduzierten Domänennamen. Achten Sie beispielsweise `participants:"ronnie@contoso*"` darauf, die E-Mail-Adresse in doppelte Anführungszeichen einzuschließen.

Beachten Sie jedoch, dass das Verhindern der Empfängererweiterung in der Suchabfrage dazu führen kann, dass relevante Elemente nicht in den Suchergebnissen zurückgegeben werden. E-Mail-Nachrichten in Exchange können mit unterschiedlichen Textformaten in den Empfängerfeldern gespeichert werden. Die Empfängererweiterung soll dazu beitragen, diese Tatsache zu mindern, indem Nachrichten zurückgegeben werden, die unterschiedliche Textformate enthalten können. Das Verhindern der Empfängererweiterung kann dazu führen, dass die Suchabfrage nicht alle Elemente zurückgibt, die für Ihre Untersuchung relevant sein können.

> [!NOTE]
> Wenn Sie die von einer Suchabfrage zurückgegebenen Elemente aufgrund der Empfängererweiterung überprüfen oder reduzieren müssen, sollten Sie Advanced eDiscovery verwenden. Sie können nach Nachrichten suchen (unter Nutzung der Empfängererweiterung), sie einem Prüfdateisatz hinzufügen und dann Prüfdateisatzabfragen oder Filter verwenden, um die Ergebnisse zu überprüfen oder einzugrenzen. Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall](collecting-data-for-ediscovery.md) und Abfragen der Daten in einem [Prüfdateisatz.](review-set-search.md)

## <a name="searchable-site-properties"></a>Durchsuchbare Websiteeigenschaften

In der folgenden Tabelle sind einige der SharePoint und OneDrive for Business Eigenschaften aufgeführt, die mithilfe der eDiscovery-Suchtools im Microsoft 365 Compliance Center oder mithilfe der **New-ComplianceSearch** oder des **Set-ComplianceSearch-Cmdlets** durchsucht werden können. Die Tabelle enthält ein Beispiel für die  _property:value_-Syntax für jede Eigenschaft und eine Beschreibung der für jedes Beispiel zurückgegebenen Suchergebnisse.

Eine vollständige Liste der SharePoint Eigenschaften, die durchsucht werden können, finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint.](/SharePoint/technical-reference/crawled-and-managed-properties-overview) Eigenschaften, die in der Spalte **"Abfragbar"** mit **"Ja"** markiert sind, können durchsucht werden.

<br>

****

|Eigenschaft|Beschreibung der Eigenschaft|Beispiel|Von den Beispielen zurückgegebene Suchergebnisse|
|---|---|---|---|
|Ursprung|Das Feld "Autor" aus Office Dokumenten, das beim Kopieren eines Dokuments beibehalten wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die E-Mails an eine andere Person sendet, die es dann in SharePoint hochlädt, behält das Dokument den ursprünglichen Autor bei. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`author:"Garth Fort"`|Alle Dokumente, die von Garth Fort erstellt wurden.|
|ContentType|Der SharePoint Inhaltstyp eines Elements, z. B. Element, Dokument oder Video.|`contenttype:document`|Alle Dokumente würden zurückgegeben.|
|Erstellt|Das Erstellungsdatum eines Elements.|`created>=06/01/2016`|Alle Elemente, die am oder nach dem 1. Juni 2016 erstellt wurden.|
|CreatedBy|Die Person, die ein Element erstellt oder hochgeladen hat. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`createdby:"Garth Fort"`|Alle von Garth Fort erstellten oder hochgeladenen Elemente.|
|DetectedLanguage|Die Sprache eines Elements.|`detectedlanguage:english`|Alle Elemente in Englisch.|
|DocumentLink|Der Pfad (URL) eines bestimmten Ordners auf einer SharePoint oder OneDrive for Business Website. Wenn Sie diese Eigenschaft verwenden, müssen Sie die Website durchsuchen, in der sich der angegebene Ordner befindet. <p> Um Elemente zurückzugeben, die sich in Unterordnern des Ordners befinden, den Sie für die documentlink-Eigenschaft angeben, müssen Sie \* der URL des angegebenen Ordners /hinzufügen, z. B. `documentlink: "https://contoso.sharepoint.com/Shared Documents/*"` <p> <br/>Weitere Informationen zum Suchen nach der documentlink-Eigenschaft und zum Verwenden eines Skripts zum Abrufen der Documentlink-URLs für Ordner auf einer bestimmten Website finden Sie unter Verwenden der [Inhaltssuche für gezielte Sammlungen.](use-content-search-for-targeted-collections.md)|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"` <p> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|Im ersten Beispiel werden alle Elemente im angegebenen OneDrive for Business Ordner zurückgegeben. Im zweiten Beispiel werden Dokumente im angegebenen Websiteordner (und allen Unterordnern) zurückgegeben, die das Wort "vertraulich" im Dateinamen enthalten.|
|Fileextension|Die Erweiterung einer Datei; z. B. docx, one, pptx oder xlsx.|`fileextension:xlsx`|Alle Excel Dateien (Excel 2007 und höher)|
|FileName|Der Name einer Datei.|`filename:"marketing plan"` <p> `filename:estimate`|Im ersten Beispiel werden Dateien mit dem exakten Ausdruck "Marketingplan" im Titel zurückgegeben. Im zweiten Beispiel werden Dateien mit dem Wort "estimate" im Dateinamen zurückgegeben.|
|LastModifiedTime|Das Datum, an dem ein Element zuletzt geändert wurde.|`lastmodifiedtime>=05/01/2016` <p> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|Im ersten Beispiel werden Elemente zurückgegeben, die am oder nach dem 1. Mai 2016 geändert wurden. Im zweiten Beispiel werden Elemente zurückgegeben, die zwischen dem 1. Mai 2016 und dem 1. Juni 2016 geändert wurden.|
|ModifiedBy|Die Person, die ein Element zuletzt geändert hat. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`modifiedby:"Garth Fort"`|Alle Elemente, die zuletzt von Garth Fort geändert wurden.|
|Pfad|Der Pfad (URL) einer bestimmten Website in einer SharePoint oder OneDrive for Business Website. <p> Um nur Elemente von der angegebenen Website zurückzugeben, müssen Sie das nachstehende `/` Element am Ende der URL hinzufügen, z. B. `path: "https://contoso.sharepoint.com/sites/international/"` <p> Um Elemente zurückzugeben, die sich in Ordnern auf der Website befinden, die Sie in der Pfadeigenschaft angeben, müssen Sie `/*` sie am Ende der URL hinzufügen, z. B.  `path: "https://contoso.sharepoint.com/Shared Documents/*"` <p> **Hinweis:** Wenn Sie die `Path` Eigenschaft zum Durchsuchen OneDrive Speicherorte verwenden, werden keine Mediendateien wie .png-, TIFF- oder WAV-Dateien in den Suchergebnissen zurückgegeben. Verwenden Sie eine andere Websiteeigenschaft in Ihrer Suchabfrage, um nach Mediendateien in OneDrive Ordnern zu suchen. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"` <p> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|Im ersten Beispiel werden alle Elemente in der angegebenen OneDrive for Business Website zurückgegeben. Im zweiten Beispiel werden Dokumente auf der angegebenen Website (und Ordner auf der Website) zurückgegeben, die das Wort "vertraulich" im Dateinamen enthalten.|
|SharedWithUsersOWSUser|Dokumente, die für den angegebenen Benutzer freigegeben und auf der Seite **"Für mich freigegeben"** auf der OneDrive for Business Website des Benutzers angezeigt wurden. Hierbei handelt es sich um Dokumente, die von anderen Personen in Ihrer Organisation explizit für den angegebenen Benutzer freigegeben wurden. Wenn Sie Dokumente exportieren, die einer Suchabfrage entsprechen, die die SharedWithUsersOWSUser-Eigenschaft verwendet, werden die Dokumente aus dem ursprünglichen Inhaltsspeicherort der Person exportiert, die das Dokument für den angegebenen Benutzer freigegeben hat. Weitere Informationen finden Sie unter [Suchen nach Websiteinhalten, die in Ihrer Organisation freigegeben sind.](#searching-for-site-content-shared-within-your-organization)|`sharedwithusersowsuser:garthf` <p> `sharedwithusersowsuser:"garthf@contoso.com"`|Beide Beispiele geben alle internen Dokumente zurück, die explizit für Garth Fort freigegeben wurden und auf der Seite **"Für mich freigegeben"** im OneDrive for Business-Konto von Garth Fort angezeigt werden.|
|Website|Die URL einer Website oder Gruppe von Websites in Ihrer Organisation.|`site:"https://contoso-my.sharepoint.com"` <p> `site:"https://contoso.sharepoint.com/sites/teams"`|Im ersten Beispiel werden Elemente aus den OneDrive for Business Websites für alle Benutzer in der Organisation zurückgegeben. Im zweiten Beispiel werden Elemente von allen Teamwebsites zurückgegeben.|
|Größe|Die Größe eines Elements in Byte.|`size>=1` <p> `size:1..10000`|Im ersten Beispiel werden Elemente zurückgegeben, die größer als 1 Byte sind. Im zweiten Beispiel werden Elemente mit einer Größe von 1 bis 10.000 Byte zurückgegeben.|
|Titel|Der Titel des Dokuments. Die Title-Eigenschaft ist Metadaten, die in Microsoft Office Dokumenten angegeben sind. Sie unterscheidet sich vom Dateinamen des Dokuments.|`title:"communication plan"`|Jedes Dokument, das den Ausdruck "Kommunikationsplan" in der Title-Metadateneigenschaft eines Office Dokuments enthält.|
|

## <a name="searchable-contact-properties"></a>Durchsuchbare Kontakteigenschaften

In der folgenden Tabelle sind die Kontakteigenschaften aufgeführt, die indiziert sind und nach denen Sie mithilfe von eDiscovery-Suchtools suchen können. Dies sind die Eigenschaften, die Benutzer für die Kontakte (auch als persönliche Kontakte bezeichnet) konfigurieren können, die sich im persönlichen Adressbuch des Postfachs eines Benutzers befinden. Um nach Kontakten zu suchen, können Sie die zu durchsuchenden Postfächer auswählen und dann eine oder mehrere Kontakteigenschaften in der Stichwortabfrage verwenden.

> [!TIP]
> Um nach Werten zu suchen, die Leerzeichen oder Sonderzeichen enthalten, verwenden Sie doppelte Anführungszeichen (" ") für den Ausdruck. Beispiel: `businessaddress:"123 Main Street"` .

<br>

****

|Eigenschaft|Beschreibung der Eigenschaft|
|---|---|
|BusinessAddress|Die Adresse in der **Business Address-Eigenschaft.** Die Eigenschaft wird auch als **Arbeitsadresse** auf der Kontakteigenschaftenseite bezeichnet.|
|BusinessPhone|Die Telefonnummer in einer der **Eigenschaften "Business Telefon** Number".|
|CompanyName|Der Name in der **Eigenschaft "Company".**|
|Abteilung|Der Name in der **Department-Eigenschaft.**|
|DisplayName|Der Anzeigename des Kontakts. Dies ist der Name in der **Eigenschaft "Vollständiger Name"** des Kontakts.|
|EmailAddress|Die Adresse für eine beliebige E-Mail-Adresseigenschaft für den Kontakt. Benutzer können mehrere E-Mail-Adressen für einen Kontakt hinzufügen. Wenn Sie diese Eigenschaft verwenden, werden Kontakte zurückgegeben, die einer der E-Mail-Adressen des Kontakts entsprechen.|
|FileAs|Die **Datei als** Eigenschaft. Diese Eigenschaft wird verwendet, um anzugeben, wie der Kontakt in der Kontaktliste des Benutzers aufgeführt wird. Beispielsweise kann ein Kontakt als  *FirstName, LastName*  oder  *LastName,FirstName* aufgeführt werden.|
|GivenName|Der Name in der **First Name-Eigenschaft.**|
|HomeAddress|Die Adresse in einer der **Home-Adresseigenschaften.**|
|HomePhone|Die Telefonnummer in einer  der Eigenschaften der Privattelefonnummer.|
|IMAddress|Die Chatadresseneigenschaft, bei der es sich in der Regel um eine E-Mail-Adresse handelt, die für Chatnachrichten verwendet wird.|
|MiddleName|Der Name in der **Eigenschaft "Zweiter** Vorname".|
|MobilePhone|Die Telefonnummer in der Eigenschaft **"Mobiltelefonnummer".**|
|Spitzname|Der Name in der **Nickname-Eigenschaft.**|
|OfficeLocation|Der Wert in **Office** oder **Office Location-Eigenschaft.**|
|OtherAddress|Der Wert für die **Eigenschaft "Other** address".|
|Nachname|Der Name  in der Nachnameneigenschaft.|
|Titel|Der Titel in der Eigenschaft **"Position".**|
|

## <a name="searchable-sensitive-data-types"></a>Durchsuchbare vertrauliche Datentypen

Sie können eDiscovery-Suchtools im Microsoft 365 Compliance Center verwenden, um nach vertraulichen Daten wie Kreditkartennummern oder Sozialversicherungsnummern zu suchen, die in Dokumenten auf SharePoint und OneDrive for Business Websites gespeichert sind. Dazu können Sie die `SensitiveType` Eigenschaft und den Namen (oder die ID) eines vertraulichen Informationstyps in einer Stichwortabfrage verwenden. Die Abfrage gibt beispielsweise `SensitiveType:"Credit Card Number"` Dokumente zurück, die eine Kreditkartennummer enthalten. Die Abfrage  `SensitiveType:"U.S. Social Security Number (SSN)"` gibt Dokumente zurück, die eine US-Sozialversicherungsnummer enthalten.

Eine Liste der Typen vertraulicher Informationen, nach denen Sie suchen können, finden Sie unter **"Datenklassifizierungen** \> **vertraulicher Informationstypen"** im Microsoft 365 Compliance Center. Sie können auch das Cmdlet **"Get-DlpSensitiveInformationType"** in Security & Compliance Center PowerShell verwenden, um eine Liste vertraulicher Informationstypen anzuzeigen.

Weitere Informationen zum Erstellen von Abfragen mithilfe der `SensitiveType` Eigenschaft finden Sie unter [Formularieren einer Abfrage, um vertrauliche Daten zu finden, die auf Websites gespeichert sind.](form-a-query-to-find-sensitive-data-stored-on-sites.md)

### <a name="limitations-for-searching-sensitive-data-types"></a>Einschränkungen für die Suche nach vertraulichen Datentypen

- Um nach benutzerdefinierten Typen vertraulicher Informationen zu suchen, müssen Sie die ID des Typs vertraulicher Informationen in der `SensitiveType` Eigenschaft angeben. Die Verwendung des Namens eines benutzerdefinierten vertraulichen Informationstyps (wie im Beispiel für integrierte Typen vertraulicher Informationen im vorherigen Abschnitt gezeigt) gibt keine Ergebnisse zurück. Verwenden Sie die **Spalte Publisher** auf der Seite **"Typen vertraulicher Informationen"** im Compliance Center (oder die **eigenschaft Publisher** in PowerShell), um zwischen integrierten und benutzerdefinierten Typen vertraulicher Informationen zu unterscheiden. Integrierte typen vertraulicher Daten weisen einen Wert `Microsoft Corporation` für die **Publisher-Eigenschaft auf.**

  Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um den Namen und die ID für die benutzerdefinierten typen vertraulicher Daten in Ihrer Organisation anzuzeigen:

  ```powershell
  Get-DlpSensitiveInformationType | Where-Object {$_.Publisher -ne "Microsoft Corporation"} | FT Name,Id
  ```

  Anschließend können Sie die ID in der `SensitiveType` Sucheigenschaft verwenden, um Dokumente zurückzugeben, die den benutzerdefinierten vertraulichen Datentyp enthalten, z. B. `SensitiveType:7e13277e-6b04-3b68-94ed-1aeb9d47de37`

- Sie können keine Typen vertraulicher Informationen und die `SensitiveType` Sucheigenschaft verwenden, um in Exchange Online Postfächern nach ruhenden vertraulichen Daten zu suchen. Dazu gehören 1:1-Chatnachrichten, 1:N-Gruppenchatnachrichten und Teamkanalunterhaltungen in Microsoft Teams, da alle diese Inhalte in Postfächern gespeichert sind. Sie können jedoch DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um vertrauliche E-Mail-Daten während der Übertragung zu schützen. Weitere Informationen finden Sie unter ["Informationen zur Verhinderung von Datenverlust"](dlp-learn-about-dlp.md) und [zum Suchen nach personenbezogenen Daten.](/compliance/regulatory/gdpr)

## <a name="search-operators"></a>Suchoperatoren

Boolesche Suchoperatoren wie **AND**, **OR** und **NOT** helfen Ihnen bei der Definition präziserer Suchvorgänge, indem sie bestimmte Wörter in die Suchabfrage einschließen oder ausschließen. Andere Techniken, z. B. die Verwendung von Eigenschaftsoperatoren (z. `>=` B. oder `..` ), Anführungszeichen, Klammern und Platzhaltern, helfen Ihnen bei der Verfeinerung einer Suchabfrage. In der folgenden Tabelle sind die Operatoren aufgeführt, mit denen Sie Suchergebnisse eingrenzen oder erweitern können.

<br>

****

|Operator|Verwendung|Beschreibung|
|---|---|---|
|AND|Wort1 AND Wort2|Gibt Elemente zurück, die alle angegebenen Schlüsselwörter oder  `property:value` Ausdrücke enthalten. Würde beispielsweise  `from:"Ann Beebe" AND subject:northwind` alle von Ann Beebe gesendeten Nachrichten zurückgeben, die das Wort Nordwind in der Betreffzeile enthielten. <sup>2</sup>|
|+|Schlüsselwort1 + Schlüsselwort2 + Schlüsselwort3|Gibt die Elemente zurück, die  *entweder*  `keyword2` oder  `keyword3` *enthalten und*  , die ebenfalls  `keyword1` enthalten. Damit entspricht dieses Beispiel der Abfrage  `(keyword2 OR keyword3) AND keyword1`.  <p> Die Abfrage `keyword1 + keyword2` (mit einem Leerzeichen hinter dem Symbol) ist nicht identisch mit **+** der Verwendung des **AND-Operators.** Diese Abfrage wäre gleichbedeutend mit  `"keyword1 + keyword2"` und gibt Elemente mit dem exakten Ausdruck  `"keyword1 + keyword2"` zurück.|
|OR|Wort1 OR Wort2|Gibt Elemente zurück, die mindestens eines der angegebenen Schlüsselwörter oder  `property:value` Ausdrücke enthalten. <sup>2</sup>|
|NOT|Wort1 NOT Wort2 <p> NOT Von:"Ann Beebe" <p> NOT kind:im|Schließt elemente aus, die durch ein Schlüsselwort oder einen Ausdruck angegeben  `property:value` werden. Im zweiten Beispiel werden von Ann Beebe gesendete Nachrichten ausgeschlossen. Im dritten Beispiel werden alle Chatunterhaltungen ausgeschlossen, z. B. Skype for Business Unterhaltungen, die im Postfachordner "Aufgezeichnete Unterhaltungen" gespeichert werden. <sup>2</sup>|
|-|Wort1 - Wort2|Identisch mit dem Operator **NOT**. Diese Abfrage gibt also Elemente zurück, die Elemente enthalten  `keyword1` und ausschließen würden, die  `keyword2` enthalten.|
|NEAR|Wort1 NEAR(n) Wort2|Gibt Elemente mit Wörtern zurück, die sich nah sind, wobei "n" der Anzahl der Wörter entspricht, die den Abstand zwischen den gesuchten Wörtern darstellen. Gibt beispielsweise `best NEAR(5) worst` jedes Element zurück, bei dem das Wort "am schlechtesten" innerhalb von fünf Wörtern von "am besten" liegt. Wenn keine Anzahl angegeben wird, wird der Standardabstand von 8 Wörtern verwendet. <sup>2</sup>|
|:|Eigenschaftswert|Doppelpunkt (:) gibt in der  `property:value` Syntax an, dass der Wert der eigenschaft, nach der gesucht wird, den angegebenen Wert enthält. Gibt beispielsweise  `recipients:garthf@contoso.com` alle Nachrichten zurück, die an garthf@contoso.com gesendet wurden.|
|=|property=value|Identisch mit dem **Operator :**|
|\<|Eigenschaft\<Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, kleiner ist als der angegebene Wert.<sup>1</sup>|
|\>|Eigenschaft\>Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer ist als der angegebene Wert.<sup>1</sup>|
|\<=|Eigenschaft\<=Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, kleiner gleich dem angegebenen Wert ist.<sup>1</sup>|
|\>=|Eigenschaft\>=Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer gleich dem angegebenen Wert ist.<sup>1</sup>|
|..|property:value1.. Wert2|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer gleich Wert1 und kleiner gleich Wert2 ist.<sup>1</sup>|
|"  "|"fair Value" <p> Betreff:"Vierteljährliche Finanzdaten"|Verwenden Sie doppelte Anführungszeichen (" ") zum Suchen nach einem exakten Ausdruck oder Begriff in Stichwort- und  `property:value` Suchabfragen.|
|\*|cat\* <p> Betreff:set\*|Präfixsuchen (auch *Präfixvergleich* genannt), bei denen ein Platzhalterzeichen ( * ) in Schlüsselwörtern oder Abfragen am Ende eines Worts platziert `property:value` wird. Bei Präfixsuchen gibt die Suche Ergebnisse mit Begriffen zurück, die das Wort gefolgt von Null oder mehr Zeichen enthalten. Gibt beispielsweise Dokumente zurück, `title:set*` die das Wort "set", "setup" und "setting" (und andere Wörter, die mit "set" beginnen) im Dokumenttitel enthalten. <p> **Hinweis:** Sie können nur Präfixsuchen verwenden. z. B. **Cat _ oder \* *_* set \* *_. Suffixsuchen (_* \* Cat**), Infixsuchen (**c \* t**) und Teilzeichenfolgensuchen (**\* Katze \***) werden nicht unterstützt. <p> Fügen Sie auch einen Punkt ( \. ) zu einer Präfixsuche werden die zurückgegebenen Ergebnisse geändert. Der Grund dafür ist, dass ein Punkt als Stoppwort behandelt wird. For example, searching for **cat _ and searching for \* *_* cat. \*** will return different results. Es wird empfohlen, keinen Punkt in einer Präfixsuche zu verwenden.|
|(  )| (fair OR frei) AND (Von:contoso.com) <p> (IPO OR Initiale) AND (Aktien OR Anteile) <p> (Vierteljährliche Finanzdaten)|Mit Klammern werden Boolesche Ausdrücke,  `property:value`-Elemente und Schlüsselwörter gruppiert.  `(quarterly financials)` gibt z. B. Elemente zurück, die die Wörter "Vierteljährliche" und "Finanzdaten" enthalten.  |
|

> [!NOTE]
> <sup>1</sup> Verwenden Sie diesen Operator für Eigenschaften mit Datums- oder Numerischen Werten.<br/> <sup>2</sup> boolesche Suchoperatoren müssen groß geschrieben sein; Beispiel: **AND**. Wenn Sie einen Operator in Kleinbuchstaben verwenden, z. B. **"and",** wird er in der Suchabfrage als Schlüsselwort behandelt.

## <a name="search-conditions"></a>Suchbedingungen

Sie können einer Suchabfrage Bedingungen hinzufügen, um eine Suche einzugrenzen und einen genaueren Satz von Ergebnissen zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird.

[Bedingungen für allgemeine Eigenschaften ](#conditions-for-common-properties)

[Bedingungen für E-Mail-Eigenschaften](#conditions-for-mail-properties)

[Bedingungen für Dokumenteigenschaften](#conditions-for-document-properties)

[Mit Bedingungen verwendete Operatoren](#operators-used-with-conditions)

[Richtlinien für die Verwendung von Bedingungen](#guidelines-for-using-conditions)

[Beispiele](#examples-of-using-conditions-in-search-queries)

### <a name="conditions-for-common-properties"></a>Bedingungen für allgemeine Eigenschaften 

Erstellen Sie eine Bedingung mit allgemeinen Eigenschaften beim Durchsuchen von Postfächern und Websites in derselben Suche. In der folgenden Tabelle sind die verfügbaren Eigenschaften aufgeführt, die beim Hinzufügen einer Bedingung verwendet werden sollen.

<br>

****

|Bedingung|Beschreibung|
|---|---|
|Datum|Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Bei Dokumenten das Datum, an dem ein Dokument zuletzt geändert wurde.|
|Absender/Autor|Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten die Person, die im Feld "Autor" aus Office Dokumenten stammt. Sie können mehrere Namen durch Kommas getrennt eingeben. Zwei oder mehr Werte werden vom **OR-Operator** logisch verbunden.|
|Größe (in Bytes)|Für E-Mails und Dokumente die Größe des Elements (in Bytes).|
|Betreff/Titel|Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Wie zuvor erläutert, handelt es sich bei der Title-Eigenschaft um Metadaten, die in Microsoft Office Dokumenten angegeben sind. Sie können den Namen mehrerer Subjekte/Titel durch Kommas getrennt eingeben. Zwei oder mehr Werte werden vom **OR-Operator** logisch verbunden.|
|Aufbewahrungsbezeichnung|Sowohl für E-Mails als auch für Dokumente: Aufbewahrungsbezeichnungen, die Nachrichten und Dokumenten automatisch durch Richtlinien für automatische Bezeichnungen zugewiesen wurden, oder Aufbewahrungsbezeichnungen, die manuell von Benutzern zugewiesen wurden. Aufbewahrungsbezeichnungen werden verwendet, um E-Mails und Dokumente für die Informationsgovernance zu klassifizieren und Aufbewahrungsregeln basierend auf den durch die Bezeichnung definierten Einstellungen zu erzwingen. Sie können einen Teil des Aufbewahrungsbezeichnungsnamens eingeben und einen Platzhalter verwenden oder den vollständigen Bezeichnungsnamen eingeben. Weitere Informationen zu Aufbewahrungsbezeichnungen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)|
|

### <a name="conditions-for-mail-properties"></a>Bedingungen für E-Mail-Eigenschaften

Erstellen Sie eine Bedingung mithilfe von E-Mail-Eigenschaften beim Durchsuchen von Postfächern oder öffentlichen Ordnern. In der folgenden Tabelle sind die E-Mail-Eigenschaften aufgeführt, die Sie für eine Bedingung verwenden können. Diese Eigenschaften sind eine Teilmenge der E-Mail-Eigenschaften, die zuvor beschrieben wurden. Diese Beschreibungen werden aus Gründen der Einfachheit wiederholt.

<br>

****

|Bedingung|Beschreibung|
|---|---|
|Nachrichtenart|Der Nachrichtentyp, nach dem gesucht wird. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Art“. Mögliche Werte: <ul><li>contacts</li><li>docs</li><li>email</li><li>Externe Daten</li><li>Fax</li><li>im</li><li>journals</li><li>meetings</li><li>microsoftteams</li><li>notes</li><li>posts</li><li>rssfeeds</li><li>tasks</li><li>voicemail</li></ul>|
|Teilnehmer|Alle Personenfelder in einer E-Mail-Nachricht. Diese Felder sind From, To, Cc und Bcc.|
|Typ|Die Nachrichtenklasseneigenschaft für ein E-Mail-Element. Dies ist die gleiche Eigenschaft wie die ItemClass-E-Mail-Eigenschaft. Es handelt sich auch um eine Mehrwertbedingung. Um also mehrere Nachrichtenklassen auszuwählen, halten Sie die **STRG-TASTE** gedrückt, und klicken Sie dann auf zwei oder mehr Nachrichtenklassen in der Dropdownliste, die Sie der Bedingung hinzufügen möchten. Jede Nachrichtenklasse, die Sie in der Liste auswählen, wird vom **OR-Operator** in der entsprechenden Suchabfrage logisch verbunden. <p> Eine Liste der Nachrichtenklassen (und deren entsprechende Nachrichtenklassen-ID), die von Exchange verwendet werden und die Sie in der **Nachrichtenklassenliste** auswählen können, finden Sie unter ["Elementtypen und Nachrichtenklassen".](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes)|
|Auszahlung|Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Empfangen“.|
|Empfänger|Alle Empfängerfelder in einer E-Mail-Nachricht. Diese Felder sind "An", "Cc" und "Bcc".|
|Absender|Der Absender einer E-Mail-Nachricht.|
|Gesendet|Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Gesendet“.|
|Betreff|Der Text in der Betreffzeile einer E-Mail.|
|An|Der Empfänger einer E-Mail-Nachricht im Feld "An".|
|

### <a name="conditions-for-document-properties"></a>Bedingungen für Dokumenteigenschaften

Erstellen Sie eine Bedingung mithilfe von Dokumenteigenschaften beim Suchen nach Dokumenten auf SharePoint und OneDrive for Business Websites. In der folgenden Tabelle sind die Dokumenteigenschaften aufgeführt, die Sie für eine Bedingung verwenden können. Diese Eigenschaften sind eine Teilmenge der zuvor beschriebenen Websiteeigenschaften. Diese Beschreibungen werden aus Gründen der Einfachheit wiederholt.

<br>

****

|Bedingung|Beschreibung|
|---|---|
|Ursprung|Das Feld "Autor" aus Office Dokumenten, das beim Kopieren eines Dokuments beibehalten wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die E-Mails an eine andere Person sendet, die es dann in SharePoint hochlädt, behält das Dokument den ursprünglichen Autor bei.|
|Titel|Der Titel des Dokuments. Die Title-Eigenschaft ist Metadaten, die in Office Dokumenten angegeben sind. Sie unterscheidet sich vom Dateinamen des Dokuments.|
|Erstellt|Das Erstellungsdatum eines Dokuments.|
|Zuletzt geändert|Das Datum, an dem ein Dokument zuletzt geändert wurde.|
|Dateityp|Die Erweiterung einer Datei; z. B. docx, one, pptx oder xlsx. Dies ist die gleiche Eigenschaft wie die FileExtension-Websiteeigenschaft. <p> **Hinweis:** Wenn Sie eine Dateitypbedingung mit dem Operator **"Equals"** oder **"Equals"** in eine Suchabfrage einschließen, können Sie keine Präfixsuche (einschließlich des Platzhalterzeichens ( \* ) am Ende des Dateityps verwenden, um alle Versionen eines Dateityps zurückzugeben. In diesem Fall wird der Platzhalter ignoriert. Wenn Sie z. B. die Bedingung `Equals any of doc*` einschließen, werden nur Dateien mit einer Erweiterung von `.doc` zurückgegeben. Dateien mit einer Erweiterung von `.docx` werden nicht zurückgegeben. Um alle Versionen eines Dateityps zurückzugeben, verwenden Sie das *Paar "property:value"* in einer Stichwortabfrage. Beispiel: `filetype:doc*` .|
|

### <a name="operators-used-with-conditions"></a>Mit Bedingungen verwendete Operatoren

Beim Hinzufügen einer Bedingung können Sie einen Operator auswählen, der für den Typ der Eigenschaft für die Bedingung relevant ist. Die folgende Tabelle enthält die mit Bedingungen verwendeten Operatoren und die dazugehörigen Entsprechungen, die in der Suchabfrage verwendet werden.

<br>

****

|Operator|Entsprechung in der Abfrage|Beschreibung|
|---|---|---|
|Nach|`property>date`|Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die nach dem angegebenen Datum gesendet, empfangen oder geändert wurden. |
|Vor|`property<date`|Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die vor dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
|Zwischen|`date..date`|Wird mit Datums- und Größenbedingungen verwendet. Bei Verwendung mit einer Datumsbedingung werden Elemente zurückgegeben, die innerhalb des angegebenen Datumsbereichs gesendet, empfangen oder geändert wurden. Bei Verwendung mit einer Größenbedingung werden Elemente zurückgegeben, deren Größe innerhalb des angegebenen Bereichs liegt.|
|Contains any of|`(property:value) OR (property:value)`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die mindestens einen Teil der angegebenen Zeichenfolgenwerte enthalten.|
|Doesn't contain any of|`-property:value` <p> `NOT property:value`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die keinen Teil des angegebenen Zeichenfolgenwerts enthalten.|
|Doesn't equal any of|`-property=value` <p> `NOT property=value`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die die angegebene Zeichenfolge nicht enthalten.|
|Gleich|`size=value`|Gibt Elemente zurück, die der angegebenen Größe entsprechen. <sup>1</sup>|
|Equals any of|`(property=value) OR (property=value)`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die genau den angegebenen Zeichenfolgenwerten entsprechen.|
|Größer|`size>value`|Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer als der angegebene Wert ist. <sup>1</sup>|
|Greater or equal|`size>=value`|Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer oder gleich dem angegebenen Wert ist. <sup>1</sup>|
|Weniger|`size<value`|Gibt Elemente zurück, die größer oder gleich dem spezifischen Wert sind. <sup>1</sup>|
|Less or equal|`size<=value`|Gibt Elemente zurück, die größer oder gleich dem spezifischen Wert sind. <sup>1</sup>|
|Not equal|`size<>value`|Gibt Elemente zurück, die nicht der angegebenen Größe entsprechen. <sup>1</sup>|
|

> [!NOTE]
> <sup>1</sup> Dieser Operator ist nur für Bedingungen verfügbar, die die Size-Eigenschaft verwenden.

### <a name="guidelines-for-using-conditions"></a>Richtlinien für die Verwendung von Bedingungen

Beachten Sie Folgendes bei der Verwendung von Suchbedingungen:

- Eine Bedingung ist logisch mit der Schlüsselwortabfrage (im Feld „Schlüsselwort“ angegeben) durch den **AND**-Operator verknüpft. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können Sie Ihre Ergebnisse mit Bedingungen eingrenzen.

- Wenn Sie zwei oder mehr eindeutige Bedingungen (Bedingungen, die unterschiedliche Eigenschaften angeben) zu einer Suchabfrage hinzufügen, werden diese Suchkriterien mit dem **AND**-Operator logisch verknüpft. Das bedeutet, dass nur Elemente zurückgegeben werden, die neben der Schlüsselwortabfrage allen Bedingungen entsprechen.

- Wenn Sie mehr als eine Bedingung für die gleiche Eigenschaft hinzufügen, werden diese Bedingungen mit dem **OR**-Operator logisch verknüpft. Das bedeutet, dass Elemente zurückgegeben werden, die der Schlüsselwortabfrage entsprechen und eine der Bedingungen erfüllen. Bedingungen, die sich auf die gleichen Eigenschaften beziehen, werden mit dem **OR**-Operator und die eindeutigen Bedingungen werden mit dem **AND**-Operator miteinander verknüpft.

- Wenn Sie mehrere Werte (durch Kommas oder Semikolons getrennt) zu einer Bedingung hinzufügen, werden diese Werte mit dem **OR**-Operator verknüpft. Das bedeutet, es werden Elemente zurückgegeben, die einen der angegebenen Werte für die Eigenschaft in der Bedingung enthalten.

- Die Suchabfrage, die mithilfe des Stichwörterfelds und der Bedingungen erstellt wird, wird auf der **Suchseite** im Detailbereich für die ausgewählte Suche angezeigt. In einer Abfrage gibt alles rechts neben der Notation  `(c:c)` Bedingungen an, die der Abfrage hinzugefügt werden.

- Mit Bedingungen werden der Suchabfrage nur Eigenschaften hinzugefügt, keine Operatoren. Aus diesem Grund zeigt die im Detailbereich angezeigte Abfrage keine Operatoren rechts neben der  `(c:c)` Notation an. KQL fügt die logischen Operatoren (entsprechend den bereits erläuterten Regeln) beim Ausführen der Abfrage hinzu.

- Sie können das Drag & Drop-Steuerelement verwenden, um die Reihenfolge der Bedingungen erneut anzuzeigen. Klicken Sie auf das Steuerelement für eine Bedingung, und verschieben Sie sie nach oben oder unten.

- Wie zuvor erläutert, können Sie mit einigen Bedingungseigenschaften mehrere Werte eingeben (getrennt durch Semikolons). Jeder Wert ist logisch durch den **OR-Operator** verbunden und führt zu der `(filetype=docx) OR (filetype=pptx) OR (filetype=xlsx)` Abfrage. Die folgende Abbildung zeigt ein Beispiel für eine Bedingung mit mehreren Werten.

    ![Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine bestimmte Bedingung erfüllt werden muss, verwenden Sie für jede Bedingung separate Regeln. Wenn Sie Nachrichten mit Anlagen und Nachrichten mit Inhalt, der einem Muster entspricht, z. B. die gleichen Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. Sie können eine Regel problemlos kopieren.](../media/SearchConditions1.png)

  > [!NOTE]
  > Sie können nicht mehrere Bedingungen hinzufügen (indem Sie auf "Bedingung für dieselbe Eigenschaft **hinzufügen"** klicken. Stattdessen müssen Sie mehrere Werte für die Bedingung angeben (getrennt durch Semikolons), wie im vorherigen Beispiel gezeigt.

### <a name="examples-of-using-conditions-in-search-queries"></a>Beispiele

Die folgenden Beispiele zeigen die GUI-basierte Version einer Suchabfrage mit Bedingungen, die Suchabfragesyntax, die im Detailbereich der ausgewählten Suche angezeigt wird (die auch vom Cmdlet **Get-ComplianceSearch** zurückgegeben wird) und die Logik der entsprechenden KQL-Abfrage.

#### <a name="example-1"></a>Beispiel 1

In diesem Beispiel werden Dokumente auf SharePoint und OneDrive for Business Websites zurückgegeben, die eine Kreditkartennummer enthalten und zuletzt vor dem 1. Januar 2021 geändert wurden.

**GUI**:

![Erstes Beispiel für Suchbedingungen](../media/SearchConditions2.png)

**Suchabfragesyntax:**

`SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2021-01-01)`

**Suchabfragelogik:**

`SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2021-01-01)`

Beachten Sie im vorherigen Screenshot, dass die Benutzeroberfläche der Suche bestätigt, dass die Schlüsselwortabfrage und -bedingung durch den **OPERATOR AND** verbunden sind.

#### <a name="example-2"></a>Beispiel 2

In diesem Beispiel werden E-Mail-Elemente oder Dokumente zurückgegeben, die das Schlüsselwort "report" enthalten, die vor dem 1. April 2021 gesendet oder erstellt wurden und das Wort "northwind" im Betrefffeld von E-Mail-Nachrichten oder in der Titeleigenschaft von Dokumenten enthalten. Die Abfrage schließt Webseiten aus, die den anderen Suchkriterien entsprechen.

**GUI**:

![Zweites Beispiel für Suchbedingungen](../media/SearchConditions3.png)

**Suchabfragesyntax:**

`report(c:c)(date<2021-04-01)(subjecttitle:"northwind")(-filetype:aspx)`

**Suchabfragelogik:**

`report AND (date<2021-04-01) AND (subjecttitle:"northwind") NOT (filetype:aspx)`

#### <a name="example-3"></a>Beispiel 3

In diesem Beispiel werden E-Mail-Nachrichten oder Kalenderbesprechungen zurückgegeben, die zwischen dem 1.1.2019 und dem 30.11.2020 gesendet wurden und Wörter enthalten, die mit "Telefon" oder "Smartphone" beginnen.

**GUI**:

![Drittes Beispiel für Suchbedingungen](../media/SearchConditions4.png)

**Suchabfragesyntax:**

`phone* OR smartphone*(c:c)(sent=2019-12-01..2020-11-30)(kind="email")(kind="meetings")`

**Suchabfragelogik:**

`phone* OR smartphone* AND (sent=2029-12-01..2020-11-30) AND ((kind="email") OR (kind="meetings"))`

## <a name="special-characters"></a>Sonderzeichen

Einige Sonderzeichen sind nicht im Suchindex enthalten und daher nicht durchsuchbar. Dazu gehören auch die Sonderzeichen, die Suchoperatoren in der Suchabfrage darstellen. Nachfolgend finden Sie eine Liste von Sonderzeichen, die entweder durch ein Leerzeichen in der tatsächlichen Suchabfrage ersetzt werden oder einen Suchfehler verursachen.

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>Suchen nach Websiteinhalten, die für externe Benutzer freigegeben sind

Sie können auch eDiscovery-Suchtools im Compliance Center verwenden, um nach Dokumenten zu suchen, die auf SharePoint und OneDrive for Business Websites gespeichert sind, die für Personen außerhalb Ihrer Organisation freigegeben wurden. Dies kann Ihnen helfen, vertrauliche oder proprietäre Informationen zu identifizieren, die außerhalb Ihrer Organisation geteilt werden. Dazu können Sie die  `ViewableByExternalUsers` Eigenschaft in einer Stichwortabfrage verwenden. Diese Eigenschaft gibt Dokumente oder Websites zurück, die mithilfe einer der folgenden Freigabemethoden für externe Benutzer freigegeben wurden:

- Eine Freigabe-Einladung, die erfordert, dass sich Benutzer bei Ihrer Organisation als authentifizierter Benutzer anmelden müssen.
- Ein anonymer Gastlink, mit dem jeder mit diesem Link auf die Ressource zugreifen kann, ohne authentifiziert werden zu müssen.

Im Folgenden finden Sie einige Beispiele:

- Die Abfrage  `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` gibt alle Elemente zurück, die für Personen außerhalb Ihrer Organisation freigegeben wurden und eine Kreditkartennummer enthalten.
- Die Abfrage  `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` gibt eine Liste der Dokumente auf allen Teamwebsites in der Organisation zurück, die für externe Benutzer freigegeben wurden.

> [!TIP]
> Eine Suchabfrage, die  `ViewableByExternalUsers:true AND ContentType:document` möglicherweise viele ASPX-Dateien in den Suchergebnissen zurückgibt. Um diese (oder andere Dateitypen) auszuschließen, können Sie die  `FileExtension` Eigenschaft verwenden, um bestimmte Dateitypen auszuschließen, z.  `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx` B. .

Was wird als Inhalt betrachtet, der für Personen außerhalb Ihrer Organisation freigegeben wird? Dokumente in den SharePoint und OneDrive for Business Websites Ihrer Organisation, die durch Senden einer Freigabe-Einladung freigegeben oder an öffentlichen Orten freigegeben werden. Die folgenden Benutzeraktivitäten führen beispielsweise zu Inhalten, die von externen Benutzern angezeigt werden können:

- Ein Benutzer gibt eine Datei oder einen Ordner für eine Person außerhalb Ihrer Organisation frei.
- Ein Benutzer erstellt und sendet einen Link zu einer freigegebenen Datei an eine Person außerhalb Ihrer Organisation. Über diesen Link kann der externe Benutzer die Datei anzeigen (oder bearbeiten).
- Ein Benutzer sendet eine Freigabe-Einladung oder einen Gastlink an eine Person außerhalb Ihrer Organisation, um eine freigegebene Datei anzuzeigen (oder zu bearbeiten).

### <a name="issues-using-the-viewablebyexternalusers-property"></a>Probleme bei der Verwendung der ViewableByExternalUsers-Eigenschaft

Die  `ViewableByExternalUsers` Eigenschaft stellt zwar den Status dar, ob ein Dokument oder eine Website für externe Benutzer freigegeben wird, es gibt jedoch einige Vorsichtsmaßnahmen, was diese Eigenschaft bewirkt und nicht widerspiegelt. In den folgenden Szenarien wird der Wert der  `ViewableByExternalUsers` Eigenschaft nicht aktualisiert, und die Ergebnisse einer Suchabfrage, die diese Eigenschaft verwendet, sind möglicherweise ungenau.

- Änderungen an der Freigaberichtlinie, z. B. Deaktivieren der externen Freigabe für eine Website oder für die Organisation. Die Eigenschaft zeigt weiterhin an, dass zuvor freigegebene Dokumente extern zugänglich sind, obwohl der externe Zugriff möglicherweise widerrufen wurde.
- Änderungen an der Gruppenmitgliedschaft, z. B. Hinzufügen oder Entfernen externer Benutzer zu Microsoft 365 Gruppen oder Microsoft 365 Sicherheitsgruppen. Die Eigenschaft wird nicht automatisch für Elemente aktualisiert, auf die die Gruppe Zugriff hat.
- Senden von Freigabe-Einladungen an externe Benutzer, bei denen der Empfänger die Einladung nicht angenommen hat und daher noch keinen Zugriff auf den Inhalt hat.

In diesen Szenarien gibt die  `ViewableByExternalUsers` Eigenschaft erst dann den aktuellen Freigabestatus wieder, wenn die Website oder Dokumentbibliothek erneut durchforsht und neu indiziert wird.

## <a name="searching-for-site-content-shared-within-your-organization"></a>Suchen nach in Ihrer Organisation freigegebenen Websiteinhalten

Wie zuvor erläutert, können Sie die Eigenschaft verwenden,  `SharedWithUsersOWSUser` um nach Dokumenten zu suchen, die von Personen in Ihrer Organisation freigegeben wurden. Wenn eine Person eine Datei (oder einen Ordner) für einen anderen Benutzer innerhalb Ihrer Organisation freigibt, wird auf der Seite **"Für mich freigegeben"** im OneDrive for Business Konto der Person, für die die Datei freigegeben wurde, ein Link zu der freigegebenen Datei angezeigt. Um z. B. nach den Dokumenten zu suchen, die für Sara David freigegeben wurden, können Sie die Abfrage  `SharedWithUsersOWSUser:"sarad@contoso.com"` verwenden. Wenn Sie die Ergebnisse dieser Suche exportieren, werden die Originaldokumente (die sich am Inhaltsspeicherort der Person befinden, die die Dokumente für Sara freigegeben hat) heruntergeladen.

Dokumente müssen explizit für einen bestimmten Benutzer freigegeben werden, damit sie bei Verwendung der Eigenschaft in den Suchergebnissen zurückgegeben  `SharedWithUsersOWSUser` werden. Wenn eine Person beispielsweise ein Dokument in ihrem OneDrive-Konto freigibt, hat sie die Möglichkeit, es für alle Personen (innerhalb oder außerhalb der Organisation) freizugeben, es nur für Personen innerhalb der Organisation oder für eine bestimmte Person freizugeben. Hier ist ein Screenshot des **Fensters "Freigeben"** in OneDrive, in dem die drei Freigabeoptionen angezeigt werden.

![Nur Dateien, die für bestimmte Personen freigegeben sind, werden von einer Suchabfrage zurückgegeben, die die SharedWithUsersOWSUser-Eigenschaft verwendet.](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)

Nur Dokumente, die mithilfe der dritten Option (freigegeben für **bestimmte Personen)** freigegeben werden, werden von einer Suchabfrage zurückgegeben, die die  `SharedWithUsersOWSUser` Eigenschaft verwendet.

## <a name="searching-for-skype-for-business-conversations"></a>Suchen nach Skype for Business Unterhaltungen

Mit der folgenden Stichwortabfrage können Sie gezielt nach Inhalten in Skype for Business Unterhaltungen suchen:

```powershell
kind:im
```

Die vorherige Suchabfrage gibt auch Chats von Microsoft Teams zurück. Um dies zu verhindern, können Sie die Suchergebnisse einschränken, um nur Skype for Business Unterhaltungen einzuschließen, indem Sie die folgende Stichwortabfrage verwenden:

```powershell
kind:im AND subject:conversation
```

Die vorherige Stichwortabfrage schließt Chats in Microsoft Teams aus, da Skype for Business Unterhaltungen als E-Mail-Nachrichten mit einer Betreffzeile gespeichert werden, die mit dem Wort "Unterhaltung" beginnt.

Verwenden Sie die folgende Stichwortabfrage, um nach Skype for Business Unterhaltungen zu suchen, die innerhalb eines bestimmten Datumsbereichs aufgetreten sind:

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="character-limits-for-searches"></a>Zeichenbeschränkungen für Suchvorgänge

Beim Suchen nach Inhalten in SharePoint Websites und OneDrive Konten gilt ein Grenzwert von 4.000 Zeichen für Suchabfragen.
Hier sehen Sie, wie die Gesamtzahl der Zeichen in der Suchabfrage berechnet wird:

- Die Zeichen in der Stichwortsuchabfrage (einschließlich Benutzer- und Filterfeldern) werden gegen diesen Grenzwert gezählt.
- Die Zeichen in einer beliebigen Standorteigenschaft (z. B. die URLs für alle SharePoint Websites oder OneDrive Speicherorte, die durchsucht werden) zählen gegen diesen Grenzwert.
- Die Zeichen in allen Suchberechtigungsfiltern, die auf den Benutzer angewendet werden, der die Suchanzahl für den Grenzwert ausführt.

Weitere Informationen zu Zeichenbeschränkungen finden Sie unter [eDiscovery-Suchgrenzwerte.](limits-for-content-search.md#search-limits)

> [!NOTE]
> Der Grenzwert von 4.000 Zeichen gilt für die Inhaltssuche, Core eDiscovery und Advanced eDiscovery.

## <a name="search-tips-and-tricks"></a>Tipps und Tricks für die Suche

- Bei Stichwortsuchen wird die Groß-/Kleinschreibung nicht beachtet. Beispielsweise geben **katze** und **KATZE** dieselben Ergebnisse zurück.

- Die booleschen Operatoren **AND**, **OR**, **NOT** und **NEAR** müssen groß geschrieben sein.

- A space between two keywords or two  `property:value` expressions is the same as using **AND**. Gibt z. B. alle von Sara David gesendeten Nachrichten zurück,  `from:"Sara Davis" subject:reorganization` die das Wort "neu" in der Betreffzeile enthalten.

- Verwenden Sie eine Syntax, die dem `property:value` Format entspricht. Bei Werten wird die Groß-/Kleinschreibung nicht beachtet, und nach dem Operator kann kein Leerzeichen vorhanden sein. Wenn ein Leerzeichen vorhanden ist, ist ihr beabsichtigter Wert eine Volltextsuche. For example `to: pilarp` searches for "pilarp" as a keyword, rather than for messages that were sent to pilarp.

- Wenn Sie nach einer Empfängereigenschaft wie An, Von, Cc oder Empfänger suchen, können Sie eine SMTP-Adresse, einen Alias oder einen Anzeigenamen verwenden, um einen Empfänger anzugeben. Sie können z. B. pilarp@contoso.com, pilarp oder "Pilar Pinilla" verwenden.

- Sie können nur Präfixsuchen verwenden. z. B. **Cat _ oder \* *_* set \* *_. Suffixsuchen (_* \* Cat**), Infixsuchen (**c \* t**) und Teilzeichenfolgensuchen (**\* Katze \***) werden nicht unterstützt.

- Verwenden Sie beim Durchsuchen einer Eigenschaft doppelte Anführungszeichen (" "), wenn der Suchwert aus mehreren Wörtern besteht. Gibt beispielsweise `subject:budget Q1` Nachrichten zurück, die **das Budget** in der Betreffzeile und **Q1** an einer beliebigen Stelle in der Nachricht oder in einer der Nachrichteneigenschaften enthalten. Using `subject:"budget Q1"` returns all messages that contain budget **Q1** anywhere in the subject line.

- Wenn Sie Inhalte mit einem bestimmten Eigenschaftswert in den Suchergebnissen ausschließen möchten, fügen Sie ein Minuszeichen (-) vor dem Namen der Eigenschaft hinzu. Schließt beispielsweise alle Nachrichten aus, die `-from:"Sara Davis"` von Sara David gesendet wurden.

- Sie können Elemente basierend auf dem Nachrichtentyp exportieren. Verwenden Sie beispielsweise die Syntax, um Skype Unterhaltungen und Chats in Microsoft Teams zu `kind:im` exportieren. Um nur E-Mail-Nachrichten zurückzugeben, verwenden Sie `kind:email` . Verwenden Sie zum Zurückgeben von Chats, Besprechungen und Anrufen in `kind:microsoftteams` Microsoft Teams.

- Wie bereits erläutert, müssen Sie beim Durchsuchen von Websites das nachstehende `/` Ende der URL hinzufügen, wenn Sie die `path` Eigenschaft verwenden, um nur Elemente in einer angegebenen Website zurückzugeben. Wenn Sie die nachstehenden Elemente nicht `/` einschließen, werden auch Elemente von einer Website mit einem ähnlichen Pfadnamen zurückgegeben. Wenn Sie z. B. Elemente von benannten Websites verwenden `path:sites/HelloWorld` oder auch zurückgegeben `sites/HelloWorld_East` `sites/HelloWorld_West` werden. Um nur Elemente von der HelloWorld-Website zurückzugeben, müssen Sie `path:sites/HelloWorld/` verwenden.
