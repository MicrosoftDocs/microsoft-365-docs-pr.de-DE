---
title: Prä-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.openlocfilehash: 5eefa56b96eb616c694b26c374b235ccd95c3ee9
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796018"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Prä-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland

Über diese Links gelangen Sie zu den Prä-Migrationsschritten, die für Ihre Organisation relevant sind:

Wenn Sie

- **Office 365 in Microsoft Cloud Deutschland**: führen Sie [diese Schritte](#general-tenant-migration-considerations) aus.
- **Benutzerdefinierte Domänen**: führen Sie [diesen Schritt](#dns-entries-for-custom-domains) aus.
- **Office-Apps**: erwägen Sie [diesen Schritt](#office-apps).
- **SharePoint Online**: führen Sie [diesen Schritt](#sharepoint-online) aus.
- **Exchange Online** oder **Exchange Hybrid**: führen Sie [diesen Schritt](#exchange-online) aus.
- **Skype for Business Online**: führen Sie [diesen Schritt](#skype-for-business-online) aus.
- **Dynamics 365**: führen Sie [diesen Schritt](#dynamics365) aus.
- **Power BI**: führen Sie [diesen Schritt](#power-bi) aus.
- **Active Directory Federation Services** für Azure AD Connect: führen Sie [diese Schritte](#active-directory-federation-services-ad-fs) aus.
- **Drittanbieterdienste** oder **Line-of-Business (LOB)-Apps**, die mit Office 365 integriert sind: führen Sie [diesen Schritt](#line-of-business-apps) aus.
- Mit einer MDM-Lösung eines Drittanbieters: führen Sie [diesen Schritt](#mobile-device-management) aus.
- **Azure-Dienste** mit Ihrem Office 365-Abonnement: führen Sie [diesen Schritt](#microsoft-azure) aus.

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

## <a name="dns-entries-for-custom-domains"></a>DNS-Einträge für benutzerdefinierte Domänen

<!-- before phase 9 -->

**Gilt für**: Kunden, die ein benutzerdefiniertes _msoid_-CNAME in ihrer eigenen DNS-Domäne festlegen oder eine Domäne für Exchange Online verwenden

Wenn konfiguriert, wirkt sich das _msoid_ CNAME nur auf Kunden aus, die den Office-Desktopclient verwenden (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Falls Sie ein DNS CNAME namens _msoid_ in einem oder vielen DNS-Namespaces, die Sie besitzen, festgelegt haben, müssen Sie das CNAME mindestens bis zum Ende der Phase 8 entfernen. Sie können das CNAME _msoid_ jederzeit vor dem Ende der Phase 8 entfernen.

Um zu bestätigen, dass Sie ein CNAME in ihrem DNS-Namespace festgelegt haben, folgen Sie den Schritten unten und ersetzen Sie _contoso.com_ mit Ihrem eigenen Domänennamen:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Wenn die Befehlszeile einen DNS-Datensatz zurückgibt, entfernen Sie das _msoid_ CNAME von Ihrer Domäne.

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Domäne für Exchange Online verwenden, müssen Sie Zugriff auf Ihren DNS-Hostinganbieter haben. Bitte stellen Sie sicher, dass Sie auf Ihre DNS-Einstellungen zugreifen und diese bearbeiten können, Sie werden die DNS-Datensätze während der Migration anpassen.

## <a name="office-apps"></a>Office-Apps

**Gilt für**: Kunden, die Office-Apps verwenden, speziell auf Windows-Clients <br>
**Wann angewendet**: Jederzeit vor Beginn der Phase 9

Die Umstellung von Office 365-Mandanten auf die Region „Deutschland“ erfordert, dass sich alle Benutzer von Office 365 abmelden, alle Anwendungen schließen, und sich für alle Office-Desktopanwendungen (Word, Excel, PowerPoint, Outlook usw.) und den OneDrive for Business-Client erneut anmelden, nachdem die Mandantenmigration Phase 9 erreicht hat. Das Ab- und Anmelden erlaubt den Office-Diensten das Abrufen neuer Authentifizierungstokens vom globalen Azure AD-Dienst.

Dies ist für alle Clients erforderlich. Um eine reibungslose Migrationserfahrung zu gewährleisten, wird dringend empfohlen, alle betroffenen Benutzer im Voraus und frühzeitig über diese bevorstehende Aktivität zu informieren und anzuweisen.

Kunden mit verwalteten Windows-Clients können Windows-Computer mit dem [Office Client Cutover Tool (OCCT)](https://github.com/microsoft/OCCT) vorbereiten. Das OCCT ist so konzipiert, dass es periodisch auf Windows-Clients läuft, bis der Mandant die Phase 9 der Migration erreicht hat. Wenn die Phase 9 erreicht ist, wird das OCCT automatisch ohne Benutzer-Interaktion alle notwendigen Änderungen auf dem Computer durchführen.

Das OCCT kann jederzeit vor der Phase 9 auf Windows-Clients bereitgestellt werden. Wenn das OCCT die Migrationserfahrung unterstützen soll, empfehlen wir die Bereitstellung so früh wie möglich zu beginnen, um die größtmögliche Zahl von Clients auszurüsten.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory-Verbunddienste (AD FS)

**Gilt für**: Kunden, die AD FS lokal für die Authentifizierung von Benutzern verwenden, die eine Verbindung mit Microsoft Office 365 herstellen<br>
**Wann angewendet**: Jederzeit vor Beginn der Phase 2

Lesen und Anwenden der [ADFS-Migrationsschritte](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**Gilt für**: Kunden, die SharePoint 2013 lokal verwenden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 4

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Begrenzen Sie SharePoint 2013-Workflows, die Sie während der SharePoint Online-Migration verwenden. | Reduzieren Sie SharePoint 2013-Workflows, und schließen Sie In-Flight-Workflows vor Übergängen ab. | Wenn keine Aktion ausgeführt wird, kann dies zu Verwirrung bei Benutzern und zu Helpdesk-Anrufen führen. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Gilt für:** Exchange Online-Kunden<br>
**Bei Anwendung**: Jederzeit vor Ende der Phase 9

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Benachrichtigen Sie externe Partner über den bevorstehenden Umstieg zu Office 365-Diensten. |  Kunden müssen ihre Partner benachrichtigen, für die sie die Kalenderfreigabe und die Adressraumverfügbarkeitskonfiguration aktiviert haben (ermöglichen des Teilens von Frei/Gebucht-Informationen mit Office 365). Die Verfügbarkeitskonfiguration muss umgestellt werden, damit die [weltweiten Office 365-Endpunkte](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) verwendet werden, wenn die Exchange Online-Migration abgeschlossen wird. | Ohne Umstellung kann es in einer späteren Phase der Kundenmigration zu einem Dienst- oder Clientausfall kommen. |
| Benachrichtigen Sie Benutzer über erforderliche Änderungen am IMAP4-/POP3/SMTP-Client. | Benutzer, die Geräteverbindungen mit Microsoft Cloud Deutschland-Endpunkten für Clientprotokolle wie IMAP4, POP3 und SMTP haben, müssen ihre Clientgeräte manuell aktualisieren, um zu den [Exchange Online-Servernamen](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes) zu wechseln. | Teilen Sie den Benutzern dieser Protokolle vorab diese Abhängigkeit mit, und stellen Sie sicher, dass sie während dieser Migration entweder zu Outlook Mobile oder Outlook im Web wechseln. Fehler beim Aktualisieren von Clientendpunkten führen zu Clientverbindungsfehlern mit Microsoft Cloud Deutschland, wenn Benutzerpostfächer migriert werden. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online-Hybridkunden

**Gilt für:** Alle Kunden, die eine aktive Exchange-Hybridkonfiguration mit lokalen Exchange-Servern verwenden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 5

Enterprise-Kunden mit einer Hybridbereitstellung von Exchange Online und einem lokalen Exchange Server führen den Hybridkonfigurationsassistenten ( Hybrid Configuration Wizard, HCW) und AAD Connect aus, um das Hybridsetup zu verwalten und einzurichten. Exchange Online Hybrid-Administratoren  **müssen den Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW)** im Rahmen dieser Überführung mehrmals ausführen. Beim Umstieg von Microsoft Cloud Deutschland auf die Region „Office 365 Deutschland“ muss der Administrator den neuesten Build des Hybridkonfigurationsassistenten im Modus „Office 365 Deutschland“ erneut ausführen, bevor die Exchange-Migration (Phase 5) beginnt. Führen Sie nach Abschluss der Phase 5 den Hybridkonfigurationsassistenten erneut im Modus „Office 365 weltweit“ aus, um die lokale Bereitstellung mit den Regionseinstellungen „Office 365 Deutschland“ fertigzustellen. Die HCW-Ausführung darf nicht während der Phase 5 laufen, es ist wichtig, dass die Ausführung des HCW erst nach Beendigung der Phase 5 erfolgt.
Verzeichnisattribute werden zwischen Office 365 und Azure AD synchronisiert, mit der lokalen Bereitstellung über AAD Connect. 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Erneutes Ausführen des HCW mithilfe der Einstellungen für „Office 365 Deutschland“ <br><br> <i>Sie können diese Aktivität unmittelbar nach Erhalt der Benachrichtigung des Nachrichtencenters starten, dass die Migration Ihres Office 365-Mandanten begonnen hat (Phase 1).</i>| Durch Deinstallieren und erneutes Ausführen des HCW (Version 17.0.5378.0 oder höher) aus [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) vor der Phase 5 wird sichergestellt, dass Ihre lokale Konfiguration für das Senden und Empfangen von E-Mails sowohl für Benutzer von Microsoft Cloud Deutschland als auch für Benutzer, die zur Region „Office 365 Deutschland” migriert sind, vorbereitet ist. <p><li> Wählen Sie im HCW im untenstehenden Listenfeld **Meine Office 365-Organisation wird von gehostet von** die Option **Office 365 Deutschland** aus. | Wenn Sie diese Aufgabe nicht vor Beginn der Phase 5 [Exchange-Migration] abschließen, können Unzustellbarkeitsberichte (NDRs) für E-Mails auftreten, die zwischen Ihrer lokalen Exchange-Bereitstellung und Office 365 geroutet werden.  
| Bewahren der Einstellungen für freigegebene Postfächer | Einige Hybrid-Kunden haben Cloud-Benutzerpostfächer mithilfe von Exchange Online-Befehlen in „freigegebene“ Postfächer konvertiert. Diese Cloud-Postfachkonfiguration wird in das Postfach und das lokale Exchange Online-Verzeichnis geschrieben, jedoch nicht über AAD Connect zurück zum Active Directory des Kunden synchronisiert. Das Ergebnis ist eine Diskrepanz zwischen der Active Directory-Darstellung der Postfachwerte „RemoteRecipientType“ und „RemoteDisplayType“ und derjenigen in Exchange Online, die das Postfach als freigegeben definiert. <br><br> Der Kunde ist dafür verantwortlich, dass alle freigegebenen Postfächer mit `New-RemoteMailbox -Shared`, `Enable-RemoteMailbox -Shared` oder `Set-RemoteMailbox -Shared` ordnungsgemäß bereitgestellt werden.  In dieser Referenz erfahren Sie, wie Sie [das Postfach eines Benutzers in einer hybriden Umgebung konvertieren](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide) können.| Wenn Sie diese Aufgabe nicht vor Beginn der Phase 5 [Exchange Online-Migration] abschließen, können Unzustellbarkeitsberichte (NDRs) für freigegebene Postfächer auftreten, die wieder in nicht lizenzierte Postfächer umgewandelt werden, und es kann zum Verlust des gemeinsamen Zugriffs für die betroffenen Postfächer kommen. Der Artikel [Freigegebene Postfächer werden unerwartet in Benutzerpostfächer umgewandelt, nachdem die Verzeichnissynchronisierung in einer Exchange-Hybridbereitstellung ausgeführt wurde](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) skizziert die Auswirkungen, wenn dieses Problem nicht vor Abschluss der Exchange Online-Migration behoben wird.  
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Gilt für**: Skype for Business Online-Kunden<br>
**Bei Anwendung**: Jederzeit vor Beginn der Phase 7

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Stellen Sie den Microsoft Teams-Desktopclient für Benutzer bereit, die auf Skype for Business in Deutschland zugreifen. | Durch die Migration werden Skype for Business-Benutzer für die Zusammenarbeit, für Anrufe und Chats auf Microsoft Teams umgestellt. Stellen Sie entweder den Microsoft Teams-Desktopclient bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Wenn keine Aktion ausgeführt wird, führt dies dazu, dass Microsoft Teams-Dienste für die Zusammenarbeit nicht verfügbar sind. |
| Überprüfen und Vorbereiten von migrationsbezogenen DNS-Änderungen. | Änderungen an DNS-Zonen von Kunden für Skype for Business Online. |<ul><li>Es wird empfohlen, die Gültigkeitsdauer (Time-to-Live, TTL) für alle kundeneigenen DNS-Einträge auf 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die von Microsoft verwaltete Umstellung im Zusammenhang mit dieser DNS-Änderung jederzeit innerhalb des bereitgestellten 24-Stunden-Änderungsfensters erfolgen. </li><li>Eine Dienstunterbrechung ist in der Zukunft möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365-Diensten zu der migrierten Teams-Erfahrung umgeleitet. </li></ul>|
| Vorbereiten der Endbenutzer- und Administratorschulung und der Bereitschaft für den Umstieg auf Microsoft Teams. | Wenn Sie die Benutzerkommunikation und -bereitschaft planen wird der Umstieg von Skype auf Teams erfolgreich verlaufen. | <ul><li>Kunden müssen über die neuen Dienste und die Verwendung der Dienste informiert sein, sobald ihre Dienste auf die Office 365-Dienste umgestellt wurden. </li><li>Nachdem DNS-Änderungen sowohl für die Vanity-Domänen des Kunden als auch für die ursprüngliche Domäne vorgenommen wurden, würden sich die Benutzer bei Skype for Business anmelden und sehen, dass sie nun zu Microsoft Teams migriert wurden. Dies würde auch den Desktopclient für Teams im Hintergrund herunterladen. </li></ul>|
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
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Dienste und Anwendungen von Drittanbietern, die in Office 365 integriert sind, können so programmiert werden, dass sie IP-Adressen und URLs von Microsoft Cloud Deutschland erwarten. | Erforderliche Aktion. Wenn die Aktion nicht ausgeführt wird, kann dies zu Fehlern beim Dienst oder bei der Clientsoftware führen. |
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
> Die Migration Ihrer Microsoft Azure Dienste beginnt möglicherweise nicht, bevor Ihr Office 365 Mandant die Migrationsphase 9 erreicht hat, und muss abgeschlossen werden, bevor die Migrationsphase 10 gestartet wurde.

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

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
