---
title: Netzwerk- und Migrationsplanung für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Dieser Artikel enthält Links zu Informationen zu Netzwerkplanung, Tests und Migration zu Office 365.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923588"
---
# <a name="network-and-migration-planning-for-office-365"></a>Netzwerk- und Migrationsplanung für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Dieser Artikel enthält Links zu Informationen zur Netzwerkplanung und -tests sowie zur Migration zu Office 365.
  
Bevor Sie zum ersten Mal bereitstellen oder zu Office 365 migrieren, können Sie die Informationen in diesen Themen verwenden, um die erforderliche Bandbreite zu schätzen und dann zu testen und zu überprüfen, ob Sie über genügend Bandbreite zum Bereitstellen oder Migrieren zu Office 365.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)

Die Schritte zur Optimierung Ihres Netzwerks für Microsoft 365 und andere [Microsoft-Cloudplattformen](../solutions/cloud-architecture-models.md) und -Dienste finden Sie im Poster Microsoft Cloud Networking for Enterprise Architects.
   
## <a name="estimate-network-bandwidth-requirements"></a>Schätzen der Netzwerkbandbreitenanforderungen
<a name="EstimateBandwidthRequirements"> </a>

Die Office 365 kann die Nutzung der Internetschaltung Ihrer Organisation erhöhen. Es ist wichtig zu ermitteln, ob die derzeit verfügbare Bandbreite ausreicht, um den geschätzten Anstieg zu bewältigen, sobald Office 365 vollständig bereitgestellt ist, während mindestens 20 % Kapazität zur Verarbeitung der auslastungsreichsten Tage zur Verfügung stehen.
  
Gehen Sie wie folgt vor, um die Bandbreite zu schätzen:
  
1. Bewerten Sie die Anzahl der Clients, die jeden Internet-Egress verwenden. Lassen Sie unser Multi-Terabit-Netzwerk so viele Verbindungen wie möglich verarbeiten. 
    
2. Bestimmen Sie, Office 365 Dienste und Features für Clients zur Verfügung stehen. Wahrscheinlich verfügen Sie über Gruppen von Personen mit unterschiedlichen Diensten oder Nutzungsprofilen.
    
3. Messen Sie die Netzwerknutzung für eine Pilotgruppe von Clients. Stellen Sie sicher, dass die Pilotclients für die verschiedenen Profile von Personen in der Organisation sowie für die verschiedenen geografischen Standorte repräsentativ sind. Sie können Ihre Ergebnisse mit unseren alten Rechnern für [](/microsoftteams/prepare-network) Exchange und Microsoft Teams [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) oder die Fallstudie überprüfen, die wir in unserem eigenen Netzwerk durchgeführt haben. [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) 
    
4. Verwenden Sie die Messungen aus der Pilotgruppe, um die Anforderungen der gesamten Organisation zu extrapolieren und erneut zu testen, um die Schätzungen zu überprüfen, bevor Sie Änderungen an Ihrem Netzwerk vornehmen.
    
## <a name="test-your-existing-network"></a>Testen Ihres vorhandenen Netzwerks
<a name="calculators"> </a>

 **Netzwerktools.** Testen und überprüfen Sie Ihre Internetbandbreite, um Download-, Upload- und Latenzeinschränkungen zu ermitteln. Diese Tools helfen Ihnen, die Funktionen Ihres Netzwerks für die Migration sowie nach der vollständigen Bereitstellung zu bestimmen. 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Testet die Konnektivität in Exchange Online Umgebung.
    
- Verwenden Sie [microsoft Support- und Wiederherstellungs-Assistent for Office 365,](https://diagnostics.office.com/#/Download?env=SOC) um probleme Outlook Office 365 beheben. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Bewährte Methoden für die Netzwerkplanung und die Verbesserung der Migrationsleistung für Office 365
<a name="BestPractices"> </a>

Machen Sie sich ein wenig tiefer in diese bewährten Methoden ein, um weitere Informationen zur Verbesserung Office 365 zu erhalten.
  
1. Möchten Sie ihre Benutzer sofort unterstützen? Unter Bewährte Methoden für die Verwendung von [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) in einem langsamen Netzwerk finden Sie Tipps zur Verwendung von Office 365, einschließlich SharePoint Online, Exchange Online und Lync Online, wenn Ihr Netzwerk gerade nicht kooperiert. Dieser Artikel enthält Links zu vielen Inhalten auf TechNet und Support.office.com zur Optimierung Ihrer Office 365-Erfahrung und enthält Informationen zu einfachen Möglichkeiten zum Anpassen Ihrer Webseiten und zum Festlegen ihrer Internet Explorer-Einstellungen für die beste Office 365-Erfahrung. 
    
2. Lesen [Office 365 Netzwerkverbindungsprinzipien,](./microsoft-365-network-connectivity-principles.md) um die Konnektivitätsgrundsätze für die sichere Verwaltung Office 365 Datenverkehrs zu verstehen und die bestmögliche Leistung zu erzielen. Dieser Artikel hilft Ihnen, die neuesten Hinweise für die sichere Optimierung der Office 365-Netzwerkkonnektivität zu verstehen. 
    
3. Verbessern Sie die Leistung der E-Mail-Migration, indem Sie den Zeitplan für Windows sorgfältig verwalten. Sie können Ihre Clientcomputer in Batches aktualisieren und sicherstellen, dass alle Clientcomputer aktualisiert werden, bevor Sie zu Office 365, um die Verwendung der Netzwerkbandbreite zu regeln. Weitere Informationen finden Sie unter Manuelles Aktualisieren und Konfigurieren von [Desktops für Office 365 für die neuesten Updates](https://support.microsoft.com/gp/office-2013-365-update).
    
4. Office 365 Netzwerkdatenverkehr funktioniert am besten, wenn er als vertrauenswürdiger Internetdienst behandelt wird und einen Großen Teil der herkömmlichen Filterung und Überprüfung umgehen kann, die einige Organisationen auf Netzwerkdatenverkehr an nicht vertrauenswürdige Internetdienste übertragen. Dies umfasst in der Regel das Entfernen ausgehender Verarbeitungsschritte wie Proxybenutzerauthentifizierung und Paketprüfung sowie die Sicherstellung der lokalen Internetverbindung mit der richtigen Netzwerkadressenübersetzung (Network Address Translation, NAT) und ausreichend Bandbreitenkapazität, um die erhöhten Netzwerkanforderungen zu verarbeiten. Unter [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)finden Sie weitere Anleitungen zum Konfigurieren Ihres Netzwerks für Office 365 als vertrauenswürdiger Internetdienst in Ihrem Netzwerk.
    
1. Stellen Sie [sicher, Office 365 Endpunkte zu verwalten.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) Der zusätzliche Datenverkehr, der Office 365, führt zu einer Zunahme ausgehender Proxyverbindungen sowie zu einer Zunahme des sicheren Datenverkehrs über TLS/SSL.
    
2. Wenn Ihre ausgehenden Proxys eine Benutzerauthentifizierung erfordern, kann es zu langsamen Verbindungen oder einem Funktionsverlust führen. Wenn Sie die Authentifizierungsanforderung für die Office 365 umgehen, kann dieser Aufwand reduziert werden.
    
3. Wenn Sie über eine große Anzahl von freigegebenen Kalendern und Postfächern verfügen, wird möglicherweise die Anzahl der Verbindungen von Outlook auf Exchange. Beispielsweise kann der Outlook für jeden verwendeten freigegebenen Kalender bis zu zwei zusätzliche Verbindungen öffnen. Stellen Sie in diesem Fall sicher, dass der Ausleitungsproxy die Verbindungen verarbeiten kann, oder umgehen Sie den Proxy für Verbindungen mit Office 365 für Outlook.
    
4. Bestimmen Sie die maximale Anzahl von unterstützten Geräten für eine öffentliche IP-Adresse und den Lastenausgleich für mehrere IP-Adressen. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](nat-support-with-microsoft-365.md).
    
5. Wenn Sie ausgehende Verbindungen von Computern in Ihrem Netzwerk überprüfen, verbessert die Umgehung dieser Filterung auf die Office 365 die Konnektivität und Leistung. Darüber hinaus entgeht durch das Umgehen der ausgehenden Überprüfung häufig ein einzelner Internetausflug und ermöglicht den lokalen Internetausflug für Office 365 bestimmte Netzwerkanforderungen.
    
6. Einige Kunden finden, dass interne Netzwerkeinstellungen die Leistung beeinträchtigen können. Einstellungen z. B. die maximale Größe der Übertragungseinheit (Maximum Transmission Unit, MTU), die automatische Netzwerkaushandlung oder die automatische Erkennung sowie suboptimale Routen zum Internet sind gängige Orte.
    
## <a name="network-planning-reference-for-office-365"></a>Netzwerkplanungsreferenz für Office 365
<a name="NetReference"> </a>

Diese Themen enthalten detaillierte Office 365 Netzwerkreferenzinformationen.
  
- [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)
    
- [Externe DNS-Einträge für Office 365](external-domain-name-system-records.md)
    
- [IPv6-Unterstützung in Office 365-Diensten](ipv6-support.md)
    
- [Prinzipien von Office 365-Netzwerkverbindungen](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 häufig gestellte Fragen (FAQ) für Videonetzwerke](office-365-video-networking-faq.md)
    
- [Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen](plan-for-network-devices.md)
    
- [Setupanleitungen für Office 365 Dienste](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)