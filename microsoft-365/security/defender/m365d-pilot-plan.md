---
title: Planen Ihres Pilotprojekts Microsoft 365 Defender
description: Planen Sie Ihr Pilotprojekt Microsoft 365 Defender-Projekts mit Projektbeteiligten, um die Erwartungen zu verwalten und ein erfolgreiches Ergebnis sicherzustellen.
keywords: Microsoft 365 Defender Pilotprojekt, Planen des Pilotprojekts Microsoft 365 Defender Projekts, Bewerten Microsoft 365 Defender in der Produktion, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6a52df8035ce6f84770a2d06c3b8c127e426622e
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458436"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planen Ihres Pilotprojekts Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

|![Planung](../../media/phase-diagrams/1-planning.png)<br/>Planung|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Vorbereitung](prepare-m365d-eval.md) | [![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[Angriff simulieren](m365d-pilot-simulate.md) | [![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Schließen und zusammenfassen](m365d-pilot-close.md)|
|--|--|--|--|
|*Sie sind hier!*| | | |

Sie befinden sich derzeit in der Planungsphase.

Um sicherzustellen, dass Ihr Pilotprojekt erfolgreich ist, ist es wichtig, sorgfältig mit Ihren Projektbeteiligten zu planen und die Genehmigungen von ihnen zu erhalten. Zu den Planungselementen gehören die Identifizierung von Umfang, Anwendungsfällen, Anforderungen und Erfolgskriterien.

Dieser Leitfaden führt Sie durch die Planung Ihres Pilotprojekts. 

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilotanweisungen so genau wie möglich.


## <a name="scope"></a>Umfang

Der Umfang des Pilotprojekts bestimmt, wie breit der Test sein wird, basierend auf Ihrer Umgebung und akzeptablen Testmethoden. Hier sind einige Beispielbereiche, die Sie berücksichtigen sollten:

- Entwicklungs- oder Testumgebung, die Endpunkte, Server, Domänencontroller umfasst.
- Produktionsumgebung mit Microsoft 365, Azure, Active Directory-Diensten, Endpunkten und Servern

>[!NOTE]
>Wenn Sie noch nicht über die vollständigen Lizenzen verfügen, können Sie Testlizenzen erhalten, um [Microsoft 365 Defender auszuwerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) – Planen, Vorbereiten, Einrichten, Konfigurieren und Ausführen Ihres Pilotprojekts. Ihre Projektbeteiligten spielen eine große Rolle bei der Vereinfachung des Prozesses von Anfang bis Ende.

Die zu bewertenden Betriebssystemtypen sollten auch basierend auf dem Organisations-Make-up definiert werden. Dies kann Folgendes umfassen: [Mac-Endpunkte,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux-Server,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10-Endpunkte,](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Anwendungsfälle

Anwendungsfälle stellen Anweisungen dar, wie das getestete Tool von den beabsichtigten Benutzern genutzt werden soll. Diese können aus der Sicht einer bestimmten Persona, z. B. eines SOC-Analysten, als User Stories formuliert werden. Zum Beispiel:

- Als SOC-Analyst muss ich Warnungen und Ereignisse über Geräte, Benutzer und Postfächer in meinem Netzwerk hinweg anzeigen, korrelieren, bewerten und verwalten. [Vorfallverwaltung]
- Als SOC-Analyst muss ich über das Tool und den Prozess verfügen, um böswillige Ereignisse in meinem Netzwerk automatisch zu untersuchen und darauf zu reagieren. [Automatische IR]
- Als SOC-Analyst muss ich Daten aus meiner Umgebung durchsuchen, um bekannte und potenzielle Bedrohungen und verdächtige Aktivitäten zu finden. [Erweiterte Suche]

Beachten Sie, dass diese Anwendungsfälle innerhalb der Parameter des definierten Bereichs erstellt werden sollten. Wenn beispielsweise der Umfang der Tests keine Auswertung von Tools wie Microsoft Cloud App Security umfasst, sollten Anwendungsfälle, die sich darauf als Datenquelle verlassen, nicht erstellt werden.

## <a name="requirements"></a>Anforderungen

In der Liste der Anwendungsfälle können Sie mit dem Erstellen von Anforderungen beginnen. Die Anforderungen umfassen Features, die ein Tool aufweisen muss, um die Anwendungsfälle zu erfüllen. Diese Anforderungen können in Kategorien unterteilt werden, z. B. Konfiguration und Wartung, Unterstützung für Integrationen und featurespezifische Anforderungen wie suchfähigkeit und die Möglichkeit, benutzerdefinierte Warnungen zu erstellen.

## <a name="test-plan"></a>Testplan

Je nach den Anforderungen sind möglicherweise unterschiedliche Testmethoden geeignet. Wenn beispielsweise die Notwendigkeit besteht, die Effizienz der automatisierten Wartung zu bewerten, muss der Testplan Schritte zum Generieren der Verhaltensweisen enthalten, die eine automatisierte Korrekturaktion innerhalb Microsoft 365 Defender auslösen würden. Wenn es erforderlich ist, ein bestimmtes Verhalten oder einen bestimmten Angriff zu erkennen, kann der Test weitere Schritte umfassen. Der Punkt ist, dass ein Plan vorhanden ist, um ihre Anforderungen genau zu testen.

## <a name="success-criteria"></a>Erfolgskriterien

Erfolgskriterien sind letztendlich die Leiste, die festgelegt ist, um zu messen, was Sie testen. Unabhängig davon, ob Sie Microsoft 365 Defender (oder eine andere Technologie für diese Frage) mit anderen Tools oder allein testen, müssen einige quantifizierbare Kriterien vorhanden sein, um den Wert zu bestimmen, den das Tool bereitstellt. Basierend auf dem Umfang, den Anforderungen und dem Testplan bestimmen die Erfolgskriterien, wie der Test bewertet wird. Dies sollte weniger für einen Durchlauf oder Fehler als auch für eine gewichtete Bewertung sein, die ihren Anforderungen entspricht. Um beispielsweise erfolgreich zu sein, muss ein Tool in bestimmten wichtigen Bereichen, die Sie identifizieren, möglicherweise über 80 % punkten.

## <a name="scorecard"></a>Scorecard

Eine Möglichkeit, alle Elemente Ihres Plans zusammenzuführen, kann das Erstellen einer Scorecard sein. Sehen Sie sich unten eine Beispielscorecard an:

| Anwendungsfall | Anforderungen | Konfigurationsanforderungen | Testplan | Erwartetes Ergebnis | Teststatus | Bewertung | Notes |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Verwaltung von Sicherheitsvorfällen|– Microsoft 365 Defender </br></br>– Microsoft Defender for Identity </br></br>– Microsoft Defender für Endpunkt </br></br>- Microsoft Cloud App Security (optional)|Weitere Informationen finden Sie unter den [Voraussetzungen](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) für Vorbereitung, Einrichtung und Konfiguration. |[Angriff simulieren](m365d-pilot-simulate.md) <br></br>[Untersuchen des Vorfalls](./m365d-pilot-simulate.md#investigate-an-incident) |Ermittler können den Umfang und die Auswirkungen des Vorfalls verstehen und den Vorfall verwalten.||||
|AutoIR|– Microsoft 365 Defender </br></br>– Microsoft Defender for Identity </br></br>– Microsoft Defender für Endpunkt |Weitere Informationen finden Sie unter den [Voraussetzungen](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) für Vorbereitung, Einrichtung und Konfiguration. <br>AutoIR aktivieren  |[Angriff simulieren](m365d-pilot-simulate.md) <br></br>[Automatisierte Untersuchung](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Warnungen und Vorfälle werden automatisch durch Microsoft 365 Defender behoben.||||
|Erweiterte Bedrohungssuche|– Microsoft 365 Defender </br></br>– Microsoft Defender für Endpunkt </br></br>-Microsoft Defender für Office 365 |Weitere Informationen finden Sie unter den [Voraussetzungen](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) für Vorbereitung, Einrichtung und Konfiguration.|[Szenario "Erweiterte Suche"](./m365d-pilot-simulate.md#advanced-hunting-scenario) |Ermittler können Daten durch erweiterte Suche, Pivoting auf betroffene Entitäten und durch Erstellen benutzerdefinierter Erkennungen finden.||||

## <a name="next-step"></a>Nächster Schritt

|![Vorbereitungsphase](../../media/mtp/prep.png) <br>[Vorbereitungsphase](prepare-m365d-eval.md) | Vorbereiten der Microsoft 365 Defender Pilotumgebung
|:-------|:-----|
