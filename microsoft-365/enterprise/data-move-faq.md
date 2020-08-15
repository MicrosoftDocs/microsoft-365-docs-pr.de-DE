---
title: Allgemeine häufig gestellte Fragen zur Datenverschiebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Hier finden Sie Antworten auf häufig gestellte Fragen (FAQs) zum Verschieben von Kern Daten in ein neues Office 365 Datacenter Geo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77d30778ae11865e5d773be4fa64db9b64480e76
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690657"
---
# <a name="data-move-general-faq"></a>Allgemeine häufig gestellte Fragen zur Datenverschiebung

Hier erhalten Sie Antworten auf allgemeine Fragen zum Verschieben von Kerndaten in eine neue geografische Datencenter-Region.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Welche Kunden können eine Verschiebung anfordern?
  
Vorhandene Microsoft 365-kommerzielle Kunden, die ein Land ausgewählt haben, das für das neue Geo-Rechenzentrum berechtigt ist, können eine Verlagerung anfordern.  Das Programm besteht nur für Mandanten mit einem berechtigten Landescode, der dem Microsoft 365-Mandanten zugewiesen ist, um die wichtigsten Kundendaten im Ruhezustand für berechtigte Arbeitsauslastungen an das entsprechende Microsoft 365 Datacenter Geo zu migrieren.  Bitte überprüfen Sie auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md) die Länderberechtigung.   

## <a name="how-do-we-define-core-customer-data"></a>Wie definieren wir Kundenkerndaten?
 
Der Begriff „Kundenkerndaten“ bezieht sich auf eine Teilmenge von Kundendaten, die in den [Nutzungsbedingungen für Microsoft-Onlinedienste](https://aka.ms/ost) definiert sind: 
- Exchange Online-Postfachinhalte (E-Mail-Texte, Kalendereinträge und der Inhalt von E-Mail-Anlagen)
- SharePoint Online-Websiteinhalte und die auf der Website gespeicherten Dateien
- Nach OneDrive for Business hochgeladene Dateien 

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>An welchem Punkt ist meine Migration abgeschlossen, damit die Stammkunden Daten meines Mandanten im Rest in meinem neuen Geo gespeichert werden?

Aufgrund der gegenseitigen Abhängigkeiten zwischen Exchange Online und SharePoint Online/OneDrive for Business kann eine Migration erst dann als abgeschlossen betrachtet werden, wenn beide Dienste migriert wurden.  Exchange Online und SharePoint Online/OneDrive for Business werden häufig zu getrennten Zeiten und unabhängig voneinander migriert.  Mandantenadministratoren erhalten im Nachrichtencenter eine Bestätigung, sobald die einzelnen Dienstmigrationen abgeschlossen sind. Sie können die Datenspeicherort-Karte jederzeit im Admin Center einsehen, um den Standort der ruhenden Kundenkerndaten für jeden Dienst zu überprüfen.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Wie wird sichergestellt, dass meine Kundendaten während des Verschiebens geschützt sind und dass es keine Ausfallzeiten gibt?
  
Bei der Datenverschiebung handelt es sich um Back-End-Vorgänge mit minimalen Auswirkungen auf die Endbenutzer. Eventuell betroffene Funktionen sind in dem Artikel [Während und nach der Datenverschiebung](during-and-after-your-data-move.md) aufgelistet. Wir halten uns an die [Vereinbarung zum Servicelevel für Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=523897) im Hinblick auf die Verfügbarkeit, sodass Kunden nichts für die Verschiebung vorbereiten oder während dieser überwachen müssen. 
  
Alle Microsoft 365-Dienste führen die gleichen Versionen in den Rechenzentren aus, sodass Sie eine konsistente Funktionalität sicherstellen können. Ihr Dienst wird während des gesamten Vorgangs vollständig unterstützt.

## <a name="what-is-in-scope-for-teams-migration"></a>Was ist für die Migration von Microsoft Teams vorgesehen?

Neben Exchange Online, SharePoint Online und OneDrive for Business wird Microsoft Teams-Daten in das lokale Rechenzentrum migrieren.  
- Teams-Chatnachrichten, einschließlich privater Nachrichten und Kanalmeldungen. 
- Bilder, die in Teams-Chats verwendet wurden. 

Teams-Dateien werden in SharePoint Online gespeichert, und Teams-Chatdateien werden in OneDrive for Business gespeichert.  Voicemail, Kalender, Chatverlauf und Kontakte werden in Exchange Online gesichert.  In vielen Fällen werden Exchange Online, SharePoint Online und OneDrive für Unternehmen bereits vom Kunden im lokalen Rechenzentrum Geo verwendet und sind ebenfalls Teil des Microsoft 365-Migrationsprogramms für berechtigte Kunden Länder.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Welche Auswirkungen hat es, wenn sich Dienste an unterschiedlichen geografischen Standorten befinden?

Einige der Microsoft 365-Dienste befinden sich möglicherweise in verschiedenen GEOSS für einige vorhandene Kunden und für Kunden, die sich in der Mitte des Verschiebevorgangs befinden. Unsere Dienste werden unabhängig voneinander ausgeführt, und es gibt keine Auswirkungen auf die Benutzererfahrung, wenn dies der Fall ist.  Allerdings kann eine Mandantenmigration für Datenaufbewahrungszwecke erst nach der Migration von Exchange Online und SharePoint Online/OneDrive for Business in die gleiche Datencenter-Region als abgeschlossen betrachtet werden.
  
## <a name="will-new-microsoft-365-customers-be-automatically-provisioned-in-the-new-datacenter-geos"></a>Werden neue Microsoft 365-Kunden automatisch im neuen Datacenter GEOS eingerichtet?
  
Ja. Sobald ein neues Rechenzentrums-Geo verfügbar ist, werden neue Microsoft 365-Kunden, die bei der Anmeldung ein Land auswählen, das für den neuen geografischen geografischen Standort berechtigt ist, ihre Kernkunden Daten in Rest im neuen Rechenzentrum Geo speichern.
  
 ## <a name="where-is-my-core-customer-data-located"></a>Wo befinden sich meine Hauptkunden Daten?

Mandantenadministratoren können die Datenspeicherort-Karte jederzeit im Admin Center einsehen, um den Standort der ruhenden Kundenkerndaten für jeden Dienst zu überprüfen, insbesondere für den jeweiligen Mandanten.Wir veröffentlichen auch den Speicherort von Datacenter GEOS, Rechenzentren und Speicherort Office 365 Kundendaten auf den [Office 365 interaktiven Datencenter-Karten ](https://office.com/datamaps) als Referenz für die aktuellen Standard-Stammkunden Daten an Rest-Standorten für neue Mandanten.  Im Microsoft 365 Admin Center können Sie den Speicherort Ihrer Kundendaten über den Abschnitt „Datenspeicherort“ unter Ihrem Organisationsprofil überprüfen.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Wann kann ich eine Verschiebung beantragen?
  
Auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md) erfahren Sie mehr über die unterstützten Zeitrahmen für Ihre geografische Datencenter-Region.
  
## <a name="how-can-i-request-to-be-moved"></a>Wie kann ich eine Verschiebung beantragen?
  
Für berechtigte Kunden wird eine Seite in Ihrem [Microsoft 365 Admin Center](https://admin.microsoft.com/)angezeigt. Anweisungen dazu, wie Sie eine Verschiebung beantragen können, finden Sie auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md). 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kann ich meine Auswahl nach der Beantragung einer Verschiebung ändern?
  
Es ist uns nicht möglich, Sie aus dem Prozess zu entfernen, nachdem Sie Ihre Anfrage abgeschickt haben.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Was geschieht, wenn ich nicht vor Ablauf der Frist eine Verschiebung beantrage?
  
Möglicherweise können wir Anfragen ausnahmsweise annehmen, um Ihrem Mandanten einen festgelegten Termin für die Durchführung der Migration zu erteilen. Wenden Sie sich   an den [Microsoft 365-Support](https://go.microsoft.com/fwlink/p/?LinkID=522459) , um die Anforderung zu stellen.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Wie gehe ich vor, wenn ich meine Daten verschieben möchte, um die Netzwerkleistung zu verbessern?
  
Die physische Nähe zu einem Microsoft 365-Rechenzentrum stellt keine Garantie für eine bessere Netzwerkleistung dar. Es gibt viele Faktoren und Komponenten, die sich auf die Netzwerkleistung zwischen dem Endbenutzer und dem Microsoft 365-Dienst auswirken. Weitere Informationen zu diesem Thema und zur Leistungsoptimierung finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Werden die Daten aller Dienste am selben Tag verschoben?
 
Die Daten der Dienste werden unabhängig voneinander und wahrscheinlich auch zu unterschiedlichen Zeiten verschoben.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kann ich angeben, wann meine Daten verschoben werden sollen?
 
Kunden können kein bestimmtes Datum auswählen, sie können die Verschiebung nicht verzögern, und es ist uns nicht möglich, ein bestimmtes Datum oder einen bestimmten Zeitrahmen für die Verschiebungen anzugeben.
  
 ## <a name="can-you-share-when-my-data-will-be-be-moved"></a>Können Sie angeben, wann meine Daten verschoben werden?
  
Bei der Datenverschiebung handelt es sich um Back-End-Vorgänge mit minimalen Auswirkungen für die Endbenutzer. Aufgrund der Komplexität, Präzision und Skalierbarkeit, mit der Datenverschiebungen in einer global betriebenen und automatisierten Umgebung ausgeführt werden müssen, ist es uns unmöglich anzugeben, wann eine Datenverschiebung für Ihren oder einen anderen Mandanten voraussichtlich abgeschlossen sein wird. Kunden erhalten über das Nachrichtencenter eine Bestätigung pro teilnehmendem Dienst, sobald die Verschiebung ihrer Daten abgeschlossen ist. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Was geschieht, wenn Benutzer auf die Dienste zugreifen, während die Daten verschoben werden?

Eine umfassende Liste der Funktionen, die während des Verschiebens von Daten für den jeweiligen Dienst eingeschränkt sein könnten, finden Sie unter [Während und nach der Datenverschiebung](during-and-after-your-data-move.md). 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Wie kann ich feststellen, ob die Verschiebung abgeschlossen ist?
  
Sehen Sie sich das Microsoft 365-Nachrichten Center an, um zu bestätigen, dass die Daten jedes Diensts abgeschlossen sind. Nachdem die Daten eines jeden Diensts verschoben wurden, wird hier eine Abschlussbenachrichtigung veröffentlicht. Sie werden also drei Benachrichtigungen erhalten: jeweils eine für Exchange Online, SharePoint Online und Skype for Business Online.  Sie können den Speicherort Ihrer ruhenden Kundendaten außerdem im Microsoft 365 Admin Center über den Abschnitt „Datenspeicherort“ unter Ihrem Organisationsprofil überprüfen.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Ich bin ein Microsoft 365-Kunde in einem der neuen Datencenter-GEOSS, aber als ich mich angemeldet habe, habe ich ein anderes Land ausgewählt. Wie kann ich in die neue geografische Datencenter-Region wechseln?

Es ist nicht möglich, das Ihrem Mandanten zugeordnete Registrierungsland zu ändern. Stattdessen müssen Sie einen neuen Microsoft 365-Mandanten mit einem neuen Abonnement erstellen und die Benutzer und Daten manuell an den neuen Mandanten verlagern.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Was geschieht, wenn wir während des Exchange Online Umzugs eine e-Mail-Datenmigration zu Microsoft 365 durchführen?

Dies ist ein sehr häufig auftretendes Szenario, das vollständig unterstützt wird.  Die Cloud-Migration zwischen Datencenter-Regionen behindert keine Migrationen von lokalen Postfächern in die Cloud.
  
 ## <a name="can-i-pilot-some-users"></a>Kann ich einen Test mit einigen Benutzern durchführen?
  
Sie können einen separaten Testmandanten erstellen, um die Verbindung zu testen. Der Testmandant kann jedoch nicht mit dem bestehenden Mandanten verbunden werden.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Ich möchte nicht darauf warten, bis Microsoft meine Daten verschoben hat. Kann ich einfach einen Mandanten erstellen und die Verschiebung selbst durchführen?
  
Ja, der Vorgang wird jedoch nicht so übergangslos sein, wie wenn Microsoft die Datenverschiebung durchführt.
  
Wenn Sie nach dem Bereitstellen der neuen geografischen Datencenter-Region einen neuen Mandanten erstellen, wird der neue Mandant in der neuen Region gehostet. Dieser neue Mandant ist vollständig vom vorherigen Mandanten getrennt, und Sie sind dafür verantwortlich, dass alle Benutzerpostfächer, Websiteinhalte, Domänennamen sowie alle anderen Daten verschoben werden. Beachten Sie, dass Sie den Mandantennamen nicht von einem Mandanten auf einen anderen übertragen können. Wir empfehlen, auf das von Microsoft bereitgestellte Verschiebungsprogramm zu warten, da wir dafür sorgen, dass alle Einstellungen, Daten und Abonnements für Ihre Benutzer verschoben werden.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Meine Kundendaten wurden bereits in eine neue Datencenter-Region verschoben. Kann ich sie zurückverschieben?
 
Nein, dies ist nicht möglich. Kundendaten, die an neue geografische Datacenter-Standorte verschoben wurden, können nicht zurückverschoben werden. Kunden jeder geografischen Region erwartet dieselbe Qualität in puncto Service, Leistung und Sicherheitskontrollen wie zuvor.  [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) steht einigen Kunden als Add-on zur Verfügung und ermöglicht einem einzelnen Mandanten das Erstellen von mehreren Satelliten-GEOSS und das Verlegen von Benutzerdaten zu diesen GEOSS mit Daten Wohnsitz Verpflichtungen.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Stehen Microsoft 365-Mandanten, die in den neuen Rechenzentren gehostet werden, für Benutzer außerhalb des Landes zur Verfügung?
  
Ja. Microsoft unterhält ein großes weltweites Netzwerk mit öffentlichen Internetanschlüssen an mehr als 130 Standorten in 35 Ländern weltweit, mit Peering-Abkommen mit mehr als 2.700 Internetdienstanbietern. Benutzer können von überall aus über das Internet auf die Datencenter zugreifen.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mein Mandant hat das [Multi-Geo-Add-on](https://aka.ms/multi-geo)konfiguriert. Kann ich mich noch in meinem Mandanten im Microsoft 365-Programm "migrieren" anmelden, um meine Standard-Geo-Koordinaten zu ändern und alle Benutzer, die sich nicht in einer Satelliten Region befinden, in die neue Standard-Geo-Umgebung zu

Ja, Ihr Mandant ist zur Registrierung berechtigt. Wir werden alle EXO-Postfächer von Ihrer aktuellen geografischen Standardregion in die neue lokale Datencenter-Region verschieben.  In Multi-Geo-Satellitenregionen konfigurierte EXO-Postfächer werden nicht verschoben, um die gewünschte Datenaufbewahrung in Satellitenregionen weiterhin zu respektieren.  

SharePoint Online und OneDrive for Business können nicht im Rahmen des Verschiebungsprogramms in die neue geografische Datencenter-Region migriert werden. Sie können aber OneDrive for Business-Freigaben so konfigurieren, dass sie über das Multi Geo-Programm in eine gewünschte Region übertragen werden.

## <a name="related-topics"></a>Verwandte Themen

[Verschieben der Kern Daten in das neue Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md)

[Anfordern der Datenverschiebung](request-your-data-move.md)

[Microsoft 365 Multi-Geo](https://aka.ms/multi-geo)

[Microsoft 365 Interactive Datacenter-Zuordnung](https://office.com/datamaps)

[Microsoft 365-Support](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Neue Rechenzentrumsregionen für Microsoft Dynamics CRM Live](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-Dienste nach Region](https://azure.microsoft.com/regions/)
