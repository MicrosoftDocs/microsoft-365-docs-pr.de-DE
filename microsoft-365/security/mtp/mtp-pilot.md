---
title: Ausführen des Pilotprojekts "Microsoft Threat Protection"
description: Führen Sie das Microsoft Threat Protection-Pilotprojekt in Production aus, um die Vorteile und die Akzeptanz von Microsoft Threat Protection (MTP) effektiv zu ermitteln.
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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477020"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Ausführen des Pilotprojekts "Microsoft Threat Protection" 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Um den Nutzen und die Akzeptanz von Microsoft Threat Protection (MTP) effektiv zu bestimmen, können Sie ein Pilotprojekt ausführen. Vor dem Aktivieren von Microsoft Threat Protection in Ihrer Produktionsumgebung und dem Starten der Anwendungsfälle empfiehlt es sich, die für ihr Pilotprojekt zu erledigenden Aufgaben zu ermitteln und die Erfolgskriterien festzulegen. 


## <a name="how-to-use-this-pilot-playbook"></a>Vorgehensweise zum Verwenden dieses Pilot Manuskripts

Dieses Handbuch enthält eine Übersicht über Microsoft Threat Protection und Schritt-für-Schritt-Anleitungen zum Einrichten Ihres Pilotprojekts. 

Microsoft Threat Protection ist eine einheitliche, vor-und nach Verletzung der Enterprise-Defense-Suite, die den Schutz, die Erkennung, Verhinderung, Untersuchung und Antwort über alle Endpunkte, Identitäten, e-Mails und Anwendungen hinweg einheitlich koordiniert und einen integrierten Schutz vor anspruchsvollen Angriffen bietet. Dies geschieht durch kombinieren und orchestrieren der folgenden Funktionen in einer einzigen Sicherheitslösung:
  - Microsoft Defender für Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)
  - Microsoft Defender für Office 365, der neue Name für Office 365 ATP (e-Mail) 
  - Microsoft Defender for Identity, der neue Name für Azure ATP (Identity) 
  - Microsoft Cloud-App-Sicherheit (Apps)

![Image of_Microsoft Threat Protection-Lösung für Benutzer, Azure Advanced Threat Protection, für Endpoint Microsoft Defender Advanced Threat Protection, für Cloud-apps, Microsoft Cloud App Security und für Daten, Office 365 Advanced Threat Protection  ](../../media/mtp/m365pillars.png)

Mit der integrierten Microsoft Threat Protection-Lösung können Sicherheitsexperten die Bedrohungs Signale, die Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP und Microsoft Cloud App Security erhält, zusammenfügen und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie Sie in die Umgebung eingedrungen ist, was Sie betrifft und wie Sie sich derzeit auf die Organisation auswirken. Microsoft Threat Protection führt automatische Aktionen aus, um den Angriff zu verhindern oder zu beenden und die betroffenen Postfächer, Endpunkte und Benutzeridentitäten selbst zu heilen. Ausführliche Informationen finden Sie in der [Microsoft Threat Protection-Übersicht](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .

![Phasen bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts](../../media/pilotphases.png)

Das folgende Beispiel Zeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung. Einige Erkennungen und Workflows benötigen möglicherweise mehr Lern Zeit als die anderen.

![Beispiel Zeitachse bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts](../../media/pilotimeline.png)

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.


### <a name="pilot-playbook-phases"></a>Phasen des Pilot Textbuch 

Bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts gibt es vier Phasen:

|Phase | Beschreibung | 
|:-------|:-----|
| ![Planung](../../media/mtp/plan.png)<br>[Planung](mtp-pilot-plan.md)| Erfahren Sie, was Sie vor der Ausführung Ihres Microsoft Threat Protection-Pilotprojekts zu prüfen haben: <br><br>-Scope <br> -Anwendungsfälle <br>– Anforderungen <br>-Testplan <br> -Erfolgskriterien <br> -Scorecard 
| ![Vorbereitung](../../media/mtp/prep.png) <br>[Vorbereitung](mtp-evaluation.md)|  Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft Threat Protection-Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>-Identifizieren von Beteiligten und suchen der Anmeldung für ihr Pilotprojekt <br> -Umgebungs Überlegungen <br>-Access <br>-Azure-Active Directory-Setup <br> -Konfigurations Reihenfolge <br> -Registrieren für Microsoft 365 E5-Testversion <br> -Domäne konfigurieren <br>-Zuweisen von Microsoft 365 E5-Lizenzen <br> -Abschließen des Setup-Assistenten im Portal|
| ![Angriffssimulation](../../media/mtp/run-sim.png) <br>[Angriffssimulation](mtp-pilot-simulate.md) | Um einen Angriff zu simulieren, werden Sie zu folgenden Themen geführt:<br><br>-Überprüfen der Anforderungen an die Testumgebung <br>-Simulation ausführen <br>-Untersuchen eines Vorfalls <br>-Beheben des Vorfalls 
| ![Schließen und Zusammenfassung](../../media/mtp/close.png) <br>[Schließen und Zusammenfassung](mtp-pilot-close.md) | Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu folgenden Themen geführt:<br><br>– Durchlaufen der endgültigen Ausgabe<br>-Präsentieren ihrer Ausgaben für Ihre Stakeholder <br>-Feedback geben <br>– Nächste Schritte ausführen 

## <a name="next-step"></a>Nächster Schritt
|![Planungsphase](../../media/mtp/plan.png) <br>[Planungsphase](mtp-pilot-plan.md) | Planen Ihres Microsoft Threat Protection-Pilotprojekts 
|:-------|:-----|
