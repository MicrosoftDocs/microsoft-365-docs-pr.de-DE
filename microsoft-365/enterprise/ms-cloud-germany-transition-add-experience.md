---
title: Aktivitäten nach der Migration für die Migration aus Microsoft Cloud Deutschland
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
description: 'Zusammenfassung: Aktivitäten nach der Migration nach dem Wechsel von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.'
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591756"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Aktivitäten nach der Migration für die Migration aus Microsoft Cloud Deutschland

Die folgenden Abschnitte bieten Aktivitäten nach der Migration für mehrere Dienste nach dem Wechsel von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.

## <a name="azure-ad"></a>Azure AD

### <a name="azure-ad-connect"></a>Azure AD Connect
**Gilt für:** Alle Kunden, die Identitäten mit Azure AD Connect synchronisieren

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Azure AD Connect. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde sicherstellen, dass der Delta-Synchronisierungsprozess abgeschlossen ist. Ändern Sie danach den Zeichenfolgenwert von `AzureInstance` aus 3 (Microsoft Cloud Deutschland) im Registrierungspfad `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` in 0. | Ändern Sie den Wert `AzureInstance` des Registrierungsschlüssels. Andernfalls werden Objekte nicht synchronisiert, wenn die Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD-Verbundauthentifizierung mit AD FS
**Gilt für:** Alle Kunden, die die Verbundauthentifizierung mit AD FS verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen Sie Vertrauensstellungen der vertrauenden Gruppen aus Microsoft Cloud Deutschland AD FS. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Gruppe zu den Microsoft Cloud Deutschland-Endpunkten entfernen. Dies kann nur geschehen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte verweisen, wenn Azure AD als Identitätsanbieter (Identity Provider, IdP) verwendet wird. | Organisationen mit Verbundauthentifizierung | Keine |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Gruppengenehmigungen
**Gilt für:** Endbenutzer, deren Azure AD-Gruppengenehmigungsanforderungen nicht in den letzten 30 Tagen vor der Migration genehmigt wurden 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Anforderungen für den Beitritt einer Azure AD-Gruppe in den letzten 30 Tagen vor der Migration müssen erneut durchgeführt werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde. | Kunden von Endbenutzern müssen den Zugriffsbereich verwenden, um erneut Anforderungen zum Beitritt zu einer Azure AD-Gruppe zu senden, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden. |  Als Endbenutzer: <ol><li>Navigieren Sie zum [Zugriffsbereich](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Suchen Sie eine Azure AD-Gruppe, für die innerhalb von 30 Tagen vor der Migration eine Mitgliedschaftsgenehmigung ausstehend war.</li><li>Fordern Sie den Beitritt zur Azure AD-Gruppe erneut an.</li></ol> Anforderungen zum Betritt zu einer Gruppe, die weniger als 30 Tage vor der Migration aktiv sind, können nicht genehmigt werden, es sei denn, sie werden nach der Migration wiederholt. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Benutzerdefinierte DNS-Updates
**Gilt für:** Alle Kunden, die ihre eigenen DNS-Zonen verwalten

| Schritte: | Beschreibung | Auswirkung |
|:------|:-------|:-------|
| Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienstendpunkte. | Vom Kunden verwaltete DNS-Einträge, die auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365 Global-Dienstendpunkte verweisen. | Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
||||

## <a name="third-party-services"></a>Drittanbieterdienste
**Gilt für:** Kunden, die Dienste von Drittanbietern für Office 365-Dienste-Endpunkte verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Partner und Drittanbieterdienste für Office 365-Dienstendpunkte. | <ul><li>Drittanbieterdienste und Partner, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen. Beispiel: Registrieren Sie die Galerie-App-Version der Anwendungen, falls verfügbar, in Übereinstimmung mit Ihren Anbietern und Partnern neu. </li><li>Verweisen Sie alle benutzerdefinierten Anwendungen, die die Graph-API von `graph.microsoft.de` verwenden, auf `graph.microsoft.com`. Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls sie genutzt werden. </li><li>Ändern Sie alle Unternehmensanwendungen von Drittanbietern so, dass sie zu den weltweiten Endpunkten umgeleitet werden. </li></ul>| Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Gilt für**: Kunden, die SharePoint 2013-Workflows verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Veröffentlichen Sie SharePoint 2013-Workflows erneut. | Bei der Vorbereitung der Migration wurde die Anzahl der SharePoint 2013-Workflows reduziert. Nach Abschluss der Migration kann der Kunde die Workflows erneut veröffentlichen. | Dies ist eine erforderliche Aktion. Wird sie nicht ausgeführt, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
| Freigeben von Elementen über Outlook | Die Freigabe von Elementen in SharePoint Online und OneDrive for Business über Outlook funktioniert nach der Mandantenübergabe nicht mehr. |<ul><li>In SharePoint Online und OneDrive for Business können Sie Elemente über Outlook freigeben. Nach dem Klicken auf die Outlook-Schaltfläche wird ein Link für die Freigabe erstellt und in eine neue Nachricht in Outlook Web App eingefügt.</li><li>Nach der Mandantenübernahmemigration funktioniert diese Freigabemethode nicht. Dieses Problem ist bereits bekannt. Da diese Outlook-Funktion allerdings bereits veraltet ist, ist die Behebung des Problems erst geplant, wenn die Unterstützung beendet wurde. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Gilt für**: Kunden, die eine hybride Exchange-Konfiguration verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Führen Sie den Hybridkonfigurations-Assistenten (Hybrid Configuration Wizard, HCW) für Office 365-Dienste erneut aus. | Die vorhandene HCW-Konfiguration ist für die Unterstützung von Microsoft Cloud Deutschland vorgesehen. Wenn die Migration der Exchange-Dienste abgeschlossen ist, entkoppeln wir die lokale Konfiguration von Microsoft Cloud Deutschland. |<ul><li>Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. Bevor die Migration von Exchange-Postfächern beginnt (Ankündigung mindestens 5 Tage zuvor), benachrichtigen Sie die Kunden, dass Sie alle Onboarding- oder Offboarding-Aktionen ihrer Postfächer anhalten und löschen sollen.  Andernfalls werden in den Verschiebeanforderungen Fehler angezeigt. </li><li>Nach Abschluss der Exchange-Postfachmigration benachrichtigen Sie die Kunden, dass sie Onboarding- und Offboarding-Aktionen fortsetzen können. <br> Das Ausführen des PowerShell-Cmdlets **Test-MigrationServerAvailabiilty** während der Migration von Exchange von Microsoft Cloud Deutschland zu Office 365-Diensten funktioniert möglicherweise nicht. Nach Abschluss der Migration funktioniert es jedoch ordnungsgemäß. </li><li>Wenn Kunden nach der Migration von Postfächern Probleme mit Anmeldeinformationen oder Autorisierung haben, können Benutzer ihre lokalen Administratoranmeldeinformationen in den Migrationsendpunkt erneut eingeben, indem sie `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ausführen oder diese mithilfe der Exchange-Systemsteuerung (ECP) festlegen. </li></ul>|
