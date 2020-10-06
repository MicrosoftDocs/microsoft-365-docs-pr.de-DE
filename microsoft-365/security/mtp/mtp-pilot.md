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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3d7156dfe65e9479f2505d196790800c6afd1f2a
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367965"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Ausführen des Pilotprojekts "Microsoft Threat Protection" 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Um den Nutzen und die Akzeptanz von Microsoft Threat Protection (MTP) effektiv zu bestimmen, können Sie ein Pilotprojekt ausführen. Vor dem Aktivieren von Microsoft Threat Protection in Ihrer Produktionsumgebung und beginnend mit definierten Anwendungsfällen sollten Sie am besten einen Planungsprozess durchlaufen, um die Aufgaben zu ermitteln, die in diesem Pilotprojekt erfüllt sein müssen, und die Erfolgskriterien. 


## <a name="how-to-use-this-pilot-playbook"></a>Vorgehensweise zum Verwenden dieses Pilot Manuskripts

Dieses Handbuch enthält eine Übersicht über Microsoft Threat Protection und schrittweise Anleitungen zum Einrichten Ihres Pilotprojekts. 

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
