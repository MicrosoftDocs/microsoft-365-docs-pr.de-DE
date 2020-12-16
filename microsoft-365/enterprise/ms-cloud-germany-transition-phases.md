---
title: Migrationsphasen Aktionen und Auswirkungen für die Migration von Microsoft Cloud Deutschland (allgemein)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 'Zusammenfassung: Grundlegendes zu den Migrationsphasen Aktionen und Auswirkungen der Umstellung von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) auf Office 365 Dienste im neuen rechenzentrumsbereich.'
ms.openlocfilehash: 4a032ab88704cfb46b3f451d939a784d222cbb40
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688629"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Migrationsphasen Aktionen und Auswirkungen für die Migration von Microsoft Cloud Deutschland (allgemein)

Mandanten Migrationen von Microsoft Cloud Deutschland in die Region Deutschland der Office 365 Dienste von Microsoft werden als eine Gruppe konfigurierter Aktionen für jede Arbeitsauslastung ausgeführt. Durch diese Aktionen wird sichergestellt, dass wichtige Daten und Erfahrungen zu den Office 365 Diensten migriert werden. Nachdem der Mandant der Migrations Warteschlange hinzugefügt wurde, wird jede Arbeitsauslastung als eine Reihe von Schritten abgeschlossen, die im Back-End-Dienst ausgeführt werden. Für einige Arbeitsauslastungen sind möglicherweise Aktionen durch den Administrator (oder Benutzer) erforderlich, oder die Migration kann sich auf die Verwendung für die Phasen auswirken, die in [der Organisation der Migration](ms-cloud-germany-transition.md#how-is-the-migration-organized) ausgeführt und erläutert werden.

Die folgenden Abschnitte enthalten Aktionen und Effekte für Arbeitsauslastungen, während Sie in verschiedenen Phasen der Migration Fortschreiten. Überprüfen Sie die Tabellen, und bestimmen Sie, welche Aktionen oder Effekte für Ihre Organisation gelten. Stellen Sie sicher, dass Sie bereit sind, die Schritte in den jeweiligen Phasen nach Bedarf auszuführen. Wenn Sie die erforderlichen Schritte nicht ausführen, kann dies zu Dienstunterbrechungen führen und den Abschluss der Migration zu den Office 365 Diensten verzögern.

## <a name="exchange-online"></a>Exchange Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Neue Deutschland-Region wird vorhandenen Organisationseinstellungen hinzugefügt, und Postfächer werden zu Office 365 Diensten verschoben. | In Exchange Online Konfiguration wird die neue Region "Go-local Deutsch" zur Übergangs Organisation hinzugefügt. Diese Office 365-Dienste-Region ist als Standard festgelegt, wodurch der interne Lastenausgleichsdienst das Neuverteilen von Postfächern an die entsprechende Standardregion in Office 365 Diensten ermöglicht. Bei diesem Übergang befinden sich die Benutzer auf beiden Seiten (Deutschland oder Office 365 Dienste) in derselben Organisation und können entweder den URL-Endpunkt verwenden. | Exchange Online | -Übergang von Benutzern und Diensten aus Deutschland-URLs zu Office 365-Dienste-URLs ( `https://outlook.office365.com` ). <br><br> -Benutzer erhalten während der Migration weiterhin Zugriff auf den Dienst über die URLs von Legacy Deutschland. Keine sofortige Aktion erforderlich. <br><br> -Benutzer sollten mit dem Office.com-Portal für Office Online Funktionen (Kalender, e-Mail, Personen) beginnen. Die Navigation zu Diensten, die noch nicht zu Office 365 Diensten migriert wurden, funktioniert erst, wenn Sie migriert wurde. <br><br> – Outlook Web App bietet keine Erfahrung mit öffentlichen Ordnern während der Migration. |
|||||

Weitere Überlegungen:

- `myaccount.msft.com` wird nur nach dem Cutover von Office 365 funktionieren. Links erzeugen bis zu diesem Zeitpunkt Fehlermeldungen "something went wrong".

- Benutzer von Outlook Web App, die auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (beispielsweise greift ein Benutzer in der deutschen Umgebung auf ein freigegebenes Postfach in der globalen Umgebung zu), werden aufgefordert, ein zweites Mal zu authentifizieren. Der Benutzer muss sich zunächst authentifizieren und auf sein Postfach in zugreifen und `outlook.office.de` dann das freigegebene Postfach öffnen, in dem sich befindet `outlook.office365.com` . Sie müssen ein zweites Mal authentifizieren, wenn Sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.

- Wenn ein freigegebenes Postfach Outlook mithilfe von **Datei > Informationen > Konto hinzufügen** hinzugefügt wird, können beim Anzeigen von Kalenderberechtigungen Fehler auftreten, wenn vorhandene Microsoft Cloud Deutschland-Kunden oder diese in den Übergang aufgenommen werden (der Outlook-Client versucht, die Rest-API zu verwenden `https://outlook.office.de/api/v2.0/Me/Calendars` ). Kunden, die ein Konto zum Anzeigen von Kalenderberechtigungen hinzufügen möchten, können den Registrierungsschlüssel wie unter [Benutzeroberflächenänderungen für die Freigabe eines Kalenders in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich ausgeführt wird. Dieser Registrierungsschlüssel kann organisationsweit mithilfe von Gruppenrichtlinien bereitgestellt werden.

- Während der Migrationsphase können mit den PowerShell-Cmdlets **New-migrationEndpoint**, **migrationEndpoint** und **Test-MigrationsServerAvailability** Fehler auftreten (Fehler bei Proxy). Dies ist der Fall, wenn das Vermittlungspostfach weltweit migriert wurde, das Administratorpostfach jedoch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandanten Sitzung das Vermittlungspostfach als Routinghinweis in der **ConnectionUri**. Beispiel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Wenn Sie Exchange Online Hybrid verwenden:

    - Sie müssen den Assistenten für die Hybrid Konfiguration (HCW) erneut ausführen, um die lokale Konfiguration für Microsoft Cloud Deutschland vor dem Übergang zu aktualisieren, und führen Sie den HCW bei der Bereinigung für die Office 365 Dienste erneut aus. Wenn Sie benutzerdefinierte Domänen verwenden, sind möglicherweise zusätzliche DNS-Updates erforderlich.

Weitere Informationen zu den Unterschieden für Organisationen bei der Migration und nach der Migration Exchange Onlineer Ressourcen finden Sie in den Informationen unter [Customer Experience während der Migration zu Office 365 Services in den neuen Bereichen des deutschen Datencenters](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Exchange Online Protection

Back-End-Exchange Online Schutzfeatures (EoP) werden in die Region New Germany kopiert. 

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Exchange Online Routing und Verlaufs Nachrichtendetails. | Exchange Online ermöglicht die Weiterleitung von externen Hosts an Office 365. Die externen MX-Einträge werden an den EoP-Dienst weitergeleitet. Mandanten Konfiguration und Verlaufsdetails werden migriert. | Exchange Online Kunden | -Microsoft – verwaltete DNS-Einträge werden von Office 365 Deutschland EoP auf Office 365 Dienste aktualisiert. <br><br> -Kunden sollten 30 Tage nach EoP Dual Write für die EoP-Migration warten. Andernfalls kann es zu Datenverlusten führen. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| SharePoint und OneDrive werden übergangen. | SharePoint und OneDrive werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365 Diensten migriert. Vorhandene Microsoft Cloud Deutschland-URLs bleiben erhalten (beispielsweise `contoso.sharepoint.de` ). Token, die von Microsoft Cloud Deutschland oder Office 365 Diensten ausgestellt wurden, sind während des Übergangs gültig. | SharePoint-Kunden | -Inhalt wird während zweier kurzer Zeiträume während der Migration schreibgeschützt. In dieser Zeit wird das Banner "Sie können Inhalts Inhalte nicht bearbeiten" in SharePoint erwartet. <br><br> -Der Suchindex wird nicht beibehalten und kann bis zu 10 Tage dauern, bis er neu erstellt wird. <br><br> -SharePoint/OneDrive-Inhalte werden während zwei kurzer Zeiträume während der Migration schreibgeschützt. Benutzern wird während dieser Zeit ein kurzes Banner "Sie können das Inhaltsfeld nicht bearbeiten" angezeigt. <br><br> -Der Suchindex ist möglicherweise nicht verfügbar, während der Index neu erstellt wird. Während dieses Zeitraums geben Suchabfragen möglicherweise keine vollständigen Ergebnisse zurück. <br><br> -Vorhandene Websites werden beibehalten. |
|||||

Weitere Überlegungen:

- Nach Abschluss der SharePoint Online-Migration in die Region Deutschland werden Datenindizes neu erstellt. Features, die von Suchindizes abhängig sind, können beeinträchtigt werden, wenn die Neuindizierung abgeschlossen ist.

- Wenn Ihre Organisation weiterhin SharePoint 2010-Workflows verwendet, funktionieren Sie nach dem 31. Dezember 2021 nicht mehr. SharePoint 2013 Workflows werden weiterhin unterstützt, sind jedoch standardmäßig für neue Mandanten ab dem 1. November 2020 deaktiviert. Nachdem die Migration zum SharePoint Online Dienst abgeschlossen ist, empfehlen wir Ihnen, zu Power Automation oder anderen unterstützten Lösungen zu übergehen.

- Nach Abschluss der OneDrive-Migration in die Region Deutschland werden Daten Indizes neu erstellt. Features, die von Suchindizes abhängen, sind möglicherweise betroffen, während die Neuindizierung ausgeführt wird.


## <a name="skype-for-business-online"></a>Skype for Business Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration von Skype for Business zu Teams. | Vorhandene Skype for Business Kunden werden zu Office 365 Diensten in Europa migriert und anschließend zu Microsoft Teams in der Region Deutschland Office 365 Dienste gewechselt. | Skype for Business Kunden | -Benutzer können sich nicht bei Skype for Business am Migrationsdatum anmelden. Zehn Tage vor der Migration werden Endbenutzer über in-Band auf dem Skype for Business-Client benachrichtigt, dass Sie auf Microsoft Teams aktualisiert werden. Wir werden auch in Admin Center Posten, dass diese Änderungen nach Ablauf der 10 Tage erfolgen. <br><br> -Richtlinienkonfiguration wird migriert. <br><br> -Benutzer werden zu Teams migriert und verfügen nach der Migration nicht mehr über Skype for Business. <br><br> -Benutzer müssen den Desktop-Client von Teams installiert haben. Die Installation erfolgt während der 10 Tage über Richtlinie in der Skype for Business Infrastruktur, wenn dies jedoch nicht der Fall ist, müssen Benutzer den Client dennoch herunterladen oder sich mit einem unterstützten Browser verbinden. <br><br> -Kontakte und Besprechungen werden zu Teams migriert. <br><br> -Benutzer können sich nicht bei Skype for Business Zwischenzeit Dienst Übergängen zu Office 365 Diensten anmelden und erst dann, wenn die Kunden-DNS-Einträge abgeschlossen sind. <br><br> -Kontakte und vorhandene Besprechungen werden weiterhin als Skype for Business Besprechungen fungieren. |
|||||

## <a name="office-services"></a>Office-Dienste

Der zuletzt verwendete (MRU)-Dienst in Office ist ein Cutover aus dem Deutschland-Dienst an Office 365 Diensten, keine Migration. Nur MRU-Links von der Office 365-Dienstseite werden nach der Migration aus dem Office.com-Portal angezeigt. MRU-Links aus dem Deutschland-Dienst sind nicht als MRU-Links in Office 365 Diensten sichtbar. In Office 365 sind MRU-Links nur nach Abschluss der Mandanten Migration verfügbar.

## <a name="subscription"></a>Abonnement

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Kunden können nicht ohne Zustimmung migriert werden. | Microsoft erhält die Möglichkeit, eine Migration auf zwei Arten durchführen zu können, sodass Microsoft den Übergang von Daten und Diensten zur Instanz von Office 365 Diensten koordinieren kann. <br> Der Administrator entscheidet sich für die von Microsoft gesteuerte Migration. <br> Kunden erneuern alle Abonnements in Ihrem Microsoft Cloud Deutschland-Mandanten nach dem 1. Mai 2020. Wir werden diese Kunden monatlich über das Migrationsrecht informieren, 30 Tage warten, um den Kunden die Möglichkeit zu geben, den Vorgang abzubrechen und sich dann direkt anzumelden und im ICM nachzuverfolgen. | Alle Office-Kunden | -Mandant ist als zugestimmt für die Migration markiert, und Admin Center zeigt die Bestätigung an. <br><br> -Die Bestätigung wird an den Cloud Germany-Nachrichten Center Mandanten gesendet. Die Dienstkonfiguration wird von Microsoft Cloud Deutschland-Endpunkten fortgesetzt. <br><br> -Überwachen Sie das Nachrichten Center auf Updates für den Status der Migrationsphase. |
| Abonnements werden übertragen, und Lizenzen werden neu zugewiesen. | Nachdem der Mandant auf Office 365 Dienste umgestellt wurde, werden die entsprechenden Office 365 Dienste-Abonnements für die übertragenen Microsoft Cloud Deutschland-Abonnements erworben. Benutzern mit zugewiesenen Microsoft Cloud Deutschland-Lizenzen wird Office 365 Services-Lizenzen zugewiesen. Legacy-Microsoft Cloud Deutschland-Abonnements werden nach Abschluss des Office 365 Services-Mandanten entfernt. | Alle Office-Kunden | -Änderungen an vorhandenen Abonnements werden in dieser Phase blockiert (beispielsweise keine neuen Abonnements Käufe oder Änderungen an der Anzahl der Arbeitsplätze). <br><br> -Die Änderungen an der Lizenzzuweisung werden blockiert. <br><br> -Das Microsoft Cloud Deutschland-Abonnement wird zu einem entsprechenden Office 365 Dienst Abonnement migriert. Das Office 365-Dienstangebot dieses Abonnements wird von Microsoft definiert (auch als _Angebots Zuordnung_ bezeichnet). <br><br> -Die Anzahl der von Office 365 Diensten angebotenen Features (Servicepläne) kann größer sein als im ursprünglichen Microsoft Cloud Deutschland-Angebot. Benutzerlizenzen in Office 365 Diensten werden gleichwertig ähnlichen Microsoft Cloud Deutschland-Features (Servicepläne) zugewiesen. Benutzerlizenzen aller Benutzer werden automatisch den neuen Features zugewiesen. Der Administrator muss eine explizite Aktion ausführen, um diese Lizenzen bei Bedarf zu deaktivieren. <br><br> -Wenn die Abonnement Migration abgeschlossen ist, werden sowohl Office 365-Dienste als auch Deutschland-Abonnements im Office 365-Verwaltungs Portal angezeigt, wobei der Status von Deutschland- _Abonnements als nicht_ mehr verfügbar ist. <br><br> -Benutzer werden Lizenzen neu zugewiesen, die an die neuen Office 365-Dienste-Abonnements gebunden sind. Kundenprozesse, die Abhängigkeiten von Deutschland-Abonnements oder SKU-GUIDs aufweisen, werden unterbrochen und müssen mit dem Office 365-Dienstangebot überarbeitet werden. <br><br> -Neue Abonnements im Office 365 Dienste werden mit dem neuen Ausdruck (monatlich/quartalsweise/jährlich) erworben, und der Kunde erhält eine anteilige Erstattung für das nicht verwendete Guthaben des Microsoft Cloud Deutschland-Abonnements. <br><br> -Partner Microsoft Cloud Deutschland-Mandanten werden nicht migriert. CSP-Kunden werden zu Office 365 Diensten unter dem neuen Office 365-Dienste-Mandanten desselben Partners migriert. Nach der Kundenmigration kann der Partner diesen Kunden nur über den Office 365-Dienste-Mandanten verwalten. <br><br> -Zusätzliche Funktionen sind verfügbar (beispielsweise Microsoft Planner und Microsoft Flow), es sei denn, Sie sind vom mandantenadministrator deaktiviert. Informationen zum Deaktivieren von Dienstplänen, die den Benutzerlizenzen zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Nächster Schritt

[Ausführen zusätzlicher vorab arbeiten](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
