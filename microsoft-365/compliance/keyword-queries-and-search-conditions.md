---
title: Stichwortabfragen und Suchbedingungen für die Inhaltssuche
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
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
description: 'Erfahren Sie mehr über e-Mail-und Dateieigenschaften, die Sie in Exchange Online Postfächern und in SharePoint-oder OneDrive für Unternehmen-Websites mithilfe des Inhalts Such Tools im Security #a0 Compliance Center durchsuchen können.  '
ms.openlocfilehash: d76f92de4b41c7f6f0494af36a7e1aee953b9896
ms.sourcegitcommit: cbf934ef448fc428f5ed53b07cda7a5f72c89221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "40911473"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Stichwortabfragen und Suchbedingungen für die Inhaltssuche

In diesem Thema werden die e-Mail-und Dokumenteigenschaften beschrieben, nach denen Sie in e-Mail-Elementen in Exchange Online suchen können, sowie Dokumente, die in SharePoint und OneDrive für Unternehmen Websites gespeichert sind, indem Sie die Inhaltssuche im Security #a0 Compliance Center verwenden. Sie können auch die ** \*-ComplianceSearch-** Cmdlets in Security #a0 Compliance Center PowerShell verwenden, um nach diesen Eigenschaften zu suchen. Im Thema wird außerdem Folgendes beschrieben:   
  
- Verwenden Sie boolesche Suchoperatoren, Suchbedingungen und andere Suchabfrage Techniken, um Ihre Suchergebnisse zu verfeinern.
    
- Suchen nach vertraulichen Datentypen und benutzerdefinierten vertraulichen Datentypen in SharePoint und OneDrive für Unternehmen.
    
- Suchen nach Websiteinhalten, die für Benutzer außerhalb Ihrer Organisation freigegeben sind
    
Eine Schritt-für-Schritt-Anleitung zum Erstellen einer Inhaltssuche finden Sie unter [Inhaltssuche in Office 365](content-search.md).

  
> [!NOTE]
> Die Inhaltssuche im Security #a0 Compliance Center und die entsprechenden ** \*-ComplianceSearch-** Cmdlets in Security #a1 Compliance Center PowerShell verwenden die Schlüsselwortabfrage Sprache (KQL). Ausführlichere Informationen finden Sie unter [Keyword Query Language Syntax Reference](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Durchsuchbare E-Mail-Eigenschaften

In der folgenden Tabelle sind die Eigenschaften von e-Mail-Nachrichten aufgeführt, die mithilfe der Inhalts Suchfunktion im Security #a0 Compliance Center oder mithilfe des Cmdlets **New-ComplianceSearch** oder **ComplianceSearch** durchsucht werden können. Die Tabelle enthält ein Beispiel für die  _property:value_-Syntax für jede Eigenschaft und eine Beschreibung der für jedes Beispiel zurückgegebenen Suchergebnisse. Sie können diese `property:value` Paare in das Feld Schlüsselwörter für eine Inhaltssuche eingeben. 

> [!NOTE]
> Beim Durchsuchen von e-Mail-Eigenschaften ist es nicht möglich, nach Elementen zu suchen, in denen die angegebene Eigenschaft leer oder leer ist. Wenn Sie beispielsweise die *Eigenschaft: Wert-* paar von **Subject: ""** verwenden, um nach e-Mail-Nachrichten mit einer leeren Betreffzeile zu suchen, werden keine Ergebnisse zurückgegeben. Dies gilt auch beim Durchsuchen von Website-und Kontakteigenschaften.
  
|**Eigenschaft**|**Beschreibung der Eigenschaft**|**Beispiele**|**Von den Beispielen zurückgegebene Suchergebnisse**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|Die Namen der an eine E-Mail angefügten Dateien.|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*` <br/> attachmentnames: PPTX|Nachrichten, an die eine Datei namens Jahresbericht.ppt angehängt ist. Im zweiten Beispiel werden, wenn Sie das Platzhalterzeichen verwenden, Nachrichten mit dem Wort "Jahresbericht" im Dateinamen eines Anhangs zurückgegeben. Im dritten Beispiel werden alle Anlagen mit der PPTX-Dateierweiterung zurückgegeben.|
|Bcc|Das Feld "Bcc" einer e-Mail-Nachricht. <sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|In allen Beispielen werden Nachrichten mit dem Namen "Pilar Pinilla" im Bcc-Feld zurückgegeben.|
|Kategorie| Die Kategorien, nach denen gesucht wird. Kategorien können von Benutzern mithilfe von Outlook oder Outlook im Internet (früher bekannt als Outlook Web App) definiert werden. Die folgenden Werte sind möglich:  <br/><br/>  blau  <br/>  grün  <br/>  orange  <br/>  violett  <br/>  rot  <br/>  gelb|`category:"Red Category"`|Nachrichten, denen in den Quellpostfächern die rote Kategorie zugewiesen wurde.|
|Cc|Das Feld "CC" einer e-Mail-Nachricht. <sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|In beiden Beispielen werden Nachrichten mit Pilar Pinilla im Feld CC angegeben.|
|Folderid|Die Ordner-ID (GUID) eines bestimmten Postfachordners. Wenn Sie diese Eigenschaft verwenden, müssen Sie das Postfach durchsuchen, in dem sich der angegebene Ordner befindet. Es wird nur der angegebene Ordner durchsucht. Alle Unterordner im Ordner werden nicht durchsucht. Zum Durchsuchen von Unterordnern müssen Sie die Folder-Eigenschaft für den Unterordner verwenden, den Sie durchsuchen möchten.  <br/> Weitere Informationen zum Suchen nach der Folder ID-Eigenschaft und zum Abrufen der Ordner-IDs für ein bestimmtes Postfach mithilfe eines Skripts finden Sie unter [Verwenden der Inhaltssuche in Office 365 für gezielte Auflistungen](use-content-search-for-targeted-collections.md).|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|Im ersten Beispiel werden alle Elemente im angegebenen Postfachordner zurückgegeben. Im zweiten Beispiel werden alle Elemente im angegebenen Postfachordner zurückgegeben, die von garthf@contoso.com gesendet oder empfangen wurden.|
|Von|Der Absender einer E-Mail-Nachricht.<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|Nachrichten, die vom angegebenen Benutzer oder einer bestimmten Domäne gesendet wurden.|
|HasAttachment|Gibt an, ob eine Nachricht eine Anlage enthält. Verwenden Sie die Werte **true** oder **false**.|`from:pilar@contoso.com AND hasattachment:true`|Nachrichten, die vom angegebenen Benutzer mit Anlagen gesendet werden.|
|Wichtigkeit|Die Wichtigkeit einer E-Mail-Nachricht, die ein Absender festlegen kann, wenn er eine Nachricht sendet. Standardmäßig werden Nachrichten mit normaler Wichtigkeit gesendet, außer wenn der Absender die Wichtigkeit auf **Hoch** oder **Niedrig** setzt.  |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|Nachrichten, deren Wichtigkeit auf "Hoch", "Mittel" bzw. "Niedrig" eingestellt ist.|
|IsRead|Gibt an, ob Nachrichten gelesen wurden. Verwenden Sie die Werte **true** oder **false**.|`isread:true`  <br/> `isread:false`|Im ersten Beispiel werden Nachrichten zurückgegeben, wobei die isread-Eigenschaft auf **true**festgelegt ist. Im zweiten Beispiel werden Nachrichten zurückgegeben, wobei die isread-Eigenschaft auf **false**festgelegt ist.|
|ItemClass|Verwenden Sie diese Eigenschaft, um bestimmte Datentypen von Drittanbietern zu durchsuchen, die Ihre Organisation in Office 365 importiert hat. Verwenden Sie die folgende Syntax für diese Eigenschaft:`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|Im ersten Beispiel werden Facebook-Elemente zurückgegeben, die das Wort "Contoso" in der Subject-Eigenschaft enthalten. Im zweiten Beispiel werden Twitter-Elemente zurückgegeben, die von Ann Beebe veröffentlicht wurden und die den stichwortausdruck "Northwind Traders" enthalten.  <br/> Eine vollständige Liste der Werte, die für Drittanbieter-Datentypen für die ItemClass-Eigenschaft verwendet werden sollen, finden Sie unter [Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Office 365 importiert wurden](use-content-search-to-search-third-party-data-that-was-imported.md).|
|Art| Der Typ der zu suchenden e-Mail-Nachricht. Mögliche Werte:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  verläuft (gibt Elemente aus Chats, Besprechungen und anrufen in Microsoft Teams zurück)  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|Im ersten Beispiel werden e-Mail-Nachrichten zurückgegeben, die den Suchkriterien entsprechen. Im zweiten Beispiel werden e-Mail-Nachrichten, Chat Unterhaltungen (einschließlich Skype for Business Unterhaltungen und Chats in Microsoft Teams) und Sprachnachrichten, die den Suchkriterien entsprechen, zurückgegeben. Im dritten Beispiel werden Elemente zurückgegeben, die in Office 365 aus Drittanbieter-Datenquellen, wie Twitter, Facebook und Cisco Jabber, die den Suchkriterien entsprechen, in Postfächer importiert wurden. Weitere Informationen finden Sie unter [Archivieren von drittanbieterdaten in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).|
|Participants|Alle Personen Felder in einer e-Mail-Nachricht. Diese Felder sind von, in, CC und Bcc.<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|Nachrichten, die von oder an garthf@contoso.com gesendet wurden. Im zweiten Beispiel werden alle Nachrichten zurückgegeben, die von oder an einen Benutzer in der Domäne contoso.com gesendet wurden.|
|Empfangen|Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde.|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|Nachrichten, die am 15. April 2016 empfangen wurden. Im zweiten Beispiel werden alle Nachrichten zurückgegeben, die zwischen dem 1. Januar 2016 und dem 31. März 2016 empfangen wurden.|
|Empfänger|Alle Empfängerfelder in einer e-Mail-Nachricht. Diese Felder sind to, CC und Bcc.<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|Nachrichten, die an garthf@contoso.com gesendet wurden. Im zweiten Beispiel werden Nachrichten zurückgegeben, die an einen Empfänger in der Domäne contoso.com gesendet wurden.|
|Gesendet|Das Datum, an dem eine E-Mail vom Absender gesendet wurde.|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|Nachrichten, die am angegebenen Tag oder im angegebenen Datumsbereich gesendet wurden.|
|Größe|Die Größe eines Elements in Byte.|`size>26214400`  <br/> `size:1..1048567`|Nachrichten größer als 25?? MB. Im zweiten Beispiel werden Nachrichten von 1 bis 1.048.567 Byte (1 MB) in Größe zurückgegeben.|
|Betreff|Der Text in der Betreffzeile einer E-Mail.  <br/> **Hinweis:** Wenn Sie die Subject-Eigenschaft in einer Abfrage verwenden, gibt die Suche alle Nachrichten zurück, in denen die Betreffzeile den gesuchten Text enthält. Mit anderen Worten: die Abfrage gibt nicht nur die Nachrichten zurück, die eine exakte Übereinstimmung aufweisen. Wenn Sie beispielsweise nach suchen `subject:"Quarterly Financials"`, enthalten Ihre Ergebnisse Nachrichten mit dem Betreff "Quarterly Financials 2018".|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|Nachrichten, die den Ausdruck "vierteljährliche Finanzdaten" an beliebiger Stelle im Text der Betreffzeile enthalten. Im zweiten Beispiel werden alle Nachrichten mit dem Wort "northwind" in der Betreffzeile zurückgegeben.|
|An|Das Feld „An" einer E-Mail-Nachricht.<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|In allen Beispielen wegen Nachrichten zurückgegeben, in deren Zeile "An" der Name "Ann Beebe" angegeben ist.|
|||||
   
> [!NOTE]
> <sup>1</sup> für den Wert einer Recipient-Eigenschaft können Sie e-Mail-Adresse (auch als *Benutzerprinzipalname* oder UPN bezeichnet), Anzeigename oder Alias verwenden, um einen Benutzer anzugeben. Sie können z. B. annb@contoso.com, Annb oder „Ann Beebe“ verwenden, um den Benutzer Ann Beebe anzugeben.<br/><br/>Beim Durchsuchen einer der Empfänger Eigenschaften (von, an, CC, BCC, Teilnehmern und Empfängern) versucht Office 365, die Identität jedes Benutzers zu erweitern, indem er Sie in Azure Active Directory nach oben sucht.  Wenn der Benutzer in Azure Active Directory gefunden wird, wird die Abfrage erweitert, um die e-Mail-Adresse des Benutzers (oder UPN), den Alias, den Anzeigenamen und legacyExchangeDN einzuschließen.<br/><br/>Beispielsweise wird eine Abfrage wie `participants:ronnie@contoso.com` erweitert zu. `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`<br/><br/>Um die Empfänger Erweiterung zu verhindern, können Sie ein Platzhalterzeichen (Sternchen) am Ende der e-Mail-Adresse in der Suchabfrage hinzufügen. Beispiel: `participants:ronnie@contoso.com*`.

## <a name="searchable-site-properties"></a>Durchsuchbare Websiteeigenschaften

In der folgenden Tabelle sind einige der SharePoint-und OneDrive für Unternehmen-Eigenschaften aufgeführt, die mithilfe der Inhalts Suchfunktion im Security #a0 Compliance Center oder mithilfe des Cmdlets **New-ComplianceSearch** oder **ComplianceSearch** durchsucht werden können. Die Tabelle enthält ein Beispiel für die  _property:value_-Syntax für jede Eigenschaft und eine Beschreibung der für jedes Beispiel zurückgegebenen Suchergebnisse. 
  
Eine vollständige Liste der SharePoint-Eigenschaften, die durchsucht werden können, finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Eigenschaften, die mit einem **Ja** in der **Queryable** -Spalte markiert sind, können durchsucht werden. 
  
|**Eigenschaft**|**Beschreibung der Eigenschaft**|**Beispiel**|**Von den Beispielen zurückgegebene Suchergebnisse**|
|:-----|:-----|:-----|:-----|
|Ursprung|Das Feld Autor aus Office-Dokumenten, das bleibt, wenn ein Dokument kopiert wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die e-Mails an eine andere Person weitergeben, die es dann in SharePoint hoch lädt, behält das Dokument weiterhin den ursprünglichen Autor bei. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`author:"Garth Fort"`|Alle Dokumente, die von Garth fort erstellt wurden.|
|ContentType|Der SharePoint-Inhaltstyp eines Elements wie Element, Dokument oder Video.|`contenttype:document`|Alle Dokumente werden zurückgegeben.|
|Erstellt|Das Datum, an dem ein Element erstellt wird.|`created\>=06/01/2016`|Alle Elemente, die am oder nach dem 1. Juni 2016 erstellt wurden.|
|CreatedBy|Die Person, die ein Element erstellt oder hochgeladen hat. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`createdby:"Garth Fort"`|Alle Elemente, die von Garth fort erstellt oder hochgeladen wurden.|
|DetectedLanguage|Die Sprache eines Elements.|`detectedlanguage:english`|Alle Elemente in Englisch.|
|DocumentLink|Der Pfad (URL) eines bestimmten Ordners auf einer SharePoint-oder OneDrive für Unternehmen-Website. Wenn Sie diese Eigenschaft verwenden, müssen Sie die Website durchsuchen, in der sich der angegebene Ordner befindet.  <br/> Um Elemente zurückzugeben, die sich in Unterordnern des Ordners befinden, den Sie für die documentlink-Eigenschaft angeben, müssen\* Sie die URL des angegebenen Ordners hinzufügen. Zum Beispiel`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Weitere Informationen zum Suchen nach der documentlink-Eigenschaft und zum Abrufen der documentlink-URLs für Ordner auf einer bestimmten Website mithilfe eines Skripts finden Sie unter [Verwenden der Inhaltssuche in Office 365 für gezielte Auflistungen](use-content-search-for-targeted-collections.md).|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|Im ersten Beispiel werden alle Elemente im angegebenen OneDrive für Unternehmen-Ordner zurückgegeben. Im zweiten Beispiel werden Dokumente im angegebenen Websiteordner (und alle Unterordner) zurückgegeben, die das Wort "Confidential" im Dateinamen enthalten.|
|File extension|Die Erweiterung einer Datei; beispielsweise docx, 1, PPTX oder xlsx.|`fileextension:xlsx`|Alle Excel-Dateien (Excel 2007 und höher)|
|FileName|Der Name einer Datei.|`filename:"marketing plan"`  <br/> `filename:estimate`|Im ersten Beispiel werden Dateien mit dem genauen Ausdruck "Marketingplan" im Titel zurückgegeben. Im zweiten Beispiel werden Dateien mit dem Wort "Estimate" im Dateinamen zurückgegeben.|
|LastModifiedTime|Das Datum, an dem ein Element zuletzt geändert wurde.|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|Im ersten Beispiel werden Elemente zurückgegeben, die am oder nach dem 1. Mai 2016 geändert wurden. Das zweite Beispiel gibt Elemente zurück, die zwischen dem 1. Mai 2016 und dem 1. Juni 2016 geändert wurden.|
|ModifiedBy|Die Person, die ein Element zuletzt geändert hat. Achten Sie darauf, den Anzeigenamen des Benutzers für diese Eigenschaft zu verwenden.|`modifiedby:"Garth Fort"`|Alle Elemente, die zuletzt von Garth fort geändert wurden.|
|Path|Der Pfad (URL) einer bestimmten Website in einer SharePoint-oder OneDrive für Unternehmen-Website.  <br/> Um Elemente zurückzugeben, die sich in Ordnern auf der Website befinden, die Sie für die Path-Eigenschaft angeben\* , müssen Sie die URL der angegebenen Website hinzufügen. Zum Beispiel`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **Hinweis:** Wenn Sie `Path` die Eigenschaft zum Durchsuchen von OneDrive-Speicherorten verwenden, werden keine Mediendateien wie PNG-, TIFF-oder WAV-Dateien in den Suchergebnissen zurückgegeben. Verwenden Sie eine andere Website Eigenschaft in Ihrer Suchabfrage, um nach Mediendateien in OneDrive-Ordnern zu suchen. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|Im ersten Beispiel werden alle Elemente im angegebenen OneDrive für Unternehmen-Standort zurückgegeben. Das zweite Beispiel gibt Dokumente in der angegebenen Website (und Ordner auf der Website) zurück, die das Wort "Confidential" im Dateinamen enthalten.|
|SharedWithUsersOWSUser|Dokumente, die für den angegebenen Benutzer freigegeben wurden und auf der Seite für **mich freigegeben** auf der OneDrive für Unternehmen Website des Benutzers angezeigt werden. Dabei handelt es sich um Dokumente, die von anderen Personen in Ihrer Organisation explizit für den angegebenen Benutzer freigegeben wurden. Beim Exportieren von Dokumenten, die einer Suchabfrage entsprechen, die die SharedWithUsersOWSUser-Eigenschaft verwendet, werden die Dokumente aus dem ursprünglichen Inhaltsspeicherort der Person exportiert, die das Dokument gemeinsam mit dem angegebenen Benutzer freigegeben hat. Weitere Informationen finden Sie unter [Suchen nach Websiteinhalten, die in Ihrer Organisation freigegeben](#searching-for-site-content-shared-within-your-organization)sind.|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|In beiden Beispielen werden alle internen Dokumente zurückgegeben, die explizit für Garth fort freigegeben wurden und auf der Seite für **mich freigegeben** in Garth fort in OneDrive für Unternehmen Konto angezeigt werden.|
|Website|Die URL einer Website oder Gruppen von Websites in Ihrer Organisation.|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|Im ersten Beispiel werden Elemente aus den OneDrive für Unternehmen Websites für alle Benutzer in der Organisation zurückgegeben. Im zweiten Beispiel werden Elemente von allen Teamwebsites zurückgegeben.|
|Größe|Die Größe eines Elements in Byte.|`size>=1`  <br/> `size:1..10000`|Das erste Beispiel gibt Elemente zurück, die größer als 1 Byte sind. Das zweite Beispiel gibt Elemente von 1 bis 10.000 Bytes an Größe zurück.|
|Position|Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Microsoft Office Dokumenten angegeben sind. Er unterscheidet sich vom Dateinamen des Dokuments.|`title:"communication plan"`|Jedes Dokument, das den Ausdruck "Kommunikationsplan" in der Title Metadata-Eigenschaft eines Office-Dokuments enthält.|
|||||
   
## <a name="searchable-contact-properties"></a>Durchsuchbare Kontakteigenschaften

In der folgenden Tabelle sind die Kontakteigenschaften aufgelistet, die indiziert werden und nach denen Sie die Inhaltssuche verwenden können. Dies sind die Eigenschaften, die Benutzern zur Verfügung stehen, um für die Kontakte (auch persönliche Kontakte genannt) zu konfigurieren, die sich im persönlichen Adressbuch des Postfachs eines Benutzers befinden. Um nach Kontakten zu suchen, können Sie die zu durchsuchenden Postfächer auswählen und dann eine oder mehrere Kontakteigenschaften in der Stichwortabfrage verwenden.
  
> [!TIP]
> Um nach Werten zu suchen, die Leerzeichen oder Sonderzeichen enthalten, verwenden Sie doppelte Anführungszeichen (""), um den Ausdruck einzuhalten; Beispiel: `businessaddress:"123 Main Street"`. 
  
|**Eigenschaft**|**Beschreibung der Eigenschaft**|
|:-----|:-----|
|BusinessAddress|Die Adresse in der **Business Address** -Eigenschaft. Die-Eigenschaft wird auch auf der Seite Kontakteigenschaften als **Arbeits** Adresse bezeichnet.|
|Businessphone|Die Telefonnummer in einer der **Geschäftstelefonnummer** -Eigenschaften.|
|CompanyName|Der Name in der **Company** -Eigenschaft.|
|Abteilung|Der Name in der **Department** -Eigenschaft.|
|DisplayName|Der Anzeigename des Kontakts. Dies ist der Name in der **vollständigen Name** -Eigenschaft des Kontakts.|
|EmailAddress|Die Adresse für eine beliebige e-Mail-Adress Eigenschaft für den Kontakt. Benutzer können mehrere e-Mail-Adressen für einen Kontakt hinzufügen. Wenn Sie diese Eigenschaft verwenden, werden Kontakte zurückgegeben, die mit den e-Mail-Adressen des Kontakts übereinstimmen.|
|FileAs|Die Eigenschaft " **file as** ". Diese Eigenschaft wird verwendet, um anzugeben, wie der Kontakt in der Kontaktliste des Benutzers aufgeführt wird. Beispielsweise könnte ein Kontakt als *FirstName, LastName* oder *LastName, FirstName*aufgelistet werden.|
|GivenName|Der Name in der **First Name** -Eigenschaft.|
|HomeAddress|Die Adresse in einer der Eigenschaften der **Home** -Adresse.|
|HomePhone|Die Telefonnummer in den Eigenschaften der **privaten** Telefonnummer.|
|IMAddress|Die Eigenschaft "Chat Adresse", bei der es sich normalerweise um eine e-Mail-Adresse für Chatnachrichten handelt.|
|MiddleName|Der Name in der **Middle** Name-Eigenschaft.|
|MobilePhone|Die Telefonnummer in der Eigenschaft **Mobil** Telefonnummer.|
|Nickname|Der Name in der **Nickname** -Eigenschaft.|
|OfficeLocation|Der Wert in der **Office** -oder **Office-Standort** Eigenschaft.|
|OtherAddress|Der Wert für die **andere** Address-Eigenschaft.|
|Nachname|Der Name in der **Last** Name-Eigenschaft.|
|Position|Der Titel in der **Position Title** -Eigenschaft.|
|||||

## <a name="searchable-sensitive-data-types"></a>Durchsuchbare vertrauliche Datentypen

Sie können das Feature für die Inhaltssuche im Security and Compliance Center verwenden, um nach vertraulichen Daten wie Kreditkartennummern oder Sozialversicherungsnummern zu suchen, die in Dokumenten auf SharePoint und OneDrive für Unternehmen Websites gespeichert sind. Sie können dies tun, indem Sie `SensitiveType` die-Eigenschaft und den Namen eines vertraulichen Informationstyps in einer Stichwortabfrage verwenden. Die Abfrage `SensitiveType:"Credit Card Number"` gibt beispielsweise Dokumente zurück, die eine Kreditkartennummer enthalten. Die Abfrage `SensitiveType:"U.S. Social Security Number (SSN)"` gibt Dokumente zurück, die eine Sozialversicherungsnummer der USA enthalten. Wenn Sie eine Liste der vertraulichen Datentypen anzeigen möchten, nach denen Sie suchen können, gehen Sie zu **Klassifizierungs** \> **Typen für vertrauliche Informationen** im Security #a0 Compliance Center. Sie können auch das Cmdlet **Get-DlpSensitiveInformationType** in der PowerShell Security #a0 Compliance Center verwenden, um eine Liste vertraulicher Informationstypen anzuzeigen. 
  
Sie können die `SensitiveType` -Eigenschaft auch verwenden, um nach dem Namen eines benutzerdefinierten vertraulichen Informationstyps zu suchen, den Sie (oder ein anderer Administrator) für Ihre Organisation erstellt haben. Sie können die Spalte **Publisher** auf der Seite **vertrauliche Informationstypen** im Security #a0 Compliance Center (oder in der **Publisher** -Eigenschaft in PowerShell) verwenden, um zwischen integrierten und benutzerdefinierten Typen vertraulicher Informationen zu unterscheiden. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md).
  
Weitere Informationen zum Erstellen von Abfragen mithilfe der `SensitiveType` -Eigenschaft finden Sie unter [Formular Abfragen zum Auffinden vertraulicher Daten, die auf Websites gespeichert](form-a-query-to-find-sensitive-data-stored-on-sites.md)sind.

> [!NOTE]
> Sie können keine vertraulichen Datentypen und `SensitiveType` die Search-Eigenschaft verwenden, um nach vertraulichen Daten zu suchen, die sich in Exchange Online Postfächern bei-Rest befinden. Sie können jedoch Datenverlust Verhinderung (DLP)-Richtlinien verwenden, um vertrauliche e-Mail-Daten während der Übertragung zu schützen. Weitere Informationen finden Sie unter [Übersicht über Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) und [Suchen nach personenbezogenen Daten](search-for-and-find-personal-data.md).
  
## <a name="search-operators"></a>Suchoperatoren

Boolesche Suchoperatoren wie **and**, **or**und **Not**helfen Ihnen bei der Definition präziser Suchvorgänge, indem Sie bestimmte Wörter in die Suchabfrage einbeziehen oder ausschließen. Andere Techniken, beispielsweise die Verwendung von eigenschaftsoperatoren \>(beispielsweise = oder..), Anführungszeichen, Klammern und Platzhalter, unterstützen Sie beim Verfeinern einer Suchabfrage. In der folgenden Tabelle sind die Operatoren aufgeführt, die Sie zum einschränken oder Erweitern von Suchergebnissen verwenden können. 
  
|**Operator**|**Verwendung**|**Beschreibung**|
|:-----|:-----|:-----|
|AND|Wort1 AND Wort2|Gibt Elemente zurück, die alle angegebenen Schlüsselwörter oder `property:value` Ausdrücke enthalten. Beispielsweise `from:"Ann Beebe" AND subject:northwind` würden alle von Ann Beebe gesendeten Nachrichten zurückgegeben, die das Wort Northwind in der Betreffzeile enthalten. <sup>2</sup>|
|+|Suchbegriff1 + Wort2 + Wort3|Gibt die Elemente zurück, die  *entweder*  `keyword2` oder  `keyword3` *enthalten und*  , die ebenfalls  `keyword1` enthalten. Damit entspricht dieses Beispiel der Abfrage  `(keyword2 OR keyword3) AND keyword1`.  <br/> Die Abfrage `keyword1 + keyword2` (mit einem Leerzeichen nach **+** dem Symbol) ist nicht identisch mit dem **and-** Operator. Diese Abfrage wäre gleichbedeutend mit  `"keyword1 + keyword2"` und gibt Elemente mit dem exakten Ausdruck  `"keyword1 + keyword2"` zurück.|
|OR|Wort1 OR Wort2|Gibt Elemente zurück, die einen oder mehrere der angegebenen Schlüsselwörter `property:value` oder Ausdrücke enthalten. <sup>2</sup>|
|NOT|Wort1 NOT Wort2  <br/> NOT Von:"Ann Beebe"  <br/> Nicht freundlich: Chat|Schließt Elemente an, die durch ein Schlüsselwort `property:value` oder einen Ausdruck angegeben werden. Im zweiten Beispiel werden von Ann Beebe gesendete Nachrichten ausgeschlossen. Das dritte Beispiel schließt alle Chat Unterhaltungen aus, beispielsweise Skype for Business Unterhaltungen, die im Postfachordner für den Unterhaltungsverlauf gespeichert werden. <sup>2</sup>|
|-|Wort1 - Wort2|Identisch mit dem Operator **NOT**. Diese Abfrage gibt also Elemente zurück, `keyword1` die Elemente enthalten, die enthalten `keyword2`und diese ausschließen.|
|NEAR|Wort1 NEAR(n) Wort2|Gibt Elemente mit Wörtern zurück, die sich nah sind, wobei "n" der Anzahl der Wörter entspricht, die den Abstand zwischen den gesuchten Wörtern darstellen. Gibt beispielsweise `best NEAR(5) worst` ein beliebiges Element zurück, bei dem das Wort "Worst" innerhalb von fünf Wörtern von "Best" ist. Wenn keine Anzahl angegeben wird, wird der Standardabstand von 8 Wörtern verwendet. <sup>2</sup>|
|ONEAR|Wort1 NEAR(n) Wort2|Ähnelt **near**, gibt jedoch Elemente mit Wörtern zurück, die sich in der angegebenen Reihenfolge nahe beieinander befinden. `best ONEAR(5) worst` Gibt beispielsweise ein beliebiges Element zurück, bei dem das Wort "am besten" vor dem Wort "Worst" auftritt und sich die beiden Wörter innerhalb von fünf Wörtern voneinander befinden. Wenn keine Anzahl angegeben wird, wird der Standardabstand von 8 Wörtern verwendet. <sup>2</sup> <br/> **Hinweis:** Der **ONEAR** -Operator wird beim Durchsuchen von Postfächern nicht unterstützt. Dies funktioniert nur beim Durchsuchen von SharePoint-und OneDrive für Unternehmen-Websites. Wenn Sie Postfächer und Websites in derselben Suche durchsuchen und die Abfrage den **ONEAR** -Operator enthält, gibt die Suche Postfachelemente zurück, als würden Sie den **near** -Operator verwenden. Mit anderen Worten: die Suche gibt Elemente zurück, in denen sich die angegebenen Wörter unabhängig von der Reihenfolge, in der die Wörter auftreten, nahe beieinander befinden.|
|:|Eigenschaftswert|Der Doppelpunkt (:) in der `property:value` Syntax gibt an, dass der Wert der Eigenschaft, nach der gesucht wird, den angegebenen Wert enthält. `recipients:garthf@contoso.com` Gibt beispielsweise alle an garthf@contoso.com gesendeten Nachrichten zurück.|
|=|Eigenschaft = Wert|Identisch mit dem **:** -Operator.|
|\<|Eigenschaft\<Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, kleiner ist als der angegebene Wert.<sup>1</sup>|
|\>|Eigenschaft\>Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer ist als der angegebene Wert.<sup>1</sup>|
|\<=|Eigenschaft\<=Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, kleiner gleich dem angegebenen Wert ist.<sup>1</sup>|
|\>=|Eigenschaft\>=Wert|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer gleich dem angegebenen Wert ist.<sup>1</sup>|
|..|Eigenschaft: value1.. Wert2|Zeigt an, dass die Eigenschaft, nach der gesucht wird, größer gleich Wert1 und kleiner gleich Wert2 ist.<sup>1</sup>|
|"  "|"fair Value"  <br/> Betreff:"Vierteljährliche Finanzdaten"|Verwenden Sie doppelte Anführungszeichen (""), um nach einem genauen Ausdruck oder Begriff `property:value` in Schlüsselwort-und Suchabfragen zu suchen.|
|\*|cat\*  <br/> Betreff:set\*|Präfix-Platzhaltersuchen (wobei das Sternchen am Ende eines Wortes eingefügt wird) entsprechen NULL oder mehr Zeichen in Schlüsselwörtern oder `property:value` Abfragen. Beispielsweise werden `title:set*` Dokumente zurückgegeben, die das Wort Set, das Setup und die Einstellung (und andere Wörter, die mit "Set" beginnen) im Dokumenttitel enthalten.  <br/><br/> **Hinweis:** Sie können nur Präfix-Platzhaltersuchen verwenden; beispielsweise **Cat\* ** oder **Sets\***. Suffix-suchen (**\*Cat** ), Infix-suchen (**\*c t**) und Teil Zeichenfolgensuchen (**\*Cat\***) werden nicht unterstützt.|
|(  )| (fair OR frei) AND (Von:contoso.com)  <br/> (IPO OR Initiale) AND (Aktien OR Anteile)  <br/> (Vierteljährliche Finanzdaten)|Mit Klammern werden Boolesche Ausdrücke,  `property:value`-Elemente und Schlüsselwörter gruppiert.  `(quarterly financials)` gibt z. B. Elemente zurück, die die Wörter "Vierteljährliche" und "Finanzdaten" enthalten.  |
|||||
   
> [!NOTE]
> <sup>1</sup> verwenden Sie diesen Operator für Eigenschaften, die Datums-oder numerische Werte aufweisen.<br/> <sup>2</sup> boolesche Suchoperatoren müssen groß geschrieben sein; Beispiel: **und**. Wenn Sie einen Kleinbuchstaben-Operator wie **und**verwenden, wird er als Schlüsselwort in der Suchabfrage behandelt. 
  
## <a name="search-conditions"></a>Suchbedingungen

Sie können einer Suchabfrage Bedingungen hinzufügen, um eine Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird.
  
[Bedingungen für allgemeine Eigenschaften ](#conditions-for-common-properties)

[Bedingungen für E-Mail-Eigenschaften](#conditions-for-mail-properties)

[Bedingungen für Dokumenteigenschaften](#conditions-for-document-properties)

[Mit Bedingungen verwendete Operatoren](#operators-used-with-conditions)

[Richtlinien für die Verwendung von Bedingungen](#guidelines-for-using-conditions)

[Beispiele](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Bedingungen für allgemeine Eigenschaften 

Erstellen Sie eine Bedingung mithilfe allgemeiner Eigenschaften beim Durchsuchen von Postfächern und Websites in derselben Suche. In der folgenden Tabelle sind die verfügbaren Eigenschaften aufgeführt, die beim Hinzufügen einer Bedingung verwendet werden sollen.
  
|**Bedingung**|**Beschreibung**|
|:-----|:-----|
|Datum|Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde.|
|Absender/Autor|Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Für Dokumente die im Feld Autor zitierte Person aus Office-Dokumenten. Sie können mehr als einen Namen eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den **or** -Operator logisch miteinander verbunden.|
|Größe (in Byte)|Für e-Mail und Dokumente die Größe des Elements (in Byte).|
|Betreff/Titel|Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Für Dokumente der Titel des Dokuments. Wie bereits erläutert, ist die Title-Eigenschaft in Microsoft Office Dokumenten angegebene Metadaten. Sie können den Namen von mehr als einem Betreff/Titel eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den **or** -Operator logisch miteinander verbunden.|
|Konformitäts Bezeichnung|Für e-Mails und Dokumente werden Aufbewahrungs Bezeichnungen, die Nachrichten und Dokumenten automatisch durch Bezeichnungsrichtlinien oder Aufbewahrungs Bezeichnungen zugewiesen wurden, die manuell von Benutzern zugewiesen wurden. Aufbewahrungs Bezeichnungen werden verwendet, um e-Mails und Dokumente für die Informationssteuerung zu klassifizieren und Aufbewahrungsregeln basierend auf den von der Bezeichnung definierten Einstellungen zu erzwingen. Sie können einen Teil des Namens der Aufbewahrungs Bezeichnung eingeben und einen Platzhalter verwenden oder den vollständigen Namen der Bezeichnung eingeben. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungs Bezeichnungen](labels.md).|
|||
  
### <a name="conditions-for-mail-properties"></a>Bedingungen für E-Mail-Eigenschaften

Erstellen Sie beim Durchsuchen von Postfächern oder öffentlichen Ordnern eine Bedingung mithilfe von e-Mail-Eigenschaften. In der folgenden Tabelle werden die e-Mail-Eigenschaften aufgelistet, die Sie für eine Bedingung verwenden können. Diese Eigenschaften sind eine Teilmenge der e-Mail-Eigenschaften, die zuvor beschrieben wurden. Diese Beschreibungen werden zur Vereinfachung wiederholt.
  
|**Bedingung**|**Beschreibung**|
|:-----|:-----|
|Nachrichten Art| Der Nachrichtentyp, nach dem gesucht wird. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Art“. Mögliche Werte:  <br/><br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  verläuft  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail|
|Participants|Alle Personen Felder in einer e-Mail-Nachricht. Diese Felder sind von, in, CC und Bcc.|
|Typ|Die Nachrichtenklassen Eigenschaft für ein e-Mail-Element. Dies ist die gleiche Eigenschaft wie die ItemClass-e-Mail-Eigenschaft. Es handelt sich auch um eine mehrwertige Bedingung. Wenn Sie also mehrere Nachrichtenklassen auswählen möchten, halten Sie die **STRG** -Taste gedrückt, und klicken Sie dann in der Dropdownliste auf mindestens zwei Nachrichtenklassen, die Sie der Bedingung hinzufügen möchten. Jede Nachrichtenklasse, die Sie in der Liste auswählen, wird in der entsprechenden Suchabfrage logisch durch den **or** -Operator verbunden.  <br/> Eine Liste der Nachrichtenklassen (und der zugehörigen Nachrichtenklassen-ID), die von Exchange verwendet werden und die Sie in der **Nachrichtenklassen** Liste auswählen können, finden Sie unter [Elementtypen und Nachrichtenklassen](https://go.microsoft.com/fwlink/?linkid=848143).|
|Empfangen|Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Empfangen“.|
|Empfänger|Alle Empfängerfelder in einer e-Mail-Nachricht. Diese Felder sind to, CC und Bcc.|
|Absender|Der Absender einer E-Mail-Nachricht.|
|Gesendet|Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Gesendet“.|
|Betreff|Der Text in der Betreffzeile einer E-Mail.|
|An|Der Empfänger einer e-Mail-Nachricht im Feld an.|
|||
  
### <a name="conditions-for-document-properties"></a>Bedingungen für Dokumenteigenschaften

Erstellen Sie eine Bedingung mithilfe von Dokumenteigenschaften beim Suchen nach Dokumenten auf SharePoint und OneDrive für Unternehmen Websites. In der folgenden Tabelle sind die Dokumenteigenschaften aufgeführt, die Sie für eine Bedingung verwenden können. Diese Eigenschaften sind eine Teilmenge der zuvor beschriebenen Websiteeigenschaften. Diese Beschreibungen werden zur Vereinfachung wiederholt.
  
|**Bedingung**|**Beschreibung**|
|:-----|:-----|
|Ursprung|Das Feld Autor aus Office-Dokumenten, das bleibt, wenn ein Dokument kopiert wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die e-Mails an eine andere Person weitergeben, die es dann in SharePoint hoch lädt, behält das Dokument weiterhin den ursprünglichen Autor bei.|
|Position|Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Office-Dokumenten angegeben sind. Er unterscheidet sich von dem Dateinamen des Dokuments.|
|Erstellt|Das Datum, an dem ein Dokument erstellt wird.|
|Zuletzt geändert|Das Datum, an dem ein Dokument zuletzt geändert wurde.|
|Dateityp|Die Erweiterung einer Datei; beispielsweise docx, 1, PPTX oder xlsx. Dies ist die gleiche Eigenschaft wie die FileExtension-Website Eigenschaft.|
|||
  
### <a name="operators-used-with-conditions"></a>Mit Bedingungen verwendete Operatoren

Beim Hinzufügen einer Bedingung können Sie einen Operator auswählen, der für den Typ der Eigenschaft für die Bedingung relevant ist. Die folgende Tabelle enthält die mit Bedingungen verwendeten Operatoren und die dazugehörigen Entsprechungen, die in der Suchabfrage verwendet werden.
  
|**Operator**|**Entsprechung in der Abfrage**|**Beschreibung**|
|:-----|:-----|:-----|
|Nach|`property>date`|Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die nach dem angegebenen Datum gesendet, empfangen oder geändert wurden. |
|Vor|`property<date`|Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die vor dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
|Zwischen|`date..date`|Wird mit Datums- und Größenbedingungen verwendet. Bei Verwendung mit einer Datumsbedingung werden Elemente zurückgegeben, die innerhalb des angegebenen Datumsbereichs gesendet, empfangen oder geändert wurden. Bei Verwendung mit einer Größenbedingung werden Elemente zurückgegeben, deren Größe innerhalb des angegebenen Bereichs liegt.|
|Contains any of|`(property:value) OR (property:value)`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die mindestens einen Teil der angegebenen Zeichenfolgenwerte enthalten.|
|Doesn't contain any of|`-property:value`  <br/> `NOT property:value`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die keinen Teil des angegebenen Zeichenfolgenwerts enthalten.|
|Doesn't equal any of|`-property=value`  <br/> `NOT property=value`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die die angegebene Zeichenfolge nicht enthalten.|
|Gleich|`size=value`|Gibt Elemente zurück, die der angegebenen Größe entsprechen. <sup>1</sup>|
|Equals any of|`(property=value) OR (property=value)`|Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die genau den angegebenen Zeichenfolgenwerten entsprechen.|
|Größer|`size>value`|Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer als der angegebene Wert ist. <sup>1</sup>|
|Greater or equal|`size>=value`|Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer oder gleich dem angegebenen Wert ist. <sup>1</sup>|
|Weniger|`size<value`|Gibt Elemente zurück, die größer oder gleich dem angegebenen Wert sind. <sup>1</sup>|
|Less or equal|`size<=value`|Gibt Elemente zurück, die größer oder gleich dem angegebenen Wert sind. <sup>1</sup>|
|Not equal|`size<>value`|Gibt Elemente zurück, die nicht der angegebenen Größe entsprechen. <sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> dieser Operator steht nur für Bedingungen zur Verfügung, die die Size-Eigenschaft verwenden. 
  
### <a name="guidelines-for-using-conditions"></a>Richtlinien für die Verwendung von Bedingungen

Beachten Sie Folgendes bei der Verwendung von Suchbedingungen:
  
- Eine Bedingung ist logisch mit der Schlüsselwortabfrage (im Feld „Schlüsselwort“ angegeben) durch den **AND**-Operator verknüpft. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können Sie Ihre Ergebnisse mit Bedingungen eingrenzen. 
    
- Wenn Sie einer Suchabfrage zwei oder mehr eindeutige Bedingungen hinzufügen (Bedingungen, die unterschiedliche Eigenschaften angeben), werden diese Bedingungen durch den **and-** Operator logisch miteinander verbunden. Das bedeutet, dass nur Elemente zurückgegeben werden, die neben der Schlüsselwortabfrage allen Bedingungen entsprechen. 
    
- Wenn Sie mehr als eine Bedingung für die gleiche Eigenschaft hinzufügen, werden diese Bedingungen mit dem **OR**-Operator logisch verknüpft. Das bedeutet, dass Elemente zurückgegeben werden, die der Schlüsselwortabfrage entsprechen und eine der Bedingungen erfüllen. Bedingungen, die sich auf die gleichen Eigenschaften beziehen, werden mit dem **OR**-Operator und die eindeutigen Bedingungen werden mit dem **AND**-Operator miteinander verknüpft. 
    
- Wenn Sie mehrere Werte (durch Kommas oder Semikolons getrennt) zu einer einzelnen Bedingung hinzufügen, werden diese Werte durch den **or** -Operator miteinander verbunden. Das bedeutet, es werden Elemente zurückgegeben, die einen der angegebenen Werte für die Eigenschaft in der Bedingung enthalten. 
    
- Die Suchabfrage, die mithilfe des Felds Schlüsselwörter und der Bedingungen erstellt wird, wird auf der Seite **Suche** im Detailbereich für die ausgewählte Suche angezeigt. In einer Abfrage gibt alles rechts neben der Notation `(c:c)` Bedingungen an, die der Abfrage hinzugefügt werden. 
    
- Mit Bedingungen werden der Suchabfrage nur Eigenschaften hinzugefügt, keine Operatoren. Aus diesem Grund werden in der im Detailbereich angezeigten Abfrage keine Operatoren rechts von der `(c:c)` Notation angezeigt. KQL fügt die logischen Operatoren (entsprechend den bereits erläuterten Regeln) beim Ausführen der Abfrage hinzu. 
    
- Sie können das Drag & Drop-Steuerelement verwenden, um die Reihenfolge der Bedingungen neu zu befolgen. Klicken Sie auf das Steuerelement für eine Bedingung, und nach oben oder unten.
    
- Wie bereits beschrieben können bei einigen Bedingungseigenschaften mehrere Werte eingegeben werden. Diese Werte werden mit **OR**-Operator logisch verknüpft. Das Ergebnis ist das gleiche wie beim Verwenden mehrerer Instanzen der gleichen Bedingung, wobei jede jeweils einen einzelnen Wert aufweist. Die folgenden Abbildungen zeigen ein Beispiel für eine einzelne Bedingung mit mehreren Werten und ein Beispiel für mehrere Bedingungen (für dieselbe Eigenschaft) mit einem einzelnen Wert. Beide Beispiele ergeben dieselbe Abfrage:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine bestimmte Bedingung erfüllt werden muss, verwenden Sie für jede Bedingung separate Regeln. Wenn Sie Nachrichten mit Anlagen und Nachrichten mit Inhalt, der einem Muster entspricht, z. B. die gleichen Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. Sie können eine Regel problemlos kopieren.](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Mehrere Suchkriterien für die gleiche Eigenschaft](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> Wenn für eine Bedingung mehrere Werte zulässig sind, wird empfohlen, eine einzelne Bedingung mit mehreren Werten (durch Kommas oder Semikolons getrennt) zu verwenden. Auf diese Weise können Sie leichter sicherstellen, dass Sie die gewünschte Abfragelogik erhalten. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Beispiele

Die folgenden Beispiele zeigen die GUI-basierte Version einer Suchabfrage mit Bedingungen, die Suchabfrage Syntax, die im Detailbereich der ausgewählten Suche (die auch vom Cmdlet **Get-ComplianceSearch** zurückgegeben wird) und die Logik der entsprechenden KQL-Abfrage angezeigt wird. 
  
#### <a name="example-1"></a>Beispiel 1

In diesem Beispiel werden Dokumente in SharePoint und OneDrive für Unternehmen Websites zurückgegeben, die eine Kreditkartennummer enthalten und zuletzt vor dem 1. Januar 2016 geändert wurden.
  
 **GUI**
  
![Erstes Beispiel für Suchbedingungen](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Suchabfragesyntax**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **Suchabfragelogik**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>Beispiel 2

In diesem Beispiel werden e-Mail-Elemente oder Dokumente zurückgegeben, die das Stichwort "Report" enthalten, die vor dem 1. April 2105 gesendet oder erstellt wurden und die das Wort "Northwind" im Feld Betreff von e-Mail-Nachrichten oder in der Eigenschaft title von Dokumenten enthalten. Die Abfrage schließt Webseiten aus, die den anderen Suchkriterien entsprechen.
  
 **GUI**
  
![Zweites Beispiel für Suchbedingungen](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Suchabfragesyntax**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **Suchabfragelogik**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Beispiel 3

In diesem Beispiel werden e-Mail-Nachrichten oder Kalender Besprechungen zurückgegeben, die zwischen 12/1/2016 und 11/30/2016 gesendet wurden und die Wörter enthalten, die mit "Phone" oder "Smartphone" beginnen.
  
 **GUI**
  
![Drittes Beispiel für Suchbedingungen](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Suchabfragesyntax**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Suchabfragelogik**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>Suchen nach Websiteinhalten, die für externe Benutzer freigegeben sind

Sie können auch das Feature für die Inhaltssuche im Security #a0 Compliance Center verwenden, um nach Dokumenten zu suchen, die in SharePoint gespeichert sind, und OneDrive für Unternehmen Websites, die für Personen außerhalb Ihrer Organisation freigegeben wurden. Dies kann Ihnen helfen, vertrauliche oder proprietäre Informationen zu identifizieren, die außerhalb Ihrer Organisation freigegeben werden. Sie können dies tun, indem Sie `ViewableByExternalUsers` die-Eigenschaft in einer Stichwortabfrage verwenden. Diese Eigenschaft gibt Dokumente oder Websites zurück, die für externe Benutzer freigegeben wurden, indem Sie eine der folgenden Freigabemethoden verwenden: 
  
- Eine Freigabeeinladung, bei der sich Benutzer als authentifizierter Benutzer bei Ihrer Organisation anmelden müssen.
    
- Einen anonymen Gast-Link, mit dem jeder, der über diesen Link verfügt, auf die Ressource zugreifen kann, ohne authentifiziert werden zu müssen.
    
Im Folgenden finden Sie einige Beispiele:
  
- Die Abfrage `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` gibt alle Elemente zurück, die für Personen außerhalb Ihrer Organisation freigegeben wurden und eine Kreditkartennummer enthalten. 
    
- Die Abfrage `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` gibt eine Liste von Dokumenten auf allen Teamwebsites in der Organisation zurück, die für externe Benutzer freigegeben wurden. 
    
> [!TIP]
> Eine Suchabfrage wie `ViewableByExternalUsers:true AND ContentType:document` möglicherweise eine Vielzahl von ASPX-Dateien in den Suchergebnissen zurück. Um diese (oder andere Dateitypen) zu eliminieren, können Sie die `FileExtension` -Eigenschaft verwenden, um bestimmte Dateitypen auszuschließen. zum Beispiel `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
Was wird als Inhalt betrachtet, der für Personen außerhalb Ihrer Organisation freigegeben wird? Dokumente in SharePoint-und OneDrive für Unternehmen-Websites Ihrer Organisation, die durch Senden einer Freigabeeinladung oder an öffentlichen Speicherorten freigegeben werden. Die folgenden Benutzeraktivitäten führen beispielsweise zu Inhalten, die von externen Benutzern angezeigt werden können:
  
- Ein Benutzer teilt eine Datei oder einen Ordner für eine Person außerhalb Ihrer Organisation.
    
- Ein Benutzer erstellt und sendet einen Link zu einer freigegebenen Datei an eine Person außerhalb Ihrer Organisation. Mit diesem Link kann der externe Benutzer die Datei anzeigen (oder bearbeiten).
    
- Ein Benutzer sendet eine Freigabeeinladung oder einen Gast Link an eine Person außerhalb Ihrer Organisation, um eine freigegebene Datei anzuzeigen (oder zu bearbeiten).
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Probleme bei Verwendung der ViewableByExternalUsers-Eigenschaft

Während die `ViewableByExternalUsers` -Eigenschaft den Status darstellt, ob ein Dokument oder eine Website für externe Benutzer freigegeben wird, gibt es einige Vorbehalte gegenüber dem, was diese Eigenschaft ausführt und nicht reflektiert. In den folgenden Szenarien wird der Wert der `ViewableByExternalUsers` Eigenschaft nicht aktualisiert, und die Ergebnisse einer Inhalts Suchabfrage, die diese Eigenschaft verwendet, sind möglicherweise ungenau. 
  
- Änderungen an Freigaberichtlinien, wie das Deaktivieren der externen Freigabe für eine Website oder für die Organisation. Die-Eigenschaft zeigt weiterhin freigegebene Dokumente als extern zugänglich an, obwohl der externe Zugriff möglicherweise widerrufen wurde.
    
- Änderungen an Gruppenmitgliedschaften, wie das Hinzufügen oder Entfernen externer Benutzer zu Office 365 Gruppen oder Office 365 Sicherheitsgruppen. Die Eigenschaft wird nicht automatisch für Elemente aktualisiert, auf die die Gruppe Zugriff hat.
    
- Senden von Freigabeeinladungen an externe Benutzer, bei denen der Empfänger die Einladung nicht angenommen hat und daher noch nicht auf den Inhalt zugreifen kann.
    
In diesen Szenarien gibt die `ViewableByExternalUsers` Eigenschaft den aktuellen Freigabestatus erst wieder, wenn die Website oder Dokumentbibliothek neu gecrawlt und neu indiziert wurde. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Suchen nach Websiteinhalten, die in Ihrer Organisation freigegeben sind

Wie bereits erläutert, können Sie die `SharedWithUsersOWSUser` -Eigenschaft verwenden, um nach Dokumenten zu suchen, die von Personen in Ihrer Organisation gemeinsam genutzt wurden. Wenn eine Person eine Datei (oder einen Ordner) mit einem anderen Benutzer in Ihrer Organisation freigibt, wird auf der Seite **gemeinsam genutzte** Dateien im OneDrive für Unternehmen Konto der Person, für die die Datei freigegeben wurde, ein Link zur freigegebenen Datei angezeigt. Wenn Sie beispielsweise nach den Dokumenten suchen möchten, die für Sara Davis freigegeben wurden, können Sie die `SharedWithUsersOWSUser:"sarad@contoso.com"`Abfrage verwenden. Wenn Sie die Ergebnisse dieser Suche exportieren, werden die ursprünglichen Dokumente (am Speicherort des Inhalts der Person, die die Dokumente mit Sara freigegeben hat) heruntergeladen.
  
Dokumente müssen explizit für einen bestimmten Benutzer freigegeben werden, der bei Verwendung der `SharedWithUsersOWSUser` Eigenschaft in Suchergebnissen zurückgegeben werden soll. Wenn beispielsweise eine Person ein Dokument in Ihrem OneDrive-Konto freigibt, haben Sie die Möglichkeit, Sie für jeden freizugeben (innerhalb oder außerhalb der Organisation), Sie nur für Personen innerhalb der Organisation freizugeben oder Sie für eine bestimmte Person freizugeben. Hier ist ein Screenshot des Fensters " **Freigeben** " in OneDrive, in dem die drei Freigabeoptionen angezeigt werden. 
  
![Nur für bestimmte Personen freigegebene Dateien werden von einer Suchabfrage zurückgegeben, die die SharedWithUsersOWSUser-Eigenschaft verwendet.](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Nur Dokumente, die mit der dritten Option (für **bestimmte Personen**freigegeben) freigegeben werden, werden von einer Suchabfrage zurückgegeben `SharedWithUsersOWSUser` , die die Eigenschaft verwendet. 

## <a name="searching-for-skype-for-business-conversations"></a>Suchen nach Skype for Business Unterhaltungen

Sie können die folgende Stichwortabfrage verwenden, um in Skype for Business Unterhaltungen gezielt nach Inhalten zu suchen:

```powershell
kind:im
```

Die vorherige Suchabfrage gibt auch Chats von Microsoft Teams zurück. Um dies zu verhindern, können Sie die Suchergebnisse eingrenzen, um nur Skype for Business Unterhaltungen mit der folgenden Stichwortabfrage einzuschließen:

```powershell
kind:im AND subject:conversation
```

Die vorherige Stichwortabfrage schließt Chats in Microsoft Teams aus, da Skype for Business Unterhaltungen als e-Mail-Nachrichten mit einer Betreffzeile gespeichert werden, die mit dem Wort "Conversation" beginnt.

Verwenden Sie die folgende Stichwortabfrage, um nach Skype for Business Unterhaltungen zu suchen, die in einem bestimmten Datumsbereich aufgetreten sind:

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>Tipps und Tricks für die Suche

- Bei Stichwort suchen wird die Groß-/Kleinschreibung nicht beachtet. Beispielsweise geben **katze** und **KATZE** dieselben Ergebnisse zurück. 
    
- Die booleschen Operatoren **and**, **or**, **Not**, **near**und **ONEAR** müssen groß geschrieben sein. 
    
- A space between two keywords or two  `property:value` expressions is the same as using **AND**. `from:"Sara Davis" subject:reorganization` Gibt beispielsweise alle von Sara Davis gesendeten Nachrichten zurück, die das Wort Reorganization in der Betreffzeile enthalten. 
    
- Verwenden Sie eine Syntax, `property:value` die mit dem Format übereinstimmt. Bei Werten wird die Groß-/Kleinschreibung nicht beachtet, und nach dem Operator kann kein Leerzeichen vorhanden sein. Wenn ein Leerzeichen vorhanden ist, handelt es sich bei dem vorgesehenen Wert um eine Volltextsuche. Beispielsweise `to: pilarp` wird nach "pilarp" als Schlüsselwort gesucht, statt an Nachrichten, die an pilarp gesendet wurden. 
    
- Wenn Sie nach einer Empfängereigenschaft wie An, Von, Cc oder Empfänger suchen, können Sie eine SMTP-Adresse, einen Alias oder einen Anzeigenamen verwenden, um einen Empfänger anzugeben. Sie können z. B. pilarp@contoso.com, pilarp oder "Pilar Pinilla" verwenden.
    
- Sie können nur Präfix-Platzhaltersuchen verwenden; beispielsweise **Cat\* ** oder **Sets\***. Suffix-suchen (**\*Cat**), Infix-suchen (**\*c t**) und Teil Zeichenfolgensuchen (**\*Cat\***) werden nicht unterstützt. 
    
- Verwenden Sie beim Durchsuchen einer Eigenschaft doppelte Anführungszeichen (""), wenn der Suchwert aus mehreren Wörtern besteht. Gibt Beispiels `subject:budget Q1` Weise Nachrichten zurück, die das **Budget** in der Betreffzeile enthalten und das **Q1** an einer beliebigen Stelle in der Nachricht oder in einer der Nachrichteneigenschaften enthalten. Using `subject:"budget Q1"` gibt alle Nachrichten zurück, die das **Budget Q1** an beliebiger Position in der Betreffzeile enthalten. 
    
- Wenn Sie Inhalte mit einem bestimmten Eigenschaftswert in den Suchergebnissen ausschließen möchten, fügen Sie ein Minuszeichen (-) vor dem Namen der Eigenschaft hinzu. `-from:"Sara Davis"` Schließt beispielsweise alle von Sara Davis gesendeten Nachrichten aus.

- Einige Sonderzeichen sind nicht im Suchindex enthalten und sind daher nicht durchsuchbar, dazu gehören die Operatoren für die Suche (+-=:) und die folgenden Zeichen, die entweder durch ein $Null ersetzt werden oder Fehler verursachen können, wenn nachgesucht wird! @ #% ^ &; _ / ?

- Sie können Elemente auf der Grundlage des Nachrichtentyps exportieren. Um beispielsweise Skype-Unterhaltungen und-Chats in Microsoft Teams zu exportieren `kind:im`, verwenden Sie die Syntax. Wenn Sie nur e-Mail-Nachrichten `kind:email`zurückgeben möchten, verwenden Sie. Um Chats, Besprechungen und Anrufe in Microsoft Teams zurückzugeben, `kind:microsoftteams`verwenden Sie.
