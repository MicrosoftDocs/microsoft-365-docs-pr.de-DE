---
title: Rollen und Verantwortlichkeiten von Microsoft Managed Desktops
description: In diesem Thema werden die Rollen und Verantwortlichkeiten beschrieben, die von Microsoft für Microsoft Managed Desktop bereitgestellt werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9eedd9b6ca9995595c75044b7877ed6eaca21127
ms.sourcegitcommit: b9663acecf0bfdca2486818ec7e08a6f882d0dc9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35425689"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen und Verantwortlichkeiten von Microsoft Managed Desktops


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Was macht Microsoft für Sie, wenn Ihre Organisation in Microsoft Managed Desktop registriert ist? Und was sind die Verantwortlichkeiten Ihrer Organisation?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen und Zuständigkeiten von Microsoft

Im folgenden finden Sie einige wichtige Rollen und Verantwortlichkeiten, die Ihnen von Microsoft bereitgestellt werden.

Rolle oder Verantwortung | Beschreibung
--- | ---
MDM-Richtlinienverwaltung | Microsoft wendet MDM-Richtlinien entsprechend den bewährten Methoden an und prüft die Anforderungen für Richtlinienänderungen. Wir nehmen auch Änderungen an Ihrem Mandanten vor, die in [Geräterichtlinien](../service-description/device-policies.md)vorgeschrieben sind.
Unterstützung für Endbenutzer | Microsoft stellt Endbenutzer Unterstützung für Geräte, Windows und Office-Produktsuite für alle registrierten Benutzer über die Get-Hilfe-App bereit, die auf allen von Microsoft verwalteten Desktop Geräten vorinstalliert ist. 
Unterstützung für den Microsoft Managed Desktop-Dienst | Microsoft unterstützt Kunden-IT-Abteilungen über ein Microsoft Managed Desktop Operations-Team. Dieses Team unterstützt technische Problembehandlung, Änderungsanforderungen und Incident Management für die von Microsoft verwaltete Desktop Umgebung des Kunden. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Sicherheitsüberwachung | Microsoft überwacht Kunden von Microsoft verwaltete Desktop Geräte mit Microsoft Defender ATP. Wenn eine Bedrohung durch das Microsoft Managed Desktop Security Operations Center (SoC) erkannt wird, wird Microsoft den Kunden Benachrichtigen, das Gerät isolieren und das Problem Remote beheben. Weitere Informationen finden Sie unter [Security](../service-description/security.md).
Update Überwachung und-Verwaltung | Microsoft überwacht aktiv die von Microsoft verwalteten Desktop Geräte von Kunden, um sicherzustellen, dass die neuesten Qualitäts-und Funktionsupdates für Microsoft Windows und Microsoft Office installiert sind. Weitere Informationen finden Sie unter [How Updates are Handling](../service-description/updates.md).
Benutzer-und Geräte Gruppierung | Das Microsoft Managed Desktop Operations-Team erstellt und verwaltet die erforderlichen Geräte-und Benutzergruppen im Rahmen des IT-Betriebs. Für diese Gruppen sind keine Mitgliedschafts-oder Konfigurationsänderungen zulässig. Das Ändern dieser Gruppen kann zu einer unerwarteten Konfiguration von Geräten und dem Verlust der Funktionalität führen. Bei Problemen oder Fragen rund um diese Gruppen, die einmal eingerichtet wurden, können IT-Administratoren sich an Microsoft Managed Desktop Operations wenden. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ihre Rollen und Verantwortlichkeiten

Im folgenden finden Sie eine zusätzliche Reihe allgemeiner Rollen und Zuständigkeiten, die nicht von Microsoft bereitgestellt werden, sondern für eine erfolgreiche Bereitstellung erforderlich sind. Er ist nicht erschöpfend, gilt jedoch für die meisten Organisationen. Es gibt ein paar Elemente darunter, die sowohl von Microsoft als auch von den Kunden gemeinsam genutzt werden Verantwortlichkeiten. 

Rolle oder Verantwortung | Beschreibung
--- | ---
Änderungsverwaltung | Microsoft informiert Kunden vorab darüber, wann Änderungen an der von Microsoft verwalteten Desktop Umgebung vorgenommen werden müssen. Der Kunde muss über einen eigenen Änderungsverwaltungsprozess verfügen und einen Kontakt mit dem Microsoft Managed Desktop Operations Team hergestellt haben. Der Kunde muss auch über Ressourcen verfügen, um diese Änderungen zu überprüfen und zu genehmigen. Weitere Informationen finden Sie unter [Vorgänge und Überwachung](../service-description/operations-and-monitoring.md).  
Identitätsverwaltung | Der Kunde ist dafür verantwortlich, Benutzerkonten zu erstellen, Benutzern Gruppen zuzuweisen und die Metadaten auf dem neuesten Stand zu halten. 
Office 365 Konfiguration und-Verwaltung | Microsoft ist dafür verantwortlich sicherzustellen, dass Office-Anwendungen für Endbenutzer bereitgestellt werden und diese Anwendungen auf dem neuesten Stand gehalten werden. <br><br> Der Kunde ist für die Verwaltung von Office 365 Diensten und-Richtlinien verantwortlich, einschließlich Exchange Online Verwaltungszuständigkeiten:<br>-E-Mail-Verwaltung<br>-Mailbox-und Regelkonfiguration<br>-Lokale Exchange-Verwaltung<br><br>Der Kunde ist auch für Tools für die Zusammenarbeit, SharePoint Server-Verwaltung, Domänenverwaltung, Sicherheits-und Informationsrichtlinien, die im Office 365-Verwaltungsportal festgelegt sind, verantwortlich. 
Unterstützung für Endbenutzer | Der Kunde ist für die Bereitstellung von Endbenutzer Unterstützung für Folgendes verantwortlich: <br>-Vor-Ort-Infrastruktur: alle Netzwerk-und Internetkonnektivität, VPN-Infrastruktur und Clientkonfiguration, lokale Konferenzraum Geräte, Drucker, Proxy Server und Konfiguration, Firewalls.<br><br>-Unternehmensweite Cloud-Ressourcen: e-Mail, SharePoint, Zusammenarbeitsdienste und andere Cloud-Infrastrukturen, die sich auf den unternehmensweiten Technologie Fußabdruck beziehen.<br><br>-Branche und alle anderen unternehmensspezifischen Anwendungen.
Apps | Rollen und Verantwortlichkeiten variieren etwas für die apps, die im Rahmen von Microsoft Managed Desktop im Vergleich zu den von Ihnen bereitgestellten bereitgestellt werden. <br><br>Für von Microsoft bereitgestellte Apps (Office 365 ProPlus Standard Suite mit Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams und OneNote) stellt **Microsoft** den vollständigen Dienst für die Bereitstellung, das Update und den Support bereit. **Sie** müssen Lizenzen für diese apps erwerben und zuweisen, Benutzer zu Sicherheitsgruppen hinzufügen und das Ende des Lebens verwalten und alle benötigten Office 365 Addons bereitstellen.<br><br>Für apps, die Sie bereitstellen (beispielsweise Ihre Branchen-Apps), sind **Sie** für diese Aktionen verantwortlich, unabhängig davon, ob Sie diese selbst verpacken oder einen anderen Anbieter als Microsoft engagieren. <br><br>-Identifizieren von Anwendungen, die für bestimmte Benutzergruppen erforderlich sind<br>-Erstellen und Verwalten von Azure Ad Gruppen für die APP-Bereitstellung<br>-Verpacken von apps zur Erfüllung von Microsoft InTune-Bereitstellungsstandards<br>-Hochladen von apps in Microsoft InTune<br>-Testen von apps in der Microsoft Managed Desktop-Umgebung<br>-Testen von apps mit Ihren Endbenutzern<br>-Verwalten und Zuweisen von Benutzern zu Anwendungen<br>-Identifizieren und Bereitstellen von Anwendungsupdates über Microsoft InTune<br>-Deinstallieren und Entfernen von Anwendungen, wenn Sie zurückgezogen wurden<br>-Beschaffung und Zuweisung von Lizenzen<br>-Bereitstellen von Endbenutzer Unterstützung für Branchen-apps<br>-Remoteverwaltung von App-Einstellungen<br><br>**Microsoft** stellt Microsoft InTune-Bereitstellungstools bereit, um die Anwendungen an Remoteclients zu übermitteln.<br><br>Weitere Informationen finden Sie unter [apps](../get-ready/apps.md)
Sicherheitsüberwachung und-Antwort | Der Kunde ist für die Untersuchung und Lösung von Vorfällen für verwaltete Desktop Geräte von Microsoft verantwortlich und stellt sicher, dass das Microsoft Managed Desktop Operations-Team über alle Probleme informiert wird, die sich auf den Dienst auswirken können.
Betriebsunterstützung | Der Kunde ist für die Bereitstellung einer Liste bevorzugter Kundenkontakte und Fachexperten verantwortlich. Microsoft benötigt diese für den Fall, dass ein nicht von Microsoft verwalteter Desktop-Vorfall vorliegt. <br><br>Der Kunde ist außerdem für die Untersuchung und Lösung von Vorfällen für verwaltete Desktop Geräte und-Dienste von nicht-Microsoft verantwortlich und stellt sicher, dass das Microsoft Managed Desktop Operations-Team immer informiert wird.
Netzwerkinfrastruktur, einschließlich VPN | Der Kunde ist für die Einrichtung, Konfiguration und Verwaltung (einschließlich der Problembehandlung und des Debuggings) aller netzwerkbezogenen Infrastrukturen und Dienste verantwortlich, einschließlich Internetkonnektivität, Netzwerk Steuerungen, Proxykonfiguration und Remote Verbindungsinfrastruktur.<br><br>Wenn ein Proxy (in Hardware oder Software) konfiguriert ist, gibt es eine Sammlung von URLs, die vom Proxy zugelassen werden müssen. Der Kunde ist für die Behandlung von Konflikten oder Inkompatibilitäten aufgrund mehrerer Proxys verantwortlich. Sie können mithilfe von konfigurierbaren Einstellungen Netzwerk Proxys hinzufügen, die für Ihre Organisation spezifisch sind. Weitere Informationen finden Sie unter [konfigurierbare Einstellungen](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Weitere Informationen finden Sie unter [Proxy Konfiguration](../get-ready/network.md).
Drucken | Der Kunde ist für die Installation, Wartung und Verwaltung von Druckern und Druckwarteschlangen verantwortlich. Cloud Printing ist eine empfohlene Lösung, ist jedoch nicht erforderlich. 




