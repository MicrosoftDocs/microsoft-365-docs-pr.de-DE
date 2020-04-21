---
title: 'Schritt 3: Vermeiden von Spitzkehren für Netzwerke'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und entfernen Sie Spitzkehren für Netzwerke für eine bessere Leistung.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583425"
---
# <a name="step-3-avoid-network-hairpins"></a>Schritt 3: Vermeiden von Spitzkehren für Netzwerke

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 1: Vernetzung](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Eine [Netzwerkhaarnadel](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) liegt vor, wenn der an ein Ziel gerichtete Datenverkehr zuerst an einen weiteren Zwischenstandort umgeleitet wird, z. B. an einen lokalen Sicherheitsstapel, einen Cloudzugriffsbroker oder ein cloudbasiertes Webgateway. Hier ein Beispiel:

![Beispiel für eine Netzwerkhaarnadel](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

Eine Netzwerkhaarnadel kann auch durch unzureichendes Routing im Internet durch Netzwerkdienstanbieter verursacht werden. 

Eine Haarnadel fügt Latenz hinzu und kann potenziell den Datenverkehr an einen geografisch entfernten Standort umleiten.

Überprüfen Sie zum Optimieren der Leistung für den Datenverkehr zu cloudbasierten Microsoft 365-Diensten, ob der ISP, der die lokale Internetverbindung bereitstellt, über eine direkte Peering-Beziehung mit dem Microsoft Global Network in der Nähe dieses Ziels verfügt. Diese Verbindungen haben keine Spitzkehren.

Wenn Sie cloudbasierte Netzwerk- oder Sicherheitsdienste für Microsoft 365-Datenverkehr verwenden, stellen Sie sicher, dass der Spitzkehreneffekt ausgewertet und die Auswirkung auf die Leistung verstanden wird. Überprüfen Sie Folgendes:

- Anzahl und Ziele der Dienstanbieter, durch die der Datenverkehr in Beziehung zu Ihren Zweigstellen und Microsoft Global Network-Peering-Punkten weitergeleitet wird 
- Qualität der Netzwerk-Peering-Beziehung des Dienstanbieters mit Ihrem ISP und Microsoft 
- Leistungseinbußen von Backhauling in der Infrastruktur des Dienstanbieters

Wann immer möglich, konfigurieren Sie Ihre Edge-Router, um vertrauenswürdigen Microsoft 365-Datenverkehr direkt zu senden, statt ihn über eine Drittanbietercloud oder einen cloudbasierten Netzwerksicherheitsanbieterweiterzuleiten oder zu tunneln, der Ihren Internetdatenverkehr verarbeitet. 

![Beispiel für die Umgehung einer Netzwerkhaarnadel](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Um zu testen, wie nahe Sie sich an einem Einstiegspunkt zum globalen Microsoft-Netzwerk befinden, und wie nahe Sie sich an dem Punkt befinden, an dem das Netzwerk Ihrer Organisation mit Ihrem ISP verbunden ist, verwenden Sie das [Office 365 Network Onboarding-Tool](https://connectivity.office.com/).

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step3) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 4](../media/stepnumbers/Step4.png)|[Konfigurieren von Datenverkehrumgehungen](networking-configure-proxies-firewalls.md)|
