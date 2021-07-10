---
title: Microsoft Managed Desktop-Rollen und Verantwortlichkeiten
description: In diesem Artikel werden die Rollen und Zuständigkeiten beschrieben, die Microsoft für Microsoft Managed Desktop bereitstellt.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7b9efe1a52c108e3de46429d64f9a5535ad13e4e
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362750"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop-Rollen und Verantwortlichkeiten


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Was macht Microsoft für Sie, wenn Ihre Organisation in Microsoft Managed Desktop registriert ist? Und was sind die Zuständigkeiten Ihrer Organisation?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen und Zuständigkeiten von Microsoft

Microsoft stellt die folgenden Schlüsselrollen und Zuständigkeiten bereit:

Rolle oder Verantwortung | Beschreibung
--- | ---
MDM-Richtlinienverwaltung | Microsoft wendet MDM-Richtlinien gemäß den bewährten Methoden an und berücksichtigt Anforderungen für Richtlinienänderungen. Wir nehmen auch Änderungen an Ihrem Mandanten vor, wie in [den Geräterichtlinien](../service-description/device-policies.md)vorgeschrieben.
Benutzerunterstützung | Wir bieten einen Mechanismus für erhöhten Zugriff auf Geräte und für Probleme, die bei Bedarf eskaliert werden. Weitere Informationen finden Sie unter [Benutzerunterstützung.](../service-description/user-support.md)
Microsoft Managed Desktop-Dienstunterstützung | Microsoft unterstützt Ihre IT-Abteilung über ein Microsoft Managed Desktop Operations Team. Dieses Team unterstützt die technische Problembehandlung, Änderungsanforderungen und das Vorfallmanagement für die Microsoft Managed Desktop Umgebung des Kunden. Weitere Informationen finden Sie unter [Administratorunterstützung für Microsoft Managed Desktop.](../working-with-managed-desktop/admin-support.md)
Überwachung der Sicherheit | Microsoft überwacht Ihre Microsoft Managed Desktop Geräte mit Microsoft Defender für Endpunkt. Wenn das Microsoft Managed Desktop Security Operations Center (SOC) eine Bedrohung erkennt, werden wir Sie benachrichtigen, das Gerät isolieren und das Problem remote beheben. Weitere Informationen finden Sie unter ["Sicherheit".](../service-description/security.md)
Updateüberwachung und -verwaltung | Wir überwachen Ihre Microsoft Managed Desktop Geräte aktiv, um sicherzustellen, dass die neuesten Qualitäts- und Funktionsupdates für Microsoft Windows und Microsoft Office installiert sind. Weitere Informationen finden Sie unter [Behandeln von Updates.](../service-description/updates.md)
Benutzer- und Gerätegruppierung | Microsoft Managed Desktop Operations-Team erstellt und verwaltet erforderliche Geräte- und Benutzergruppen im Rahmen von IT-Vorgängen. Für diese Gruppen sind keine Mitgliedschafts- oder Konfigurationsänderungen zulässig. Das Ändern dieser Gruppen kann zu einer unerwarteten Konfiguration von Geräten und zu einem Verlust der Funktionalität führen. Bei Problemen oder Fragen zu diesen Gruppen können SICH IT-Administratoren an Microsoft Managed Desktop Vorgänge wenden. Weitere Informationen finden Sie unter [Administratorunterstützung für Microsoft Managed Desktop.](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>Ihre Rollen und Zuständigkeiten

Dieser Satz allgemeiner Rollen und Zuständigkeiten ist für die Bereitstellung erforderlich, wird jedoch nicht von Microsoft bereitgestellt. Er ist nicht vollständig, gilt aber für die meisten Organisationen. Es gibt einige Elemente, für die Sie und Microsoft gemeinsam verantwortlich sind. 

Rolle oder Verantwortung | Beschreibung
--- | ---
Change Management | Microsoft benachrichtigt Kunden im Voraus, wenn Änderungen an ihrer Microsoft Managed Desktop Umgebung vorgenommen werden müssen. Weitere Informationen finden Sie unter [Dienständerungen und Kommunikation.](../service-description/servicechanges.md)<br><br>Sie müssen über einen eigenen Änderungsverwaltungsprozess verfügen und einen Kontakt mit Microsoft Managed Desktop Operations-Team eingerichtet haben. Sie müssen auch über Ressourcen verfügen, um diese Änderungen zu überprüfen und zu genehmigen. Weitere Informationen finden Sie unter [Vorgänge und Überwachung.](../service-description/operations-and-monitoring.md)  
Identitätsverwaltung | Sie sind dafür verantwortlich, Benutzerkonten zu erstellen, Benutzern Gruppen zuzuweisen und Metadaten auf dem neuesten Stand zu halten. 
Konfiguration und Verwaltung von Microsoft 365 Apps for Enterprise | Microsoft ist dafür verantwortlich, sicherzustellen, Office Anwendungen für Benutzer bereitgestellt werden und diese Anwendungen auf dem neuesten Stand gehalten werden. <br><br> Sie sind für die Verwaltung Microsoft 365 Dienste und Richtlinien verantwortlich, einschließlich Exchange Online Verwaltungsaufgaben:<br>– E-Mail-Verwaltung<br>– Postfach- und Regelkonfiguration<br>– Exchange lokale Verwaltung<br><br>Sie sind auch für Tools für die Zusammenarbeit, SharePoint Serververwaltung, Domänenverwaltung sowie Sicherheits- und Informationsrichtlinien verantwortlich, die im Microsoft 365 Admin Center festgelegt sind. 
Benutzerunterstützung | Bereitstellung des gesamten Benutzersupports und der technischen Unterstützung vom ersten Kontakt bis zur Lösung für den Benutzer, entweder von Ihnen oder über einen bestimmten Supportpartner. Sie müssen entweder direkt Support für Benutzer bereitstellen oder mit einem Partner zusammenarbeiten, um Support für diese Bereiche bereitzustellen: <br><br>– Lokale Infrastruktur: alle Netzwerk- und Internetkonnektivität, VPN-Infrastruktur und Clientkonfiguration, lokale Konferenzraumgeräte, Drucker, Proxyserver und Konfiguration sowie Firewalls.<br><br>– Unternehmensweite Cloudressourcen: E-Mail, SharePoint, Dienste für die Zusammenarbeit und andere Cloudinfrastruktur, die sich auf den unternehmensweiten Technologiebedarf beziehen.<br><br>– Branche und andere unternehmensspezifische Anwendungen.
Apps | Rollen und Zuständigkeiten variieren geringfügig für die Apps, die als Teil der Microsoft Managed Desktop bereitgestellt werden, im Vergleich zu den von Ihnen bereitgestellten Apps. <br><br>Für Apps, die von Microsoft bereitgestellt werden (Microsoft 365 Apps for Enterprise aus Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams und OneNote), stellt **Microsoft** Volldienst für die Bereitstellung, das Update und den Support bereit. **Sie** müssen Lizenzen für diese Apps abrufen und zuweisen, Sicherheitsgruppen Benutzer hinzufügen, das Ende der Lebensdauer verwalten und alle benötigten Add-Ons bereitstellen.<br><br>Für Apps, die Sie bereitstellen (z. B. Ihre Branchen-Apps), unabhängig davon, ob Sie sie selbst verpacken oder einen Nicht-Microsoft-Anbieter dazu beauftragen, sind **Sie** für diese Aktionen verantwortlich: <br><br>– Identifizieren von Anwendungen, die für benutzerorientierte Benutzergruppen erforderlich sind<br>– Erstellen und Verwalten von Azure AD-Gruppen für die App-Bereitstellung<br>– Verpacken von Apps, um Microsoft Intune Bereitstellungsstandards zu erfüllen<br>– Hochladen von Apps auf Microsoft Intune<br>– Testen von Apps in Microsoft Managed Desktop Umgebung<br>– Testen von Apps mit Ihren Benutzern<br>– Verwalten und Zuweisen von Benutzern zu Anwendungen<br>– Identifizieren und Bereitstellen von Anwendungsupdates über Microsoft Intune<br>– Deinstallieren und Entfernen von Anwendungen, wenn sie eingestellt wurden<br>– Beschaffen und Zuweisen von Lizenzen<br>– Bereitstellen von Benutzerunterstützung für Branchen-Apps<br>– Remoteverwaltung von App-Einstellungen<br><br>**Microsoft** stellt Microsoft Intune Bereitstellungstools bereit, um die Anwendungen an Remoteclients bereitzustellen.<br><br>Weitere Informationen finden Sie unter [Apps](../get-ready/apps.md).
Sicherheitsüberwachung und Reaktion | Sie sind dafür verantwortlich, Vorfälle für Geräte zu untersuchen und zu beheben, die nicht Microsoft Managed Desktop Geräte sind, und sicherzustellen, dass das Microsoft Managed Desktop Operations Team über alle Probleme informiert wird, die sich auf den Dienst auswirken können.
Unterstützung von Vorgängen | Sie müssen eine Liste der bevorzugten Kontakte und Fachexperten in Ihrer Organisation bereitstellen. Wir benötigen diese Kontakte, wenn es einen operativen Vorfall gibt, der nicht mit Microsoft Managed Desktop zusammenhängt. <br><br>Sie sind auch dafür verantwortlich, Vorfälle für Geräte und Dienste zu untersuchen und zu beheben, die sich nicht in Microsoft Managed Desktop befinden, und sicherzustellen, dass das Microsoft Managed Desktop Operations Team immer informiert ist.
Netzwerkinfrastruktur, einschließlich VPN | Sie sind für die Einrichtung, Konfiguration und Verwaltung (einschließlich Problembehandlung und Debugging) aller netzwerkbezogenen Infrastruktur und Dienste verantwortlich, einschließlich Internetkonnektivität, Netzwerksteuerelemente, Proxykonfiguration und Remoteverbindungsinfrastruktur.<br><br>Wenn ein Proxy konfiguriert ist (in Hardware oder Software), gibt es eine Sammlung von URLs, die vom Proxy zugelassen werden müssen. Sie sind für die Behandlung von Konflikten oder Inkompatibilitäten aufgrund mehrerer Proxys verantwortlich. Sie können Netzwerkproxys hinzufügen, die für Ihre Organisation spezifisch sind, indem Sie konfigurierbare Einstellungen verwenden. Weitere Informationen finden Sie unter ["Konfigurierbare Einstellungen".](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Weitere Informationen finden Sie unter [Proxykonfiguration.](../get-ready/network.md)
Drucken | Sie sind für die Installation, Wartung und Verwaltung von Druckern und Druckwarteschlangen verantwortlich. Das Drucken in der Cloud ist eine empfohlene Lösung, die jedoch nicht erforderlich ist. 




