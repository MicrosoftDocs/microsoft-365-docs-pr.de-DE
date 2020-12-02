---
title: Zusätzliche Arbeits Vorbereitungsinformationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Zusammenfassung: zusätzliche vorarbeits Informationen beim Wechsel von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) zu Office 365 Diensten im neuen rechenzentrumsbereich.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551708"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Arbeits Vorbereitungsinformationen für die Migration von Microsoft Cloud Deutschland

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Stellen Sie sicher, dass die Netzwerkkonnektivität zu [Office 365 Diensten-URLs und IP-Adressen](https://aka.ms/o365urls)besteht. | Alle vom Kunden gehosteten Clients und Dienste, die für den Zugriff auf Office 365 Dienst verwendet werden, müssen auf die Endpunkte der Office 365 Dienste zugreifen können. | Alle Transitioning-Kunden und Kunden mit Netzwerkzugriff auf Microsoft Cloud Deutschland beschränkt. | Erforderliche Aktion. InAktion kann zu Fehlern des Diensts oder der Client Software führen. |
| Überprüfen und Vorbereiten der migrationsbezogenen DNS-Änderungen. | Der Kunde bereitet DNS-Einträge für Exchange Online und Exchange Online Schutz vor (MX-Eintrag usw.). | Exchange Online Kunden | Dies ist eine empfohlene Aktion. Keine Aktion bedeutet, dass die e-Mails von migrierten Kunden über Microsoft Cloud Deutschland weitergeleitet werden können, bis Microsoft Cloud Deutschland-Dienste deaktiviert sind. |
| Überprüfen und Vorbereiten der migrationsbezogenen DNS-Änderungen. | Änderungen des kundeneigenen DNS-Zonen für Skype for Business Online. | Skype for Business Online-Kunden | -Es wird empfohlen, die Gültigkeitsdauer (Time-to-Live, TTL) für alle DNS-Einträge im Besitz von Kunden in 5 Minuten zu aktualisieren, um die Aktualisierung von DNS-Einträgen zu beschleunigen. Allerdings kann die mit dieser DNS-Änderung verbundene von Microsoft verwaltete Cutover jederzeit innerhalb des angegebenen 24-stündigen Fenster Wechsels auftreten. <br><br> -Die Unterbrechung des Diensts ist in der Zukunft möglich. Benutzer können sich nicht bei Skype for Business anmelden und werden in den Office 365 Diensten zu den migrierten Teams umgeleitet. |
| Vorbereiten der Schulung von Endbenutzern und Administratoren und Bereitschaft für den Übergang zu Microsoft Teams. | Sie können den Übergang von Skype zu Microsoft Teams durch die Planung der Benutzerkommunikation und Bereitschaft erfolgreich durchführen. | Skype for Business Online-Kunden | -Clients müssen über die neuen Dienste informiert sein und nach der Umstellung ihrer Dienste auf die Office 365 Dienste verwenden. <br><br> -Nachdem DNS-Änderungen sowohl für die Kunden-Eitelkeits Domänen als auch für die anfängliche Domäne vorgenommen wurden, würden sich die Benutzer bei Skype for Business anmelden und sehen, dass Sie jetzt zu Microsoft Teams migriert werden. Dadurch wird auch der Desktop Client für Microsoft Teams im Hintergrund heruntergeladen. |
| Vorbereiten der Schulung von Endbenutzern und Administratoren für Benutzer, die Ihr Konto für IOS und Android entfernen und erneut hinzufügen möchten Microsoft Outlook. | Microsoft Outlook für IOS-und Android-Konten, die mit Postfächern in Microsoft Cloud Deutschland konfiguriert sind, müssen möglicherweise entfernt und Outlook erneut hinzugefügt werden, damit die neue Konfiguration für Office 365 Dienste ordnungsgemäß synchronisiert wird. | Microsoft Outlook für IOS-und Android-Kunden | Outlook-Postfächer, die zuvor für Microsoft Cloud Deutschland konfiguriert wurden, greifen möglicherweise nicht die neue Konfiguration von Office 365 Diensten auf, was zu Fehlern und einer beeinträchtigten Leistung anderer Benutzeroberflächen führt. IT-Administratoren werden angehalten, Dokumentationen bereitzustellen, mit denen Benutzer proaktiv angewiesen werden, ihre Konten zu Microsoft Outlook für IOS und Android zu entfernen und erneut hinzuzufügen, wenn nach der Migration Probleme mit der Anmeldung oder Synchronisierung von e-Mails auftreten. |
| Bereiten Sie die Benutzer darauf vor, nach der Migration über einen Neustart und die Anmeldung bei ihren Clients zu benachrichtigen. | Die Office-Clientlizenzierung wechselt von Microsoft Cloud Deutschland zu Office 365 Diensten in der Migration. Clients holen eine neue gültige Lizenz ein, nachdem Sie sich bei Office-Clients bei und in angemeldet haben. | Microsoft 365 apps-Kunden |  Die Office-Produkte der Benutzer müssen Lizenzen von Office 365 Diensten aktualisieren. Wenn Lizenzen nicht aktualisiert werden, treten bei Office-Produkten möglicherweise Lizenz Überprüfungsfehler auf. |
| Alle Testabonnements werden abgebrochen. | Testabonnements werden nicht migriert und blockieren die Übertragung von kostenpflichtigen Abonnements. | Alle Kunden | Testdienste sind abgelaufen und nicht funktionsfähig, wenn Benutzer nach dem Abbruch von Benutzern darauf zugreifen. |
| Bereitstellen von Microsoft Teams-Desktop Clients für Benutzer, die auf Skype for Business in Deutschland zugreifen. | Migration verschiebt Benutzer zu Teams für Zusammenarbeit, Anrufe und Chats. Stellen Sie entweder den Microsoft Teams-Desktop Client bereit, oder stellen Sie sicher, dass ein unterstützter Browser verfügbar ist. | Skype for Business Kunden | Inaktivität führt nicht zur Verfügbarkeit von Teams-Zusammenarbeitsdiensten. |
| Analysieren Sie die Unterschiede bei den Lizenz Funktionen zwischen Microsoft Cloud Deutschland und Office 365 Diensten. | Office 365 Dienste umfassen zusätzliche Features und Dienste, die in der aktuellen Microsoft Cloud Deutschland nicht verfügbar sind. Während der Abonnement Übertragung werden neue Features für Benutzer verfügbar sein. | Alle Kunden | -Analysieren Sie die verschiedenen Features, die von den Lizenzen für Microsoft Cloud Deutschland und Office 365 Diensten bereitgestellt werden. Beginnen Sie mit der [Beschreibung des Office 365-Platt Form Diensts](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> – Stellen Sie fest, ob neue Features von Office 365 Diensten anfänglich deaktiviert werden sollten, um Auswirkungen auf Benutzer oder Benutzer Änderungsverwaltung zu begrenzen, und ändern Sie bei Bedarf die Zuweisung von Benutzerlizenzen. <br><br> -Vorbereiten von Benutzern und Helpdesk-Mitarbeitern für neue Dienste und Features, die von Office 365 Diensten bereitgestellt werden. |
| Erstellen von organisationsweiten [Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention) zum Schutz vor versehentlichem Löschen von Inhalten während der Migration.  | -Um sicherzustellen, dass der Inhalt während der Migration nicht versehentlich von den Endbenutzern gelöscht wird, können Kunden eine unternehmensweite Aufbewahrungsrichtlinie aktivieren. <br><br> -Obwohl die Aufbewahrung nicht erforderlich ist, da die Aufbewahrungszeiträume, die während der Migration jederzeit erteilt werden, erwartungsgemäß funktionieren sollten, ist eine Aufbewahrungsrichtlinie ein Sicherungsmechanismus für Sicherungen. Gleichzeitig kann eine Aufbewahrungsrichtlinie nicht von allen Kunden verwendet werden, insbesondere von denen, die über die Beibehaltung besorgt sind. | Office-Kunden | Wenden Sie die Aufbewahrungsrichtlinie wie in [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)beschrieben an. |
| [Sicherung der Active Directory Verbunddienste-Farm (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) für Notfallwiederherstellungsszenarien. | Kunden müssen die AD FS-Farm entsprechend sichern, um sicherzustellen, dass die Vertrauensstellungen der vertrauenden Seite globalen & deutschen Endpunkten wiederhergestellt werden können, ohne den Aussteller-URI der Domänen zu berühren. Microsoft empfiehlt, bei Bedarf die schnelle Wiederherstellung von AD FS für eine Sicherung der Farm und der entsprechenden Wiederherstellung zu verwenden. | Organisationen für die Verbundauthentifizierung | Erforderliche Aktion. Wenn die AD FS-Farm des Kunden fehlschlägt, führt dies zu einer Beeinträchtigung des Dienstes während der Migration. |


## <a name="exchange-online"></a>Exchange Online

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Benachrichtigen externer Partner über den bevorstehenden Übergang zu Office 365 Diensten. | Verfügbarkeitsadressraum Konfigurationen ermöglichen die Freigabe von Frei/Gebucht-Informationen mit Office 365. | Exchange Online Kunden, die den Freigabe Kalender und den Adressraum für die Verfügbarkeit aktiviert haben. | Erforderliche Aktion.  Wenn dies nicht der Fall ist, kann dies zu einer späteren Phase der Kundenmigration zu Dienst-oder Client Fehlern führen. |
|||||

Wenn Sie über Hybrid Exchange verfügen:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Deinstallieren Sie frühere Versionen des Assistenten für die Hybrid Konfiguration (HCW), und installieren und führen Sie dann die neueste Version von 17.0.5378.0 aus aus [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | Die neueste Version des HCW enthält notwendige Updates zur Unterstützung von Kunden, die von Microsoft Cloud Deutschland zu Office 365 Diensten wechseln. <br><br> Updates umfassen Änderungen an lokalen Zertifikateinstellungen für Sendeconnector und Empfangsconnector. | Exchange Online Kunden, die eine Hybrid Bereitstellung durchführen | Erforderliche Aktion. Wenn dies nicht der Fall ist, kann dies zu Dienst-oder Client Fehlern führen. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Wenn Sie SharePoint 2013 haben:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Beschränken SharePoint 2013 Workflows, die während der SharePoint Online Migration verwendet werden. | Reduzieren Sie SharePoint 2013 Workflows, und führen Sie in-Flight-Workflows vor dem Übergang aus. | SharePoint Online Kunden | Untätigkeit kann zu Verwirrung bei Benutzern und Helpdesk-anrufen führen. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobile

Wenn Sie eine MDM-Lösung (Mobile Device Management) eines Drittanbieters verwenden:

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | MDM-Lösungen können auf `outlook.de` Endpunkte Zielen. Bei diesem Übergang zu Office 365 Diensten sollten Client Profile auf die URL der Office 365 Dienste aktualisieren `outlook.office365.com` . | Exchange Online-und MDM-Kunden | Clients funktionieren möglicherweise weiterhin, während auf den `outlook.de` Endpunkt zugegriffen werden kann, aber Sie schlagen fehl, wenn Microsoft Cloud Deutschland-Endpunkte nicht mehr verfügbar sind. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>Branchen-apps

Wenn Sie einen Drittanbieter-Service oder Branchen-Apps verwenden, die in Office 365 integriert sind: 

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, ob eine Neukonfiguration nach der Migration erforderlich ist. | Drittanbieterdienste und-Anwendungen, die in Office 365 integriert werden, können so codiert werden, dass Sie Microsoft Cloud Deutschland-IP-Adressen und-URLs erwarten. | Alle Kunden | Erforderliche Aktion. InAktion kann zu Fehlern des Diensts oder der Client Software führen. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Ermitteln Sie, welche Azure-Dienste verwendet werden, und bereiten Sie die zukünftige Migration von Deutschland zum Office 365-Dienste-Mandanten durch Zusammenarbeit mit ihren Partnern vor. Führen Sie die im Textbuch zur [Azure-Migration](https://docs.microsoft.com/azure/germany/germany-migration-main)beschriebenen Schritte aus. | Die Migration von Azure-Ressourcen ist eine Kunden Verantwortung und erfordert nach vorgeschriebenen Schritten manuellen Aufwand. Das Verständnis, welche Dienste in der Organisation verwendet werden, ist der Schlüssel zu einer erfolgreichen Migration von Azure-Diensten. <br><br> Office 365 Deutschland Kunden, die Azure-Abonnements unter derselben Identitäts Partition (Organisation) haben, müssen der von Microsoft vorgeschriebenen Reihenfolge folgen, wenn Sie mit der Migration von Abonnements und Diensten beginnen können. | Azure-Kunden | -Kunden haben möglicherweise mehrere Azure-Abonnements, jedes Abonnement enthält Infrastruktur, Dienste und Plattformkomponenten. <br><br> -Administratoren sollten Abonnements und beteiligte identifizieren, um sicherzustellen, dass eine schnelle Migration und Validierung im Rahmen dieses Migrations Ereignisses möglich ist. <br><br> Wenn die Migration dieser Abonnements und Azure-Komponenten innerhalb der vorgeschriebenen Zeitachse nicht erfolgreich abgeschlossen wurde, wirkt sich dies auf die Fertigstellung des Office-und Azure AD Übergang zu Office 365 Diensten aus und kann zu Datenverlusten führen.  <br><br> -Eine Benachrichtigung im Nachrichtencenter signalisiert den Punkt, an dem die von Kunden geleitete Migration beginnen kann. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Für Dynamics 365-Sandkasten Abonnements müssen Sie unbedingt die Produktionsumgebung der Dynamics SQL-Instanz aus Ihrem Dynamics 365-Abonnement in Microsoft Cloud Deutschland herunterladen. Die neueste Produktionssicherung sollte im Sandkasten vor der Sandkasten Migration wiederhergestellt werden. | Bei der Migration von Dynamics 365 müssen Kunden sicherstellen, dass die Sandbox-Umgebung mit der neuesten Produktionsdatenbank aktualisiert wird. | Microsoft Dynamics-Kunden | Das Team des Teams hilft Kunden bei der Durchführung trockener Abfahrten, um das Versionsupgrade von 8. x auf 9,1. x zu validieren. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Entfernen von Objekten aus Power BI-Abonnements, die nicht von Power BI Microsoft Cloud Deutschland zu Office 365 Diensten migriert werden. | Für die Migration von Power BI-Diensten müssen Kundenaktionen zum Löschen bestimmter Artefakte, wie Datasets und Dashboards, erforderlich sein. | Power BI-Kunden | Administratoren müssen möglicherweise die folgenden Elemente aus Ihrem Abonnement entfernen: <br> -Real-Time Datasets (beispielsweise Streaming oder Push-Datasets) <br> -Power BI lokale Data Gateway-Konfiguration und-Datenquelle |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Überprüfen und Vorbereiten der DNS-Änderung, wenn das aktuelle DNS über einen MSOID-CNAME-Eintrag verfügt. | Änderungen an DNS-Zonen im Kundenbesitz | Office-Clientdienste-Kunden | Aktualisieren Sie die Gültigkeitsdauer (Time to Live, TTL) für kundeneigene DNS-Einträge auf 5 Minuten, wenn ein MSOID-CNAME vorhanden ist. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>Identitätsverbund

| Schritt (e) | Beschreibung | Gilt für | Auswirkung |
|:-------|:-----|:-------|:-------|
| Generieren der Vertrauensstellung der vertrauenden Seite für globale Azure AD Endpunkte. | Kunden müssen manuell eine Vertrauensstellung (rpt) der vertrauenden Seite auf [globale](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) Endpunkte erstellen. Dies erfolgt durch Hinzufügen eines neuen RPT über GUI durch Nutzung der globalen Verbundmetadaten-URL und anschließendes verwenden [Azure AD RPT-Anspruchsregeln](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (in der AD FS-Hilfe), um die Anspruchsregeln zu generieren und in die RPT zu importieren. | Organisationen für die Verbundauthentifizierung | Erforderliche Aktion. Inaktivität führt zu Dienst Beeinträchtigungen während der Migration. |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Migrationsphasen-Aktionen und-Auswirkungen](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Diensten](ms-cloud-germany-transition-add-general.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
