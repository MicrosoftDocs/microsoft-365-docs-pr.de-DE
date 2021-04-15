---
title: Häufig gestellte Fragen zur Geräteerkennung
description: Antworten auf häufig gestellte Fragen (FAQs) zur Geräteerkennung
keywords: Geräteerkennung, Ermittlung, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b3fef3479fa2d36806e6657b31f5152c54b9251f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764999"
---
# <a name="device-discovery-frequently-asked-questions"></a>Häufig gestellte Fragen zur Geräteerkennung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Hier finden Sie Antworten auf häufig gestellte Fragen (FAQs) zur Geräteerkennung.

## <a name="what-is-basic-discovery-mode"></a>Was ist der Basisermittlungsmodus?
Dieser Modus ermöglicht es jedem integrierten Microsoft Defender for Endpoint-Gerät, Netzwerkdaten zu sammeln und benachbarte Geräte zu ermitteln. Integrierte Endpunkte erfassen passiv Ereignisse im Netzwerk und extrahieren Geräteinformationen aus ihnen. Es wird kein Netzwerkdatenverkehr initiiert. Integrierte Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät angezeigt wird. Diese Daten werden zum Auflisten nicht verwalteter Geräte in Ihrem Netzwerk verwendet.

## <a name="can-i-disable-basic-discovery"></a>Kann ich die Grundlegende Ermittlung deaktivieren?
Sie haben die Möglichkeit, die Geräteerkennung über die Seite Erweiterte [Features zu](advanced-features.md) deaktivieren. Sie verlieren jedoch die Sichtbarkeit auf nicht verwalteten Geräten in Ihrem Netzwerk. 

## <a name="what-is-standard-discovery-mode"></a>Was ist der Standardermittlungsmodus?
 In diesem Modus können in Microsoft Defender for Endpoint integrierte Endpunkte beobachtete Geräte im Netzwerk aktiv austesten, um die gesammelten Daten (mit einer vernachlässigbaren Menge an Netzwerkdatenverkehr) zu bereichern. Dieser Modus wird dringend empfohlen, um einen zuverlässigen und zusammenhängenden Gerätebestand zu erstellen. Wenn Sie diesen Modus deaktivieren und den Basisermittlungsmodus auswählen, erhalten Sie wahrscheinlich nur eingeschränkte Sichtbarkeit nicht verwalteter Endpunkte in Ihrem Netzwerk.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Kann ich steuern, welche Geräte die Standarderkennung ausführen?
 Sie können die Liste der Geräte anpassen, die zum Ausführen der Standardermittlung verwendet werden. Sie können entweder die Standarderkennung auf allen integrierten Geräten aktivieren, die diese Funktion unterstützen (derzeit nur Windows 10-Geräte), oder Sie können eine Teilmenge oder Teilmenge Ihrer Geräte auswählen, indem Sie ihre Gerätetags angeben. In diesem Fall werden alle anderen Geräte so konfiguriert, dass nur die Grundlegende Ermittlung ausgeführt wird. Die Konfiguration ist auf der Seite Geräteermittlungseinstellungen verfügbar.

## <a name="which-onboarded-devices-can-perform-discovery"></a>Welche integrierten Geräte können die Ermittlung durchführen?
 Integrierte Geräte, die unter Windows 10, Version 1809 oder höher ausgeführt werden, können eine Ermittlung durchführen.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Was geschieht, wenn meine integrierten Geräte mit meinem Heimnetzwerk oder mit dem öffentlichen Zugriffspunkt verbunden sind?
 Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks. Durch korrelieren von Netzwerkbezeichnern für alle Mandantenclients werden Ereignisse zwischen Ereignissen unterschieden, die von privaten Netzwerken und Unternehmensnetzwerken empfangen wurden. Private Netzwerkgeräte werden nicht im Bestand aufgeführt und nicht aktiv untersucht.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Welche Protokolle erfassen und analysieren Sie?
 Standardmäßig erfassen und analysieren alle integrierten Geräte, die unter Windows 10, Version 1809 oder höher ausgeführt werden, die folgenden Protokolle: ARP, CDP, DHCP, DHCPv6, IP (Header), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (Header), UDP (Header), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Welche Protokolle verwenden Sie für aktives Sondieren in der Standarderkennung?
 Wenn ein Gerät für die Ausführung der Standardermittlung konfiguriert ist, werden verfügbar gemachte Dienste mithilfe der folgenden Protokolle untersucht: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Wie kann ich ausschließen, dass Ziele mit der Standarderkennung untersucht werden?
 Wenn ihr Netzwerk Geräte enthält, die nicht aktiv überprüft werden sollten, können Sie auch eine Liste von Ausschlüssen definieren, um zu verhindern, dass sie gescannt werden. Die Konfiguration ist auf der Seite Geräteermittlungseinstellungen verfügbar.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Kann ich ausschließen, dass Geräte erkannt werden?
 Da die Geräteermittlung passive Methoden zum Ermitteln von Geräten im Netzwerk verwendet, kann jedes Gerät, das mit Ihren integrierten Geräten im Unternehmensnetzwerk kommuniziert, ermittelt und im Inventar aufgeführt werden. Sie können Geräte nur von der aktiven Probe ausschließen.

## <a name="how-frequent-is-the-active-probing"></a>Wie häufig ist die aktive Probe?
 Geräte werden aktiv untersucht, wenn Änderungen der Gerätemerkmale (alle 1 bis 3 Wochen) beobachtet werden, um sicherzustellen, dass die vorhandenen Informationen auf dem neuesten Stand sind.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mein Sicherheitstool hat eine Warnung UnicastScanner.ps1 oder von diesem initiierten Portprüfungsaktivitäten ausgelöst. Was sollte ich tun?
 Die aktiven Probeskripts werden von Microsoft signiert und sind sicher. Sie können der Ausschlussliste den folgenden Pfad hinzufügen: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Wie viel Datenverkehr wird vom aktiven Test standard discovery generiert?
 Aktives Sondieren kann bis zu 5K Datenverkehr zwischen dem integrierten Gerät und dem testierten Gerät generieren, bei jedem Testversuch

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Warum besteht eine Diskrepanz zwischen "integrierten" Geräten im Gerätebestand und der Anzahl der "zu integrierende Geräte" in der Dashboardkachel?
Möglicherweise gibt es Unterschiede zwischen der Anzahl der aufgeführten Geräte unter "kann in das Geräteinventar integrierte" und der Sicherheitsempfehlung "Onboard to Microsoft Defender for Endpoint" und dem Dashboard-Widget "Geräte zum Onboarding" gesetzt werden.

 Die Sicherheitsempfehlung und das Dashboard-Widget sind für Geräte, die im Netzwerk stabil sind. ausgenommen kurzlebige Geräte, Gastgeräte und andere. Die Idee besteht in der Empfehlung für persistente Geräte, die auch auf die allgemeine Sicherheitsleistung der Organisation implizieren.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Kann ich nicht verwaltete Geräte integrieren, die gefunden wurden?
 Ja. Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk. Das Onboarding in den Dienst kann die Sichtbarkeit der Dienste erhöhen. 


