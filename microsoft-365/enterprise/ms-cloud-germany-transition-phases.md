---
title: Aktionen und Auswirkungen der Migrationsphasen für die Migration von Microsoft Cloud Deutschland (generell)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
description: 'Zusammenfassung: Verstehen der Aktionen und Auswirkungen der Migrationsphasen für die Verschiebung von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.'
ms.openlocfilehash: 53a8c9470093db9d57d8dc18f4242d1a596c6efd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165633"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Aktionen und Auswirkungen der Migrationsphasen für die Migration von Microsoft Cloud Deutschland (generell)

Mandantenmigrationen von Microsoft Cloud Deutschland (MCD) in die Region "Deutschland" der globalen Office 365-Dienste von Microsoft werden als eine Reihe von Phasen und deren konfigurierte Aktionen für jede Arbeitsauslastung ausgeführt. Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren.

![Die neun Phasen der Migration in die neuen deutschen Rechenzentren](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Der Migrationsprozess wird in Abhängigkeit von der Gesamtgröße und Komplexität der Organisation über viele Wochen abgeschlossen. Während der Migration können Benutzer und Administratoren weiterhin die Dienste mit den in dieser Dokumentation detaillierten Änderungen nutzen. Die Grafik und Tabelle definieren Phasen und Schritte während der Migration.

|Schritt|Duration|Verantwortliche Partei|Beschreibung|
|:--------|:--------|:--------|:--------|
|Opt-In|Stunden|Kunde|Entscheiden Sie sich für Ihre Organisation für die Migration.|
|Pre-Work|Tage|Kunde|Führen Sie die erforderlichen Arbeiten aus, um Benutzer, Arbeitsstationen und Netzwerke für die Migration vorzubereiten.|
|Azure Active Directory (Azure AD)|1-2 Tage|Microsoft|Migrieren Sie Azure AD-Organisation zu weltweit.|
|Azure|Wochen|Kunde|Erstellen Sie neue weltweite Azure-Abonnements und Azure-Übergangsdienste.|
|Abonnement & Lizenzübergang|1-2 Tage|Microsoft|Erwerben Sie weltweite Abonnements, kündigen Sie Microsoft Cloud Deutschland-Abonnements und Übergangsbenutzerlizenzen.|
|SharePoint und OneDrive|15+ Tage|Microsoft|Migrieren sie SharePoint- und OneDrive for #A0 und sharepoint.de URLs.|
|Exchange Online|15+ Tage|Microsoft|Migrieren von Exchange Online-Inhalten und Übergang zu weltweiten URLs.|
|Sicherheit & Compliance|1-2 Tage|Microsoft|Übergangssicherheit & Compliancerichtlinien und -inhalten.|
|Skype for Business|1-2 Tage|Microsoft|Übergang von Skype for Business zu Microsoft Teams.|
|Power BI & Dynamics 365|15+ Tage|Microsoft|Migrieren von Power BI- und Dynamics 365-Inhalten.|
|Finalize Azure AD|1-2 Tage|Microsoft|Vollständige Mandantenübergabe für weltweit.|
|Clean-Up|1-2 Tage|Kunde|Bereinigen Von älteren Verbindungen mit Microsoft Cloud Deutschland, z. B. Active Directory Federation Services (AD FS) Relying Party Trust, Azure AD Connect und Office-Clientneustarts.|

Die Phasen und ihre Aktionen stellen sicher, dass wichtige Daten und Erfahrungen zu den globalen Office 365-Diensten migriert werden. Nachdem Ihr Mandant der Migrations-Warteschlange hinzugefügt wurde, wird jeder Workload als eine Reihe von Schritten abgeschlossen, die auf dem Backend-Dienst ausgeführt werden. Einige Workloads erfordern möglicherweise Aktionen des Administrators (oder Benutzers), oder die Migration kann die Verwendung der ausgeführten Phasen beeinflussen, die unter [Wie ist die Migration organisiert?](ms-cloud-germany-transition.md#how-is-the-migration-organized) diskutiert werden.

Die folgenden Abschnitte enthalten Aktionen und Auswirkungen für Workloads, während sie die verschiedenen Phasen der Migration durchlaufen. Überprüfen Sie die Tabellen und stellen Sie fest, welche Aktionen oder Auswirkungen auf Ihre Organisation zutreffen. Stellen Sie sicher, dass Sie vorbereitet sind, die Schritte in den jeweiligen Phasen wie erforderlich auszuführen. Wenn die erforderlichen Schritte nicht ausgeführt werden, kann dies zu einem Ausfall des Dienstes führen und der Abschluss der Migration zu den Office 365-Diensten kann sich verzögern.

## <a name="opt-in"></a>Opt-In

**Gilt für**: Alle Kunden mit einem Office 365-Mandanten, der in der Microsoft Cloud Deutschland (MCD) gehostet wird

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
| Wir können Office 365-Mandanten, die in der MCD gehostet werden, nicht ohne Zustimmung migrieren. | Microsoft erhält das Recht, auf zwei Arten zu migrieren, wodurch Microsoft den Übergang von Daten und Diensten zur Instanz der globalen Office 365-Dienste orchestrieren kann. <ol><li>Der Office 365-Mandantenadministrator entscheidet sich für die von Microsoft gesteuerte Migration. </li><li> Kunden verlängern abonnements in ihrem MCD Office 365-Mandanten nach dem 1. Mai 2020. Wir benachrichtigen diese Kunden jeden Monat über das Migrationsrecht, warten 30 Tage, um Kunden die Möglichkeit zu geben, abgesagt zu werden, und melden uns dann direkt an.</li></ol> | <ul><li>Der Mandant wird als für die Migration zulässig markiert, und das Admin Center zeigt eine Bestätigung an. </li><li>Die Bestätigung wird im Office 365-Mandanten-Nachrichtencenter bereitgestellt. Die Dienstkonfiguration wird von den Endpunkten der Microsoft Cloud Deutschland fortgesetzt. </li><li>Der Mandantenadministrator muss das Office 365 Message Center auf Updates für den Migrationsphasenstatus überwachen. </li></ul>|

## <a name="before-the-migration-starts"></a>Vor beginn der Migration

Stellen Sie sicher, dass Sie mit den Migrationsvorbereitungsschritten vertraut [sind, die für alle Kunden gelten.](ms-cloud-germany-transition-add-pre-work.md)

Falls Sie einen DNS-CNAME namens _msoid_ in einem oder mehreren #A0 festgelegt haben, die Sie besitzen, müssen Sie den CNAME bis spätestens Ende von Phase 8 entfernen. Sie können das CNAME _msoid_ jederzeit vor dem Ende von Phase 8 entfernen. Weitere Informationen [finden Sie in der Vorarbeit für DNS](ms-cloud-germany-transition-add-pre-work.md#dns).

Falls Sie einmaliges Anmelden für Office 365 und Azure in der Microsoft Cloud Deutschland-Instanz verwenden, müssen Sie Die Migration Ihres Azure-Abonnements entsprechend vorbereiten und planen. Stellen Sie sicher, dass Sie die [Vorarbeit für Microsoft Azure verstehen.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

## <a name="before-phase-2-starts"></a>Vor Beginn von Phase 2

Wenn Sie ADFS verwenden, stellen Sie sicher, dass Sie Ihre [ADFS-Konfiguration](ms-cloud-germany-transition-azure-ad.md) vor und nach dem Hinzufügen der Vertrauensstellung der vertrauenden Partei für den office 365 Global-Dienst sichern.

## <a name="subscription-transfer-phase-3"></a>Abonnementübertragung (Phase 3)

**Gilt für**: Alle Kunden mit einem Office 365-Mandanten, der in der Microsoft Cloud Deutschland (MCD) gehostet wird

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Abonnements werden übertragen und Lizenzen werden neu zugewiesen. | Entsprechende Office 365 Global Services-Abonnements werden in der Office 365 Global-Instanz für die übertragenen Microsoft Cloud Deutschland-Abonnements erworben. Benutzern mit zugewiesenen Microsoft Cloud Deutschland-Lizenzen werden Lizenzen in der Office 365 Global-Instanz zugewiesen. Alte Microsoft Cloud Deutschland-Abonnements werden nach Abschluss aus dem Office 365-Dienste-Mandanten entfernt.| <ul><li>Änderungen an vorhandenen Abonnements werden während dieser Phase blockiert (z. B. keine neuen Abonnementkäufe oder Änderungen an der Anzahl der Sitze).</li><li>Lizenzzuweisungsänderungen werden blockiert.</li><li>Das Microsoft Cloud Deutschland-Abonnement wird zu dem entsprechenden Office 365 Global Services-Abonnement migriert. Das Angebot für globale Office 365-Dienste dieses Abonnements wird von Microsoft definiert (auch als _Angebotszuordnung bezeichnet)._</li><li>Die Anzahl der Features (Dienstpläne), die von Office 365-Diensten angeboten werden, kann größer sein als im ursprünglichen Microsoft Cloud Deutschland-Angebot. Benutzerlizenzen in Office 365-Diensten werden äquivalent zu ähnlichen Microsoft Cloud Deutschland-Funktionen (Servicepläne) zugewiesen. Benutzerlizenzen aller Benutzer werden automatisch an diese neuen Features zugewiesen. Falls notwendig, muss der Administrator die Deaktivierung dieser Lizenzen durch eine explizite Aktion vornehmen. </li><li>Nach Abschluss der Abonnementmigration werden sowohl Office 365-Dienste als auch Microsoft Cloud Deutschland-Abonnements im Office 365 Admin Portal angezeigt, und der Status von Microsoft Cloud Deutschland-Abonnements ist als nicht mehr _verfügbar._ </li><li>Benutzern werden lizenzen zugewiesen, die an die neuen Office 365-Dienstabonnements gebunden sind. Alle Kundenprozesse, die Abhängigkeiten von Microsoft Cloud Deutschland-Abonnements oder SKU-GUIDs aufweisen, werden unterbrochen und müssen mit dem Office 365-Dienstangebot überarbeitet werden. </li><li>Neue Abonnements in den Office 365-Diensten werden mit dem neuen Ausdruck (monatlich/vierteljährlich/jährlich) erworben, und der Kunde erhält eine teilbasierte Rückerstattung für das nicht verwendete Guthaben des Microsoft Cloud Deutschland-Abonnements. </li><li>Partner Microsoft Cloud Deutschland-Mandanten werden nicht migriert. CSP-Kunden werden unter dem neuen Mandanten für Office 365-Dienste desselben Partners auf Office 365-Dienste migriert. Nach der Kundenmigration kann der Partner diesen Kunden nur noch über den Mandanten für Office 365-Dienste verwalten. </li><li>Zusätzliche Funktionen sind verfügbar (z. B. Microsoft Planner und Microsoft Flow), es sei denn, der Mandantenadministrator deaktiviert. Informationen zum Deaktivieren von Dienstplänen, die Benutzern zugewiesen sind, finden Sie unter [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (Phase 4)

**Gilt für**: Alle Kunden, die SharePoint Online verwenden

Falls Sie sharePoint 2013-Workflows weiterhin verwenden, beschränken Sie die Verwendung von SharePoint 2013-Workflows während der SharePoint Online-Migration.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
| SharePoint und OneDrive werden übergangen | SharePoint Online und OneDrive for Business werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365 Global Services migriert.<br><ul><li>Bestehende URLs von Microsoft Cloud Deutschland bleiben erhalten (Beispiel: `contoso.sharepoint.de`)</li><li>Vorhandene Websites werden beibehalten.</li><li>Clientseitige Authentifizierungstoken, die vom Sicherheitstokendienst (Security Token Service, STS) in der Microsoft Cloud Deutschland- oder Office 365 Global Services-Instanz ausgestellt wurden, sind während des Übergangs gültig.</li></ul>|<ul><li>Inhalte sind während der Migration für zwei kurze Zeiträume schreibgeschützt. Währen dieser Zeit wird ein Banner „Sie können Inhalte nicht bearbeiten“ in SharePoint angezeigt.</li><li>Der Suchindex wird nicht beibehalten und kann bis zu 10 Tage dauern, bis er neu erstellt wird.</li><li>SharePoint Online- und OneDrive for #A0 sind während der Migration für zwei kurze Zeiträume schreibgeschützt. Benutzer werden während dieser Zeit kurzfristig ein Banner „Sie können Inhalte nicht bearbeiten“ sehen.</li><li>Nach Abschluss der SharePoint #A0 sind die Suchergebnisse für SharePoint Online- und OneDrive for #A1 möglicherweise nicht verfügbar, während der Index neu erstellt wird. Während dieser Periode geben Suchanfragen möglicherweise unvollständige Resultate zurück. Features, die von Suchindizes abhängig sind, z. B. SharePoint Online News, können während der Neuindizierung beeinträchtigt werden.</li><li>SharePoint 2013-Workflows werden während der Migration unterbrochen und müssen nach der Migration erneut veröffentlicht werden.</li></ul>|
||||

Zusätzliche Überlegungen:

- Wenn Ihre Organisation immer noch SharePoint 2010-Workflows verwendet, werden diese nach 31. Dezember 2021 nicht mehr funktionieren. SharePoint 2013-Workflows bleiben unterstützt, obwohl sie ab 1. November 2020 für neue Mandaten standardmäßig ausgeschaltet werden. Wenn die Migration zu den SharePoint Onlinediensten abgeschlossen ist, empfehlen wir, dass Sie zu Power Automate oder anderen unterstützten Lösungen wechseln.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz noch nicht migriert wurde, müssen bei Version 16.0.20616.12000 (oder niedriger) von SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM bleiben. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz bereits migriert wurde, müssen SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM auf Version 16.0.20717.12000 oder höher aktualisieren. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.

> [!NOTE]
> Für den Fall, dass Sie eDiscovery verwenden, stellen Sie sicher, dass Sie die [eDiscovery-Migrationserfahrung kennen.](ms-cloud-germany-transition-add-experience.md#ediscovery-phase-4-to-the-end-of-phase-9)

## <a name="exchange-online-phase-5"></a>Exchange Online (Phase 5)

**Gilt für:** Alle Kunden, die Exchange Online verwenden

Wenn Sie Exchange Online hybrid verwenden: Exchange Online-Hybridadministratoren müssen den Assistenten für die Hybridkonfiguration  **(Hybrid Configuration Wizard, HCW)** im Rahmen dieses Übergangs mehrmals ausführen. Wenden Sie [die Exchange-Vorarbeit an,](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-configuration) **bevor der Migrationsschritt 5 beginnt.** Exchange Online-Hybridkunden müssen die neueste Version des Exchange Hybrid Configuration Wizard (HCW) im "Office 365 Deutschland"-Modus ausführen, um die lokale Konfiguration für die Migration zu globalen Office 365-Diensten vorzubereiten.

Nach Abschluss der Migrationsphase **9** (wenn der Message Center-Hinweis veröffentlicht wird) müssen Sie den HCW erneut mithilfe von Office 365 Worldwide-Einstellungen ausführen, um Ihre lokalen Systeme auf die globalen Office 365-Dienste zu verweisen.

Informationen zum Ändern von Benutzerfotos in Phase 5 finden Sie unter [Exchange Online Set-UserPhoto Phase 5.](ms-cloud-germany-transition-add-experience.md#exchange-online-set-userphoto-during-phase-5)

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
|Beenden oder Löschen von Onboarding- oder Offboardingpostfachbewegungen, d. h. verschieben Sie Postfächer nicht zwischen lokalem Exchange und Exchange Online.  | Dadurch wird sichergestellt, dass die Anforderungen zum Verschieben der Postfächer nicht fehlschlagen. | Wenn dies nicht der Fehler ist, kann dies zu einem Ausfall des Diensts oder der Office-Clients führen. |
| Exchange Online-Postfächer werden von Microsoft Cloud Deutschland zu Globalen Office 365-Diensten verschoben.| Die Exchange Online-Konfiguration fügt die neue lokale deutsche Region zur Übergangsorganisation hinzu. Die Region "Globale Office 365-Dienste" ist als Standard festgelegt, wodurch der interne Lastenausgleichsdienst Postfächer an die entsprechende Standardregion in Office 365-Diensten weiterverteilen kann. In diesem Übergang befinden sich Benutzer auf beiden Seiten (MCD- oder globale Dienste) in derselben Organisation und können beide URL-Endpunkte verwenden. |<ul><li>Stellen Sie Benutzer und Dienste von Ihren älteren MCD-URLs (outlook.office.de) zu neuen URLs für Office 365-Dienste ( `https://outlook.office365.com` ) um.</li><li>Benutzer können während der Migration weiterhin über ältere MCD-URLs auf den Dienst zugreifen, müssen jedoch nach Abschluss der Migration die Verwendung der älteren URLs beenden.</li><li>Benutzer sollten auf das weltweite Office-Portal für Office Online-Features (Kalender, E-Mail, Personen) umstiegen. Die Navigation zu Diensten, die noch nicht zu Office 365-Diensten migriert wurden, funktioniert erst, wenn sie migriert wurden. </li><li>Die Outlook Web App stellt während der Migration keine Öffentliche Ordner zur Verfügung. </li></ul>|
| Aktualisieren von benutzerdefinierten DNS-Einstellungen für die AutoErmittlung| Vom Kunden verwaltete DNS-Einstellungen für Die AutoErmittlung, die derzeit auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, um nach Abschluss der Exchange Online-Phase (Phase 5) auf den globalen Office 365-Endpunkt zu verweisen. <br> Vorhandene #A0 mit CNAME, die auf autodiscover-outlook.office.de müssen aktualisiert werden, um auf autodiscover.outlook.com. |  Verfügbarkeitsanforderungen und Dienstermittlungsaufrufe über AutoErmittlungspunkt direkt an die Office 365-Dienste. Kunden, die diese DNS-Updates nicht ausführen, treten beim Abschluss der Migration möglicherweise Probleme mit dem AutoErmittlungsdienst auf. |
||||

Zusätzliche Überlegungen:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` funktioniert erst nach der Mandantenübergabe in Phase 9. Links werden bis zu diesem Zeitpunkt Fehlermeldungen wie „Etwas ist fehlgeschlagen“ zurückgeben.

- Benutzer von Outlook Web App, die auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (z. B. ein Benutzer in der MCD-Umgebung, der auf ein freigegebenes Postfach in der globalen Umgebung zutritt), werden aufgefordert, sich ein zweites Mal zu authentifizieren. Der Benutzer muss sich zuerst authentifizieren und auf sein eigenes Postfach in `outlook.office.de` zugreifen und dann das freigegebene Postfach in `outlook.office365.com` öffnen. Sie müssen sich ein zweites Mal authentifizieren, wenn sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.

- Bei vorhandenen Microsoft Cloud Deutschland-Kunden oder solchen, die sich im Übergangsphase befindet, kann beim Hinzufügen eines freigegebenen Postfachs zu Outlook mithilfe von **Datei > Info > Konto** hinzufügen das Anzeigen von Kalenderberechtigungen fehlschlagen (der Outlook-Client versucht, die Rest-API zu `https://outlook.office.de/api/v2.0/Me/Calendars` verwenden). Kunden, die ein Konto zum Anzeigen von Kalenderberechtigungen hinzufügen möchten, können den Registrierungsschlüssel wie unter Benutzererfahrungsänderungen für die Freigabe eines Kalenders [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich ist. Dieser Registrierungsschlüssel kann unternehmensweit über eine Gruppenrichtlinie bereitgestellt werden.

- Die Verwendung der PowerShell-Cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, und **Test-MigrationsServerAvailability** kann während der Migrationsphase zu Fehlern führen (Fehler auf dem Proxy). Dies geschieht, wenn das Vermittlungspostfach auf weltweit migriert wurde, das Administrator-Postfach aber noch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandantensitzung das Vermittlungspostfach als Routing-Hinweis in **ConnectionUri**. Zum Beispiel:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Um mehr über die Unterschiede zwischen Organisationen bei der Migration und nach der Migration von Exchange Online-Ressourcen zu erfahren, lesen Sie die Informationen in [Kundenerfahrung während der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection / Security and Compliance (Phase 6)

**Gilt für:** Alle Kunden, die Exchange Online verwenden<br>

Back-End-Exchange Online Protection (EOP)-Features werden in die neue Region "Deutschland" kopiert.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Migration des Exchange Online-Routing und von historischen Nachrichtendetails. | Exchange Online ermöglicht das Weiterleiten von externen Hosts auf Office 365. Die externen MX-Datensätze werden umgestellt, um auf die EOP-Dienste weiterzuleiten. Die Mandanten-Konfiguration und historische Details werden migriert. |<ul><li>Von Microsoft verwaltete DNS-Einträge werden von Office 365 Deutschland EOP auf Office 365-Dienste aktualisiert.</li><li>Kunden sollten 30 Tage nach dem doppelten EOP-Schreiben für die EOP-Migration warten. Anderenfalls kann es zu einem Datenverlust kommen.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business Online (Phase 7)

**Gilt für:** Alle Kunden, die Skype for Business Online verwenden

Stellen Sie sicher, dass Sie mit den Vorarbeiten für Ihr [Skype for Business Online-Migrationsverfahren vertraut](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) sind.

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Wechseln von Skype for Business zu Microsoft Teams. | Vorhandene Skype for Business-Kunden werden zu Office 365 Global Services in Europa migriert und dann zu Microsoft Teams in der Region "Deutschland" von Office 365-Diensten umgeschaltet. |<ul><li>Benutzer können sich am Migrationsdatum nicht bei Skype for Business anmelden. Zehn Tage vor der Migration werden Sie im Admin Center über den Zeitpunkt der Migration informiert, und erneut, wenn die Migration beginnt.</li><li> Die Richtlinienkonfiguration wird migriert. </li><li>Benutzer werden zu Teams migriert und verfügen nach der Migration nicht mehr über Skype for Business. </li><li>Benutzer müssen den Teams-Desktopclient installiert haben. Die Installation erfolgt während der 10 Tage über Richtlinien in der Skype for Business-Infrastruktur. Wenn dies jedoch fehlschlägt, müssen Benutzer den Client manuell herunterladen oder eine Verbindung mit einem unterstützten Browser herstellen. </li><li>Kontakte und Besprechungen werden zu Teams migriert.</li><li>Benutzer können sich nicht bei Skype for Business anmelden, wenn der Zeitdienst zu Office 365-Diensten überwechselt wird, und erst, wenn die Kunden-DNS-Einträge abgeschlossen sind. </li><li>Kontakte und vorhandene Besprechungen funktionieren weiterhin als Skype for Business-Besprechungen. </li></ul>|
||||

Wenn Sie nach Abschluss der Migrationsphase 9 eine Verbindung mit Skype for Business Online mit PowerShell herstellen müssen, verwenden Sie den folgenden Code, um eine Verbindung herzustellen:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (Phase 8)

**Gilt für:** Alle Kunden, die Microsoft Dynamics 365 verwenden

Stellen Sie sicher, dass Sie mit den Vorarbeiten für Die Installation von [Microsoft Dynamics 365 vertraut](ms-cloud-germany-transition-add-pre-work.md#dynamics365) sind.

Kunden mit Dynamics 365 benötigen zusätzliches Engagement, um die Dynamics-Organisationen der Organisation unabhängig zu migrieren.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Microsoft Dynamics-Ressourcen | Kunden mit Microsoft Dynamics werden von Microsoft Engineering oder Microsoft FastTrack mit dem Übergang von Microsoft Dynamics 365 zur Instanz der globalen Office 365-Dienste beschäftigt.* |<ul><li>Nach der Migration überprüft der Administrator die Organisation. <</li><li>Der Administrator ändert Workflows bei Bedarf. </li><li>Der Administrator entfernt den AdminOnly-Modus entsprechend.</li><li>Der Administrator ändert den Organisationstyp von _Sandbox_ aus, wenn dies der Richtige ist.</li><li>Benachrichtigen Sie Endbenutzer über die neue URL, um auf die Instanz (Organisation) zu zugreifen.</li><li>Aktualisieren Sie alle eingehenden Verbindungen mit der neuen Endpunkt-URL. </li><li>Der Dynamics-Dienst ist während des Übergangs für Benutzer nicht verfügbar. </li><li>Benutzer müssen den Organisationszustand und die Features nach der Migration der einzelnen Organisationen überprüfen.</li></ul>|
||||

\* (i) Kunden mit Microsoft Dynamics 365 müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab.

## <a name="power-bi-phase-8"></a>Power BI (Phase 8)

**Gilt für:** Alle Kunden, die Microsoft Power BI (PBI) verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Migration von Power BI-Ressourcen | Kunden mit Microsoft Power BI (PBI) werden von Microsoft Engineering oder Microsoft FastTrack engagiert, nachdem sie manuell ein vorhandenes PBI-Migrationstool ausgelöst haben, um Power BI zur Instanz der globalen Office 365-Dienste zu überwechseln.\*\* |<ul><li>Die folgenden Power BI-Elemente _werden_ nicht umgewechselt, und sie müssen neu erstellt werden: <</li><li>Echtzeit-Datasets (z. B. Streaming- oder Push-Datasets). </li><li>Konfiguration und Datenquelle des lokalen Power BI-Datengateways. </li><li>Berichte, die auf den Echtzeit-Datasets aufgebaut sind, stehen nach der Migration nicht mehr zur Verfügung und müssen neu erstellt werden. </li><li>Power BI-Dienste stehen Benutzern während des Übergangs nicht zur Verfügung. Der Dienst sollte höchstens 24 Stunden lang nicht verfügbar sein.</li><li>Benutzer müssen Datenquellen und ihre lokalen Datengateways nach der Migration mit dem Power BI-Dienst neu konfigurieren.  Solange dies nicht der Fall ist, können Benutzer diese Datenquellen nicht verwenden, um planmäßige Aktualisierungen und/oder direkte Abfragen für diese Datenquellen auszuführen. </li><li>Kapazitäten und Premiumarbeitsräume können nicht migriert werden. Kunden müssen alle Kapazitäten vor der Migration löschen und nach der Migration neu erstellen. Verschieben Sie Arbeitsbereiche ggf. zurück zu Kapazitäten.</li></ul>  |
||||

\*\* (i) Kunden mit Microsoft Power BI müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab.

## <a name="office-apps"></a>Office-Apps

**Gilt für:** Alle Kunden, die Office-Desktopanwendungen verwenden (Word, Excel, PowerPoint, Outlook, ...)

Office 365-Mandanten, die in die Region "Deutschland" überwechseln, müssen alle Benutzer schließen, sich von Office 365 abmelden und sich für alle Office-Desktopanwendungen (Word, Excel, PowerPoint, Outlook usw.) und oneDrive for #A0 anmelden, nachdem die Mandantenmigration Phase 9 erreicht hat. Wenn Sie sich ab- und anmelden, können die Office-Dienste neue Authentifizierungstoken vom globalen Azure AD-Dienst abrufen.

Stellen Sie sicher, dass Sie die [Vorarbeiten für mobile Geräte abgeschlossen](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) haben.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Clients, Office Online während der Office-Client-Übernahmemigration, Azure AD finalisiert den Mandantenbereich so, dass er auf die Office 365-Dienste verweist. | Mit dieser Konfigurationsänderung können Office-Clients aktualisiert und auf die Office 365-Dienstendpunkte verweisen. | <ul><li>Benachrichtigen Sie Benutzer, _alle_ Office-Apps zu schließen, und melden Sie sich dann wieder an (oder erzwingen Sie, dass Clients neu gestartet werden und benutzer sich anmelden), damit Office-Clients die Änderung auf sich nehmen können. </li><li>Benachrichtigen Sie Benutzer und  Mitarbeiter des Helpdesks, dass Benutzern möglicherweise ein Office-Banner angezeigt wird, das sie zum Reaktivieren von Office-Apps innerhalb von 72 Stunden nach der Umstellung anfordert. </li><li>Alle Office-Anwendungen auf persönlichen Computern müssen geschlossen werden, und Benutzer müssen sich abmelden und sich dann erneut anmelden. Melden Sie sich in der gelben Aktivierungsleiste an, um die Office 365-Dienste zu reaktivieren.</li><li>Für freigegebene Computer sind Aktionen erforderlich, die mit persönlichen Computern vergleichbar sind, und es ist kein spezielles Verfahren erforderlich. </li><li>Auf mobilen Geräten müssen Sich Benutzer von Apps abmelden, diese schließen und sich dann erneut anmelden.</li></ul>|
||||

## <a name="line-of-business-apps"></a>Branchenspezifische Apps

Stellen Sie sicher, dass Sie die Vorarbeit für Business-Apps abgeschlossen haben, falls Sie über [Business-Of-Business-Apps](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) verfügen.

## <a name="office-services"></a>Office-Dienste

Der zuletzt verwendete Dienst (MRU) in Office ist eine Umstellung von Microsoft Cloud Deutschland auf Office 365 Global Services, keine Migration. Nur MRU-Links von der Office 365 Global Services-Seite sind nach der Migration aus dem Office.com sichtbar. MRU-Links aus der Microsoft Cloud Deutschland werden in Office 365 Global Services nicht als MRU-Links angezeigt. In Globalen Office 365-Diensten ist der Zugriff auf MRU-Links erst möglich, nachdem die Mandantenmigration Phase 9 erreicht hat.

## <a name="post-migration"></a>Nach der Migration

Lesen Sie den Artikel zu Den [Aktivitäten nach](ms-cloud-germany-transition-add-experience.md#post-migration) der Migration, und führen Sie sie entsprechend aus.

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
