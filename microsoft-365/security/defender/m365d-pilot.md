---
title: Ausführen des Pilotprojekts Microsoft 365 Defender Projekts
description: Führen Sie Ihr Pilotprojekt Microsoft 365 Defender Projekt in der Produktion aus, um die Vorteile und die Einführung von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft 365 Defender Pilotprojekt, Pilotphase Microsoft 365 Defender Projekt ausführen, Microsoft 365 Defender in der Produktion auswerten, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289955"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ausführen des Pilotprojekts Microsoft 365 Defender Projekts 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieser Leitfaden hilft Ihnen bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Take-Aways für Sie starten, um ergebnisse zu berücksichtigen und zu dokumentieren.

![Phasen der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


Die Durchführung eines Pilotprojekts hilft Ihnen, den Vorteil der Einführung von Microsoft 365 Defender effektiv zu ermitteln. Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Anwendungsfälle starten, sollten Sie die für Ihr Pilotprojekt auszuführenden Aufgaben ermitteln und die Erfolgskriterien festlegen. 


## <a name="how-to-use-this-pilot-playbook"></a>So verwenden Sie dieses Pilot-Playbook

Dieses Handbuch enthält eine Übersicht über Microsoft 365 Defender und schrittweise Anleitungen zum Einrichten Ihres Pilotprojekts. 

Microsoft 365 Defender ist eine einheitliche Verteidigungssuite vor und nach einem Angriff, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion auf Endpunkte, Identitäten, E-Mails und Anwendungen nativ koordiniert, um integrierten Schutz vor komplexen Angriffen bereitzustellen. Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und koordiniert:

- Microsoft Defender für Endpunkt (Endpunkte)
- Microsoft Defender für Office 365 (E-Mail)
- Microsoft Defender for Identity (Identität)
- Microsoft Cloud App Security (Apps)

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkt, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale, die Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security empfangen, zusammenfügen und den gesamten Umfang und die Auswirkungen der Bedrohung ermitteln, wie sie in die Umgebung gelangt sind, was sie betrifft und wie sie sich derzeit auf die Organisation auswirkt. Microsoft 365 Defender führt automatische Maßnahmen aus, um den Angriff zu verhindern oder zu beenden und die betroffenen Postfächer, Endpunkte und Benutzeridentitäten selbst zu verwunden. Weitere Informationen finden Sie in der [Microsoft 365 Defender Übersicht.](microsoft-365-defender.md)

Die folgende Beispielzeitachse hängt davon ab, ob Sie die richtigen Ressourcen in Ihrer Umgebung haben. Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.

![Beispielzeitachse beim Ausführen eines Microsoft 365 Defender Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilotanweisungen so genau wie möglich.

### <a name="pilot-playbook-phases"></a>Pilot-Playbookphasen

Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender Pilotprojekts:

|Phase | Beschreibung |
|:-------|:-----|
| [Planung](m365d-pilot-plan.md)<br> ~ 1 Tag| Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen: <br><br>– Bereich <br> – Anwendungsfälle <br>– Anforderungen <br>– Testplan <br> – Erfolgskriterien <br> – Scorecard 
| [Vorbereitung](m365d-evaluation.md) <br>~2 Tage|  Greifen Sie auf Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>– Identifizieren von Beteiligten und Anfordern der Anmeldung für Ihr Pilotprojekt <br> – Überlegungen zur Umgebung <br>– Zugriff <br>– Azure Active Directory Einrichten <br> - Konfigurationsreihenfolge <br> – Registrieren für Microsoft 365 E5 Testversion <br> - Konfigurieren der Domäne <br>– Zuweisen Microsoft 365 E5 Lizenzen <br> – Abschließen des Setup-Assistenten im Portal|
| [Angriffssimulation](m365d-pilot-simulate.md) <br>~2 Tage| Um einen Angriff zu simulieren, werden Sie zu Folgendem geführt:<br><br>– Überprüfen der Anforderungen an die Testumgebung <br>- Ausführen der Simulation <br>– Untersuchen eines Vorfalls <br>– Beheben des Vorfalls 
| [Schließen und Zusammenfassung](m365d-pilot-close.md) <br>~ 1 Tag| Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu Folgendem geführt:<br><br>– Durchlaufen Der endgültigen Ausgabe<br>– Präsentieren Ihrer Ergebnisse für Ihre Projektbeteiligten <br>– Feedback geben <br>– Führen Sie die nächsten Schritte aus 

## <a name="next-step"></a>Nächster Schritt

|[Planungsphase](m365d-pilot-plan.md) | Planen Ihres Microsoft 365 Defender-Pilotprojekts 
|:-------|:-----|
