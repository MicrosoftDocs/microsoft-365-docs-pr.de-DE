---
title: Planen des Pilotprojekts "Microsoft 365 Defender"
description: Planen Sie Ihr Pilotprojekt "Microsoft 365 Defender" mit Beteiligten, um die Erwartungen zu verwalten und ein erfolgreiches Ergebnis sicherzustellen.
keywords: Microsoft Threat Protection Pilotprojekt, Plan Pilot Microsoft Threat Protection Project, bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection Pilotprojekt, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 4420342f964564305bb113c45ee0e3107f8a822e
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130981"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planen des Pilotprojekts "Microsoft 365 Defender" 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

|![Planung](../../media/phase-diagrams/1-planning.png)<br/>Planung|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Vorbereitung](prepare-mtpeval.md) | [![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Angriff simulieren](mtp-pilot-simulate.md) | [![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Schließen und zusammenfassen](mtp-pilot-close.md)|
|--|--|--|--|
|*Sie sind hier!*| | | |

Sie befinden sich derzeit in der Planungsphase.

Um sicherzustellen, dass das Pilotprojekt erfolgreich verläuft, ist es wichtig, dass Sie die Genehmigungen ihrer Beteiligten am Anfang sorgfältig planen und erhalten. Zu den Planungselementen gehören das Identifizieren von Umfang, Anwendungsfällen, Anforderungen und Erfolgskriterien.

In diesem Leitfaden wird erläutert, wie Sie Ihr Pilotprojekt planen. 

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.


## <a name="scope"></a>Bereich

Der Bereich des Pilotprojekts bestimmt, wie breit der Test ist, basierend auf Ihrer Umgebung und den zulässigen Testmethoden. Hier sind einige Beispiel Bereiche, die zu prüfen sind:
- Entwicklungs-oder Testumgebung mit Endpunkten, Servern, Domänencontrollern.
- Produktionsumgebung mit Microsoft 365, Azure, Active Directory Diensten, Endpunkten und Servern

>[!NOTE]
>Wenn Sie noch nicht über die vollständigen Lizenzen verfügen, können Sie Testlizenzen zur [Evaluierung von Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) erhalten – planen, vorbereiten, einrichten, konfigurieren und Ausführen des Pilotprojekts. Ihre Beteiligten werden eine wichtige Rolle dabei spielen, den Prozess von Anfang bis Ende zu erleichtern.

Die Typen der auszuwertenden Betriebssysteme sollten auch basierend auf der organisatorischen Verfassung definiert werden. Dies kann Folgendes umfassen: [Mac-Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-Server](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Anwendungsfälle

Anwendungsfälle stellen Anweisungen dar, wie das zu testende Tool von den vorgesehenen Benutzern verwendet werden soll. Diese können als Benutzergeschichten aus der Sicht einer bestimmten Person formuliert werden, beispielsweise als SOC-Analyst. Beispiel:
- Als SOC-Analyst muss ich Warnungen und Ereignisse für Geräte, Benutzer und Postfächer in meinem Netzwerk anzeigen, korrelieren, bewerten und verwalten. [Vorfallverwaltung]
- Als SOC-Analyst muss ich das Tool und den Prozess zum automatischen untersuchen und reagieren auf böswillige Ereignisse in meinem Netzwerk haben. [Auto IR]
- Als SOC-Analyst muss ich Daten aus meiner Umgebung suchen, um bekannte und potenzielle Bedrohungen sowie verdächtige Aktivitäten zu finden. [Erweiterte Suche]

Beachten Sie, dass diese Anwendungsfälle innerhalb der Parameter des definierten Bereichs erstellt werden sollten. Wenn beispielsweise der Testumfang keine Evaluierung von Tools wie Microsoft Cloud App Security umfasst, sollten Anwendungsfälle, die sich auf diese als Datenquelle stützen, nicht erstellt werden.

## <a name="requirements"></a>Anforderungen

In der Liste der Anwendungsfälle können Sie mit dem Erstellen von Anforderungen beginnen. Anforderungen umfassen Features, die ein Tool zum erfüllen der Anwendungsfälle benötigen muss. Diese Anforderungen können in Kategorien wie Konfiguration und Wartung, Unterstützung für Integrationen und funktionsspezifische Anforderungen wie die Jagd Fähigkeit und die Möglichkeit zum Erstellen von benutzerdefinierten Warnungen aufgeteilt werden.

## <a name="test-plan"></a>Testplan

Je nach Anforderungen können unterschiedliche Testmethoden geeignet sein. Wenn beispielsweise die Effizienz der automatischen Behebung bewertet werden soll, muss der Testplan Schritte zum Generieren des Verhaltens (s) enthalten, das eine automatisierte Korrekturaktion in Microsoft 365 Defender auslösen würde. Wenn die Anforderung ein bestimmtes Verhalten oder einen Angriff erkennen soll, kann der Test weitere Schritte beinhalten. Der Punkt besteht darin, dass ein Plan vorhanden ist, mit dem die Anforderungen genau getestet werden.

## <a name="success-criteria"></a>Erfolgskriterien

Die Erfolgskriterien sind letztendlich das balkenset, das anhand des Tests gemessen wird. Unabhängig davon, ob Sie Microsoft 365 Defender (oder eine andere Technologie für diese Angelegenheit) für andere Tools oder für sich selbst testen, muss es einige quantifizierbare Kriterien geben, um den vom Tool bereitgestellten Wert zu ermitteln. Basierend auf dem Umfang, den Anforderungen und dem Testplan bestimmen die Erfolgskriterien, wie der Test bewertet wird. Dies sollte ein geringerer Pass oder ein fehlgeschlagener oder ein größerer Teil eines gewichteten Scorings sein, das auf Ihren Anforderungen basiert. Um beispielsweise erfolgreich zu sein, muss ein Tool möglicherweise in bestimmten von Ihnen identifizierten kritischen Bereichen über 80% Punkten.

## <a name="scorecard"></a>Scorecard

Eine Möglichkeit, alle Elemente Ihres Plans zusammenzuführen, kann das Erstellen einer Scorecard sein. Eine Beispiel-Scorecard finden Sie weiter unten:

| Anwendungsfall | Anforderungen | Konfigurationsanforderungen | Testplan | Erwartetes Ergebnis | Test Status | Bewertung | Anmerkungen |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Vorfallverwaltung|-Microsoft 365 Defender  </br></br>-Microsoft Defender für Identity </br></br>-Microsoft Defender für Endpoint </br></br>-Microsoft Cloud-App-Sicherheit (optional)|Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration. |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Untersuchen des Vorfalls](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Ermittler können den Umfang und die Auswirkungen des Vorfalls verstehen und den Vorfall verwalten.||||
|AutoIR|-Microsoft 365 Defender </br></br>-Microsoft Defender für Identity </br></br>-Microsoft Defender für Endpoint |Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration. <br>AutoIR aktivieren  |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Automatische Untersuchung](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Warnungen und Vorfälle werden automatisch von Microsoft 365 Defender behoben.||||
|Erweiterte Suche|-Microsoft 365 Defender </br></br>-Microsoft Defender für Endpoint </br></br>-Microsoft Defender für Office 365 |Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration.|[Erweitertes Jagd Szenario](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Ermittler können Daten über erweitertes suchen, pivotieren für betroffene Entitäten und durch Erstellen von benutzerdefinierten Erkennungen finden.||||



## <a name="next-step"></a>Nächster Schritt
|![Vorbereitungsphase](../../media/mtp/prep.png) <br>[Vorbereitungsphase](prepare-mtpeval.md) | Vorbereiten der Pilotumgebung für Microsoft 365 Defender
|:-------|:-----|
