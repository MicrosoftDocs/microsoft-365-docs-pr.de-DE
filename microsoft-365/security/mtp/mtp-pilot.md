---
title: Ausführen des Pilotprojekts "Microsoft 365 Defender"
description: Führen Sie das Microsoft 365 Defender-Pilotprojekt in Production aus, um die Vorteile und die Akzeptanz von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft Threat Protection Pilotprojekt, Ausführen eines Pilotprojekts für Microsoft Threat Protection, bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131290"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ausführen des Pilotprojekts "Microsoft 365 Defender" 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Um den Nutzen und die Akzeptanz von Microsoft 365 Defender effektiv zu bestimmen, können Sie ein Pilotprojekt ausführen. Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und ihre Anwendungsfälle starten, sollten Sie die für ihr Pilotprojekt zu erledigenden Aufgaben bestimmen und die Erfolgskriterien festlegen. 


## <a name="how-to-use-this-pilot-playbook"></a>Vorgehensweise zum Verwenden dieses Pilot Manuskripts

Dieses Handbuch enthält eine Übersicht über Microsoft 365 Defender und Schritt-für-Schritt-Anleitungen zum Einrichten Ihres Pilotprojekts. 

Microsoft 365 Defender ist eine einheitliche, vor-und nach Verletzung der Enterprise Defense-Suite, die den Schutz, die Erkennung, Verhinderung, Untersuchung und Antwort über alle Endpunkte, Identitäten, e-Mails und Anwendungen hinweg einheitlich koordiniert und einen integrierten Schutz vor anspruchsvollen Angriffen bietet. Dies geschieht durch kombinieren und orchestrieren der folgenden Funktionen in einer einzigen Sicherheitslösung:
  - Microsoft Defender für Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)
  - Microsoft Defender für Office 365, der neue Name für Office 365 ATP (e-Mail) 
  - Microsoft Defender for Identity, der neue Name für Azure ATP (Identity) 
  - Microsoft Cloud-App-Sicherheit (Apps)

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte von Microsoft Defender für Endpoint, für Cloud-apps, Microsoft Cloud-App-Sicherheit und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungs Signale, die Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security erhält, zusammenfügen und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie Sie in die Umgebung eingedrungen ist, welche Auswirkungen Sie hat und wie Sie sich derzeit auf die Organisation auswirkt. Microsoft 365 Defender unternimmt automatische Aktionen zum verhindern oder Beenden des Angriffs und zur Selbstheilung betroffener Postfächer, Endpunkte und Benutzeridentitäten. Ausführliche Informationen finden Sie in der [Microsoft 365 Defender-Übersicht](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .

![Phasen bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)

Das folgende Beispiel Zeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung. Einige Erkennungen und Workflows benötigen möglicherweise mehr Lern Zeit als die anderen.

![Beispiel Zeitachse in Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.


### <a name="pilot-playbook-phases"></a>Phasen des Pilot Textbuch 

Bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts gibt es vier Phasen:

|Phase | Beschreibung | 
|:-------|:-----|
| [Planung](mtp-pilot-plan.md)<br> ~ 1 Tag| Hier erfahren Sie, was Sie vor der Ausführung Ihres Microsoft 365 Defender-Pilotprojekts besprechen sollten: <br><br>-Scope <br> -Anwendungsfälle <br>– Anforderungen <br>-Testplan <br> -Erfolgskriterien <br> -Scorecard 
| [Vorbereitung](mtp-evaluation.md) <br>~ 2 Tage|  Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>-Identifizieren von Beteiligten und suchen der Anmeldung für ihr Pilotprojekt <br> -Umgebungs Überlegungen <br>-Access <br>-Azure-Active Directory-Setup <br> -Konfigurations Reihenfolge <br> -Registrieren für Microsoft 365 E5-Testversion <br> -Domäne konfigurieren <br>-Zuweisen von Microsoft 365 E5-Lizenzen <br> -Abschließen des Setup-Assistenten im Portal|
| [Angriffssimulation](mtp-pilot-simulate.md) <br>~ 2 Tage| Um einen Angriff zu simulieren, werden Sie zu folgenden Themen geführt:<br><br>-Überprüfen der Anforderungen an die Testumgebung <br>-Simulation ausführen <br>-Untersuchen eines Vorfalls <br>-Beheben des Vorfalls 
| [Schließen und Zusammenfassung](mtp-pilot-close.md) <br>~ 1 Tag| Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu folgenden Themen geführt:<br><br>– Durchlaufen der endgültigen Ausgabe<br>-Präsentieren ihrer Ausgaben für Ihre Stakeholder <br>-Feedback geben <br>– Nächste Schritte ausführen 

## <a name="next-step"></a>Nächster Schritt
|[Planungsphase](mtp-pilot-plan.md) | Planen des Pilotprojekts für Microsoft 365 Defender 
|:-------|:-----|
