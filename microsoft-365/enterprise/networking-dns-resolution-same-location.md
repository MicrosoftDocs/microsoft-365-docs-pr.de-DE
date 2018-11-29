---
title: 'Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Für eine bessere Leistung müssen Sie Ihre DNS-Auflösung nachvollziehen und konfigurieren können.
ms.openlocfilehash: 9ccd5c477b4aeda8e7dcf482cc09c8a357f19f40
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867576"
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
