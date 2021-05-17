---
title: Microsoft Managed Desktop-Rollen und Verantwortlichkeiten
description: In diesem Artikel werden die Rollen und Verantwortlichkeiten beschrieben, die von Microsoft für die Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841315"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop-Rollen und Verantwortlichkeiten


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Was macht Microsoft für Sie, wenn Microsoft Managed Desktop registriert ist? Und welche Verantwortung hat Ihre Organisation?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen und Zuständigkeiten von Microsoft

Microsoft stellt die folgenden Schlüsselrollen und Verantwortlichkeiten zur:

Rolle oder Verantwortung | Beschreibung
--- | ---
Verwaltung von MDM-Richtlinien | Microsoft wird MDM-Richtlinien gemäß bewährten Methoden anwenden und Anforderungen für Richtlinienänderungen berücksichtigen. Wir nehmen auch Änderungen an Ihrem Mandanten vor, wie in [Geräterichtlinien vorgeschrieben.](../service-description/device-policies.md)
Benutzerunterstützung | Wir bieten Benutzerunterstützung für Geräte, Windows und die Microsoft 365 Apps for Enterprise-Produktsuite für alle registrierten Benutzer über die Hilfe-App, die auf allen geräten vorinstalliert Microsoft Managed Desktop ist. 
Microsoft Managed Desktop-Serviceunterstützung | Microsoft unterstützt Ihre IT-Abteilung über ein Microsoft Managed Desktop Operations Team. Dieses Team unterstützt die technische Problembehandlung, Änderungsanforderungen und das Vorfallmanagement für die Umgebung Microsoft Managed Desktop Kunden. Weitere Informationen finden Sie unter [Admin Support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Überwachung der Sicherheit | Microsoft überwacht Ihre Microsoft Managed Desktop mit Microsoft Defender for Endpoint. Wenn das Microsoft Managed Desktop Security Operations Center (SOC) eine Bedrohung erkennt, benachrichtigen wir Sie, isolieren das Gerät und beheben das Problem remote. Weitere Informationen finden Sie unter [Security](../service-description/security.md).
Aktualisieren der Überwachung und Verwaltung | Wir überwachen Aktiv Ihre Microsoft Managed Desktop, um sicherzustellen, dass die neuesten Qualitäts- und Featureupdates für Microsoft Windows und Microsoft Office. Weitere Informationen finden Sie unter [How updates are handled](../service-description/updates.md).
Benutzer- und Gerätegruppen | Microsoft Managed Desktop-Betriebsteam erstellt und verwaltet erforderliche Geräte- und Benutzergruppen im Rahmen von IT-Vorgängen. An diesen Gruppen sind keine Mitgliedschafts- oder Konfigurationsänderungen zulässig. Das Ändern dieser Gruppen kann zu unerwarteten Konfigurationen von Geräten und Funktionsverlusten führen. Bei Problemen oder Fragen zu diesen Gruppen können sich IT-Administratoren an die Microsoft Managed Desktop wenden. Weitere Informationen finden Sie unter [Admin Support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ihre Rollen und Verantwortlichkeiten

Dieser Satz gängiger Rollen und Zuständigkeiten ist für die Bereitstellung erforderlich, wird jedoch nicht von Microsoft bereitgestellt. Er ist nicht vollständig, gilt aber für die meisten Organisationen. Es gibt einige Elemente, für die Sie und Microsoft gemeinsam verantwortlich sind. 

Rolle oder Verantwortung | Beschreibung
--- | ---
Change Management | Microsoft benachrichtigt Kunden im Voraus, wenn Änderungen an ihrer Umgebung vorgenommen Microsoft Managed Desktop müssen. Weitere Informationen finden Sie unter [Dienständerungen und Kommunikation](../service-description/servicechanges.md).<br><br>Sie müssen über einen eigenen Änderungsverwaltungsprozess verfügen und einen Kontakt mit dem Microsoft Managed Desktop eingerichtet haben. Sie müssen auch über Ressourcen zum Überprüfen und Genehmigen dieser Änderungen verfügen. Weitere Informationen finden Sie unter [Vorgänge und Überwachung](../service-description/operations-and-monitoring.md).  
Identitätsverwaltung | Sie sind für das Erstellen von Benutzerkonten, das Zuweisen von Benutzern zu Gruppen und das Aktualisieren von Metadaten verantwortlich. 
Microsoft 365 Apps for Enterprise Konfiguration und Verwaltung | Microsoft ist dafür verantwortlich, Office, dass Anwendungen für Benutzer bereitgestellt werden und diese Anwendungen auf dem neuesten Stand gehalten werden. <br><br> Sie sind für die Verwaltung Microsoft 365 und Richtlinien verantwortlich, einschließlich Exchange Online Verwaltungsaufgaben:<br>- E-Mail-Verwaltung<br>- Postfach- und Regelkonfiguration<br>- Exchange lokale Verwaltung<br><br>Sie sind auch für Tools für die Zusammenarbeit, SharePoint Serververwaltung, Domänenverwaltung und Sicherheits- und Informationsrichtlinien verantwortlich, die im Microsoft 365 festgelegt sind. 
Benutzerunterstützung | Sie müssen Benutzerunterstützung für: <br>- Lokale Infrastruktur: alle Netzwerk- und Internetverbindungen, VPN-Infrastruktur und Clientkonfiguration, lokale Konferenzraumgeräte, Drucker, Proxyserver und -konfiguration sowie Firewalls.<br><br>– Unternehmensweite Cloudressourcen: E-Mail, SharePoint, Zusammenarbeitsdienste und andere Cloudinfrastrukturen, die sich auf den unternehmensweiten Technologiebedarf beziehen.<br><br>- Geschäftsbereich und alle anderen unternehmensspezifischen Anwendungen.
Apps | Die Rollen und Verantwortlichkeiten unterscheiden sich für die apps, die im Rahmen der Microsoft Managed Desktop bereitgestellt werden, im Vergleich zu den von Ihnen bereitgestellten Apps. <br><br>Für apps provided by Microsoft (Microsoft 365 Apps for Enterprise comprising Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams, and OneNote), **Microsoft** will provide full service for the deployment, update, and support. **Sie** müssen Lizenzen für diese Apps abrufen und zuweisen, Benutzer zu Sicherheitsgruppen hinzufügen, das Ende der Lebensdauer verwalten und alle benötigten Add-Ons bereitstellen.<br><br>Für apps you provide (such as your line-of-business apps), whether you package them yourself or engage a non-Microsoft vendor to do so, **you** are responsible for these actions: <br><br>– Identifizieren von Anwendungen, die für zielgruppenorientierte Benutzergruppen erforderlich sind<br>– Erstellen und Verwalten von Azure AD-Gruppen für die App-Bereitstellung<br>– Packen von Apps zur Erfüllung Microsoft Intune Bereitstellungsstandards<br>– Hochladen von Apps in Microsoft Intune<br>– Testen von Apps in Microsoft Managed Desktop Umgebung<br>– Testen von Apps mit Ihren Benutzern<br>- Verwalten und Zuweisen von Benutzern zu Anwendungen<br>– Identifizieren und Bereitstellen von Anwendungsupdates Microsoft Intune<br>– Deinstallieren und Entfernen von Anwendungen, wenn sie eingestellt wurden<br>– Beschaffen und Zuweisen von Lizenzen<br>– Bereitstellen von Benutzerunterstützung für Business-Apps<br>– Remoteverwaltung von App-Einstellungen<br><br>**Microsoft** stellt Microsoft Intune Bereitstellungstools bereit, um die Anwendungen an Remoteclients zu liefern.<br><br>Weitere Informationen finden Sie unter [Apps](../get-ready/apps.md).
Sicherheitsüberwachung und Reaktion | Sie sind dafür verantwortlich, Vorfälle für Geräte zu untersuchen und zu beheben, die nicht Microsoft Managed Desktop Geräten sind, und sicherzustellen, dass das Microsoft Managed Desktop Operations Team über alle Probleme informiert wird, die sich auf den Dienst auswirken können.
Betriebsunterstützung | Sie müssen eine Liste der bevorzugten Kontakte und Experten für Themen in Ihrer Organisation bereitstellen. Wir benötigen diese Kontakte, wenn es einen betriebsbedingten Vorfall gibt, der nichts mit der Microsoft Managed Desktop. <br><br>Sie sind auch für die Untersuchung und Lösung von Vorfällen für Geräte und Dienste verantwortlich, die sich nicht in Microsoft Managed Desktop befinden, und sicherstellen, dass das Microsoft Managed Desktop Operations Team immer informiert ist.
Netzwerkinfrastruktur, einschließlich VPN | Sie sind für die Einrichtung, Konfiguration und Verwaltung (einschließlich Problembehandlung und Debuggen) aller netzwerkbezogenen Infrastruktur und Dienste verantwortlich, einschließlich Internetverbindung, Netzwerksteuerelemente, Proxykonfiguration und Remoteverbindungsinfrastruktur.<br><br>Wenn ein Proxy konfiguriert ist (in Hardware oder Software), gibt es eine Auflistung von URLs, die vom Proxy zulässig sein müssen. Sie sind für die Problembehandlung von Konflikten oder Inkompatibilitäten aufgrund mehrerer Proxys verantwortlich. Sie können netzwerkspezifische Proxys für Ihre Organisation mithilfe konfigurierbarer Einstellungen hinzufügen. Weitere Informationen finden Sie unter [Konfigurierbare Einstellungen](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Weitere Informationen finden Sie unter [Proxykonfiguration](../get-ready/network.md).
Drucken | Sie sind für die Installation, Wartung und Verwaltung von Druckern und Druckwarteschlangen verantwortlich. Clouddruck ist eine empfohlene Lösung, ist jedoch nicht erforderlich. 




