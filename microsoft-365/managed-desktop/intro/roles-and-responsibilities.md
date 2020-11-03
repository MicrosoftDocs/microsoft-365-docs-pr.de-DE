---
title: Microsoft Managed Desktop-Rollen und Verantwortlichkeiten
description: In diesem Artikel werden die Rollen und Verantwortlichkeiten von Microsoft für Microsoft Managed Desktop beschrieben.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: de0bc092c35c7f48c562da8d4218f7a638abe1d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847780"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop-Rollen und Verantwortlichkeiten


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Was macht Microsoft für Sie, wenn Ihre Organisation in Microsoft Managed Desktop registriert ist? Und was sind die Verantwortlichkeiten Ihrer Organisation?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen und Zuständigkeiten von Microsoft

Microsoft stellt diese wichtigen Rollen und Zuständigkeiten bereit:

Rolle oder Verantwortung | Beschreibung
--- | ---
MDM-Richtlinienverwaltung | Microsoft wendet MDM-Richtlinien entsprechend den bewährten Methoden an und prüft die Anforderungen für Richtlinienänderungen. Wir nehmen auch Änderungen an Ihrem Mandanten vor, wie in [Geräterichtlinien](../service-description/device-policies.md)vorgeschrieben.
Benutzerunterstützung | Wir bieten Benutzerunterstützung für Geräte, Windows und die Microsoft 365 apps for Enterprise-Produktsuite für alle registrierten Benutzer über die Get-Hilfe-APP, die auf allen von Microsoft verwalteten Desktop Geräten vorinstalliert ist. 
Unterstützung für den Microsoft Managed Desktop-Dienst | Microsoft bietet Unterstützung für Ihre IT-Abteilung über ein Microsoft Managed Desktop Operations-Team. Dieses Team unterstützt technische Problembehandlung, Änderungsanforderungen und Incident Management für die von Microsoft verwaltete Desktop Umgebung des Kunden. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Sicherheitsüberwachung | Microsoft überwacht Ihre verwalteten Desktop Geräte von Microsoft mit Microsoft Defender für Endpoint. Wenn das Microsoft Managed Desktop Security Operations Center (SoC) eine Bedrohung erkennt, werden wir Sie benachrichtigen, das Gerät isolieren und das Problem Remote beheben. Weitere Informationen finden Sie unter [Security](../service-description/security.md).
Update Überwachung und-Verwaltung | Wir überwachen aktiv ihre von Microsoft verwalteten Desktop Geräte, um sicherzustellen, dass die neuesten Qualitäts-und Funktionsupdates für Microsoft Windows und Microsoft Office installiert sind. Weitere Informationen finden Sie unter [How Updates are Handling](../service-description/updates.md).
Benutzer-und Geräte Gruppierung | Das Microsoft Managed Desktop Operations-Team erstellt und verwaltet die erforderlichen Geräte-und Benutzergruppen im Rahmen des IT-Betriebs. Für diese Gruppen sind keine Mitgliedschafts-oder Konfigurationsänderungen zulässig. Das Ändern dieser Gruppen kann zu einer unerwarteten Konfiguration von Geräten und dem Verlust der Funktionalität führen. Bei Problemen oder Fragen rund um diese Gruppen, die einmal eingerichtet wurden, können IT-Administratoren sich an Microsoft Managed Desktop Operations wenden. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ihre Rollen und Verantwortlichkeiten

Diese zusätzlichen allgemeinen Rollen und Zuständigkeiten sind für die Bereitstellung erforderlich, werden jedoch nicht von Microsoft bereitgestellt. Er ist nicht erschöpfend, gilt jedoch für die meisten Organisationen. Es gibt einige Elemente, für die Sie und Microsoft verantwortlich sind. 

Rolle oder Verantwortung | Beschreibung
--- | ---
Change Management | Microsoft informiert Kunden vorab darüber, wann Änderungen an der von Microsoft verwalteten Desktop Umgebung vorgenommen werden müssen. Weitere Informationen finden Sie unter [Dienständerungen und Kommunikation](../service-description/servicechanges.md).<br><br>Sie müssen über einen eigenen Änderungsverwaltungsprozess verfügen und einen Kontakt mit dem Microsoft Managed Desktop Operations-Team hergestellt haben. Sie müssen auch über Ressourcen verfügen, um diese Änderungen zu überprüfen und zu genehmigen. Weitere Informationen finden Sie unter [Vorgänge und Überwachung](../service-description/operations-and-monitoring.md).  
Identitätsverwaltung | Sie sind für das Erstellen von Benutzerkonten, das Zuweisen von Benutzern zu Gruppen und das Aktualisieren der Metadaten verantwortlich. 
Microsoft 365-Apps für Unternehmenskonfiguration und-Verwaltung | Microsoft ist dafür verantwortlich sicherzustellen, dass Office-Anwendungen für Benutzer bereitgestellt werden und diese Anwendungen auf dem neuesten Stand gehalten werden. <br><br> Sie sind für die Verwaltung von Microsoft 365-Diensten und-Richtlinien verantwortlich, einschließlich Exchange Online Verwaltungszuständigkeiten:<br>-E-Mail-Verwaltung<br>-Mailbox-und Regelkonfiguration<br>-Lokale Exchange-Verwaltung<br><br>Sie sind auch für Tools für die Zusammenarbeit, SharePoint Server-Verwaltung, Domänenverwaltung und Sicherheits-und Informationsrichtlinien zuständig, die im Microsoft 365 Admin Center festgelegt sind. 
Benutzerunterstützung | Sie müssen die Benutzerunterstützung für Folgendes bereitstellen: <br>-Vor-Ort-Infrastruktur: gesamte Netzwerk-und Internetkonnektivität, VPN-Infrastruktur und Clientkonfiguration, lokale Konferenzraum Geräte, Drucker, Proxy Server und-Konfiguration sowie Firewalls.<br><br>-Unternehmensweite Cloud-Ressourcen: e-Mail, SharePoint, Zusammenarbeitsdienste und andere Cloud-Infrastrukturen, die sich auf den unternehmensweiten Technologie Fußabdruck beziehen.<br><br>-Branche und alle anderen unternehmensspezifischen Anwendungen.
Apps | Rollen und Verantwortlichkeiten variieren etwas für die apps, die im Rahmen von Microsoft Managed Desktop im Vergleich zu den von Ihnen bereitgestellten apps bereitgestellt werden. <br><br>Für von Microsoft bereitgestellte Apps (Microsoft 365 apps for Enterprise, bestehend aus Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams und OneNote) stellt **Microsoft** den vollständigen Dienst für die Bereitstellung, das Update und den Support bereit. **Sie** müssen Lizenzen für diese apps erwerben und zuweisen, Benutzer zu Sicherheitsgruppen hinzufügen und das Ende der Lebensdauer verwalten und alle Add-ons bereitstellen, die Sie benötigen.<br><br>Für apps, die Sie bereitstellen (beispielsweise Ihre Branchen-Apps), sind **Sie** für diese Aktionen verantwortlich, unabhängig davon, ob Sie diese selbst verpacken oder einen anderen Anbieter als Microsoft engagieren. <br><br>-Identifizieren von Anwendungen, die für bestimmte Benutzergruppen erforderlich sind<br>-Erstellen und Verwalten von Azure Ad Gruppen für die APP-Bereitstellung<br>-Verpacken von apps zur Erfüllung von Microsoft InTune-Bereitstellungsstandards<br>-Hochladen von apps in Microsoft InTune<br>-Testen von apps in der Microsoft Managed Desktop-Umgebung<br>-Testen von apps mit ihren Benutzern<br>-Verwalten und Zuweisen von Benutzern zu Anwendungen<br>-Identifizieren und Bereitstellen von Anwendungsupdates über Microsoft InTune<br>-Deinstallieren und Entfernen von Anwendungen, wenn Sie zurückgezogen wurden<br>-Beschaffung und Zuweisung von Lizenzen<br>-Bereitstellen von Benutzerunterstützung für Branchen-apps<br>-Remoteverwaltung von App-Einstellungen<br><br>**Microsoft** stellt Microsoft InTune-Bereitstellungstools bereit, um die Anwendungen an Remoteclients zu übermitteln.<br><br>Weitere Informationen finden Sie unter [apps](../get-ready/apps.md).
Sicherheitsüberwachung und Reaktion | Sie sind für das untersuchen und Beheben von Vorfällen für Geräte zuständig, bei denen es sich nicht um von Microsoft verwaltete Desktop Geräte handelt, und sicherstellen, dass das Microsoft Managed Desktop Operations-Team über alle Probleme informiert wird, die sich auf den Dienst auswirken können.
Betriebsunterstützung | Sie müssen eine Liste der bevorzugten Kontakte und Fachexperten in Ihrer Organisation bereitstellen. Wir benötigen diese im Fall eines betriebsbedingten Vorfalls, der nicht mit dem von Microsoft verwalteten Desktop verbunden ist. <br><br>Außerdem sind Sie für die Untersuchung und Lösung von Vorfällen für Geräte und Dienste zuständig, die sich nicht in Microsoft Managed Desktop befinden, und sicherstellen, dass das Microsoft Managed Desktop Operations-Team immer informiert wird.
Netzwerkinfrastruktur, einschließlich VPN | Sie sind für die Einrichtung, Konfiguration und Verwaltung (einschließlich der Problembehandlung und des Debuggings) aller netzwerkbezogenen Infrastrukturen und Dienste, einschließlich Internetkonnektivität, Netzwerk Steuerelemente, Proxykonfiguration und Remote Verbindungsinfrastruktur, verantwortlich.<br><br>Wenn ein Proxy (in Hardware oder Software) konfiguriert ist, gibt es eine Sammlung von URLs, die vom Proxy zugelassen werden müssen. Sie sind für die Problembehandlung von Konflikten oder Inkompatibilitäten aufgrund mehrerer Proxys verantwortlich. Sie können mithilfe von konfigurierbaren Einstellungen Netzwerk Proxys hinzufügen, die für Ihre Organisation spezifisch sind. Weitere Informationen finden Sie unter [konfigurierbare Einstellungen](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Weitere Informationen finden Sie unter [Proxy Konfiguration](../get-ready/network.md).
Drucken | Sie sind für die Installation, Wartung und Verwaltung von Druckern und Druckwarteschlangen verantwortlich. Cloud Printing ist eine empfohlene Lösung, ist jedoch nicht erforderlich. 




