---
title: 'Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Für eine bessere Leistung müssen Sie Ihre DNS-Auflösung nachvollziehen und konfigurieren können.
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073265"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Stellen Sie in Schritt 2 sicher, dass jedes Ihrer Büros über eine lokale Internetverbindung verfügt und lokale DNS-Server verwendet. Beides ist erforderlich, um Verbindungslatenz zu reduzieren und sicherzustellen, dass lokale Clientcomputer Verbindungen zum nächsten Einstiegspunkt für cloudbasierte Microsoft 365-Dienste herstellen.

In herkömmlichen Netzwerken für große Organisationen läuft der Internetdatenverkehr über das Netzwerk-Backbone zu einer zentralen Internetverbindung. Dies funktioniert nicht gut, um die Leistung auf eine global verteilte Software-as-a-Service-Infrastruktur (SaaS) zu optimieren, die die Office 365- und Enterprise Mobility + Security(EMS)-Produkte in Microsoft 365 enthält.

Das Microsoft Global Network beinhaltet Front-End-Server zu den Clouddiensten für Microsoft 365 weltweit. Die beste Leistung wird erzielt, wenn lokale Clients auf einen Front-End-Server zugreifen, der ihnen geografisch am nächsten ist, statt Datenverkehr über ein Netzwerk-Backbone und zum Front-End-Server zu senden, der am nächsten zur zentralen Internetverbindung der Organisation ist.

Um eine Clientanforderung an den geografisch nächsten Front-End-Server zu leiten, verwenden die DNS-Server von Microsoft die DNS-Abfragen, die der anfänglichen Verbindungsanforderung des Clients entsprechen. Daher gilt für die niedrigste Netzwerklatenz Folgendes:

- Alle Büros Ihrer Organisation sollten eine lokale Internetverbindung für den Netzwerkdatenverkehr der Kategorie [Optimieren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) haben.
- Jede lokale Internetverbindung sollte einen regionalen DNS-Server für ausgehenden Internetdatenverkehr von diesem Ort verwenden.

Weitere Informationen finden Sie unter [Lokaler Ausgang von Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step2) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Vermeiden von Spitzkehren für Netzwerke](networking-avoid-network-hairpins.md)|
