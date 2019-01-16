---
title: Microsoft verwalteter Desktop Rollen und Aufgaben
description: In diesem Thema werden die Funktionen und Aufgaben von Microsoft für Microsoft verwalteter Desktop bereitgestellt.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868200"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft verwalteter Desktop Rollen und Aufgaben


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wenn Ihre Organisation Microsoft verwalteter Desktop registriert ist, tun was Microsoft für Sie? Und was sind Ihrer Organisation Zuständigkeiten?

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft Rollen und Aufgaben

Im folgenden sind einige wichtige Rollen und Aufgaben, die Ihnen von Microsoft bereitgestellt werden.

Rolle oder Verantwortung | Beschreibung
--- | ---
MDM Gruppenrichtlinien-Verwaltungskonsole | Microsoft wird Anwenden von MDM Richtlinien nach den bewährten Methoden und Anforderungen für die Richtlinie Änderungen berücksichtigen. Es wird auch Ihres Mandanten wie in [Geräterichtlinien](../service-description/device-policies.md)vorgeschrieben ändern.
Support für Endbenutzer | Microsoft bietet den Endbenutzersupport für Geräte, Windows und Office Produktsuite für alle registrierten Benutzer durch die Hilfe-app, die auf allen Geräten von Microsoft verwalteten Desktops vorinstalliert ist. 
Unterstützung für den Microsoft verwalteten Desktops | Microsoft bietet Unterstützung für Kunden IT Abteilungen über ein Desktop Vorgänge Team von Microsoft verwaltet. Dieses Team wird unterstützen die Problembehandlung bei technischen, Anfragen und Incident Management für die Umgebung des Kunden Microsoft verwalteter Desktop zu ändern. Weitere Informationen finden Sie unter [Unterstützung für Microsoft verwalteter Desktop Admin](../working-with-managed-desktop/admin-support.md).
Überwachen der Sicherheit | Microsoft überwacht Customer Microsoft verwalteter Desktop Geräte mit Windows Defender ATP. Wenn eine Bedrohung erkannt wird, durch die Microsoft verwaltete Desktops Security Operations Center (SOC), Microsoft benachrichtigt der "Kunde", das Gerät zu isolieren und Remote, das Problem zu beheben. Weitere Informationen finden Sie unter [Sicherheit](../service-description/security.md).
Aktualisieren der Überwachung und Verwaltung | Microsoft überwacht aktiv Kunden Microsoft verwalteter Desktop Geräte, um sicherzustellen, dass die neuesten Updates für die Qualität und Feature für Microsoft Windows und Microsoft Office installiert sind. Weitere Informationen finden Sie unter [wie Updates behandelt werden](../service-description/updates.md).
Benutzer und Gerät gruppieren | Microsoft verwalteter Desktop Betriebsteams erstellen und als Teil der IT-Vorgänge erforderlich Gerät und Benutzergruppen verwalten. Es sollte nicht an diese Gruppen ohne Genehmigung von Microsoft verwalteten Desktops Betriebsteams vorgenommenen Änderungen vorhanden sein.

## <a name="your-roles-and-responsibilities"></a>Rollen und Aufgaben

Es folgt eine zusätzliche Reihe von allgemeinen Rollen und Aufgaben, die nicht von Microsoft bereitgestellt werden, aber für eine erfolgreiche Bereitstellung erforderlich sind. Es ist nicht vollständig kann jedoch für die meisten Organisationen. Es gibt einige Elemente unten, Microsoft und der Kunde Responsibilties freigeben. 

Rolle oder Verantwortung | Beschreibung
--- | ---
Änderungsmanagement | Kunden, werden von Microsoft im Voraus benachrichtigt werden, wenn Änderungen für ihre Umgebung Microsoft verwalteter Desktop getroffen werden müssen. Der Kunde ist erforderlich, damit ihre eigenen Änderungsmanagement verarbeiten und einen Kontakt mit Microsoft verwalteten Desktops Operations Team eingerichtet haben. Der Kunde muss auch Ressourcen überprüfen und genehmigen diese Änderungen haben. Weitere Informationen finden Sie unter [Operations und Überwachung](../service-description/operations-and-monitoring.md).  
Identitätsverwaltung | Der Kunde ist verantwortlich für das Erstellen von Benutzerkonten, Zuweisung von Benutzern zu Gruppen und Metadaten auf dem aktuellen Stand zu halten. 
Office 365-Konfiguration und Verwaltung | Microsoft ist dafür verantwortlich, sicherzustellen Bereitstellen einer Office-Anwendung für Endbenutzer und Anwendungen auf dem aktuellen Stand bleiben. <br><br> Der Kunde ist verantwortlich für die Verwaltung von Office 365-Dienste und Richtlinien, einschließlich Exchange Online-Verwaltung Aufgaben:<br>-E-Mail Verwaltung<br>-Mailbox und Regel Konfiguration<br>-Lokale Exchange-Verwaltung<br><br>Der Kunde ist auch für Tools für die Zusammenarbeit, für die SharePoint Server, Domänenmanagement, Sicherheit und Informationen Richtlinien in der Office 365-Verwaltungsportals verantwortlich. 
Support für Endbenutzer | Der Kunde ist verantwortlich für die Bereitstellung von Unterstützung für Endbenutzer: <br>-Klicken Sie auf Website-Infrastruktur: alle Netzwerk und Internet Connectivity, VPN-Infrastruktur und Clientkonfiguration, lokalen Konferenz Raum Equipment, Drucker, Proxyserver und Firewalls-Konfiguration.<br><br>-Unternehmensweite Cloudressourcen: e-Mail, SharePoint, Collaboration-Dienste und andere Cloud-Infrastruktur, die auf der unternehmensweiten Technologie Speicherbedarf bezieht.<br><br>-Zeile der Business und der andere Unternehmen bestimmte Programme.
Apps | Microsoft stellt Bereitstellungsrichtlinien für genehmigten Anwendungen mithilfe von Intune auf Anfrage bereit.<br><br>Der Kunde ist verantwortlich für:<br>-Bereitstellung eine Liste von apps für ihre Organisation (außerhalb von Office 365-apps)<br>-Verwaltung von app Lizenz<br>– Müssen den richtigen Typ und die Anzahl der Lizenzen<br>-App Zuordnung<br>– Apps Azure AD-Benutzergruppen zuweisen<br>-App updates<br>– Überwachung, Packen und Bereitstellen von Feature und app-updates<br>-Benutzer Anwendungstests (Benutzerakzeptanztest)<br>-Bereitstellung einer geeigneten bereitstellbare Paket<br><br>Weitere Informationen finden Sie unter [Apps](../get-ready/apps.md)
Überwachung der Sicherheit und die Antwortzeit | Der Kunde ist verantwortlich für die Untersuchung und Beheben von Vorfälle für nicht - Microsoft verwalteter Desktop-Geräte und sicherstellen, dass das Microsoft verwalteten Desktops Vorgänge Team mögliche Fehler informiert wird, die den Dienst auswirken können.
Unterstützung von Vorgängen | Der Kunde ist verantwortlich für die Bereitstellung einer Liste der bevorzugten Kundenkontakte und Fachleuten. Microsoft benötigt diese für den Fall, dass ein nicht - Microsoft verwalteter Desktop betriebliche Vorfall vorhanden ist. <br><br>Der Kunde ist auch verantwortlich für die Untersuchung und Beheben von Vorfälle für nicht - Microsoft verwalteter Desktop-Geräte und Dienste und sicherstellen, dass das Microsoft verwalteten Desktops Vorgänge Team immer informiert wird.
Netzwerkinfrastruktur, einschließlich VPN | Der Kunde ist verantwortlich für die Installation, Konfiguration und Verwaltung (einschließlich Problembehandlung und Debuggen) aller netzwerkbezogene Infrastruktur und Dienste, einschließlich Internet Connectivity Netzwerk-Steuerelemente, Proxykonfiguration und Remote Konnektivität-Infrastruktur.<br><br>Wenn ein Proxy (in Hardware- oder) konfiguriert ist, ist es eine Auflistung von URLs, die von den Proxy zugelassen werden muss. Der Kunde ist verantwortlich für die Problembehandlung bei Konflikte oder Inkompatibilitäten aufgrund mehrere Proxys.<br><br>Weitere Informationen finden Sie unter [Proxy-Konfiguration](../get-ready/network.md).
Drucken | Der Kunde ist verantwortlich für die Installation, Wartung und Verwaltung von Druckern und print Warteschlangen. Cloud Drucken wird empfohlen, ist jedoch nicht erforderlich. 




