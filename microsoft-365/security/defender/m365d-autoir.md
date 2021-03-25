---
title: Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender
description: Verschaffen Sie sich in Microsoft 365 Defender einen Überblick über automatisierte Untersuchungs- und Reaktionsfunktionen, auch Selbstheilung genannt.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, Selbstheilung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 8ed6f1ccd6587d6c618974a123f0d5d42a44e753
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199633"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Wenn Ihre Organisation [Microsoft 365 Defender](microsoft-365-defender.md)verwendet, erhält Ihr Sicherheitsteam eine Warnung, wenn ein bösartiges oder verdächtiges Artefakt erkannt wird. Angesichts des scheinbar nie endenden Bedrohungsflusses stehen Sicherheitsteams häufig vor Herausforderungen bei der Behandlung des hohen Benachrichtigungsvolumens. Glücklicherweise umfasst Microsoft 365 Defender funktionen für die automatisierte Untersuchung und Behebung (AIR), die Ihrem Sicherheitsteam bei der effizienteren und effektiveren Lösung von Bedrohungen helfen können.

Dieser Artikel bietet eine Übersicht über AIR und enthält Links zu den nächsten Schritten und zusätzlichen Ressourcen.

> [!TIP]
> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Funktionsweise der automatisierten Untersuchung und Selbstheilung

Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsbetriebsteam, diese Warnungen zu betrachten und Schritte zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Automatisierte Untersuchungs- und Reaktionsfunktionen mit Selbstheilung in Microsoft 365 Defender können helfen.

Sehen Sie sich das folgende Video an, um zu sehen, wie die Selbstheilung funktioniert: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender funktioniert die automatisierte Untersuchung und Reaktion mit Selbstheilungsfunktionen auf Allen Geräten, E-Mail-& und Identitäten.
 
> [!TIP]
> In diesem Artikel wird beschrieben, wie automatisierte Untersuchungen und Reaktionen funktionieren. Informationen zum Konfigurieren dieser Funktionen finden Sie [unter Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Ihr eigener virtueller Analyst

Stellen Sie sich vor, sie haben einen virtuellen Analysten in Ihrem Sicherheitsteam der Stufe 1 oder Ebene 2. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten. Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann. Wenn dieses Szenario nach Science Fiction klingt, ist dies nicht der Fall! Ein solcher virtueller Analytiker ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist *automatisierte Untersuchung und Antwort.*

Automatisierte Untersuchungs- und Reaktionsfunktionen ermöglichen Es Ihrem Sicherheitsteam, die Kapazität Ihrer Organisation zur Verarbeitung von Sicherheitswarnungen und Vorfällen erheblich zu erhöhen. Mit der automatisierten Untersuchung und Reaktion können Sie die Kosten für die Behandlung von Untersuchungs- und Behebungsaktivitäten reduzieren und das Beste aus Ihrer Bedrohungsschutzsuite nutzen. Automatisierte Untersuchungs- und Reaktionsfunktionen unterstützen Ihr Sicherheitsteam durch:

1. Ermitteln, ob eine Bedrohung eine Aktion erfordert;
2. Durchführen (oder Empfehlen) der erforderlichen Korrekturaktionen;
3. Bestimmen, ob und welche weiteren Untersuchungen stattfinden sollten; und
4. Wiederholen des Vorgangs für andere Warnungen.

## <a name="the-automated-investigation-process"></a>Der Prozess der automatischen Untersuchung

Eine Warnung erstellt einen Vorfall, der eine automatisierte Untersuchung starten kann. Die automatisierte Untersuchung führt zu einem Urteil für jedes Beweisstück. Die Urteile können lauten:
- *Bösartig*;
- *Verdächtig*; oder 
- *Keine Bedrohungen gefunden.* 

Behebungsaktionen für bösartige oder verdächtige Entitäten werden identifiziert. Beispiele für Korrekturaktionen sind:
- Senden einer Datei in Quarantäne;
- Beenden eines Prozesses;
- Isolieren eines Geräts;
- Blockieren einer URL; und 
- andere Aktionen. (Siehe [Korrekturaktionen in Microsoft 365 Defender](m365d-remediation-actions.md).)

Je [nachdem, wie automatisierte Untersuchungs-](m365d-configure-auto-investigation-response.md) und Reaktionsfunktionen für Ihre Organisation konfiguriert sind, werden Korrekturaktionen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt. Alle Aktionen, ob ausstehend oder abgeschlossen, werden im [Aktionscenter aufgelistet.](m365d-action-center.md)

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine inkriminierte Entität an anderer Stelle gesehen wird, erweitert die automatisierte Untersuchung ihren Bereich, um diese Entität zu umfassen, und der Untersuchungsprozess wiederholt sich. 

In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale in Microsoft Defender for Identity, Microsoft Defender for Endpoint und Defender für Office 365, wie in der folgenden Tabelle zusammengefasst: 

|Entitäten |Dienste für den Bedrohungsschutz  |
|:---------|:---------|
|Geräte (auch als Endpunkte bezeichnet und manchmal auch als Computer bezeichnet)     |[Microsoft Defender für Endpunkt](../defender-endpoint/automated-investigations.md)<br/>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|E-Mail-Inhalt (E-Mail-Nachrichten, die Dateien und URLs enthalten können)     |[Microsoft Defender für Office 365](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Abhilfemaßnahmen. es hängt davon ab, wie die automatisierte Untersuchung und Reaktion für Ihre Organisation konfiguriert ist. Weitere Informationen finden Sie unter [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="next-steps"></a>Nächste Schritte

- [Informationen zu den Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurieren der automatisierten Untersuchung und Reaktion für Ihre Organisation](m365d-configure-auto-investigation-response.md)
- [Erfahren Sie mehr über das Info-Center](m365d-action-center.md)
