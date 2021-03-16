---
title: Vorbereitung für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 'Zusammenfassung: Vorbereitung der Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) nach Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 5110c6bd86d5df35a7ceccb4abfedf059cb826d0
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826176"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Vorbereitung für die Migration von Microsoft Cloud Deutschland

Über diese Links gelangen Sie zu den Schritten für die Vorarbeit, die für Ihre Organisation relevant ist:

- Gehen Sie für alle Kunden, die Office 365 in Microsoft Cloud Deutschland verwenden, [wie im folgenden Schritt vor.](#applies-to-everyone)
- Führen Sie [diesen Schritt](#exchange-online) aus, wenn Sie Exchange Online oder eine Exchange-Hybridversion verwenden.
- Führen Sie [diesen Schritt](#sharepoint-online) aus, wenn Sie SharePoint Online verwenden.
- Fphren Sie [diesen Schritt](#mobile) aus, wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden.
- Führen Sie [diesen Schritt](#line-of-business-apps) aus, wenn Sie einen Drittanbieterdienst oder branchenspezifische Apps verwenden, die in Office 365 integriert sind.
- Führen Sie [diesen Schritt](#microsoft-azure) aus, wenn Sie außer den in Ihrem Office 365-Abonnement enthaltenen noch weitere Azure-Dienste nutzen.
- Führen Sie [diesen Schritt](#dynamics365) aus, wenn Sie außerdem Dynamics 365 verwenden.
- Führen Sie [diesen Schritt](#power-bi) aus, wenn Sie außerdem Power BI verwenden.
- Führen Sie [diesen Schritt](#dns) für DNS-Änderungen aus.
- Führen Sie [diese Schritte](#federated-identity) aus, wenn Sie einen Identitätsverbund nutzen.

## <a name="applies-to-everyone"></a>Gilt für alle Benutzer

| Schritt(e) | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Bereiten Sie sich darauf vor, Benutzer über das Neustarten und Anmelden bei ihren Clients nach der Migration zu benachrichtigen. | Die Office-Clientlizenzierung geht bei der Migration von Microsoft Cloud Deutschland zu Office 365-Diensten über. Clients erhalten nach dem Abmelden von Office-Clients eine neue gültige Lizenz. | Die Office-Produkte der Benutzer müssen die Lizenzen für Office 365-Dienste aktualisieren. Bei Lizenzen, die nicht aktualisiert werden, treten möglicherweise Fehler bei Office-Produkten auf. |
| Stellen Sie die Netzwerkkonnektivität mit [Office 365-Dienst-URLs und -IP-Adressen](https://aka.ms/o365urls) sicher. | Alle clients and services hosted by the customer that are used to access Office 365 service must be able to access the Office 365 Global services endpoints. <br>Für den Fall, dass Sie oder Ihre Zusammenarbeitspartner Firewallregeln haben, die den Zugriff auf die URLs und IP-Adressen verhindern würden, die in URLs und IP-Adressen von [Office 365-Diensten](https://aka.ms/o365urls) aufgeführt sind, müssen die Firewallregeln geändert werden, um den Zugriff auf die globalen Office 365-Dienstendpunkte zu ermöglichen.| Fehler des Diensts oder der Clientsoftware können auftreten, wenn dies nicht vor Phase 4 erfolgt  |
| Kündigen aller Testabonnements. | Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. | Die Testdienste sind abgelaufen und funktionieren nicht, wenn sie nach dem Abbruch von Benutzern aufgerufen werden. |
| Analysieren Sie die Unterschiede bei den Lizenzfeatures zwischen Microsoft Cloud Deutschland und Office 365-Diensten. | Office 365-Dienste umfassen zusätzliche Features und Dienste, die in der aktuellen Microsoft Cloud Deutschland nicht verfügbar sind. Während der Abonnementübertragung stehen Benutzern neue Features zur Verfügung. | <ul><li> Analysieren Sie die verschiedenen Features, die von den Lizenzen für Microsoft Cloud Deutschland und Office 365 Services bereitgestellt werden. Beginnen Sie mit der [Beschreibung des Office 365-Plattformdiensts](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Ermitteln Sie, ob neue Features von Office 365-Diensten zunächst deaktiviert werden sollten, um Die Auswirkungen auf Benutzer oder die Verwaltung von Benutzeränderung zu begrenzen und die Zuweisungen von Benutzerlizenzen bei Bedarf zu ändern. </li><li>Bereiten Sie Benutzer und Helpdeskmitarbeiter auf neue Dienste und Features vor, die von Office 365-Diensten bereitgestellt werden. |
| Erstellen Sie organisationsweite [Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention) zum Schutz vor dem versehentlichen Löschen von Inhalten während der Migration.  |<ul><li>Um sicherzustellen, dass Inhalte während der Migration nicht versehentlich von Endbenutzern gelöscht werden, können Kunden eine organisationsweite Aufbewahrungsrichtlinie aktivieren. </li><li>Auch wenn die Aufbewahrung nicht erforderlich ist, da Aufbewahrungsspeicher während der Migration jederzeit wie erwartet funktionieren sollten, ist das Einrichten einer Aufbewahrungsrichtlinie ein Sicherungssicherheitsmechanismus. Gleichermaßen wird eine Aufbewahrungsrichtlinie vielleicht nicht von allen Kunden verwendet, insbesondere von denjenigen, die sich Sorgen um die übermäßige Aufbewahrung machen.</li></ul>| Wenden Sie Aufbewahrungsrichtlinie so an, wie in [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) beschrieben. Es kann zu Ausfällen des Dienstes oder der Client-Software kommen, wenn dies nicht vor Phase 4 von 9 erfolgt. </li></ul>|
| Korrigieren von Lizenzüberagen | Unter bestimmten Umständen können Kunden möglicherweise mehr Dienste nutzen als erworben werden. Diese Bedingung wird als Lizenzüberage bezeichnet. Microsoft kann Kunden in einer Lizenzüberagebedingung nicht von Microsoft Cloud Deutschland in die deutschen Rechenzentrumsregionen migrieren. Um den kontinuierlichen Zugriff auf den Dienst und die Daten sicherzustellen, benötigt jeder zugewiesene Benutzer eine Lizenz. | Alle Kunden | Kunden müssen die Lizenzüberagebedingung bewerten und beheben, indem sie zusätzliche Lizenzen erwerben oder Lizenzen von Benutzern nicht zuweisen. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory-Verbunddienste (AD FS)

**Betrifft:** Kunden, die AD FS lokal verwenden, um Benutzer zu authentifizieren, die eine Verbindung mit Microsoft Office 365 herstellen

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| [Sicherung der Active Directory-Verbunddienste (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) für Notfallwiederherstellungsszenarios. | Kunden müssen die AD FS-Farm ordnungsgemäß sichern, um sicherzustellen, dass die Vertrauensstellung der vertrauenden Seite für globale Endpunkte und Deutschland-Endpunkte wiederhergestellt werden kann, ohne den Aussteller-URI der Domänen anzufassen. Microsoft empfiehlt die Verwendung von AD FS Rapid Restore für eine Sicherung der Farm und die entsprechende Wiederherstellung, falls erforderlich. | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies während der Migration zu Dienstbeeinträchtigungen führen, wenn in der AD FS-Farm des Kunden Fehler auftreten. Weitere Informationen finden Sie unter [ADFS-Migrationsschritte.](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange Online

**Gilt für**: Exchange Online-Kunden, die den Freigabekalender und den Verfügbarkeitsadressenraum aktiviert haben.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Benachrichtigen Sie externe Partner über den bevorstehenden Umstieg zu Office 365-Diensten. | Verfügbare Adressraumkonfigurationen ermöglichen die Freigabe von Frei-/Gebucht-Informationen mit Office 365. | Wenn diese Aktion nicht ausgeführt wird, kann dies in einer späteren Phase der Kundenmigration zu einem Dienst- oder Clientausfall führen. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online-Hybridkonfiguration

**Gilt für**: Exchange Online-Kunden mit einer aktiven Exchange-Hybridkonfiguration

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie jederzeit auf die neueste Version des Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW), bevor Ihr Mandant in Die Migrationsphase 5 eintritt. Sie können diese Aktivität unmittelbar nach Erhalt der Benachrichtigung des Nachrichtencenters starten, dass Ihre Office 365-Mandantenmigration begonnen hat.<br><br> Ein hybrider Exchange Online-Kunde von Microsoft Cloud Deutschland muss frühere Versionen von HCW deinstallieren, und dann die aktuellste Version (17.0.5378.0 oder höher) von [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) installieren und ausführen. |<ul><li>Die neueste Version des HCW enthält die erforderlichen Updates zur Unterstützung von Kunden, die von Microsoft Cloud Deutschland zu Office 365-Diensten wechseln.</li><li> Updates umfassen Änderungen an den lokalen Zertifikateinstellungen für den Senden-Connector und den Empfangen-Connector.</li><li> Exchange-Administratoren müssen den HCW jederzeit neu installieren, bevor Phase 5 von 9 (Exchange-Migration) beginnt.<br>Wählen Sie bei der Ausführung des HCW vor Phase 5 auf der 2. Seite des HCW unter _Office 365 Exchange Online_ im Listenfeld unter Meine Office _365-Organisation_ die Option "Office 365 Deutschland" aus.</li><li>**HINWEIS**: Nach Abschluss der Office 365-Mandantenmigration entfernen und installieren Sie den HCW erneut, dieses Mal verwenden Sie die Einstellungen "Office 365 Worldwide" auf der 2. Seite des HCW, um Ihre Hybrideinrichtung mit dem globalen Exchange Online-Dienst abzuschließen.</li></ul>|Wenn der HCW vor Phase 5 (Exchange-Migration) nicht ausgeführt wird, kann dies zu Dienst- oder Clientfehlern führen. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Gilt für**: Kunden, die SharePoint 2013 lokal verwenden


| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Begrenzen Sie SharePoint 2013-Workflows, die Sie während der SharePoint Online-Migration verwenden. | Reduzieren Sie SharePoint 2013-Workflows, und schließen Sie In-Flight-Workflows vor Übergängen ab. | Wenn keine Aktion ausgeführt wird, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

**Gilt für**: Skype For Business Online-Kunden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Bereitstellen des Teams-Desktopclients für Benutzer, die auf Skype for Business in Deutschland zugreifen. | Die Migration verschiebt Skype for Business-Benutzer zur Zusammenarbeit, zum Anruf und zum Chat zu Microsoft Teams. Stellen Sie entweder den Microsoft Teams-Desktopclient bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Untätigkeit führt zur Nichtverfügbarkeit von Microsoft Teams-Zusammenarbeitsdiensten. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Änderungen an DNS-Zonen von Kunden für Skype for Business Online. |<ul><li>Es wird empfohlen, die Time-to-Live (TTL) für alle dns-Einträge im Besitz des Kunden auf 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die von Microsoft verwaltete Übername im Zusammenhang mit dieser DNS-Änderung jederzeit innerhalb des bereitgestellten 24-Stunden-Änderungsfensters erfolgen. </li><li>Dienstunterbrechungen sind in Zukunft möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365-Diensten zu der migrierten Teams-Erfahrung umgeleitet. </li></ul>|
| Vorbereiten der Endbenutzer- und Administratorschulung und der Bereitschaft für den Umstieg auf Microsoft Teams. | Wenn Sie die Benutzerkommunikation und -bereitschaft planen wird der Umstieg von Skype auf Teams erfolgreich verlaufen. | <ul><li>Clients müssen sich der neuen Dienste bewusst sein und wissen, wie sie nach dem Übergang ihrer Dienste zu den Office 365-Diensten verwendet werden. </li><li>Nachdem DNS-Änderungen für die Vanitydomänen des Kunden und die ursprüngliche Domäne vorgenommen wurden, würden sich Die Benutzer bei Skype for Business anmelden und sehen, dass sie jetzt zu Teams migriert werden. Dadurch wird auch der Desktopclient für Teams im Hintergrund heruntergeladen. </li></ul>|
||||

## <a name="mobile"></a>Mobilgeräte

Wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden:

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Vorbereiten der Endbenutzer- und Administratorschulung für Benutzer für iOS und Android, die ihr Konto aus Microsoft Outlook entfernen und erneut hinzufügen. | Microsoft Outlook für iOS-und Android-Konten, die mit Postfächern in Microsoft Cloud Deutschland konfiguriert sind, muss möglicherweise entfernt und erneut zu Outlook hinzugefügt werden, um die neue Office 365-Dienstkonfiguration ordnungsgemäß zu synchronisieren. | Kunden von Microsoft Outlook für iOS und Android | Zuvor für Microsoft Cloud Deutschland konfigurierte Outlook-Postfächer können die neue Office 365-Dienste-Konfiguration nicht verwenden, was zu Fehlern und schlechter Leistung anderer Benutzererfahrungen führt. IT-Administratoren werden aufgefordert, Dokumentation bereitzustellen, die Benutzer proaktiv anweist, ihre Konten für iOS und Android aus Microsoft Outlook zu entfernen und erneut hinzuzufügen, wenn nach der Migration Probleme beim Anmelden oder beim Synchronisieren von E-Mails auftreten. |
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Lösungen für die mobile Geräteverwaltung (Mobile Device Management, MDM) können auf `outlook.de` Endpunkte zielen. Bei diesem Umstieg auf Office 365-Dienste sollten Clientprofile auf die Office 365-Dienst-URL `outlook.office365.com`aktualisiert werden. | Exchange Online und MDM-Kunden | Clients funktionieren möglicherweise weiterhin, solange auf den `outlook.de`-Endpunkt zugegriffen werden kann. Wenn nicht mehr auf Microsoft Cloud Deutschland-Endpunkte zugegriffen werden kann, treten Fehler auf. |
|||||

## <a name="line-of-business-apps"></a>Branchenspezifische Apps

Wenn Sie einen Drittanbieterdienst oder branchenspezifische Apps verwenden, die in Office 365 integriert sind: 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Dienste und Anwendungen von Drittanbietern, die in Office 365 integriert sind, können so programmiert werden, dass sie IP-Adressen und URLs von Microsoft Cloud Deutschland erwarten. | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gilt für**: Kunden, die Microsoft Dynamics verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Für Dynamics 365-Sandkastenabonnements müssen Sie unbedingt die Produktionsumgebung der SQL-Instanz von Dynamics aus Ihrem Dynamics 365-Abonnement in Microsoft Cloud Deutschland herunterladen. Die neueste Produktionssicherung sollte vor der Sandkastenmigration im Sandkasten wiederhergestellt werden. | Die Migration von Dynamics 365 setzt voraus, dass Kunden sicherstellen, dass die Sandkastenumgebung mit der neuesten Produktionsdatenbank aktualisiert wird. | Das FastTrack-Team unterstützt Kunden bei der Durchführung von Trockentests, um das Versionsupgrade von 8.x auf 9.1.x zu überprüfen. |
||||

## <a name="power-bi"></a>Power BI

**Gilt für**: Power BI-Kunden 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen von Objekten aus Power BI-Abonnements, die nicht von Power BI Microsoft Cloud Deutsch nach Office 365-Diensten migriert werden. | Für die Migration von Power BI-Diensten sind Kundenaktionen erforderlich, um bestimmte Artefakte wie Datasets und Dashboards zu löschen. | <ul><li>Administratoren müssen möglicherweise die folgenden Elemente aus Ihrem Abonnement entfernen: </li><li>Real-Time Datasets (z. B. Streaming- oder Push-Datasets) </li><li>Lokale Power BI Data Gateway-Konfiguration und Datenquelle </li></ul>|
||||

## <a name="dns"></a>DNS

**Betrifft:** Kunden, die Office Desktop-Client verwenden (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Entfernen Sie MSOID, CName aus dem kundeneigenen DNS, wenn es jederzeit vor dem Azure Active Directory (Azure AD)-Cut-Over vorhanden ist. Ein TTL von 5 Minuten kann eingestellt werden, sodass die Änderung schnell greift.

## <a name="federated-identity"></a>Identitätsverbund

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Kennung für Single Sign-On (SSO) zu einer vorhandenen Vertrauensstellung hinzufügen und automatische AD FS-Metadatenaktualisierungen deaktivieren. | Bevor Sie mit der Migration beginnen, muss eine ID zur AD FS-Vertrauensstellung hinzugefügt werden. Um ein versehentliches Entfernen der Kennung der vertrauenden Partei zu vermeiden, deaktivieren Sie die automatische Aktualisierung für Metadaten-Updates. <br><br> Führen Sie diesen Befehl als einzelne Befehlszeile auf dem AD FS-Server aus: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Organisationen mit Verbundauthentifizierung | Erforderliche Aktion. Wenn vor der Phase 4 von 9 (SharePoint) nichts unternommen wird, hat dies Auswirkungen auf den Dienst während der Migration.  |
| Generieren einer Vertrauensstellung der vertrauenden Seite für globale Azure AD-Endpunkte. | Kunden müssen manuell eine Vertrauensstellung der vertrauenden Seite (RPT) für [globale](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) Endpunkte erstellen. Dazu wird eine neue RPT über die GUI hinzugefügt, indem die globale Verbundmetadaten-URL verwendet und dann [Azure AD RPT-Anspruchsregeln](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (in der Hilfe zu AD FS) verwendet werden, um die Anspruchsregeln zu generieren und sie in die RPT zu importieren. | Organisationen mit Verbundauthentifizierung | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, hat dies Auswirkungen auf den Dienst während der Migration. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Wenn Sie dieselbe Azure Active Directory-Identitätspartition für Office 365 und Microsoft Azure in der Microsoft Cloud Deutschland-Instanz verwenden, stellen Sie sicher, dass Sie sich auf die kundengesteuerte Migration von Microsoft Azure-Diensten vorbereiten.
Die Migration Ihrer Microsoft Azure-Dienste darf nicht gestartet werden, bevor Ihr Office 365-Mandant die Migrationsphase 3 erreicht hat und vor Abschluss der Migrationsphase 8 abgeschlossen sein muss.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, welche Azure-Dienste verwendet werden, und bereiten Sie die künftige Migration von Deutschland zum Office 365-Dienstmandanten vor, indem Sie mit ihren Partnern zusammenarbeiten. Befolgen Sie die Schritte im [Playbook zur Azure-Migration](https://docs.microsoft.com/azure/germany/germany-migration-main). |<ul><li>Die Migration von Azure-Ressourcen liegt in der Verantwortung des Kunden und erfordert manuellen Anstrengungen beim Ausführen der vorgeschriebenen Schritte. Für eine erfolgreiche Migration von Azure-Diensten ist es wichtig, dass Sie verstehen, welche Dienste in der Organisation verwendet werden. </li><li> Kunden von Office 365 Deutschland mit Azure-Abonnements unter derselben Identitätspartition (Organisation) müssen die von Microsoft vorgeschriebene Reihenfolge bei der Migration von Abonnement und Diensten einhalten.</li></ul>|<ul><li>Kunden können über mehrere Azure-Abonnements verfügen, die jedes Abonnement enthalten, das Infrastruktur, Dienste und Plattformkomponenten enthält. </li><li> Administratoren sollten Abonnements und Beteiligte identifizieren, um sicherzustellen, dass eine schnelle Migration und Überprüfung im Rahmen dieses Migrationsereignis möglich ist. </li><li>Wenn Sie die Migration dieser Abonnements und Azure-Komponenten nicht innerhalb der vorgegebenen Zeitachse erfolgreich abgeschlossen haben, wirkt sich dies auf den Abschluss des Office- und Azure AD-Umstiegs auf Office 365-Dienste aus. Dies kann zu Datenverlusten führen. </li><li> Eine Message Center-Benachrichtigung signalisiert den Zeitpunkt, an dem die kundenorientierte Migration beginnen kann. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

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
