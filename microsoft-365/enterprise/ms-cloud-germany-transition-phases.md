---
title: Aktionen während der Migrationsphasen und Auswirkungen für die Migration von Microsoft Cloud Deutschland
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
ms.openlocfilehash: 8e3e6fb228445823481b52d27e5a7b6c623349e2
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995021"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>Aktionen während der Migrationsphasen und Auswirkungen für die Migration von Microsoft Cloud Deutschland

Mandanten-Migrationen von Microsoft Cloud Deutschland (MCD) in die Region "Deutschland" der Office 365 Global-Dienste von Microsoft erfolgen in mehreren Phasen mit entsprechenden konfigurierten Aktionen für jeden Workload. Diese Abbildung zeigt die zehn Phasen der Migration in die neuen deutschen Rechenzentren.

![Die zehn Phasen der Migration in die neuen deutschen Rechenzentren](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Der Migrationsprozess dauert mehrere Wochen, abhängig von der Gesamtgröße und Komplexität der Organisation. Während der Migration können Benutzer und Administratoren die Dienste weiterhin nutzen, jedoch mit wichtigen Änderungen, die in dieser Dokumentation beschrieben werden. In der Grafik und der Tabelle sind die Phasen und Schritte während der Migration dargestellt.

|Schritt|Dauer|Verantwortliche Partei|Beschreibung|
|:--------|:--------|:--------|:--------|
|Anmelden|Stunden|Kunde|Anmelden Ihrer Organisation für die Migration.|
|Vorarbeit|Tage|Kunde|Durchführen der erforderlichen Maßnahmen, um Benutzer, Arbeitsstationen und das Netzwerk für die Migration vorzubereiten.|
|Azure Active Directory (Azure AD)|1-2 Tage|Microsoft|Migrieren der Azure AD-Organisation zu weltweit.|
|Azure|Wochen|Kunde|Erstellen neuer weltweiter Azure-Abonnements und des Überführen von Azure-Diensten.|
|Abonnement- und Lizenzüberführung|1-2 Tage|Microsoft|Erwerben weltweiter Abonnements, kündigen von Microsoft Cloud Deutschland-Abonnements und Überführen von Benutzerlizenzen.|
|SharePoint und OneDrive|Mehr als 15 Tage|Microsoft|Migrieren von SharePoint- und OneDrive for Business-Inhalten, Beibehalten von sharepoint.de-URLs.|
|Exchange Online|Mehr als 15 Tage|Microsoft|Migrieren von Exchange Online-Inhalten und Umstieg auf weltweite URLs.|
|Sicherheit und Compliance|1-2 Tage|Microsoft|Überführen von Sicherheits- und Compliancerichtlinien und -inhalten.|
|Skype for Business|1-2 Tage|Microsoft|Wechsel von Skype for Business zu Microsoft Teams.|
|Power BI und Dynamics 365|Mehr als 15 Tage|Microsoft|Migrieren von Power BI- und Dynamics 365-Inhalten.|
|Azure AD finalisieren|1-2 Tage|Microsoft|Endgültige Mandantenumstellung auf weltweit.|
|Bereinigung|1-2 Tage|Kunde|Bereinigen älterer Verbindungen mit Microsoft Cloud Deutschland, z. B. Active Directory-Verbunddienste (AD FS) – Vertrauensstellung der vertrauenden Seite, Azure AD Connect und Office-Client-Neustarts.|
|Deaktivieren der Endpunkte|30 Tage|Microsoft|30 Tage nach Abschluss von Azure AD wird der Azure AD-Dienst „Microsoft Cloud Deutschland“ den Endpunktzugriff für die umgestiegene Organisation beenden. Endpunktanforderungen wie Authentifizierung werden ab diesem Zeitpunkt für den Dienst „Microsoft Cloud Deutschland“ fehlschlagen. |


Die Phasen und die entsprechenden Aktionen stellen sicher, dass kritische Daten und Lösungen zu den Office 365 Global-Diensten migriert werden. Nachdem Ihr Mandant der Migrations-Warteschlange hinzugefügt wurde, wird jeder Workload als eine Reihe von Schritten abgeschlossen, die auf dem Backend-Dienst ausgeführt werden. Einige Workloads erfordern möglicherweise Aktionen des Administrators (oder Benutzers), oder die Migration kann die Verwendung der ausgeführten Phasen beeinflussen, die unter [Wie ist die Migration organisiert?](ms-cloud-germany-transition.md#how-is-the-migration-organized) diskutiert werden.

Die folgenden Abschnitte enthalten Aktionen und Auswirkungen für Workloads, während sie die verschiedenen Phasen der Migration durchlaufen. Überprüfen Sie die Tabellen und stellen Sie fest, welche Aktionen oder Auswirkungen auf Ihre Organisation zutreffen. Stellen Sie sicher, dass Sie vorbereitet sind, die Schritte in den jeweiligen Phasen wie erforderlich auszuführen. Wenn die erforderlichen Schritte nicht ausgeführt werden, kann dies zu einem Ausfall des Dienstes führen und der Abschluss der Migration zu den Office 365-Diensten kann sich verzögern.

## <a name="phase-opt-in"></a>Phase: Anmeldung

**Gilt für**: Alle Kunden mit einem in der Microsoft Cloud Deutschland (MCD) gehosteten Office 365-Mandanten. Microsoft kann in der MCD gehostete Office 365-Mandanten nicht ohne Zustimmung migrieren.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
|**Aufgabe des Kunden**: der Migration zustimmen| Der Kunde erteilt die Zustimmung für die Migration, sodass Microsoft die Berechtigung für die Migration erhält sowie zum Organisieren des Wechsels von Daten und Diensten zur globalen Office 365-Dienste-Instanz. Es gibt zwei Möglichkeiten: <ol><li>Der Office 365-Mandantenadministrator wählt die von Microsoft gesteuerte Migration. </li><li> Kunden haben sämtliche Abonnements in ihrem MCD Office 365-Mandanten nach dem 1. Mai 2020 erneuert. Microsoft wird diese Kunden jeden Monat über das Migrationsrecht informieren, 30 Tage warten, um ihnen die Möglichkeit zur Stornierung zu geben, und dann direkt die Anmeldung vornehmen.</li></ol> | <ul><li>Der Mandant ist als mit der Migration einverstanden gekennzeichnet, und im Admin Center wird eine Bestätigung angezeigt. </li><li>Die Zustimmung wird im Nachrichtencenter des Office 365-Mandanten gepostet. Die Dienstkonfiguration wird von Microsoft Cloud Deutschland-Endpunkten fortgesetzt. </li><li> </li></ul>
|**Mandantenadministrator-**: Nach Nachrichten Ausschau halten|Der Mandantenadministrator muss ab nun das Office 365-Nachrichtencenter auf Updates zum Status der Migrationsphase überwachen.|Der Kunde kann erforderliche Aufgaben rechtzeitig ausführen.
||||

## <a name="phase-1-before-the-migration-starts"></a>Phase 1: Befor die Migration beginnt

Stellen Sie sicher, dass Sie sich mit den [Migrationsvorbereitungsschritten, die für alle Kunden gelten](ms-cloud-germany-transition-add-pre-work.md) vertraut gemacht haben.

Falls Sie ein DNS CNAME namens _msoid_ in einem oder vielen DNS-Namespaces, die Sie besitzen, festgelegt haben, müssen Sie das CNAME mindestens bis zum Ende der Phase 8 entfernen. Sie können das CNAME _msoid_ jederzeit vor dem Ende der Phase 8 entfernen. Weitere Information finden Sie unter [Vorbereitung für DNS](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains).

Falls Sie ein einmaliges Anmelden für Office 365 und Azure in der Microsoft Cloud Deutschland-Instanz verwenden, müssen Sie die Migration Ihres Azure-Abonnements entsprechend vorbereiten und planen. Stellen Sie sicher, dass Sie die [Vorbereitung für Microsoft Azure](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure) verstehen.

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD Connect mit AD FS-Verbund
**Gilt für**: Kunden mit AD FS-Verbund

**Wird angewendet**: Vor Beginn von Phase 2

Wenn Sie Active Directory-Verbunddienste (AD FS) verwenden, sorgen Sie für die [Sicherung Ihrer ADFS-Konfiguration vor und nach dem Hinzufügen der Vertrauensstellung der vertrauenden Seite](ms-cloud-germany-transition-azure-ad.md) für den globalen Office 365-Dienst **vor** Beginn von Phase 2.

## <a name="phase-2-azure-ad-migration"></a>Phase 2: Azure AD-Migration
In dieser Phase wird Azure Active Directory in die neue Rechenzentrumsregion migriert und wird aktiv. Die alten Azure AD-Endpunkte sind weiterhin verfügbar.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online Hybrid – lokales Anpassen von AuthServer
**Gilt für:** Alle Kunden, die eine aktive Exchange-Hybridkonfiguration mit lokalen Exchange-Servern verwenden

**Wann angewendet**: Nach dem Ende der Phase 2

Der lokale AuthServer muss auf den globalen Sicherheitstokendienst (Security Token Service, STS) für die Authentifizierung zeigen, nachdem die Azure AD-Migration beendet ist.
Auf diese Weise wird sichergestellt, dass Authentifizierungsanforderungen für Exchange-Verfügbarkeitsanforderungen für Benutzer mit Migrationsstatus, die auf die lokale Hybridumgebung ausgerichtet sind, für den Zugriff auf den lokalen Dienst authentifiziert sind. Auf ähnliche Weise stellt dies die Authentifizierung von Anforderungen von lokalen zu Office 365-Globalen Dienstendpunkten sicher. Nach Abschluss der Azure AD-Migration (Phase 2) muss der Administrator der lokalen Exchange-(Hybrid-)Topologie einen neuen Authentifizierungsdienstendpunkt für die Office 365-Globalen Dienste hinzufügen. Ersetzen Sie mit diesem Befehl von Exchange PowerShell `<TenantID>` durch die Mandanten-ID Ihrer Organisation im Azure-Portal unter Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

Wenn Sie diese Aufgabe nicht ausführen, kann es sein, dass die Frei/Gebucht-Hybridanforderungen keine Informationen für Postfachbenutzer bereitstellen, die von Microsoft Cloud Deutschland zu Office 365-Diensten migriert wurden.

## <a name="phase-3-subscription-transfer"></a>Phase 3: Abonnementübertragung

**Gilt für**: Alle Kunden mit einem in Microsoft Cloud Deutschland (MCD) gehosteten Office 365-Mandanten

MCD-Partnermandanten werden nicht migriert. CSP-Kunden werden unter dem neuen Mandanten für Office 365-Dienste desselben Partners auf Office 365-Dienste migriert. Nach der Kundenmigration kann der Partner diesen Kunden nur noch über den Mandanten für Office 365-Dienste verwalten.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Abonnements werden übertragen| Das Microsoft Cloud Deutschland-Abonnement wird zum entsprechenden Office 365 Global-Dienste-Abonnement migriert. <ul><li>Das Office 365 Global-Dienste-Angebot dieses Abonnements wird von Microsoft definiert (auch als _Angebotszuordnung_ bekannt).</li><li> Entsprechende Abonnements für Office 365 Global-Dienste werden in der Office 365 Global-Instanz für die übertragenen Microsoft Cloud Deutschland-Abonnements erworben.</li><li>Alte Microsoft Cloud Deutschland-Abonnements werden nach Abschluss aus dem Office 365-Dienste-Mandanten entfernt.</li></ul>| <ul><li>Änderungen an bestehenden Abonnements (z. B. der Kauf neuer Abonnements oder Änderung der Arbeitsplatzzahl) werden während dieser Phase blockiert.</li><li>Änderungen bei Lizenzzuweisungen werden blockiert. </li><li>Wenn die Migration der Abonnements abgeschlossen ist, werden sowohl Office 365-Dienste als auch MCD-Abonnements im Office 365 Admin-Portal sichtbar sein, der Staus der MCD-Abonnements wird dabei _Bereitstellung aufgehoben_ lauten. </li><li>Alle Kundenprozesse mit Abhängigkeiten von Microsoft Cloud Deutschland-Abonnements oder SKU GUIDs werden unterbrochen und müssen anhand des Office 365-Dienstangebots überarbeitet werden. </li><li>Neue Abonnements für die Office 365-Dienste werden mit der neuen Laufzeit (monatlich/vierteljährlich/jährlich) erworben, und der Kunde erhält eine anteilige Rückerstattung für den nicht verwendeten Restbetrag des Microsoft Cloud Deutschland-Abonnements. </li></ul> |
|Lizenzen werden neu zugewiesen|Benutzern mit zugewiesenen Microsoft Cloud Deutschland-Lizenzen werden Lizenzen in der Office 365 Global-Instanz zugewiesen.|<ul><li>Den Benutzern werden Lizenzen neu zugewiesen, die an die neuen Office 365-Dienstabonnements gebunden sind. Die Benutzerlizenzen aller Benutzer werden automatisch den neuen Features zugewiesen.</li><li>Die Anzahl der Features (Dienstpläne), die von Office 365-Diensten angeboten werden, kann höher sein als im ursprünglichen Microsoft Cloud Deutschland-Angebot.  Benutzerlizenzen in Office 365-Diensten werden äquivalent zu ähnlichen Microsoft Cloud Deutschland-Funktionen (Servicepläne) zugewiesen. </li></ul> 
|**Administratoraufgabe** Features deaktivieren|Falls notwendig, muss der Administrator die Deaktivierung dieser Features durch eine gezielte Aktion vornehmen. |<ul><li>Benutzer werden neue unbekannte Dienste im Portal sehen</li><li>Zusätzliche Funktionalitäten sind verfügbar (z. B. Microsoft Planner und Microsoft Flow), sofern sie nicht vom Mandantenadministrator deaktiviert wurden. Informationen zum Deaktivieren von Dienstplänen, die Benutzerlizenzen zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).</li></ul>
|**Administratoraufgabe**|Alle Kundenprozesse mit Abhängigkeiten von Microsoft Cloud Deutschland-Abonnements oder SKU GUIDs müssen anhand des Office 365-Dienstangebots überarbeitet werden.|Kundenprozesse funktionieren weiterhin.
||||

**Gilt für**: Microsoft-Partner, die das Office 365-Partnerportal verwenden

Zwischen Phase 2 und Phase 3 ist das Partnerportal möglicherweise nicht zugänglich. Während dieser Zeit können Partner möglicherweise nicht auf die Informationen des Mandanten im Partnerportal zugreifen. Da jede Migration anders abläuft, kann die Dauer die das Portal nicht erreichbar ist, Stunden betragen.


## <a name="phase-4-sharepoint-online"></a>Phase 4: SharePoint Online

**Gilt für**: Alle Kunden, die SharePoint Online verwenden.

Wenn Sie immer noch SharePoint 2013-Workflows verwenden, schränken Sie die Verwendung von SharePoint 2013-Workflows während der SharePoint Online-Migration ein.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
| SharePoint und OneDrive werden überführt. | SharePoint Online und OneDrive for Business werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365 Global-Diensten migriert.<br><ul><li>Bestehende Microsoft Cloud Deutschland-URLs bleiben erhalten (Beispiel: `contoso.sharepoint.de`).</li><li>Bestehende Websites bleiben erhalten.</li><li>Clientseitige Authentifizierungstoken, die vom Security Token Service (STS) in der Microsoft Cloud Deutschland- oder Office 365 Global-Dienstinstanz ausgegeben wurden, sind während der Überführung gültig.</li></ul>|<ul><li>Inhalte werden für zwei kurze Zeiträume während der Migration schreibgeschützt sein. Währen dieser Zeit wird ein Banner mit der Mitteilung "Sie können Inhalte nicht bearbeiten" in SharePoint angezeigt.</li><li>Der Suchindex bleibt nicht erhalten, und es kann bis zu 10 Tage dauern, bis er wieder erstellt ist.</li><li>SharePoint Online-/OneDrive for Business-Inhalte werden für zwei kurze Zeiträume während der Migration schreibgeschützt sein. Benutzern wird während dieser Zeit kurzfristig ein Banner mit der Mitteilung "Sie können Inhalte nicht bearbeiten" angezeigt.</li><li>Nach Abschluss der SharePoint Online-Migration sind möglicherweise keine Suchergebnisse für SharePoint Online- und OneDrive for Business-Inhalte verfügbar, während der Index neu erstellt wird. Während dieses Zeitraums werden bei Suchabfragen möglicherweise unvollständige Resultate zurückgegeben. Funktionen, die von Suchindizes abhängig sind, könnten betroffen sein, bis die Neuindizierung abgeschlossen ist.</li><li>SharePoint 2013-Workflows werden während der Migration unterbrochen und müssen nach der Migration erneut veröffentlicht werden.</li></ul>
|**SPO-Administratoren**: Erneute Veröffentlichung von SharePoint 2013-Workflows| Ein SharePoint Online-Administrator veröffentlicht nach der Migration die SharePoint 2013-Workflows erneut.|SharePoint 2013-Workflows sind verfügbar.
|**PowerShell-Benutzer**: Update auf neues Modul| Alle Benutzer des SharePoint Online PowerShell-Moduls müssen nach Abschluss der SharePoint Online-Migration module/Microsoft.SharePointOnline.CSOM auf Version 16.0.20717.12000 oder höher aktualisieren. Der erfolgte Abschluss wird im Nachrichtencenter mitgeteilt.| Es kommt nicht mehr zu Fehlern bei SharePoint Online über PowerShell oder dem clientseitigen Objektmodell.
||||

Zusätzliche Überlegungen:

- Wenn Ihre Organisation immer noch SharePoint 2010-Workflows verwendet, werden diese nach 31. Dezember 2021 nicht mehr funktionieren. SharePoint 2013-Workflows bleiben unterstützt, obwohl sie ab 1. November 2020 für neue Mandaten standardmäßig ausgeschaltet werden. Wenn die Migration zu den SharePoint Onlinediensten abgeschlossen ist, empfehlen wir, dass Sie zu Power Automate oder anderen unterstützten Lösungen wechseln.
 - Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz noch nicht migriert wurde, müssen bei Version 16.0.20616.12000 (oder niedriger) von SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM bleiben. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.
- Während dieser Phase werden sich die IP-Adressen hinter den SharePoint-URLs ändern. Nach dem Übergang zu den Office 365 Global-Diensten werden die Adressen für die erhaltenen Mandanten-URLs (z. B. `contoso.sharepoint.de` und `contoso-my.sharepoint.de`) geändert in [Weltweite Microsoft 365-URLs und IP-Adressbereiche (SharePoint Online und OneDrive for Business)](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business).

> [!NOTE]
> Falls Sie eDiscovery verwenden, achten Sie auf die [eDiscovery Migrationserfahrung](ms-cloud-germany-transition-add-scc.md).

## <a name="phase-5-exchange-online"></a>Phase 5: Exchange Online 
Beginnend mit Phase 5 werden Exchange Online-Postfächer von Microsoft Cloud Deutschland zu Office 365 Global-Diensten verschoben.

Die Office 365 Global-Dienste-Region ist als standardmäßig festgelegt, sodass der interne Lastenausgleichsdienst die Postfächer an die entsprechende Standardregion in den Office 365-Diensten weiterverteilen kann. Bei diesem Übergang befinden sich die Benutzer beider Seiten (MCD- oder Global-Dienste) in der gleichen Organisation und können einen der beiden URL-Endpunkte verwenden.

Die neue Region "Deutschland" wird zum Organisationssetup hinzugefügt. Die Exchange Online-Konfiguration fügt die neue lokale Region "Deutschland" zur wechselnden Organisation hinzu.

- Überführung der Benutzer und Dienste von Ihren älteren MCD-URLs (`https://outlook.office.de`) zu neuen Office 365-Dienst-URLs (`https://outlook.office365.com`).
-  Die Exchange Online-Dienste (Outlook-Webzugriff und Exchange Admin Center) für die neue deutsche Rechenzentrumsregion werden ab dieser Phase verfügbar sein. Sie werden nicht vorher verfügbar sein.
- Benutzer können während der Migration weiterhin über ältere MCD-URLs auf den Dienst zugreifen, müssen jedoch nach Abschluss der Migration die Verwendung der älteren URLs einstellen.
- Die Benutzer sollten zum weltweiten Office-Portal für Office Online-Features ("Kalender", "E-Mail", "Personen") übergehen. Die Navigation zu Diensten, die noch nicht zu Office 365-Diensten migriert wurden, wird erst nach ihrer Migration möglich sein. 
- Diese Einschränkung gilt auch für Hintergrunddienste wie "Mein Konto". Mein Konto für globale Dienste wird nach Abschluss von Phase 9 verfügbar. Bis dahin müssen Benutzer das MCD-Portal verwenden, um ihre Kontoeinstellungen zu verwalten.
- In der Outlook Web App wird das Feature "Öffentlicher Ordner" während der Migration nicht verfügbar sein.

Wenn Sie die Benutzerfotos während der Phase 5 ändern möchten, lesen Sie [Exchange Online-PowerShell – Set-UserPhoto während der Phase 5](#exchange-online-powershell).

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>DNS-Datensatz für AutoErmittlung in Exchange Online
**Gilt für:** Kunden, welche Exchange Online mit einer benutzerdefinierten Domäne verwenden

Vom Kunden verwaltete DNS-Einstellungen für die AutoErmittlung, die derzeit auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, um nach Abschluss der Exchange Online-Phase (Phase 5) auf den globalen Office 365-Endpunkt zu verweisen. <br> Bestehende DNS-Einträge mit CNAME mit Verweis auf „autodiscover-outlook.office.de“ müssen aktualisiert werden, damit sie auf **autodiscover.outlook.com** verweisen.

Bei Kunden, die diese DNS-Updates nach dem **Abschluss der Migrationsphase 9** nicht ausführen, können nach Abschluss der Migration Probleme mit dem Dienst auftreten.

> [!NOTE]
> Überprüfungsfehler im Admin Center für benutzerdefinierte Domänen für den AutoErmittlungseintrag können ignoriert werden. Dienste funktionieren nur dann ordnungsgemäß, wenn der #A0 in "autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**Gilt für:** Exchange Online-Administratoren, die Exchange Online PowerShell verwenden

Die Verwendung der PowerShell-Cmdlets **New-MigrationEndpoint**, **Set-MigrationEndpoint** und **Test-MigrationsServerAvailability** kann während der Migrationsphase zu Fehlern führen (Fehler auf dem Proxy). Dies geschieht, wenn das Vermittlungspostfach auf weltweit migriert wurde, das Administrator-Postfach aber noch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandantensitzung das Vermittlungspostfach als Routing-Hinweis in **ConnectionUri**. Beispiel:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
Die Verwendung des PowerShell-Cmdlets **Set-UserPhoto** führt zu einem Fehler, wenn ein Benutzerpostfach, jedoch kein Administratorpostfach migriert wurde (oder umgekehrt). In diesem Fall muss ein Administrator beim Erstellen der PowerShell-Sitzung des Mandanten die E-Mail-ID des Benutzers, dessen Foto geändert werden muss, in `ConnectionUri` übergeben: 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 Hierbei ist `<user_email>` ein Platzhalter für die E-Mail-ID des Benutzerpostfachs. 

Zusätzliche Überlegungen:
- Benutzer, die mit Outlook Web App auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (Beispiel: ein Benutzer in der MCD-Umgebung greift auf ein freigegebenes Postfach in der Global-Umgebung zu), werden aufgefordert, sich ein zweites Mal zu authentifizieren. Der Benutzer muss sich zuerst authentifizieren und auf sein eigenes Postfach in `outlook.office.de` zugreifen und dann das freigegebene Postfach in `outlook.office365.com` öffnen. Sie müssen sich ein zweites Mal authentifizieren, wenn sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.
- Für bestehende Microsoft Cloud Deutschland-Kunden oder solche, die sich in der Übergangsphase befinden, kann das Anzeigen von Kalenderberechtigungen fehlschlagen, wenn ein freigegebenes Postfach über **Datei > Info > Konto hinzufügen** zu Outlook hinzugefügt wird (der Outlook-Client versucht, die Rest-API `https://outlook.office.de/api/v2.0/Me/Calendars` zu verwenden). Kunden, die ein Konto hinzufügen möchten, um Kalenderberechtigungen anzuzeigen, können den Registrierungsschlüssel wie in [Änderungen der Benutzererfahrung für die Freigabe eines Kalenders in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich sein wird. Dieser Registrierungsschlüssel kann unternehmensweit über eine Gruppenrichtlinie bereitgestellt werden.
- Alle Kunden, die eine aktive Exchange-Hybridkonfiguration verwenden, können Postfächer nicht von der lokalen Exchange Server zu Exchange Online verschieben, weder in Microsoft Cloud Deutschland noch in die neue Rechenzentrumsregion in Deutschland. Kunden müssen sicherstellen, dass laufende Postfachbewegungen vor Phase 5 abgeschlossen wurden und nach Abschluss dieser Phase fortgesetzt werden.
- Stellen Sie sicher, dass alle Benutzer, die ältere Protokolle (POP3/IMAP4/SMTP) für ihre Geräte verwenden, darauf vorbereitet sind, die Endpunkte in ihrem Client zu ändern, nachdem ihr Exchange-Postfach in die neue deutsche Rechenzentrumsregion verschoben wurde, wie in den [Schritten vor der Migration für Exchange Online](ms-cloud-germany-transition-add-pre-work.md#exchange-online) beschrieben.
- Das Planen von Skype for Business-Besprechungen in Outlook Web App ist nach der Migration des Postfachs nicht mehr verfügbar. Bei Bedarf müssen Benutzer stattdessen Outlook verwenden.

Um mehr über die Unterschiede zwischen Organisationen bei der Migration und nach der Migration von Exchange Online-Ressourcen zu erfahren, lesen Sie die Informationen in [Kundenerfahrung während der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition-experience.md).

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>Phase 6: Exchange Online Protection/Sicherheit und Compliance

**Gilt für:** Alle Kunden, die Exchange Online verwenden<br>

Die Backend-Funktionen von Exchange Online Protection (EOP) werden in die neue Region "Deutschland" kopiert. Exchange Online ermöglicht das Routing von externen Hosts zu Office 365, und historische Mandantendetails werden migriert, was auch Back-End-Dienste für Sicherheits- und Compliancefeatures umfasst.

Kunden, die nur Exchange Online-Funktionen verwenden (Nichthybrid), müssen zu diesem Zeitpunkt nicht aufpassen.

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online-Hybridbereitstellungen
**Gilt für:** Alle Kunden, die eine aktive Exchange-Hybridkonfiguration mit lokalen Exchange-Servern verwenden

Stellen Sie sicher, dass die [Exchange-Vorbereitungen](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) durchgeführt wurden, **bevor der Migrationsschritt der Phase 5 beginnt**. Exchange Online-Hybrid-Kunden müssen die neueste Version des Assistenten für die Exchange-Hybridkonfiguration (Exchange Hybrid Configuration Wizard, HCW) im Modus „Office 365 Deutschland“ ausführen, um die lokale Konfiguration für die Migration zu Office 365-Globalen Diensten vorzubereiten.

**Administrator-Aktionen:**
- Zwischen dem Start der Migrationsphase 6 und dem Abschluss der Migrationsphase 9 (wenn der Nachrichtencenterhinweis veröffentlicht wurde) müssen Sie erneut den HCW mit Office 365 Worldwide-Einstellungen ausführen, um Ihre lokalen Systeme auf die Office 365 Global-Dienste zu verweisen. Wenn Sie diese Aufgabe nicht vor Beginn der Phase 9 [Migration abgeschlossen] abschließen, können Unzustellbarkeitsberichte (NDRs) für E-Mails auftreten, die zwischen Ihrer lokalen Exchange-Bereitstellung und Office 365 geroutet werden.
- Beenden oder löschen Sie alle Onboarding- oder Offboarding-Postfachverschiebungen, d. h. verschieben Sie keine Postfächer zwischen Exchange (lokal) und Exchange Online.  Dadurch wird sichergestellt, dass die Anforderungen zum Verschieben der Postfächer nicht fehlschlagen. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Office-Clients führen.
- Zusätzliche Send-Connectors, die neben dem vom HCW erstellten Connector erstellt wurden, und die auf Exchange Online abzielen, müssen in dieser Phase unmittelbar nach Ausführung des HCW-Laufs aktualisiert werden, da sie ansonsten nicht mehr funktionieren. Die TLS-Domäne muss für diese Send-Connectors aktualisiert werden. <br> Verwenden Sie folgenden PowerShell-Befehl in Ihrem Exchange Server-Umgebung, um die TLS-Domäne zu aktualisieren:
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online"></a>Phase 7: Skype for Business Online

**Gilt für**: Alle Kunden, die Skype for Business Online verwenden

Überprüfen Sie [die Schritte vor der Migration für die Skype for Business Online-Migration,](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) und stellen Sie sicher, dass Sie alle Schritte abgeschlossen haben.
In dieser Phase wird Skype for Business zu Microsoft Teams migriert. Bestehende Skype for Business-Kunden werden auf Office 365 Global-Dienste in Europa migriert und anschließend auf Microsoft Teams in der Region "Deutschland" der Office 365-Dienste umgestellt.

- Benutzer können sich am Migrationsdatum nicht bei Skype for Business anmelden. Zehn Tage vor der Migration erhält der Kunde eine Nachricht im Admin Center, die ankündt, wann die Migration stattfinden wird, und erneut, wenn die Migration beginnt.
- Die Richtlinienkonfiguration wird migriert. 
- Benutzer werden zu Teams migriert und haben nach der Migration keinen Zugriff mehr auf Skype for Business.
- Benutzer müssen den Microsoft Teams-Desktopclient installiert haben. Die Installation erfolgt während der 10 Tage über Richtlinien in der Skype for Business-Infrastruktur. Wenn dies jedoch fehlschlägt, müssen Benutzer den Client manuell herunterladen oder eine Verbindung mit einem unterstützten Browser herstellen.
- Kontakte und Besprechungen werden zu Microsoft Teams migriert.
- Benutzer können sich während der Umstellung von Diensten auf Office 365-Dienste nicht in Skype for Business anmelden und auch nicht, bevor die Kunden-DNS-Einträge abgeschlossen sind.
- Kontakte und bestehende Besprechungen werden weiterhin als Skype for Business-Besprechungen funktionieren.
- Die Webbrowserversion von Microsoft Teams funktioniert nach Abschluss von Phase 9 nicht mehr.

Wenn Sie nach Abschluss der Migrationsphase 9 eine Verbindung mit Skype for Business Online mit PowerShell herstellen müssen, verwenden Sie den folgenden PowerShell-Code, um eine Verbindung herzustellen:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>Phase 8: Dynamics 365

**Gilt für:** Alle Kunden, die Microsoft Dynamics 365 verwenden

Vergewissern Sie sich, dass Sie sich mit de Vorgang [Vorbereitungen für Ihre Microsoft Dynamics 365-Installation](ms-cloud-germany-transition-add-pre-work.md#dynamics365) vertraut gemacht haben.

Kunden mit Dynamics 365 müssen zusätzliche Aktionen ausführen, um die Dynamics-Organisationen der Organisation unabhängig migrieren zu können.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Microsoft Dynamics-Ressourcen | Kunden, die mit Microsoft Dynamics arbeiten, werden von Microsoft Engineering oder Microsoft FastTrack beauftragt, Microsoft Dynamics 365 auf die Office 365 Global-Dienstinstanz umzustellen.* |<ul><li>Nach der Migration überprüft der Administrator die Organisation. <</li><li>Der Administrator ändert bei Bedarf die Workflows. </li><li>Der Administrator deaktiviert ggf. den AdminOnly-Modus.</li><li>Der Administrator ändert ggf. die Art der Organisation von _Sandbox_.</li><li>Benachrichtigen Sie die Endbenutzer über die neue URL für den Zugriff auf die Instanz (Organisation).</li><li>Aktualisieren Sie alle eingehenden Verbindungen auf die neue Endpunkt-URL. </li><li>Der Dynamics-Dienst steht Benutzern während des Übergangs nicht zur Verfügung. </li><li>Benutzer müssen die Integrität und Funktionen der Organisation nach der Migration jeder einzelnen Organisation überprüfen.</li></ul>|
||||

\* (i) Kunden mit Microsoft Dynamics 365 müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab.

## <a name="phase-8-power-bi"></a>Phase 8: Power BI

**Gilt für:** Alle Kunden, die Microsoft Power BI (PBI) verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Migration von Power BI-Ressourcen | Kunden mit Microsoft Power BI (PBI) werden von Microsoft Engineering oder Microsoft FastTrack angehalten, nachdem ein vorhandenes PBI-Migrationstool manuell ausgelöst wurde, Power BI auf die Office 365-Dienstinstanz umzustellen.\*\* |<ul><li>Die folgenden Power BI-Elemente werden _nicht_ umgestellt und müssen neu erstellt werden: <</li><li>Echtzeit-Datasets (beispielsweise Streaming- oder Push-Datasets). </li><li>Lokale Power BI-Konfiguration des Datengateways und die Datenquelle. </li><li>Berichte, die auf den Echtzeit-Datasets basieren, sind nach der Migration nicht verfügbar und müssen neu erstellt werden. </li><li>Power BI-Dienste stehen Benutzern während des Übergangs nicht zur Verfügung. Der Dienst sollte höchstens 24 Stunden lang nicht verfügbar sein.</li><li>Benutzer müssen nach der Migration Datenquellen und ihre lokalen Datengateways mit dem Power BI-Dienst neu konfigurieren.  Solange dies nicht der Fall ist, können Benutzer diese Datenquellen nicht verwenden, um planmäßige Aktualisierungen und/oder direkte Abfragen für diese Datenquellen auszuführen. </li><li>Kapazitäten und Premium-Arbeitsbereiche können nicht migriert werden. Kunden müssen alle Kapazitäten vor der Migration löschen und nach der Migration neu erstellen. Verschieben Sie Arbeitsbereiche ggf. zurück zu Kapazitäten.</li></ul>  |
||||

\*\* (i) Kunden mit Microsoft Power BI müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab.

## <a name="phase-9-office-apps"></a>Phase 9: Office-Apps

**Gilt für:** Alle Kunden, die Office-Desktopanwendungen (Word, Excel, PowerPoint, Outlook, ...) verwenden

Die Umstellung von Office 365-Mandanten auf die Region „Deutschland“ erfordert, dass alle Benutzer Anwendungen schließen, sich von Office 365 abmelden und für alle Office-Desktopanwendungen (Word, Excel, PowerPoint, Outlook usw.) und den OneDrive for Business-Client erneut anmelden, nachdem die Mandantenmigration Phase 9 erreicht hat. Durch das Ab- und Anmelden können die Office-Dienste neue Authentifizierungstoken vom globalen Azure AD-Dienst abrufen.

Die beste Benutzererfahrung kann sichergestellt werden, indem Sie die neuesten Office-Anwendungen verwenden. Unternehmen sollten die Nutzung des monatlichen Enterprise-Kanals in Betracht ziehen.

Stellen Sie sicher, dass Sie den Vorgang [Vorbereitung für Mobilgeräte](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) abgeschlossen haben.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Clients, Office Online während der Office-Client-Übernahmemigration, Azure AD finalisiert den Mandantenbereich so, dass er auf die Office 365-Dienste verweist. | Mit dieser Konfigurationsänderung können Office-Clients aktualisiert und auf die Office 365-Dienstendpunkte verweisen. | <ul><li>Benachrichtigen Sie die Benutzer, dass _alle_ Office-Apps geschlossen werden müssen, und sich dann erneut anzumelden (oder erzwingen Sie den Neustart der Clients und die Anmeldung der Benutzer), damit die Office-Clients die Änderung übernehmen können. </li><li>Informieren Sie die Benutzer und Mitarbeiter des Helpdesks, dass Benutzern *möglicherweise* ein Office-Banner angezeigt wird, das sie dazu auffordert, Office-Apps innerhalb von 72 Stunden nach der Umstellung zu reaktivieren. </li><li>Alle Office-Anwendungen auf privaten Computern müssen geschlossen werden, und die Benutzer müssen sich abmelden und dann erneut anmelden. Melden Sie sich in der gelben Aktivierungsleiste an, um die Office 365-Dienste zu reaktivieren.</li><li>Gemeinsam genutzte Computer erfordern Aktionen, die mit jenen für private Computer vergleichbar sind, erfordern aber keine spezielle Vorgehensweise. </li><li>Auf mobilen Geräten müssen sich die Benutzer von Apps abmelden, sie schließen und sich dann erneut anmelden.</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>Phase 9: Vorbereiten branchenspezifischer Apps

**Gilt für:** Alle Kunden, die branchenspezifische Apps verwendet, die mit Office 365 verbunden sind

Falls Sie über branchenspezifische Apps verfügen, stellen Sie sicher, dass Sie die [Vorbereitungen für branchenspezifische Apps](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) abgeschlossen haben.

## <a name="phase-9--10-azure-ad-finalization"></a>Phase 9 und 10: Azure AD-Abschluss

**Gilt für:** Alle Kunden

Wenn der Office 365-Mandant den letzten Schritt der Migration (Azure AD Finalization (Phase 9)) abgeschlossen hat, werden alle Dienste in die welt umstiegen. Weder Anwendungen noch Benutzer sollten über einen der Microsoft Cloud Deutschland-Endpunkte auf Ressourcen für den Mandanten zugreifen. 30 Tage nach Ende des Abschlusses wird der Azure AD-Dienst „Microsoft Cloud Deutschland“ automatisch den Endpunktzugriff für den umgestellten Mandanten beenden. Endpunktanforderungen wie Authentifizierung werden ab diesem Zeitpunkt für den Dienst „Microsoft Cloud Deutschland“ fehlschlagen. 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren von Benutzerendpunkten | Sicherstellen, dass alle Benutzer mithilfe der entsprechenden weltweiten Microsoft-Endpunkte auf den Dienst zugreifen |30 Tage nach Abschluss der Migration werden Anforderungen von Microsoft Cloud Deutschland-Endpunkten nicht mehr unterstützt. Client- oder Anwendungsverkehr schlägt dann fehl.  |
| Aktualisieren der Azure AD-Anwendungsendpunkte | Sie müssen die Authentifizierungs-, Azure Active Directory (Azure AD) Graph- und MS Graph-Endpunkte für Ihre Anwendungen auf diejenigen des Dienstes „Microsoft weltweit“ aktualisieren. | 30 Tage nach Abschluss der Migration werden Anforderungen von Microsoft Cloud Deutschland-Endpunkten nicht mehr unterstützt. Client- oder Anwendungsverkehr schlägt dann fehl. |
||||

### <a name="azure-ad-connect"></a>Azure AD Connect
**Gilt für:** Alle Kunden, die Identitäten mit Azure AD Connect synchronisieren

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Azure AD Connect. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde sicherstellen, dass der Delta-Synchronisierungsprozess abgeschlossen ist. Ändern Sie danach den Zeichenfolgenwert von `AzureInstance` aus 3 (Microsoft Cloud Deutschland) im Registrierungspfad `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` in 0. | Ändern Sie den Wert `AzureInstance` des Registrierungsschlüssels. Andernfalls werden Objekte nicht synchronisiert, wenn die Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

## <a name="post-migration"></a>Nach der Migration

Stellen Sie sicher, dass sie den Artikel [Aktivitäten nach der Migration](ms-cloud-germany-transition-add-experience.md) gelesen haben und diese dann entsprechend ausführen.
