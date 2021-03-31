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
ms.openlocfilehash: fb352c17d9868cf5c42034e198be63b6e0543dbb
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445602"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Vorbereitung für die Migration von Microsoft Cloud Deutschland

Über diese Links gelangen Sie zu den Schritten für die Vorarbeit, die für Ihre Organisation relevant ist:

- Für **alle Kunden**, die Office 365 in Microsoft Cloud Deutschland verwenden: Führen Sie [diese Schritte](#general-tenant-migration-considerations) aus.
- Führen Sie [diesen Schritt](#dns) für **DNS-Änderungen** aus.
- Wenn Sie **Active Directory-Verbunddienste (AD FS)** lokal verwenden, führen Sie [diese Schritte](#active-directory-federation-services-ad-fs) aus.
- Führen Sie [diesen Schritt](#sharepoint-online) aus, wenn Sie **SharePoint Online** verwenden.
- Führen Sie [diesen Schritt](#exchange-online) aus, wenn Sie **Exchange Online** oder eine **Exchange-Hybridversion** verwenden.
- Wenn Sie **Skype for Business Online** verwenden, führen Sie [diesen Schritt](#skype-for-business-online) aus
- Führen Sie [diesen Schritt](#mobile-device-management) aus, wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden.
- Führen Sie [diesen Schritt](#line-of-business-apps) aus, wenn Sie einen **Drittanbieterdienst** oder **branchenspezifische Apps** verwenden, die in Office 365 integriert sind.
- Führen Sie [diesen Schritt](#dynamics365) aus, wenn Sie außerdem **Dynamics 365** verwenden.
- Führen Sie [diesen Schritt](#power-bi) aus, wenn Sie außerdem **Power BI** verwenden.
- Führen Sie [diesen Schritt](#microsoft-azure) aus, wenn Sie **Azure-Dienste** mit Ihrem Office 365-Abonnement nutzen.

## <a name="general-tenant-migration-considerations"></a>Überlegungen zur allgemeinen Mandantenmigration

**Gilt für:** Alle Kunden, die Office 365 in der Microsoft Deutschland Cloud-Instanz verwenden

Office 365-Mandanten- und Benutzer-IDs bleiben während der Migration erhalten. Azure AD-Dienstaufrufe werden von Microsoft Cloud Deutschland zu Office 365-Globalen Diensten umgeleitet und sind für Office 365-Dienste transparent.

- Anträge betroffener Personen (DSRs) für die Datenschutzbestimmungen (DSGVO) werden im Azure-Verwaltungsportal für zukünftige Anforderungen ausgeführt. Alle älteren oder Nicht-Kunden-Diagnosedaten, die sich in Microsoft Cloud Deutschland befinden, werden spätestens nach 30 Tagen gelöscht.
- MFA-Anforderungen (Multi-Factor Authentication), die Microsoft Authenticator als Benutzer-ObjectID (GUID) anzeigen, während der Mandant in Office 365-Dienste kopiert wird. MFA-Anforderungen werden trotz dieses Anzeigeverhaltens erwartungsgemäß ausgeführt.  Microsoft Authenticator-Konten, die mithilfe von Office 365-Dienstendpunkten aktiviert wurden, zeigen den Benutzerprinzipalnamen (User Principal Name, UPN) an.  Konten, die mithilfe von Microsoft Cloud Deutschland-Endpunkten hinzugefügt wurden, zeigen die Benutzer-ObjectID an, aber es können sowohl Microsoft Cloud Deutschland- als auch Office 365-Dienstendpunkte verwendet werden.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Bereiten Sie sich darauf vor, Benutzer über das Neustarten und Anmelden bei ihren Clients nach der Migration zu benachrichtigen. | Die Office-Clientlizenzierung geht bei der Migration von Microsoft Cloud Deutschland zu Office 365-Diensten über. Clients erhalten nach dem Abmelden von Office-Clients eine neue gültige Lizenz. | Die Office-Produkte der Benutzer müssen die Lizenzen für Office 365-Dienste aktualisieren. Bei Lizenzen, die nicht aktualisiert werden, treten möglicherweise Fehler bei Office-Produkten auf. |
| Stellen Sie die Netzwerkkonnektivität mit [Office 365-Dienst-URLs und -IP-Adressen](https://aka.ms/o365urls) sicher. | Alle Clients und Dienste, die vom Kunden gehostet und für den Zugriff auf den Office 365-Dienst verwendet werden, müssen auf die Endpunkte für Office 365 Global-Dienste zugreifen können. <br>Falls Sie oder Ihre Zusammenarbeitspartner Firewallregeln festgelegt haben, die den Zugriff auf die URLs und IP-Adressen verhindern würden, die unter [Office 365-Dienst-URLs und -IP-Adressen](https://aka.ms/o365urls) aufgeführt sind, müssen Sie diese Firewallregeln ändern, um den Zugriff auf die Office 365 Global-Dienstendpunkte zu ermöglichen.| Es kann zu Ausfällen des Dienstes oder der Client-Software kommen, wenn dies nicht vor Phase 4 erfolgt.  |
| Kündigen aller Testabonnements. | Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. | Die Testdienste sind abgelaufen und funktionieren nicht, wenn sie nach der Kündigung von Benutzern aufgerufen werden. |
| Analysieren Sie die Unterschiede bei den Lizenzfeatures zwischen Microsoft Cloud Deutschland und den Office 365-Globalen Diensten. | Office 365-Dienste umfassen zusätzliche Features und Dienste, die in der aktuellen Microsoft Cloud Deutschland nicht verfügbar sind. Während der Abonnementübertragung stehen Benutzern neue Features zur Verfügung. | <ul><li> Analysieren Sie die unterschiedlichen Features, die über Lizenzen für Microsoft Cloud Deutschland und Office 365-Globale Dienste bereitgestellt werden. Beginnen Sie mit der [Beschreibung des Office 365-Plattformdiensts](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Ermitteln Sie, ob neue Features von Office 365-Diensten anfänglich deaktiviert sein sollten, um die Auswirkungen auf die Benutzer oder die Verwaltung von Benutzeränderungen einzuschränken, und ändern Sie die Benutzerlizenzzuweisungen nach Bedarf. </li><li>Bereiten Sie die Benutzer und Helpdesk-Mitarbeiter auf neue Dienste und Funktionen vor, die von Office 365-Diensten bereitgestellt werden. |
| Erstellen Sie organisationsweite [Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention) zum Schutz vor dem versehentlichen Löschen von Inhalten während der Migration.  |<ul><li>Um sicherzustellen, dass Inhalte während der Migration nicht versehentlich von Endbenutzern gelöscht werden, können Kunden eine organisationsweite Aufbewahrungsrichtlinie aktivieren. </li><li>Eine Aufbewahrung ist zwar nicht erforderlich, da die Aufbewahrungsfristen während der Migration erwartungsgemäß funktionieren sollten. Eine Aufbewahrungsrichtlinie ist daher ein Sicherheitsmechanismus. Gleichermaßen wird eine Aufbewahrungsrichtlinie vielleicht nicht von allen Kunden verwendet, insbesondere von denjenigen, die sich Sorgen um die übermäßige Aufbewahrung machen.</li></ul>| Wenden Sie Aufbewahrungsrichtlinie so an, wie in [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) beschrieben. Es kann zu Ausfällen des Dienstes oder der Client-Software kommen, wenn dies nicht vor Phase 4 von 9 erfolgt. </li></ul>|
|||||

## <a name="dns"></a>DNS

<!-- before phase 9 -->

**Gilt für**: Kunden, die ein benutzerdefiniertes _msoid_ CNAME in ihrer eigenen DNS-Domäne festlegen

Wenn konfiguriert, wirkt sich das _msoid_ CNAME nur auf Kunden aus, die den Office-Desktopclient verwenden (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Falls Sie ein DNS CNAME namens _msoid_ in einem oder vielen DNS-Namespaces, die Sie besitzen, festgelegt haben, müssen Sie das CNAME mindestens bis zum Ende der Phase 8 entfernen. Sie können das CNAME _msoid_ jederzeit vor dem Ende der Phase 8 entfernen.

Um zu bestätigen, dass Sie ein CNAME in ihrem DNS-Namespace festgelegt haben, folgen Sie den Schritten unten und ersetzen Sie _contoso.com_ mit Ihrem eigenen Domänennamen:

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

Wenn die Befehlszeile einen DNS-Datensatz zurückgibt, entfernen Sie das _msoid_ CNAME von Ihrer Domäne.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory-Verbunddienste (AD FS)

<!-- before phase 4 -->

**Gilt für**: Kunden, die AD FS lokal für die Authentifizierung von Benutzern verwenden, die eine Verbindung mit Microsoft Office 365 herstellen<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 4

Lesen und Anwenden der [ADFS-Migrationsschritte](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Gilt für**: Kunden, die SharePoint 2013 lokal verwenden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 4

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Begrenzen Sie SharePoint 2013-Workflows, die Sie während der SharePoint Online-Migration verwenden. | Reduzieren Sie SharePoint 2013-Workflows, und schließen Sie In-Flight-Workflows vor Übergängen ab. | Wenn keine Aktion ausgeführt wird, kann dies zu Verwirrung bei Benutzern und zu Helpdesk-Anrufen führen. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Gilt für**: Exchange Online-Kunden, die die Freigabe von Kalendern und Verfügbarkeitsadressraum aktiviert haben<br>
**Bei Anwendung**: Jederzeit vor Ende der Phase 9

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Benachrichtigen Sie externe Partner über den bevorstehenden Umstieg zu Office 365-Diensten. | Verfügbare Adressraumkonfigurationen ermöglichen die Freigabe von Frei-/Gebucht-Informationen mit Office 365. | Wenn dies nicht ausgeführt wird, kann dies in einer späteren Phase der Kundenmigration zu einem Dienst- oder Clientausfall führen. |
||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online Hybrid-Konfiguration

**Gilt für:** Alle Kunden, die eine aktive Exchange-Hybridkonfiguration mit lokalen Exchange-Servern verwenden<br>
**Anwendung :** Immer vor Beginn von Phase 5

Unternehmenskunden mit einer Hybridbereitstellung von Exchange Online und einer lokalen Exchange Server führen den Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW) aus, um die Hybrideinrichtung zu verwalten und zu einrichten. Beim Übergang von Microsoft Cloud Deutschland zur Office 365 Deutschland-Region muss der Administrator den neuesten Build von HCW im "Office 365 Deutschland"-Modus erneut ausführen, bevor die Exchange-Migration (Phase 5) beginnt. Führen Sie dann den HCW nach Abschluss von Phase 5 erneut im Modus "Office 365 Worldwide" aus, um die lokale Bereitstellung mit den Office 365 Deutschland-Regioneneinstellungen zu finalisieren.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| (Pre-Stage 5) – Erneutes Ausführen von HCW mithilfe von Office 365 Deutschland-Einstellungen <br><br> <i>Sie können diese Aktivität unmittelbar nach Erhalt der Mitteilung vom Nachrichtencenter starten, dass die Migration Ihres Office 365-Mandanten begonnen hat (Phase 1).</i>| Wenn Sie HCW (17.0.5378.0 oder höher) vor Phase 5 deinstallieren und erneut ausführen, wird sichergestellt, dass Ihre lokale Konfiguration für das Senden und Empfangen von E-Mails mit Microsoft Cloud Deutschland-Benutzern und Benutzern bereit ist, die zu [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Deutschland migriert wurden. <p><li> Wählen Sie im HCW für das Listenfeld unter **Meine Office 365-Organisation,** die von gehostet wird, **Office 365 Deutschland aus.** | Wenn Sie diese Aufgabe nicht abschließen, bevor Phase 5 [Exchange Migration] beginnt, können unzuverl ndrs für E-Mails entstehen, die zwischen Ihrer lokalen Exchange-Bereitstellung und Office 365 geroutet werden.  
| (Post-Stage 5) – Erneutes Ausführen von HCW mithilfe von Office 365 Worldwide-Einstellungen <br><br> <i>Sie können diese Aktivität starten, nachdem Sie die Benachrichtigung des Nachrichtencenters erhalten haben, dass Ihre Exchange-Migration abgeschlossen ist (Phase 5).</i>| Durch das Deinstallieren und erneute Ausführen von HCW nach Phase 5 wird die lokale Konfiguration für die Hybridkonfiguration mit [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) nur Office 365 global zurückgesetzt. <p><li> Wählen Sie im Listenfeld unter **Meine Office 365-Organisation,** die von gehostet wird, Die Option Office **365 Weltweit aus.** | Wenn Sie diese Aufgabe nicht vor Phase 9 [Migration Abgeschlossen] abschließen, können unzuverl ndrs für E-Mails entstehen, die zwischen Ihrer lokalen Exchange-Bereitstellung und Office 365 geroutet werden.  
| Einrichten eines lokalen AuthServers, der auf den globalen Sicherheitstokendienst (STS) für die Authentifizierung verweist | Auf diese Weise wird sichergestellt, dass Authentifizierungsanforderungen für Exchange-Verfügbarkeitsanforderungen für Benutzer mit Migrationsstatus, die auf die lokale Hybridumgebung ausgerichtet sind, für den Zugriff auf den lokalen Dienst authentifiziert sind. Auf ähnliche Weise stellt dies die Authentifizierung von Anforderungen von lokalen zu Office 365-Globalen Dienstendpunkten sicher. | Nach Abschluss der Azure AD-Migration (Phase 2) muss der Administrator der lokalen Exchange-(Hybrid-)Topologie einen neuen Authentifizierungsdienstendpunkt für die Office 365-Globalen Dienste hinzufügen. Ersetzen Sie mit diesem Befehl von Exchange PowerShell `<TenantID>` durch die Mandanten-ID Ihrer Organisation im Azure-Portal unter Azure Active Directory.<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> Wenn Sie diese Aufgabe nicht ausführen, kann es sein, dass die Frei/Gebucht-Hybridanforderungen keine Informationen für Postfachbenutzer bereitstellen, die von Microsoft Cloud Deutschland zu Office 365-Diensten migriert wurden.  |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Gilt für**: Skype for Business Online-Kunden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 7

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Stellen Sie den Microsoft Teams-Desktopclient für Benutzer bereit, die auf Skype for Business in Deutschland zugreifen. | Durch die Migration werden Skype for Business-Benutzer für die Zusammenarbeit, für Anrufe und Chats auf Microsoft Teams umgestellt. Stellen Sie entweder den Microsoft Teams-Desktopclient bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Wenn keine Aktion ausgeführt wird, führt dies dazu, dass Microsoft Teams-Dienste für die Zusammenarbeit nicht verfügbar sind. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Änderungen an DNS-Zonen von Kunden für Skype for Business Online. |<ul><li>Es wird empfohlen, die Gültigkeitsdauer (Time-to-Live, TTL) für alle kundeneigenen DNS-Einträge auf 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die von Microsoft verwaltete Umstellung im Zusammenhang mit dieser DNS-Änderung jederzeit innerhalb des bereitgestellten 24-Stunden-Änderungsfensters erfolgen. </li><li>Eine Dienstunterbrechung in der Zukunft ist möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365-Diensten zu der migrierten Teams-Erfahrung umgeleitet. </li></ul>|
| Vorbereiten der Endbenutzer- und Administratorschulung und der Bereitschaft für den Umstieg auf Microsoft Teams. | Wenn Sie die Benutzerkommunikation und -bereitschaft planen wird der Umstieg von Skype auf Teams erfolgreich verlaufen. | <ul><li>Kunden müssen über die neuen Dienste und die Verwendung der Dienste informiert sein, sobald ihre Dienste auf die Office 365-Dienste umgestellt wurden. </li><li>Nachdem DNS-Änderungen sowohl für die Vanity-Domänen des Kunden als auch für die ursprüngliche Domäne vorgenommen wurden, melden sich die Benutzer bei Skype for Business an und sehen, dass sie nun zu Microsoft Teams migriert wurden. Dadurch wird auch der Desktopclient für Microsoft Teams im Hintergrund heruntergeladen. </li></ul>|
||||

## <a name="mobile-device-management"></a>Verwaltung mobiler Geräte

<!-- before phase 5 -->
**Gilt für:** Kunden, die eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 5

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Vorbereiten der Endbenutzer- und Administratorschulung für Benutzer für iOS und Android, die ihr Konto aus Microsoft Outlook entfernen und erneut hinzufügen. | Microsoft Outlook für iOS-und Android-Konten, die mit Postfächern in Microsoft Cloud Deutschland konfiguriert sind, muss möglicherweise entfernt und erneut zu Outlook hinzugefügt werden, um die neue Office 365-Dienstkonfiguration ordnungsgemäß zu synchronisieren. | Kunden von Microsoft Outlook für iOS und Android | Zuvor für Microsoft Cloud Deutschland konfigurierte Outlook-Postfächer können die neue Office 365-Dienste-Konfiguration nicht verwenden, was zu Fehlern und schlechter Leistung anderer Benutzererfahrungen führt. IT-Administratoren werden aufgefordert, Dokumentation bereitzustellen, die Benutzer proaktiv anweist, ihre Konten für iOS und Android aus Microsoft Outlook zu entfernen und erneut hinzuzufügen, wenn nach der Migration Probleme beim Anmelden oder beim Synchronisieren von E-Mails auftreten. |
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | MDM-Lösungen (Mobile Device Management) können als Ziel `outlook.de` -Endpunkte haben. Bei diesem Umstieg auf Office 365-Dienste sollten Clientprofile auf die Office 365-Dienst-URL `outlook.office365.com`aktualisiert werden. | Exchange Online und MDM-Kunden | Clients funktionieren möglicherweise weiterhin, solange auf den `outlook.de`-Endpunkt zugegriffen werden kann. Wenn nicht mehr auf Microsoft Cloud Deutschland-Endpunkte zugegriffen werden kann, treten Fehler auf. |
|||||

## <a name="line-of-business-apps"></a>Branchenspezifische Apps

**Gilt für:** Kunden, die branchenspezifische Apps mit Endpunkten verwenden, die von Microsoft Cloud Deutschland bereitgestellt wurden<br>
**Bei Anwendung**: Nach Abschluss der Phase 2 und bevor Ende der Phase 9

Wenn Sie Drittanbieterdienste oder branchenspezifische Apps verwenden, die mit Office 365 integriert sind, müssen Sie alle Abhängigkeiten auf Endpunkten, die von der Microsoft Cloud Deutschland-Instanz bereitgestellt werden, auflösen. Wenn z. B. Ihre Branchen-Apps mit `https://graph.microsoft.de/` in Verbindung stehen, müssen Sie den Endpunkt in `https://graph.microsoft.com/` ändern. Die Endpunkte des Microsoft Office 365-Globalen Diensts werden Ihrem Mandanten nach Phase 2 zur Verfügung stehen.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Dienste und Anwendungen von Drittanbietern, die in Office 365 integriert sind, können so programmiert werden, dass sie IP-Adressen und URLs von Microsoft Cloud Deutschland erwarten. | Erforderliche Aktion. Wenn keine Aktion ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gilt für:** Kunden, die Microsoft Dynamics 365 verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Für Dynamics 365-Sandkastenabonnements müssen Sie unbedingt die Produktionsumgebung der SQL-Instanz von Dynamics aus Ihrem Dynamics 365-Abonnement in Microsoft Cloud Deutschland herunterladen. Die neueste Produktionssicherung sollte vor der Sandkastenmigration im Sandkasten wiederhergestellt werden. | Die Migration von Dynamics 365 setzt voraus, dass Kunden sicherstellen, dass die Sandkastenumgebung mit der neuesten Produktionsdatenbank aktualisiert wird. | Das FastTrack-Team unterstützt Kunden bei der Durchführung von Trockentests, um das Versionsupgrade von 8.x auf 9.1.x zu überprüfen. |
||||

## <a name="power-bi"></a>Power BI

**Gilt für**: Kunden, die Power BI verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen von Objekten aus Power BI-Abonnements, die nicht von Power BI Microsoft Cloud Deutsch nach Office 365-Diensten migriert werden. | Für die Migration von Power BI-Diensten sind Kundenaktionen erforderlich, um bestimmte Artefakte wie Datasets und Dashboards zu löschen. | <ul><li>Administratoren müssen möglicherweise die folgenden Elemente aus ihrem Abonnement entfernen: </li><li>Echtzeit-Datasets (beispielsweise Streaming- oder Push-Datasets) </li><li>Lokale Power BI-Konfiguration des Datengateways und die Datenquelle </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Wenn Sie in der Microsoft Cloud Deutschland-Instanz dieselbe Azure Active Directory-Identitätspartition für Office 365 und Microsoft Azure verwenden, stellen Sie sicher, dass Sie sich auf die kundengesteuerte Migration von Microsoft Azure-Diensten vorbereiten.

> [!NOTE]
> Mit der Migration Ihrer Microsoft Azure-Dienste darf nicht begonnen werden, bevor Ihr Office 365-Mandant Migrationsphase 3 erreicht hat, und sie muss vor Abschluss von Migrationsphase 8 abgeschlossen sein.

Kunden, die Office 365- und Azure-Ressourcen (z. B. Netzwerk, Datenverarbeitung und Speicher) verwenden, führen die Migration von Ressourcen zur Office 365-Dienstinstanz aus. Diese Migration obliegt dem Kunden. Beiträge des Nachrichtencenters signalisieren den Anfang. Die Migration muss vor Abschluss der Azure AD-Organisation in der Office 365-Diensteumgebung abgeschlossen sein. Informationen zu Azure-Migrationen finden Sie im Azure-Migrationsplaybook [Übersicht über den Migrationsleitfaden für Azure Deutschland](https://docs.microsoft.com/azure/germany/germany-migration-main).

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Ermitteln Sie, welche Azure-Dienste verwendet werden, und bereiten Sie die künftige Migration von Deutschland zum Office 365-Dienstmandanten vor, indem Sie mit ihren Partnern zusammenarbeiten. Befolgen Sie die Schritte im [Playbook zur Azure-Migration](/azure/germany/germany-migration-main). |<ul><li>Die Migration von Azure-Ressourcen liegt in der Verantwortung des Kunden und erfordert manuellen Anstrengungen beim Ausführen der vorgeschriebenen Schritte. Für eine erfolgreiche Migration von Azure-Diensten ist es wichtig, dass Sie verstehen, welche Dienste in der Organisation verwendet werden. </li><li> Kunden von Office 365 Deutschland mit Azure-Abonnements unter derselben Identitätspartition (Organisation) müssen die von Microsoft vorgeschriebene Reihenfolge bei der Migration von Abonnement und Diensten einhalten.</li></ul>|<ul><li>Kunden können mehrere Azure-Abonnements haben, von denen jedes Abonnement Infrastruktur-, Dienst und Plattformkomponenten umfasst. </li><li> Administratoren sollten Abonnements und Beteiligte identifizieren, um sicherzustellen, dass im Rahmen dieses Migrationsereignisses eine schnelle Migration und Überprüfung möglich ist. </li><li>Wenn Sie die Migration dieser Abonnements und Azure-Komponenten nicht innerhalb der vorgegebenen Zeitachse erfolgreich abgeschlossen haben, wirkt sich dies auf den Abschluss des Office- und Azure AD-Umstiegs auf Office 365-Dienste aus. Dies kann zu Datenverlusten führen. </li><li> Eine Benachrichtigung über das Nachrichtencenter signalisiert den Punkt, an dem die von Kunden durchgeführte Migration beginnen kann. </li></ul>|
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
