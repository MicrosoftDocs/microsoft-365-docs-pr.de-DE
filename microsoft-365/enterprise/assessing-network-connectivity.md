---
title: Bewerten der Microsoft 365-Netzwerkkonnektivität
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt über eine Internetverbindung eine Verbindung mit dem Dienst herstellen können. Mit der Weiterentwicklung des Diensts werden die Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905476"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Bewerten der Microsoft 365-Netzwerkkonnektivität

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt über eine Internetverbindung eine Verbindung mit dem Dienst herstellen können. Mit der Weiterentwicklung des Diensts werden die Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
  
Kunden, die Microsoft 365 verwenden möchten, sollten ihre vorhandenen und prognostizierten Anforderungen an die Internetverbindung im Rahmen des Bereitstellungsprojekts bewerten. Für Bereitstellungen der Unternehmensklasse ist eine zuverlässige und entsprechend dimensionierte Internetkonnektivität ein wichtiger Bestandteil der nutzungsintensiven Microsoft 365 und Szenarien.
  
Netzwerkauswertungen können von vielen verschiedenen Personen und Organisationen in Abhängigkeit von Ihrer Größe und Ihren Einstellungen durchgeführt werden. Der Netzwerkumfang der Bewertung kann auch variieren, je nachdem, wo Sie sich im Bereitstellungsprozess befinden. Damit Sie besser verstehen können, was für die Durchführung einer Netzwerkbewertung benötigt wird, haben wir einen Leitfaden zur Netzwerkbewertung erstellt, der Ihnen dabei hilft, die verfügbaren Optionen zu verstehen. Diese Bewertung bestimmt, welche Schritte und Ressourcen dem Bereitstellungsprojekt hinzugefügt werden müssen, damit sie erfolgreich Microsoft 365.
  
Eine umfassende Netzwerkbewertung bietet mögliche Lösungen für Netzwerkdesignprobleme sowie Implementierungsdetails. Einige Netzwerkbewertungen zeigen, dass eine optimale Netzwerkkonnektivität mit Microsoft 365 mit geringfügigen Konfigurations- oder Entwurfsänderungen an der vorhandenen Netzwerk- und Internet-Ausgangsinfrastruktur berücksichtigt werden kann.

Einige Bewertungen deuten darauf hin, dass Microsoft 365 Netzwerkverbindungen zusätzliche Investitionen in Netzwerkkomponenten erfordern. Beispielsweise können Unternehmensnetzwerke, die Zweigstellen und mehrere geografische Regionen umfassen, Investitionen in SD-WAN-Lösungen oder eine optimierte Routinginfrastruktur erfordern, um die Internetverbindung zu Microsoft 365. Gelegentlich weist eine Bewertung darauf hin, dass die Netzwerkkonnektivität mit Microsoft 365 von Vorschriften oder Leistungsanforderungen für Szenarien wie Skype for Business Medienqualität beeinflusst [wird.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Diese zusätzlichen Anforderungen können zu Investitionen in internetkonnektivitätsinfrastruktur, Routingoptimierung und spezielle direkte Konnektivität führen.

Einige Ressourcen, die Sie bei der Bewertung Ihres Netzwerks unterstützen:

- Unter [Microsoft 365 Übersicht über die Netzwerkkonnektivität](microsoft-365-networking-overview.md) finden Sie konzeptionelle Informationen zu Microsoft 365 Netzwerk.
- Unter [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) finden Sie Informationen zu den Konnektivitätsprinzipien für die sichere Verwaltung Microsoft 365 Datenverkehrs und zum Erzielen der bestmöglichen Leistung.
- Melden Sie sich für [Microsoft FastTrack an,](https://www.microsoft.com/fasttrack) um unterstützung bei Microsoft 365 Planung, Entwurf und Bereitstellung zu erhalten. 
- Im abschnitt [Microsoft 365 Konnektivitätstest](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) finden Sie grundlegende Konnektivitätstests, die spezifische Anleitungen zu Verbesserungen der Netzwerkkonnektivität bieten, die zwischen einem bestimmten Benutzerstandort und einem bestimmten Microsoft 365.

> [!NOTE]
> Die Microsoft-Autorisierung ist erforderlich, um ExpressRoute für Office 365. Microsoft überprüft jede Kundenanforderung und autorisiert ExpressRoute nur für Office 365, wenn die behördliche Anforderung eines Kunden eine direkte Konnektivität vorsingt. Wenn Sie solche Anforderungen haben, geben Sie bitte den Textauszug und den Weblink zu der Verordnung an, die Sie so interpretieren, dass eine direkte Verbindung im ExpressRoute für [Office 365-Anforderungsformular](https://aka.ms/O365ERReview) erforderlich ist, um eine Microsoft-Überprüfung zu starten. Nicht autorisierte Abonnements, die Routenfilter für Office 365 erstellen, erhalten [eine Fehlermeldung.](https://support.microsoft.com/kb/3181709)
  
Wichtige Punkte, die Sie bei der Planung Ihrer Netzwerkbewertung für Microsoft 365:
  
- Microsoft 365 ist ein sicherer, zuverlässiger, leistungsstarker Dienst, der über das öffentliche Internet ausgeführt wird. Wir investieren weiterhin, um diese Aspekte des Diensts zu verbessern. Alle Microsoft 365 sind über Internetverbindung verfügbar.

- Wir optimieren kontinuierlich wichtige Aspekte der Microsoft 365 z. B. Verfügbarkeit, globale Reichweite und Leistung für internetbasierte Konnektivität. Viele Microsoft 365 nutzen beispielsweise einen erweiterten Satz von Edgeknoten mit Internetzugriff. Dieses Edgenetzwerk bietet die beste Nähe und Leistung für Verbindungen, die über das Internet kommen.

- Wenn Sie erwägen, Microsoft 365 für einen der enthaltenen Dienste wie Teams oder Skype for Business Online-Sprach-, Video- oder Besprechungsfunktionen zu verwenden, sollten Kunden eine End-to-End-Netzwerkbewertung abschließen und die Konnektivitätsanforderungen mithilfe von [Microsoft FastTrack erfüllen.](https://www.microsoft.com/fasttrack)

Wenn Sie die Microsoft 365 auswerten und nicht sicher sind, wo Sie mit ihrer Netzwerkbewertung beginnen sollen oder netzwerkdesignische Herausforderungen gefunden haben, die Sie überwinden müssen, arbeiten Sie bitte mit Ihrem Microsoft-Kontoteam zusammen.

## <a name="the-microsoft-365-connectivity-test"></a>Der Microsoft 365 Konnektivitätstest

Der [Microsoft 365](https://aka.ms/netonboard) Konnektivitätstest ist ein Tool zur Bewertung des Konzepts (Proof of Concept, POC), das grundlegende Konnektivitätstests für Ihren Microsoft 365-Mandanten durch führt und spezifische Netzwerkentwurfsempfehlungen für eine optimale Leistung Microsoft 365 macht. Das Tool hebt allgemeine Designoptionen für große Unternehmensnetzwerkperimeter hervor, die für das Internetwebbrowsen nützlich sind, sich aber auf die Leistung großer SaaS-Anwendungen wie Microsoft 365.

Das Netzwerk-Onboarding-Tool führt die folgenden Schritte aus:

- Erkennt Ihren Standort, oder Sie können einen zu testenden Speicherort angeben.
- Überprüft den Standort Ihres Netzwerk-Ausgangs
- Testet den Netzwerkpfad zur nächsten Microsoft 365 der Eingangstür des Diensts
- Stellt erweiterte Tests mit einer herunterladbaren Windows 10 bereit, die Empfehlungen für den Entwurf des Umkreisnetzwerks in Bezug auf Proxyserver, Firewalls und DNS enthält. Das Tool führt auch Leistungstests für Skype for Business Online, Microsoft Teams, SharePoint Online und Exchange Online.

Das Tool verfügt über zwei Komponenten: eine browserbasierte Benutzeroberfläche, die grundlegende Konnektivitätsinformationen sammelt, und eine herunterladbare Windows 10-Anwendung, die erweiterte Tests ausgeführt und zusätzliche Bewertungsdaten zurückgibt.

Das browserbasierte Tool zeigt die folgenden Informationen an:

- Registerkarte "Ergebnisse und Auswirkungen"
  - Der Standort auf einer Karte der In-Use-Service-Eingangstür
  - Der Standort auf einer Karte mit anderen Fronttüren des Diensts, die eine optimale Konnektivität bieten würden
  - Relative Leistung im Vergleich zu anderen Microsoft 365 Kunden in Ihrer Nähe
- Registerkarte "Details und Lösungen"
  - Benutzerstandort nach Stadt und Land
  - Netzwerkstandort nach Stadt, Bundesland und Land
  - Benutzer-zu-Netzwerk-Ausgangsabstand
  - Microsoft 365 Exchange Online der Front-Door-Position des Diensts
  - Optimale Microsoft 365 Exchange Online für die Benutzerstandorte
  - Kunden in Ihrer U-Bahn-Region mit besserer Leistung

Die herunterladbare Anwendung für erweiterte Tests enthält die folgenden zusätzlichen Informationen:

- Registerkarte "Details und Lösungen" (angefügt)
  - Standardgateway des Benutzers
  - Client-DNS-Server
  - Client-DNS-Rekursiver Resolver
  - Exchange Online DNS-Server
  - SharePoint Online-DNS-Server
  - Proxyserveridentifikation
  - Überprüfung der Medienkonnektivität
  - Paketverlust in Medienqualität
  - Wartezeit für Medienqualität
  - Jitter der Medienqualität
  - Neusortierung von Paketen in Medienqualität
- Konnektivitätstests mit mehreren featurespezifischen Endpunkten
- Netzwerkpfaddiagnose, die Tracert- und Latenzdaten für die Dienste Exchange Online, SharePoint Online und Teams enthält

Sie können sich über den Microsoft 365 Konnektivitätstest und Feedback im Blogbeitrag Updated [Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) lesen. Informationen zu zukünftigen Updates für dieses Tool und andere Microsoft 365 Netzwerkupdates werden im Blog [Office 365 veröffentlicht.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Hier ist ein kurzer Link, den Sie verwenden können, um zurück zu kommen: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 – Überblick über die Netzwerkkonnektivität](microsoft-365-networking-overview.md)

[Prinzipien von Microsoft 365-Netzwerkverbindungen](./microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Office 365 – IP-Adress- und URL-Webdienst](microsoft-365-ip-web-service.md)

[Microsoft 365 netzwerk- und leistungsoptimierung](network-planning-and-performance.md)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)