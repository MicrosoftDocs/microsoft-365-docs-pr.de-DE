---
title: Planen des Microsoft 365 -Pilotprojekts
description: Planen Sie Ihr Microsoft 365 -Pilotprojekt mit den Projektbeteiligten, um die Erwartungen zu verwalten und ein erfolgreiches Ergebnis sicherzustellen.
keywords: Microsoft Threat Protection-Pilotprojekt, Planen des Microsoft Threat Protection-Pilotprojekts, Bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930174"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planen des Microsoft 365 -Pilotprojekts 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

|![Planung](../../media/phase-diagrams/1-planning.png)<br/>Planung|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Vorbereitung](prepare-mtpeval.md) | [![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Angriff simulieren](mtp-pilot-simulate.md) | [![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Schließen und zusammenfassen](mtp-pilot-close.md)|
|--|--|--|--|
|*Sie sind hier!*| | | |

Sie sind derzeit in der Planungsphase.

Um sicherzustellen, dass Ihr Pilotprojekt erfolgreich ist, ist es wichtig, dass Sie zu Beginn sorgfältig planen und Genehmigungen von den Projektbeteiligten einplanen. Zu den Planungselementen gehören das Identifizieren von Bereich, Verwendungsfällen, Anforderungen und Erfolgskriterien.

Dieses Handbuch führt Sie durch die Planung Ihres Pilotprojekts. 

>[!IMPORTANT]
>Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.


## <a name="scope"></a>Bereich

Der Umfang des Pilotprojekts bestimmt, wie umfassend der Test sein wird, basierend auf Ihrer Umgebung und den akzeptablen Testmethoden. Hier sind einige Beispielbereiche, die Sie berücksichtigen sollten:
- Entwicklungs- oder Testumgebung, die Endpunkte, Server, Domänencontroller umfasst.
- Produktionsumgebung mit Microsoft 365, Azure, Active Directory-Diensten, Endpunkten und Servern

>[!NOTE]
>Wenn Sie noch nicht über die vollständigen Lizenzen verfügen, können Sie Testlizenzen erhalten, um [Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) auszuwerten – Planen, Vorbereiten, Einrichten, Konfigurieren und Ausführen Ihres Pilotprojekts. Ihre Beteiligten spielen eine wichtige Rolle, um den Prozess von Anfang bis Ende zu erleichtern.

Die Typen von Betriebssystemen, die ausgewertet werden sollen, sollten auch basierend auf der Organisationsstruktur definiert werden. Dies kann Folgendes umfassen: [Mac-Endpunkte,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux-Server,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10-Endpunkte,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Anwendungsfälle

Use cases represent statements of how the tool being tested is intended to be consumed by its intended users. Diese können aus der Sicht einer bestimmten Person, z. B. eines SOC-Analysten, als Benutzergeschichten formuliert werden. Zum Beispiel:
- Als SOC-Analyst muss ich Warnungen und Ereignisse auf allen Geräten, Benutzern und Postfächern in meinem Netzwerk anzeigen, korrelieren, bewerten und verwalten. [Vorfallverwaltung]
- Als SOC-Analyst muss ich über das Tool und den Prozess verfügen, um bösartige Ereignisse in meinem Netzwerk automatisch untersuchen und darauf reagieren zu können. [Auto IR]
- Als SOC-Analyst muss ich Daten aus meiner Umgebung durchsuchen, um bekannte und potenzielle Bedrohungen sowie verdächtige Aktivitäten zu finden. [Erweiterte Suche]

Beachten Sie, dass diese Verwendungsfälle innerhalb der Parameter des definierten Bereichs erstellt werden sollten. Wenn der Testbereich beispielsweise keine Auswertung von Tools wie Microsoft Cloud App Security umfasst, sollten Keine Anwendungsfälle erstellt werden, die dies als Datenquelle verwenden.

## <a name="requirements"></a>Anforderungen

Aus der Liste der Verwendungsfälle können Sie mit dem Erstellen von Anforderungen beginnen. Zu den Anforderungen gehören Features, die ein Tool zur Erfüllung der Verwendungsfälle haben muss. Diese Anforderungen können in Kategorien unterteilt werden, z. B. Konfiguration und Wartung, Unterstützung für Integrationen und featurespezifische Anforderungen wie Suchfähigkeit und die Möglichkeit zum Erstellen benutzerdefinierter Warnungen.

## <a name="test-plan"></a>Testplan

Je nach den Anforderungen sind möglicherweise unterschiedliche Testmethoden geeignet. Wenn z. B. die Notwendigkeit besteht, die Effizienz der automatisierten Korrektur zu bewerten, muss der Testplan Schritte zum Generieren der Verhaltensweisen enthalten, die eine automatisierte Korrekturaktion in Microsoft 365 Defender auslösen würden. Wenn die Anforderung besteht, ein bestimmtes Verhalten oder einen bestimmten Angriff zu erkennen, kann der Test weitere Schritte umfassen. Der Punkt besteht in einem Plan, mit dem Sie Ihre Anforderungen genau testen können.

## <a name="success-criteria"></a>Erfolgskriterien

Erfolgskriterien sind letztendlich die Leiste, mit der gemessen wird, was Sie testen. Unabhängig davon, ob Sie Microsoft 365 Defender (oder eine andere Technologie) mit anderen Tools oder allein testen, müssen einige quantifizierbare Kriterien erfüllt sein, um den Wert zu ermitteln, den das Tool bietet. Anhand des Umfangs, der Anforderungen und des Testplans bestimmen die Erfolgskriterien, wie der Test bewertet werden soll. Dies sollte weniger pass- oder fail-bewertung und mehr einer gewichteten Bewertung basierend auf Ihren Anforderungen sein. Um z. B. erfolgreich zu sein, muss ein Tool in bestimmten kritischen Bereichen, die Sie identifizieren, möglicherweise über 80 % punkten.

## <a name="scorecard"></a>Scorecard

Eine Möglichkeit, alle Elemente Ihres Plans zusammenzubringen, kann das Erstellen einer Scorecard sein. Sehen Sie sich unten eine Beispiel scorecard an:

| Anwendungsfall | Anforderungen | Konfigurationsanforderungen | Testplan | Erwartetes Ergebnis | Teststatus | Bewertung | Anmerkungen |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Verwaltung von Sicherheitsvorfällen|- Microsoft 365 Defender  </br></br>– Microsoft Defender for Identity </br></br>– Microsoft Defender für Endpunkt </br></br>- Microsoft Cloud App Security (optional)|Weitere Informationen [finden Sie unter](https://aka.ms/mtp-trial-lab) den Voraussetzungen für vorbereitung, Einrichtung und Konfiguration |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Untersuchen des Vorfalls](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Ermittler können den Umfang und die Auswirkungen des Vorfalls verstehen und den Vorfall verwalten.||||
|AutoIR|- Microsoft 365 Defender </br></br>– Microsoft Defender for Identity </br></br>– Microsoft Defender für Endpunkt |Weitere Informationen [finden Sie unter](https://aka.ms/mtp-trial-lab) den Voraussetzungen für vorbereitung, Einrichtung und Konfiguration <br>Aktivieren der AutoIR  |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Automatisierte Untersuchung](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Warnungen und Vorfälle werden von Microsoft 365 Defender automatisch behoben||||
|Erweiterte Suche|- Microsoft 365 Defender </br></br>– Microsoft Defender für Endpunkt </br></br>-Microsoft Defender für Office 365 |Weitere Informationen [finden Sie unter](https://aka.ms/mtp-trial-lab) den Voraussetzungen für vorbereitung, Einrichtung und Konfiguration|[Szenario "Erweiterte Suche"](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |Ermittler können Daten über die erweiterte Suche, pivotieren für die betroffenEntitäten und durch Erstellen benutzerdefinierter Erkennungen finden.||||



## <a name="next-step"></a>Nächster Schritt
|![Vorbereitungsphase](../../media/mtp/prep.png) <br>[Vorbereitungsphase](prepare-mtpeval.md) | Vorbereiten Ihrer Microsoft 365 Defender-Pilotumgebung
|:-------|:-----|
