---
title: Weitere Erfahrungs Informationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Weitere Informationen zur Kundenzufriedenheit beim Wechsel von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365 Diensten im neuen rechenzentrumsbereich.'
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551875"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Weitere Erfahrungs Informationen für die Migration von Microsoft Cloud Deutschland 

Die folgenden Abschnitte bieten zusätzliche Informationen zu Kundenerfahrungen.

## <a name="services"></a>Dienste

### <a name="azure-ad"></a>Azure AD

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Azure AD Mandant in Microsoft Cloud Deutschland wurde in Office 365 Dienste kopiert. | Azure AD den Mandanten in Office 365 Dienste kopiert. Mandanten-und Benutzer-IDs bleiben erhalten. Azure Ad Service Anrufe werden von Microsoft Cloud Deutschland zu Office 365 Diensten umgeleitet und sind für Dienste transparent. | Alle Office-Kunden | -Allgemeine Datenschutzverordnung (dsgvo) Datensubjekt Anforderungen (DSRs) werden aus dem Azure-Verwaltungsportal für zukünftige Anforderungen ausgeführt. Alle Legacy-oder nicht-Kunden-Diagnosedaten, die in Microsoft Cloud Deutschland wohnhaft sind, werden am oder vor Ablauf von 30 Tagen gelöscht. <br><br> -Kunden, die Verbund Authentifizierungen mit Active Directory Verbunddiensten (AD FS) verwenden, sollten keine Änderungen an den Aussteller-URIs vornehmen, die bei der Migration für alle Authentifizierungen mit lokalem Active Directory verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Herausgeber-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von einem _verwalteten_ in einen _Verbund_ konvertiert wird und umgekehrt. Es wird empfohlen, dass Kunden keine Verbunddomäne im Azure AD migrierten Mandanten hinzufügen, entfernen oder konvertieren. Herausgeber-URIs können geändert werden, nachdem die Migration vollständig abgeschlossen wurde. <br><br> -Multi-Factor Authentication (MFA)-Anforderungen, die Microsoft Authenticator verwenden, werden als Benutzer-ObjectID (eine GUID) angezeigt, während der Mandant in Office 365 Dienste kopiert wird. MFA-Anforderungen werden trotz dieses Anzeigeverhaltens wie erwartet ausgeführt.  Microsoft Authenticator-Konten, die mithilfe der Endpunkte von Office 365 Diensten aktiviert wurden, werden der Benutzerprinzipalname (User Principal Name, UPN) angezeigt.  Mit Microsoft Cloud Deutschland-Endpunkten hinzugefügte Konten zeigen die Benutzer-ObjectID an, funktionieren jedoch sowohl mit Microsoft Cloud Deutschland als auch mit Office 365-Dienstendpunkten.  |
| Richten Sie AuthServer lokal ein, das auf den globalen STS-Dienst verweist. | Dadurch wird sichergestellt, dass Anforderungen von Benutzern, die zu Microsoft Cloud Deutschland für Exchange-Verfügbarkeitsanforderungen migrieren, die auf die lokale Hybridumgebung abzielen, für den Zugriff auf den lokalen Dienst authentifiziert werden. Auf ähnliche Weise wird die Authentifizierung von Anforderungen von lokalen zu Office 365 Dienstendpunkten sichergestellt. | Exchange Online Kunden mit Hybriden (lokalen) Bereitstellungen | Nachdem Azure AD Migration abgeschlossen ist, muss der Administrator der lokalen Exchange-Topologie (Hybrid) einen neuen Authentifizierungsdienst-Endpunkt für die Office 365 Dienste hinzufügen. Ersetzen Sie mit diesem Befehl in Exchange PowerShell `<TenantID>` durch die Mandanten-ID Ihrer Organisation (im Azure-Portal unter **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Wenn diese Aufgabe nicht abgeschlossen wird, können hybride Frei/Gebucht-Anforderungen keine Informationen für Postfachbenutzer bereitstellen, die von Microsoft Cloud Deutschland zu Office 365 Diensten migriert wurden.  |
| Migration von Azure-Ressourcen. | Kunden, die Office 365-und Azure-Ressourcen verwenden (beispielsweise Netzwerk, COMPUTE und Speicher), führen die Migration von Ressourcen zur Instanz von Office 365 Services durch. Diese Migration ist eine Verantwortung für Kunden. Nachrichten Center-Beiträge signalisieren den Start. Die Migration muss vor Abschluss der Azure AD Organisation in der Office 365 Dienstumgebung abgeschlossen sein. | Azure-Kunden | Informationen zu Azure-Migrationen finden Sie im Textbuch zur Azure-Migration, [Übersicht über Migrations Anleitungen für Azure Deutschland](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

Bei Verwendung von " **Setup-UserPhoto**":

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Die neue Region Deutschland wird einem vorhandenen Organisations Setup hinzugefügt, und Postfächer werden in Office 365 Dienste verschoben. | In Exchange Online Konfiguration wird die neue Region "Go-local Deutsch" zur Übergangs Organisation hinzugefügt. Diese Office 365-Dienste-Region ist als Standard festgelegt, wodurch der interne Lastenausgleichsdienst das Neuverteilen von Postfächern an die entsprechende Standardregion in Office 365 Diensten ermöglicht. Bei diesem Übergang befinden sich die Benutzer auf beiden Seiten (Deutschland oder Office 365 Dienste) in derselben Organisation und können entweder den URL-Endpunkt verwenden. |  Exchange Online | Wenn ein Benutzerpostfach migriert wurde, aber ein Administratorpostfach nicht migriert wurde oder umgekehrt, können Administratoren nicht die Ausführung von " **UserPhoto**", ein PowerShell-Cmdlet, ausführen. In diesem Fall muss ein Administrator eine zusätzliche Zeichenfolge `ConnectionUri` während der Verbindung übergeben, die mit der folgenden Syntax eingerichtet wurde: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> Hierbei `<user_email>` ist der Platzhalter für die e-Mail-ID des Benutzers, dessen Foto mithilfe von " **UserPhoto**" geändert werden muss. |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

Wenn Sie eine hybride, lokale Bereitstellung verwenden:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
|Beenden oder löschen Sie alle Onboarding-oder offboarding-Verschiebungen von Postfächern.  | Dadurch wird sichergestellt, dass die Verschiebeanforderungen nicht mit einem Fehler fehlschlagen. | Exchange Online Kunden mit Hybriden (lokalen) Bereitstellungen | Erforderliche Aktion. Wenn dies nicht der Fall ist, kann dies zu einem Ausfall des Diensts oder von Software Clients führen. |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-Ressourcen | Kunden mit Microsoft Dynamics werden vom Engineering oder von der kurzphase zum Übergang von Dynamics zur Office 365-Dienstinstanz eingesetzt. * | Microsoft Dynamics 365-Kunden | – Nach der Migration überprüft der Administrator die Organisation. <br><br> -Der Administrator ändert bei Bedarf Workflows. <br><br> -Der Administrator löscht den AdminOnly-Modus entsprechend. <br><br> -Der Administrator ändert je nach Bedarf den Organisationstyp aus der _Sandbox_. <br><br> -Endbenutzer über die neue URL Benachrichtigen, um auf die Instanz (org) zuzugreifen. <br><br> – Aktualisieren Sie alle eingehenden Verbindungen mit der neuen Endpunkt-URL. <br><br> -Der Dynamics-Dienst steht Benutzern während des Übergangs nicht zur Verfügung. <br><br> -Benutzer müssen die Organisations Integrität und-Features nach der Migration der einzelnen org-Objekte überprüfen.  |
|||||

\* (i) Kunden mit Microsoft Dynamics 365 müssen in diesem Migrationsszenario, wie im angegebenen Migrationsprozess definiert, Maßnahmen ergreifen. (II) ein Fehler des Kunden, um Maßnahmen zu ergreifen, bedeutet, dass Microsoft nicht in der Lage ist, die Migration abzuschließen. (III) Wenn Microsoft die Migration aufgrund der Untätigkeit des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab. 


### <a name="power-bi"></a>Power BI

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Power BI-Ressourcen | Kunden mit Microsoft Power BI werden nach dem manuellen Auslösen eines vorhandenen PBI-Migrationstools, das die Power BI auf die Office 365-Dienstinstanz umwandelt, von Engineering oder Kurzzeit eingesetzt.\*\* | Microsoft Power BI-Kunden | -Die folgenden Power BI-Elemente werden _nicht_ übergangen und müssen neu erstellt werden: <br><br> -Echtzeitdaten Sätze (beispielsweise Streaming oder Push-Datasets). <br> -Power BI lokale Data Gateway-Konfiguration und-Datenquelle. <br> -Berichte, die auf den Echtzeitdaten Sätzen basieren, werden nach der Migration nicht mehr verfügbar sein und müssen neu erstellt werden. <br><br> -Power BI-Dienste sind für Benutzer während des Übergangs nicht verfügbar. Die Nichtverfügbarkeit des Diensts sollte nicht mehr als 24 Stunden betragen. <br><br> -Benutzer müssen Datenquellen und ihre lokalen Datengateways mit dem Power BI-Dienst nach der Migration neu konfigurieren.  Bis dies der Fall ist, können Benutzer diese Datenquellen nicht verwenden, um geplante Aktualisierungen und/oder direkte Abfragen für diese Datenquellen durchzuführen. <br><br> -Kapazitäten und Premium-Arbeitsbereiche können nicht migriert werden. Kunden müssen alle Kapazitäten vor der Migration löschen und nach der Migration neu erstellen. Stellen Sie nach Bedarf Arbeitsbereiche wieder auf Kapazitäten ein.  |
|||||

\*\* (i) Kunden mit Microsoft Power BI müssen in diesem Migrationsszenario, wie im angegebenen Migrationsprozess definiert, Maßnahmen ergreifen. (II) ein Fehler des Kunden, um Maßnahmen zu ergreifen, bedeutet, dass Microsoft nicht in der Lage ist, die Migration abzuschließen. (III) Wenn Microsoft die Migration aufgrund der Untätigkeit des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab. 


### <a name="office-apps"></a>Office-Apps

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Clients Office Online während des Office-Client Cutover Azure AD den MANDANTENBEREICH so ab, dass er auf die Office 365 Dienste verweist.<!--v-gmoor: What?--> | Mit dieser Konfigurationsänderung können Office-Clients aktualisiert und auf die Endpunkte der Office 365 Dienste verweist werden. | Alle Office-Kunden | – Entfernen Sie MSOID CNAME aus dem kundeneigenen DNS, sofern vorhanden. <br><br> -Benachrichtigen Sie die Benutzer, dass _alle_ Office-Apps geschlossen werden sollen, und melden Sie sich dann wieder an (oder erzwingen Sie, dass Clients neu gestartet werden und Benutzer sich anmelden), damit Office-Clients die Änderung aufnehmen können. <br><br> -Benutzer und Helpdesk-Mitarbeiter benachrichtigen, dass Benutzern *möglicherweise* ein Office-Banner angezeigt wird, in dem Sie aufgefordert werden, Office-Apps innerhalb von 72 Stunden nach der Cutover zu reaktivieren. <br><br> -Alle Office-Anwendungen auf persönlichen Computern müssen geschlossen sein, und die Benutzer müssen sich abmelden und sich dann erneut anmelden. Melden Sie sich in der gelben aktivierungsleiste zur Reaktivierung für Office 365 Dienste an. <br><br> -Freigegebene Computer erfordern Aktionen, die den persönlichen Computern ähneln, und erfordern keine spezielle Vorgehensweise. <br><br> -Auf mobilen Geräten müssen sich Benutzer von apps abmelden, Sie schließen und sich dann erneut anmelden. |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>Während der Migration


### <a name="exchange-online"></a>Exchange Online

Für eDiscovery:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Während der Migration führen eDiscovery-Suchvorgänge einen Fehler aus oder geben 0 Ergebnisse für SharePoint Online, OneDrive für Unternehmen und Exchange Online migrierte Speicherorte zurück. | Während der Migration können Kunden weiterhin Fälle, Aufbewahrungen, Suchvorgänge und Exporte im Security & Compliance Center, einschließlich der Inhaltssuche, erstellen.  Durchsuchen von SharePoint Online-, OneDrive für Unternehmen-und Exchange Online-Speicherorten, die migriert wurden, werden jedoch entweder 0 Ergebnisse zurückgegeben oder ein Fehler generiert. Informationen zur Behebung finden Sie in der Spalte _IMPACT_ . | Alle Kunden, die eDiscovery verwenden |  Für den Fall, dass bei einer Suche 0 Ergebnisse oder ein Fehler während der Migration zurückgegeben wird, führen Sie die folgende Aktion für SharePoint Online aus: <br><br>  Laden Sie Websites direkt von SharePoint Online/OneDrive für Unternehmen Website herunter, indem Sie die Anweisungen unter [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)befolgen. Für diese Methode sind SharePoint Online Administratorberechtigungen oder schreibgeschützte Berechtigungen für die Website erforderlich. <br><br> Wenn Grenzwerte überschritten werden, wie unter [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)erläutert, können Kunden den OneDrive für Unternehmen synchronisierungsclient verwenden, indem Sie die Anweisungen unter [Synchronisieren von SharePoint-und Microsoft Teams-Dateien mit Ihrem Computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)befolgen. <br><br> -Exchange Online <br><br> - [In-Place-eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| SharePoint und OneDrive werden übergangen. | SharePoint und OneDrive werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365 Diensten migriert. Vorhandene Microsoft Cloud Deutschland-URLs werden beibehalten ( `contoso.sharepoint.de` ). Token, die von Microsoft Cloud Deutschland oder Office 365 Diensten ausgestellt wurden, sind während des Übergangs gültig. | SharePoint-Kunden | Inflight SharePoint 2013 Workflows werden während der Migration unterbrochen und müssen nach der Migration erneut veröffentlicht werden. |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype for Business Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Skype for Business zu Teams. | Vorhandene Skype for Business Kunden werden zu Office 365 Diensten in Europa migriert und anschließend zu Microsoft Teams in der Region Deutschland Office 365 Dienste gewechselt. | Skype for Business Kunden |  PowerShell verwendet zum Verwalten von Einstellungen und Richtlinien für Ihren Mandanten und Ihre Benutzer. Fügen Sie beim Herstellen einer Verbindung mit einer PowerShell-Sitzung Folgendes hinzu: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>Tipps nach der Migration

### <a name="azure-ad"></a>Azure AD

Für Hybrid:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren Sie Azure AD Connect. | Nachdem der Schnitt auf Azure AD abgeschlossen ist, verwendet die Organisation Office 365 Dienste vollständig und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An dieser Stelle muss der Kunde sicherstellen, dass der Delta-Synchronisierungsprozess abgeschlossen wurde, und anschließend den Zeichenfolgenwert von `AzureInstance` 3 (Microsoft Cloud Deutschland) in den Registrierungspfad auf 0 ändern `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Hybrid Azure AD – verbundene Organisationen | Ändern Sie den Wert des `AzureInstance` Registrierungsschlüssels. Andernfalls führt dies dazu, dass Objekte nicht synchronisiert werden, nachdem die Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

Für die Verbundauthentifizierung:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Entfernen von Vertrauensstellungen der vertrauenden Seite von Microsoft Cloud Deutschland AD FS. | Nachdem der Schnitt auf Azure AD abgeschlossen ist, verwendet die Organisation Office 365 Dienste vollständig und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Seite an die Microsoft Cloud Deutschland-Endpunkte entfernen. Dies kann nur erfolgen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte deuten, wenn Azure AD als Identitätsanbieter (IDP) genutzt wird. | Organisationen für die Verbundauthentifizierung | Keine. |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Für Azure AD:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Anforderungen für die Teilnahme an einer Azure Ad Gruppe in den letzten 30 Tagen vor der Migration müssen erneut angefordert werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde. | Endbenutzer müssen die Zugriffs Konsole verwenden, um eine erneute Anforderung zum Beitritt zu einer Azure Ad Gruppe zu übermitteln, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden. | Endbenutzer, deren Azure Ad Gruppen Genehmigungsanforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden |  Als Endbenutzer: <ol><li>Navigieren Sie zu [Access Panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Hier finden Sie eine Azure Ad Gruppe, für die die Mitgliedschaftsgenehmigung in 30 Tagen vor der Migration aussteht.</li><li>Anforderung, erneut an der Azure Ad Gruppe teilzunehmen.</li></ol> Anforderungen für die Teilnahme an einer Gruppe, die weniger als 30 Tage vor der Migration aktiv ist, können nicht genehmigt werden, es sei denn, Sie werden nach der Migration erneut angefordert. |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

Für DNS:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienste-Endpunkte. | Kunden verwaltete DNS-Einträge, die auf Office 365 Deutschland deuten, müssen so aktualisiert werden, dass Sie auf die Endpunkte der Office 365 Dienste verweist. | Alle Office-Kunden | Erforderliche Aktion. Wenn dies nicht der Fall ist, kann dies zu einem Ausfall des Diensts oder von Software Clients führen. |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Für Dienste von Drittanbietern für Office 365 Dienstendpunkte:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren von Partnern und Drittanbieterdiensten für Office 365 Dienstendpunkte. | -Drittanbieterdienste und-Partner, die auf Office 365 Deutschland deuten, müssen so aktualisiert werden, dass Sie auf die Endpunkte der Office 365 Dienste verweist. Beispiel: Erneutes Registrieren, in Abstimmung mit ihren Lieferanten und Partnern, die Version der Gallery-App der Anwendungen, falls verfügbar. <br><br> -Richten Sie alle benutzerdefinierten Anwendungen, die die Graph-API nutzen, von `graph.microsoft.de` in `graph.microsoft.com` . Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls diese genutzt werden. <br><br> – Ändern Sie alle nicht-Anbieter-Unternehmensanwendungen, um Sie auf die weltweiten Endpunkte umzuleiten.  | Alle Office-Kunden | Erforderliche Aktion. Wenn dies nicht der Fall ist, kann dies zu einem Ausfall des Diensts oder von Software Clients führen. |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

Wenn Sie eine hybride Exchange-Konfiguration verwenden:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Führen Sie den Assistenten für die Hybrid Konfiguration (HCW) für Office 365 Dienste erneut aus. | Die vorhandene HCW-Konfiguration soll Microsoft Cloud Deutschland unterstützen. Wenn die Migration von Exchange-Diensten abgeschlossen ist, wird die lokale Konfiguration von Microsoft Cloud Deutschland entkoppelt. | Exchange Online Kunden, die eine hybridbereitstellung durchführen | Erforderliche Aktion. Wenn dies nicht der Fall ist, kann dies zu einem Ausfall des Diensts oder von Software Clients führen. Benachrichtigen Sie Clients vor Beginn der Exchange-Postfachmigration (mit einer Frist von 5 oder mehr Tagen), dass Sie alle Onboarding-oder offboarding-Verschiebungen ihrer Postfächer beenden und löschen sollten.  Wenn dies nicht der Fall ist, werden Fehler in ihren Verschiebeanforderungen angezeigt. <br><br> – Nachdem die Exchange-Postfachmigration abgeschlossen ist, Benachrichtigen Sie die Clients, dass Sie das Onboarding fortsetzen können und offboarding verschoben werden. <br> Das Ausführen von **Test-MigrationServerAvailabiilty**, ein PowerShell-Cmdlet, während der Migration von Exchange von Microsoft Cloud Deutschland zu Office 365 Diensten funktioniert möglicherweise nicht. Es funktioniert jedoch ordnungsgemäß, nachdem die Migration abgeschlossen ist. <br><br> Wenn Clients bei der Migration von Postfächern auf Probleme mit Anmeldeinformationen oder Autorisierung stoßen, können die Benutzer ihre lokalen Administratoranmeldeinformationen erneut in den Migrations Endpunkt eingeben `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` , oder indem Sie die gleiche Einstellung mithilfe der Exchange-Systemsteuerung (ECP) durchführen.  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

Für eDiscovery:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
|  Alle SharePoint Online-, OneDrive für Unternehmen-und Exchange Online-Speicherorte wurden zusammen mit dem Security and Compliance Center (SCC) migriert. | Alle eDiscovery-Aktivitäten sollten vom weltweiten Mandanten ausgeführt werden. Suchvorgänge werden nun 100% erfolgreich ausgeführt.  Fehler oder Fehler sollten normalen Support Kanälen entsprechen. | Alle Kunden, die eDiscovery verwenden | Keine. |
| Entfernen organisationsweiter Aufbewahrungsrichtlinien, die während der Schritte vor der Migration erstellt wurden | Kunden können die organisationsweiten Aufbewahrungsrichtlinien entfernen, die während der Arbeit der Kunden vor der Migration erstellt wurden. | Alle Kunden, die eine Aufbewahrungsrichtlinie im Rahmen der Schritte vor der Migration angewendet haben. | Keine. |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Veröffentlichen Sie SharePoint 2013 Workflows erneut. | Bei der Arbeit vor der Migration haben wir die Anzahl der SharePoint 2013-Workflows reduziert. Nachdem die Migration abgeschlossen ist, kann der Kunde die Workflows erneut veröffentlichen. | Alle Office-Kunden | Dies ist eine erforderliche Aktion. Wenn dies nicht der Fall ist, können Benutzer Verwirrungen auftreten und Anrufe bei Helpdesks durchführen. |
| Freigeben von Elementen über Outlook | Das Freigeben von Elementen über Outlook funktioniert nicht mehr nach Mandanten-Cutover. | SharePoint Online und OneDrive for Business | -In SharePoint Online und OneDrive für Unternehmen können Sie Elemente über Outlook freigeben. Nach dem Drücken der Outlook-Schaltfläche wird ein freigegebener Link erstellt und in einer neuen Nachricht im Outlook Web App abgelegt. <br><br> – Nach dem Mandanten-Cutover funktioniert diese Methode der Freigabe nicht. Wir erkennen, dass es sich um ein bekanntes Problem handelt. Da sich dieses Outlook-Feature jedoch im Pfad der veralteten Funktion befindet, ist die Behebung des Problems erst dann geplant, wenn die veraltete Aufgabe ausgeführt wird. |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>Nächster Schritt

[Grundlegendes zu Migrationsphasen Aktionen und Auswirkungen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Migrationsphasen-Aktionen und-Auswirkungen](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Diensten](ms-cloud-germany-transition-add-general.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
