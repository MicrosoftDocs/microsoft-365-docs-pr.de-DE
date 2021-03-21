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
description: Dieser Artikel enthält Beschreibungen zusätzlicher Eigenschaften, die beim Exportieren von Ergebnissen für einen Office 365-Überwachungsprotokolldatensatz enthalten sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69a34f4de948bc9533ef2872d94171134e50ffea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927073"
---
# <a name="detailed-properties-in-the-audit-log"></a>Detaillierte Eigenschaften im Überwachungsprotokoll

Wenn Sie die Ergebnisse einer Überwachungsprotokollsuche aus dem Security & Compliance Center exportieren, haben Sie die Möglichkeit, alle Ergebnisse herunterzuladen, die Ihren Suchkriterien entsprechen. Wählen Sie dazu **Ergebnisse exportieren** Alle Ergebnisse auf der Seite \>  **Überwachungsprotokollsuche** herunterladen aus. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).
  
 Wenn Sie alle Ergebnisse für eine Überwachungsprotokollsuche exportieren, werden die Rohdaten aus dem einheitlichen Überwachungsprotokoll in eine CSV-Datei (Comma-Separated Value) kopiert, die auf Ihren lokalen Computer heruntergeladen wird. Diese Datei enthält zusätzliche Informationen aus jedem Überwachungsdatensatz in einer Spalte **namens AuditData**. Diese Spalte enthält eine mehrwertige Eigenschaft für mehrere Eigenschaften aus dem Überwachungsprotokolldatensatz. Jede **Eigenschaft: Wertpaare** in dieser mehrwertigen Eigenschaft werden durch ein Komma getrennt. 
  
In der folgenden Tabelle werden die Eigenschaften beschrieben, die (abhängig vom Dienst, in dem ein Ereignis auftritt) in der Spalte **AuditData** mit mehreren Eigenschaften enthalten sind. Der **Office 365-Dienst** mit dieser Eigenschaftenspalte gibt den Dienst und den Typ der Aktivität (Benutzer oder Administrator) an, die die Eigenschaft enthalten. Ausführlichere Informationen zu diesen Eigenschaften oder zu Eigenschaften, die möglicherweise nicht in diesem Thema aufgeführt sind, finden Sie unter [Management Activity API Schema](/office/office-365-management-api/office-365-management-activity-api-schema).
  
> [!TIP]
> Sie können das JSON-Transformationsfeature in Power Query in Excel verwenden, um die **Spalte AuditData** in mehrere Spalten zu teilen, sodass jede Eigenschaft eine eigene Spalte hat. Dadurch können Sie nach einer oder mehreren dieser Eigenschaften sortieren und filtern. Informationen dazu finden Sie unter Exportieren, Konfigurieren und Anzeigen [von Überwachungsprotokolleinträgen](export-view-audit-log-records.md). 
  
|**Eigenschaft**|**Beschreibung**|**Microsoft 365-Dienst mit dieser Eigenschaft**|
|:-----|:-----|:-----|
|Akteur|Das Benutzer- oder Dienstkonto, das die Aktion ausgeführt hat.|Azure Active Directory|
|AddOnName|Der Name eines Add-Ons, das in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Der Typ von Add-Ons in Microsoft Teams ist ein Bot, ein Connector oder eine Registerkarte.|Microsoft Teams|
|AddOnType|Der Typ eines Add-Ons, das in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Die folgenden Werte geben den Typ des Add-Ons an.  <br/> **1** – Gibt einen Bot an.<br/> **2** – Gibt einen Connector an.<br/> **3** – Gibt eine Registerkarte an.|Microsoft Teams|
|AzureActiveDirectoryEventType|Der Typ des Azure Active Directory-Ereignisses. Die folgenden Werte geben den Ereignistyp an.  <br/> **0** – Gibt ein Kontoanmeldungsereignis an.<br/> **1** – Gibt ein Azure-Anwendungssicherheitsereignis an.|Azure Active Directory|
|ChannelGuid|Die ID eines Microsoft Teams-Kanals. Das Team, in dem sich der Kanal befindet, wird durch die **Eigenschaften TeamName** und **TeamGuid** identifiziert.|Microsoft Teams|
|ChannelName|Der Name eines Microsoft Teams-Kanals. Das Team, in dem sich der Kanal befindet, wird durch die **Eigenschaften TeamName** und **TeamGuid** identifiziert.|Microsoft Teams|
|Client|Das Clientgerät, das Gerätebetriebssystem und der Gerätebrowser, der für das Anmeldeereignis verwendet wird (z. B. Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Informationen zum E-Mail-Client, der zum Ausführen des Vorgangs verwendet wurde, z. B. eine Browserversion, eine Outlook-Version und Informationen zu mobilen Geräten|Exchange (Postfachaktivität)|
|ClientIP|Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.<br/><br/> Bei einigen Diensten ist der in dieser Eigenschaft angezeigte Wert möglicherweise die IP-Adresse einer vertrauenswürdigen Anwendung (z.B. Office in den Web-Apps), die anstelle eines Benutzers in den Dienst einruft und nicht die IP-Adresse des Geräts, das von der Person, die die Aktivität ausgeführt hat, verwendet wird. <br/><br/>Außerdem wird bei Administratoraktivitäten (oder von einem Systemkonto ausgeführten Aktivitäten) für Azure Active Directory-bezogene Ereignisse die IP-Adresse nicht protokolliert, und der Wert für die ClientIP-Eigenschaft ist `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|Das Datum und die Uhrzeit in koordinierter Weltzeit (UTC), wann der Benutzer die Aktivität ausgeführt hat.|Alle|
|DestinationFileExtension|Der Erweiterung der Datei, die kopiert oder verschoben wurde. Diese Eigenschaft wird nur für die Benutzeraktivitäten FileCopied und FileMoved angezeigt.|SharePoint|
|DestinationFileName|Der Name der Datei wird kopiert oder verschoben. Diese Eigenschaft wird nur für die Aktionen FileCopied und FileMoved angezeigt.|SharePoint|
|DestinationRelativeUrl|Die URL des Zielordners, in den eine Datei kopiert oder verschoben wurde. Die Kombination der Werte für **siteURL,** **DestinationRelativeURL** und **DestinationFileName** ist identisch mit dem Wert für die **ObjectID-Eigenschaft,** die den vollständigen Pfadnamen für die kopierte Datei ist. Diese Eigenschaft wird nur für die Benutzeraktivitäten FileCopied und FileMoved angezeigt.|SharePoint|
|EventSource|Gibt an, dass ein Ereignis in SharePoint eingetreten ist. Mögliche Werte sind **SharePoint** und **ObjectModel**.|SharePoint|
|ExternalAccess|Gibt für die Exchange-Administratoraktivität an, ob das Cmdlet von einem Benutzer in Ihrer Organisation, von Mitarbeitern des Microsoft-Rechenzentrums oder einem Rechenzentrumsdienstkonto oder von einem delegierten Administrator ausgeführt wurde. Der Wert **False** gibt an, dass das Cmdlet von einer Person in Ihrer Organisation ausgeführt wurde. Der Wert **True** gibt an, dass das Cmdlet von Mitarbeiter des Rechenzentrums, einem Rechenzentrum-Dienstkonto oder einem delegierten Administrator ausgeführt wurde.  <br/> Gibt für die Exchange-Postfachaktivität an, ob ein Benutzer außerhalb Ihrer Organisation auf ein Postfach zugegriffen hat.|Exchange|
|ExtendedProperties|Die erweiterten Eigenschaften für ein Azure Active Directory-Ereignis.|Azure Active Directory|
|ID|Die ID des Berichtseintrags. Die ID identifiziert den Berichtseintrag eindeutig.|Alle|
|InternalLogonType|Für die interne Verwendung reserviert.|Exchange (Postfachaktivität)|
|ItemType|Der Typ des Objekts, auf das zugegriffen bzw. das geändert wurde. Mögliche Werte sind **File**, **Folder**, **Web**, **Site**, **Tenant** und **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifiziert Anmeldefehler, die möglicherweise aufgetreten sind.|Azure Active Directory|
|LogonType|Der Typ des Postfachzugriffs. Die folgenden Werte geben den Typ des Benutzers an, der auf das Postfach zugegriffen hat.  <br/><br/> **0** – Gibt einen Postfachbesitzer an.<br/> **1** – Gibt einen Administrator an.<br/> **2** – Gibt einen Delegaten an. <br/>**3** – Gibt den Transportdienst im Microsoft-Rechenzentrum an.<br/> **4** – Gibt ein Dienstkonto im Microsoft-Rechenzentrum an. <br/>**6** – Gibt einen delegierten Administrator an.|Exchange (Postfachaktivität)|
|MailboxGuid|Die Exchange-GUID des Postfachs, auf das zugegriffen wurde.|Exchange (Postfachaktivität)|
|MailboxOwnerUPN|Die E-Mail-Adresse der Person, die das Postfach besitzt, auf das zugegriffen wurde.|Exchange (Postfachaktivität)|
|Members|Listet die Benutzer auf, die einem Team hinzugefügt oder aus diesem entfernt wurden. Die folgenden Werte geben den Rollentyp an, der dem Benutzer zugewiesen wurde.  <br/><br/> **1** – Gibt die Rolle Besitzer an.<br/> **2** - Gibt die Mitgliedsrolle an.<br/> **3** - Gibt die Gastrolle an. <br/><br/>Die Eigenschaft „Mitglieder“ enthält auch den Namen Ihrer Organisation und die E-Mail-Adresse des Mitglieds.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|Diese Eigenschaft wird für Administratorereignisse einbezogen, wie z. B. das Hinzufügen eines Benutzers als Mitglied einer Website oder der Administratorgruppe einer Websitesammlung. Die Eigenschaft enthält den Namen der Eigenschaft, die geändert wurde (z. B. die Gruppe Websiteadministrator), den neuen Wert der geänderten Eigenschaft (z. B. den Benutzer, der als Websiteadministrator hinzugefügt wurde, und den vorherigen Wert des geänderten Objekts.|Alle (Administratoraktivität)|
|ObjectId|Für Exchange-Verwaltungsüberwachungsprotokolle der Name des Objekts, das vom Cmdlet geändert wurde.  <br/> Bei SharePoint-Aktivitäten der vollständige NAME des URL-Pfads der Datei oder des Ordners, auf die ein Benutzer zu zugegriffen hat.  <br/> Bei Azure AD-Aktivitäten der Name des geänderten Benutzerkontos.|Alle|
|Vorgang|Der Name der Benutzer- oder Verwaltungsaktivität. Der Wert dieser Eigenschaft entspricht dem Wert, der in der Dropdownliste **Aktivitäten** ausgewählt wurde. Wenn **Ergebnisse für alle Aktivitäten anzeigen** ausgewählt wurde, enthält der Bericht Einträge für alle Benutzer- und Administratoraktivitäten für alle Dienste. Eine Beschreibung der Vorgänge/Aktivitäten, die im Überwachungsprotokoll  protokolliert werden, finden Sie auf der Registerkarte Überwachte Aktivitäten unter Durchsuchen des Überwachungsprotokolls [in Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> Für Exchange-Administratoraktivitäten gibt diese Eigenschaft den Namen des Cmdlets an, das ausgeführt wurde.|Alle|
|OrganizationId|Die GUID für Ihre Organisation.|Alle|
|Pfad|Der Name des Postfachordners, in dem sich die Nachricht, auf die zugegriffen wurde, befindet. Diese Eigenschaft identifiziert auch den Ordner, in dem eine Nachricht erstellt oder kopiert/verschoben wird.|Exchange (Postfachaktivität)|
|Parameter|Für die Exchange-Administratoraktivität den Namen und wert für alle Parameter, die mit dem Cmdlet verwendet wurden, das in der Operation-Eigenschaft identifiziert ist.|Exchange (Administratoraktivität)|
|RecordType|Der vom Datensatz angegebene Vorgangstyp. Diese Eigenschaft gibt den Dienst oder das Feature an, in dem der Vorgang ausgelöst wurde. Eine Liste der Datensatztypen und des entsprechenden ENUM-Werts (der wert, der in der **RecordType-Eigenschaft** in einem Überwachungsdatensatz angezeigt wird) finden Sie unter [Überwachungsprotokolldatensatztyp](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).| 
|ResultStatus|Gibt an, ob die Aktion (angegeben in der **Operation-Eigenschaft)** erfolgreich war oder nicht.  <br/> Bei Exchange-Administratoraktivitäten ist der Wert **entweder True** (erfolgreich) oder **False** (fehlgeschlagen).|Alle  <br/>|
|SecurityComplianceCenterEventType|Gibt an, dass die Aktivität ein Security & Compliance Center-Ereignis war. Alle Security & Compliance Center-Aktivitäten haben den Wert **0** für diese Eigenschaft.|Security & Compliance Center|
|SharingType|Der Typ der Freigabeberechtigungen, die dem Benutzer zugewiesen wurden, für den die Ressource freigegeben wurde. Dieser Benutzer wird in der **UserSharedWith-Eigenschaft** identifiziert.|SharePoint|
|Website|Die GUID der Website, auf der sich die Datei oder der Ordner, auf die bzw. den der Benutzer zugegriffen hat, befindet.|SharePoint|
|SiteUrl|Die URL der Website, auf der sich die Datei oder der Ordner, auf die bzw. den der Benutzer zugegriffen hat, befindet.|SharePoint|
|SourceFileExtension|Die Erweiterung der Datei, auf die der Benutzer zugegriffen hat. Diese Eigenschaft ist leer, wenn das Objekt, auf das zugegriffen wurde, ein Ordner ist.|SharePoint|
|SourceFileName|Der Name der Datei oder des Ordners, auf die der Benutzer zugegriffen hat.|SharePoint|
|SourceRelativeUrl|Die URL des Ordners, der die Datei enthält, auf die der Benutzer zugegriffen hat. Die Kombination der Werte für **SiteURL,** **SourceRelativeURL** und **SourceFileName** ist identisch mit dem Wert für die **ObjectID-Eigenschaft,** bei der es sich um den vollständigen Pfadnamen für die Vom Benutzer zugegriffene Datei handelt.|SharePoint|
|Betreff|Die Betreffzeile der Nachricht, auf die zugegriffen wurde.|Exchange (Postfachaktivität)|
|TabType| Der Typ der Registerkarte, die in einem Team hinzugefügt, entfernt oder aktualisiert wurde. Gültige Werte für diese Eigenschaft sind:  <br/><br/> **Excel-Pin** – Eine Excel-Registerkarte.  <br/> **Erweiterung** – Alle Apps von Erst- und Drittanbietern; z. B. Klassenzeitplan, VSTS und Formulare.  <br/> **Hinweise** – OneNote-Registerkarte.  <br/> **Pdfpin** – Eine PDF-Registerkarte.  <br/> **Powerbi** – Eine Power BI-Registerkarte.  <br/> **Powerpointpin** – Eine PowerPoint-Registerkarte.  <br/> **Sharepointfiles** – Eine SharePoint-Registerkarte.  <br/> **Webseite** – Eine angeheftet Websiteregisterkarte.  <br/> **Wiki-tab** – Eine Wiki-Registerkarte.  <br/> **Wordpin** – Eine Word-Registerkarte.|Microsoft Teams|
|Ziel|Der Benutzer, für den die Aktion (in der **Operation-Eigenschaft** identifiziert) ausgeführt wurde. Wenn beispielsweise ein Gastbenutzer zu SharePoint oder einem Microsoft Team hinzugefügt wird, wird dieser Benutzer in dieser Eigenschaft aufgeführt.|Azure Active Directory|
|TeamGuid|Die ID eines Teams in Microsoft Teams.|Microsoft Teams|
|TeamName|Der Name eines Teams in Microsoft Teams.|Microsoft Teams|
|UserAgent|Informationen zum Browser des Benutzers. Diese Informationen werden vom Browser bereitgestellt.|SharePoint|
|UserDomain|Identitätsinformationen zur Mandantenorganisation des Benutzers (Akteur), der die Aktion ausgeführt hat.|Azure Active Directory|
|UserId|Der Benutzer, der die (in der **Operation-Eigenschaft** angegebene) Aktion ausgeführt hat, die dazu geführt hat, dass der Datensatz protokolliert wurde. Überwachungsdatensätze für Aktivitäten, die von Systemkonten ausgeführt werden (z. B. SHAREPOINT\System oder NT AUTHORITY\SYSTEM), sind ebenfalls im Überwachungsprotokoll enthalten. Ein weiterer gemeinsamer Wert für die UserId-Eigenschaft ist app@sharepoint. Dies zeigt an, dass es sich bei dem "Benutzer", der die Aktivität ausgeführt hat, um eine Anwendung handelt, die in SharePoint über die erforderlichen Berechtigungen verfügt, organisationsweite Aktionen (z. B. das Durchsuchen einer SharePoint-Website oder eines OneDrive-Kontos) im Auftrag eines Benutzers, Administrators oder Diensts auszuführen. Weitere Informationen finden Sie unter [Der "app\@sharepoint"-Benutzer in Überwachungsdatensätzen](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |Alle|
|UserKey|Eine alternative ID für den in der **UserID-Eigenschaft identifizierten** Benutzer. Beispielsweise wird diese Eigenschaft mit der eindeutigen Passport-ID (PUID) für Ereignisse gefüllt, die von Benutzern in SharePoint ausgeführt werden. Diese Eigenschaft kann auch denselben Wert wie die **UserID-Eigenschaft** für Ereignisse angeben, die in anderen Diensten und Ereignissen auftreten, die von Systemkonten ausgeführt werden.|Alle|
|UserSharedWith|Der Benutzer, für den eine Ressource freigegeben wurde. Diese Eigenschaft ist enthalten, wenn der Wert für die **Operation-Eigenschaft** **SharingSet ist.** Dieser Benutzer wird auch in der Spalte **Freigegeben mit** im Bericht aufgeführt.|SharePoint|
|UserType|Der Typ des Benutzers, der den Vorgang ausgeführt hat. Die folgenden Werte geben den Benutzertyp an. <br/> <br/> **0** – Ein normaler Benutzer. <br/>**2** – Ein Administrator in Ihrer Microsoft 365-Organisation. <sup>1</sup> <br/>**3** – Ein Microsoft-Rechenzentrumsadministrator oder ein Datencentersystemkonto. <br/>**4** – Ein Systemkonto. <br/>**5** – Eine Anwendung. <br/>**6** – Ein Dienstprinzipal.<br/>**7** – Eine benutzerdefinierte Richtlinie.<br/>**8** – Eine Systemrichtlinie.|Alle|
|Version|Gibt die Versionsnummer der Aktivität (identifiziert durch die **Operation-Eigenschaft)** an, die protokolliert wird.|Alle|
|Arbeitslast|Der Microsoft 365-Dienst, in dem die Aktivität aufgetreten ist.|Alle|
||||

> [!NOTE]
><sup>1</sup> Bei Azure Active Directory-bezogenen Ereignissen wird der Wert für einen Administrator nicht in einem Überwachungsdatensatz verwendet. Überwachungsdatensätze für Aktivitäten, die von Administratoren ausgeführt werden, geben an, dass ein regulärer Benutzer (z. B. **UserType: 0**) die Aktivität ausgeführt hat. Die **UserID-Eigenschaft** identifiziert die Person (regulärer Benutzer oder Administrator), die die Aktivität ausgeführt hat.<br/>

Die oben beschriebenen Eigenschaften werden auch  angezeigt, wenn Sie beim Anzeigen der Details eines bestimmten Ereignisses auf Weitere Informationen klicken.
  
![Klicken Sie auf „Weitere Informationen“, um die genauen Eigenschaften des Datensatzes für das Überwachungsprotokollereignis anzuzeigen.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)