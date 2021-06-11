---
title: Microsoft Defender für Endpunkt
description: Microsoft Defender für Endpunkt ist eine Sicherheitsplattform für Unternehmensendpunkte, die sich vor erweiterten dauerhaften Bedrohungen schützt.
keywords: Einführung in Microsoft Defender für Endpunkt, Einführung in Microsoft Defender für Endpunkt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Computerverhaltenssensor, Cloudsicherheit, Analysen, Bedrohungserkennung, Verringerung der Angriffsfläche, Schutz der nächsten Generation, automatisierte Untersuchung und Behebung, Microsoft-Bedrohungsexperten, Sicherheitsbewertung, erweiterte Suche, Microsoft 365 Defender, Suche nach Cyberbedrohungen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 23a9b99a71d700bdeddb3398c592eeb778ceef23
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879264"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Weitere Informationen zu Windows 10 Enterprise Edition-Features und -Funktionen finden Sie unter [Windows 10 Enterprise Edition.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender für Endpunkt ist eine Sicherheitsplattform für Endpunkte für Unternehmen, die Unternehmensnetzwerke dabei unterstützt, fortgeschrittene Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender für Endpunkt verwendet die folgende Kombination von Technologien, die in Windows 10 integriert sind, und dem robusten Clouddienst von Microsoft:

-   **Endpunktverhaltenssensoren:** Eingebettet in Windows 10 sammeln und verarbeiten diese Sensoren Verhaltenssignale vom Betriebssystem und senden diese Sensordaten an Ihre private, isolierte Cloudinstanz von Microsoft Defender für Endpunkt.


-   **Cloud-Sicherheitsanalysen:** Die Nutzung von Big Data, Device Learning und einzigartiger Microsoft-Optik im Windows Ökosystem, Unternehmenscloudprodukte (z. B. Office 365) und Onlineressourcen, Verhaltenssignale werden in Einblicke, Erkennungen und empfohlene Reaktionen auf fortgeschrittene Bedrohungen übersetzt.

-   **Bedrohungserkennung:** Bedrohungserkennung, die von Microsoft-Schützern, Sicherheitsteams und von Partnern ergänzt wird, ermöglicht es Defender für Endpunkt, Tools, Techniken und Verfahren von Angreifern zu identifizieren und Warnungen zu generieren, wenn sie in gesammelten Sensordaten beobachtet werden.

<center><h2>Microsoft Defender für Endpunkt</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Bedrohungs- &-Sicherheitsrisikoverwaltung</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Verringerung der Angriffsfläche</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Schutz der nächsten Generation</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Endpunkterkennung und -antwort</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Automatisierte Untersuchung und Korrektur</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft-Bedrohungsexperten</b></a></center></td>
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

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Erfahren Sie mehr über die neuesten Verbesserungen in Defender für Endpunkt: [Neuigkeiten in Microsoft Defender für Endpunkt.](whats-new-in-microsoft-defender-atp.md)
> - Microsoft Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Bedrohungs- &-Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)**<br>
Diese integrierte Funktion verwendet einen spielverändernden risikobasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunkt-Sicherheitsrisiken und Fehlkonfigurationen. 

<a name="asr"></a>

**[Verringerung der Angriffsfläche](overview-attack-surface-reduction.md)**<br>
Der Satz von Funktionen zur Verringerung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel bereit. Indem sichergestellt wird, dass die Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Exploit-Minderungstechniken angewendet werden, verhindern die Funktionen Angriffe und Exploits. Diese Reihe von Funktionen umfasst auch [Netzwerkschutz](network-protection.md) und [Webschutz,](web-protection-overview.md)die den Zugriff auf schädliche IP-Adressen, Domänen und URLs regeln. 

<a name="ngp"></a>

**[Schutzlösungen der nächsten Generation](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Um den Sicherheitsperimeter Ihres Netzwerks weiter zu erhöhen, verwendet Microsoft Defender für Endpunkt Schutz der nächsten Generation, der entwickelt wurde, um alle Arten von bedrohungen abzufangen.

<a name="edr"></a>

**[Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md)**<br>
Endpunkterkennungs- und -reaktionsfunktionen werden eingerichtet, um erweiterte Bedrohungen zu erkennen, zu untersuchen und darauf zu reagieren, die möglicherweise über die ersten beiden Sicherheitssäulen hinausgereift sind. [Die erweiterte Suche](advanced-hunting-overview.md) bietet ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie proaktiv Verstöße finden und benutzerdefinierte Erkennungen erstellen können.

<a name="ai"></a>

**[Automatisierte Untersuchung und Korrektur](automated-investigations.md)**<br>
In Verbindung mit der Fähigkeit, schnell auf fortgeschrittene Angriffe zu reagieren, bietet Microsoft Defender für Endpunkt automatische Untersuchungs- und Korrekturfunktionen, die dazu beitragen, die Anzahl der Warnungen in Minuten zu reduzieren. 

<a name="ss"></a>

**[Microsoft-Sicherheitsbewertung für Geräte](tvm-microsoft-secure-score-devices.md)**<br>

Defender für Endpunkt enthält die Microsoft-Sicherheitsbewertung für Geräte, die Ihnen dabei hilft, den Sicherheitsstatus Ihres Unternehmensnetzwerks dynamisch zu bewerten, ungeschützte Systeme zu identifizieren und empfohlene Maßnahmen zu ergreifen, um die Gesamtsicherheit Ihrer Organisation zu verbessern.

<a name="mte"></a>

**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**<br>
Der neue dienst für die verwaltete Bedrohungssuche von Microsoft Defender für Endpunkt bietet proaktive Suche, Priorisierung sowie zusätzlichen Kontext und Einblicke, mit denen Sicherheits-Operationscenter (Security Operation Centers, SOCs) Bedrohungen schnell und präzise identifizieren und darauf reagieren können.

>[!IMPORTANT]
>Defender für Endpunkt-Kunden müssen sich für den Microsoft-Bedrohungsexperten verwalteten Dienst für die Bedrohungssuche bewerben, um proaktive Benachrichtigungen über gezielte Angriffe zu erhalten und bei Bedarf mit Experten zusammenzuarbeiten. Experts on Demand ist ein Add-On-Dienst. Benachrichtigungen über gezielte Angriffe sind immer enthalten, nachdem Sie in Microsoft-Bedrohungsexperten verwalteten Dienst für die Bedrohungssuche aufgenommen wurden.<p>
><p>Wenn Sie noch nicht registriert sind und die Vorteile nutzen möchten, wechseln Sie zu <b>Einstellungen</b> > <b>Allgemeinen</b> > <b>erweiterten Features</b> > <b>Microsoft-Bedrohungsexperten,</b> die Sie anwenden möchten. Nach der Annahme erhalten Sie die Vorteile von Benachrichtigungen über gezielte Angriffe und starten eine 90-tägige Testversion von Experten bei Bedarf. Wenden Sie sich an Ihren Microsoft-Mitarbeiter, um ein vollständiges Experts on Demand-Abonnement zu erhalten.

<a name="apis"></a>

**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**<br>
Integrieren Sie Microsoft Defender für Endpunkt in Ihre vorhandenen Workflows.

<a name="mtp"></a>

**[Integration in Microsoft-Lösungen](threat-protection-integration.md)** <br>
Defender für Endpunkt lässt sich direkt in verschiedene Microsoft-Lösungen integrieren, einschließlich:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender für Office
- Skype for Business

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Mit Microsoft 365 Defender bilden Defender, Defender für Endpunkt und verschiedene Sicherheitslösungen von Microsoft eine einheitliche Unternehmensschutzsuite vor und nach einem Angriff, die sich nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert, um komplexe Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch darauf zu reagieren.


## <a name="related-topic"></a>Verwandtes Thema
[Microsoft Defender für Endpunkt hilft bei der Erkennung anspruchsvoller Bedrohungen](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
