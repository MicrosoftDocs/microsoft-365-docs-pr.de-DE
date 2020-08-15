---
title: Azure ExpressRoute für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
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
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: In diesem Artikel erfahren Sie, wie Sie Azure Express Route mit Office 365 verwenden und das Netzwerk Implementierungsprojekt planen, wenn Sie es mit bereitstellen.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690274"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Erfahren Sie, wie Azure Express Route mit Office 365 verwendet wird und wie das Netzwerk Implementierungsprojekt geplant wird, das erforderlich ist, wenn Sie Azure Express Route für die Verwendung mit Office 365 bereitstellen. Infrastruktur-und Plattformdienste, die in Azure betrieben werden, profitieren häufig von der Behebung von Netzwerkarchitektur und Leistungsüberlegungen. In diesen Fällen wird Express Route für Azure empfohlen. Software als Service Angebote wie Office 365 und Dynamics 365 wurden für den sicheren und zuverlässigen Zugriff über das Internet entwickelt. Sie können sich über Internet Leistung und Sicherheit informieren, und wann Sie Azure Express Route für Office 365 im Artikel [bewerten von Office 365 Netzwerkkonnektivität](assessing-network-connectivity.md)in Frage stellen sollten.

> [!NOTE]
> Microsoft Authorization ist für die Verwendung von Express Route für Office 365 erforderlich. Microsoft überprüft alle Kundenanforderungen und autorisiert Express Route für Office 365 Nutzung, wenn die regulatorische Anforderung eines Kunden eine direkte Konnektivität erfordert. Wenn Sie solche Anforderungen haben, stellen Sie bitte den Textauszug und den Weblink der von Ihnen interpretierten Richtlinie bereit, damit die direkte Konnektivität im [Express Route für Office 365 Anforderungsformular](https://aka.ms/O365ERReview) zum Starten einer Microsoft-Überprüfung erforderlich ist. Nicht autorisierte Abonnements, die versuchen, Routenfilter für Office 365 zu erstellen, erhalten eine [Fehlermeldung](https://support.microsoft.com/kb/3181709).

Sie können nun eine direkte Netzwerkverbindung zu Office 365 für ausgewählte Office 365 Netzwerkdatenverkehr hinzufügen. Azure Express Route bietet eine direkte Verbindung, eine vorhersagbare Leistung und verfügt über eine Verfügbarkeits SLA von 99,95% für die Microsoft-Netzwerkkomponenten. Sie benötigen weiterhin eine Internetverbindung für Dienste, die nicht über Azure Express Route unterstützt werden.

## <a name="planning-azure-expressroute-for-office-365"></a>Planen von Azure Express Route für Office 365

Zusätzlich zur Internetkonnektivität können Sie eine Teilmenge Ihres Office 365 Netzwerkdatenverkehrs über eine direkte Verbindung weiterleiten, die Vorhersagbarkeit bietet, und eine Verfügbarkeits-SLA von 99,95% für die Microsoft-Netzwerkkomponenten. Azure Express Route bietet Ihnen diese dedizierte Netzwerkverbindung mit Office 365 und anderen Microsoft Cloud-Diensten.

Unabhängig davon, ob Sie über ein vorhandenes MPLS-WAN verfügen, können Express Route Ihrer Netzwerkarchitektur auf eine von drei Arten hinzugefügt werden. über einen unterstützten Cloud Exchange-Co-Location-Anbieter, einen Ethernet-Punkt-zu-Punkt-Verbindungsanbieter oder einen MPLS-Verbindungsanbieter. Sehen Sie, welche [Anbieter in Ihrer Region verfügbar sind](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Die direkte Express Route-Verbindung ermöglicht die Konnektivität mit den Anwendungen, die unter [What Office 365 Services enthalten sind?](azure-expressroute.md#BKMK_WhatDoIGet) weiter unten beschrieben werden. Der Netzwerkdatenverkehr für alle anderen Anwendungen und Dienste wird weiterhin im Internet durchlaufen.

Sehen Sie sich das folgende Netzwerkdiagramm auf hoher Ebene an, das eine typische Office 365 Kunden darstellt, die über das Internet eine Verbindung mit den Rechenzentren von Microsoft herstellen, um auf alle Microsoft-Anwendungen wie Office 365, Windows Update und TechNet zuzugreifen. Kunden verwenden einen ähnlichen Netzwerkpfad unabhängig davon, ob Sie über ein lokales Netzwerk oder über eine unabhängige Internetverbindung eine Verbindung herstellen möchten.

![Office 365 Netzwerkkonnektivität](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Sehen Sie sich nun das aktualisierte Diagramm an, in dem ein Office 365-Kunde dargestellt wird, der sowohl das Internet als auch Express Route verwendet, um eine Verbindung mit Office 365 herzustellen. Beachten Sie, dass einige Verbindungen wie öffentliche DNS-und Inhalts Zustellungs Netzwerkknoten weiterhin die öffentliche Internetverbindung benötigen. Beachten Sie auch, dass die Benutzer des Kunden, die sich nicht in Ihrem Express Route-verbundenen Gebäude befinden, über das Internet eine Verbindung herstellen.

![Office 365 Konnektivität mit Express Route](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Möchten Sie noch weitere Informationen? In diesem Artikel erfahren Sie, wie [Sie Ihren Netzwerkdatenverkehr mit Azure Express Route für Office 365 verwalten](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) und wie Sie [Azure Express Route für Office 365 konfigurieren](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Wir haben auch eine 10-teilige [Azure Express Route für Office 365-Schulungs](https://channel9.msdn.com/series/aer) Reihe auf Kanal 9 aufgezeichnet, um die Konzepte gründlicher zu erläutern.

## <a name="what-office-365-services-are-included"></a>Welche Office 365 Dienste sind enthalten?
<a name="BKMK_WhatDoIGet"> </a>

In der folgenden Tabelle sind die Office 365 Dienste aufgeführt, die über Express Route unterstützt werden. Lesen Sie den [Artikel Office 365 Endpunkte](https://aka.ms/o365endpoints) , um zu verstehen, welche Netzwerkanforderungen für diese Anwendungen eine Internetverbindung erfordern.

|**Eingeschlossene Anwendungen**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Schutz<sup>1</sup> <br/> Eintauchen<sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive für Unternehmen<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal und Shared<sup>1</sup> <br/> Azure-Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> für jede dieser Anwendungen sind Internet Verbindungsanforderungen nicht unterstützt über Express Route, weitere Informationen finden Sie im [Artikel Office 365 Endpunkte](https://aka.ms/o365endpoints) .

Die Dienste, die für Office 365 nicht in Express Route enthalten sind, sind Microsoft 365-Apps für Enterprise-Clientdownloads, die lokale Identitätsanbieter Anmeldung und Office 365 (betrieben von 21 vianet) in China.

## <a name="implementing-expressroute-for-office-365"></a>Implementieren von ExpressRoute für Office 365

Die Implementierung von Express Route erfordert die Einbindung von Netzwerk-und Anwendungsbesitzern und erfordert eine sorgfältige Planung, um die neue [Netzwerk Weiterleitungs Architektur](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), die Bandbreitenanforderungen, die Implementierung der Sicherheit, die hohe Verfügbarkeit usw. zu ermitteln. Zur Implementierung von Express Route müssen Sie Folgendes tun:

1. Vollständiges Verständnis der Anforderungen, die Express Route in ihrer Planung für Office 365 Konnektivität erfüllt. Erfahren Sie, welche Anwendungen das Internet oder Express Route verwenden, und planen Sie Ihre Netzwerkkapazität, Sicherheit und hohe Verfügbarkeit im Zusammenhang mit der Verwendung von Internet und Express Route für Office 365 Datenverkehr vollständig.

2. Ermitteln Sie die Ausgangs-und Peering-Speicherorte für Internet-und Express Route-Datenverkehr<sup>1</sup>.

3. Ermitteln Sie die Kapazität, die für die Internet-und Express Route-Verbindungen erforderlich ist.

4. Verfügen über einen Plan zur Implementierung von Sicherheit und anderen standardmäßigen Umkreis Steuerungen<sup>1</sup>.

5. Verfügen über ein gültiges Microsoft Azure Konto zum Abonnieren von Express Route.

6. Wählen Sie ein Verbindungsmodell und einen [genehmigten Anbieter](https://azure.microsoft.com/documentation/articles/expressroute-locations/)aus. Beachten Sie, dass Kunden mehrere Verbindungs Modelle oder Partner auswählen können und der Partner nicht mit dem vorhandenen Netzwerkanbieter übereinstimmen muss.

7. Überprüfen der Bereitstellung vor der Weiterleitung des Datenverkehrs an Express Route.

8. Implementieren Sie optional [QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) , und bewerten Sie die regionale Expansion.

<sup>1</sup> wichtige Überlegungen zur Leistung. Die hier getroffenen Entscheidungen können die Wartezeit erheblich beeinträchtigen, was für Anwendungen wie Skype for Business von entscheidender Bedeutung ist.

Weitere Verweise finden Sie in unserem [Routing Leit Faden](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) zusätzlich zur [Express Route-Dokumentation](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Um Express Route für Office 365 zu erwerben, müssen Sie mit einem oder mehreren [zugelassenen Anbietern](https://azure.microsoft.com/documentation/articles/expressroute-locations/) zusammenarbeiten, um die gewünschten Zahlen-und Größen Schaltkreise mit einem Express Route Premium-Abonnement bereitzustellen. Es gibt keine zusätzlichen Lizenzen, die bei Office 365 erworben werden können.

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Möchten Sie sich für [Express Route für Office 365](https://aka.ms/ert)anmelden?

## <a name="related-topics"></a>Verwandte Themen

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)

[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)

[Routing mit ExpressRoute für Office 365](routing-with-expressroute.md)

[Netzwerkplanung mit ExpressRoute für Office 365](network-planning-with-expressroute.md)

[Implementierung von ExpressRoute für Office 365](implementing-expressroute.md)

[Verwenden von BGP-Communities in Express Route für Office 365 Szenarien](bgp-communities-in-expressroute.md)

[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)

[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
