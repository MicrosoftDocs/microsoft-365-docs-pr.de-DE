---
title: Allgemeine häufig gestellte Fragen zur Datenverschiebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Hier finden Sie Antworten auf häufig gestellte Fragen (FAQ) zum Verschieben von Kerndaten in einen neuen geografischen Raum des Office 365-Rechenzentrums.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e66c9f29b47c3f1bc8d6e89ebf2f077eee9f4adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919128"
---
# <a name="data-move-general-faq"></a>Allgemeine häufig gestellte Fragen zur Datenverschiebung

Hier finden Sie Antworten auf allgemeine Fragen zum Verschieben von Kernkundendaten im Ruhebereich in ein neues Geografisches Datencenter.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Welche Kunden können eine Verschiebung anfordern?
  
Bestehende Microsoft 365-Gewerbekunden, die ein mit dem neuen geografischen Raum des Rechenzentrums vereinbares Land ausgewählt haben, können eine Verschiebung anfordern. Das Programm gilt nur für Mandanten mit einem berechtigten Ländercode, der dem Microsoft 365-Mandanten zugeordnet ist, für die Migration ruhender Kundenkerndaten für berechtigte Arbeitslasten zum entsprechenden geografischen Raum des Office 365-Rechenzentrums. Bitte überprüfen Sie auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md) die Länderberechtigung.   

## <a name="how-do-we-define-core-customer-data"></a>Wie definieren wir Kundenkerndaten?
 
Der Begriff „Kundenkerndaten“ bezieht sich auf eine Teilmenge von Kundendaten, die in den [Nutzungsbedingungen für Microsoft-Onlinedienste](https://aka.ms/ost) definiert sind: 
- Exchange Online-Postfachinhalte (E-Mail-Texte, Kalendereinträge und der Inhalt von E-Mail-Anlagen)
- SharePoint Online-Websiteinhalte und die auf der Website gespeicherten Dateien
- Nach OneDrive for Business hochgeladene Dateien 

## <a name="what-is-in-scope-for-teams-migration"></a>Was ist für die Migration von Microsoft Teams vorgesehen?

Neben Exchange Online, SharePoint Online und OneDrive for Business wird Microsoft Teams-Daten in das lokale Rechenzentrum migrieren. 
- Teams-Chatnachrichten, einschließlich privater Nachrichten und Kanalmeldungen. 
- Bilder, die in Teams-Chats verwendet wurden. 

Teams-Dateien werden in SharePoint Online gespeichert, und Teams-Chatdateien werden in OneDrive for Business gespeichert. Voicemail, Kalender und Kontakte werden in Exchange Online gespeichert. In vielen Fällen werden Exchange Online, SharePoint Online und OneDrive for Business bereits vom Kunden im geografischen Lokalen Rechenzentrum verwendet und sind auch Teil des Microsoft 365-Migrationsprogramms für berechtigte Kundenländer.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Wann ist meine Migration abgeschlossen, sodass die Kundenkerndaten meines Mandanten im neuen geografischen Raum im Ruhezustand gespeichert sind?

Aufgrund der gegenseitigen Abhängigkeiten zwischen Exchange Online und SharePoint Online/OneDrive for Business kann eine Migration erst dann als abgeschlossen betrachtet werden, wenn beide Dienste migriert wurden. Exchange Online und SharePoint Online/OneDrive for Business werden häufig zu getrennten Zeiten und unabhängig voneinander migriert. Kunden-Mandantenadministratoren erhalten eine Bestätigung im Message Center, wenn jede Dienstmigration abgeschlossen ist, und können die Datenspeicherortkarte jederzeit im Admin Center anzeigen, um die Wichtigsten Kundendaten am Ruhespeicherort für jeden Dienst zu bestätigen.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Wie wird sichergestellt, dass meine Kundendaten während des Verschiebens geschützt sind und dass es keine Ausfallzeiten gibt?
  
Datenbewegungen sind ein Back-End-Dienstvorgang mit minimalen Auswirkungen auf Endbenutzer. Eventuell betroffene Funktionen sind in dem Artikel [Während und nach der Datenverschiebung](during-and-after-your-data-move.md) aufgelistet. Wir halten uns an die [Vereinbarung zum Servicelevel für Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=523897) im Hinblick auf die Verfügbarkeit, sodass Kunden nichts für die Verschiebung vorbereiten oder während dieser überwachen müssen. 
  
Alle Microsoft 365-Dienste führen die gleichen Versionen in den Rechenzentren aus, sodass Sie sich auf gleichbleibende Funktionalität verlassen können. Ihr Dienst wird während des gesamten Vorgangs vollständig unterstützt.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Welche Auswirkungen hat es, wenn sich Dienste in unterschiedlichen geografischen Räumen befinden?

Einige der Microsoft 365-Dienste befinden sich möglicherweise in unterschiedlichen geografischen Räumen für einige bestehende Kunden sowie für Kunden, die sich mitten im Verschiebeprozess befinden. Unsere Dienste werden unabhängig voneinander ausgeführt, somit gibt es in einem solchen Fall keinerlei Auswirkungen auf die Benutzererfahrung.   Allerdings kann eine Mandantenmigration für Datenaufbewahrungszwecke erst nach der Migration von Exchange Online und SharePoint Online/OneDrive for Business in die gleiche Datencenter-Region als abgeschlossen betrachtet werden.

 ## <a name="where-is-my-core-customer-data-located"></a>Wo befinden sich meine Kundenkerndaten?

Kunden-Mandantenadministratoren können die Datenspeicherortkarte jederzeit im Admin Center anzeigen, um die wichtigsten Kundendaten am Ruhespeicherort für jeden Dienst, insbesondere für seinen Mandanten, zu bestätigen.  Außerdem veröffentlichen wir den Standort von Geos, Rechenzentren und Standort von Office 365-Kundendaten auf den [interaktiven Microsoft 365-Datencenterzuordnungen ](https://office.com/datamaps) als Referenz für die aktuellen Standardkundendaten an Ruhespeicherorten für neue Mandanten. Sie können den Speicherort Ihrer Kundendaten im Ruhebereich über den Abschnitt Datenspeicherort unter Ihrem Organisationsprofil im Microsoft 365 Admin Center überprüfen.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Wann kann ich eine Verschiebung beantragen?
  
Auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md) erfahren Sie mehr über die unterstützten Zeitrahmen für Ihre geografische Datencenter-Region.
  
## <a name="how-can-i-request-to-be-moved"></a>Wie kann ich eine Verschiebung beantragen?
  
Dazu berechtigten Kunden wird in ihrem [Microsoft 365 Admin Center](https://admin.microsoft.com/) eine entsprechende Seite angezeigt. Anweisungen dazu, wie Sie eine Verschiebung beantragen können, finden Sie auf der Seite [Anfordern der Datenverschiebung](request-your-data-move.md). 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kann ich meine Auswahl nach der Beantragung einer Verschiebung ändern?
  
Es ist uns nicht möglich, Sie aus dem Prozess zu entfernen, nachdem Sie Ihre Anfrage abgeschickt haben.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Was geschieht, wenn ich nicht vor Ablauf der Frist eine Verschiebung beantrage?
  
Wir können keine Migrationsanforderungen nach dem offenen Registrierungszeitraum annehmen.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Wie gehe ich vor, wenn ich meine Daten verschieben möchte, um die Netzwerkleistung zu verbessern?
  
Physische Nähe zu einem Microsoft 365-Datencenter stellt keine Garantie für eine bessere Netzwerkleistung dar. Es gibt viele Faktoren und Komponenten, die sich auf die Netzwerkleistung zwischen dem Endbenutzer und dem Microsoft 365-Dienst auswirken. Weitere Informationen zu diesem Thema und zur Leistungsoptimierung finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Werden die Daten aller Dienste am selben Tag verschoben?
 
Die Daten der Dienste werden unabhängig voneinander und wahrscheinlich auch zu unterschiedlichen Zeiten verschoben.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kann ich angeben, wann meine Daten verschoben werden sollen?
 
Kunden können kein bestimmtes Datum auswählen, sie können die Verschiebung nicht verzögern, und es ist uns nicht möglich, ein bestimmtes Datum oder einen bestimmten Zeitrahmen für die Verschiebungen anzugeben.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Können Sie freigeben, wann meine Daten verschoben werden?
  
Datenbewegungen sind ein Back-End-Vorgang mit minimalen Auswirkungen auf Endbenutzer. Die Komplexität, Genauigkeit und Skalierung, mit der wir Datenbewegungen in einer global betriebenen und automatisierten Umgebung durchführen müssen, verbieten uns die Freigabe, wenn erwartet wird, dass eine Datenbewegung für Ihren Mandanten oder einen anderen einzelnen Mandanten abgeschlossen wird. Kunden erhalten über das Nachrichtencenter eine Bestätigung pro teilnehmendem Dienst, sobald die Verschiebung ihrer Daten abgeschlossen ist. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Was geschieht, wenn Benutzer auf die Dienste zugreifen, während die Daten verschoben werden?

Eine umfassende Liste der Funktionen, die während des Verschiebens von Daten für den jeweiligen Dienst eingeschränkt sein könnten, finden Sie unter [Während und nach der Datenverschiebung](during-and-after-your-data-move.md). 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Wie kann ich feststellen, ob die Verschiebung abgeschlossen ist?
  
Sie können im Microsoft 365-Nachrichtencenter überprüfen, ob das Verschieben der Daten der einzelnen Dienste abgeschlossen ist. Nachdem die Daten eines jeden Diensts verschoben wurden, wird hier eine Abschlussbenachrichtigung veröffentlicht. Sie werden also drei Benachrichtigungen erhalten: jeweils eine für Exchange Online, SharePoint Online und Skype for Business Online. Sie können den Speicherort Ihrer Ruhedaten auch über den Abschnitt Datenspeicherort unter Ihrem Organisationsprofil im Microsoft 365 Admin Center überprüfen.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Ich bin ein Microsoft 365-Kunde in einem der neuen geografischen Räume des Rechenzentrums, habe aber während der Registrierung ein anderes Land ausgewählt. Wie kann ich in die neue geografische Datencenter-Region wechseln?

Es ist nicht möglich, das Ihrem Mandanten zugeordnete Registrierungsland zu ändern. Stattdessen müssen Sie einen neuen Microsoft 365-Mandanten mit einem neuen Abonnement erstellen, und Ihre Benutzer und Daten manuell in den neuen Mandanten übertragen.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Was geschieht, wenn die E-Mail-Datenmigration zu Microsoft 365 während der Exchange Online-Verschiebung durchgeführt wird?

Dies ist ein sehr häufig auftretendes Szenario, das vollständig unterstützt wird.  Die Cloudmigration zwischen Geografischen Datencentern wirkt sich nicht auf lokale Migrationen zu Cloudpostfächern aus.
  
 ## <a name="can-i-pilot-some-users"></a>Kann ich einen Test mit einigen Benutzern durchführen?
  
Sie können einen separaten Testmandanten erstellen, um die Verbindung zu testen. Der Testmandant kann jedoch nicht mit dem bestehenden Mandanten verbunden werden.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Ich möchte nicht darauf warten, bis Microsoft meine Daten verschoben hat. Kann ich einfach einen Mandanten erstellen und die Verschiebung selbst durchführen?
  
Ja, der Vorgang wird jedoch nicht so übergangslos sein, wie wenn Microsoft die Datenverschiebung durchführt.
  
Wenn Sie nach dem Bereitstellen der neuen geografischen Datencenter-Region einen neuen Mandanten erstellen, wird der neue Mandant in der neuen Region gehostet. Dieser neue Mandant ist vollständig vom vorherigen Mandanten getrennt, und Sie sind dafür verantwortlich, dass alle Benutzerpostfächer, Websiteinhalte, Domänennamen sowie alle anderen Daten verschoben werden. Beachten Sie, dass Sie den Mandantennamen nicht von einem Mandanten auf einen anderen übertragen können. Wir empfehlen, auf das von Microsoft bereitgestellte Verschiebungsprogramm zu warten, da wir dafür sorgen, dass alle Einstellungen, Daten und Abonnements für Ihre Benutzer verschoben werden.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Meine Kundendaten wurden bereits in eine neue Datencenter-Region verschoben. Kann ich sie zurückverschieben?
 
Nein, dies ist nicht möglich. Kundendaten, die an neue geografische Datacenter-Standorte verschoben wurden, können nicht zurückverschoben werden. Kunden jeder geografischen Region erwartet dieselbe Qualität in puncto Service, Leistung und Sicherheitskontrollen wie zuvor. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) ist für einige Kunden als Add-on verfügbar und ermöglicht es einem einzelnen Mandanten, mehrere geografische Satelliten-Räume zu erstellen und Benutzerdaten in diese Räume zu übertragen.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Werden in den neuen Datencentern gehostete Microsoft 365-Mandanten auch für Benutzer außerhalb des Landes verfügbar sein?
  
Ja. Microsoft unterhält ein großes weltweites Netzwerk mit öffentlichen Internetanschlüssen an mehr als 130 Standorten in 35 Ländern weltweit, mit Peering-Abkommen mit mehr als 2.700 Internetdienstanbietern. Benutzer können von überall aus über das Internet auf die Datencenter zugreifen.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mein Mandant hat das [Multi Geo-Add-On](https://aka.ms/multi-geo)konfiguriert. Kann ich mich in meinem Mandanten weiterhin für das Microsoft 365-Verschiebungsprogramm registrieren, um meine geografischen Standardeinstellung zu ändern und Benutzer, die sich nicht in einer Satellitenregion befinden, in den neuen standardmäßigen geografischen Raum verschieben?

Ja, Ihr Mandant kann sich registrieren, aber es gibt wichtige Überlegungen, da die Mandantenverlegung für Kunden, die Multi-Geo konfiguriert haben, nicht vollständig unterstützt wird.

SharePoint Online und OneDrive for Business können über dieses Programm nicht zum neuen Geocenter auf Mandantenebene migriert werden. Der Kundenadministrator kann OneDrive for #A0 so konfigurieren, dass sie mithilfe von Multi-Geo in eine beliebige verfügbare Region wechseln. Der Standardspeicherort für den Mandanten kann jedoch nicht geändert werden, nachdem Multi-Geo für einen Mandanten konfiguriert wurde.

Für Kunden, die sich für die Migration entscheiden, verschieben wir alle Exchange Online-Postfächer aus Ihrem aktuellen Standard-Geo in Ihr neues lokales Rechenzentrum und aktualisieren die Standardregion Exchange Online. In Multi-Geo-Satellitenregionen konfigurierte EXO-Postfächer werden nicht verschoben, um die gewünschte Datenaufbewahrung in Satellitenregionen weiterhin zu respektieren. 

## <a name="related-topics"></a>Verwandte Themen

[Verschieben von Kundenkerndaten in neue geografische Räume des Microsoft 365-Rechenzentrums](moving-data-to-new-datacenter-geos.md)

[Anfordern der Datenverschiebung](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Interaktive Microsoft 365 Rechenzentrumskarte](https://office.com/datamaps)

[Microsoft 365 Support](../admin/contact-support-for-business-products.md)

[Neue Rechenzentrumsregionen für Microsoft Dynamics CRM Live](/power-platform/admin/new-datacenter-regions)
  
[Azure-Dienste nach Region](https://azure.microsoft.com/regions/)