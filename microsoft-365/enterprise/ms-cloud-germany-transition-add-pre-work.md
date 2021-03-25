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
ms.openlocfilehash: d05b3fc06c4530a69c49962b0d2b793353033c99
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165609"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Vorbereitung für die Migration von Microsoft Cloud Deutschland

Über diese Links gelangen Sie zu den Schritten für die Vorarbeit, die für Ihre Organisation relevant ist:

- Gehen **Sie für alle Kunden,** die Office 365 in Microsoft Cloud Deutschland verwenden, wie im folgenden Schritt [vor.](#general-tenant-migration-considerations)
- Gehen **Sie für DNS-Änderungen** wie in diesem [Schritt vor.](#dns)
- Wenn Sie Active **Directory Federation Services** lokal verwenden, gehen Sie wie in den folgenden Schritten [vor.](#active-directory-federation-services-ad-fs)
- Wenn Sie **SharePoint Online verwenden,** gehen Sie [wie in diesem Schritt vor.](#sharepoint-online)
- Wenn Sie Exchange Online oder **Exchange hybrid** **verwenden,** gehen [Sie wie in diesem Schritt vor.](#exchange-online)
- Wenn Sie **Skype for Business Online verwenden,** führen Sie diesen Schritt [aus.](#skype-for-business-online)
- Fphren Sie [diesen Schritt](#mobile-device-management) aus, wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden.
- Wenn Sie Dienste  von Drittanbietern oder **Branchen-Apps verwenden,** die in Office 365 integriert sind, gehen Sie wie in diesem [Schritt vor.](#line-of-business-apps)
- Wenn Sie auch **Dynamics 365** verwenden, gehen [Sie wie in diesem Schritt vor.](#dynamics365)
- Wenn Sie auch **Power BI verwenden,** gehen [Sie wie in diesem Schritt vor.](#power-bi)
- Wenn Sie auch Azure-Dienste **mit** Ihrem Office 365-Abonnement verwenden, gehen [Sie wie in diesem Schritt vor.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>Überlegungen zur allgemeinen Mandantenmigration

**Gilt für:** Alle Kunden, die Office 365 in der Microsoft Deutschland Cloud-Instanz verwenden

Office 365-Mandanten- und Benutzerbezeichner werden während der Migration beibehalten. Azure AD-Dienstanrufe werden von Microsoft Cloud Deutschland zu Globalen Office 365-Diensten umgeleitet und sind für Office 365-Dienste transparent.

- Anträge von Datensubjekten (Data Protection Regulation, DSGVO) werden im Azure Admin-Portal für zukünftige Anforderungen ausgeführt. Alle älteren oder Nicht-Kunden-Diagnosedaten, die sich in Microsoft Cloud Deutschland befinden, werden spätestens nach 30 Tagen gelöscht.
- Mehrstufige Authentifizierungsanforderungen (Multi-Factor Authentication, MFA), die die Microsoft Authenticator-Anzeige als Benutzerobjekt-ID (GUID) verwenden, während der Mandant in Office 365-Dienste kopiert wird. MFA-Anforderungen werden trotz dieses Anzeigeverhaltens erwartungsgemäß ausgeführt.  Microsoft Authenticator-Konten, die mithilfe von Office 365-Dienstendpunkten aktiviert wurden, zeigen den Benutzerprinzipalnamen (User Principal Name, UPN) an.  Konten, die mithilfe von Microsoft Cloud Deutschland-Endpunkten hinzugefügt wurden, zeigen die Benutzer-ObjectID an, aber es können sowohl Microsoft Cloud Deutschland- als auch Office 365-Dienstendpunkte verwendet werden.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Bereiten Sie sich darauf vor, Benutzer über das Neustarten und Anmelden bei ihren Clients nach der Migration zu benachrichtigen. | Die Office-Clientlizenzierung geht bei der Migration von Microsoft Cloud Deutschland zu Office 365-Diensten über. Clients erhalten nach dem Abmelden von Office-Clients eine neue gültige Lizenz. | Die Office-Produkte der Benutzer müssen die Lizenzen für Office 365-Dienste aktualisieren. Bei Lizenzen, die nicht aktualisiert werden, treten möglicherweise Fehler bei Office-Produkten auf. |
| Stellen Sie die Netzwerkkonnektivität mit [Office 365-Dienst-URLs und -IP-Adressen](https://aka.ms/o365urls) sicher. | Alle clients and services hosted by the customer that are used to access Office 365 service must be able to access the Office 365 Global services endpoints. <br>Falls Sie oder Ihre Zusammenarbeitspartner über Firewallregeln verfügen, die den Zugriff auf die URLs und IP-Adressen unter UrLs und IP-Adressen von [Office 365-Diensten](https://aka.ms/o365urls) verhindern, müssen Sie die Firewallregeln ändern, um den Zugriff auf die globalen Office 365-Dienstendpunkte zu ermöglichen.| Fehler des Diensts oder der Clientsoftware können auftreten, wenn dies nicht vor Phase 4 erfolgt  |
| Kündigen aller Testabonnements. | Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. | Die Testdienste sind abgelaufen und funktionieren nicht, wenn sie nach dem Abbruch von Benutzern aufgerufen werden. |
| Analysieren Sie die Unterschiede bei den Lizenzfeatures zwischen Microsoft Cloud Deutschland und den Office 365 Global Services. | Office 365-Dienste umfassen zusätzliche Features und Dienste, die in der aktuellen Microsoft Cloud Deutschland nicht verfügbar sind. Während der Abonnementübertragung stehen Benutzern neue Features zur Verfügung. | <ul><li> Analysieren Sie die verschiedenen Features, die von den Lizenzen für Microsoft Cloud Deutschland und Office 365 Global Services bereitgestellt werden. Beginnen Sie mit der [Beschreibung des Office 365-Plattformdiensts](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Ermitteln Sie, ob neue Features von Office 365-Diensten zunächst deaktiviert werden sollten, um Die Auswirkungen auf Benutzer oder die Verwaltung von Benutzeränderung zu begrenzen und die Zuweisungen von Benutzerlizenzen bei Bedarf zu ändern. </li><li>Bereiten Sie Benutzer und Helpdeskmitarbeiter auf neue Dienste und Features vor, die von Office 365-Diensten bereitgestellt werden. |
| Erstellen Sie organisationsweite [Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention) zum Schutz vor dem versehentlichen Löschen von Inhalten während der Migration.  |<ul><li>Um sicherzustellen, dass Inhalte während der Migration nicht versehentlich von Endbenutzern gelöscht werden, können Kunden eine organisationsweite Aufbewahrungsrichtlinie aktivieren. </li><li>Auch wenn die Aufbewahrung nicht erforderlich ist, da Aufbewahrungsspeicher während der Migration jederzeit wie erwartet funktionieren sollten, ist das Einrichten einer Aufbewahrungsrichtlinie ein Sicherungssicherheitsmechanismus. Gleichermaßen wird eine Aufbewahrungsrichtlinie vielleicht nicht von allen Kunden verwendet, insbesondere von denjenigen, die sich Sorgen um die übermäßige Aufbewahrung machen.</li></ul>| Wenden Sie Aufbewahrungsrichtlinie so an, wie in [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) beschrieben. Es kann zu Ausfällen des Dienstes oder der Client-Software kommen, wenn dies nicht vor Phase 4 von 9 erfolgt. </li></ul>|
|||||

## <a name="dns"></a>DNS

<!-- before phase 9 -->

**Gilt für**: Kunden, die einen _benutzerdefinierten msoid_ CNAME in ihrer eigenen #A0 festlegen

Wenn konfiguriert, betrifft _msoid_ CNAME nur Kunden, die Office Desktop Client verwenden (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Falls Sie einen DNS-CNAME namens _msoid_ in einem oder mehreren #A0 festgelegt haben, die Sie besitzen, müssen Sie den CNAME bis spätestens Ende von Phase 8 entfernen. Sie können das CNAME _msoid_ jederzeit vor dem Ende von Phase 8 entfernen.

Um zu überprüfen, ob Sie einen CNAME in Ihrem _#A0_ festgelegt haben, führen Sie die folgenden Schritte aus, und ersetzen Contoso.com durch Ihren eigenen Domänennamen:

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

Wenn die Befehlszeile einen #A0 zurückgibt, entfernen Sie _den msoiden_ CNAME aus Ihrer Domäne.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory-Verbunddienste (AD FS)

<!-- before phase 4 -->

**Betrifft:** Kunden, die AD FS lokal verwenden, um Benutzer zu authentifizieren, die eine Verbindung mit Microsoft Office 365 herstellen<br>
**Anwendung :** Immer vor Beginn von Phase 4

Lesen und Anwenden der [ADFS-Migrationsschritte](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Gilt für**: Kunden, die SharePoint 2013 lokal verwenden<br>
**Anwendung :** Immer vor Beginn von Phase 4

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Begrenzen Sie SharePoint 2013-Workflows, die Sie während der SharePoint Online-Migration verwenden. | Reduzieren Sie SharePoint 2013-Workflows, und schließen Sie In-Flight-Workflows vor Übergängen ab. | Wenn keine Aktion ausgeführt wird, kann dies zu Verwirrungen bei Benutzern und Helpdesk-Anrufen führen. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Gilt für**: Exchange Online-Kunden, die den Freigabekalender und den Verfügbarkeitsadressenraum aktiviert haben<br>
**Anwendung :** Immer vor Ende von Phase 9

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Benachrichtigen Sie externe Partner über den bevorstehenden Umstieg zu Office 365-Diensten. | Verfügbare Adressraumkonfigurationen ermöglichen die Freigabe von Frei-/Gebucht-Informationen mit Office 365. | Wenn diese Aktion nicht ausgeführt wird, kann dies in einer späteren Phase der Kundenmigration zu einem Dienst- oder Clientausfall führen. |
||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online-Hybridkonfiguration

**Gilt für:** Alle Kunden, die eine aktive Exchange-Hybridkonfiguration mit lokalen Exchange-Servern verwenden<br>
**Anwendung :** Immer vor Beginn von Phase 5

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie jederzeit auf die neueste Version des Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW), bevor Ihr Mandant in Die Migrationsphase 5 eintritt. Sie können diese Aktivität unmittelbar nach Erhalt der Benachrichtigung des Nachrichtencenters starten, dass Ihre Office 365-Mandantenmigration begonnen hat (Phase 1).<br>Ihr Exchange-Administrator muss frühere Versionen des HCW deinstallieren und dann die neueste Version (17.0.5378.0 oder höher) von installieren und [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) ausführen. |<ul><li>Die neueste Version des HCW enthält die erforderlichen Updates zur Unterstützung der Exchange Online-Migration von der Microsoft Cloud Deutschland-Instanz zu Office 365 Global Services.</li><li> Updates umfassen Änderungen an lokalen Zertifikateinstellungen für den _Sendeconnector_ und den _Empfangsconnector._</li><li>Wählen Sie bei der Ausführung des HCW vor Phase 5 auf der 2. Seite des HCW unter _Office 365 Exchange Online_ im Listenfeld unter Meine Office _365-Organisation_ die Option "Office 365 Deutschland" aus.</li><li>**HINWEIS**: Nach Abschluss der Office 365-Mandantenmigration nach Phase 9 entfernen und installieren Sie den HCW erneut, dieses Mal mit den Einstellungen "Office 365 Worldwide" auf der 2. Seite des HCW, um Ihre Hybrideinrichtung mit dem globalen Exchange Online-Dienst abzuschließen.</li></ul>|Wenn der HCW vor Phase 5 (Exchange-Migration) nicht ausgeführt wird, kann dies zu Dienst- oder Clientfehlern führen. |
| Einrichten von AuthServer lokal mit Verweisen auf den globalen Sicherheitstokendienst (Security Token Service, STS) für die Authentifizierung | Dadurch wird sichergestellt, dass Authentifizierungsanforderungen für Exchange-Verfügbarkeitsanforderungen von Benutzern im Migrationsstatus, die auf die lokale Hybridumgebung zielen, für den Zugriff auf den lokalen Dienst authentifiziert werden. Auf ähnliche Weise wird die Authentifizierung von Anforderungen von lokalen an Office 365 Global Services-Endpunkte sichergestellt. | Nach Abschluss der Azure AD-Migration (Phase 2) muss der Administrator der lokalen Exchange(Hybrid-)Topologie einen neuen Authentifizierungsdienstendpunkt für die globalen Office 365-Dienste hinzufügen. Ersetzen Sie mit diesem Befehl aus Exchange PowerShell durch die Mandanten-ID Ihrer Organisation im `<TenantID>` Azure-Portal in Azure Active Directory.<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> Wenn Sie diese Aufgabe nicht ausführen, kann es sein, dass die Frei/Gebucht-Hybridanforderungen keine Informationen für Postfachbenutzer bereitstellen, die von Microsoft Cloud Deutschland zu Office 365-Diensten migriert wurden.  |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Gilt für**: Skype For Business Online-Kunden<br>
**Anwendung :** Immer vor Beginn der Phase 7

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Bereitstellen des Teams-Desktopclients für Benutzer, die auf Skype for Business in Deutschland zugreifen. | Die Migration verschiebt Skype for Business-Benutzer zur Zusammenarbeit, zum Anruf und zum Chat zu Microsoft Teams. Stellen Sie entweder den Microsoft Teams-Desktopclient bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Untätigkeit führt zur Nichtverfügbarkeit von Microsoft Teams-Zusammenarbeitsdiensten. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Änderungen an DNS-Zonen von Kunden für Skype for Business Online. |<ul><li>Es wird empfohlen, die Time-to-Live (TTL) für alle dns-Einträge im Besitz des Kunden auf 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die von Microsoft verwaltete Übername im Zusammenhang mit dieser DNS-Änderung jederzeit innerhalb des bereitgestellten 24-Stunden-Änderungsfensters erfolgen. </li><li>Dienstunterbrechungen sind in Zukunft möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365-Diensten zu der migrierten Teams-Erfahrung umgeleitet. </li></ul>|
| Vorbereiten der Endbenutzer- und Administratorschulung und der Bereitschaft für den Umstieg auf Microsoft Teams. | Wenn Sie die Benutzerkommunikation und -bereitschaft planen wird der Umstieg von Skype auf Teams erfolgreich verlaufen. | <ul><li>Clients müssen sich der neuen Dienste bewusst sein und wissen, wie sie nach dem Übergang ihrer Dienste zu den Office 365-Diensten verwendet werden. </li><li>Nachdem DNS-Änderungen für die Vanitydomänen des Kunden und die ursprüngliche Domäne vorgenommen wurden, würden sich Die Benutzer bei Skype for Business anmelden und sehen, dass sie jetzt zu Teams migriert werden. Dadurch wird auch der Desktopclient für Teams im Hintergrund heruntergeladen. </li></ul>|
||||

## <a name="mobile-device-management"></a>Mobile Geräteverwaltung

<!-- before phase 5 -->
**Gilt für:** Kunden, die eine Mobile Device Management (MDM)-Lösung eines Drittanbieters verwenden<br>
**Anwendung :** Immer vor Beginn von Phase 5

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Vorbereiten der Endbenutzer- und Administratorschulung für Benutzer für iOS und Android, die ihr Konto aus Microsoft Outlook entfernen und erneut hinzufügen. | Microsoft Outlook für iOS-und Android-Konten, die mit Postfächern in Microsoft Cloud Deutschland konfiguriert sind, muss möglicherweise entfernt und erneut zu Outlook hinzugefügt werden, um die neue Office 365-Dienstkonfiguration ordnungsgemäß zu synchronisieren. | Kunden von Microsoft Outlook für iOS und Android | Zuvor für Microsoft Cloud Deutschland konfigurierte Outlook-Postfächer können die neue Office 365-Dienste-Konfiguration nicht verwenden, was zu Fehlern und schlechter Leistung anderer Benutzererfahrungen führt. IT-Administratoren werden aufgefordert, Dokumentation bereitzustellen, die Benutzer proaktiv anweist, ihre Konten für iOS und Android aus Microsoft Outlook zu entfernen und erneut hinzuzufügen, wenn nach der Migration Probleme beim Anmelden oder beim Synchronisieren von E-Mails auftreten. |
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Lösungen für die mobile Geräteverwaltung (Mobile Device Management, MDM) können auf `outlook.de` Endpunkte zielen. Bei diesem Umstieg auf Office 365-Dienste sollten Clientprofile auf die Office 365-Dienst-URL `outlook.office365.com`aktualisiert werden. | Exchange Online und MDM-Kunden | Clients funktionieren möglicherweise weiterhin, solange auf den `outlook.de`-Endpunkt zugegriffen werden kann. Wenn nicht mehr auf Microsoft Cloud Deutschland-Endpunkte zugegriffen werden kann, treten Fehler auf. |
|||||

## <a name="line-of-business-apps"></a>Branchenspezifische Apps

**Gilt für:** Kunden, die Branchen-Apps mit Endpunkten verwenden, die von Microsoft Cloud Deutschland bereitgestellt werden<br>
**Anwendung :** Nach Abschluss von Phase 2 und vor Ende von Phase 9

Wenn Sie einen Drittanbieterdienst oder Branchen-Apps verwenden, die in Office 365 integriert sind, müssen Sie alle Abhängigkeiten von Endpunkten auflösen, die von der Microsoft Cloud Deutschland-Instanz bereitgestellt werden. Wenn Ihre Branchen-Apps beispielsweise eine Verbindung mit `https://graph.microsoft.de/` herstellen, müssen Sie den Endpunkt in `https://graph.microsoft.com/` ändern. Die Endpunkte des Microsoft Office 365 Global Service stehen Ihrem Mandanten nach Phase 2 zur Verfügung.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Dienste und Anwendungen von Drittanbietern, die in Office 365 integriert sind, können so programmiert werden, dass sie IP-Adressen und URLs von Microsoft Cloud Deutschland erwarten. | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gilt für**: Kunden, die Microsoft Dynamics 365 verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Für Dynamics 365-Sandkastenabonnements müssen Sie unbedingt die Produktionsumgebung der SQL-Instanz von Dynamics aus Ihrem Dynamics 365-Abonnement in Microsoft Cloud Deutschland herunterladen. Die neueste Produktionssicherung sollte vor der Sandkastenmigration im Sandkasten wiederhergestellt werden. | Die Migration von Dynamics 365 setzt voraus, dass Kunden sicherstellen, dass die Sandkastenumgebung mit der neuesten Produktionsdatenbank aktualisiert wird. | Das FastTrack-Team unterstützt Kunden bei der Durchführung von Trockentests, um das Versionsupgrade von 8.x auf 9.1.x zu überprüfen. |
||||

## <a name="power-bi"></a>Power BI

**Gilt für**: Kunden, die Power BI verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen von Objekten aus Power BI-Abonnements, die nicht von Power BI Microsoft Cloud Deutsch nach Office 365-Diensten migriert werden. | Für die Migration von Power BI-Diensten sind Kundenaktionen erforderlich, um bestimmte Artefakte wie Datasets und Dashboards zu löschen. | <ul><li>Administratoren müssen möglicherweise die folgenden Elemente aus Ihrem Abonnement entfernen: </li><li>Real-Time Datasets (z. B. Streaming- oder Push-Datasets) </li><li>Lokale Power BI Data Gateway-Konfiguration und Datenquelle </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Wenn Sie dieselbe Azure Active Directory-Identitätspartition für Office 365 und Microsoft Azure in der Microsoft Cloud Deutschland-Instanz verwenden, stellen Sie sicher, dass Sie sich auf die kundengesteuerte Migration von Microsoft Azure-Diensten vorbereiten.

> [!NOTE]
> Die Migration Ihrer Microsoft Azure-Dienste darf nicht gestartet werden, bevor Ihr Office 365-Mandant die Migrationsphase 3 erreicht hat und vor Abschluss der Migrationsphase 8 abgeschlossen sein muss.

Kunden, die Office 365- und Azure-Ressourcen (z. B. Netzwerk, Datenverarbeitung und Speicher) verwenden, führen die Migration von Ressourcen zur Office 365-Dienstinstanz aus. Diese Migration liegt in der Verantwortung des Kunden. Beiträge des Nachrichtencenters signalisieren den Anfang. Die Migration muss vor Abschluss der Azure AD-Organisation in der Office 365-Diensteumgebung abgeschlossen sein. Informationen zu Azure-Migrationen finden Sie im Azure-Migrationsplaybook [Übersicht über den Migrationsleitfaden für Azure Deutschland](https://docs.microsoft.com/azure/germany/germany-migration-main).

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, welche Azure-Dienste verwendet werden, und bereiten Sie die künftige Migration von Deutschland zum Office 365-Dienstmandanten vor, indem Sie mit ihren Partnern zusammenarbeiten. Befolgen Sie die Schritte im [Playbook zur Azure-Migration](/azure/germany/germany-migration-main). |<ul><li>Die Migration von Azure-Ressourcen liegt in der Verantwortung des Kunden und erfordert manuellen Anstrengungen beim Ausführen der vorgeschriebenen Schritte. Für eine erfolgreiche Migration von Azure-Diensten ist es wichtig, dass Sie verstehen, welche Dienste in der Organisation verwendet werden. </li><li> Kunden von Office 365 Deutschland mit Azure-Abonnements unter derselben Identitätspartition (Organisation) müssen die von Microsoft vorgeschriebene Reihenfolge bei der Migration von Abonnement und Diensten einhalten.</li></ul>|<ul><li>Kunden können über mehrere Azure-Abonnements verfügen, die jedes Abonnement enthalten, das Infrastruktur, Dienste und Plattformkomponenten enthält. </li><li> Administratoren sollten Abonnements und Beteiligte identifizieren, um sicherzustellen, dass eine schnelle Migration und Überprüfung im Rahmen dieses Migrationsereignis möglich ist. </li><li>Wenn Sie die Migration dieser Abonnements und Azure-Komponenten nicht innerhalb der vorgegebenen Zeitachse erfolgreich abgeschlossen haben, wirkt sich dies auf den Abschluss des Office- und Azure AD-Umstiegs auf Office 365-Dienste aus. Dies kann zu Datenverlusten führen. </li><li> Eine Message Center-Benachrichtigung signalisiert den Zeitpunkt, an dem die kundenorientierte Migration beginnen kann. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

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

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
