---
title: Vorbereiten des Sicherheitsstatus für Ihren ersten Vorfall
description: Richten Sie den Sicherheitsstatus Ihres Microsoft 365 Mandanten für Ihren ersten Vorfall in Microsoft 365 Defender ein.
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
ms.openlocfilehash: da9147955c5da9ea727854420b3d4d160583ef73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840934"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Vorbereiten des Sicherheitsstatus für Ihren ersten Vorfall

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Die Vorbereitung auf die Behandlung von Sicherheitsvorfällen umfasst das Einrichten eines ausreichenden Schutzes des Netzwerks einer Organisation vor verschiedenen Arten von Sicherheitsvorfällen. Um das Risiko von Sicherheitsvorfällen zu verringern, empfiehlt das National Institute of Standards and Technology (NIST) verschiedene Sicherheitspraktiken, einschließlich Risikobewertungen, Härtung der Hostsicherheit, sichere Konfiguration von Netzwerken und Verhinderung von Schadsoftware. 

Microsoft 365 Defender kann verschiedene Aspekte der Vorfallsverhütung behandeln: 

- Implementieren eines [Zero Trust-Frameworks](/security/zero-trust/)
- Bestimmen Ihres Sicherheitsstatus durch Zuweisen einer Bewertung mit [der Microsoft-Sicherheitsbewertung](microsoft-secure-score.md)
- Verhindern von Bedrohungen durch Sicherheitsrisikobewertungen im [Bedrohungs- und Sicherheitsrisikomanagement](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Grundlegendes zu den neuesten Sicherheitsbedrohungen, damit Sie sich darauf vorbereiten können

## <a name="step-1-implement-zero-trust"></a>Schritt 1. Implementieren von Zero Trust

[Zero Trust](/security/zero-trust/) ist eine integrierte Sicherheits-Philosophie und End-to-End-Strategie, die den komplexen Charakter jeder modernen Umgebung berücksichtigt, einschließlich der mobilen Mitarbeiter und der Benutzer, Geräte, Anwendungen und Daten, unabhängig davon, wo sie sich befinden. Durch die Bereitstellung eines einzigen Fensterausschnitts zur konsistenten Verwaltung aller Erkennungen kann Microsoft 365 Defender es Ihrem Sicherheitsteam erleichtern, die [Leitprinzipien](/security/zero-trust/#guiding-principles-of-zero-trust) von Zero Trust zu implementieren. 

Komponenten von Microsoft 365 Defender können Verstöße gegen Regeln anzeigen, die implementiert wurden, um Richtlinien für bedingten Zugriff für Zero Trust einzurichten, indem Daten von Microsoft Defender für Endpunkt (MDE) oder anderen mobilen Sicherheitsanbietern als Informationsquelle für Gerätekompatibilitätsrichtlinien und die Implementierung von gerätebasierten Richtlinien für bedingten Zugriff integriert werden. 

Das Geräterisiko beeinflusst direkt, auf welche Ressourcen der Benutzer dieses Geräts zugegriffen werden kann. Die Verweigerung des Zugriffs auf Ressourcen basierend auf bestimmten Kriterien ist das Hauptdesign von Zero Trust, und Microsoft 365 Defender informationen bereitstellt, die erforderlich sind, um die Kriterien auf Vertrauensebene zu bestimmen. Beispielsweise kann Microsoft 365 Defender die Softwareversionsebene eines Geräts über die Seite "Bedrohungs- und Sicherheitsrisikoverwaltung" bereitstellen, während Richtlinien für bedingten Zugriff Geräte mit veralteten oder anfälligen Versionen einschränken.

Automatisierung ist ein wichtiger Bestandteil der Implementierung und Pflege einer Zero Trust-Umgebung, während gleichzeitig die Anzahl der Warnungen reduziert wird, die möglicherweise zu Ereignissen bei der Reaktion auf Vorfälle (Incident Response, IR) führen würden. Komponenten von Microsoft 365 Defender können automatisiert werden, z. B. [Wartungsaktionen](m365d-autoir.md) (bekannt als Untersuchungen für einen Vorfall im Microsoft 365 Security Center), Benachrichtigungsaktionen und sogar die Erstellung von Supporttickets wie in [ServiceNow.](https://microsoft.service-now.com/sp/)

## <a name="step-2-determine-your-organizations-security-posture"></a>Schritt 2. Bestimmen des Sicherheitsstatus Ihrer Organisation

Als Nächstes können Organisationen die [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) in Microsoft 365 Defender verwenden, um Ihren aktuellen Sicherheitsstatus zu bestimmen und Empfehlungen zur Verbesserung zu berücksichtigen. Je höher die Bewertung ist, desto mehr Sicherheitsempfehlungen und Verbesserungsmaßnahmen wurden von der Organisation durchgeführt. Empfehlungen für die Sicherheitsbewertung können über verschiedene Produkte hinweg angewendet werden und ermöglichen Es Organisationen, ihre Bewertungen noch weiter zu erhöhen. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Beispiel für die Microsoft-Sicherheitsbewertung im Microsoft Security Center":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Schritt 3. Bewerten der Sicherheitsrisiken Ihrer Organisation

Die Verhinderung von Vorfällen kann dazu beitragen, die Sicherheitsvorgänge zu optimieren, um sich auf laufende kritische und wichtige Sicherheitsvorfälle zu konzentrieren. Softwarerisiken sind häufig ein verhinderbarer Einstiegspunkt für Angriffe, die zu Datendiebstahl, Datenverlust oder Betriebsunterbrechungen führen können. Wenn keine Angriffe ausgeführt werden, müssen Sicherheitsvorgänge versuchen, ein akzeptables Maß an [Sicherheitsrisiken](../defender-endpoint/tvm-exposure-score.md) in ihrer Organisation zu erreichen und aufrechtzuerhalten.

Um den Fortschritt des Softwarepatchings zu überprüfen, besuchen Sie die Seite ["Bedrohungs- und Sicherheitsrisikoverwaltung"](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) in Defender für Endpunkt, auf die Sie über die Registerkarte **"Weitere Ressourcen"** von Microsoft 365 Defender zugreifen können.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Beispiel für die Seite &quot;Bedrohung und Sicherheitsanfälligkeit&quot; im Microsoft Security Center"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Verstehen neuer Bedrohungen

Verwenden Sie [die Bedrohungsanalyse](threat-analytics.md) im Microsoft 365 Security Center, um mit der aktuellen Sicherheitsbedrohungslandschaft auf dem neuesten Stand zu bleiben. Erfahrene Microsoft-Sicherheitsexperten erstellen Berichte, die die neuesten Cyberbedrohungen detailliert beschreiben, damit Sie verstehen können, wie sie sich auf Ihr Microsoft 365 Abonnement, Geräte und Benutzer auswirken können. Diese Berichte können Folgendes umfassen:

- Aktive Bedrohungsteilnehmer und ihre Kampagnen
- Beliebte und neue Angriffstechniken
- Kritische Sicherheitsrisiken
- Allgemeine Angriffsflächen
- Weit verbreitete Schadsoftware

Die Bedrohungsanalyse untersucht auch Ihre Konfiguration und Warnungen, um zu ermitteln, wie gefährdet Sie sind und ob aktive Warnungen für einen Bericht anwendbar sind.

Sie können die Empfehlungen einer neuen Bedrohung implementieren, um Ihren Sicherheitsstatus zu stärken und den Angriffsbereich zu minimieren.

Nehmen Sie sich Zeit in Ihrem Zeitplan, um den Abschnitt ["Bedrohungsanalyse"](threat-analytics.md) im Microsoft 365 Security Center regelmäßig zu überprüfen.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 1: Erfahren Sie, wie Sie Vorfälle selektieren und analysieren](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Erfahren Sie, wie Sie [Vorfälle selektieren und analysieren.](first-incident-analyze.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
