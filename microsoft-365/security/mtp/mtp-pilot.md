---
title: Ausführen des Microsoft 365 -Pilotprojekts
description: Führen Sie Ihr Microsoft 365 -Pilotprojekt in der Produktion aus, um die Vorteile und die Akzeptanz von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft Threat Protection-Pilotprojekt, Ausführen eines Microsoft Threat Protection-Pilotprojekts, Bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933030"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ausführen des Microsoft 365 -Pilotprojekts 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieses Handbuch unterstützt Sie bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Maßnahmen versehen, mit deren Hilfe Sie die Ergebnisse widerspiegeln und dokumentieren können.

![Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


Das Ausführen eines Pilotprojekts hilft Ihnen dabei, den Vorteil der Einführung von Microsoft 365 Defender effektiv zu ermitteln. Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Verwendungsfälle starten, empfiehlt es sich, die für Ihr Pilotprojekt auszuführende Aufgabe zu bestimmen und die Erfolgskriterien festzulegen. 


## <a name="how-to-use-this-pilot-playbook"></a>Verwenden dieses Pilotspielbuchs

Dieses Handbuch bietet eine Übersicht über Microsoft 365 Defender und schrittweise Anweisungen zum Einrichten Ihres Pilotprojekts. 

Microsoft 365 Defender ist eine einheitliche Suite vor und nach der Verletzung des Unternehmens, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion über Endpunkte, Identitäten, E-Mails und Anwendungen hinweg koordiniert, um integrierten Schutz vor ausgeklügelten Angriffen zu bieten. Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und orchestriert:
  - Microsoft Defender for Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)
  - Microsoft Defender für Office 365, der neue Name für Office 365 ATP (E-Mail) 
  - Microsoft Defender for Identity, der neue Name für Azure ATP (Identität) 
  - Microsoft Cloud App Security (Apps)

![Abbildung of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkte, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale zusammenbringen, die Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security erhalten, und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie sie in die Umgebung eintrat, was sie beeinflusst und wie sie sich aktuell auf die Organisation auswirken. Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu stoppen und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu löschen. Weitere Informationen finden Sie in der [Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) Defender-Übersicht.



Die folgende Beispielzeitachse hängt davon ab, ob sie über die richtigen Ressourcen in Ihrer Umgebung verfügen. Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.

![Beispielzeitachse bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.


### <a name="pilot-playbook-phases"></a>Phasen des Pilotspielbuchs 

Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts:

|Phase | Beschreibung | 
|:-------|:-----|
| [Planung](mtp-pilot-plan.md)<br> ~ 1 Tag| Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen: <br><br>– Bereich <br> – Verwendungsfälle <br>– Anforderungen <br>– Testplan <br> – Erfolgskriterien <br> - Scorecard 
| [Vorbereitung](mtp-evaluation.md) <br>~2 Tage|  Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung zu einrichten. Sie werden geführt zu:<br><br>– Identifizieren von Beteiligten und Abmelden für Ihr Pilotprojekt <br> – Überlegungen zur Umgebung <br>– Zugriff <br>– Azure Active Directory Setup <br> – Konfigurationsreihenfolge <br> – Registrieren für die Testversion von Microsoft 365 E5 <br> - Konfigurieren der Domäne <br>– Zuweisen von Microsoft 365 E5-Lizenzen <br> – Abschließen des Setup-Assistenten im Portal|
| [Angriffssimulation](mtp-pilot-simulate.md) <br>~2 Tage| Um einen Angriff zu simulieren, werden Sie geführt zu:<br><br>– Überprüfen der Anforderungen an die Testumgebung <br>– Ausführen der Simulation <br>– Untersuchen eines Vorfalls <br>– Beheben des Vorfalls 
| [Schließen und Zusammenfassung](mtp-pilot-close.md) <br>~ 1 Tag| Wenn Sie das Ende des Prozesses erreicht haben, werden Sie geführt zu:<br><br>– Durchgehen der endgültigen Ausgabe<br>– Präsentieren Ihrer Ergebnisse für Ihre Projektbeteiligten <br>– Feedback geben <br>– Nächste Schritte 

## <a name="next-step"></a>Nächster Schritt
|[Planungsphase](mtp-pilot-plan.md) | Planen Ihres Microsoft 365 Defender-Pilotprojekts 
|:-------|:-----|
