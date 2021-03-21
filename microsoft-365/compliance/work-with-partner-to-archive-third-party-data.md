---
title: Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen benutzerdefinierten Connector zum Importieren von Drittanbieterdaten aus Datenquellen wie Salesforce Chatter, Yahoo Messenger oder Yammer.
ms.openlocfilehash: adf6583f397296361e8f0cb6f12e7054436fa34f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928379"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten

Sie können mit einem Microsoft-Partner zusammenarbeiten, um Daten aus einer Datenquelle eines Drittanbieters in Microsoft 365 zu importieren und zu archivieren. Ein Partner kann Ihnen einen benutzerdefinierten Connector bereitstellen, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) extrahiert und anschließend importiert werden. Der Partnerconnector konvertiert den Inhalt eines Elements aus der Datenquelle in ein E-Mail-Nachrichtenformat und speichert die Elemente dann in Postfächern. Nachdem Daten von Drittanbietern importiert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Litigation Hold, eDiscovery, In-Place Archiving, Auditing und Microsoft 365 Retention Policies auf diese Daten anwenden.

>[!IMPORTANT]
>Die [](communication-compliance.md) Kommunikationskonformitätslösung in Microsoft 365 kann nicht auf die von Partnerconnectors importierten Drittanbieterdaten angewendet werden, die in diesem Artikel erwähnt werden. 

Im Folgenden finden Sie eine Übersicht über den Prozess und die Schritte, die für die Zusammenarbeit mit einem Microsoft-Partner zum Importieren von Drittanbieterdaten erforderlich sind.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Schritt 2: Erstellen und Konfigurieren eines Drittanbieterdatenpostfachs](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Schritt 4: Bereitstellen von Informationen für Ihren Partner](#step-4-provide-your-partner-with-information)

[Schritt 5: Registrieren des Drittanbieterdatenconnector in Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>So funktioniert der Prozess zum Importieren von Drittanbieterdaten

In der folgenden Abbildung und Beschreibung wird erläutert, wie der Datenimportprozess eines Drittanbieters bei der Zusammenarbeit mit einem Partner funktioniert.
  
![So funktioniert der Prozess zum Importieren von Drittanbieterdaten](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Der Kunde arbeitet mit seinem Partner ihrer Wahl zusammen, um einen Connector zu konfigurieren, der Elemente aus der Datenquelle eines Drittanbieters extrahiert und diese Elemente dann in Microsoft 365 importiert.
    
2. Der Partnerconnector stellt eine Verbindung mit Datenquellen von Drittanbietern über eine Drittanbieter-API (geplant oder wie konfiguriert) bereit und extrahiert Elemente aus der Datenquelle. Der Partnerconnector konvertiert den Inhalt eines Elements in ein E-Mail-Format. Eine Beschreibung [des](#more-information) Nachrichtenformatschemas finden Sie im Abschnitt Weitere Informationen. 
    
3. Partnerconnector stellt eine Verbindung mit dem Azure-Dienst in Microsoft 365 mithilfe von Exchange Web Service (EWS) über einen bekannten Endpunkt bereit.
    
4. Elemente werden in das Postfach eines bestimmten Benutzers oder in ein spezielles Postfach zur Aufnahme aller Drittanbieterdaten importiert. Ob ein Element in das Postfach eines bestimmten Benutzers oder in das Postfach für Drittanbieterdaten importiert wird, basiert auf den folgenden Kriterien:
    
   1. **Elemente mit einer Benutzer-ID, die einem Benutzerkonto entspricht:** Wenn der Partnerconnector die Benutzer-ID des Elements in der Datenquelle eines Drittanbieters einer bestimmten Benutzer-ID  in Microsoft 365 zuordnung, wird das Element in den Ordner "Löschen" im Ordner "Wiederherstellbare Elemente" des Benutzers kopiert. Benutzer können nicht auf Elemente im Ordner „Endgültige Löschvorgänge“ zugreifen. Sie können jedoch eDiscovery-Tools verwenden, um nach Elementen im Ordner "Löschen" zu suchen.
    
   1. **Elemente, die keine Benutzer-ID haben, die einem Benutzerkonto entspricht:** Wenn der Partnerconnector die Benutzer-ID eines Elements nicht einer bestimmten Benutzer-ID zuordnung, wird das Element **in** den Posteingangsordner des Datenpostfachs eines Drittanbieters kopiert. Das Importieren von Elementen in den Posteingang ermöglicht Ihnen oder einem anderen Benutzer in Ihrer Organisation, sich beim Drittanbieter-Postfach anzumelden und diese Elemente zu verwalten und zu sehen, ob Anpassungen an der Partnerconnectorkonfiguration vorgenommen werden müssen.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Schritt 1: Partner für Drittanbieterdaten suchen

Eine wichtige Komponente für die Archivierung von Drittanbieterdaten in Microsoft 365 ist die Suche und Zusammenarbeit mit einem Microsoft-Partner, der sich auf die Erfassung von Daten aus einer Datenquelle eines Drittanbieters und deren Import in Microsoft 365 spezialisiert hat. Nachdem die Daten importiert wurden, können sie zusammen mit den anderen #A0 Ihrer Organisation archiviert und aufbewahrt werden, z. B. E-Mails aus Exchange und Dokumente aus SharePoint und OneDrive for Business. Ein Partner erstellt einen Connector, der Daten aus den Datenquellen von Drittanbietern Ihrer Organisation extrahiert (z. B. BlackBerry, Facebook, Google+, Thomson Reuters, Twitter und YouTube) und diese Daten an eine Microsoft 365-API weitergibt, die Elemente als E-Mail-Nachrichten in Exchange-Postfächer importiert.
  
In den folgenden Abschnitten sind die Microsoft-Partner (und die von ihnen unterstützten Drittanbieterdatenquellen) aufgeführt, die am Programm zur Archivierung von Drittanbieterdaten in Microsoft 365 teilnehmen.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) unterstützt die folgenden Drittanbieterdatenquellen:
  
- BlackBerry
    
- Bloomberg Data Streams
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs Data Streams
    
- OpenText
    
- Live-Hilfe für Oracle/ATG 'click-to-call'
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- SQL-Datenbanken
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial ](https://www.archivesocial.com) unterstützt die folgenden Datenquellen von Drittanbietern: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

Die folgenden Datenquellen von Drittanbietern werden von ["Globenet"](https://www.globanet.com) unterstützt: 
  
- AOL mit Pivot-Client
 
    
- BlackBerry-Anrufprotokolle (v5, v10, v12)

    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- Benutzerdefinierte getrennte Textdateien
    
- Benutzerdefinierte XML-Dateien
    
- Facebook (Seiten)
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business, Versionen 2007 R2 - 2016 (lokal)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) unterstützt die folgenden Drittanbieterdatenquellen: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) unterstützt die folgenden Datenquellen von Drittanbietern: 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- AOL mit Pivot-Client
    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry-Anrufprotokolle (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Mail
    
- CellTrust
    
- Chat Import
    
- Echtzeitprotokollierung und -richtinie für Chat
    
- Chatter
    
- Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Collaboration Import
    
- Echtzeitprotokollierung für Zusammenarbeit
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- Chat-Import
    
- Echtzeitprotokollierung und -richtinie für Chat
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6, v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Microsoft 365 Lync Dedicated
    
- Microsoft 365 Shared IM
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba](https://www.verba.com) unterstützt die folgenden Datenquellen von Drittanbietern: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Chatnachricht in Cisco Jabber
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE Voice
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle/Acme Packet Session Border Controller Video
    
- Oracle/Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- Chatnachricht in Skype for Business/Lync
    
- Skype for Business/Lync Video
    
- Skype for Business/Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop-Computerbildschirm
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>Schritt 2: Erstellen und Konfigurieren eines Drittanbieterdatenpostfachs in Microsoft 365

Im Folgenden finden Sie die Schritte zum Erstellen und Konfigurieren eines Datenpostfachs eines Drittanbieters zum Importieren von Daten in Microsoft 365. Wie bereits erläutert, werden Elemente in dieses Postfach importiert, wenn der Partnerconnector die Benutzer-ID des Elements nicht einem Benutzerkonto zuordnung.
  
 **Führen Sie diese Aufgaben im Microsoft 365 Admin Center aus**
  
1. Erstellen Sie ein Benutzerkonto, und weisen Sie ihm eine Exchange Online Plan 2-Lizenz zu. weitere [Informationen finden Sie unter Hinzufügen von Benutzern zu Microsoft 365](../admin/add-users/add-users.md). Eine Plan 2-Lizenz ist erforderlich, um das Postfach in einem Rechtsstreit zu platzieren oder ein Archivpostfach mit einem unbegrenzten Speicherkontingent zu aktivieren.
    
2. Fügen Sie das Benutzerkonto für das Datenpostfach eines Drittanbieters der **#A0** in Microsoft 365 hinzu. weitere [Informationen finden Sie unter Zuweisen von Administratorrollen in Microsoft 365](../admin/add-users/assign-admin-roles.md).
    
    > [!TIP]
    > Notieren Sie die Anmeldeinformationen für dieses Benutzerkonto. Sie müssen diese für Ihren Partner bereitstellen, wie in Schritt 4 beschrieben. 
  
 **Ausführen dieser Aufgaben im Exchange Admin Center**
  
1. Ausblenden des Drittanbieterdatenpostfachs aus dem Adressbuch und anderen Adresslisten in Ihrer Organisation; weitere [Informationen finden Sie unter Verwalten von Benutzerpostfächern](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes). Alternativ können Sie den folgenden PowerShell-Befehl ausführen:
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Weisen Sie dem Datenpostfach eines Drittanbieters die Berechtigung **FullAccess** zu, damit Administratoren oder Compliance officers das Datenpostfach eines Drittanbieters im #A0 öffnen können. Weitere [Informationen finden Sie unter Verwalten von Berechtigungen für Empfänger](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Aktivieren Sie die folgenden compliancebezogenen Features für das Datenpostfach eines Drittanbieters:
    
    - Aktivieren des Archivpostfachs; weitere [Informationen finden Sie unter Aktivieren von Archivpostfächern](enable-archive-mailboxes.md) und Aktivieren der [unbegrenzten Archivierung.](enable-unlimited-archiving.md) Auf diese Weise können Sie Speicherplatz im primären Postfach frei machen, indem Sie eine Archivrichtlinie einrichten, die Datenelemente von Drittanbietern in das Archivpostfach verschiebt. Dadurch erhalten Sie unbegrenzten Speicherplatz für Drittanbieterdaten.
    
    - Aktivieren Sie für das Drittanbieterdaten-Postfach das Beweissicherungsverfahren. Sie können auch eine Microsoft 365-Aufbewahrungsrichtlinie im Security and Compliance Center anwenden. Durch das Speichern dieses Postfachs werden Datenelemente von Drittanbietern (auf unbestimmte Zeit oder für eine bestimmte Dauer) aufbewahrt und verhindert, dass sie aus dem Postfach gelöscht werden. Sehen Sie sich eines der folgenden Themen an:
    
      - [Aktivieren des Beweissicherungsverfahrens für ein Postfach](./create-a-litigation-hold.md)
    
      - [Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)
    
    - Aktivieren der Postfach-Überwachungsprotokollierung für Besitzer-, Stellvertreter- und Administratorzugriff auf das Datenpostfach eines Drittanbieters; weitere [Informationen finden Sie unter Aktivieren der Postfachüberwachung](enable-mailbox-auditing.md). Auf diese Weise können Sie alle Aktivitäten überwachen, die von jedem Benutzer ausgeführt werden, der Zugriff auf das Datenpostfach eines Drittanbieters hat.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Schritt 3: Benutzerpostfächer für Drittanbieterdaten konfigurieren

Als Nächstes müssen Sie die Benutzerpostfächer für die Unterstützung von Drittanbieterdaten konfigurieren. Führen Sie diese Aufgaben mithilfe des Exchange Admin Centers oder mithilfe der entsprechenden cmdlets Windows PowerShell aus.
  
1. Aktivieren des Archivpostfachs für jeden Benutzer; weitere [Informationen finden Sie unter Aktivieren von Archivpostfächern](enable-archive-mailboxes.md) und Aktivieren der [unbegrenzten Archivierung.](enable-unlimited-archiving.md)
    
2. Platzieren von Benutzerpostfächern in einem Prozessaufbewahrungsverfahren oder Anwenden einer Microsoft 365-Aufbewahrungsrichtlinie; siehe eines der folgenden Themen: 
    
    - [Aktivieren des Beweissicherungsverfahrens für ein Postfach](./create-a-litigation-hold.md)
    
    - [Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)
    
    Wie bereits weiter oben erwähnt, können Sie beim Aktivieren des Beweissicherungsverfahrens für Postfächer festlegen, wie lange Elemente aus einer Drittanbieter-Datenquelle aufbewahrt werden sollen. Sie können auch festlegen, dass sie dauerhaft aufbewahrt werden sollen.

## <a name="step-4-provide-your-partner-with-information"></a>Schritt 4: Bereitstellen von Informationen für Ihren Partner

Der letzte Schritt besteht in der Bereitstellung der folgenden Informationen für Ihren Partner, damit er den Connector so konfigurieren kann, dass eine Verbindung mit Ihrer Organisation hergestellt wird, um Daten in Benutzerpostfächer und das Datenpostfach eines Drittanbieters zu importieren. 
  
- Der Endpunkt, der zum Herstellen einer Verbindung mit dem Azure-Dienst in Microsoft 365 verwendet wird:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Die Anmeldeinformationen (Microsoft 365-Benutzer-ID und -Kennwort) des Datenpostfachs eines Drittanbieters, das Sie in Schritt 2 erstellt haben. Diese Anmeldeinformationen sind erforderlich, damit der Partnerconnector auf Elemente zugreifen und sie in das Drittanbieterdaten-Postfach importieren kann.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Schritt 5: Registrieren des Drittanbieterdatenconnector in Azure Active Directory

Ab dem 30. September 2018 verwendet der Azure-Dienst in Microsoft 365 die moderne Authentifizierung in Exchange Online, um Datenconnectors von Drittanbietern zu authentifizieren, die versuchen, eine Verbindung mit Ihrer Organisation herzustellen, um Daten zu importieren. Der Grund für diese Änderung ist, dass die moderne Authentifizierung mehr Sicherheit bietet als die aktuelle Methode, die auf einer Liste zulässiger Connectors von Drittanbietern basiert, die den zuvor beschriebenen Endpunkt zum Herstellen einer Verbindung mit dem Azure-Dienst verwenden.

Damit ein Datenconnector eines Drittanbieters mithilfe der neuen modernen Authentifizierungsmethode eine Verbindung mit Microsoft 365 herstellen kann, muss ein Administrator in Ihrer Organisation zustimmen, den Connector als vertrauenswürdige Dienstanwendung in Azure Active Directory zu registrieren. Dazu wird eine Berechtigungsanforderung akzeptiert, um dem Connector den Zugriff auf die Daten Ihrer Organisation in Azure Active Directory zu ermöglichen. Nachdem Sie diese Anforderung akzeptiert haben, wird der Drittanbieterdatenconnector als Unternehmensanwendung zu Azure Active Directory hinzugefügt und als Dienstprinzipal dargestellt. Weitere Informationen zum Zustimmungsprozess finden Sie unter  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Hier sind die Schritte, um auf die Anforderung zum Registrieren des Connectors zu zugreifen und diese zu akzeptieren:

1. Wechseln Sie [zu dieser Seite,](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) und melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an.

   Das folgende Dialogfeld wird angezeigt. Sie können die Carets erweitern, um die Berechtigungen zu überprüfen, die dem Connector zugewiesen werden.

   ![Das Dialogfeld Berechtigungsanforderung wird angezeigt](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. Klicken Sie auf **Annehmen**.

Nachdem Sie die Anforderung akzeptiert haben, wird das [Azure-Portal](https://portal.azure.com) angezeigt. Klicken Sie zum Anzeigen der Liste der Anwendungen für Ihre Organisation auf **Azure Active Directory**  >  **Enterprise-Anwendungen.** Der Microsoft 365-Drittanbieterdatenconnector ist auf dem Blatt **Enterprise-Anwendungen** aufgeführt.

> [!IMPORTANT]
> Nach dem 30. September 2018 werden Drittanbieterdaten nicht mehr in Postfächer in Ihrer Organisation importiert, wenn Sie keinen Drittanbieterdatenconnector in Azure Active Directory registrieren. Beachten Sie, dass vorhandene Datenconnectors von Drittanbietern (die vor dem 30. September 2018 erstellt wurden) auch in Azure Active Directory registriert werden müssen, indem Sie das Verfahren in Schritt 5 folgen.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Widerrufen der Zustimmung für einen Datenconnector eines Drittanbieters

Nachdem Ihre Organisation der Berechtigungsanforderung zur Registrierung eines Drittanbieterdatenconnector in Azure Active Directory zugestimmt hat, kann Ihre Organisation diese Zustimmung jederzeit widerrufen. Das Widerrufen der Zustimmung für einen Connector bedeutet jedoch, dass Daten aus der Datenquelle eines Drittanbieters nicht mehr in Microsoft 365 importiert werden.

Um die Zustimmung für einen Datenconnector eines Drittanbieters zu widerrufen, können Sie die Anwendung (durch Löschen des entsprechenden Dienstprinzipals) aus Azure Active Directory mithilfe des Blatts **Enterprise-Anwendungen** im Azure-Portal oder mithilfe des [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell löschen. Sie können auch das [Cmdlet Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell verwenden.
  
## <a name="more-information"></a>Weitere Informationen

- Wie bereits weiter oben erläutert, werden Elemente aus Drittanbieter-Datenquellen als E-Mail-Nachrichten in Exchange-Postfächer importiert. Der Partnerconnector importiert das Element mithilfe eines Schemas, das von der Microsoft 365-API benötigt wird. Die folgende Tabelle beschreibt die Nachrichteneigenschaften eines Elements aus einer Drittanbieter-Datenquelle, nachdem es als E-Mail-Nachricht in ein Exchange-Postfach importiert wurde. Zudem ist angegeben, wenn die Nachrichteneigenschaft zwingend erforderlich ist. Erforderliche Eigenschaften müssen aufgefüllt werden. Wenn einem Element eine obligatorische Eigenschaft fehlt, wird es nicht nach Microsoft 365 importiert. Der Importvorgang gibt eine Fehlermeldung zurück, in der erläutert wird, warum ein Element nicht importiert wurde und welche Eigenschaft fehlt.<br/><br/>
    
    |**Nachrichteneigenschaft**|**Erforderlich?**|**Beschreibung**|**Beispielwert**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Ja  <br/> |Der Benutzer, der das Element in der Drittanbieter-Datenquelle ursprünglich erstellt oder gesendet hat. Der Partnerconnector versucht, die Benutzer-ID aus dem Quellelement (z. B. ein Twitter-Handle) einem Benutzerkonto für alle Teilnehmer (Benutzer in den Feldern FROM und TO) zu zuordnungen. Eine Kopie der Nachricht wird in das Postfach jedes Teilnehmers importiert. Wenn keiner der Teilnehmer aus dem Element einem Benutzerkonto zugeordnet werden kann, wird das Element in das Archivierungspostfach eines Drittanbieters in Microsoft 365 importiert.  <br/> <br/> Der Teilnehmer, der als Absender des Elements identifiziert wird, muss über ein aktives Postfach in der Organisation verfügen, in die das Element importiert wird. Wenn der Absender nicht über ein aktives Postfach verfügt, wird der folgende Fehler zurückgegeben:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Ja  <br/> |Der Benutzer, der ein Element erhalten hat (wenn für ein Element in der Datenquelle zutreffend).  <br/> | `bob@contoso.com` <br/> |
    |**Betreff** <br/> |Nein  <br/> |Der Betreff des Quellelements.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |Ja  <br/> |Das Datum, an dem das Element ursprünglich in der Kundendatenquelle erstellt oder veröffentlicht wurde. Beispielsweise das Datum, an dem eine Twitter-Nachricht getwittert wurde.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |Nein  <br/> |Der Inhalt der Nachricht oder des Beitrags. Bei einigen Datenquellen kann der Inhalt dieser Eigenschaft mit dem Inhalt der Eigenschaft **SUBJECT** identisch sein. Während des Importvorgangs versucht der Partnerconnector, die vollständige Genauigkeit von der Inhaltsquelle so wie möglich zu erhalten. Soweit möglich, werden Dateien, Grafiken oder andere Inhalte aus dem Textkörper des Quellelements in diese Eigenschaft einbezogen. Andernfalls wird der Inhalt aus dem Quellelement in die Eigenschaft **ATTACHMENT** einbezogen. Der Inhalt dieser Eigenschaft hängt vom Partnerconnector und von der Funktion der Quellplattform ab.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |Nein  <br/> |Wenn ein Element in der Datenquelle (z. B. ein Tweet in Twitter oder eine Instant Messaging-Unterhaltung) über eine angefügte Datei verfügt oder Bilder enthält, versucht die Partner-Verbindung zunächst, Anlagen in die **BODY-Eigenschaft** zu schließen. Wenn dies nicht möglich ist, wird es der ** ATTACHMENT ** -Eigenschaft hinzugefügt. Weitere Beispiele für Anlagen sind „Gefällt mir“-Angaben in Facebook, Metadaten aus der Inhaltsquelle und Antworten auf eine Nachricht oder einen Beitrag.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Ja  <br/> | Dies ist eine Eigenschaft mit mehreren Werten, die vom Partnerconnector erstellt und mit Werten gefüllt wird. Das Format dieser Eigenschaft ist  `IPM.NOTE.Source.Event` . (Diese Eigenschaft muss mit  `IPM.NOTE` beginnen. Dieses Format ähnelt dem format für die  `IPM.NOTE.X` Nachrichtenklasse.) Diese Eigenschaft enthält die folgenden Informationen:  <br/><br/>`Source`: Gibt die Datenquelle eines Drittanbieters an; z. B. Twitter, Facebook oder BlackBerry.  <br/> <br/>  `Event`: Gibt den Typ der Aktivität an, die in der Datenquelle eines Drittanbieters ausgeführt wurde, von der die Elemente erstellt wurden; z. B. ein Tweet in Twitter oder ein Beitrag in Facebook. Ereignisse sind für die jeweilige Datenquelle spezifisch.  <br/> <br/>  Ein Zweck dieser Eigenschaft ist es zum Beispiel, bestimmte Elemente basierend auf der Datenquelle zu filtern, aus der ein Element stammt, oder basierend auf dem Typ des Ereignisses. So könnten Sie in einer eDiscovery-Suche zum Beispiel eine Suchabfrage erstellen, um alle Tweets zu finden, die von einem bestimmten Benutzer gepostet wurden.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Wenn Elemente erfolgreich in Postfächer in Microsoft 365 importiert werden, wird ein eindeutiger Bezeichner als Teil der HTTP-Antwort an den Aufrufer zurückgegeben. Dieser Bezeichner namens , kann für nachfolgende Problembehandlungszwecke von Partnern für die  `x-IngestionCorrelationID` End-to-End-Nachverfolgung von Elementen verwendet werden. Es wird empfohlen, dass Partner diese Informationen entsprechend erfassen und sammeln. Im Folgenden ist ein Beispiel einer HTTP-Antwort mit diesem Bezeichner aufgeführt:

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- Sie können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um nach Elementen zu suchen, die aus einer Datenquelle eines Drittanbieters in Postfächer importiert wurden. Um speziell nach diesen importierten Elementen zu suchen, können Sie die folgenden Nachrichteneigenschaft-Wert-Paare im Schlüsselwortfeld für eine Inhaltssuche verwenden.
    
  - **`kind:externaldata`**: Verwenden Sie dieses Eigenschaften-Wert-Paar, um alle Datentypen von Drittanbietern zu durchsuchen. Wenn Sie beispielsweise nach Elementen suchen möchten, die aus einer Datenquelle eines Drittanbieters importiert wurden und das Wort "contoso" in der Subject-Eigenschaft des importierten Elements enthalten, verwenden Sie die Schlüsselwortabfrage  `kind:externaldata AND subject:contoso` .
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: Verwenden Sie dieses Eigenschaften-Wert-Paar, um nur einen angegebenen Typ von Drittanbieterdaten zu durchsuchen. Wenn Sie beispielsweise nur Facebook-Daten durchsuchen möchten, die das Wort "contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die Schlüsselwortabfrage  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` . 

  Eine vollständige Liste der Werte, die für Drittanbieterdatentypen für die Eigenschaft verwendet werden sollen, finden Sie unter  `itemclass` Use Content Search to search [third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).
    
   Weitere Informationen zur Verwendung der Inhaltssuche und zum Erstellen von Stichwortsuchabfragen finden Sie unter:
    
  - [Inhaltssuche](content-search.md)
    
  - [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)