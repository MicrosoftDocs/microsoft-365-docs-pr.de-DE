---
title: Detaillierte Eigenschaften im Überwachungsprotokoll
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
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Dieser Artikel enthält eine Beschreibung der zusätzlichen Eigenschaften, die beim Exportieren von Ergebnissen für einen Office 365 Überwachungsprotokolleintrag enthalten sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 250db03e7d330ed013909925b44f8d9843f1197d
ms.sourcegitcommit: 5480982967a90ca3060a59676a6b29155f2de861
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49350701"
---
# <a name="detailed-properties-in-the-audit-log"></a>Detaillierte Eigenschaften im Überwachungsprotokoll

Wenn Sie die Ergebnisse einer Überwachungsprotokoll Suche aus dem Security & Compliance Center exportieren, haben Sie die Möglichkeit, alle Ergebnisse herunterzuladen, die Ihren Suchkriterien entsprechen. Wählen Sie dazu **Export Ergebnisse** \> **alle Ergebnisse herunterladen** auf der Seite **Überwachungsprotokoll Suche** aus. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).
  
 Wenn Sie alle Ergebnisse für eine Überwachungsprotokoll Suche exportieren, werden die Rohdaten aus dem vereinheitlichten Überwachungsprotokoll in eine CSV-Datei (Comma-Separated Value) kopiert, die auf den lokalen Computer heruntergeladen wird. Diese Datei enthält zusätzliche Informationen aus jedem Überwachungseintrag in einer Spalte mit dem Namen **Auditdata**. Diese Spalte enthält eine mehrwertige Eigenschaft für mehrere Eigenschaften aus dem Überwachungsprotokolleintrag. Jedes der **Eigenschaft: Wert** -Paare in dieser mehrwertigen Eigenschaft werden durch ein Komma getrennt. 
  
In der folgenden Tabelle werden die Eigenschaften beschrieben, die (je nach Dienst, in dem ein Ereignis auftritt) in der **Auditdata** -Spalte mit mehreren Eigenschaften enthalten sind. Der **Office 365 Dienst mit dieser Eigenschafts** Spalte gibt den Dienst und den Aktivitätstyp (Benutzer oder Administrator) an, der die Eigenschaft enthält. Ausführlichere Informationen zu diesen Eigenschaften oder zu Eigenschaften, die in diesem Thema möglicherweise nicht aufgeführt sind, finden Sie unter [Management Activity API Schema](https://go.microsoft.com/fwlink/p/?LinkId=717993).
  
> [!TIP]
> Sie können das JSON-Transformations Feature in Power Query in Excel verwenden, um die **Auditdata** -Spalte in mehrere Spalten aufzuteilen, sodass jede Eigenschaft eine eigene Spalte aufweist. Dadurch können Sie nach einer oder mehreren dieser Eigenschaften sortieren und filtern. Weitere Informationen hierzu finden Sie unter [exportieren, konfigurieren und Anzeigen von Überwachungsprotokolldaten Sätzen](export-view-audit-log-records.md). 
  
|**Eigenschaft**|**Beschreibung**|**Microsoft 365-Dienst mit dieser Eigenschaft**|
|:-----|:-----|:-----|
|Akteur|Das Benutzer-oder Dienstkonto, das die Aktion ausgeführt hat.|Azure Active Directory|
|AddOnName|Der Name eines Add-ons, das in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Der Typ von Add-ons in Microsoft Teams ist ein bot, ein Konnektor oder ein Tab.|Microsoft Teams|
|AddOnType|Der Typ eines Add-ons, das in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Die folgenden Werte geben den Typ des Add-ons an.  <br/> **1** – gibt einen bot an.<br/> **2** – gibt einen Konnektor an.<br/> **3** -gibt eine Registerkarte an.|Microsoft Teams|
|AzureActiveDirectoryEventType|Der Typ des Azure Active Directory-Ereignisses. Die folgenden Werte geben den Typ des Ereignisses an.  <br/> **0** -gibt ein Konto Anmeldeereignis an.<br/> **1** – gibt ein Azure-Anwendungs Sicherheitsereignis an.|Azure Active Directory|
|ChannelGuid|Die ID eines Microsoft Teams-Kanals. Das Team, in dem sich der Kanal befindet, wird durch die Eigenschaften **Teamname** und **TeamGuid** identifiziert.|Microsoft Teams|
|ChannelName|Der Name eines Microsoft Teams-Kanals. Das Team, in dem sich der Kanal befindet, wird durch die Eigenschaften **Teamname** und **TeamGuid** identifiziert.|Microsoft Teams|
|Client|Das Clientgerät, das Gerätebetriebssystem und der für das Anmeldeereignis verwendete Gerätebrowser (beispielsweise Nokia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Informationen zum e-Mail-Client, der zum Ausführen des Vorgangs verwendet wurde, beispielsweise eine Browserversion, Outlook-Version und Informationen zu mobilen Geräten|Exchange (Post Fach Aktivität)|
|ClientIP|Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird entweder im Format IPv4 oder im Format IPv6 angezeigt.<br/><br/> Bei einigen Diensten ist der in dieser Eigenschaft angezeigte Wert möglicherweise die IP-Adresse einer vertrauenswürdigen Anwendung (z. B. Office in den Web-Apps), die sich anstelle eines Benutzers in den Dienst einwählt, und nicht die IP-Adresse des Geräts, das von der Person, die die Aktivität ausgeführt hat, verwendet wird. <br/><br/>Für Administratoraktivitäten (oder Aktivitäten, die von einem Systemkonto ausgeführt werden) bei Azure-Active Directory bezogenen Ereignissen wird die IP-Adresse nicht protokolliert, und der Wert für die ClientIP-Eigenschaft lautet `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|Das Datum und die Uhrzeit in koordinierter Weltzeit (UTC), wann der Benutzer die Aktivität ausgeführt hat.|Alle|
|DestinationFileExtension|Der Erweiterung der Datei, die kopiert oder verschoben wurde. Diese Eigenschaft wird nur für die Aktivitäten filecopied und filemigrationed User angezeigt.|SharePoint|
|DestinationFileName|Der Name der Datei wird kopiert oder verschoben. Diese Eigenschaft wird nur für die filecopied-und fileactions-Aktionen angezeigt.|SharePoint|
|DestinationRelativeUrl|Die URL des Zielordners, in den eine Datei kopiert oder verschoben wurde. Die Kombination der Werte für die **SiteUrl**, die **DestinationRelativeURL** und die **destinationFileName** -Eigenschaft ist identisch mit dem Wert für die **objectID** -Eigenschaft, bei der es sich um den vollständigen Pfadnamen für die kopierte Datei handelt. Diese Eigenschaft wird nur für die Aktivitäten filecopied und filemigrationed User angezeigt.|SharePoint|
|EventSource|Gibt an, dass ein Ereignis in SharePoint eingetreten ist. Mögliche Werte sind **SharePoint** und **ObjectModel**.|SharePoint|
|ExternalAccess|Gibt für Exchange-Administratoraktivitäten an, ob das Cmdlet von einem Benutzer in Ihrer Organisation, von Mitarbeitern des Microsoft-Rechenzentrums oder von einem Rechenzentrum-Dienstkonto oder von einem Delegierten Administrator ausgeführt wurde. Der Wert **False** gibt an, dass das Cmdlet von einer Person in Ihrer Organisation ausgeführt wurde. Der Wert **True** gibt an, dass das Cmdlet von Mitarbeiter des Rechenzentrums, einem Rechenzentrum-Dienstkonto oder einem delegierten Administrator ausgeführt wurde.  <br/> Gibt für Exchange-Post Fach Aktivität an, ob ein Benutzer außerhalb Ihrer Organisation auf ein Postfach zugegriffen hat.|Exchange|
|ExtendedProperties|Die erweiterten Eigenschaften für ein Azure Active Directory-Ereignis.|Azure Active Directory|
|ID|Die ID des Berichts Eintrags. Die ID identifiziert den Berichtseintrag eindeutig.|Alle|
|InternalLogonType|Für die interne Verwendung reserviert.|Exchange (Post Fach Aktivität)|
|ItemType|Der Typ des Objekts, auf das zugegriffen bzw. das geändert wurde. Mögliche Werte sind **File**-, **Folder**-, **Web**-, **Site**-, **Mandanten**-und **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifiziert Anmeldefehler, die möglicherweise aufgetreten sind.|Azure Active Directory|
|LogonType|Der Typ des Postfachzugriffs. Die folgenden Werte geben den Typ des Benutzers an, der auf das Postfach zugegriffen hat.  <br/><br/> **0** – gibt einen Postfachbesitzer an.<br/> **1** – gibt einen Administrator an.<br/> **2** – gibt einen Delegaten an. <br/>**3** – gibt den Transportdienst im Microsoft-Datencenter an.<br/> **4** – gibt ein Dienstkonto im Microsoft-Datencenter an. <br/>**6** – gibt einen delegierten Administrator an.|Exchange (Post Fach Aktivität)|
|MailboxGuid|Die Exchange-GUID des Postfachs, auf das zugegriffen wurde.|Exchange (Post Fach Aktivität)|
|MailboxOwnerUPN|Die E-Mail-Adresse der Person, die das Postfach besitzt, auf das zugegriffen wurde.|Exchange (Post Fach Aktivität)|
|Members|Listet die Benutzer auf, die einem Team hinzugefügt oder daraus entfernt wurden. Die folgenden Werte geben den Rollentyp an, der dem Benutzer zugewiesen wurde.  <br/><br/> **1** – gibt die Besitzerrolle an.<br/> **2** - Gibt die Mitgliedsrolle an.<br/> **3** - Gibt die Gastrolle an. <br/><br/>Die Eigenschaft „Mitglieder“ enthält auch den Namen Ihrer Organisation und die E-Mail-Adresse des Mitglieds.|Microsoft Teams|
|ModifiedProperties (Name, Neuwert, oldValue)|Diese Eigenschaft wird für Administratorereignisse einbezogen, wie z. B. das Hinzufügen eines Benutzers als Mitglied einer Website oder der Administratorgruppe einer Websitesammlung. Die Eigenschaft enthält den Namen der Eigenschaft, die geändert wurde (beispielsweise die Websiteadministratorgruppe), den neuen Wert der geänderten Eigenschaft (beispielsweise den Benutzer, der als Websiteadministrator hinzugefügt wurde, und den vorherigen Wert des geänderten Objekts).|All (Administrator Aktivität)|
|ObjectId|Für Exchange-Verwaltungsüberwachungsprotokolle der Name des Objekts, das vom Cmdlet geändert wurde.  <br/> Für SharePoint-Aktivitäten der vollständige URL-Pfadname der Datei oder des Ordners, auf die ein Benutzer zugegriffen hat.  <br/> Für Azure AD Aktivität der Name des Benutzerkontos, das geändert wurde.|Alle|
|Vorgang|Der Name der Benutzer- oder Verwaltungsaktivität. Der Wert dieser Eigenschaft entspricht dem Wert, der in der Dropdownliste **Aktivitäten** ausgewählt wurde. Wenn **Ergebnisse für alle Aktivitäten anzeigen** ausgewählt wurde, enthält der Bericht Einträge für alle Benutzer-und Administratoraktivitäten für alle Dienste. Eine Beschreibung der Vorgänge/Aktivitäten, die im Überwachungsprotokoll protokolliert werden, finden Sie auf der Registerkarte über **wachte Aktivitäten** unter [Durchsuchen des Überwachungsprotokolls im Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> Für Exchange-Administratoraktivitäten gibt diese Eigenschaft den Namen des Cmdlets an, das ausgeführt wurde.|Alle|
|OrganizationId|Die GUID für Ihre Organisation.|Alle|
|Pfad|Der Name des Postfachordners, in dem sich die Nachricht, auf die zugegriffen wurde, befindet. Diese Eigenschaft identifiziert auch den Ordner a, in dem eine Nachricht erstellt oder kopiert/verschoben wird.|Exchange (Post Fach Aktivität)|
|Parameter|Für die Exchange-Administrator Aktivität der Name und der Wert für alle Parameter, die mit dem Cmdlet verwendet wurden, das in der Operation-Eigenschaft angegeben ist.|Exchange (Administrator Aktivität)|
|RecordType|Der vom Datensatz angegebene Vorgangstyp. Diese Eigenschaft gibt den Dienst oder das Feature an, in dem der Vorgang ausgelöst wurde. Eine Liste der Datensatztypen und der dazugehörigen Enumerationswerte (Dies ist der Wert, der in der **RecordType** -Eigenschaft in einem Überwachungseintrag angezeigt wird) finden Sie unter [Audit Log Record Type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).| 
|ResultStatus|Gibt an, ob die Aktion (in der **Operation** -Eigenschaft angegeben) erfolgreich war oder nicht.  <br/> Für die Exchange-Administrator Aktivität ist der Wert entweder **true** (erfolgreich) oder **false** (fehlerhaft).|Alle  <br/>|
|SecurityComplianceCenterEventType|Gibt an, dass es sich bei der Aktivität um ein Sicherheits & Compliance Center-Ereignis handelt. Alle Aktivitäten des Security & Compliance Center haben für diese Eigenschaft den Wert " **0** ".|Security & Compliance Center|
|SharingType|Der Typ der Freigabeberechtigungen, die dem Benutzer zugewiesen wurden, für den die Ressource freigegeben wurde. Dieser Benutzer wird in der **UserSharedWith** -Eigenschaft angegeben.|SharePoint|
|Website|Die GUID der Website, auf der sich die Datei oder der Ordner, auf die bzw. den der Benutzer zugegriffen hat, befindet.|SharePoint|
|SiteUrl|Die URL der Website, auf der sich die Datei oder der Ordner, auf die bzw. den der Benutzer zugegriffen hat, befindet.|SharePoint|
|SourceFileExtension|Die Erweiterung der Datei, auf die der Benutzer zugegriffen hat. Diese Eigenschaft ist leer, wenn das Objekt, auf das zugegriffen wurde, ein Ordner ist.|SharePoint|
|SourceFileName|Der Name der Datei oder des Ordners, auf die der Benutzer zugegriffen hat.|SharePoint|
|SourceRelativeUrl|Die URL des Ordners, der die Datei enthält, auf die der Benutzer zugegriffen hat. Die Kombination der Werte für die **SiteUrl**, die **SourceRelativeURL** und die **sourceFileName** -Eigenschaft ist identisch mit dem Wert für die **objectID** -Eigenschaft, bei der es sich um den vollständigen Pfadnamen für die Datei handelt, auf die der Benutzer zugegriffen hat.|SharePoint|
|Betreff|Die Betreffzeile der Nachricht, auf die zugegriffen wurde.|Exchange (Post Fach Aktivität)|
|TabType| Der Typ der Registerkarte, die in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Gültige Werte für diese Eigenschaft sind:  <br/><br/> **Excel-Pin** – eine Excel-Registerkarte.  <br/> **Erweiterung** – alle apps für Erstanbieter und Drittanbieter; wie Klassen Zeitplan, VSTS und Formulare.  <br/> **Notizen** – OneNote-Registerkarte.  <br/> **Pdfpin** – eine PDF-Registerkarte.  <br/> **Powerbi** -eine Power BI-Registerkarte.  <br/> **Powerpointpin** -eine PowerPoint-Registerkarte.  <br/> **Sharepointfiles** – eine SharePoint-Registerkarte.  <br/> **Webseite** – eine angeheftete Website-Registerkarte.  <br/> **Wiki-Tab** – eine wiki-Registerkarte.  <br/> **Wordpin** -eine Word-Registerkarte.|Microsoft Teams|
|Ziel|Der Benutzer, für den die Aktion (in der Eigenschaft " **Operation** " bezeichnet) ausgeführt wurde. Wenn beispielsweise ein Gastbenutzer SharePoint oder einem Microsoft-Team hinzugefügt wird, wird dieser Benutzer in dieser Eigenschaft aufgeführt.|Azure Active Directory|
|TeamGuid|Die ID eines Teams in Microsoft Teams.|Microsoft Teams|
|TeamName|Der Name eines Teams in Microsoft Teams.|Microsoft Teams|
|UserAgent|Informationen zum Browser des Benutzers. Diese Informationen werden vom Browser bereitgestellt.|SharePoint|
|UserDomain|Identitätsinformationen über die mandantenorganisation des Benutzers (Akteur), der die Aktion ausgeführt hat.|Azure Active Directory|
|UserId|Der Benutzer, der die Aktion (in der Eigenschaft " **Operation** " angegeben) ausgeführt hat, die dazu geführt hat, dass der Datensatz protokolliert wurde. Überwachungseinträge für von Systemkonten ausgeführte Aktivitäten (wie SHAREPOINT\system oder NT AUTHORITY\SYSTEM) sind ebenfalls im Überwachungsprotokoll enthalten. Ein anderer allgemeiner Wert für die UserID-Eigenschaft ist APP@SharePoint. Dies zeigt an, dass es sich bei dem "Benutzer", der die Aktivität ausgeführt hat, um eine Anwendung handelt, die in SharePoint über die erforderlichen Berechtigungen verfügt, organisationsweite Aktionen (z. B. das Durchsuchen einer SharePoint-Website oder eines OneDrive-Kontos) im Auftrag eines Benutzers, Administrators oder Diensts auszuführen. Weitere Informationen finden Sie unter [Der "app\@sharepoint"-Benutzer in Überwachungsdatensätzen](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |Alle|
|UserKey|Eine Alternative ID für den in der **UserID** -Eigenschaft angegebenen Benutzer. Beispielsweise wird diese Eigenschaft mit der eindeutigen Passport-ID (PUID) für Ereignisse aufgefüllt, die von Benutzern in SharePoint ausgeführt werden. Diese Eigenschaft kann auch denselben Wert wie die **UserID** -Eigenschaft für Ereignisse angeben, die in anderen Diensten und Ereignissen auftreten, die von Systemkonten ausgeführt werden.|Alle|
|UserSharedWith|Der Benutzer, für den eine Ressource freigegeben wurde. Diese Eigenschaft ist enthalten, wenn der Wert für die **Operation** -Eigenschaft **sharingset** ist. Dieser Benutzer wird auch in der Spalte **Shared with** im Bericht aufgeführt.|SharePoint|
|UserType|Der Typ des Benutzers, der den Vorgang ausgeführt hat. Die folgenden Werte geben den Benutzertyp an. <br/> <br/> **0** -ein regulärer Benutzer. <br/>**2** -ein Administrator in Ihrer Microsoft 365-Organisation. <sup>1</sup> <br/>**3** -ein Microsoft Datacenter-Administrator-oder Datacenter-Systemkonto. <br/>**4** – ein Systemkonto. <br/>**5** – eine Anwendung. <br/>**6** -ein Dienstprinzipal.<br/>**7** – eine benutzerdefinierte Richtlinie.<br/>**8** – eine Systemrichtlinie.|Alle|
|Version|Gibt die Versionsnummer der Aktivität an (identifiziert durch die **Operation** -Eigenschaft), die protokolliert wird.|Alle|
|Workload|Der Microsoft 365-Dienst, auf dem die Aktivität aufgetreten ist.|Alle|
||||

> [!NOTE]
><sup>1</sup> bei Azure-Active Directory bezogenen Ereignissen wird der Wert für einen Administrator nicht in einem Überwachungsdatensatz verwendet. Überwachungseinträge für von Administratoren ausgeführte Aktivitäten geben an, dass ein normaler Benutzer (beispielsweise **usertype: 0**) die Aktivität ausgeführt hat. Mit der **UserID** -Eigenschaft wird die Person (normaler Benutzer oder Administrator) identifiziert, die die Aktivität ausgeführt hat.<br/>

Die oben beschriebenen Eigenschaften werden auch angezeigt, wenn Sie beim Anzeigen der Details eines bestimmten Ereignisses auf **Weitere Informationen** klicken.
  
![Klicken Sie auf „Weitere Informationen“, um die genauen Eigenschaften des Datensatzes für das Überwachungsprotokollereignis anzuzeigen.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
