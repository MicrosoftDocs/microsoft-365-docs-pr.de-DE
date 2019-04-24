---
title: 'Schritt 3: Vermeiden von Spitzkehren für Netzwerke'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und entfernen Sie Spitzkehren für Netzwerke für eine bessere Leistung.
ms.openlocfilehash: eef8770dff6c54da51650b0fb70077fdd125f981
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291519"
---
# <a name="step-3-avoid-network-hairpins"></a>Schritt 3: Vermeiden von Spitzkehren für Netzwerke

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Eine [Spitzkehre für Netzwerke](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) tritt ein, wenn Datenverkehr für ein Ziel zunächst an ein anderes Zwischenziel geleitet wird, wie einen lokalen Sicherheitsstapel, einen Cloudzugriffsbroker oder ein cloudbasiertes Webgateway. Eine Spitzkehre für Netzwerke kann auch durch fehlerhaftes Routing im Internet aufgrund von Netzwerkdienstanbietern verursacht werden. Eine Spitzkehre sorgt für Latenz und kann Datenverkehr potenziell an ein geografisch entferntes Ziel umleiten.

Überprüfen Sie zum Optimieren der Leistung für den Datenverkehr zu cloudbasierten Microsoft 365-Diensten, ob der ISP, der die lokale Internetverbindung bereitstellt, über eine direkte Peering-Beziehung mit dem Microsoft Global Network in der Nähe dieses Ziels verfügt. Diese Verbindungen haben keine Spitzkehren.

Wenn Sie cloudbasierte Netzwerk- oder Sicherheitsdienste für Microsoft 365-Datenverkehr verwenden, stellen Sie sicher, dass der Spitzkehreneffekt ausgewertet und die Auswirkung auf die Leistung verstanden wird. Überprüfen Sie Folgendes:

- Anzahl und Ziele der Dienstanbieter, durch die der Datenverkehr in Beziehung zu Ihren Zweigstellen und Microsoft Global Network-Peering-Punkten weitergeleitet wird 
- Qualität der Netzwerk-Peering-Beziehung des Dienstanbieters mit Ihrem ISP und Microsoft 
- Leistungseinbußen von Backhauling in der Infrastruktur des Dienstanbieters

Wann immer möglich, konfigurieren Sie Ihre Edge-Router, um vertrauenswürdigen Microsoft 365-Datenverkehr direkt zu senden, statt ihn über eine Drittanbietercloud oder einen cloudbasierten Netzwerksicherheitsanbieterweiterzuleiten oder zu tunneln, der Ihren Internetdatenverkehr verarbeitet. 

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step3) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Konfigurieren von Datenverkehrumgehungen](networking-configure-proxies-firewalls.md)|
