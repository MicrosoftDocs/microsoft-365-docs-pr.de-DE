---
title: Microsoft 365 Defender
description: Microsoft 365 Defender ist eine koordinierte Lösung zum Schutz von Bedrohungen, die für den Schutz von Geräten, Identitäten, Daten und Anwendungen entwickelt wurde.
keywords: Einführung in Microsoft Threat Protection, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 573f30dc3d8a43a337a4333dbaf05baf916857fa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357899"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Möchten Sie Microsoft 365 Defender erfahren? Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [ihr Pilotprojekt in der Produktion ausführen](https://aka.ms/m365d-pilotplaybook).
>

Microsoft 365 Defender ist eine einheitliche, vor-und nach Verletzung der Enterprise Defense-Suite, die die Erkennung, Verhinderung, Untersuchung und Antwort über alle Endpunkte, Identitäten, e-Mails und Anwendungen hinweg einheitlich koordiniert und einen integrierten Schutz vor anspruchsvollen Angriffen bietet.

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungs Signale, die von diesen Produkten empfangen werden, zusammenfügen und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen. wie Sie in die Umgebung eingingen, welche Auswirkungen Sie hat und wie Sie sich derzeit auf die Organisation auswirkt. Microsoft 365 Defender unternimmt automatische Aktionen zum verhindern oder Beenden des Angriffs und zur Selbstheilung betroffener Postfächer, Endpunkte und Benutzeridentitäten.  


<center><h2>Microsoft 365 Defender-Dienste</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender für Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender für Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender für Identity</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud-App-Sicherheit</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Lesen Sie diesen [interaktiven Leitfaden für Microsoft 365 Defender](https://aka.ms/MTP-Interactive-Guide).


Microsoft 365 Defender Suite schützt: 
- **Endpunkte mit Microsoft Defender für Endpoint** -Microsoft Defender for Endpoint ist eine einheitliche Endpunkt Plattform für vorbeugenden Schutz, Erkennung nach einem Verstoß, automatische Untersuchung und Antwort. 
- **E-Mail und Zusammenarbeit mit Microsoft Defender für Office 365** -Defender für Office 365 schützt Ihre Organisation vor böswilligen Bedrohungen durch e-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. 
- Identitäten **mit Microsoft Defender for Identity and Azure AD Identity Protection** – Microsoft Defender for Identity verwendet Active Directory Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insider Aktionen, die an Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen. 
- **Anwendungen mit Microsoft Cloud App Security** -Microsoft Cloud App Security ist eine umfassende Cross-SaaS-Lösung, die eine Tiefe Sichtbarkeit, starke Datensteuerelemente und einen verbesserten Bedrohungsschutz für Ihre Cloud-apps bringt. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Die einzigartige produktübergreifende produktschicht von Microsoft 365 Defender erweitert die einzelnen Suite-Komponenten um:
- Schützen von Angriffen und koordinieren von Abwehrreaktionen in der gesamten Suite durch Signal Freigabe und automatisierte Aktionen
- Erzählen Sie die ganze Geschichte des Angriffs auf Produktwarnungen, Verhaltensweisen und Kontexte für Sicherheitsteams, indem Sie Daten zu Warnungen, verdächtigen Ereignissen und betroffenen Objekten auf "Incidents" miteinander verknüpfen.
- Automatisieren der Antwort auf Kompromisse durch Auslösen der Selbstheilung für Betroffene Objekte durch automatische Behebung
- Aktivieren von Sicherheitsteams für die Durchführung detaillierter und effektiver Bedrohungen bei der Suche über Endpunkt-und Office-Daten

![Seite "Abbildung der Vorfall Übersicht"](../../media/overview-incident.png) <br>
Produktübergreifender Vorfall (Übersicht)

![Bild der Warnungs Warteschlange](../../media/incident-list.png)<br>
Alle zusammengehörigen Warnungen in allen Suite-Produkten korrelieren in einem einzelnen Vorfall (Warnungsansicht)

![Bild der Vorfall Warteschlange](../../media/advanced-hunting.png)<br>
Abfragebasierte Suche über die Rohdaten von e-Mail-und Endpunkt Daten


Zu den produktübergreifenden Features von Microsoft 365 Defender gehören: 
- **Produktübergreifender Einzelbereich von Glass** -Central alle Informationen für Erkennungen, Betroffene Objekte, automatisierte Aktionen und zugehörige Beweise in einer einzelnen Warteschlange und in einem einzelnen Bereich in [Security.Microsoft.com](https://security.microsoft.com). 
- **Kombinierte Vorfälle-Warteschlange** – um Sicherheitsexperten zu helfen, sich auf das zu konzentrieren, was entscheidend ist, indem Sie sicherstellen, dass der vollständige Angriffsbereich, die betroffenen Ressourcen und die automatisierten Korrekturaktionen zusammengefasst und rechtzeitig aufgetaucht werden. 
- **Automatische Antwort auf Bedrohungen** – wichtige Informationen zur Bedrohung werden in Echtzeit zwischen den Microsoft 365 Defender-Produkten freigegeben, um das Fortschreiten eines Angriffs zu unterbrechen. Wenn beispielsweise eine Schadsoftware auf einem Endpunkt erkannt wird, der von Microsoft Defender für Endpoint geschützt ist, wird Defender für Office 365 angewiesen, die Datei aus allen e-Mail-Nachrichten zu überprüfen und zu entfernen. Die Datei wird von der gesamten Microsoft 365 Security Suite aus Sicht blockiert.
- **Selbstheilung für kompromittierte Geräte, Benutzeridentitäten und Postfächer** – Microsoft 365 Defender verwendet automatische Aktionen und Textbuch mit AI-Leistung, um betroffene Objekte wieder in einen sicheren Zustand zu verlagern. Microsoft 365 Defender nutzt die automatischen Korrekturfunktionen der Suite-Produkte, um sicherzustellen, dass alle betroffenen Objekte, die sich auf einen Vorfall beziehen, nach Möglichkeit automatisch behoben werden.
- **Produktübergreifende Bedrohungs Jagd** – Sicherheitsteams können Ihr einzigartiges organisatorisches Wissen nutzen, um nach Zeichen von Kompromissen zu suchen, indem Sie Ihre eigenen benutzerdefinierten Abfragen über die Rohdaten erstellen, die von den verschiedenen Schutzprodukten erfasst werden. Microsoft 365 Defender bietet abfragebasierten Zugriff auf 30 Tage historischer RAW-Signale und Warnungsdaten über den Endpunkt und Microsoft Defender für Office 365 Daten. 


## <a name="get-started"></a>Erste Schritte
Die Microsoft 365 Defender-Lizenzierungsanforderungen müssen erfüllt sein, bevor Sie den Dienst im Microsoft 365 Security Center unter [Security.Microsoft.com](https://security.microsoft.com)aktivieren können. Weitere Informationen finden Sie unter:
- [Lizenzanforderungen](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender aktivieren](mtp-enable.md)
