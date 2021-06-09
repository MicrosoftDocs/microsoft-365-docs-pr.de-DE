---
title: Microsoft 365 Defender
description: Microsoft 365 Defender ist eine koordinierte Lösung zum Schutz vor Bedrohungen, die entwickelt wurde, um Geräte, Identität, Daten und Anwendungen zu schützen.
keywords: Einführung in MMicrosoft 365 Defender, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 21a80abd36fd8e7e33f0ccf9b145d409119205ec
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842650"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender ist eine vereinheitlichte Enterprise-Defense-Suite, die Erkennung, Verhinderung, Untersuchung und Reaktionen auf Endpunkte, Identitäten, E-Mails und Anwendungen systemweit koordiniert, um integrierten Schutz vor komplexen Angriffen zu bieten.

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale zusammenfügen, die jedes dieser Produkte erhält, und den vollständigen Umfang und die Auswirkungen der Bedrohung ermitteln. wie sie in die Umgebung gelangt ist, welche Auswirkungen sie hat und wie sie sich derzeit auf die Organisation auswirkt. Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und die betroffenen Postfächer, Endpunkte und Benutzeridentitäten selbst zu verwenden.  


<center><h2>Microsoft 365 Defender-Dienste</center></h2>
<table><tr><td><center><b><a href="/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender für Endpunkt</b></center></a></td>
<td><center><b><a href="/office365/securitycompliance/office-365-atp"><b>Microsoft Defender für Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Interaktiver Defender-Leitfaden

In diesem interaktiven Leitfaden erfahren Sie, wie Sie Ihre Organisation mit Microsoft 365 Defender schützen. Sie werden sehen, wie Microsoft 365 Defender Ihnen helfen kann, Sicherheitsrisiken zu erkennen, Angriffe auf Ihre Organisation zu untersuchen und schädliche Aktivitäten automatisch zu verhindern.

[Sehen Sie sich den interaktiven Leitfaden an](https://aka.ms/M365Defender-InteractiveGuide)



Microsoft 365 Defender Suite schützt: 
- **Endpunkte mit Microsoft Defender für Endpunkt** – Microsoft Defender für Endpunkt ist eine einheitliche Endpunktplattform für präventiven Schutz, Erkennung nach einem Angriff, automatisierte Untersuchung und Reaktion. 
- **E-Mail und Zusammenarbeit mit Microsoft Defender für Office 365** – Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. 
- **Identitäten mit Microsoft Defender for Identity und Azure AD Identity Protection** – Microsoft Defender for Identity verwendet Active Directory-Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insideraktionen gegen Ihre Organisation zu identifizieren, zu erkennen und zu untersuchen. 
- **Anwendungen mit Microsoft Cloud App Security** – Microsoft Cloud App Security ist eine umfassende SaaS-übergreifende Lösung, die tiefe Sichtbarkeit, starke Datenkontrollen und verbesserten Bedrohungsschutz für Ihre Cloud-Apps bietet. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Die eindeutige produktübergreifende Ebene von Defender erweitert die einzelnen Suite-Komponenten um Folgendes:
- Tragen Sie zum Schutz vor Angriffen bei und koordinieren Sie die reaktionssicheren Reaktionen in der gesamten Suite durch Signalfreigabe und automatisierte Aktionen.
- Erfahren Sie mehr über den Angriff über Produktwarnungen, Verhaltensweisen und Kontext für Sicherheitsteams, indem Sie Daten zu Warnungen, verdächtigen Ereignissen und betroffenen Ressourcen zu "Vorfällen" hinzufügen.
- Automatisieren Sie die Reaktion auf Kompromittierung, indem Sie die Selbstkorrektur für betroffene Ressourcen durch automatische Korrektur auslösen.
- Ermöglichen Sie Sicherheitsteams, eine detaillierte und effektive Bedrohungssuche über Endpunkt- und Office-Daten hinweg durchzuführen.

![Abbildung der Vorfallübersichtsseite](../../media/overview-incident.png) <br>
Produktübergreifender Vorfall (Übersicht)

![Abbildung der Warnungswarteschlange](../../media/incident-list.png)<br>
Alle zugehörigen Warnungen in den Suite-Produkten korreliert in einem einzigen Vorfall (Warnungsansicht)

![Abbildung der Vorfallwarteschlange](../../media/advanced-hunting.png)<br>
Abfragebasierte Suche nach E-Mail- und Endpunkt-Rohdaten


Microsoft 365 Zu den produktübergreifenden Defender-Features gehören: 
- **Produktübergreifender einzelner Bereich –** Zentrale Ansicht aller Informationen zu Erkennungen, betroffenen Ressourcen, durchgeführten automatisierten Aktionen und zugehörigen Nachweisen in einer einzigen Warteschlange und einem einzelnen Bereich in [security.microsoft.com.](https://security.microsoft.com) 
- **Kombinierte Vorfallwarteschlange** – Damit sich Sicherheitsexperten auf das Wesentliche konzentrieren können, indem sie den gesamten Angriffsbereich sicherstellen, werden betroffene Ressourcen und automatisierte Abhilfemaßnahmen gruppiert und zeitnah angezeigt. 
- **Automatische Reaktion auf Bedrohungen** – Kritische Bedrohungsinformationen werden in Echtzeit zwischen den Microsoft 365 Defender-Produkten geteilt, um das Fortgang eines Angriffs zu stoppen. Wenn z. B. eine schädliche Datei auf einem Endpunkt erkannt wird, der durch Microsoft Defender für Endpunkt geschützt ist, weist sie Defender an, Office 365 die Datei zu scannen und aus allen E-Mail-Nachrichten zu entfernen. Die Datei wird bei der Anzeige durch die gesamte Microsoft 365 Sicherheitssuite blockiert.
- **Selbstreparatur für kompromittierte Geräte, Benutzeridentitäten und Postfächer** – Microsoft 365 Defender verwendet automatische Ki-Aktionen und Playbooks, um betroffene Ressourcen wieder in einen sicheren Zustand zu versetzen. Microsoft 365 Defender nutzt automatische Korrekturfunktionen der Suite-Produkte, um sicherzustellen, dass alle betroffenen Ressourcen im Zusammenhang mit einem Vorfall nach Möglichkeit automatisch behoben werden.
- **Produktübergreifende Bedrohungssuche** – Sicherheitsteams können ihr einzigartiges Organisationswissen nutzen, um nach Gefährdungszeichen zu suchen, indem sie eigene benutzerdefinierte Abfragen über die rohen Daten erstellen, die von den verschiedenen Schutzprodukten gesammelt werden. Microsoft 365 Defender bietet abfragebasierten Zugriff auf 30 Tage historische Rohsignale und Warnungsdaten für Endpunkte und Microsoft Defender für Office 365 Daten. 


## <a name="get-started"></a>Erste Schritte
Microsoft 365 Die Defender-Lizenzierungsanforderungen müssen erfüllt sein, bevor Sie den Dienst im Microsoft 365 Security Center auf [security.microsoft.com](https://security.microsoft.com)aktivieren können. Weitere Informationen finden Sie unter:
- [Lizenzanforderungen](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender aktivieren](m365d-enable.md)


## <a name="see-also"></a>Siehe auch
- [Bereitstellen von Bedrohungsschutzfunktionen über Microsoft 365 E5](/microsoft-365/solutions/deploy-threat-protection)
