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
description: Dieser Artikel enthält Links zu Informationen zur Netzwerkplanung, zum Testen und zur Migration zu Office 365.
ms.openlocfilehash: aed8bacd4dc08aa6d77ad0c530e721ac9d383bf5
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149106"
---
# <a name="network-and-migration-planning-for-office-365"></a>Netzwerk- und Migrationsplanung für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Dieser Artikel enthält Links zu Informationen zur Netzwerkplanung und zum Testen sowie zur Migration zu Office 365.
  
Bevor Sie die Bereitstellung zum ersten Mal durchführen oder zu Office 365 migrieren, können Sie anhand der Informationen in diesen Themen die benötigte Bandbreite ermitteln und dann testen und überprüfen, ob sie über genügend Bandbreite für die Bereitstellung oder Migration zu Office 365 verfügen.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)

Die Schritte zum Optimieren Ihres Netzwerks für Microsoft 365 und andere Microsoft Cloud-Plattformen und -Dienste finden Sie auf dem Poster ["Microsoft Cloud Networking for Enterprise Architects".](../solutions/cloud-architecture-models.md)
   
## <a name="estimate-network-bandwidth-requirements"></a>Ermitteln der Netzwerkbandbreitenanforderungen
<a name="EstimateBandwidthRequirements"> </a>

Die Verwendung von Office 365 kann die Nutzung des Internetschalters Ihrer Organisation erhöhen. Es ist wichtig zu bestimmen, ob die zurzeit verfügbare Bandbreite ausreicht, um den geschätzten Anstieg zu bewältigen, sobald Office 365 vollständig bereitgestellt ist, während mindestens 20 % der Kapazität für die Auslastung der Tage übrig bleibt.
  
Führen Sie die folgenden Schritte aus, um die Bandbreite zu schätzen:
  
1. Bewerten Sie die Anzahl der Clients, die jeden Internetausgang verwenden. Lassen Sie unser Multi-Terabit-Netzwerk so viel wie möglich von der Verbindung verarbeiten. 
    
2. Bestimmen Sie, welche Office 365 Dienste und Features für Clients zur Verfügung stehen. Wahrscheinlich verfügen Sie über Gruppen von Personen mit unterschiedlichen Diensten oder Nutzungsprofilen.
    
3. Messen der Netzwerkverwendung für eine Pilotgruppe von Clients. Stellen Sie sicher, dass die Pilotclients für die verschiedenen Profile von Personen in der Organisation sowie für die verschiedenen geografischen Standorte repräsentativ sind. Sie können Ihre Ergebnisse anhand unserer alten Rechner auf [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) und [Microsoft Teams](/microsoftteams/prepare-network) oder die [Fallstudie](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) überprüfen, die wir in unserem eigenen Netzwerk durchgeführt haben. 
    
4. Verwenden Sie die Messungen der Pilotgruppe, um die Anforderungen der gesamten Organisation zu extrapolieren und die Einschätzungen erneut zu überprüfen, bevor Sie Änderungen an Ihrem Netzwerk vornehmen.
    
## <a name="test-your-existing-network"></a>Testen Ihres vorhandenen Netzwerks
<a name="calculators"> </a>

 **Netzwerktools.** Testen und überprüfen Sie Ihre Internetbandbreite, um Download-, Upload- und Latenzeinschränkungen zu ermitteln. Diese Tools helfen Ihnen, die Funktionen Ihres Netzwerks für die Migration sowie nach der vollständigen Bereitstellung zu ermitteln. 
    
- [Microsoft Remote Connectivity Analyzer:](https://go.microsoft.com/fwlink/p/?LinkId=517243)Testet die Konnektivität in Ihrer Exchange Online Umgebung.
    
- Verwenden Sie die [Microsoft Support- und Wiederherstellungs-Assistent für Office 365,](https://diagnostics.office.com/#/Download?env=SOC) um Outlook und Office 365 Probleme zu beheben. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Bewährte Methoden für die Netzwerkplanung und die Verbesserung der Migrationsleistung für Office 365
<a name="BestPractices"> </a>

Befassen Sie sich etwas eingehender mit diesen bewährten Methoden, um weitere Informationen zur Verbesserung Ihrer Office 365 Erfahrung zu erhalten.
  
1. Möchten Sie sofort damit beginnen, Ihren Benutzern zu helfen? In [den bewährten Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) finden Sie Tipps zur Verwendung von Office 365, einschließlich SharePoint Online, Exchange Online und Lync Online, wenn Ihr Netzwerk gerade nicht ging. Dieser Artikel enthält Links zu vielen Inhalten auf TechNet und Support.office.com, um Ihre Office 365 Erfahrung zu optimieren, und enthält Informationen zu einfachen Möglichkeiten zum Anpassen Ihrer Webseiten und zum Festlegen Ihrer Internet Explorer-Einstellungen für die beste Office 365 Erfahrung. 
    
2. Lesen Sie Office 365 Prinzipien der [Netzwerkkonnektivität,](./microsoft-365-network-connectivity-principles.md) um die Konnektivitätsprinzipien für die sichere Verwaltung Office 365 Datenverkehrs und das Erzielen der bestmöglichen Leistung zu verstehen. Dieser Artikel hilft Ihnen, die neuesten Hinweise für die sichere Optimierung der Office 365-Netzwerkkonnektivität zu verstehen. 
    
3. Verbessern Sie die Leistung der E-Mail-Migration, indem Sie den Zeitplan für Windows Updates sorgfältig verwalten. Sie können Ihre Clientcomputer in Batches aktualisieren und sicherstellen, dass alle Clientcomputer aktualisiert werden, bevor Sie zu Office 365 migrieren, um die Verwendung der Netzwerkbandbreite zu regeln. Weitere Informationen finden Sie unter [Manuelles Aktualisieren und Konfigurieren von Desktops für Office 365 für die neuesten Updates.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 Netzwerkdatenverkehr funktioniert am besten, wenn er als vertrauenswürdiger Internetdienst behandelt wird und einen Großteil der herkömmlichen Filterung und Überprüfung umgehen kann, die einige Organisationen im Netzwerkdatenverkehr an nicht vertrauenswürdige Internetdienste platzieren. Dies umfasst in der Regel das Entfernen ausgehender Verarbeitungen wie Proxybenutzerauthentifizierung und Paketüberprüfung sowie die Sicherstellung des lokalen Ausgangs in das Internet mit der richtigen Netzwerkadressübersetzung (Network Address Translation, NAT) und ausreichend Bandbreitenkapazität, um die erhöhten Netzwerkanforderungen zu verarbeiten. Weitere Anleitungen zum Konfigurieren Ihres Netzwerks für die Verarbeitung von Office 365 als vertrauenswürdiger Internetdienst in Ihrem Netzwerk finden Sie unter ["Verwalten Office 365 Endpunkte".](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
1. Stellen Sie [sicher, dass Office 365 Endpunkte verwaltet werden.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) Der zusätzliche Datenverkehr, der Office 365, führt zu einem Anstieg ausgehender Proxyverbindungen sowie zu einem Anstieg des sicheren Datenverkehrs über TLS/SSL.
    
2. Wenn Ihre ausgehenden Proxys eine Benutzerauthentifizierung erfordern, kann es zu einer langsamen Verbindung oder zu einem Funktionsverlust führen. Das Umgehen der Authentifizierungsanforderung für die Office 365 Domänen kann diesen Aufwand reduzieren.
    
3. Wenn Sie über eine große Anzahl von freigegebenen Kalendern und Postfächern verfügen, wird möglicherweise eine Erhöhung der Anzahl von Verbindungen von Outlook zu Exchange angezeigt. Beispielsweise kann der Outlook-Client bis zu zwei zusätzliche Verbindungen für jeden verwendeten freigegebenen Kalender öffnen. Stellen Sie in diesem Fall sicher, dass der Ausgehende Proxy die Verbindungen verarbeiten kann, oder umgehen Sie den Proxy für Verbindungen zu Office 365 für Outlook.
    
4. Bestimmen Sie die maximale Anzahl der unterstützten Geräte für eine öffentliche IP-Adresse und wie der Lastenausgleich über mehrere IP-Adressen hinweg erfolgt. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](nat-support-with-microsoft-365.md).
    
5. Wenn Sie ausgehende Verbindungen von Computern in Ihrem Netzwerk überprüfen, verbessert das Umgehen dieser Filterung an die Office 365 Domänen die Konnektivität und Leistung. Darüber hinaus entgeht durch das Umgehen der ausgehenden Prüfung häufig die Notwendigkeit eines einzelnen Internetausgangs und ermöglicht den lokalen Internetausgang für Office 365 bestimmte Netzwerkanforderungen.
    
6. Einige Kunden finden, dass interne Netzwerkeinstellungen die Leistung beeinträchtigen können. Einstellungen wie die maximale Größe der Übertragungseinheit (MTU), automatische Netzwerkaushandlung oder automatische Erkennung sowie suboptimale Routen zum Internet sind häufige Orte zum Suchen.
    
## <a name="network-planning-reference-for-office-365"></a>Netzwerkplanungsreferenz für Office 365
<a name="NetReference"> </a>

Diese Themen enthalten detaillierte Office 365 Netzwerkreferenzinformationen.
  
- [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)
    
- [Externe DNS-Einträge für Office 365](external-domain-name-system-records.md)
    
- [IPv6-Unterstützung in Office 365-Diensten](ipv6-support.md)
    
- [Prinzipien von Office 365-Netzwerkverbindungen](./microsoft-365-network-connectivity-principles.md)
    
- [Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen](plan-for-network-devices.md)
    
- [Einrichtungshandbücher für Office 365-Dienste](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)