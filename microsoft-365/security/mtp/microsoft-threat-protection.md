---
title: Microsoft 365 Defender
description: Microsoft 365 Defender ist eine koordinierte Bedrohungsschutzlösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen
keywords: Einführung in Microsoft Threat Protection, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Geräte, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 254d3b9abc4a356e5a0fd429d6505faacafd3a8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906712"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](./mtp-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender ist eine vereinheitlichte Enterprise-Defense-Suite, die Erkennung, Verhinderung, Untersuchung und Reaktionen auf Endpunkte, Identitäten, E-Mails und Anwendungen systemweit koordiniert, um integrierten Schutz vor komplexen Angriffen zu bieten.

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale, die jedes dieser Produkte erhält, zusammenbringen und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen. Wie sie in die Umgebung eintrat, welche Auswirkungen sie hat und wie sie sich derzeit auf die Organisation auswirken. Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu beenden.  


<center><h2>Microsoft 365 Defender Services</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender für Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Interaktives Microsoft 365 Defender-Handbuch

In diesem interaktiven Leitfaden erfahren Sie, wie Sie Ihre Organisation mit Microsoft 365 Defender schützen. Sie sehen, wie Microsoft 365 Defender Ihnen dabei helfen kann, Sicherheitsrisiken zu erkennen, Angriffe auf Ihre Organisation zu untersuchen und schädliche Aktivitäten automatisch zu verhindern.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender Suite schützt: 
- **Endpunkte mit Microsoft Defender for Endpoint** – Microsoft Defender for Endpoint ist eine einheitliche Endpunktplattform für vorbeugenden Schutz, Erkennung nach Sicherheitsverletzungen, automatisierte Untersuchung und Reaktion. 
- E-Mail und Zusammenarbeit mit **Microsoft Defender für Office 365** – Defender for Office 365 schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. 
- **Identitäten** mit Microsoft Defender for Identity und Azure AD Identity Protection – Microsoft Defender for Identity verwendet Active Directory-Signale, um erweiterte Bedrohungen, gefährdete Identitäten und schädliche Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die an Ihre Organisation gerichtet sind. 
- **Anwendungen mit Microsoft Cloud App-Sicherheit** – Microsoft Cloud App Security ist eine umfassende saaS-übergreifende Lösung, die umfassende Sichtbarkeit, starke Datenkontrollen und erweiterten Bedrohungsschutz für Ihre Cloud-Apps bietet. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Die einzigartige produktübergreifende Ebene von Microsoft 365 Defender erweitert die einzelnen Suitekomponenten auf:
- Schützen vor Angriffen und Koordinieren von Defensivantworten in der gesamten Suite durch Signalfreigabe und automatisierte Aktionen
- Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'
- Automatisieren der Reaktion auf Kompromisse durch Auslösen der Selbstheilung betroffener Objekte durch automatisierte Korrektur
- Aktivieren von Sicherheitsteams für eine detaillierte und effektive Bedrohungssuche über Endpunkt- und Office-Daten hinweg

![Übersichtsseite "Bild des Vorfalls"](../../media/overview-incident.png) <br>
Produktübergreifender Vorfall (Übersicht)

![Abbildung der Benachrichtigungswarteschlange](../../media/incident-list.png)<br>
Alle zugehörigen Warnungen in den Suiteprodukten korrelierten in einem einzelnen Vorfall (Benachrichtigungsansicht)

![Abbildung der Warteschlange für Vorfälle](../../media/advanced-hunting.png)<br>
Abfragebasierte Suche über E-Mail- und Endpunktrohdaten


Zu den produktübergreifenden Microsoft 365 Defender-Features gehören: 
- **Produktübergreifender** einzelner Glasbereich – Zentrale Ansicht aller Informationen zu Erkennungen, betroffenen Ressourcen, automatisierten Aktionen und zugehörigen Nachweisen in einer einzelnen Warteschlange und einem einzelnen Bereich in [security.microsoft.com](https://security.microsoft.com). 
- **Warteschlange für** kombinierte Vorfälle – Um Sicherheitsexperten dabei zu helfen, sich auf das Wichtige zu konzentrieren, indem sie den vollständigen Angriffsbereich sicherstellen, werden die auswirkungensprallten Ressourcen und automatisierten Abhilfemaßnahmen zusammengefasst und zeitnah angezeigt. 
- **Automatische Reaktion auf Bedrohungen** – Informationen zu kritischen Bedrohungen werden in Echtzeit zwischen den Microsoft 365 Defender-Produkten freigegeben, um das Fortschreiten eines Angriffs zu verhindern. Wenn beispielsweise eine schädliche Datei auf einem von Microsoft Defender for Endpoint geschützten Endpunkt erkannt wird, wird Defender for Office 365 angewiesen, die Datei aus allen E-Mail-Nachrichten zu scannen und zu entfernen. Die Datei wird von der gesamten Microsoft 365-Sicherheitssuite beim Sehen blockiert.
- Selbstheilung für gefährdete **Geräte,** Benutzeridentitäten und Postfächer – Microsoft 365 Defender verwendet ki-betriebene automatische Aktionen und Playbooks, um beeinträchtigte Objekte wieder in einen sicheren Zustand zurück zu bringen. Microsoft 365 Defender nutzt automatische Korrekturfunktionen der Suiteprodukte, um sicherzustellen, dass alle im Zusammenhang mit einem Vorfall in Zusammenhang stehenden Ressourcen nach Möglichkeit automatisch behoben werden.
- **Produktübergreifende** Bedrohungssuche : Sicherheitsteams können ihr einzigartiges Organisationswissen nutzen, um nach Anzeichen von Kompromissen zu fahnen, indem sie eigene benutzerdefinierte Abfragen über die von den verschiedenen Schutzprodukten gesammelten Rohdaten erstellen. Microsoft 365 Defender bietet abfragebasierten Zugriff auf 30 Tage mit historischen Unformatsignalen und Warnungsdaten für Endpunkte und Microsoft Defender für Office 365-Daten. 


## <a name="get-started"></a>Erste Schritte
Microsoft 365 Defender-Lizenzierungsanforderungen müssen erfüllt sein, bevor Sie den Dienst im Microsoft 365 Security Center unter [security.microsoft.com.](https://security.microsoft.com) Weitere Informationen finden Sie unter:
- [Lizenzanforderungen](prerequisites.md#licensing-requirements)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)