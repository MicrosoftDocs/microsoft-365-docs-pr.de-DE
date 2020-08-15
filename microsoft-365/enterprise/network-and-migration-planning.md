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
description: Dieser Artikel enthält Links zu Informationen zum Planen, testen und Migrieren von Netzwerken zu Office 365.
ms.openlocfilehash: 1e6973f93c65012f4ca007332a47cc6b9e67b3b0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690841"
---
# <a name="network-and-migration-planning-for-office-365"></a>Netzwerk- und Migrationsplanung für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Dieser Artikel enthält Links zu Informationen zur Planung und zum Testen von Netzwerken sowie zur Migration zu Office 365.
  
Bevor Sie das erste Mal bereitstellen oder zu Office 365 migrieren, können Sie die Informationen in diesen Themen verwenden, um die benötigte Bandbreite zu schätzen und anschließend zu testen und zu überprüfen, ob genügend Bandbreite für die Bereitstellung oder Migration zu Office 365 verfügbar ist.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune).

Die Schritte zur Optimierung Ihres Netzwerks für Microsoft 365 und andere Microsoft Cloud-Plattformen und-Dienste finden Sie unter [Microsoft Cloud Networking for Enterprise Architects](https://aka.ms/cloudarchnetworking) Poster.
   
## <a name="estimate-network-bandwidth-requirements"></a>Schätzen der Anforderungen an die Netzwerkbandbreite
<a name="EstimateBandwidthRequirements"> </a>

Die Verwendung von Office 365 kann die Auslastung der Internet Schaltung Ihrer Organisation verbessern. Es ist wichtig, zu ermitteln, ob die derzeit verfügbare Bandbreite ausreicht, um den geschätzten Zuwachs zu bewältigen, wenn Office 365 vollständig bereitgestellt ist, während mindestens 20% Kapazität zur Verarbeitung der arbeitsreichsten Tage bleibt.
  
Führen Sie die folgenden Schritte aus, um die Bandbreite zu schätzen:
  
1. Bewerten Sie die Anzahl der Clients, die die einzelnen Internet Ausgänge verwenden sollen. Lassen Sie unser Multi-Terabit-Netzwerk so viel von der Verbindung wie möglich verarbeiten. 
    
2. Ermitteln Sie, welche Office 365 Dienste und Features für Clients verfügbar sein sollen. Sie haben wahrscheinlich Gruppen von Personen mit unterschiedlichen Diensten oder Nutzungsprofilen.
    
3. Messen Sie die Netzwerkverwendung für eine Pilotgruppe von Clients. Stellen Sie sicher, dass die Pilot Clients für die verschiedenen Profile von Personen in der Organisation sowie für die verschiedenen geografischen Standorte repräsentativ sind. Sie können Ihre Ergebnisse gegen unsere alten Rechner für [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) und [Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=321551) oder die [Fallstudie](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) , die wir in unserem eigenen Netzwerk durchgeführt haben, überprüfen. 
    
4. Verwenden Sie die Messungen der Pilotgruppe, um die Anforderungen der gesamten Organisation hochzurechnen und erneut zu testen, um die Schätzungen zu überprüfen, bevor Sie Änderungen an Ihrem Netzwerk vornehmen.
    
## <a name="test-your-existing-network"></a>Testen des vorhandenen Netzwerks
<a name="calculators"> </a>

 **Netzwerktools.** Testen und überprüfen Sie Ihre Internet Bandbreite, um Download-, Upload-und Latenz Einschränkungen zu ermitteln. Mithilfe dieser Tools können Sie die Funktionen Ihres Netzwerks für die Migration sowie nach der vollständigen Bereitstellung ermitteln. 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): testet die Konnektivität in Ihrer Exchange Online Umgebung.
    
- Verwenden Sie den [Microsoft-Support-und Wiederherstellungs-Assistenten für Office 365](https://diagnostics.office.com/#/Download?env=SOC) , um Outlook-und Office 365 Probleme zu beheben. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Bewährte Methoden für die Netzwerkplanung und die Verbesserung der Migrationsleistung für Office 365
<a name="BestPractices"> </a>

Lesen Sie die folgenden bewährten Methoden, um weitere Informationen zum Verbessern Ihrer Office 365 Erfahrung zu erhalten.
  
1. Möchten Sie sofort mit der Unterstützung Ihrer Benutzer beginnen? Tipps zur Verwendung von Office 365, einschließlich SharePoint Online, Exchange Online und lync Online, wenn Ihr Netzwerk einfach nicht zusammenarbeitet, finden Sie unter [bewährte Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) . Dieser Artikel enthält Links zu Lasten von Inhalten auf TechNet und Support.Office.com zur Optimierung Ihrer Office 365 Erfahrung und enthält Informationen zu einfachen Möglichkeiten zum Anpassen Ihrer Webseiten und zum Festlegen ihrer Internet Explorer Einstellungen für die beste Office 365 Erfahrung. 
    
2. Lesen Sie [Office 365 Grundsätze der Netzwerkkonnektivität](https://aka.ms/o365networkingprinciples) , um die Verbindungs Prinzipien für die sichere Verwaltung Office 365 Datenverkehrs und die bestmögliche Leistung zu verstehen. Dieser Artikel hilft Ihnen, die neuesten Hinweise für die sichere Optimierung der Office 365-Netzwerkkonnektivität zu verstehen. 
    
3. Verbessern der e-Mail-Migrationsleistung durch sorgfältiges Verwalten des Zeitplans für Windows-Updates Sie können Ihre Clientcomputer in Batches aktualisieren und sicherstellen, dass alle Clientcomputer vor der Migration zu Office 365 aktualisiert werden, um die Verwendung der Netzwerkbandbreite zu regulieren. Weitere Informationen finden Sie unter [Manuelles Aktualisieren und Konfigurieren von Desktops für Office 365 für die neuesten Updates](https://support.microsoft.com/gp/office-2013-365-update).
    
4. Office 365 Netzwerkdatenverkehr funktioniert am besten, wenn er als vertrauenswürdiger Internetdienst behandelt wird und den Großteil der herkömmlichen Filterung und Überprüfung umgehen kann, die einige Organisationen im Netzwerkdatenverkehr an nicht vertrauenswürdige Internetdienste platzieren. Dies umfasst normalerweise das Entfernen der ausgehenden Verarbeitung wie Proxybenutzer Authentifizierung und Paketüberprüfung sowie das Sicherstellen des lokalen Ausstiegs ins Internet mit der richtigen Netzwerkadressübersetzung (Network Address Translation, NAT) und genügend Bandbreitenkapazität zur Verarbeitung der erhöhten Netzwerkanforderungen. Weitere Anleitungen zum Konfigurieren Ihres Netzwerks für die Verarbeitung von Office 365 als vertrauenswürdigen Internet Dienst in Ihrem Netzwerk erhalten Sie unter [Managing Office 365 Endpunkte](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).
    
1. Sicherstellen der [Verwaltung von Office 365 Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) Der zusätzliche Datenverkehr, der Office 365 wird, führt zu einer erhöhten Zahl ausgehender Proxyverbindungen sowie zu einer erhöhten Sicherheit des Datenverkehrs über TLS/SSL.
    
2. Wenn Ihre ausgehenden Proxybenutzer Authentifizierung erfordern, treten möglicherweise eine langsame Konnektivität oder ein Funktionsverlust auf. Durch Umgehung der Authentifizierungsanforderung für die Office 365 Domänen kann dieser Aufwand reduziert werden.
    
3. Wenn Sie eine große Anzahl von freigegebenen Kalendern und Postfächern haben, wird möglicherweise die Anzahl der Verbindungen zwischen Outlook und Exchange erhöht. Beispielsweise kann der Outlook-Client bis zu zwei zusätzliche Verbindungen für jeden freigegebenen Kalender öffnen, der verwendet wird. Stellen Sie in diesem Fall sicher, dass der Ausstiegs Proxy die Verbindungen verarbeiten kann, oder umgehen Sie den Proxy für Verbindungen mit Office 365 für Outlook.
    
4. Bestimmen Sie die maximale Anzahl unterstützter Geräte für eine öffentliche IP-Adresse und wie ein Lastenausgleich über mehrere IP-Adressen verteilt wird. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](nat-support-with-microsoft-365.md).
    
5. Wenn Sie ausgehende Verbindungen von Computern in Ihrem Netzwerk untersuchen, wird durch Umgehung dieser Filterung mit den Office 365 Domänen die Konnektivität und Leistung verbessert. Darüber hinaus wird durch die Umgehung der ausgehenden Überprüfung häufig die Notwendigkeit eines einzelnen Internet Ausstiegs beseitigt, und es wird ein lokales Internet Ausstieg für Office 365 bestimmte Netzwerkanforderungen aktiviert.
    
6. Einige Kunden finden interne Netzwerkeinstellungen können sich auf die Leistung auswirken. Einstellungen wie maximale Übertragungseinheit (MTU)-Größe, automatische Netzwerk Aushandlung oder automatische Erkennung sowie suboptimale Routen zum Internet sind allgemeine Orte, die Sie suchen müssen.
    
## <a name="network-planning-reference-for-office-365"></a>Referenz zur Netzwerkplanung für Office 365
<a name="NetReference"> </a>

Diese Themen enthalten ausführliche Office 365 Netzwerk Referenzinformationen.
  
- [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)
    
- [Externe DNS-Einträge für Office 365](external-domain-name-system-records.md)
    
- [IPv6-Unterstützung in Office 365-Diensten](ipv6-support.md)
    
- [Prinzipien von Office 365-Netzwerkverbindungen](https://aka.ms/o365networkingprinciples)
    
- [Office 365 häufig gestellten Fragen zu Videonetzwerken (FAQ)](office-365-video-networking-faq.md)
    
- [Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen](plan-for-network-devices.md)
    
- [Installationshandbücher für Office 365 Dienste](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
