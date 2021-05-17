---
title: Microsoft Defender für Endpunkt
description: Microsoft Defender for Endpoint ist eine Sicherheitsplattform für Unternehmensendpunkte, die bei der Verteidigung vor erweiterten beständigen Bedrohungen hilft.
keywords: Einführung in Microsoft Defender for Endpoint, Einführung in Microsoft Defender for Endpoint, Cybersecurity, advanced persistent threat, enterprise security, machine behavioral sensor, cloud security, analytics, threat intelligence, attack surface reduction, next-generation protection, automated investigation and remediation, microsoft threat experts, secure score, advanced hunting, Microsoft 365 Defender, cyber threat hunting
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
ms.openlocfilehash: 57d4506e32db5defe29f2d0e59f72bd4c1998310
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935929"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Weitere Informationen zu features and functionality Windows 10 Enterprise Edition finden Sie unter [Windows 10 Enterprise Edition](https://www.microsoft.com/WindowsForBusiness/buy).

Microsoft Defender for Endpoint ist eine Unternehmensendpunktsicherheitsplattform, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und auf sie zu reagieren.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint verwendet die folgende Kombination aus Technologie, die in Windows 10 und dem robusten Clouddienst von Microsoft entwickelt wurde:

-   **Endpunktverhaltenssensoren:** Eingebettet in Windows 10 erfassen und verarbeiten diese Sensoren Verhaltenssignale vom Betriebssystem und senden diese Sensordaten an Ihre private, isolierte Cloudinstanz von Microsoft Defender for Endpoint.


-   **Cloudsicherheitsanalyse:** Unter Verwendung von Big Data, Device-Learning und einzigartiger Microsoft-Optik im gesamten Windows-Ökosystem, in Unternehmens-Cloud-Produkten (z. B. Office 365) und Onlineressourcen werden Verhaltenssignale in Einblicke, Erkennungen und empfohlene Antworten auf erweiterte Bedrohungen übersetzt.

-   Bedrohungsintelligenz: Generiert von Microsoft-Jägern, Sicherheitsteams und erweitert durch Bedrohungsintelligenz, die von Partnern bereitgestellt wird, ermöglicht die Bedrohungsintelligenz Defender for Endpoint, Angreifertools, -techniken und -verfahren zu identifizieren und Warnungen zu generieren, wenn sie in gesammelten Sensordaten beobachtet werden.

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Sicherheitsrisikoverwaltung & Bedrohungen</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Reduzierung der Angriffsfläche</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Schutz der nächsten Generation</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Endpunkterkennung und -antwort</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Automatisierte Untersuchung und Behebung</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft-Bedrohungsexperten</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Zentrale Konfiguration und Verwaltung, APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Erfahren Sie mehr über die neuesten Verbesserungen in Defender for Endpoint: [Neuigkeiten in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
> - Microsoft Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Sicherheitsrisikoverwaltung & Bedrohungen](next-gen-threat-and-vuln-mgt.md)**<br>
Diese integrierte Funktion verwendet einen spielveränderungsbasierten Ansatz für die Ermittlung, Priorisierung und Behebung von Endpunktrisiken und Fehlkonfigurationen. 

<a name="asr"></a>

**[Reduzierung der Angriffsfläche](overview-attack-surface-reduction.md)**<br>
Der Satz von Funktionen zur Reduzierung der Angriffsfläche stellt die erste Verteidigungslinie im Stapel bereit. Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich die Funktionen gegen Angriffe und Diebenutzung. Dieser Satz von Funktionen umfasst auch [Netzwerkschutz](network-protection.md) und [Webschutz,](web-protection-overview.md)die den Zugriff auf schädliche IP-Adressen, Domänen und URLs regeln. 

<a name="ngp"></a>

**[Schutzlösungen der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Zur weiteren Verstärkung des Sicherheitsperimeters Ihres Netzwerks verwendet Microsoft Defender for Endpoint den Schutz der nächsten Generation, der alle Arten neuer Bedrohungen abfangen soll.

<a name="edr"></a>

**[Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md)**<br>
Funktionen zur Erkennung und Reaktion von Endpunkten werden zum Erkennen, Untersuchen und Reagieren auf erweiterte Bedrohungen verwendet, die die ersten beiden Sicherheitspfeiler möglicherweise über die ersten beiden Sicherheitspfeiler hinaus haben. [Die erweiterte Suche](advanced-hunting-overview.md) bietet ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Verstöße proaktiv finden und benutzerdefinierte Erkennungen erstellen können.

<a name="ai"></a>

**[Automatisierte Untersuchung und Behebung](automated-investigations.md)**<br>
In Verbindung mit der schnellen Reaktion auf erweiterte Angriffe bietet Microsoft Defender for Endpoint automatische Untersuchungs- und Korrekturfunktionen, mit deren Hilfe das Volumen von Warnungen in Minuten im Großen reduziert werden kann. 

<a name="ss"></a>

**[Microsoft-Sicherheitsbewertung für Geräte](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint enthält Microsoft Secure Score for Devices, mit dem Sie den Sicherheitsstatus Ihres Unternehmensnetzwerks dynamisch bewerten, nicht geschützte Systeme identifizieren und empfohlene Maßnahmen ergreifen können, um die allgemeine Sicherheit Ihrer Organisation zu verbessern.

<a name="mte"></a>

**[Microsoft-Bedrohungsexperten](microsoft-threat-experts.md)**<br>
Der neue dienst für die Suche nach verwalteten Bedrohungen von Microsoft Defender for Endpoint bietet proaktives Aufsuchen, Priorisierung sowie zusätzliche Kontexte und Einblicke, mit denen Sicherheitsoperationscenter (Security Operation Center, SOCs) Bedrohungen schnell und präzise identifizieren und darauf reagieren können.

>[!IMPORTANT]
>Defender for Endpoint-Kunden müssen sich für den Microsoft-Bedrohungsexperten dienst für die Suche nach verwalteten Bedrohungen bewerben, um proaktive Benachrichtigungen über gezielte Angriffe zu erhalten und bei Bedarf mit Experten zusammenzuarbeiten. Experts on Demand ist ein Add-On-Dienst. Benachrichtigungen über gezielte Angriffe werden immer einbezogen, nachdem Sie in Microsoft-Bedrohungsexperten dienst für die Suche nach verwalteten Bedrohungen akzeptiert wurden.<p>
><p>Wenn Sie noch nicht registriert sind und ihre Vorteile <b></b> nutzen möchten, wechseln Sie zu Einstellungen > <b>Allgemeine</b> > <b></b> erweiterte Features, Microsoft-Bedrohungsexperten > <b>anwenden</b> möchten. Sobald sie akzeptiert wurden, erhalten Sie die Vorteile von Benachrichtigungen über gezielte Angriffe und starten eine 90-tägige Testversion von Experten bei Bedarf. Wenden Sie sich an Ihren Microsoft-Vertreter, um ein vollständiges Experts on Demand-Abonnement zu erhalten.

<a name="apis"></a>

**[Zentrale Konfiguration und Verwaltung, APIs](management-apis.md)**<br>
Integrieren Sie Microsoft Defender for Endpoint in Ihre vorhandenen Workflows.

<a name="mtp"></a>

**[Integration in Microsoft-Lösungen](threat-protection-integration.md)** <br>
Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden, darunter:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender für Office
- Skype for Business

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Mit Microsoft 365 Defender bilden Defender for Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.


## <a name="related-topic"></a>Verwandtes Thema
[Microsoft Defender for Endpoint hilft beim Erkennen anspruchsvoller Bedrohungen](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
