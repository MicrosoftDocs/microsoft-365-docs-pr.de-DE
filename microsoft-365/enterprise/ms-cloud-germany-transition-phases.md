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
ms.openlocfilehash: 310b8abe0597a4d28a5c539e52bf9a0f5f5f83d9
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515178"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Aktionen und Auswirkungen der Migrationsphasen für die Migration von Microsoft Cloud Deutschland (generell)

Mandanten-Migrationen von Microsoft Cloud Deutschland in die Region Deutschland der Office 365-Dienste von Microsoft werden als eine Reihe von Phasen und deren konfigurierten Aktionen für jeden Workload ausgeführt. Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren. 

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

Die Phasen und ihre Aktionen stellen sicher, dass kritische Daten und Erfahrungen zu den Office 365-Diensten migriert werden. Nachdem Ihr Mandant der Migrations-Warteschlange hinzugefügt wurde, wird jeder Workload als eine Reihe von Schritten abgeschlossen, die auf dem Backend-Dienst ausgeführt werden. Einige Workloads erfordern möglicherweise Aktionen des Administrators (oder Benutzers), oder die Migration kann die Verwendung der ausgeführten Phasen beeinflussen, die unter [Wie ist die Migration organisiert?](ms-cloud-germany-transition.md#how-is-the-migration-organized) diskutiert werden.

Die folgenden Abschnitte enthalten Aktionen und Auswirkungen für Workloads, während sie die verschiedenen Phasen der Migration durchlaufen. Überprüfen Sie die Tabellen und stellen Sie fest, welche Aktionen oder Auswirkungen auf Ihre Organisation zutreffen. Stellen Sie sicher, dass Sie vorbereitet sind, die Schritte in den jeweiligen Phasen wie erforderlich auszuführen. Wenn die erforderlichen Schritte nicht ausgeführt werden, kann dies zu einem Ausfall des Dienstes führen und der Abschluss der Migration zu den Office 365-Diensten kann sich verzögern.

## <a name="opt-in"></a>Opt-In
| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
| Wir können Kunden ohne ihre Zustimmung nicht migrieren. | Microsoft hat das Recht, auf zwei Arten zu migrieren, wodurch Microsoft den Übergang von Daten und Diensten zur Office 365-Dienstinstanz koordinieren kann. <br> Der Administrator meldet sich für die von Microsoft gesteuerte Migration an. <br> Kunden erneuern sämtliche Abonnements in ihrem Microsoft Cloud Deutschland-Mandanten nach dem 1. Mai 2020. Wir werden diese Kunden jeden Monat über das Migrationsrecht informieren, 30 Tage warten, um den Kunden die Möglichkeit zu geben, die Migration zu stornieren, und uns dann direkt anmelden und dies in ICM nachverfolgen. | Alle Office-Kunden | – Der Mandant ist als mit der Migration einverstanden markiert und das Admin Center zeigt die Bestätigung. <br><br> – Die Zustimmung wird im Mandanten-Nachrichtencenter von Cloud Deutschland veröffentlicht. Die Dienstkonfiguration wird von den Endpunkten der Microsoft Cloud Deutschland fortgesetzt. <br><br> – Monitor-Nachrichtencenter für Aktualisierungen des Status der Migrationsphasen. |


## <a name="subscription-phase-3"></a>Abonnement (Phase 3)

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Abonnements werden übertragen und Lizenzen werden neu zugewiesen. | Nach der Umstellung des Mandanten auf Office 365-Dienste werden für die übertragenen Microsoft Cloud Deutschland-Abonnements entsprechende Office 365-Dienste-Abonnements erworben. Benutzer mit zugewiesenen Lizenzen von Microsoft Cloud Deutschland erhalten Lizenzen für Office 365-Dienste zugewiesen. Alte Microsoft Cloud Deutschland-Abonnements werden nach Abschluss aus dem Office 365-Dienste-Mandanten entfernt. | Alle Office Kunden | – Änderungen an bestehenden Abonnements (z. B. der Kauf neuer Abonnements oder Änderung der Arbeitsplatzzahl) werden während dieser Phase blockiert. <br><br> – Änderungen der Lizenzzuweisung werden blockiert.  <br><br> – Das Microsoft Cloud Deutschland-Abonnement wird auf ein entsprechendes Office 365-Dienste-Abonnement migriert. Das Office 365-Dienste-Angebot dieses Abonnements wird von Microsoft definiert (auch als _Angebotsabbildung_ bekannt). <br><br> – Die Anzahl der Features (Dienstpläne), die von Office 365-Diensten angeboten werden, kann höher sein als im ursprünglichen Microsoft Cloud Deutschland-Angebot.  Benutzerlizenzen in Office 365-Diensten werden äquivalent zu ähnlichen Microsoft Cloud Deutschland-Funktionen (Servicepläne) zugewiesen. Benutzerlizenzen aller Benutzer werden automatisch an diese neuen Features zugewiesen. Falls notwendig, muss der Administrator die Deaktivierung dieser Lizenzen durch eine explizite Aktion vornehmen. <br><br> – Wenn die Migration der Abonnements abgeschlossen ist, werden sowohl Office 365-Dienste wie auch Deutschland-Abonnements im Office 365 Admin-Portal sichtbar sein, der Staus der Deutschland-Abonnements wird _abgemeldet_ sein. <br><br> – Den Benutzern werden neue Lizenzen zugewiesen, die an die neuen Office 365-Dienste-Abonnements gebunden sind. Alle Kundenprozesse mit Abhängigkeiten zu Deutschland-Abonnements oder SKU GUIDs werden unterbrochen und müssen mit dem Office 365-Serviceangebot überarbeitet werden. <br><br> – Neue Abonnements für die Office 365-Dienste werden mit der neuen Laufzeit (monatlich/vierteljährlich/jährlich) erworben, und der Kunde erhält eine anteilige Rückerstattung für den nicht verwendeten Restbetrag des Microsoft Cloud Deutschland-Abonnements. <br><br> – Mandanten von Partner Microsoft Cloud Deutschland werden nicht migriert. CSP-Kunden werden unter dem neuen Mandanten für Office 365-Dienste desselben Partners auf Office 365-Dienste migriert. Nach der Kundenmigration kann der Partner diesen Kunden nur noch über den Mandanten für Office 365-Dienste verwalten. <br><br> – Zusätzliche Funktionalitäten sind verfügbar (z. B. Microsoft Planner und Microsoft Flow), sofern sie nicht vom Mandantenadministrator deaktiviert wurden. Informationen zum Deaktivieren von Dienstplänen, die Benutzerlizenzen zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||


## <a name="sharepoint-online-phase-4"></a>SharePoint Online (Phase 4)

**Gilt für**: SharePoint Online

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-----|:-------|
| SharePoint und OneDrive werden übergangen | SharePoint Online und OneDrive for Business werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365 Global Services migriert.<br><ul><li>Bestehende URLs von Microsoft Cloud Deutschland bleiben erhalten (Beispiel: `contoso.sharepoint.de`)</li><li>Vorhandene Websites werden beibehalten.</li><li>Clientseitige Authentifizierungstoken, die vom Sicherheitstokendienst (Security Token Service, STS) in der Microsoft Cloud Deutschland- oder Office 365 Global Services-Instanz ausgestellt wurden, sind während des Übergangs gültig.</li></ul>|<ul><li>Inhalte sind während der Migration für zwei kurze Zeiträume schreibgeschützt. Währen dieser Zeit wird ein Banner „Sie können Inhalte nicht bearbeiten“ in SharePoint angezeigt.</li><li>Der Suchindex wird nicht beibehalten und kann bis zu 10 Tage dauern, bis er neu erstellt wird.</li><li>SharePoint Online- und OneDrive for #A0 sind während der Migration für zwei kurze Zeiträume schreibgeschützt. Benutzer werden während dieser Zeit kurzfristig ein Banner „Sie können Inhalte nicht bearbeiten“ sehen.</li><li>Nach Abschluss der SharePoint #A0 sind die Suchergebnisse für SharePoint Online- und OneDrive for #A1 möglicherweise nicht verfügbar, während der Index neu erstellt wird. Während dieser Periode geben Suchanfragen möglicherweise unvollständige Resultate zurück. Features, die von Suchindizes abhängig sind, z. B. SharePoint Online News, können während der Neuindizierung beeinträchtigt werden.</li></ul>|
||||

Zusätzliche Überlegungen:

- Wenn Ihre Organisation immer noch SharePoint 2010-Workflows verwendet, werden diese nach 31. Dezember 2021 nicht mehr funktionieren. SharePoint 2013-Workflows bleiben unterstützt, obwohl sie ab 1. November 2020 für neue Mandaten standardmäßig ausgeschaltet werden. Wenn die Migration zu den SharePoint Onlinediensten abgeschlossen ist, empfehlen wir, dass Sie zu Power Automate oder anderen unterstützten Lösungen wechseln.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz noch nicht migriert wurde, müssen bei Version 16.0.20616.12000 (oder niedriger) von SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM bleiben. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz bereits migriert wurde, müssen SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM auf Version 16.0.20717.12000 oder höher aktualisieren. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.

## <a name="exchange-online-phase-5"></a>Exchange Online (Phase 5)

**Gilt für:**  Exchange Online

Wenn Sie Exchange Online hybrid verwenden: Exchange Online Hybrid-Kunden müssen den Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW) im Rahmen dieses Übergangs mehrmals ausführen.

Wie in der [](ms-cloud-germany-transition-add-pre-work.md#exchange-online)Migrationsvorarbeit beschrieben, müssen Exchange Online-Hybridkunden vor Beginn der Migrationsphase **5** die neueste Version des HCW im Office 365 Deutschland-Modus ausführen, um die lokale Konfiguration für die Migration zu Office 365 global vorzubereiten.

Nach Abschluss der Migrationsphase **5** (wenn der Message Center-Hinweis veröffentlicht wird) müssen Sie den HCW erneut mithilfe von Office 365 Worldwide-Einstellungen ausführen, um Ihre lokalen Systeme auf den globalen Office 365-Dienst zu verweisen. Wenn Sie benutzerdefinierte Domänen verwenden, werden möglicherweise weitere DNS-Updates erforderlich sein.


| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Exchange Online-Postfächer werden von Microsoft Cloud Deutschland zu Globalen Office 365-Diensten verschoben.| Die Exchange Online-Konfiguration fügt die neue lokale deutsche Region zur Übergangsorganisation hinzu. Die Region "Globale Office 365-Dienste" ist als Standard festgelegt, wodurch der interne Lastenausgleichsdienst Postfächer an die entsprechende Standardregion in Office 365-Diensten weiterverteilen kann. In diesem Übergang befinden sich Benutzer auf beiden Seiten (Deutschland oder globale Dienste) in derselben Organisation und können einen der beiden URL-Endpunkte verwenden. |<ul><li>Stellen Sie Benutzer und Dienste von Ihren älteren URLs (outlook.office.de) in neue URLs für Office 365-Dienste ( `https://outlook.office365.com` ) um.</li><li>Benutzer können während der Migration weiterhin über ältere URLs in Deutschland auf den Dienst zugreifen, müssen jedoch nach Abschluss der Migration die Verwendung der älteren URLs beenden.</li><li>Benutzer sollten auf das weltweite Office-Portal für Office Online-Features (Kalender, E-Mail, Personen) umstiegen. Die Navigation zu Diensten, die noch nicht zu Office 365-Diensten migriert wurden, funktioniert erst, wenn sie migriert wurden. </li><li>Die Outlook Web App stellt während der Migration keine Öffentliche Ordner zur Verfügung. </li></ul>|
| Aktualisieren von benutzerdefinierten DNS-Einstellungen für die AutoErmittlung| Vom Kunden verwaltete DNS-Einstellungen für Die AutoErmittlung, die derzeit auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, um nach Abschluss der Exchange Online-Phase (Phase 5) auf den globalen Office 365-Endpunkt zu verweisen. <br> Vorhandene #A0 mit CNAME, die auf autodiscover-outlook.office.de müssen aktualisiert werden, um auf autodiscover.outlook.com. |  Verfügbarkeitsanforderungen und Dienstermittlungsaufrufe über AutoErmittlungspunkt direkt an die Office 365-Dienste. Kunden, die diese DNS-Updates nicht ausführen, treten beim Abschluss der Migration möglicherweise Probleme mit dem AutoErmittlungsdienst auf. |
||||

Zusätzliche Überlegungen:

- `myaccount.microsoft.com` wird erst nach der Übernahme auf Office 365 funktionieren. Links werden bis zu diesem Zeitpunkt Fehlermeldungen wie „Etwas ist fehlgeschlagen“ zurückgeben.

- Benutzer, die mit Outlook Web App auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (Beispiel: ein Benutzer in der Deutschland-Umgebung greift auf ein freigegebenes Postfach in der globalen Umgebung zu), werden aufgefordert, sich ein zweites Mal zu authentifizieren. Der Benutzer muss sich zuerst authentifizieren und auf sein eigenes Postfach in `outlook.office.de` zugreifen und dann das freigegebene Postfach in `outlook.office365.com` öffnen. Sie müssen sich ein zweites Mal authentifizieren, wenn sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.

- Für bestehende Microsoft Cloud Deutschland-Kunden oder solche, die sich in der Übergangsphase befinden, kann das Anzeigen von Kalenderberechtigungen fehlschlagen, wenn ein freigegebenes Postfach über **Datei > Info > Konto hinzufügen** zu Outlook hinzugefügt wird (der Outlook-Client versucht, die Rest-API `https://outlook.office.de/api/v2.0/Me/Calendars` zu verwenden). Kunden, die ein Konto hinzufügen möchten, um Kalenderberechtigungen anzuzeigen, können den Registrierungsschlüssel wie in [Änderungen der Benutzererfahrung für die Freigabe eines Kalenders in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich sein wird. Dieser Registrierungsschlüssel kann unternehmensweit über eine Gruppenrichtlinie bereitgestellt werden.

- Die Verwendung der PowerShell-Cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, und **Test-MigrationsServerAvailability** kann während der Migrationsphase zu Fehlern führen (Fehler auf dem Proxy). Dies geschieht, wenn das Vermittlungspostfach auf weltweit migriert wurde, das Administrator-Postfach aber noch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandantensitzung das Vermittlungspostfach als Routing-Hinweis in **ConnectionUri**. Beispiel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

Um mehr über die Unterschiede zwischen Organisationen bei der Migration und nach der Migration von Exchange Online-Ressourcen zu erfahren, lesen Sie die Informationen in [Kundenerfahrung während der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection / Security and Compliance (Phase 6)

Die Backend-Funktionen von Exchange Online Protection (EOP) werden in die neue Region Deutschland kopiert. 

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration des Exchange Online-Routing und von historischen Nachrichtendetails. | Exchange Online ermöglicht das Weiterleiten von externen Hosts auf Office 365. Die externen MX-Datensätze werden umgestellt, um auf die EOP-Dienste weiterzuleiten. Die Mandanten-Konfiguration und historische Details werden migriert. | Exchange Online-Kunden | – Microsoft-verwaltete DNS-Einträge werden von Office 365 Deutschland EOP zu Office 365-Diensten aktualisiert. <br><br> – Kunden sollten währen 30 Tagen nach dem EOP Dual Write auf die EOP-Migration warten. Anderenfalls kann es zu einem Datenverlust kommen. |
|||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business Online (Phase 7)

| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Wechseln von Skype for Business zu Microsoft Teams. | Bestehende Skype for Business-Kunden werden auf Office 365-Dienste in Europa migriert und anschließend auf Microsoft Teams in der Region Deutschland der Office 365-Dienste umgestellt. | Skype for Business-Kunden | – Benutzer können sich am Migrationsdatum nicht bei Skype for Business anmelden. Zehn Tage vor der Migration werden Sie im Admin Center über den Zeitpunkt der Migration informiert, und erneut, wenn die Migration beginnt. <br><br> – Die Richtlinienkonfiguration wird migriert.  <br><br> – Die Benutzer werden nach Teams migriert und verfügen nach der Migration nicht mehr über Skype for Business. <br><br> – Die Benutzer müssen den Teams-Desktopclient installiert haben. Die Installation erfolgt während der 10 Tage über Richtlinien in der Skype for Business-Infrastruktur. Wenn dies jedoch fehlschlägt, müssen Benutzer den Client manuell herunterladen oder eine Verbindung mit einem unterstützten Browser herstellen. <br><br> – Kontakte und Besprechungen werden nach Teams migriert. <br><br> – Benutzer können sich während der Übergangszeit der Dienste nach Office 365-Dienste nicht in Skype for Business anmelden und auch nicht, bevor die Kunden-DNS-Einträge abgeschlossen sind. <br><br> – Kontakte und vorhandene Besprechungen werden weiterhin als Skype for Business-Besprechungen funktionieren.  |
|||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (Phase 8)
Kunden mit Dynamics 365 benötigen zusätzliches Engagement, um die Dynamics-Organisationen der Organisation unabhängig zu migrieren.
 
| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-Ressourcen | Kunden, die mit Microsoft Dynamics arbeiten, werden vom Engineering oder FastTrack beauftragt, Dynamics zur die Office 365-Dienstinstanz zu verlagern.* | Microsoft Dynamics 365-Kunden | – Der Administrator überprüft die Organisation nach der Migration. <br><br> – Der Administrator ändert bei Bedarf die Workflows. <br><br> – Der Administrator deaktiviert ggf. den AdminOnly-Modus. <br><br> – Der Administrator ändert ggf. die Art der Organisation von _Sandbox_. <br><br> – Benachrichtigen Sie die Endbenutzer über die neue URL für den Zugriff auf die Instanz (Organisation). <br><br> – Aktualisieren Sie alle eingehenden Verbindungen auf die neue Endpunkt-URL. <br><br> – Der Dynamics-Dienst steht Benutzern während des Übergangs nicht zur Verfügung. <br><br> – Benutzer sind verpflichtet, die Integrität und Funktionen der Organisation nach der Migration jeder einzelnen Organisation zu überprüfen.  |
|||||

\* (i) Kunden mit Microsoft Dynamics 365 müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab.


## <a name="power-bi-phase-8-of-9"></a>Power BI (Phase 8 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Power BI-Ressourcen | Kunden mit Microsoft Power BI werden von Engineering oder FastTrack beauftragt, nachdem ein vorhandenes PBI-Migrationstool manuell ausgelöst wurde, Power BI auf die Office 365-Dienstinstanz umzustellen.\*\* | Microsoft Power BI-Kunden | – Die folgenden Power BI-Elemente werden _nicht_ verschoben, und müssen neu erstellt werden: <br><br> – Echtzeit-Datasets (beispielsweise Streaming- oder Push-Datasets). <br> – Lokale Power BI-Konfiguration des Datengateways und die Datenquelle. <br> – Berichte, die auf den Echtzeit-Datasets basieren, sind nach der Migration nicht verfügbar und müssen neu erstellt werden. <br><br> – Power BI-Dienste stehen Benutzern während des Übergangs nicht zur Verfügung. Der Dienst sollte höchstens 24 Stunden lang nicht verfügbar sein. <br><br> – Benutzer müssen nach der Migration Datenquellen und ihre lokalen Datengateways mit dem Power BI-Dienst neu konfigurieren.  Solange dies nicht der Fall ist, können Benutzer diese Datenquellen nicht verwenden, um planmäßige Aktualisierungen und/oder direkte Abfragen für diese Datenquellen auszuführen. <br><br> – Kapazitäten und Premium-Arbeitsbereiche können nicht migriert werden. Kunden müssen alle Kapazitäten vor der Migration löschen und nach der Migration neu erstellen. Verschieben Sie Arbeitsbereiche ggf. zurück zu Kapazitäten.  |
|||||

\*\* (i) Kunden mit Microsoft Power BI müssen in diesem Migrationsszenario Maßnahmen ergreifen, die durch den bereitgestellten Migrationsprozess definiert sind. (ii) Wenn der Kunde keine Maßnahmen ergreift, bedeutet dies, dass Microsoft die Migration nicht abschließen kann. (iii) Wenn Microsoft die Migration aufgrund der Inaktivität des Kunden nicht abschließen kann, läuft das Abonnement des Kunden am 29. Oktober 2021 ab. 


## <a name="office-apps"></a>Office-Apps

Office-Kunden, die in die Region Deutschland überwechseln, müssen alle #A0 (Word, PowerPoint, Outlook usw.) und den OneDrive for #A1 nach Abschluss der Migration schließen und abmelden und wieder anmelden. Wenn Sie sich ab- und anmelden, können die Office-Dienste neue Authentifizierungstoken vom globalen Azure AD-Dienst abrufen.
 
| Schritte: | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Clients, Office Online während der Office-Client-Übernahmemigration, Azure AD finalisiert den Mandantenbereich so, dass er auf die Office 365-Dienste verweist. | Mit dieser Konfigurationsänderung können Office-Clients aktualisiert und auf die Office 365-Dienstendpunkte verweisen. | Alle Office-Kunden | – Benachrichtigen Sie die Benutzer, dass _alle_ Office-Apps geschlossen werden, und melden Sie sich dann erneut an (oder erzwingen Sie den Neustart der Clients und die Anmeldung der Benutzer), damit die Office-Clients die Änderung übernehmen können. <br><br> – Informieren Sie die Benutzer und Mitarbeiter des Helpdesks, dass Benutzern *möglicherweise* ein Office-Banner angezeigt wird, das sie dazu auffordert, Office-Apps innerhalb von 72 Stunden nach der Übernahmemigration zu reaktivieren. <br><br> – Alle Office-Anwendungen auf privaten Computern müssen geschlossen werden, und die Benutzer müssen sich abmelden und dann erneut anmelden. Melden Sie sich in der gelben Aktivierungsleiste an, um die Office 365-Dienste zu reaktivieren. <br><br> – Gemeinsam genutzte Computer erfordern Aktionen, die mit privaten Computern vergleichbar sind, erfordern aber keine spezielle Vorgehensweise. <br><br> – Auf mobilen Geräten müssen sich die Benutzer von Apps abmelden, sie schließen und sich dann erneut anmelden. |
|||||

## <a name="office-services"></a>Office-Dienste

Der Dienst „zuletzt verwendet“ (most recently used, MRU) in Office ist eine Übernahme des Deutschland-Dienstes zu Office 365-Dienste, keine Migration.  Nach der Migration vom Office.com-Portal werden nur MRU-Links von der Seite der Office 365-Dienste sichtbar sein. MRU-Links vom Deutschland-Dienst werden nicht als MRU-Links in den Office 365-Diensten sichtbar sein. MRU-Links in Office 365 sind erst verfügbar, wenn die Mandanten-Migration abgeschlossen ist.


## <a name="next-step"></a>Nächster Schritt

[Zusätzliche Vorarbeit durchführen](ms-cloud-germany-transition-add-pre-work.md)

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

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
