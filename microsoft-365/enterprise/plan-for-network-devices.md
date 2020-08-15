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
description: 'Zusammenfassung: Beschreibung von Überlegungen zu Netzwerkkapazität, WAN-Beschleunigern und Lastenausgleichsgeräten, die zum Herstellen einer Verbindung mit Office 365 verwendet werden.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690535"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planen von Netzwerkgeräten, die eine Verbindung zu Office 365-Diensten herstellen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*
  
Einige Netzwerkhardware kann Einschränkungen hinsichtlich der Anzahl gleichzeitiger Sitzungen haben, die unterstützt werden. Für Organisationen mit mehr als 2.000 Benutzern wird empfohlen, dass Sie Ihre Netzwerkgeräte überwachen, um sicherzustellen, dass Sie den zusätzlichen Office 365 Dienst Datenverkehr verarbeiten können. Die SNMP-Überwachungssoftware (Simple Network Management Protocol) kann Ihnen dabei helfen.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune).

Lokale ausgehende Internet Proxyeinstellungen wirken sich auch auf die Konnektivität mit Office 365 Diensten für Ihre Clientanwendungen aus. Sie müssen auch Ihre Netzwerkproxy Geräte so konfigurieren, dass Verbindungen für Microsoft Cloud Services-URLs und-Anwendungen zugelassen werden. Jede Organisation ist anders. Um eine Vorstellung davon zu erhalten, wie Microsoft diesen Prozess verwaltet und wie viel Bandbreite wir bereitstellen, [Lesen Sie die Fallstudie](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
In den folgenden Skype for Business-Hilfeartikeln finden Sie weitere Informationen zu Skype for Business Einstellungen:
  
- [Problembehandlung bei Skype for Business Online Anmeldefehlern für Administratoren](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Sie können keine Verbindung mit Skype for Business herstellen oder bestimmte Features funktionieren nicht, da eine lokale Firewall die Verbindung blockiert.](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Während viele dieser Einstellungen Skype for Business spezifisch sind, ist die allgemeine Anleitung zur Netzwerkkonfiguration für alle Office 365 Dienste hilfreich.
  
## <a name="determining-network-capacity"></a>Bestimmen der Netzwerkkapazität

Jedes Netzwerkgerät, das in einer Verbindung vorhanden ist, hat seine Kapazitätsgrenze. Zu diesen Geräten gehören die Client-und Server Netzwerkadapter, Router, Switches und Hubs, die diese Geräte miteinander verbinden. Ausreichende Netzwerkkapazität bedeutet, dass keines von Ihnen ausgelastet ist. Die Überwachung der Netzwerkaktivität ist unerlässlich, um sicherzustellen, dass die tatsächlichen Lasten auf allen Netzwerkgeräten kleiner als ihre maximale Kapazität sind. Die Netzwerkkapazität wirkt sich auf die Leistung des Proxy Geräts aus.
  
In den meisten Fällen legt die Bandbreite der Internet Verbindung den Grenzwert für die Menge des Datenverkehrs fest. Die schwache Leistung während der Hauptverkehrszeiten wird wahrscheinlich durch eine übermäßige Nutzung der Internet Verbindung verursacht. Diese Situation gilt auch für ein Branch Office-Szenario, in dem Zweigstellenproxy Server Computer mit dem Proxygerät am Hauptsitz der Zweigniederlassung über eine langsame WAN-Verbindung (Wide Area Network) verbunden sind.
  
Überwachen Sie die Netzwerkaktivität auf der Proxy Netzwerkschnittstelle, um die Netzwerkkapazität zu testen. Wenn es mehr als 75 Prozent der maximalen Bandbreite einer beliebigen Netzwerkschnittstelle ist, sollten Sie die Bandbreite der Netzwerkinfrastruktur erhöhen, die unzureichend ist. Sie können auch erweiterte Funktionen wie HTTP-Komprimierung verwenden.
  
## <a name="wan-accelerators"></a>WAN-Beschleuniger

Wenn Ihre Organisation WAN-Beschleunigungs Proxy-Appliances verwendet, können Probleme auftreten, wenn Sie auf die Office 365 Dienste zugreifen. Möglicherweise müssen Sie Ihr Netzwerkgerät oder Ihre Geräte optimieren, um sicherzustellen, dass Ihre Benutzer beim Zugriff auf Office 365 eine konsistente Erfahrung haben. Beispielsweise verschlüsseln Office 365 Dienste einige Office 365 Inhalte und den TCP-Header. Ihr Gerät kann diese Art von Datenverkehr möglicherweise nicht verarbeiten.
  
Lesen Sie unsere Support-Anweisung zur [Verwendung des WAN Optimization Controllers oder der Datenverkehrs-/Inspektionsgeräte mit Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Hardware- und softwarebasierter Lastenausgleich

In Ihrer Organisation muss ein Hardwaregerät zum Lastenausgleich (HLB) oder eine NLB-Lösung (Network Lastenausgleich) verwendet werden, um Anforderungen an Ihre Active Directory Verbunddienste-Server (AD FS) und/oder Ihre Exchange-hybridserver zu verteilen. Lastenausgleichsgeräte steuern den Netzwerkdatenverkehr für die lokalen Server. Diese Server sind wichtig, um die Verfügbarkeit der einmaligen Anmeldung und der Exchange-hybridbereitstellung sicherzustellen.
  
Wir bieten eine softwarebasierte NLB-Lösung, die in Windows Server integriert ist. Diese Lösung wird von Office 365 zur Implementierung des Lastenausgleichs unterstützt.
  
## <a name="firewalls-and-proxies"></a>Firewalls und Proxys

Weitere Informationen zum Konfigurieren von Firewalls und Proxys für die Verbindung mit Office 365 finden Sie unter [Managing Office 365 Endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Bewertung Office 365 Netzwerkkonnektivität](assessing-network-connectivity.md)und [Office 365 Endpunkte](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) , um mehr über Geräte und schaltkreisauswahl zu erfahren.
  
## <a name="see-also"></a>Siehe auch

[Installationshandbücher für Office 365 Dienste](setup-guides-for-microsoft-365.md)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
