---
title: Vorbereiten Ihrer Sicherheitslage für Ihren ersten Vorfall
description: Richten Sie die Microsoft 365 des Mandanten für Ihren ersten Vorfall in Microsoft 365 ein.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4fc124bf8787d5880d78a4f5208bd66329da07a0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539035"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Vorbereiten Ihrer Sicherheitslage für Ihren ersten Vorfall

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Die Vorbereitung der Behandlung von Vorfällen umfasst die Einrichtung eines ausreichenden Schutzes des Netzwerks einer Organisation vor verschiedenen Arten von Sicherheitsvorfällen. Um das Risiko von Sicherheitsvorfällen zu verringern, empfiehlt das National Institute of Standards and Technology (NIST) mehrere Sicherheitspraktiken, einschließlich Risikobewertungen, Die Sicherung der Hostsicherheit, das sichere Konfigurieren von Netzwerken und das Verhindern von Schadsoftware. 

Microsoft 365 Defender kann dabei helfen, verschiedene Aspekte der Verhinderung von Vorfällen zu berücksichtigen: 

- Implementieren eines [Zero Trust-Frameworks](https://docs.microsoft.com/security/zero-trust/)
- Bestimmen Ihrer Sicherheitslage durch Zuweisen einer Bewertung mit [Microsoft Secure Score](microsoft-secure-score.md)
- Verhindern von Bedrohungen durch Sicherheitsrisikobewertungen im [Bedrohungs- und Sicherheitsrisikomanagement](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Grundlegendes zu den neuesten Sicherheitsbedrohungen, damit Sie sich darauf vorbereiten können

## <a name="step-1-implement-zero-trust"></a>Schritt 1. Implementieren der Nullvertrauensstellung

[Zero Trust](https://docs.microsoft.com/security/zero-trust/) ist eine integrierte Sicherheitsphilosophie und End-to-End-Strategie, die den komplexen Charakter jeder modernen Umgebung berücksichtigt, einschließlich der mobilen Mitarbeiter und der Benutzer, Geräte, Anwendungen und Daten, unabhängig davon, wo sie sich befinden. Durch die Bereitstellung eines einzigen Fensterausschnitts zum konsistenten Verwalten aller Erkennungen kann Microsoft 365 Defender das [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Implementieren der Leitprinzipien von Zero Trust für Ihr Sicherheitsbetriebsteam vereinfachen. 

Komponenten von Microsoft 365 Defender können Verstöße gegen Regeln anzeigen, die implementiert wurden, um Richtlinien für bedingten Zugriff für Zero Trust zu erstellen, indem Daten von Microsoft Defender for Endpoint (MDE) oder anderen mobilen Sicherheitsanbietern als Informationsquelle für Gerätekonformitätsrichtlinien und die Implementierung gerätebasierter Richtlinien für bedingten Zugriff integriert werden. 

Das Geräterisiko wirkt sich direkt darauf aus, auf welche Ressourcen der Benutzer dieses Geräts zugreifen kann. Die Verweigerung des Zugriffs auf Ressourcen basierend auf bestimmten Kriterien ist das Hauptthema von Zero Trust, und Microsoft 365 Defender stellt Informationen zur Verfügung, die zum Bestimmen der Kriterien auf Vertrauensebene erforderlich sind. Beispielsweise kann Microsoft 365 Defender die Softwareversionsebene eines Geräts über die Seite Bedrohungs- und Sicherheitsrisikoverwaltung bereitstellen, während Richtlinien für bedingten Zugriff Geräte mit veralteten oder anfälligen Versionen einschränken.

Die Automatisierung ist ein wichtiger Bestandteil der Implementierung und Aufrechterhaltung einer Zero Trust-Umgebung und reduziert gleichzeitig die Anzahl der Warnungen, die potenziell zu Vorfallreaktionsereignissen führen würden. Komponenten von Microsoft 365 Defender können automatisiert werden, z. B. Korrekturaktionen [(auch](m365d-autoir.md) als Untersuchungen für einen Vorfall im Microsoft 365 Security Center bezeichnet), Benachrichtigungsaktionen und sogar das Erstellen von Supporttickets wie in [ServiceNow](https://microsoft.service-now.com/sp/).

## <a name="step-2-determine-your-organizations-security-posture"></a>Schritt 2. Bestimmen der Sicherheitslage Ihrer Organisation

Als Nächstes können Organisationen die [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender verwenden, um Ihre aktuelle Sicherheitslage zu ermitteln und Empfehlungen zur Verbesserung zu berücksichtigen. Je höher die Bewertung ist, desto mehr Sicherheitsempfehlungen und Verbesserungsmaßnahmen wurden von der Organisation ergriffen. Empfehlungen für die sichere Bewertung können für verschiedene Produkte verwendet werden und es Organisationen ermöglichen, ihre Ergebnisse noch weiter zu erhöhen. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Beispiel für Microsoft Secure Score im Microsoft Security Center":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Schritt 3: Bewerten der Sicherheitsrisikorisiken In Ihrer Organisation

Die Verhinderung von Vorfällen kann dazu beitragen, die Sicherheitsvorgänge zu optimieren, um sich auf wichtige und wichtige Sicherheitsvorfälle zu konzentrieren. Softwarerisiken sind häufig ein verhinderbarer Einstiegspunkt für Angriffe, die zu Datendiebstahl, Datenverlust oder Unterbrechungen des Geschäftsbetriebs führen können. Wenn keine Angriffe im Einsatz sind, müssen Sicherheitsvorgänge bestrebt sein, ein akzeptables Maß an Sicherheitsrisiko [in](../defender-endpoint/tvm-exposure-score.md) ihrer Organisation zu erreichen und auf dem Niveau zu halten.

Um den Fortschritt des Softwarepatchings zu überprüfen, besuchen Sie die Seite Bedrohungs- und Sicherheitsrisikoverwaltung in Defender for Endpoint, auf die Sie über Microsoft 365 Defender über die Registerkarte Weitere Ressourcen **zugreifen** können. [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Beispiel für die Seite &quot;Bedrohung und Sicherheitsanfälligkeit&quot; im Microsoft Security Center"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Verstehen neuer Bedrohungen

Verwenden [Sie die Bedrohungsanalyse](threat-analytics.md) im Microsoft 365 Security Center, um mit der aktuellen Sicherheitsrisikolandschaft auf dem neuesten Stand zu bleiben. Erfahrene Microsoft-Sicherheitsforscher erstellen Berichte, in denen die neuesten Cyberbedrohungen detailliert beschrieben werden, damit Sie verstehen können, wie sich diese auf Ihr Microsoft 365, Geräte und Benutzer auswirken können. Diese Berichte können Folgendes umfassen:

- Aktive Bedrohungsakteure und ihre Kampagnen
- Beliebte und neue Angriffstechniken
- Kritische Sicherheitsrisiken
- Allgemeine Angriffsoberflächen
- Verbreitete Schadsoftware

Die Bedrohungsanalyse betrachtet auch Ihre Konfiguration und Warnungen, um festzustellen, wie riskant Sie sind und ob aktive Warnungen für einen Bericht gelten.

Sie können die Empfehlungen einer neuen Bedrohung implementieren, um Ihre Sicherheitslage zu stärken und ihre Angriffsfläche zu minimieren.

Nehmen Sie sich Zeit in Ihrem Zeitplan, um den Abschnitt [Threat Analytics](threat-analytics.md) des Microsoft 365 zu überprüfen.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 1: Erfahren Sie, wie Sie Vorfälle analysieren und analysieren.](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Erfahren Sie, [wie Sie Vorfälle triagen und analysieren.](first-incident-analyze.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
