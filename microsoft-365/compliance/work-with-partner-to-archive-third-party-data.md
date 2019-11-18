---
title: Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Ihre Organisation kann mit einem Microsoft-Partner zusammenarbeiten, um einen benutzerdefinierten Connector zum Importieren von drittanbieterdaten aus Datenquellen wie Salesforce Chatter, Yahoo Messenger oder jammern einzurichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Office 365 archivieren, sodass Sie Office 365 Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Steuerung der drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 9a1767baadb237196161032166f78c06dc7e099b
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686307"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a>Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365

Sie können mit einem Microsoft-Partner zusammenarbeiten, um Daten aus einer Drittanbieter-Datenquelle in Office 365 zu importieren und zu archivieren. Ein Partner kann Ihnen einen benutzerdefinierten Connector zur Verfügung stellen, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle extrahiert (regelmäßig) und diese Elemente anschließend in Office 365 importiert. Der Partner Connector wandelt den Inhalt eines Elements aus der Datenquelle in ein e-Mail-Nachrichtenformat um und speichert dann die Elemente in Postfächern in Office 365. Nachdem Sie Daten von Drittanbietern importiert haben, können Sie Office 365 Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung und Office 365-Aufbewahrungsrichtlinien auf diese Daten anwenden.
  
Im folgenden finden Sie eine Übersicht über den Prozess und die erforderlichen Schritte für die Zusammenarbeit mit einem Microsoft-Partner zum Importieren von drittanbieterdaten in Office 365.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Schritt 4: Bereitstellen von Informationen für Ihren Partner](#step-4-provide-your-partner-with-information)

[Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>So funktioniert der Prozess zum Importieren von Drittanbieterdaten

In der folgenden Abbildung und Beschreibung wird erläutert, wie der Datenimportvorgang eines Drittanbieters bei der Arbeit mit einem Partner funktioniert.
  
![So funktioniert der Prozess zum Importieren von Drittanbieterdaten](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Der Kunde arbeitet mit seinem Partner an der Wahl, um einen Connector zu konfigurieren, der Elemente aus der Drittanbieter-Datenquelle extrahiert und diese Elemente dann in Office 365 importiert.
    
2. Der Partner Connector stellt über eine API eines Drittanbieters (auf geplanter oder konfigurierter Basis) eine Verbindung mit Drittanbieter-Datenquellen her und extrahiert Elemente aus der Datenquelle. Der Partnerconnector konvertiert den Inhalt eines Elements in ein E-Mail-Format. Eine Beschreibung des Nachrichtenformat Schemas finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
    
3. Partner Connector stellt über einen bekannten Endpunkt eine Verbindung mit dem Azure-Dienst in Office 365 mithilfe des Exchange-Webdiensts (EWS) her.
    
4. Elemente werden in das Postfach eines bestimmten Benutzers oder in ein spezielles Postfach zur Aufnahme aller Drittanbieterdaten importiert. Ob ein Element in das Postfach eines bestimmten Benutzers oder in das Postfach für Drittanbieterdaten importiert wird, basiert auf den folgenden Kriterien:
    
    a. **Elemente mit einer Benutzer-ID, die einem Office 365 Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID des Elements in der Drittanbieter-Datenquelle einer bestimmten Benutzer-ID in Office 365 zuordnen kann, wird das Element im Ordner "refundable Items" des Benutzers in den Ordner " **Säuberungen** " kopiert. Benutzer können nicht auf Elemente im Ordner „Endgültige Löschvorgänge“ zugreifen. Sie können jedoch Office 365 eDiscovery-Tools verwenden, um nach Elementen im Ordner "Säuberungen" zu suchen.
    
    b. **Elemente, die nicht über eine Benutzer-ID verfügen, die einem Office 365 Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID eines Elements nicht einer bestimmten Benutzer-ID in Office 365 zuordnen kann, wird das Element in den Ordner **Posteingang** des Drittanbieter-Daten Postfachs kopiert. Das Importieren von Elementen in den Posteingang ermöglicht Ihnen oder einem anderen Benutzer in Ihrer Organisation, sich beim Drittanbieter-Postfach anzumelden und diese Elemente zu verwalten und zu sehen, ob Anpassungen an der Partnerconnectorkonfiguration vorgenommen werden müssen.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Schritt 1: Partner für Drittanbieterdaten suchen

Eine wichtige Komponente zum Archivieren von drittanbieterdaten in Office 365 besteht darin, einen Microsoft-Partner zu finden und zu verwenden, der sich auf die Erfassung von Daten aus einer Drittanbieter-Datenquelle und den Import in Office 365 spezialisiert hat. Nachdem die Daten importiert wurden, können Sie zusammen mit anderen Microsoft-Daten Ihrer Organisation wie e-Mails von Exchange und Dokumenten aus SharePoint und OneDrive für Unternehmen archiviert und aufbewahrt werden. Ein Partner erstellt einen Konnektor, der Daten aus den drittanbieterdaten Quellen Ihrer Organisation extrahiert (wie BlackBerry, Facebook, Google +, Thomson Reuters, Twitter und YouTube) und übergibt diese Daten an eine Office 365-API, die Elemente in Exchange-Postfächer importiert, als e-Mail-Nachrichten. 
  
In den folgenden Abschnitten werden die Microsoft-Partner (und die von Ihnen unterstützten Drittanbieter-Datenquellen) aufgeführt, die am Programm zum Archivieren von drittanbieterdaten in Office 365 teilnehmen.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

die [17a-4 LLC](https://www.17a-4.com) unterstützt die folgenden Drittanbieter-Datenquellen:
  
- BlackBerry
    
- Bloomberg Data Streams
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- Schwätzchen
    
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

[ArchiveSocial](https://www.archivesocial.com) unterstützt die folgenden Drittanbieter-Datenquellen: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) unterstützt die folgenden Drittanbieter-Datenquellen: 
  
- AOL mit Pivot-Client
 
    
- BlackBerry-Anrufprotokolle (v5, v10, v12)

    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco Chat &amp; Presence Server (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)

- Cisco WebEx-Teams

- Citrix- &amp; Arbeitsbereichs Freigabe

- CrowdCompass

- Benutzerdefinierte Textdateien mit Trennzeichen
    
- Benutzerdefinierte XML-Dateien
    
- Facebook (Seiten)
    
- FactSet
    
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
    
- Symphonie
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) unterstützt die folgenden Drittanbieter-Datenquellen: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) unterstützt die folgenden Drittanbieter-Datenquellen: 
  
- Versuchen
    
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
    
- Störgeräusche
    
- Cisco Chat &amp; Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Collaboration Import
    
- Echtzeitprotokollierung für Zusammenarbeit
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
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
    
- Ice/YellowJacket
    
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
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphonie
    
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

[Verba](https://www.verba.com) unterstützt die folgenden Drittanbieter-Datenquellen: 
  
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
    
- Cisco UCCX/UCCE-Video
    
- Cisco UCCX/UCCE-VoIP
    
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
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>Schritt 2: Drittanbieter-Postfach in Office 365 erstellen und konfigurieren

Hier finden Sie die Schritte zum Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs zum Importieren von Daten in Office 365. Wie bereits erläutert, werden Elemente in dieses Postfach importiert, wenn der Partner Connector die Benutzer-ID des Elements nicht einem Office 365 Benutzerkonto zuordnen kann.
  
 **Führen Sie diese Aufgaben im Microsoft 365 Admin Center aus.**
  
1. Erstellen Sie ein Benutzerkonto in Office 365, und weisen Sie ihm eine Exchange Online Plan 2-Lizenz zu. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern zu Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Eine Plan 2-Lizenz ist erforderlich, um das Postfach in einem Beweissicherungsverfahren aufzubewahren oder ein Archivpostfach mit einem unbegrenzten Speicherkontingent zu aktivieren.
    
2. Fügen Sie das Benutzerkonto für das Drittanbieter-Daten Postfach der **Administratorrolle Exchange-Administrator** in Office 365 hinzu. Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Notieren Sie die Anmeldeinformationen für dieses Benutzerkonto. Sie müssen diese für Ihren Partner bereitstellen, wie in Schritt 4 beschrieben. 
  
 **Führen Sie diese Aufgaben im Exchange Admin Center aus.**
  
1. Ausblenden des Drittanbieter-Daten Postfachs aus dem Adressbuch und anderen Adresslisten in Ihrer Organisation; Weitere Informationen finden Sie unter [Verwalten von Benutzerpostfächern](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternativ können Sie den folgenden PowerShell-Befehl ausführen:
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Weisen Sie dem Drittanbieter-Daten Postfach die Berechtigung **FullAccess** zu, damit Administratoren oder Compliance Officer das Drittanbieter-Daten Postfach im Outlook-Desktop Client öffnen können. Weitere Informationen finden Sie unter [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Aktivieren Sie die folgenden kompatibilitätsbezogenen Office 365 Funktionen für das Drittanbieter-Daten Postfach:
    
    - Aktivieren des Archivpostfachs siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md). Auf diese Weise können Sie Speicherplatz im primären Postfach freigeben, indem Sie eine Archivrichtlinie einrichten, mit der Datenelemente von Drittanbietern in das Archivpostfach verschoben werden. Dadurch erhalten Sie unbegrenzten Speicher für drittanbieterdaten.
    
    - Aktivieren Sie für das Drittanbieterdaten-Postfach das Beweissicherungsverfahren. Sie können auch eine Office 365-Aufbewahrungsrichtlinie im Security and Compliance Center anwenden. Beim Platzieren dieses Postfachs bleiben Datenelemente von Drittanbietern (auf unbestimmte Zeit oder für eine bestimmte Dauer) erhalten und verhindern, dass Sie aus dem Postfach gelöscht werden. Lesen Sie eines der folgenden Themen:
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Übersicht über Aufbewahrungsrichtlinien in Office 365](retention-policies.md)
    
    - Aktivieren der postfachüberwachungsprotokollierung für den Besitzer-, Stellvertreter-und Administratorzugriff auf das Daten Postfach eines Drittanbieters; Weitere Informationen finden Sie unter [Aktivieren der postfachüberwachung in Office 365](enable-mailbox-auditing.md). Auf diese Weise können Sie alle von Benutzern ausgeführten Aktivitäten überwachen, die Zugriff auf das Daten Postfach eines Drittanbieters haben.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Schritt 3: Benutzerpostfächer für Drittanbieterdaten konfigurieren

Als Nächstes müssen Sie die Benutzerpostfächer für die Unterstützung von Drittanbieterdaten konfigurieren. Führen Sie diese Aufgaben mithilfe der Exchange-Verwaltungskonsole oder mithilfe der entsprechenden Windows PowerShell-Cmdlets aus.
  
1. Aktivieren Sie das Archivpostfach für jeden Benutzer. siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md).
    
2. Platzieren von Benutzerpostfächern für das Beweissicherungsverfahren oder Anwenden einer Office 365 Aufbewahrungsrichtlinie Lesen Sie eines der folgenden Themen: 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Übersicht über Aufbewahrungsrichtlinien in Office 365](retention-policies.md)
    
    Wie bereits weiter oben erwähnt, können Sie beim Aktivieren des Beweissicherungsverfahrens für Postfächer festlegen, wie lange Elemente aus einer Drittanbieter-Datenquelle aufbewahrt werden sollen. Sie können auch festlegen, dass sie dauerhaft aufbewahrt werden sollen.

## <a name="step-4-provide-your-partner-with-information"></a>Schritt 4: Bereitstellen von Informationen für Ihren Partner

Im letzten Schritt müssen Sie dem Partner die folgenden Informationen bereitstellen, damit er den Connector für die Verbindung mit Office 365-Organisation konfigurieren kann, um Daten in Benutzerpostfächer und das Drittanbieterdaten-Postfach zu importieren. 
  
- Der Endpunkt, der zum Herstellen einer Verbindung mit dem Azure-Dienst in Office 365 verwendet wird:

    ```text
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Die Anmeldeinformationen (Office 365 Benutzer-ID und das Kennwort) des Drittanbieter-Daten Postfachs, das Sie in Schritt 2 erstellt haben. Diese Anmeldeinformationen sind erforderlich, damit der Partnerconnector auf Elemente zugreifen und sie in das Drittanbieterdaten-Postfach importieren kann.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory

Ab dem 30. September 2018 wird der Azure-Dienst in Office 365 zunächst die moderne Authentifizierung in Exchange Online verwenden, um Daten Konnektoren von Drittanbietern zu authentifizieren, die versuchen, eine Verbindung mit Ihrer Office 365 Organisation herzustellen, um Daten zu importieren. Der Grund für diese Änderung besteht darin, dass die moderne Authentifizierung mehr Sicherheit bietet als die aktuelle Methode, die auf Whitelisting-Drittanbieter-Konnektoren basiert, die den zuvor beschriebenen Endpunkt zum Herstellen einer Verbindung mit dem Azure-Dienst verwenden.

Damit ein Drittanbieter-Daten Konnektor mithilfe der neuen modernen Authentifizierungsmethode eine Verbindung mit Office 365 herstellen kann, muss ein Administrator in Ihrer Office 365 Organisation zustimmen, dass der Connector als vertrauenswürdige Dienstanwendung in Azure Active Directory registriert wird. Dies erfolgt durch Annahme einer Berechtigungsanforderung, damit der Connector auf die Daten Ihrer Organisation in Azure Active Directory zugreifen kann. Nachdem Sie diese Anforderung angenommen haben, wird der Drittanbieter-Daten Konnektor als Unternehmensanwendung zu Azure Active Directory hinzugefügt und als Dienstprinzipal dargestellt. Weitere Informationen zum Zustimmungsprozess finden Sie unter [Mandanten-admin-Zustimmung](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Hier sind die Schritte zum Zugreifen auf und akzeptieren der Anforderung zum Registrieren des Connectors:

1. Wechseln Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) , und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administrators an.<br/><br/>Das folgende Dialogfeld wird angezeigt. Sie können die Carets erweitern, um die Berechtigungen zu überprüfen, die dem Connector zugewiesen werden.<br/><br/>![Das Dialogfeld Berechtigungsanforderung wird angezeigt.](media/O365-ThirdPartyDataConnector-OptIn1.png)
2. Klicken Sie auf **Annehmen**.

Nachdem Sie die Anforderung angenommen haben, wird das [Azure-Portal](https://portal.azure.com) angezeigt. Um die Liste der Anwendungen für Ihre Organisation anzuzeigen, klicken Sie auf **Azure Active Directory** > **Enterprise Applications**. Der Office 365 Drittanbieter-Daten Connector wird auf dem Blade **Enterprise-Anwendungen** aufgeführt.

> [!IMPORTANT]
> Nach dem 30. September 2018 werden drittanbieterdaten nicht mehr in Postfächer in Ihrer Organisation importiert, wenn Sie keinen Daten Konnektor eines Drittanbieters in Azure Active Directory registrieren. Hinweis vorhandene Drittanbieter-Daten-Konnektoren (die vor dem 30. September 2018 erstellt wurden) müssen ebenfalls in Azure Active Directory registriert werden, indem Sie das Verfahren in Schritt 5 ausführen.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Widerrufen der Zustimmung für einen Daten Konnektor eines Drittanbieters

Nachdem Ihre Organisation der Berechtigungsanforderung zugestimmt hat, um einen Drittanbieter-Daten Konnektor in Azure Active Directory zu registrieren, kann Ihre Organisation diese Zustimmung jederzeit widerrufen. Das Widerrufen der Zustimmung für einen Connector bedeutet jedoch, dass Daten aus der Drittanbieter-Datenquelle nicht mehr in Office 365 importiert werden.

Um die Zustimmung für einen Drittanbieter-Datenconnector zu widerrufen, können Sie die Anwendung (durch Löschen des entsprechenden Dienst Prinzipals) aus Azure Active Directory mithilfe des Blades **Enterprise-Anwendungen** im Azure-Portal oder mithilfe des [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell löschen. Sie können auch das Cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell verwenden.
  
## <a name="more-information"></a>Weitere Informationen

- Wie bereits weiter oben erläutert, werden Elemente aus Drittanbieter-Datenquellen als E-Mail-Nachrichten in Exchange-Postfächer importiert. Der Partner Connector importiert das Element mithilfe eines Schemas, das für die Office 365-API erforderlich ist. Die folgende Tabelle beschreibt die Nachrichteneigenschaften eines Elements aus einer Drittanbieter-Datenquelle, nachdem es als E-Mail-Nachricht in ein Exchange-Postfach importiert wurde. Zudem ist angegeben, wenn die Nachrichteneigenschaft zwingend erforderlich ist. Erforderliche Eigenschaften müssen aufgefüllt werden. Wenn ein Element eine obligatorische Eigenschaft fehlt, wird es nicht in Office 365 importiert. Beim Importvorgang wird eine Fehlermeldung mit der Erläuterung zurückgegeben, warum ein Element nicht importiert wurde und welche Eigenschaft fehlt.
    
    |**Nachrichteneigenschaft**|**Erforderlich?**|**Beschreibung**|**Beispielwert**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Ja  <br/> |Der Benutzer, der das Element in der Drittanbieter-Datenquelle ursprünglich erstellt oder gesendet hat. Der Partner Connector versucht, die Benutzer-ID des Quellelements (beispielsweiseeines Twitter-Handles) einem Office 365 Benutzerkontos für alle Teilnehmer (Benutzer in den Feldern von und bis) zuzuordnen. Eine Kopie der Nachricht wird in das Postfach jedes Teilnehmers importiert. Wenn keiner der Teilnehmer aus dem Element einem Office 365-Benutzerkonto zugeordnet werden kann, wird das Element in Office 365 in das Archivierungs Postfach eines Drittanbieters importiert.  <br/> <br/> Der Teilnehmer, der als Absender des Elements identifiziert wird, muss über ein aktives Postfach in der Office 365 Organisation verfügen, in das das Element importiert wird. Wenn der Absender nicht über ein aktives Postfach verfügt, wird der folgende Fehler zurückgegeben:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Ja  <br/> |Der Benutzer, der ein Element erhalten hat (wenn für ein Element in der Datenquelle zutreffend).  <br/> | `bob@contoso.com` <br/> |
    |**Betreff** <br/> |Nein  <br/> |Der Betreff des Quellelements.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**Datum** <br/> |Ja  <br/> |Das Datum, an dem das Element ursprünglich erstellt oder in der Kundendatenquelle veröffentlicht wurde. Beispielsweise dieses Datum, an dem eine Twitter-Nachricht getweetet wurde.  <br/> | `01 NOV 2015` <br/> |
    |**Text** <br/> |Nein  <br/> |Der Inhalt der Nachricht oder des Beitrags. Bei einigen Datenquellen kann der Inhalt dieser Eigenschaft mit dem Inhalt der Eigenschaft **SUBJECT** identisch sein. Während des Importvorgangs versucht der Partner Connector, die vollständige Genauigkeit von der Inhaltsquelle wie möglich beizubehalten. Soweit möglich, werden Dateien, Grafiken oder andere Inhalte aus dem Textkörper des Quellelements in diese Eigenschaft einbezogen. Andernfalls wird der Inhalt aus dem Quellelement in die Eigenschaft **ATTACHMENT** einbezogen. Der Inhalt dieser Eigenschaft hängt vom Partner-Konnektor und der Funktion der QuellPlattform ab.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**Anlage** <br/> |Nein  <br/> |Wenn ein Element in der Datenquelle (beispielsweise ein tweet in Twitter oder eine Chatnachrichten Unterhaltung) über eine angefügte Datei verfügt oder Bilder enthält, versucht der Partner Connect zunächst, Anlagen in die **Body** -Eigenschaft einzuschließen. Wenn dies nicht möglich ist, wird es zur * * Attachment * *-Eigenschaft hinzugefügt. Weitere Beispiele für Anlagen sind „Gefällt mir“-Angaben in Facebook, Metadaten aus der Inhaltsquelle und Antworten auf eine Nachricht oder einen Beitrag.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Ja  <br/> | Dies ist eine Eigenschaft mit mehreren Werten, die vom Partnerconnector erstellt und mit Werten gefüllt wird. Das Format dieser Eigenschaft ist `IPM.NOTE.Source.Event`. (Diese Eigenschaft muss mit `IPM.NOTE`beginnen. Dieses Format ähnelt dem für die `IPM.NOTE.X` Nachrichtenklasse.) Diese Eigenschaft enthält die folgenden Informationen:  <br/><br/>`Source`: Gibt die Datenquelle eines Drittanbieters an; zum Beispiel Twitter, Facebook oder BlackBerry.  <br/> <br/>  `Event`: Gibt die Art der Aktivität an, die in der Drittanbieter-Datenquelle ausgeführt wurde, die die Elemente erstellt hat; zum Beispiel ein tweet in Twitter oder ein Beitrag in Facebook. Ereignisse sind für die jeweilige Datenquelle spezifisch.  <br/> <br/>  Ein Zweck dieser Eigenschaft ist es zum Beispiel, bestimmte Elemente basierend auf der Datenquelle zu filtern, aus der ein Element stammt, oder basierend auf dem Typ des Ereignisses. So könnten Sie in einer eDiscovery-Suche zum Beispiel eine Suchabfrage erstellen, um alle Tweets zu finden, die von einem bestimmten Benutzer gepostet wurden.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Wenn Elemente in Office 365 erfolgreich in Postfächer importiert werden, wird ein eindeutiger Bezeichner als Teil der HTTP-Antwort zurück an den Aufrufer zurückgegeben. Dieser Bezeichner, der `x-IngestionCorrelationID`aufgerufen wird, kann für nachfolgende Problembehandlungszwecke von Partnern zur End-to-End-Überwachung von Elementen verwendet werden. Es wird empfohlen, dass Partner diese Informationen entsprechend erfassen und sammeln. Im Folgenden ist ein Beispiel einer HTTP-Antwort mit diesem Bezeichner aufgeführt:

    ```text
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- Sie können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um nach Elementen zu suchen, die in Office 365 von einer Drittanbieter-Datenquelle in Postfächer importiert wurden. Um gezielt nach diesen importierten Elementen zu suchen, können Sie die folgenden Nachrichten Eigenschaftswert-Paare im Feld Stichwort für eine Inhaltssuche verwenden.
    
  - **`kind:externaldata`**: Verwenden Sie dieses Eigenschaftswert-Paar, um alle Drittanbieter-Datentypen zu durchsuchen. Um beispielsweise nach Elementen zu suchen, die aus einer Drittanbieter-Datenquelle importiert wurden und das Wort "Contoso" in der Subject-Eigenschaft des importierten Elements enthielten, würden Sie `kind:externaldata AND subject:contoso`die Stichwortabfrage verwenden.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: Verwenden Sie dieses Eigenschaftswert-Paar, um nur einen Typ von drittanbieterdaten zu suchen. Wenn Sie beispielsweise nur Facebook-Daten durchsuchen möchten, die das Wort "Contoso" in der Subject-Eigenschaft enthalten, verwenden `itemclass:ipm.externaldata.Facebook* AND subject:contoso`Sie die Stichwort-Abfrage. 

  Eine vollständige Liste der Werte, die für Drittanbieter-Datentypen für die `itemclass` Eigenschaft verwendet werden sollen, finden Sie unter [Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Office 365 importiert wurden](use-content-search-to-search-third-party-data-that-was-imported.md) .
    
   Weitere Informationen zur Verwendung der Inhaltssuche und zum Erstellen von Stichwortsuchabfragen finden Sie unter:
    
  - [Inhaltssuche in Office 365](content-search.md)
    
  - [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
 
