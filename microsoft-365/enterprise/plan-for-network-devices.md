---
title: Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Zusammenfassung: Beschreibt Überlegungen zu Netzwerkkapazität, WAN-Zugriffstasten und Lastenausgleichsgeräten, die zum Herstellen einer Verbindung mit Office 365.'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927500"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*
  
Einige Netzwerkhardware kann Einschränkungen hinsichtlich der Anzahl gleichzeitiger Sitzungen haben, die unterstützt werden. Organisationen mit mehr als 2.000 Benutzern empfehlen, ihre Netzwerkgeräte zu überwachen, um sicherzustellen, dass sie den zusätzlichen Datenverkehr Office 365 können. Die Software zur Überwachung des einfachen Netzwerkverwaltungsprotokolls (Simple Network Management Protocol, SNMP) kann Ihnen dabei helfen.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)

Lokale Einstellungen für ausgehende Internetproxys wirken sich auch auf die Konnektivität mit Office 365 Für Ihre Clientanwendungen aus. Außerdem müssen Sie Ihre Netzwerkproxygeräte so konfigurieren, dass Verbindungen für URLs und Anwendungen von Microsoft Cloud Services zulässig sind. Jede Organisation ist anders. Eine Vorstellung davon, wie Microsoft diesen Prozess verwaltet und wie viel Bandbreite wir bereitstellen, erhalten Sie in der [Fallstudie](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Die folgenden Skype for Business Hilfeartikel enthalten weitere Informationen zu Skype for Business Einstellungen:
  
- [Problembehandlung Skype for Business Online-Anmeldefehlern für Administratoren](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Sie können keine Verbindung Skype for Business, oder bestimmte Features funktionieren nicht, da eine lokale Firewall die Verbindung blockiert.](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Während viele dieser Einstellungen Skype for Business sind, ist die allgemeine Anleitung zur Netzwerkkonfiguration für alle Office 365 nützlich.
  
## <a name="determining-network-capacity"></a>Bestimmen der Netzwerkkapazität

Jedes Netzwerkgerät, das in einer Verbindung vorhanden ist, hat seine Kapazitätsbeschränkung. Zu diesen Geräten gehören die Client- und Servernetzwerkadapter, Router, Switches und Hubs, die sie miteinander verbinden. Eine ausreichende Netzwerkkapazität bedeutet, dass keines davon gesättigt ist. Die Überwachung der Netzwerkaktivität ist wichtig, um sicherzustellen, dass die tatsächlichen Lasten auf allen Netzwerkgeräten kleiner als ihre maximale Kapazität sind. Die Netzwerkkapazität wirkt sich auf die Leistung des Proxygeräts aus.
  
In den meisten Situationen legt die Bandbreite der Internetverbindung den Grenzwert für den Datenverkehr fest. Eine schwache Leistung während der Spitzenzeiten des Datenverkehrs wird wahrscheinlich durch die übermäßige Nutzung der Internetverbindung verursacht. Diese Situation gilt auch für ein Zweigstellenszenario, in dem Proxyservercomputer von Zweigstellen über eine langsame WAN-Verbindung mit dem Proxygerät an der Zweigstellenzentrale verbunden sind.
  
Überwachen Sie zum Testen der Netzwerkkapazität die Netzwerkaktivität auf der Proxynetzwerkschnittstelle. Wenn es mehr als 75 Prozent der maximalen Bandbreite einer Netzwerkschnittstelle ist, sollten Sie die Bandbreite der unzureichenden Netzwerkinfrastruktur erhöhen. Sie können auch erweiterte Features wie die HTTP-Komprimierung verwenden.
  
## <a name="wan-accelerators"></a>WAN-Beschleuniger

Wenn Ihre Organisation WAN-Beschleunigungsproxy-Appliances (Wide Area Network) verwendet, können Probleme auftreten, wenn Sie auf die Office 365 zugreifen. Möglicherweise müssen Sie Ihr Netzwerkgerät oder Ihre Geräte optimieren, um sicherzustellen, dass Ihre Benutzer eine konsistente Benutzererfahrung beim Zugriff auf Office 365. Beispielsweise verschlüsseln Office 365 Dienste einige Office 365 und den TCP-Header. Ihr Gerät kann diesen Datenverkehr möglicherweise nicht verarbeiten.
  
Lesen Sie unsere Support-Anweisung zum [Verwenden des WAN-Optimierungscontrollers oder von Datenverkehrs-/Inspektionsgeräten mit Office 365.](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>Hardware- und softwarebasierter Lastenausgleich

Ihre Organisation muss einen Hardwaregerät zum Lastenausgleich (Hardware Load Balancer, HLB) oder eine Netzwerklastenausgleichslösung (Network Load Balancing, NLB) verwenden, um Anforderungen an Ihre Ad #A0 (Active Directory Federation Services) und/oder Ihre Exchange verteilen. Lastenausgleichsgeräte steuern den Netzwerkdatenverkehr zu den lokalen Servern. Diese Server sind entscheidend für die Sicherstellung der Verfügbarkeit von einmaligem Anmelden und Exchange Hybridbereitstellung.
  
Wir bieten eine softwarebasierte NLB-Lösung, die in Windows ist. Diese Lösung wird von Office 365 zur Implementierung des Lastenausgleichs unterstützt.
  
## <a name="firewalls-and-proxies"></a>Firewalls und Proxys

Weitere Informationen zum Konfigurieren von Firewalls und Proxys für die Verbindung mit Office 365 finden Sie unter [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Assessing Office 365 network connectivity](assessing-network-connectivity.md)und Office 365 [endpoints FAQ,](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) um mehr über Geräte und die Auswahl von Schaltungen zu erfahren.
  
## <a name="see-also"></a>Siehe auch

[Setupanleitungen für Office 365 Dienste](setup-guides-for-microsoft-365.md)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)