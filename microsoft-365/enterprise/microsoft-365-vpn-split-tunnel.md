---
title: Übersicht über geteilte VPN-Tunnel mit Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/3/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Anleitung zum Verwenden des geteilten VPN-Tunnels mit Office 365 zur Optimierung der Office 365-Konnektivität für Remotebenutzer.
ms.openlocfilehash: aad7932abb6b96a518b069ec24e836d2b5d234a1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696011"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe eines geteilten VPN-Tunnels
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Für Kunden, die Ihre Remotearbeitsgeräte mit dem Unternehmensnetzwerk oder der Cloudinfrastruktur über VPN verbinden, empfiehlt Microsoft, dass die wichtigsten Office 365-Szenarios **Microsoft Teams**, **SharePoint Online** und **Exchange Online** über eine _geteilte VPN-Tunnel_-Konfiguration umgeleitet werden. Dies wird besonders wichtig als Strategie zur Erleichterung der fortgesetzten Mitarbeiterproduktivität in Service und Produktion bei großmaßstäbiger Heimarbeit wie z. B. während der COVID-19-Krise.

![Split-Tunnel-VPN – Konfiguration](../media/vpn-split-tunneling/vpn-model-2.png)

_Abbildung 1: eine geteilte VPN-Tunnellösung mit definierten Office 365-Ausnahmen, die direkt an den Dienst gesendet werden. Aller anderer Datenverkehr durchläuft den VPN-Tunnel unabhängig vom Ziel._

Der Kern dieses Ansatzes besteht darin, Unternehmen eine einfache Methode bereitstellen, das Risiko einer Überlastung der VPN-Infrastruktur zu minimieren und die Leistung von Office 365 innerhalb kürzester Zeit erheblich zu verbessern. Wenn Sie VPN-Clients so konfigurieren, dass der kritischste und umfangreichste Office 365-Datenverkehr den VPN-Tunnel umgehen kann, werden die folgenden Vorteile erreicht:

- Schwächt die Grundursache für die Mehrzahl der vom Kunden gemeldeten Probleme mit der Leistungs- und Netzwerkkapazität in Unternehmens-VPN-Architekturen mit Auswirkungen auf die Office 365-Benutzeroberfläche sofort ab
  
  Die empfohlene Lösung zielt speziell auf die im Thema [Office 365-URLs und -IP-Adressbereiche](https://aka.ms/o365ips) als **Optimize** kategorisierten Office 365-Dienstendpunkte ab. Der Datenverkehr zu diesen Endpunkten ist in hohem Maße gegen Latenz und Bandbreiteneinschränkung empfindlich, und die Umgehung des VPN-Tunnels kann die Endbenutzererfahrung erheblich verbessern sowie die Netzwerklast des Unternehmens reduzieren. Office 365-Verbindungen, die nicht den größten Teil der Bandbreiten- oder der Benutzeroberflächenbasis bilden, können weiterhin mit dem restlichen Internet-gebundenen Datenverkehr durch den VPN-Tunnel geleitet werden. Weitere Informationen finden Sie unter [Die Strategie des geteilten VPN-Tunnels](#the-vpn-split-tunnel-strategy).

- Kann von Kunden schnell konfiguriert, getestet und implementiert werden, ohne dass zusätzliche Infrastruktur- oder Anwendungsanforderungen erforderlich sind

  Je nach VPN-Plattform und Netzwerkarchitektur dauert die Implementierung nur wenige Stunden. Weitere Informationen finden Sie unter [Implementieren eines geteilten VPN Tunnels](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Bewahrt die Sicherheitsposition von Kunden-VPN-Implementierungen, indem nicht geändert wird, wie andere Verbindungen umgeleitet werden, einschließlich Datenverkehr zum Internet

  Die empfohlene Konfiguration folgt dem Prinzip der **minimalen Rechte** für Ausnahmen von VPN-Datenverkehr und ermöglicht Kunden, geteilte VPN-Tunnel zu implementieren, ohne die Benutzer oder die Infrastruktur weiteren Sicherheitsrisiken auszusetzen. Der Netzwerkdatenverkehr, der direkt an Office 365-Endpunkte umgeleitet wird, wird für die Integrität durch die Office-Clientanwendungsstacks überprüft und auf IP-Adressen für Office 365-Dienste festgelegt, die sowohl auf Anwendungs- als auch auf Netzwerkebene verstärkt sind. Weitere Informationen hierzu finden Sie unter [Alternative Möglichkeiten für Sicherheitsexperten und IT-Mitarbeiter, moderne Sicherheitskontrollen in den heutigen einzigartigen Remotearbeitsszenarios zu erreichen (Blog des Microsoft Security Teams)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Wird von den meisten Unternehmens-VPN-Plattformen einheitlich unterstützt

  Microsoft arbeitet weiterhin mit Branchenpartnern an der Erstellung von kommerziellen VPN-Lösungen, um Partnern dabei zu helfen, gezielte Anleitungen und Konfigurationsvorlagen für ihre Lösungen in Übereinstimmung mit den oben aufgeführten Empfehlungen zu entwickeln. Weitere Informationen finden Sie unter [HOWTO-Leitfäden für häufige VPN-Plattformen](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft empfiehlt, die VPN-Konfiguration des geteilten Tunnels auf dokumentierte dedizierte IP-Bereiche für Office 365-Dienste zu konzentrieren. FQDN- oder AppID-basierte geteilte-Tunnel-Konfigurationen sind zwar auf bestimmten VPN-Clientplattformen möglich, decken jedoch möglicherweise wichtige Office 365-Szenarien nicht vollständig ab und können mit IP-basierten VPN-Routingregeln in Konflikt geraten. Aus diesem Grund empfiehlt Microsoft nicht die Verwendung von Office 365-FQDNs zum Konfigurieren des geteilten Tunnel-VPN. Die Verwendung der FQDN-Konfiguration kann in anderen verwandten Szenarien nützlich sein, z. B. bei der Anpassung von .PAC-Dateien oder bei der Implementierung der Proxyumgehung.

Vollständige Implementierungsanleitungen finden Sie unter [Implementierung eines geteilten VPN-Tunnels für Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="the-vpn-split-tunnel-strategy"></a>Die Strategie des geteilten VPN-Tunnels

Herkömmliche Unternehmensnetzwerke sind häufig so konzipiert, dass sie sicher für eine Pre-Cloudwelt arbeiten, in der die wichtigsten Daten, Dienste und Anwendungen lokal gehostet werden und direkt mit dem internen Unternehmensnetzwerk verbunden sind, ebenso wie die Mehrzahl der Benutzer. Die Netzwerkinfrastruktur basiert also auf diesen Elementen, in denen Zweigniederlassungen über _Multiprotocol Label Switching(MPLS)_-Netzwerke mit dem Hauptsitz verbunden sind und Remotebenutzer über ein VPN eine Verbindung mit dem Unternehmensnetzwerk herstellen müssen, um auf lokale Endpunkte und das Internet zugreifen zu können. Bei diesem Modell wird der gesamte Datenverkehr von Remotebenutzern durch das Unternehmensnetzwerk geleitet und über einen gemeinsamen Ausgangspunkt an den Clouddienst geleitet.

![Erzwungene VPN-Konfiguration](../media/vpn-split-tunneling/vpn-model-1.png)

_Abbildung 2: eine gemeinsame VPN-Lösung für Remotebenutzer, bei welcher der gesamte Datenverkehr unabhängig vom Bestimmungsort wieder in das Unternehmensnetzwerk gezwungen wird_

Da Unternehmen Daten und Anwendungen in die Cloud verlagern, ist dieses Modell weniger effektiv geworden, da es schnell umständlich, kostspielig und nicht skalierbar wird, die Netzwerkleistung und -effizienz der Benutzer erheblich beeinträchtigt und die Möglichkeit der Organisation einschränkt, sich den ändernden Anforderungen anzupassen. Zahlreiche Microsoft-Kunden haben berichtet, dass vor einigen Jahren 80 % des Netzwerkverkehrs an ein internes Ziel floss, aber im Jahr 2020 werden mehr als 80 % des Datenverkehrs mit einer externen cloudbasierten Ressource vernetzt.

Die COVID-19-Krise hat dieses Problem noch verschärft, so dass für die große Mehrheit der Organisationen sofortige Lösungen erforderlich sind. Viele Kunden haben festgestellt, dass das erzwungene VPN-Modell für ein Szenario 100%iger Remotearbeit, wie es diese Krise erforderlich gemacht hat, nicht skalierbar oder performant genug ist. Schnelle Lösungen sind erforderlich, damit diese Organisationen weiterhin effizient arbeiten können.

Für den Office 365-Dienst hat Microsoft die Konnektivitätsanforderungen für den Dienst genau auf dieses Problem ausgerichtet, wobei eine gezielte, streng kontrollierte und relativ statische Gruppe von Dienstendpunkten sehr einfach und schnell optimiert werden kann, um eine hohe Leistung für die Benutzer zu erzielen, die auf den Dienst zugreifen, und um die Belastung der VPN-Infrastruktur zu verringern, damit sie von dem Datenverkehr genutzt werden kann, der sie noch benötigt.

In Office 365 werden die erforderlichen Endpunkte für Office 365 in drei Kategorien kategorisiert: **Optimize**, **Allow** und **Default**. Die **Optimize**-Endpunkte stehen hier im Mittelpunkt und weisen die folgenden Merkmale auf:

- Sind Endgeräte im Besitz Microsoft und Verwalteten Endpunkten, auf der Microsoft-Infrastruktur gehostet?
- Sind für die Kernworkloads von Office 365 wie Exchange Online, SharePoint Online, Skype for Business Online und Microsoft Teams vorgesehen
- Lassen Sie IPs bereitstellen
- Geringe Änderungsrate, und es wird erwartet, dass die Zahl klein ist (zurzeit 20 IP-Subnetze)
- sind empfindlich gegen hohe Volumen und/oder Latenz
- können die erforderlichen Sicherheitselemente im Dienst anstatt inline im Netzwerk bereitstellen
- machen ungefähr 70–80 % der Datenmenge des Office 365-Diensts aus

Die festgelegten Endpunkte können auf den erzwungenen VPN-Tunnel aufgeteilt werden und über die lokale Benutzeroberfläche direkt an den Office 365-Dienst gesendet werden. Dies wird als **geteilter Tunnel** bezeichnet.

Sicherheitselemente, wie z. B. DLP, AV-Schutz, Authentifizierung und Zugriffssteuerung, können für diese Endpunkte auf verschiedenen Ebenen innerhalb des Diensts wesentlich effizienter bereitgestellt werden. Da auch der Großteil des Datenverkehrvolumens von der VPN-Lösung weggeleitet wird, setzt dies VPN-Kapazität für kritischen geschäftlichen Datenverkehr frei, der immer noch darauf angewiesen ist. Außerdem dürfte es in vielen Fällen nicht mehr notwendig sein, ein langwieriges und kostspieliges Aktualisierungsprogramm zu durchlaufen, um diese neue Arbeitsweise handhaben zu können.

![Konfiguration eines geteilten VPN-Tunnels](../media/vpn-split-tunneling/vpn-model-2.png)

_Abbildung 3: eine geteilte VPN-Tunnellösung mit definierten Office 365-Ausnahmen, die direkt an den Dienst gesendet werden. Aller anderer Datenverkehr wird unabhängig vom Ziel zurück in das Unternehmensnetzwerk gezwungen._

Aus der Sicherheitsperspektive verfügt Microsoft über eine Reihe von Sicherheitsfunktionen, die verwendet werden können, um eine ähnliche oder sogar verbesserte Sicherheit zu bieten als die, die durch eine Inline-Inspektion durch lokale Sicherheitsstapel erreicht wird. Der Blogbeitrag des Microsoft Security-Teams [Alternative Möglichkeiten für Sicherheitsexperten und IT-Mitarbeiter, moderne Sicherheitskontrollen in den heutigen, einzigartigen Remotearbeitsszenarios zu erreichen](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) bietet eine klare Zusammenfassung der verfügbaren Funktionen. Ausführlichere Anleitungen finden Sie in diesem Artikel. Über Microsofts Implementierung von geteilten VPN-Tunneling können Sie auch unter [Betrieb über VPN: Wie Microsoft seine Remotemitarbeiter in Verbindung hält](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) lesen.

In vielen Fällen kann diese Umsetzung innerhalb weniger Stunden erreicht werden, was eine rasche Lösung eines der dringendsten Probleme ermöglicht, mit denen Organisationen konfrontiert sind, wenn sie schnell großmaßstäbig auf Remotearbeit umstellen. Implementierungsanleitungen für den geteilten VPN-Tunnel finden Sie unter [Implementierung des geteilten VPN-Tunnels für Office 365](microsoft-365-vpn-implement-split-tunnel.md).

>[!NOTE]
>Microsoft hat sich verpflichtet, die Änderungen an den **Optimize**-Endpunkten für Office 365 bis mindestens **30. Juni 2020** einzustellen, damit sich die Kunden auf andere Herausforderungen konzentrieren können, anstatt die Endpunkt-Whitelist nach der ursprünglichen Implementierung beizubehalten.

## <a name="related-topics"></a>Verwandte Themen

[Implementieren eines geteilten VPN-Tunnels für Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Office 365-Leistungsoptimierung für Benutzer in China](microsoft-365-networking-china.md)

[Alternative Möglichkeiten für Sicherheitsexperten und IT-Mitarbeiter, moderne Sicherheitskontrollen in den heutigen einzigartigen Remotearbeitsszenarien zu erreichen (Blog des Microsoft Security Teams)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Verbessern der VPN-Leistung bei Microsoft: Verwenden von Windows 10-VPN-Profilen zur Aktivierung automatischer Verbindungen](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Betrieb über VPN: Wie Microsoft seine Remotemitarbeitern in Verbindung hält](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)

[Microsoft 365-Konnektivitätstest](https://aka.ms/netonboard)
