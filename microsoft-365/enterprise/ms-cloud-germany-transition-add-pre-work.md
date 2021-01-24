---
title: Vorbereitung für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921566"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Vorbereitung für die Migration von Microsoft Cloud Deutschland


Über diese Links gelangen Sie zu den Schritten für die Vorarbeit, die für Ihre Organisation relevant ist:

- Befolgen Sie [diese Schritte](#applies-to-everyone) für alle Abonnements.
- Führen Sie [diesen Schritt](#exchange-online) aus, wenn Sie Exchange Online oder eine Exchange-Hybridversion verwenden.
- Führen Sie [diesen Schritt](#sharepoint-online) aus, wenn Sie SharePoint Online verwenden.
- Fphren Sie [diesen Schritt](#mobile) aus, wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden.
- Führen Sie [diesen Schritt](#line-of-business-apps) aus, wenn Sie einen Drittanbieterdienst oder branchenspezifische Apps verwenden, die in Office 365 integriert sind.
- Führen Sie [diesen Schritt](#azure) aus, wenn Sie außer den in Ihrem Office 365-Abonnement enthaltenen noch weitere Azure-Dienste nutzen.
- Führen Sie [diesen Schritt](#dynamics365) aus, wenn Sie außerdem Dynamics 365 verwenden.
- Führen Sie [diesen Schritt](#power-bi) aus, wenn Sie außerdem Power BI verwenden.
- Führen Sie [diesen Schritt](#dns) für DNS-Änderungen aus.
- Führen Sie [diese Schritte](#federated-identity) aus, wenn Sie einen Identitätsverbund nutzen.

## <a name="applies-to-everyone"></a>Gilt für alle Benutzer

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Stellen Sie die Netzwerkkonnektivität mit [Office 365-Dienst-URLs und -IP-Adressen](https://aka.ms/o365urls) sicher. | Alle Clients und Dienste des Kunden, die für den Zugriff auf den Office 365-Dienst verwendet werden, müssen auf die Endpunkte für Office 365-Dienste zugreifen können. | Alle Kunden, die umsteigen, und Kunden mit Netzwerkzugriff, der auf Microsoft Cloud Deutschland beschränkt ist. | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Der Kunde bereitet DNS-Einträge für Exchange Online und Exchange Online Protection (MX-Eintrag usw.) vor. | Exchange Online-Kunden | Dies ist eine empfohlene Aktion. „Keine Aktion“ bedeutet, dass E-Mails von migrierten Kunden über Microsoft Cloud Deutschland weitergeleitet werden, bis die Dienste von Microsoft Cloud Deutschland deaktiviert werden. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Änderungen an DNS-Zonen von Kunden für Skype for Business Online. | Skype for Business Online-Kunden | - Es wird empfohlen, die Gültigkeitsdauer (Time-to-Live, TTL) für alle kundeneigenen DNS-Einträge für DNS-Einträge auf 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die von Microsoft verwaltete Übername im Zusammenhang mit dieser DNS-Änderung jederzeit innerhalb des bereitgestellten 24-Stunden-Änderungsfensters erfolgen. <br><br> - Eine Dienstunterbrechung in der Zukunft ist möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365-Diensten zu der migrierten Teams-Erfahrung umgeleitet. |
| Vorbereiten der Endbenutzer- und Administratorschulung und der Bereitschaft für den Umstieg auf Microsoft Teams. | Wenn Sie die Benutzerkommunikation und -bereitschaft planen wird der Umstieg von Skype auf Teams erfolgreich verlaufen. | Skype for Business Online-Kunden | - Kunden müssen sich über die neuen Dienste und die Verwendung der Dienste informieren, sobald ihre Dienste in die Office 365-Dienste übergegangen sind. <br><br> - Nachdem DNS-Änderungen sowohl für die Vanity-Domäne des Kunden als auch für die ursprüngliche Domäne vorgenommen wurden, melden sich Benutzer bei Skype for Business an und sehen, dass sie nun zu Teams migriert wurden. Dadurch wird auch der Desktopclient für Teams im Hintergrund heruntergeladen. |
| Vorbereiten der Endbenutzer- und Administratorschulung für Benutzer für iOS und Android, die ihr Konto aus Microsoft Outlook entfernen und erneut hinzufügen. | Microsoft Outlook für iOS-und Android-Konten, die mit Postfächern in Microsoft Cloud Deutschland konfiguriert sind, muss möglicherweise entfernt und erneut zu Outlook hinzugefügt werden, um die neue Office 365-Dienstkonfiguration ordnungsgemäß zu synchronisieren. | Kunden von Microsoft Outlook für iOS und Android | Zuvor für Microsoft Cloud Deutschland konfigurierte Outlook-Postfächer können die neue Office 365-Dienste-Konfiguration nicht verwenden, was zu Fehlern und schlechter Leistung anderer Benutzererfahrungen führt. IT-Administratoren werden aufgefordert, Dokumentation bereitzustellen, die Benutzer proaktiv anweist, ihre Konten für iOS und Android aus Microsoft Outlook zu entfernen und erneut hinzuzufügen, wenn nach der Migration Probleme beim Anmelden oder beim Synchronisieren von E-Mails auftreten. |
| Bereiten Sie sich darauf vor, Benutzer über das Neustarten und Anmelden bei ihren Clients nach der Migration zu benachrichtigen. | Die Office-Clientlizenzierung geht bei der Migration von Microsoft Cloud Deutschland zu Office 365-Diensten über. Clients erhalten nach dem Abmelden von Office-Clients eine neue gültige Lizenz. | Microsoft 365 Apps-Kunden |  Die Office-Produkte der Benutzer müssen die Lizenzen für Office 365-Dienste aktualisieren. Bei Lizenzen, die nicht aktualisiert werden, treten möglicherweise Fehler bei Office-Produkten auf. |
| Kündigen aller Testabonnements. | Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. | Alle Kunden | Die Testdienste sind abgelaufen und funktionieren nicht, wenn sie nach dem Abbruch von Benutzern aufgerufen werden. |
| Bereitstellen des Teams-Desktopclients für Benutzer, die auf Skype for Business in Deutschland zugreifen. | Durch die Migration werden Benutzer zur Zusammenarbeit, für Anrufe und für Chats in Teams verschoben. Stellen Sie entweder den Teams-Desktopclient bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Skype for Business-Kunden | Wenn keine Aktion ausgeführt wird, führt dies dazu, dass Teams-Dienste für die Zusammenarbeit nicht verfügbar sind. |
| Analysieren Sie die Unterschiede bei den Lizenzfeatures zwischen Microsoft Cloud Deutschland und Office 365-Diensten. | Office 365-Dienste umfassen zusätzliche Features und Dienste, die in der aktuellen Microsoft Cloud Deutschland nicht verfügbar sind. Während der Abonnementübertragung stehen Benutzern neue Features zur Verfügung. | Alle Kunden | - Analysieren Sie die unterschiedlichen Funktionen, die von den Lizenzen für Microsoft Cloud Deutschland und Office 365-Dienste bereitgestellt werden. Beginnen Sie mit der [Beschreibung des Office 365-Plattformdiensts](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> - Ermitteln Sie, ob neue Features von Office 365-Diensten anfänglich deaktiviert sein sollten, um die Auswirkungen auf die Benutzer oder die Verwaltung von Benutzeränderungen einzuschränken, und ändern Sie die Benutzerlizenzzuweisungen nach Bedarf. <br><br> - Bereiten Sie die Benutzer und Helpdesk-Mitarbeiter auf neue Dienste und Funktionen vor, die von Office 365-Diensten bereitgestellt werden. |
| Erstellen Sie organisationsweite [Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention) zum Schutz vor dem versehentlichen Löschen von Inhalten während der Migration.  | - Um sicherzustellen, dass Inhalte während der Migration nicht versehentlich von Endbenutzern gelöscht werden, können Kunden eine organisationsweite Aufbewahrungsrichtlinie aktivieren. <br><br> - Eine Aufbewahrung ist zwar nicht erforderlich, da die Aufbewahrungsfristen während der Migration erwartungsgemäß funktionieren sollten. Eine Aufbewahrungsrichtlinie ist daher ein Sicherheitsmechanismus. Gleichermaßen wird eine Aufbewahrungsrichtlinie vielleicht nicht von allen Kunden verwendet, insbesondere von denjenigen, die sich Sorgen um die übermäßige Aufbewahrung machen. | Office-Kunden | Wenden Sie Aufbewahrungsrichtlinie so an, wie in [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) beschrieben. |
| [Sicherung der Active Directory-Verbunddienste (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) für Notfallwiederherstellungsszenarios. | Kunden müssen die AD FS-Farm ordnungsgemäß sichern, um sicherzustellen, dass die Vertrauensstellung der vertrauenden Seite für globale Endpunkte und Deutschland-Endpunkte wiederhergestellt werden kann, ohne den Aussteller-URI der Domänen anzufassen. Microsoft empfiehlt die Verwendung von AD FS Rapid Restore für eine Sicherung der Farm und die entsprechende Wiederherstellung, falls erforderlich. | Organisationen mit Verbundauthentifizierung | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies während der Migration zu Dienstbeeinträchtigungen führen, wenn in der AD FS-Farm des Kunden Fehler auftreten. |


## <a name="exchange-online"></a>Exchange Online

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Benachrichtigen Sie externe Partner über den bevorstehenden Umstieg zu Office 365-Diensten. | Verfügbare Adressraumkonfigurationen ermöglichen die Freigabe von Frei-/Gebucht-Informationen mit Office 365. | Exchange Online-Kunden, die die Freigabe von Kalendern und verfügbarem Adressraum aktiviert haben. | Erforderliche Aktion.  Wenn diese Aktion nicht ausgeführt wird, kann dies in einer späteren Phase der Kundenmigration zu einem Dienst- oder Clientausfall führen. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>Für Exchange-Hybridbereitstellung

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Deinstallieren Sie frühere Versionen des Assistenten für die Hybridkonfiguration (HCW), und installieren und führen Sie dann die neueste Version 17.0.5378.0 von [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) aus. | Die neueste Version des HCW enthält die erforderlichen Updates zur Unterstützung von Kunden, die von Microsoft Cloud Deutschland zu Office 365-Diensten wechseln. <br><br> Updates umfassen Änderungen an den lokalen Zertifikateinstellungen für den Sendeconnector und den Empfangsconnector. | Exchange Online-Kunden, die die Hybridbereitstellung ausführen | Erforderliche Aktion. Wenn Sie diese Aktion nicht ausführen, kann dies zu einem Dienst- oder Clientausfall führen. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>Microsoft Office SharePoint Online

Wenn Sie über SharePoint 2013 verfügen:

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Begrenzen Sie SharePoint 2013-Workflows, die Sie während der SharePoint Online-Migration verwenden. | Reduzieren Sie SharePoint 2013-Workflows, und schließen Sie In-Flight-Workflows vor Übergängen ab. | SharePoint Online-Kunden | Wenn keine Aktion ausgeführt wird, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
|||||

## <a name="mobile"></a>Mobilgeräte

Wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden:

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | MDM-Lösungen können `outlook.de`-Endpunkte als Ziel haben. Bei diesem Umstieg auf Office 365-Dienste sollten Clientprofile auf die Office 365-Dienst-URL `outlook.office365.com`aktualisiert werden. | Exchange Online und MDM-Kunden | Clients funktionieren möglicherweise weiterhin, solange auf den `outlook.de`-Endpunkt zugegriffen werden kann. Wenn nicht mehr auf Microsoft Cloud Deutschland-Endpunkte zugegriffen werden kann, treten Fehler auf. |
|||||

## <a name="line-of-business-apps"></a>Branchenspezifische Apps

Wenn Sie einen Drittanbieterdienst oder branchenspezifische Apps verwenden, die in Office 365 integriert sind: 

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Dienste und Anwendungen von Drittanbietern, die in Office 365 integriert sind, können so programmiert werden, dass sie IP-Adressen und URLs von Microsoft Cloud Deutschland erwarten. | Alle Kunden | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
|||||

## <a name="azure"></a>Azure 

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, welche Azure-Dienste verwendet werden, und bereiten Sie die künftige Migration von Deutschland zum Office 365-Dienstmandanten vor, indem Sie mit ihren Partnern zusammenarbeiten. Befolgen Sie die Schritte im [Playbook zur Azure-Migration](https://docs.microsoft.com/azure/germany/germany-migration-main). | Die Migration von Azure-Ressourcen liegt in der Verantwortung des Kunden und erfordert manuellen Anstrengungen beim Ausführen der vorgeschriebenen Schritte. Für eine erfolgreiche Migration von Azure-Diensten ist es wichtig, dass Sie verstehen, welche Dienste in der Organisation verwendet werden. <br><br> Kunden von Office 365 Deutschland mit Azure-Abonnements unter derselben Identitätspartition (Organisation) müssen die von Microsoft vorgeschriebene Reihenfolge bei der Migration von Abonnement und Diensten einhalten. | Azure-Kunden | - Kunden können mehrere Azure-Abonnements haben, von denen jedes Abonnement Infrastruktur-, Dienst und Plattformkomponenten enthält. <br><br> - Administratoren sollten Abonnements und Beteiligte identifizieren, um sicherzustellen, dass im Rahmen dieses Migrationsereignisses eine schnelle Migration und Überprüfung möglich ist. <br><br> Wenn Sie die Migration dieser Abonnements und Azure-Komponenten nicht innerhalb der vorgegebenen Zeitachse erfolgreich abgeschlossen haben, wirkt sich dies auf den Abschluss des Office- und Azure AD-Umstiegs auf Office 365-Dienste aus. Dies kann zu Datenverlusten führen.  <br><br> - Eine Benachrichtigung über das Nachrichtencenter signalisiert den Punkt, an dem die von Kunden durchgeführte Migration beginnen kann. |
|||||

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

## <a name="dynamics-365"></a>Dynamics 365

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Für Dynamics 365-Sandkastenabonnements müssen Sie unbedingt die Produktionsumgebung der SQL-Instanz von Dynamics aus Ihrem Dynamics 365-Abonnement in Microsoft Cloud Deutschland herunterladen. Die neueste Produktionssicherung sollte vor der Sandkastenmigration im Sandkasten wiederhergestellt werden. | Die Migration von Dynamics 365 setzt voraus, dass Kunden sicherstellen, dass die Sandkastenumgebung mit der neuesten Produktionsdatenbank aktualisiert wird. | Microsoft Dynamics-Kunden | Das FastTrack-Team unterstützt Kunden bei der Durchführung von Trockentests, um das Versionsupgrade von 8.x auf 9.1.x zu überprüfen. |
|||||

## <a name="power-bi"></a>Power BI

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Entfernen von Objekten aus Power BI-Abonnements, die nicht von Power BI Microsoft Cloud Deutsch nach Office 365-Diensten migriert werden. | Für die Migration von Power BI-Diensten sind Kundenaktionen erforderlich, um bestimmte Artefakte wie Datasets und Dashboards zu löschen. | Power BI-Kunden | Administratoren müssen möglicherweise die folgenden Elemente aus Ihrem Abonnement entfernen: <br> - Echtzeit-Datasets (beispielsweise Streaming- oder Push-Datasets). <br> - Lokale Power BI-Konfiguration des Datengateways und die Datenquelle. |
|||||

## <a name="dns"></a>DNS

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Entfernen Sie MSOID, CNAME aus dem DNS des Kunden, wenn es vor der Azure AD-Umstellung existiert. Ein TTL von 5 Minuten kann eingestellt werden, sodass die Änderung schnell greift. | Kundeneigene Änderungen an DNS-Zonen | Kunden von Office-Clientdiensten | 
|||||

## <a name="federated-identity"></a>Identitätsverbund

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Kennung für Single Sign-On (SSO) zu einer vorhandenen Vertrauensstellung hinzufügen und automatische AD FS-Metadatenaktualisierungen deaktivieren. | Bevor Sie mit der Migration beginnen, muss eine ID zur AD FS-Vertrauensstellung hinzugefügt werden. Um ein versehentliches Entfernen der Kennung der vertrauenden Partei zu vermeiden, deaktivieren Sie die automatische Aktualisierung für Metadaten-Updates. <br><br> Führen Sie diesen Befehl auf dem AD FS-Server aus: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Organisationen mit Verbundauthentifizierung | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, hat dies Auswirkungen auf den Dienst während der Migration.  |
| Generieren einer Vertrauensstellung der vertrauenden Seite für globale Azure AD-Endpunkte. | Kunden müssen manuell eine Vertrauensstellung der vertrauenden Seite (RPT) für [globale](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) Endpunkte erstellen. Dazu wird eine neue RPT über die GUI hinzugefügt, indem die globale Verbundmetadaten-URL verwendet und dann [Azure AD RPT-Anspruchsregeln](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (in der Hilfe zu AD FS) verwendet werden, um die Anspruchsregeln zu generieren und sie in die RPT zu importieren. | Organisationen mit Verbundauthentifizierung | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, hat dies Auswirkungen auf den Dienst während der Migration. |
|||||

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Aktionen und Auswirkungen der Migrationsphasen](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen für [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
