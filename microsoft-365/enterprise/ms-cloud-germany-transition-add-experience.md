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
ms.openlocfilehash: ecc549ca4d0bb8122de3bf092c004c919e958d5e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165645"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Migrationsphasenaktionen und Auswirkungen für die Migration von Microsoft Cloud Deutschland (erweitert)

Mandanten-Migrationen von Microsoft Cloud Deutschland in die Region Deutschland der Office 365-Dienste von Microsoft werden als eine Reihe von Phasen und deren konfigurierten Aktionen für jeden Workload ausgeführt. Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren.

![Die neun Phasen der Migration in die neuen deutschen Rechenzentren](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Die folgenden Abschnitte enthalten weitere Informationen zu den Erfahrungen der Kunden beim Wechsel von Microsoft Cloud Deutschland zu Office 365-Dienste in der neuen deutschen Rechenzentrumsregion.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>Office 365-Portaldienste zwischen Phase 2 und Phase 3

Zwischen Phase 2 und Phase 3 ist das Partnerportal möglicherweise nicht zugänglich. Während dieser Zeit können Partner möglicherweise nicht auf die Informationen des Mandanten im Partnerportal zugreifen. Da jede Migration anders abläuft, kann die Dauer die das Portal nicht erreichbar ist, Stunden betragen.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery Phase 4 bis zum Ende von Phase 9

**Gilt für:** Alle Kunden, die eDiscovery verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Von Beginn von Phase 4 bis zum Abschluss von Phase 9 schlagen eDiscovery-Suchen fehl oder geben 0 (null) Ergebnisse für SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte zurück, die migriert wurden. | Während der Migration können Kunden weiterhin Fälle, Archive, Suchvorgänge und Exporte im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations) erstellen, einschließlich [Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content). Bei Suchvorgängen in SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorten, die migriert wurden, werden jedoch entweder 0 Ergebnisse oder ein Fehler zurückgegeben. Informationen zur Problembehebung finden Sie in der Spalte _Auswirkung_. | Für den Fall, dass eine Suche 0 (null) Ergebnisse oder einen Fehler während der Migration zurückgibt, sollten Sie die folgende Aktion für SharePoint Online ausführen: <ul><li>Laden Sie Websites direkt von der SharePoint Online- oder OneDrive for Business-Website herunter, indem Sie die Anweisungen in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) befolgen. Für diese Methode sind SharePoint Online-Administratorberechtigungen oder Nur-Lesen-Berechtigungen auf der Website erforderlich.</li><li>Wenn Limits überschritten werden, wie in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) erläutert wird, können Kunden den OneDrive for Business-Synchronisierungsclient verwenden, indem sie den Anweisungen unter [Synchronisieren von SharePoint- und Team Dateien mit Ihrem Computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) folgen.</li><li>Weitere Informationen finden Sie unter [In-Situ-eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery). |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>Exchange Online Set-UserPhoto während der Phase 5

**Gilt für:** Alle Kunden, die Benutzerfotos in Exchange Online speichern und **Set-UserPhoto** verwenden:

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Die neue Region „Deutschland“ wird einem vorhandenen Exchange Online-Organisationssetup hinzugefügt, und Postfächer werden zu Office 365-Diensten verschoben. | Die Exchange Online-Konfiguration fügt die neue lokale deutsche Region zur Übergangsorganisation hinzu. Diese Office 365-Dienste-Region ist standardmäßig festgelegt, sodass der interne Lastenausgleichsdienst die Postfächer an die entsprechende Standardregion in den Office 365-Diensten weiterverteilen kann. Bei diesem Übergang befinden sich die Benutzer beider Seiten (Deutschland oder Office 365-Dienste) in der gleichen Organisation und können einen der beiden URL-Endpunkte verwenden. | Wenn ein Benutzerpostfach, aber kein Administratorpostfach migriert wurde (oder umgekehrt), können Administratoren **Set-UserPhoto**, ein PowerShell-Cmdlet, nicht ausführen. In diesem Fall muss ein Administrator während der Verbindungseinrichtung eine zusätzliche Zeichenfolge in `ConnectionUri` übergeben, indem er die folgende Syntax verwendet: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> Hierbei steht `<user_email>` für die E-Mail-ID des Benutzers, dessen Foto mithilfe von **Set-UserPhoto** geändert werden muss. |
||||

## <a name="post-migration"></a>Nach der Migration

### <a name="azure-ad-phase-9"></a>Azure AD (Phase 9)

**Gilt für:** Alle Kunden, die Identitäten mit Azure AD Connect synchronisieren

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Azure AD Connect. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde sicherstellen, dass der Delta-Synchronisierungsprozess abgeschlossen ist. Ändern Sie danach den Zeichenfolgenwert von `AzureInstance` aus 3 (Microsoft Cloud Deutschland) im Registrierungspfad `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` in 0. | Ändern Sie den Wert `AzureInstance` des Registrierungsschlüssels. Andernfalls werden Objekte nicht synchronisiert, wenn die Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

**Gilt für:** Alle Kunden, die Verbundauthentifizierung mit AD FS verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen Sie Vertrauensstellungen der vertrauenden Gruppen aus Microsoft Cloud Deutschland AD FS. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Gruppe zu den Microsoft Cloud Deutschland-Endpunkten entfernen. Dies kann nur geschehen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte verweisen, wenn Azure AD als Identitätsanbieter (Identity Provider, IdP) verwendet wird. | Organisationen mit Verbundauthentifizierung | Keine |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Gilt für:** Endbenutzer, deren Azure AD-Gruppengenehmigungsanforderungen nicht in den letzten 30 Tagen vor der Migration genehmigt wurden 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Anforderungen für den Beitritt einer Azure AD-Gruppe in den letzten 30 Tagen vor der Migration müssen erneut durchgeführt werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde. | Kunden von Endbenutzern müssen den Zugriffsbereich verwenden, um erneut Anforderungen zum Beitritt zu einer Azure AD-Gruppe zu senden, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden. |  Als Endbenutzer: <ol><li>Navigieren Sie zum [Zugriffsbereich](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Suchen Sie eine Azure AD-Gruppe, für die innerhalb von 30 Tagen vor der Migration eine Mitgliedschaftsgenehmigung ausstehend war.</li><li>Fordern Sie den Beitritt zur Azure AD-Gruppe erneut an.</li></ol> Anforderungen zum Betritt zu einer Gruppe, die weniger als 30 Tage vor der Migration aktiv sind, können nicht genehmigt werden, es sei denn, sie werden nach der Migration wiederholt. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Gilt für:** Alle Kunden, die ihre eigenen DNS-Zonen verwalten

| Schritte: | Beschreibung | Auswirkung |
|:------|:-------|:-------|
| Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienstendpunkte. | Vom Kunden verwaltete DNS-Einträge, die auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365 Global-Dienstendpunkte verweisen. | Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
||||

**Gilt für:** Kunden, die Drittanbieterdienste für Office 365-Dienstendpunkte verwenden.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Partner und Drittanbieterdienste für Office 365-Dienstendpunkte. | <ul><li>Drittanbieterdienste und Partner, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen. Beispiel: Registrieren Sie die Galerie-App-Version der Anwendungen, falls verfügbar, in Übereinstimmung mit Ihren Anbietern und Partnern neu. </li><li>Verweisen Sie alle benutzerdefinierten Anwendungen, die die Graph-API von `graph.microsoft.de` verwenden, auf `graph.microsoft.com`. Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls sie genutzt werden. </li><li>Ändern Sie alle Unternehmensanwendungen von Drittanbietern so, dass sie zu den weltweiten Endpunkten umgeleitet werden. </li></ul>| Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
||||

### <a name="sharepoint-online-post-migration"></a>Nach der SharePoint Online-Migration

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Veröffentlichen Sie SharePoint 2013-Workflows erneut. | Bei der Vorbereitung der Migration wurde die Anzahl der SharePoint 2013-Workflows reduziert. Nach Abschluss der Migration kann der Kunde die Workflows erneut veröffentlichen. | Dies ist eine erforderliche Aktion. Wird sie nicht ausgeführt, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
| Freigeben von Elementen über Outlook | Die Freigabe von Elementen in SharePoint Online und OneDrive for Business über Outlook funktioniert nach der Mandantenübernahmemigration nicht mehr. |<ul><li>In SharePoint Online und OneDrive for Business können Sie Elemente über Outlook freigeben. Nach dem Klicken auf die Outlook-Schaltfläche wird ein Link für die Freigabe erstellt und in eine neue Nachricht in Outlook Web App eingefügt.</li><li>Nach der Mandantenübernahmemigration funktioniert diese Freigabemethode nicht. Dieses Problem ist bereits bekannt. Da diese Outlook-Funktion allerdings bereits veraltet ist, ist die Behebung des Problems erst geplant, wenn die Unterstützung beendet wurde. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Nach der Exchange Online-Migration

Bei Verwendung einer Exchange-Hybridkonfiguration:

| Schritt(e) | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Führen Sie den Hybridkonfigurations-Assistenten (Hybrid Configuration Wizard, HCW) für Office 365-Dienste erneut aus. | Die vorhandene HCW-Konfiguration ist für die Unterstützung von Microsoft Cloud Deutschland vorgesehen. Wenn die Migration der Exchange-Dienste abgeschlossen ist, entkoppeln wir die lokale Konfiguration von Microsoft Cloud Deutschland. |<ul><li>Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. Bevor die Migration von Exchange-Postfächern beginnt (Ankündigung mindestens 5 Tage zuvor), benachrichtigen Sie die Kunden, dass Sie alle Onboarding- oder Offboarding-Aktionen ihrer Postfächer anhalten und löschen sollen.  Andernfalls werden in den Verschiebeanforderungen Fehler angezeigt. </li><li>Nach Abschluss der Exchange-Postfachmigration benachrichtigen Sie die Kunden, dass sie Onboarding- und Offboarding-Aktionen fortsetzen können. <br> Das Ausführen des PowerShell-Cmdlets **Test-MigrationServerAvailabiilty** während der Migration von Exchange von Microsoft Cloud Deutschland zu Office 365-Diensten funktioniert möglicherweise nicht. Nach Abschluss der Migration funktioniert es jedoch ordnungsgemäß. </li><li>Wenn Kunden nach der Migration von Postfächern Probleme mit Anmeldeinformationen oder Autorisierung haben, können Benutzer ihre lokalen Administratoranmeldeinformationen in den Migrationsendpunkt erneut eingeben, indem sie `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ausführen oder diese mithilfe der Exchange-Systemsteuerung (ECP) festlegen. </li></ul>|

### <a name="ediscovery-post-migration"></a>Nach der eDiscovery-Migration

**Gilt für:** Alle Kunden, die eDiscovery verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
|  Alle SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte wurden zusammen mit dem Security and Compliance Center (SCC) migriert. | Alle eDiscovery-Aktivitäten sollten vom weltweiten Mandanten aus ausgeführt werden. Suchvorgänge sind jetzt zu 100 % erfolgreich.  Alle Fehler oder Ausfälle sollten normalen Supportkanälen folgen. | Keine |
||||

**Gilt für:** Alle Kunden, die eine Aufbewahrungsrichtlinie im Rahmen der Schritte vor der Migration angewendet haben

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen organisationsweiter Aufbewahrungsrichtlinien, die während der Schritte vor der Migration erstellt wurden | Kunden können die organisationsweiten Aufbewahrungsrichtlinien entfernen, die während der Arbeit der Kunden vor der Migration erstellt wurden. | Keine |
||||

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

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)