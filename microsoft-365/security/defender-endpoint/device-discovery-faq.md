---
title: Häufig gestellte Fragen zur Geräteermittlung
description: Hier finden Sie Antworten auf häufig gestellte Fragen (FAQs) zur Geräteermittlung
keywords: Geräteermittlung, entdecken, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
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
ms.openlocfilehash: b2c0b986ef6dbb54cd34e9b4413711cd3e5f9c6d
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053155"
---
# <a name="device-discovery-frequently-asked-questions"></a>Häufig gestellte Fragen zur Geräteermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Hier finden Sie Antworten auf häufig gestellte Fragen (FAQs) zur Geräteermittlung.

## <a name="what-is-basic-discovery-mode"></a>Was ist der Grundlegende Ermittlungsmodus?
Dieser Modus ermöglicht es jedem integrierten Microsoft Defender für Endpunkt-Gerät, Netzwerkdaten zu sammeln und benachbarte Geräte zu ermitteln. Integrierte Endpunkte sammeln passiv Ereignisse im Netzwerk und extrahieren Geräteinformationen daraus. Es wird kein Netzwerkdatenverkehr initiiert. Integrierte Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät erkannt wird. Diese Daten dienen zum Auflisten nicht verwalteter Geräte in Ihrem Netzwerk.

## <a name="can-i-disable-basic-discovery"></a>Kann ich die Grundlegende Ermittlung deaktivieren?
Sie haben die Möglichkeit, die Geräteermittlung über die Seite ["Erweiterte Features"](advanced-features.md) zu deaktivieren. Sie verlieren jedoch die Sichtbarkeit auf nicht verwalteten Geräten in Ihrem Netzwerk. 

## <a name="what-is-standard-discovery-mode"></a>Was ist der Standardermittlungsmodus?
 In diesem Modus können Endpunkte, die in Microsoft Defender für Endpunkt integriert sind, beobachtete Geräte im Netzwerk aktiv untersuchen, um gesammelte Daten (mit geringem Netzwerkdatenverkehr) zu erweitern. Dieser Modus wird dringend empfohlen, um einen zuverlässigen und konsistenten Gerätebestand zu erstellen. Wenn Sie diesen Modus deaktivieren und den Grundlegenden Ermittlungsmodus auswählen, erhalten Sie wahrscheinlich nur eingeschränkte Sichtbarkeit von nicht verwalteten Endpunkten in Ihrem Netzwerk.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Kann ich steuern, welche Geräte die Standardermittlung durchführen?
 Sie können die Liste der Geräte anpassen, die für die Standardermittlung verwendet werden. Sie können die Standardermittlung auf allen integrierten Geräten aktivieren, die diese Funktion ebenfalls unterstützen (derzeit nur Windows 10 Geräte) oder eine Teilmenge oder Teilmenge Ihrer Geräte auswählen, indem Sie deren Gerätetags angeben. In diesem Fall werden alle anderen Geräte so konfiguriert, dass nur die Basic Discovery ausgeführt wird. Die Konfiguration ist auf der Seite mit den Geräteermittlungseinstellungen verfügbar.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>Kann ich nicht verwaltete Geräte aus der Gerätebestandsliste ausschließen?
Ja, Sie können Filter anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen. Sie können auch die Spalte "Onboardingstatus" in API-Abfragen verwenden, um nicht verwaltete Geräte herauszufiltern. 


## <a name="which-onboarded-devices-can-perform-discovery"></a>Welche integrierten Geräte können ermittlungsfähig sein?
 Integrierte Geräte, die auf Windows 10 Version 1809 oder höher ausgeführt werden, können ermittlungsfähig sein.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Was geschieht, wenn meine integrierten Geräte mit meinem Heimnetzwerk oder mit dem öffentlichen Zugriffspunkt verbunden sind?
 Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks. Durch die Korrelation von Netzwerkbezeichnern über alle Mandantenclients hinweg werden Ereignisse zwischen Ereignissen unterschieden, die von privaten Netzwerken und Unternehmensnetzwerken empfangen wurden. Wenn die Mehrzahl der Geräte im Netzwerk beispielsweise meldet, dass sie mit demselben Netzwerknamen und derselben Standardgateway- und DHCP-Serveradresse verbunden sind, kann davon ausgegangen werden, dass es sich bei diesem Netzwerk wahrscheinlich um ein Unternehmensnetzwerk handelt. Private Netzwerkgeräte werden nicht im Bestand aufgeführt und nicht aktiv untersucht.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Welche Protokolle erfassen und analysieren Sie?
 Standardmäßig erfassen und analysieren alle integrierten Geräte, die auf Windows 10 Version 1809 oder höher ausgeführt werden, die folgenden Protokolle: ARP, CDP, DHCP, DHCPv6, IP (Header), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (Header), UDP (Header), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Welche Protokolle verwenden Sie für die aktive Untersuchung in der Standardermittlung?
 Wenn ein Gerät für die Ausführung der Standardermittlung konfiguriert ist, werden die verfügbar gemachten Dienste mithilfe der folgenden Protokolle untersucht: ARP, FTP, HTTP, HTTPS, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL, RPC, mDNS, DHCP, AFP, CrestonCIP, IphoneSync

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Wie kann ich ziele ausschließen, mit der Standardermittlung untersucht zu werden?
 Wenn in Ihrem Netzwerk Geräte vorhanden sind, die nicht aktiv untersucht werden sollten, können Sie auch eine Liste von Ausschlüssen definieren, um zu verhindern, dass sie gescannt werden. Die Konfiguration ist auf der Seite mit den Geräteermittlungseinstellungen verfügbar.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Kann ich ausschließen, dass Geräte erkannt werden?
 Da die Geräteermittlung passive Methoden verwendet, um Geräte im Netzwerk zu ermitteln, können alle Geräte, die mit Ihren integrierten Geräten im Unternehmensnetzwerk kommunizieren, ermittelt und im Bestand aufgeführt werden. Sie können Geräte nur von der aktiven Untersuchung ausschließen.

## <a name="how-frequent-is-the-active-probing"></a>Wie häufig wird die aktive Untersuchung ausgeführt?
 Geräte werden aktiv untersucht, wenn Änderungen der Geräteeigenschaften beobachtet werden (alle 1 bis 3 Wochen), um sicherzustellen, dass die vorhandenen Informationen auf dem neuesten Stand sind.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Was soll ich tun, wenn mein Sicherheitstool eine Warnung zu UnicastScanner.ps1 oder von ihm initiierten Portüberprüfungsaktivitäten ausgelöst hat?
 Die aktiven Testskripts werden von Microsoft signiert und sind sicher. Sie können der Ausschlussliste den folgenden Pfad hinzufügen: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Wie viel Datenverkehr wird vom aktiven Test für die Standardermittlung generiert?
 Das aktive Austesten kann bis zu 5 KB Datenverkehr zwischen dem integrierten Gerät und dem untersuchten Gerät generieren, bei jedem Testversuch.

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Warum gibt es eine Abweichung zwischen "kann integriert werden"-Geräten im Gerätebestand und der Anzahl der "zu integrierenden Geräte" in der Dashboardkachel?
Möglicherweise stellen Sie Unterschiede zwischen der Anzahl der aufgeführten Geräte unter "Kann integriert werden" im Gerätebestand, der Sicherheitsempfehlung "Onboarding in Microsoft Defender für Endpunkt" und dem Dashboard-Widget "Geräte zum Onboarding" fest.

 Die Sicherheitsempfehlungen und das Dashboard-Widget gelten für Geräte, die im Netzwerk stabil sind. ausschließen von kurzlebigen Geräten, Gastgeräten und anderen Geräten. Die Idee besteht darin, auf persistenten Geräten zu empfehlen, die auch die gesamtsicherheitsbewertung der Organisation implizieren.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Kann ich nicht verwaltete Geräte integrieren, die gefunden wurden?
 Ja. Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk. Durch das Onboarding in den Dienst kann die Sichtbarkeit der Sicherheit für sie erhöht werden. 

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>Ich habe festgestellt, dass der Integritätsstatus des nicht verwalteten Geräts immer "Aktiv" ist. Warum ist das der Fall?
Vorübergehend ist der Zustand des nicht verwalteten Gerätestatus während des Standardaufbewahrungszeitraums des Gerätebestands "Aktiv", unabhängig vom tatsächlichen Zustand.
