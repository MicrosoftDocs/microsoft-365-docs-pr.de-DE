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
description: Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt über eine Internetverbindung eine Verbindung mit dem Dienst herstellen können. Mit der Weiterentwicklung des Diensts werden Die Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905476"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Bewerten der Microsoft 365-Netzwerkkonnektivität

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt über eine Internetverbindung eine Verbindung mit dem Dienst herstellen können. Mit der Weiterentwicklung des Diensts werden Die Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
  
Kunden, die Microsoft 365 verwenden möchten, sollten ihre vorhandenen und prognostizierten Anforderungen an die Internetverbindung im Rahmen des Bereitstellungsprojekts bewerten. Für Bereitstellungen der Unternehmensklasse ist eine zuverlässige und entsprechend dimensionierte Internetverbindung ein wichtiger Bestandteil der Nutzung von Microsoft 365-Features und -Szenarien.
  
Netzwerkauswertungen können von vielen verschiedenen Personen und Organisationen in Abhängigkeit von Ihrer Größe und Ihren Einstellungen durchgeführt werden. Der Netzwerkumfang der Bewertung kann auch variieren, je nachdem, wo Sie sich im Bereitstellungsprozess befinden. Damit Sie besser verstehen können, was für die Durchführung einer Netzwerkbewertung benötigt wird, haben wir einen Leitfaden zur Netzwerkbewertung erstellt, der Ihnen dabei hilft, die verfügbaren Optionen zu verstehen. Diese Bewertung bestimmt, welche Schritte und Ressourcen dem Bereitstellungsprojekt hinzugefügt werden müssen, damit Sie Microsoft 365 erfolgreich übernehmen können.
  
Eine umfassende Netzwerkbewertung bietet mögliche Lösungen für Netzwerkdesignprobleme sowie Implementierungsdetails. Einige Netzwerkbewertungen zeigen, dass eine optimale Netzwerkkonnektivität mit Microsoft 365 mit geringfügigen Konfigurations- oder Entwurfsänderungen an der vorhandenen Netzwerk- und Internet-Ausgangsinfrastruktur berücksichtigt werden kann.

Einige Bewertungen deuten darauf hin, dass für die Netzwerkkonnektivität mit Microsoft 365 zusätzliche Investitionen in Netzwerkkomponenten erforderlich sind. Beispielsweise können Unternehmensnetzwerke, die Zweigstellen und mehrere geografische Regionen umfassen, Investitionen in SD-WAN-Lösungen oder eine optimierte Routinginfrastruktur erfordern, um die Internetverbindung mit Microsoft 365 zu unterstützen. Gelegentlich weist eine Bewertung darauf hin, dass die Netzwerkkonnektivität mit Microsoft 365 durch Vorschriften oder Leistungsanforderungen für Szenarien wie Die Medienqualität von [Skype for Business Online beeinflusst wird.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Diese zusätzlichen Anforderungen können zu Investitionen in internetkonnektivitätsinfrastruktur, Routingoptimierung und spezielle direkte Konnektivität führen.

Einige Ressourcen, die Sie bei der Bewertung Ihres Netzwerks unterstützen:

- Unter [Microsoft 365 Network Connectivity overview](microsoft-365-networking-overview.md) finden Sie konzeptionelle Informationen zu Microsoft 365-Netzwerken.
- Unter [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) erfahren Sie mehr über die Konnektivitätsprinzipien für die sichere Verwaltung von Microsoft 365-Datenverkehr und die bestmögliche Leistung.
- Registrieren Sie sich [für Microsoft FastTrack,](https://www.microsoft.com/fasttrack) um Unterstützung bei der Planung, dem Entwurf und der Bereitstellung von Microsoft 365 zu erhalten. 
- Im Folgenden finden Sie im Abschnitt [Microsoft 365-Konnektivitätstests](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) grundlegende Konnektivitätstests, die spezifische Anleitungen zu Verbesserungen der Netzwerkkonnektivität bieten, die zwischen einem bestimmten Benutzerstandort und Microsoft 365 vorgenommen werden können.

> [!NOTE]
> Die Microsoft-Autorisierung ist erforderlich, um ExpressRoute für Office 365 zu verwenden. Microsoft überprüft jede Kundenanforderung und autorisiert expressRoute für die Office 365-Nutzung nur, wenn die behördliche Anforderung eines Kunden eine direkte Konnektivität vorsingt. Wenn Sie über solche Anforderungen verfügen, geben Sie bitte den Textauszug und den Weblink zu der Verordnung an, die Sie so interpretieren, dass eine direkte Verbindung im [ExpressRoute for Office 365-Anforderungsformular](https://aka.ms/O365ERReview) erforderlich ist, um eine Microsoft-Überprüfung zu starten. Nicht autorisierte Abonnements, die Routenfilter für Office 365 erstellen möchten, erhalten [eine Fehlermeldung.](https://support.microsoft.com/kb/3181709)
  
Wichtige Punkte, die Sie bei der Planung Ihrer Netzwerkbewertung für Microsoft 365 berücksichtigen sollten:
  
- Microsoft 365 ist ein sicherer, zuverlässiger, leistungsstarker Dienst, der über das öffentliche Internet ausgeführt wird. Wir investieren weiterhin, um diese Aspekte des Diensts zu verbessern. Alle Microsoft 365-Dienste sind über Internetverbindung verfügbar.

- Wir optimieren kontinuierlich wichtige Aspekte von Microsoft 365, z. B. Verfügbarkeit, globale Reichweite und Leistung für internetbasierte Konnektivität. Viele Microsoft 365-Dienste nutzen beispielsweise einen erweiterten Satz von Edgeknoten mit Internetzugriff. Dieses Edgenetzwerk bietet die beste Nähe und Leistung für Verbindungen, die über das Internet kommen.

- Wenn Sie erwägen, Microsoft 365 für einen der enthaltenen Dienste wie Teams oder Skype for Business Online-Sprach-, Video- oder Besprechungsfunktionen zu verwenden, sollten Kunden eine End-to-End-Netzwerkbewertung abschließen und die Konnektivitätsanforderungen mithilfe von [Microsoft FastTrack erfüllen.](https://www.microsoft.com/fasttrack)

Wenn Sie Microsoft 365 auswerten und nicht sicher sind, wo Sie mit Ihrer Netzwerkbewertung beginnen sollen oder Netzwerkentwurfsherausforderungen gefunden haben, die Sie überwinden müssen, arbeiten Sie bitte mit Ihrem Microsoft-Kontoteam zusammen.

## <a name="the-microsoft-365-connectivity-test"></a>Der Microsoft 365-Konnektivitätstest

Der [Microsoft 365-Konnektivitätstest](https://aka.ms/netonboard) ist ein PoC(Proof of Concept)-Netzwerkbewertungstool, das grundlegende Konnektivitätstests für Ihren Microsoft 365-Mandanten durch führt und spezifische Netzwerkentwurfsempfehlungen für eine optimale Microsoft 365-Leistung gibt. Das Tool hebt allgemeine Designoptionen für große Unternehmensnetzwerkperimeter hervor, die für das Surfen im Internet nützlich sind, sich aber auf die Leistung großer SaaS-Anwendungen wie Microsoft 365 auswirken.

Das Netzwerk-Onboarding-Tool führt die folgenden Schritte aus:

- Erkennt Ihren Standort, oder Sie können einen zu testenden Speicherort angeben.
- Überprüft den Standort Ihres Netzwerk-Ausgangs
- Testet den Netzwerkpfad zur nächsten Microsoft 365-Dienst-Eingangstür
- Stellt erweiterte Tests mithilfe einer herunterladbaren Windows 10-Anwendung bereit, die Empfehlungen zum Entwurf von Umkreisnetzwerken in Bezug auf Proxyserver, Firewalls und DNS enthält. Das Tool führt auch Leistungstests für Skype for Business Online, Microsoft Teams, SharePoint Online und Exchange Online aus.

Das Tool verfügt über zwei Komponenten: eine browserbasierte Benutzeroberfläche, die grundlegende Konnektivitätsinformationen sammelt, und eine herunterladbare Windows 10-Anwendung, die erweiterte Tests ausgeführt und zusätzliche Bewertungsdaten zurückgibt.

Das browserbasierte Tool zeigt die folgenden Informationen an:

- Registerkarte "Ergebnisse und Auswirkungen"
  - Der Standort auf einer Karte der In-Use-Service-Eingangstür
  - Der Standort auf einer Karte mit anderen Fronttüren des Diensts, die eine optimale Konnektivität bieten würden
  - Relative Leistung im Vergleich zu anderen Microsoft 365-Kunden in Ihrer Nähe
- Registerkarte "Details und Lösungen"
  - Benutzerstandort nach Stadt und Land
  - Netzwerkstandort nach Stadt, Bundesland und Land
  - Benutzer-zu-Netzwerk-Ausgangsabstand
  - Standort des Microsoft 365 Exchange Online-Diensts vor der Tür
  - Optimale Microsoft 365 Exchange Online-Dienst-Fronttüren für den Benutzerstandort
  - Kunden in Ihrer U-Bahn-Region mit besserer Leistung

Die herunterladbare Anwendung für erweiterte Tests enthält die folgenden zusätzlichen Informationen:

- Registerkarte "Details und Lösungen" (angefügt)
  - Standardgateway des Benutzers
  - Client-DNS-Server
  - Client-DNS-Rekursiver Resolver
  - Exchange Online-DNS-Server
  - SharePoint Online-DNS-Server
  - Proxyserveridentifikation
  - Überprüfung der Medienkonnektivität
  - Paketverlust in Medienqualität
  - Wartezeit für Medienqualität
  - Jitter der Medienqualität
  - Neusortierung von Paketen in Medienqualität
- Konnektivitätstests mit mehreren featurespezifischen Endpunkten
- Netzwerkpfaddiagnose, die Tracert- und Latenzdaten für die Exchange Online-, SharePoint Online- und Teams-Dienste enthält

Informationen zum Microsoft 365-Konnektivitätstest und Feedback finden Sie im Blogbeitrag [Aktualisierte Microsoft 365-Konnektivitätstest-POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) mit neuen Empfehlungen für netzwerkdesign. Informationen zu zukünftigen Updates für dieses Tool und anderen Microsoft 365-Netzwerkupdates werden im [Office 365-Netzwerkblog](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) veröffentlicht.
  
Hier ist ein kurzer Link, den Sie verwenden können, um zurück zu kommen: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 – Überblick über die Netzwerkkonnektivität](microsoft-365-networking-overview.md)

[Prinzipien von Microsoft 365-Netzwerkverbindungen](./microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Office 365 – IP-Adress- und URL-Webdienst](microsoft-365-ip-web-service.md)

[Microsoft 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)