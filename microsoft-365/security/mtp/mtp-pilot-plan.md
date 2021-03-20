---
title: Planen Ihres Microsoft 365 Defender-Pilotprojekts
description: Planen Sie Ihr Microsoft 365 Defender-Pilotprojekt mit Denkbeteiligten, um die Erwartungen zu verwalten und ein erfolgreiches Ergebnis sicherzustellen.
keywords: Microsoft Threat Protection-Pilotprojekt, Planen des Microsoft Threat Protection-Pilotprojekts, Bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
ms.openlocfilehash: 2f5cf2d26682e1b3be139fdabe521be6170a1732
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903916"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planen Ihres Microsoft 365 Defender-Pilotprojekts 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

|![Planung](../../media/phase-diagrams/1-planning.png)<br/>Planung|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Vorbereitung](prepare-mtpeval.md) | [![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Angriff simulieren](mtp-pilot-simulate.md) | [![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Schließen und zusammenfassen](mtp-pilot-close.md)|
|--|--|--|--|
|*Sie sind hier!*| | | |

Sie sind derzeit in der Planungsphase.

Um sicherzustellen, dass Ihr Pilotprojekt erfolgreich ist, ist es wichtig, dass Sie gründlich planen und am Anfang Genehmigungen von Ihren Projektbeteiligten erhalten. Zu den Planungselementen gehören das Identifizieren von Bereich, Verwendungsfällen, Anforderungen und Erfolgskriterien.

In diesem Leitfaden erfahren Sie, wie Sie Ihr Pilotprojekt planen. 

>[!IMPORTANT]
>Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.


## <a name="scope"></a>Bereich

Der Umfang des Pilotprojekts bestimmt, wie breit der Test sein wird, basierend auf Ihrer Umgebung und akzeptablen Testmethoden. Im Folgenden finden Sie einige Beispielbereiche, die Sie berücksichtigen sollten:
- Entwicklungs- oder Testumgebung, die Endpunkte, Server, Domänencontroller umfasst.
- Produktionsumgebung mit Microsoft 365, Azure, Active Directory-Diensten, Endpunkten und Servern

>[!NOTE]
>Wenn Sie noch nicht über die vollständigen Lizenzen verfügen, können Sie Testlizenzen zum Bewerten [von Microsoft 365 Defender](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) erhalten – Planen, Vorbereiten, Einrichten, Konfigurieren und Ausführen Ihres Pilotprojekts. Ihre Interessengruppen spielen eine wichtige Rolle bei der Erleichterung des Prozesses von Anfang bis Ende.

Die Typen von Betriebssystemen, die ausgewertet werden sollen, sollten auch basierend auf der Organisationsstruktur definiert werden. Dies kann Folgendes umfassen: [Mac-Endpunkte](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-Server](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-Endpunkte](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Anwendungsfälle

Use Cases stellen Anweisungen dar, wie das getestete Tool von den beabsichtigten Benutzern genutzt werden soll. Diese können aus der Sicht einer bestimmten Person, z. B. eines SOC-Analysten, als Benutzerberichte formuliert werden. Beispiel:
- Als SOC-Analyst muss ich Warnungen und Ereignisse auf allen Geräten, Benutzern und Postfächern in meinem Netzwerk anzeigen, korrelieren, bewerten und verwalten. [Vorfallverwaltung]
- Als SOC-Analyst muss ich über das Tool und den Prozess verfügen, um bösartige Ereignisse in meinem Netzwerk automatisch zu untersuchen und darauf zu reagieren. [Auto IR]
- Als SOC-Analyst muss ich Daten aus meiner Umgebung durchsuchen, um bekannte und potenzielle Bedrohungen und verdächtige Aktivitäten zu finden. [Erweiterte Suche]

Beachten Sie, dass diese Verwendungsfälle innerhalb der Parameter des definierten Bereichs erstellt werden sollten. Wenn der Testbereich beispielsweise keine Auswertung von Tools wie Microsoft Cloud App Security umfasst, sollten keine Anwendungsfälle erstellt werden, die auf dieser Als Datenquelle beruhen.

## <a name="requirements"></a>Anforderungen

In der Liste der Verwendungsfälle können Sie mit dem Erstellen von Anforderungen beginnen. Zu den Anforderungen gehören Features, die ein Tool erfüllen muss, um die Verwendungsfälle zu erfüllen. Diese Anforderungen können in Kategorien unterteilt werden, z. B. Konfiguration und Wartung, Unterstützung von Integrationen und featurespezifische Anforderungen wie Die Suche und die Möglichkeit, benutzerdefinierte Warnungen zu erstellen.

## <a name="test-plan"></a>Testplan

Je nach Anforderungen sind möglicherweise unterschiedliche Testmethoden geeignet. Wenn beispielsweise die Anforderung besteht, die Wirksamkeit der automatisierten Korrektur zu bewerten, muss der Testplan Schritte zum Generieren des Verhaltens enthalten, das eine automatisierte Korrekturaktion in Microsoft 365 Defender auslösen würde. Wenn die Anforderung besteht, ein bestimmtes Verhalten oder einen bestimmten Angriff zu erkennen, kann der Test weitere Schritte umfassen. Es geht um einen Plan zum genauen Testen ihrer Anforderungen.

## <a name="success-criteria"></a>Erfolgskriterien

Erfolgskriterien sind letztendlich die Leiste, die auf das maßt, was Sie testen. Unabhängig davon, ob Sie Microsoft 365 Defender (oder eine andere Technologie in diesem Fall) mit anderen Tools oder allein testen, muss es einige quantifizierbare Kriterien zur Bestimmung des vom Tool zur Verfügung stellenen Werts gibt. Anhand des Umfangs, der Anforderungen und des Testplans bestimmen die Erfolgskriterien, wie der Test bewertet wird. Dies sollte weniger pass or fail und mehr einer gewichteten Bewertung sein, die auf Ihren Anforderungen basiert. Um z. B. erfolgreich zu sein, muss ein Tool in bestimmten kritischen Bereichen, die Sie identifizieren, möglicherweise über 80 % punkten.

## <a name="scorecard"></a>Scorecard

Eine Möglichkeit, alle Elemente Ihres Plans zusammenzubringen, kann das Erstellen einer Scorecard sein. Eine Beispiel scorecard finden Sie unten:

| Anwendungsfall | Anforderungen | Konfigurationsanforderungen | Testplan | Erwartetes Ergebnis | Teststatus | Bewertung | Anmerkungen |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Verwaltung von Sicherheitsvorfällen|- Microsoft 365 Defender  </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint </br></br>- Microsoft Cloud App Security (optional)|Weitere Informationen [finden Sie unter](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) Voraussetzungen für die Vorbereitung, Einrichtung und Konfiguration |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Untersuchen des Vorfalls](./mtp-pilot-simulate.md#investigate-an-incident) |Ermittler können den Umfang und die Auswirkungen des Vorfalls verstehen und den Vorfall verwalten||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint |Weitere Informationen [finden Sie unter](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) Voraussetzungen für die Vorbereitung, Einrichtung und Konfiguration <br>Aktivieren von AutoIR  |[Angriff simulieren](mtp-pilot-simulate.md) <br></br>[Automatisierte Untersuchung](./mtp-pilot-simulate.md#automated-investigation-and-remediation) |Warnungen und Vorfälle werden von Microsoft 365 Defender automatisch behoben||||
|Erweiterte Suche|- Microsoft 365 Defender </br></br>- Microsoft Defender for Endpoint </br></br>-Microsoft Defender für Office 365 |Weitere Informationen [finden Sie unter](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) Voraussetzungen für die Vorbereitung, Einrichtung und Konfiguration|[Szenario der erweiterten Suche](./mtp-pilot-simulate.md#advanced-hunting-scenario) |Ermittler können Daten mithilfe der erweiterten Suche, des Pivots zu betroffener Entitäten und durch Erstellen von benutzerdefinierten Erkennungen finden.||||



## <a name="next-step"></a>Nächster Schritt
|![Vorbereitungsphase](../../media/mtp/prep.png) <br>[Vorbereitungsphase](prepare-mtpeval.md) | Vorbereiten Ihrer Microsoft 365 Defender-Pilotumgebung
|:-------|:-----|