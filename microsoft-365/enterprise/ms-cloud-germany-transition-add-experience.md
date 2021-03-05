---
title: Migrationsphasenaktionen und Auswirkungen für die Migration von Microsoft Cloud Deutschland (erweitert)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Zusammenfassung: Zusätzliche Kundeninformationen zur Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 26db69583bac68723d5d57b07abb856c8190d9b1
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454467"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Migrationsphasenaktionen und Auswirkungen für die Migration von Microsoft Cloud Deutschland (erweitert) 

Mandanten-Migrationen von Microsoft Cloud Deutschland in die Region Deutschland der Office 365-Dienste von Microsoft werden als eine Reihe von Phasen und deren konfigurierten Aktionen für jeden Workload ausgeführt. Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren.

![Die neun Phasen der Migration in die neuen deutschen Rechenzentren](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Die folgenden Abschnitte enthalten weitere Informationen zu den Erfahrungen der Kunden beim Wechsel von Microsoft Cloud Deutschland zu Office 365-Dienste in der neuen deutschen Rechenzentrumsregion.

## <a name="services"></a>Dienste

Zwischen Phase 2 von 9 und Phase 3 von 9 ist möglicherweise kein Zugriff auf das Partnerportal möglich. Während dieser Zeit kann der Partner möglicherweise nicht auf die Mandanteninformationen im Partnerportal zugreifen. Da jede Migration unterschiedlich ist, kann die Dauer der Barrierefreiheit in Stunden sein. 

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (Phase 2 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Azure AD-Mandant in Microsoft Cloud Deutschland wird zu Office 365-Diensten kopiert. | Azure AD kopiert den Mandanten zu den Office 365-Diensten. Mandanten- und Benutzer-IDs bleiben erhalten. Azure AD-Dienstaufrufe werden von Microsoft Cloud Deutschland zu Office 365-Diensten umgeleitet und sind für Dienste transparent. | Alle Office-Kunden | – Allgemeine Datenbetreffetreffsanforderungen (DSRs) für die Datenschutzbestimmungen (DSGVO) werden im Azure-Verwaltungsportal für zukünftige Anforderungen ausgeführt. Alle älteren oder Nicht-Kunden-Diagnosedaten, die sich in Microsoft Cloud Deutschland befinden, werden spätestens nach 30 Tagen gelöscht. <br><br> – Kunden, die Verbundauthentifizierungen mit Active Directory-Verbunddiensten (AD FS) verwenden, sollten keine Änderungen an Aussteller-URIs vornehmen, die während der Migration für alle Authentifizierungen mit lokalem Active Directory verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Aussteller-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von _verwaltet_ zu _Verbund_ oder umgekehrt konvertiert wird. Wir empfehlen, dass Kunden keine Verbunddomäne, die migriert wurde, im Azure AD-Mandanten hinzufügen, entfernen oder konvertieren. Aussteller-URIs können nach Abschluss der Migration geändert werden. <br><br> – MFA-Anforderungen (Multi-Factor Authentication), die Microsoft Authenticator als Benutzer-ObjectID (GUID) anzeigen, während der Mandant in Office 365-Dienste kopiert wird. MFA-Anforderungen werden trotz dieses Anzeigeverhaltens erwartungsgemäß ausgeführt.  Microsoft Authenticator-Konten, die mithilfe von Office 365-Dienstendpunkten aktiviert wurden, zeigen den Benutzerprinzipalnamen (User Principal Name, UPN) an.  Konten, die mithilfe von Microsoft Cloud Deutschland-Endpunkten hinzugefügt wurden, zeigen die Benutzer-ObjectID an, aber es können sowohl Microsoft Cloud Deutschland- als auch Office 365-Dienstendpunkte verwendet werden.  |
| Richten Sie AuthServer lokal mit Verweis auf den globalen STS-Dienst ein. | Auf diese Weise wird sichergestellt, dass Anforderungen von Benutzern, die aufgrund von Exchange-Verfügbarkeitsanforderungen, die auf die lokale Hybridumgebung ausgerichtet sind, zu Microsoft Cloud Deutschland migrieren, für den Zugriff auf den lokalen Dienst authentifiziert sind. Auf ähnliche Weise stellt dies die Authentifizierung von Anforderungen von lokalen zu Office 365-Dienstendpunkten sicher. | Exchange Online-Kunden mit hybriden (lokalen) Bereitstellungen | Nach Abschluss der Azure AD-Migration muss der Administrator der lokalen Exchange-(Hybrid-)Topologie einen neuen Authentifizierungsdienstendpunkt für die Office 365-Dienste hinzufügen. Ersetzen Sie mit diesem Befehl von Exchange PowerShell `<TenantID>` durch die Mandanten-ID Ihrer Organisation (im Azure-Portal unter **Azure Active Directory-**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Wenn Sie diese Aufgabe nicht ausführen, kann es sein, dass die Frei/Gebucht-Hybridanforderungen keine Informationen für Postfachbenutzer bereitstellen, die von Microsoft Cloud Deutschland zu Office 365-Diensten migriert wurden.  |
| Migration von Azure-Ressourcen. | Kunden, die Office 365- und Azure-Ressourcen (z. B. Netzwerk, Datenverarbeitung und Speicher) verwenden, führen die Migration von Ressourcen zur Office 365-Dienstinstanz aus. Diese Migration obliegt dem Kunden. Beiträge des Nachrichtencenters signalisieren den Anfang. Die Migration muss vor Abschluss der Azure AD-Organisation in der Office 365-Diensteumgebung abgeschlossen sein. | Azure-Kunden | Informationen zu Azure-Migrationen finden Sie im Azure-Migrationsplaybook [Übersicht über den Migrationsleitfaden für Azure Deutschland](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Phase 5 von 9)

Wenn Sie **Set-UserPhoto** verwenden:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Die neue deutsche Region wird einem vorhandenen Organisationssetup hinzugefügt, und Postfächer werden zu Office 365-Diensten verschoben. | Die Exchange Online-Konfiguration fügt die neue lokale deutsche Region zur Übergangsorganisation hinzu. Diese Office 365-Dienste-Region ist standardmäßig festgelegt, sodass der interne Lastenausgleichsdienst die Postfächer an die entsprechende Standardregion in den Office 365-Diensten weiterverteilen kann. Bei diesem Übergang befinden sich die Benutzer beider Seiten (Deutschland oder Office 365-Dienste) in der gleichen Organisation und können einen der beiden URL-Endpunkte verwenden. |  Exchange Online | Wenn ein Benutzerpostfach, aber kein Administratorpostfach migriert wurde (oder umgekehrt), können Administratoren **Set-UserPhoto**, ein PowerShell-Cmdlet, nicht ausführen. In diesem Fall muss ein Administrator während der Verbindungseinrichtung eine zusätzliche Zeichenfolge in `ConnectionUri` übergeben, indem er die folgende Syntax verwendet: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> Hierbei steht `<user_email>` für die E-Mail-ID des Benutzers, dessen Foto mithilfe von **Set-UserPhoto** geändert werden muss. |
|||||

Wenn Sie eine lokale Hybridbereitstellung verwenden:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
|Stoppen oder löschen Sie alle Onboarding- oder Offboarding-Verschiebungen von Postfächern.  | Dadurch wird sichergestellt, dass die Verschiebeanforderungen nicht fehlschlagen. | Exchange Online-Kunden mit (lokalen) Hybridbereitstellungen | Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (Phase 8 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-Ressourcen | Kunden, die mit Microsoft Dynamics arbeiten, werden vom Engineering oder FastTrack beauftragt, Dynamics zur die Office 365-Dienstinstanz zu verlagern.* | Microsoft Dynamics 365-Kunden | – Der Administrator überprüft die Organisation nach der Migration. <br><br> – Der Administrator ändert bei Bedarf die Workflows. <br><br> – Der Administrator deaktiviert ggf. den AdminOnly-Modus. <br><br> – Der Administrator ändert ggf. die Art der Organisation von _Sandbox_. <br><br> – Benachrichtigen Sie die Endbenutzer über die neue URL für den Zugriff auf die Instanz (Organisation). <br><br> – Aktualisieren Sie alle eingehenden Verbindungen auf die neue Endpunkt-URL. <br><br> – Der Dynamics-Dienst steht Benutzern während des Übergangs nicht zur Verfügung. <br><br> – Benutzer sind verpflichtet, die Integrität und Funktionen der Organisation nach der Migration jeder einzelnen Organisation zu überprüfen.  |
|||||

\* (i) Kunden mit Microsoft Dynamics 365 müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab. 


### <a name="power-bi-phase-8-of-9"></a>Power BI (Phase 8 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Power BI-Ressourcen | Kunden mit Microsoft Power BI werden von Engineering oder FastTrack beauftragt, nachdem ein vorhandenes PBI-Migrationstool manuell ausgelöst wurde, Power BI auf die Office 365-Dienstinstanz umzustellen.\*\* | Microsoft Power BI-Kunden | – Die folgenden Power BI-Elemente werden _nicht_ verschoben, und müssen neu erstellt werden: <br><br> – Echtzeit-Datasets (beispielsweise Streaming- oder Push-Datasets). <br> – Lokale Power BI-Konfiguration des Datengateways und die Datenquelle. <br> – Berichte, die auf den Echtzeit-Datasets basieren, sind nach der Migration nicht verfügbar und müssen neu erstellt werden. <br><br> – Power BI-Dienste stehen Benutzern während des Übergangs nicht zur Verfügung. Der Dienst sollte höchstens 24 Stunden lang nicht verfügbar sein. <br><br> – Benutzer müssen nach der Migration Datenquellen und ihre lokalen Datengateways mit dem Power BI-Dienst neu konfigurieren.  Solange dies nicht der Fall ist, können Benutzer diese Datenquellen nicht verwenden, um planmäßige Aktualisierungen und/oder direkte Abfragen für diese Datenquellen auszuführen. <br><br> – Kapazitäten und Premium-Arbeitsbereiche können nicht migriert werden. Kunden müssen alle Kapazitäten vor der Migration löschen und nach der Migration neu erstellen. Verschieben Sie Arbeitsbereiche ggf. zurück zu Kapazitäten.  |
|||||

\*\* (i) Kunden mit Microsoft Power BI müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab. 



## <a name="during-migration"></a>Während der Migration

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Phase 4 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| SharePoint und OneDrive werden überführt. | SharePoint und OneDrive werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365-Diensten migriert. Bestehende URLs von Microsoft Cloud Deutschland bleiben erhalten (`contoso.sharepoint.de`). Tokens, die von Microsoft Cloud Deutschland oder Office 365-Diensten herausgegeben wurden, bleiben während des Übergangs gültig. | SharePoint-Kunden | SharePoint 2013-Inflight-Workflows werden während der Migration unterbrochen und müssen nach der Migration erneut veröffentlicht werden. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Phase 5 von 9)

Für eDiscovery:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Während der Migration schlagen eDiscovery-Suchen fehl oder geben 0 Ergebnisse für SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte zurück, die migriert wurden. | Während der Migration können Kunden weiterhin Fälle, Archive, Suchvorgänge und Exporte im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations) erstellen, einschließlich [Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).  Bei Suchvorgängen in SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorten, die migriert wurden, werden jedoch entweder 0 Ergebnisse oder ein Fehler zurückgegeben. Informationen zur Problembehebung finden Sie in der Spalte _Auswirkung_. | Alle Kunden, die eDiscovery verwenden |  Für den Fall, dass eine Suche 0 Ergebnisse oder einen Fehler während der Migration zurückgibt, sollten Sie die folgende Aktion für SharePoint Online ausführen: <br><br>  Laden Sie Websites direkt von der SharePoint Online-/OneDrive for Business-Website herunter, indem Sie die Anweisungen in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) befolgen. Für diese Methode sind SharePoint Online-Administratorberechtigungen oder Nur-Lesen-Berechtigungen auf der Website erforderlich. <br><br> Wenn Limits überschritten werden, wie in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) erläutert wird, können Kunden den OneDrive for Business-Synchronisierungsclient verwenden, indem sie den Anweisungen unter [Synchronisieren von SharePoint- und Team Dateien mit Ihrem Computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) folgen. <br><br> – Exchange Online <br><br> - [Compliance-eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (Phase 7 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Wechseln von Skype for Business zu Microsoft Teams. | Bestehende Skype for Business-Kunden werden auf Office 365-Dienste in Europa migriert und anschließend auf Microsoft Teams in der Region Deutschland der Office 365-Dienste umgestellt. | Skype for Business-Kunden |  Mithilfe von PowerShell können Sie Einstellungen und Richtlinien für Ihren Mandanten und Ihre Benutzer verwalten. Fügen Sie beim Herstellen einer Verbindung mit einer PowerShell-Sitzung Folgendes hinzu: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Nach der Migration

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (Phase 9 von 9)

Für Hybrid:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren Sie Azure AD Connect. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde sicherstellen, dass der Delta-Synchronisierungsprozess abgeschlossen ist. Ändern Sie danach den Zeichenfolgenwert von `AzureInstance` aus 3 (Microsoft Cloud Deutschland) im Registrierungspfad `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` in 0. | Über Azure AD Hybrid verbundene Organisationen | Ändern Sie den Wert `AzureInstance` des Registrierungsschlüssels. Andernfalls werden Objekte nicht synchronisiert, wenn die Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

Für Verbundauthentifizierung:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Entfernen Sie Vertrauensstellungen der vertrauenden Gruppen aus Microsoft Cloud Deutschland AD FS. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Gruppe zu den Microsoft Cloud Deutschland-Endpunkten entfernen. Dies kann nur geschehen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte verweisen, wenn Azure AD als Identitätsanbieter (Identity Provider, IdP) verwendet wird. | Organisationen mit Verbundauthentifizierung | Keine |
|||||

Für Azure AD:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Anforderungen für den Beitritt einer Azure AD-Gruppe in den letzten 30 Tagen vor der Migration müssen erneut durchgeführt werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde. | Kunden von Endbenutzern müssen den Zugriffsbereich verwenden, um erneut Anforderungen zum Beitritt zu einer Azure AD-Gruppe zu senden, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden. | Endbenutzer, deren Azure AD-Gruppengenehmigungsanforderungen nicht in den letzten 30 Tagen vor der Migration genehmigt wurden |  Als Endbenutzer: <ol><li>Navigieren Sie zum [Zugriffsbereich](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Suchen Sie eine Azure AD-Gruppe, für die innerhalb von 30 Tagen vor der Migration eine Mitgliedschaftsgenehmigung ausstehend war.</li><li>Fordern Sie den Beitritt zur Azure AD-Gruppe erneut an.</li></ol> Anforderungen zum Betritt zu einer Gruppe, die weniger als 30 Tage vor der Migration aktiv sind, können nicht genehmigt werden, es sei denn, sie werden nach der Migration wiederholt. |
|||||

Für DNS:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienstendpunkte. | Vom Kunden verwaltete DNS-Einträge, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen. | Alle Office-Kunden | Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
|||||

Für Dienste von Drittanbietern für Office 365-Dienstendpunkte:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Aktualisieren Sie Partner und Drittanbieterdienste für Office 365-Dienstendpunkte. | – Drittanbieterdienste und Partner, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen. Beispiel: Registrieren Sie die Galerie-App-Version der Anwendungen, falls verfügbar, in Übereinstimmung mit Ihren Anbietern und Partnern neu. <br><br> – Verweisen Sie alle benutzerdefinierten Anwendungen, die die Graph-API von `graph.microsoft.de` verwenden, auf `graph.microsoft.com`. Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls sie genutzt werden. <br><br> – Ändern Sie alle Unternehmensanwendungen von Drittanbietern so, dass sie zu den weltweiten Endpunkten umgeleitet werden.  | Alle Office-Kunden | Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Phase 4 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Veröffentlichen Sie SharePoint 2013-Workflows erneut. | Bei der Vorbereitung der Migration wurde die Anzahl der SharePoint 2013-Workflows reduziert. Nach Abschluss der Migration kann der Kunde die Workflows erneut veröffentlichen. | Alle Office-Kunden | Dies ist eine erforderliche Aktion. Wird sie nicht ausgeführt, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
| Freigeben von Elementen über Outlook | Das Freigeben von Elementen über Outlook funktioniert nach der Mandanten-Übernahmemigration nicht mehr. | SharePoint Online und OneDrive for Business | – In SharePoint Online und OneDrive for Business können Sie Elemente über Outlook freigeben. Nach dem Klicken auf die Outlook-Schaltfläche wird ein Link für die Freigabe erstellt und in eine neue Nachricht in Outlook Web App eingefügt. <br><br> – Nach der Mandanten-Übernahmemigration funktioniert diese Freigabemethode nicht. Dieses Problem ist bereits bekannt. Da diese Outlook-Funktion allerdings bereits veraltet ist, ist die Behebung des Problems erst geplant, wenn die Unterstützung beendet wurde. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Phase 5 von 9)

Bei Verwendung einer Exchange-Hybridkonfiguration:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Führen Sie den Hybridkonfigurations-Assistenten (Hybrid Configuration Wizard, HCW) für Office 365-Dienste erneut aus. | Die vorhandene HCW-Konfiguration ist für die Unterstützung von Microsoft Cloud Deutschland vorgesehen. Wenn die Migration der Exchange-Dienste abgeschlossen ist, entkoppeln wir die lokale Konfiguration von Microsoft Cloud Deutschland. | Exchange Online-Kunden, die eine Hybridbereitstellung ausführen | – Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. Bevor die Migration von Exchange-Postfächern beginnt (Ankündigung mindestens 5 Tage zuvor), benachrichtigen Sie die Kunden, dass Sie alle Onboarding- oder Offboarding-Aktionen ihrer Postfächer anhalten und löschen sollen.  Andernfalls werden in den Verschiebeanforderungen Fehler angezeigt. <br><br> – Nach Abschluss der Exchange-Postfachmigration benachrichtigen Sie die Kunden, dass sie Onboarding- und Offboarding-Aktionen fortsetzen können. <br> Das Ausführen des PowerShell-Cmdlets **Test-MigrationServerAvailabiilty** während der Migration von Exchange von Microsoft Cloud Deutschland zu Office 365-Diensten funktioniert möglicherweise nicht. Nach Abschluss der Migration funktioniert es jedoch ordnungsgemäß. <br><br> Wenn Kunden nach der Migration von Postfächern Probleme mit Anmeldeinformationen oder Autorisierung haben, können Benutzer ihre lokalen Administratoranmeldeinformationen in den Migrationsendpunkt erneut eingeben, indem sie `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ausführen oder diese mithilfe der Exchange-Systemsteuerung (ECP) festlegen.  |

Für eDiscovery:

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
|  Alle SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte wurden zusammen mit dem Security and Compliance Center (SCC) migriert. | Alle eDiscovery-Aktivitäten sollten vom weltweiten Mandanten aus ausgeführt werden. Suchvorgänge sind jetzt zu 100 % erfolgreich.  Alle Fehler oder Ausfälle sollten normalen Supportkanälen folgen. | Alle Kunden, die eDiscovery verwenden | Keine |
| Entfernen organisationsweiter Aufbewahrungsrichtlinien, die während der Schritte vor der Migration erstellt wurden | Kunden können die organisationsweiten Aufbewahrungsrichtlinien entfernen, die während der Arbeit der Kunden vor der Migration erstellt wurden. | Alle Kunden, die eine Aufbewahrungsrichtlinie im Rahmen der Schritte vor der Migration angewendet haben | Keine |
|||||



## <a name="next-step"></a>Nächster Schritt

[Phasen, Aktionen und Auswirkungen der Migration verstehen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
