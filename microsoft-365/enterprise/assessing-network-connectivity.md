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
description: Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt eine Verbindung mit dem Dienst über eine Internetverbindung herstellen können. Während sich der Dienst entwickelt, werden Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690680"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Bewerten der Microsoft 365-Netzwerkkonnektivität

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist so konzipiert, dass Kunden auf der ganzen Welt eine Verbindung mit dem Dienst über eine Internetverbindung herstellen können. Während sich der Dienst entwickelt, werden Sicherheit, Leistung und Zuverlässigkeit von Microsoft 365 basierend auf Kunden verbessert, die das Internet verwenden, um eine Verbindung mit dem Dienst herzustellen.
  
Kunden, die Microsoft 365 verwenden möchten, sollten Ihre vorhandenen und prognostizierten Anforderungen an die Internetkonnektivität als Teil des Bereitstellungsprojekts bewerten. Für die Bereitstellung von Unternehmensklassen ist eine zuverlässige und entsprechend große Internetverbindung ein wichtiger Bestandteil des Verbrauchs von Microsoft 365-Features und-Szenarien.
  
Netzwerk Auswertungen können je nach Größe und Einstellungen von vielen verschiedenen Personen und Organisationen ausgeführt werden. Der Netzwerkbereich der Bewertung kann auch variieren, je nachdem, wo Sie sich im Bereitstellungsprozess befinden. Damit Sie besser verstehen, was zum Durchführen einer Netzwerkbewertung benötigt wird, haben wir einen Leitfaden zur Netzwerkbewertung erstellt, um Ihnen die verfügbaren Optionen näher zu bringen. Mit dieser Bewertung wird bestimmt, welche Schritte und Ressourcen dem Bereitstellungsprojekt hinzugefügt werden müssen, damit Sie Microsoft 365 erfolgreich implementieren können.
  
Durch eine umfassende Netzwerkbewertung werden mögliche Lösungen für Herausforderungen im Zusammenspiel mit dem Netzwerk Design sowie Implementierungsdetails bereitgestellt. Einige Netzwerkbewertungen zeigen, dass die optimale Netzwerkverbindung mit Microsoft 365 mit kleineren Konfigurations-oder Entwurfsänderungen an der vorhandenen Netzwerk-und Internet Ausgangs Infrastruktur untergebracht werden kann.

Einige Bewertungen deuten darauf hin, dass die Netzwerkverbindung mit Microsoft 365 zusätzliche Investitionen in Netzwerkkomponenten erfordert. Unternehmensnetzwerke, die Zweigniederlassungen und mehrere geografische Regionen umfassen, benötigen möglicherweise Investitionen in SD-WAN-Lösungen oder eine optimierte Routinginfrastruktur zur Unterstützung der Internetkonnektivität mit Microsoft 365. Gelegentlich wird in einer Bewertung darauf hingewiesen, dass die Netzwerkverbindung mit Microsoft 365 von den Vorschriften oder Leistungsanforderungen für Szenarien wie [Skype for Business Online Medienqualität](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)beeinflusst wird. Diese zusätzlichen Anforderungen können zu Investitionen in die Infrastruktur für die Internetkonnektivität, die Routing Optimierung und die spezielle direkte Konnektivität führen.

Einige Ressourcen, die Ihnen bei der Bewertung Ihres Netzwerks helfen:

- Konzeptionelle Informationen zum Microsoft 365-Netzwerk finden Sie unter Übersicht über die [Microsoft 365-Netzwerkkonnektivität](microsoft-365-networking-overview.md) .
- Informationen zu den Verbindungs Prinzipien für die sichere Verwaltung von Microsoft 365-Datenverkehr und optimale Leistung erhalten Sie unter [Microsoft 365 Network Connectivity Principles](https://aka.ms/o365networkingprinciples) .
- Registrieren Sie sich für [Microsoft](https://www.microsoft.com/fasttrack) kurzpanne, um Unterstützung bei der Planung, Entwicklung und Bereitstellung von Microsoft 365 zu erhalten. 
- Lesen Sie den Abschnitt [Microsoft 365 Connectivity Test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) , um grundlegende Verbindungstests auszuführen, die spezifische Hinweise zur Verbesserung der Netzwerkkonnektivität bieten, die zwischen einem bestimmten Benutzerstandort und Microsoft 365 hergestellt werden kann.

> [!NOTE]
> Microsoft Authorization ist für die Verwendung von Express Route für Office 365 erforderlich. Microsoft überprüft alle Kundenanforderungen und autorisiert Express Route nur für Office 365 Nutzung, wenn die regulatorische Anforderung eines Kunden eine direkte Konnektivität erfordert. Wenn Sie solche Anforderungen haben, stellen Sie bitte den Textauszug und den Weblink der von Ihnen interpretierten Richtlinie bereit, damit die direkte Konnektivität im [Express Route für Office 365 Anforderungsformular](https://aka.ms/O365ERReview) zum Starten einer Microsoft-Überprüfung erforderlich ist. Nicht autorisierte Abonnements, die versuchen, Routenfilter für Office 365 zu erstellen, erhalten eine [Fehlermeldung](https://support.microsoft.com/kb/3181709).
  
Wichtige Punkte, die bei der Planung Ihrer Netzwerkbewertung für Microsoft 365 zu berücksichtigen sind:
  
- Microsoft 365 ist ein sicherer, zuverlässiger Dienst mit hoher Leistung, der über das öffentliche Internet ausgeführt wird. Wir investieren weiterhin, um diese Aspekte des Diensts zu verbessern. Alle Microsoft 365-Dienste sind über Internetkonnektivität verfügbar.

- Wir optimieren kontinuierlich Kernaspekte von Microsoft 365 wie Verfügbarkeit, globale Reichweite und Leistung für internetbasierte Konnektivität. Beispielsweise nutzen viele Microsoft 365-Dienste eine wachsende Gruppe von Edge-Knoten mit Internetzugriff. Dieses Edge-Netzwerk bietet die beste Nähe und Leistung für Verbindungen, die über das Internet kommen.

- Bei der Verwendung von Microsoft 365 für alle enthaltenen Dienste wie Teams oder Skype for Business online sprach-, Video-oder Besprechungsfunktionen sollten Kunden eine End-to-End-Netzwerkbewertung durchführen und die Verbindungsanforderungen mit [Microsoft](https://www.microsoft.com/fasttrack)Kurzfilm erfüllen.

Wenn Sie Microsoft 365 bewerten und nicht sicher sind, wo Sie mit ihrer Netzwerkbewertung beginnen oder Herausforderungen im Zusammenfall mit dem Netzwerk Design gefunden haben, die Sie unterstützen müssen, wenden Sie sich an Ihr Microsoft-Konto Team.

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 Connectivity Test

Der [Microsoft 365 Connectivity Test](https://aka.ms/netonboard) ist ein Machbarkeits-Netzwerk Bewertungstool (Proof of Concept), das grundlegende Verbindungstests für Ihren Microsoft 365-Mandanten ausführt und spezifische Empfehlungen für das Netzwerk Design für eine optimale Leistung von Microsoft 365 stellt. Das Tool hebt allgemeine Entwurfsentscheidungen für große Enterprise-Netzwerkperimeter hervor, die für das Surfen im Internet nützlich sind, wirkt sich jedoch auf die Leistung großer SaaS-Anwendungen wie Microsoft 365 aus.

Das Onboarding-Tool für das Netzwerk führt folgende Schritte aus:

- Ermittelt ihren Standort oder Sie können einen Test Speicherort angeben
- Überprüft den Speicherort Ihres Netzwerk Ausstiegs.
- Testet den Netzwerkpfad auf die nächste Microsoft 365-Dienst Haustür
- Bietet erweiterte Tests mit einer herunterladbaren Windows 10-Anwendung, die Empfehlungen zum Entwurf des Umkreisnetzwerks in Bezug auf Proxy Server, Firewalls und DNS macht. Das Tool führt auch Leistungstests für Skype for Business Online, Microsoft Teams, SharePoint Online und Exchange Online aus.

Das Tool verfügt über zwei Komponenten: eine browserbasierte Benutzeroberfläche, die grundlegende Verbindungsinformationen sammelt, und eine herunterladbare Windows 10-Anwendung, die erweiterte Tests ausführt und zusätzliche Bewertungsdaten zurückgibt.

Das browserbasierte Tool zeigt die folgenden Informationen an:

- Registerkarte "Ergebnisse und Auswirkungen"
  - Der Ort auf der Karte der Haustür des in-use-Diensts
  - Der Ort auf einer Karte mit anderen Dienst Fronttüren, die eine optimale Konnektivität bieten würde
  - Relative Leistung im Vergleich zu anderen Microsoft 365-Kunden in Ihrer Nähe
- Registerkarte "Details und Lösungen"
  - Benutzerstandort nach Ort und Land
  - Netzwerk Ausgangsstandort nach Stadt, Staat und Land
  - Abstand von Benutzer zu Netzwerk Ausgang
  - Front-Door-Standort von Microsoft 365 Exchange Online-Dienst
  - Optimale Microsoft 365 Exchange Online-Dienst-Haustür (en) für den Benutzerstandort
  - Kunden in ihrer Metro-Region mit besserer Leistung

Die herunterladbare Anwendung für erweiterte Tests bietet die folgenden zusätzlichen Informationen:

- Registerkarte "Details und Lösungen" (angehängt)
  - Standardgateway des Benutzers
  - Client-DNS-Server
  - Client-DNS-rekursive Auflösung
  - Exchange Online DNS-Server
  - SharePoint Online DNS-Server
  - Proxy Serveridentifikation
  - Überprüfung der Medien Konnektivität
  - Paketverlust für Medienqualität
  - Wartezeit für Medienqualität
  - Jitter der Medienqualität
  - Neuordnen von Medien Qualitäts Paketen
- Verbindungstests zu mehreren funktionsspezifischen Endpunkten
- Netzwerkpfad Diagnose, die tracert-und Latenz Daten für die Exchange Online, SharePoint Online und Microsoft Teams-Dienste enthält

Sie können den Microsoft 365-Konnektivitäts Test lesen und Feedback zum [aktualisierten Microsoft 365 Connectivity Test POC mit dem Blogbeitrag "neue Netzwerk Design Empfehlungen](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) " bereitstellen. Informationen zu zukünftigen Updates für dieses Tool und andere Microsoft 365-Netzwerk Updates werden im Blog [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) veröffentlicht.
  
Hier ist ein kurzer Link, den Sie verwenden können, um zurückzukehren: [ https://aka.ms/o365networkconnectivity .](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 – Überblick über die Netzwerkkonnektivität](microsoft-365-networking-overview.md)

[Prinzipien von Microsoft 365-Netzwerkverbindungen](https://aka.ms/o365networkingprinciples)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Office 365 – IP-Adress- und URL-Webdienst](microsoft-365-ip-web-service.md)

[Microsoft 365 Netzwerk-und Leistungsoptimierung](network-planning-and-performance.md)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
