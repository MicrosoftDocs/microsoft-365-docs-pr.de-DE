---
title: Bedrohungsschutz (Windows 10)
description: Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion.
keywords: Bedrohungsschutz, Microsoft Defender für Endpunkt, Verringerung der Angriffsfläche, Schutz der nächsten Generation, EDR, automatisierte Untersuchung und Reaktion, Microsoft-Bedrohungsexperten, Microsoft-Sicherheitsbewertung für Geräte, erweiterte Suche, Suche nach Cyberbedrohungen, Schutz vor Webbedrohungen
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840994"
---
# <a name="threat-protection"></a>Bedrohungsschutz
[Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. Defender für Endpunkt schützt Endpunkte vor Cyberbedrohungen, erkennt fortgeschrittene Angriffe und Datenschutzverletzungen, automatisiert Sicherheitsvorfälle und verbessert den Sicherheitsstatus.

> [!TIP]
> Ermöglichen Sie Ihren Benutzern den einfachen Zugriff auf Clouddienste und lokale Anwendungen und ermöglichen Sie moderne Verwaltungsfunktionen für alle Geräte. Weitere Informationen finden Sie unter ["Sichern Ihrer Remotemitarbeiter".](/enterprise-mobility-security/remote-work/) 

<center><h2>Microsoft Defender für Endpunkt</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Bedrohungs-& Sicherheitsrisikomanagement</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Verringerung der Angriffsfläche</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Schutz der nächsten Generation</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Endpunkterkennung und -antwort</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Automatisierte Untersuchung und Korrektur</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft-Bedrohungsexperten</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Zentrale Konfiguration und Verwaltung, APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Verteidiger</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)**<br>
Diese integrierte Funktion verwendet einen spielverändernden risikobasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunkt-Sicherheitsrisiken und Fehlkonfigurationen.

- [Übersicht über bedrohungsbasierte & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Erste Schritte](tvm-prerequisites.md)
- [Zugriff auf Ihren Sicherheitsstatus](tvm-dashboard-insights.md)
- [Verbessern Sie Ihren Sicherheitsstatus und verringern Sie Risiken](tvm-security-recommendation.md)
- [Erkennen von Sicherheitsrisiken auf Ihren Geräten](tvm-software-inventory.md)

<a name="asr"></a>

**[Verringerung der Angriffsfläche](overview-attack-surface-reduction.md)**<br>
Der Satz von Funktionen zur Verringerung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel dar. Indem sichergestellt wird, dass die Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Exploit-Minderungstechniken angewendet werden, widersetzen sich diese Funktionen Angriffen und Ausnutzung.

- [Hardwarebasierte Isolierung](overview-hardware-based-isolation.md)
- [Anwendungssteuerung](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Gerätesteuerung](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Exploit-Schutz.](exploit-protection.md)
- [Netzwerkschutz,](network-protection.md) [Webschutz](web-protection-overview.md)
- [Kontrollierter Ordnerzugriff](controlled-folders.md)
- [Netzwerkfirewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)

<a name="ngp"></a>

**[Schutzlösungen der nächsten Generation](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Um den Sicherheitsperimeter Ihres Netzwerks weiter zu erhöhen, verwendet Microsoft Defender für Endpunkt Schutz der nächsten Generation, der entwickelt wurde, um alle Arten von bedrohungen abzufangen.

- [Verhaltensüberwachung](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Cloudbasierter Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Maschinelles Lernen](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL-Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Automatisierter Sandkastendienst](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md)**<br>
Endpunkterkennungs- und -reaktionsfunktionen werden eingerichtet, um Angriffsversuche und aktive Verstöße zu erkennen, zu untersuchen und darauf zu reagieren. Mit der erweiterten Suche verfügen Sie über ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie proaktiv Verstöße finden und benutzerdefinierte Erkennungen erstellen können.

- [Benachrichtigungen](alerts-queue.md)
- [Historische Endpunktdaten](investigate-machines.md#timeline)
- [Reaktionsorchestrierung](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Forensische Sammlung](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Bedrohungserkennung](threat-indicator-concepts.md)
- [Erweiterter Detonations- und Analysedienst](respond-file-alerts.md#deep-analysis)
- [Erweiterte Suche](advanced-hunting-overview.md)
    - [Benutzerdefinierte Erkennungen](overview-custom-detections.md)

<a name="ai"></a>

**[Automatisierte Untersuchung und Korrektur](automated-investigations.md)**<br>
Zusätzlich zur schnellen Reaktion auf fortgeschrittene Angriffe bietet Microsoft Defender für Endpunkt automatische Untersuchungs- und Korrekturfunktionen, die dazu beitragen, die Anzahl der Warnungen in Minuten zu reduzieren.

- [Automatisierte Untersuchung und Korrektur](automated-investigations.md)
- [Anzeigen von Details und Ergebnissen von automatischen Untersuchungen](auto-investigation-action-center.md)
- [Anzeigen und Genehmigen von Korrekturaktionen](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**<br>
Der neue Verwaltete Bedrohungssuche-Dienst von Microsoft Defender für Endpunkt bietet proaktive Suche, Priorisierung und zusätzlichen Kontext und Einblicke. Microsoft-Bedrohungsexperten ermöglicht es Security Operation Centers (SOCs), Bedrohungen schnell und präzise zu erkennen und darauf zu reagieren.

- [Benachrichtigung über gezielte Angriffe](microsoft-threat-experts.md)
- [Experten nach Bedarf](microsoft-threat-experts.md)
- [Konfigurieren Ihres Microsoft 365 von Defender verwalteten Suchdiensts](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**<br>
Integrieren Sie Microsoft Defender für Endpunkt in Ihre vorhandenen Workflows.
- [Onboarding](onboard-configure.md)
- [API- und SIEM-Integration](configure-siem.md)
- [Verfügbar gemachte APIs](apis-intro.md)
- [Rollenbasierte Zugriffssteuerung (RBAC)](rbac.md)
- [Berichterstellung und Trends](threat-protection-reports.md)

<a name="integration"></a>
**[Integration in Microsoft-Lösungen](threat-protection-integration.md)** <br>
 Microsoft Defender für Endpunkt lässt sich direkt in verschiedene Microsoft-Lösungen integrieren, einschließlich:
- Intune
- Microsoft Defender für Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype for Business
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Verteidiger](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Mit Microsoft 365 Defender bilden Microsoft Defender für Endpunkt und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Unternehmensschutzsuite vor und nach dem Angriff, die systemintern in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um komplexe Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch darauf zu reagieren.
