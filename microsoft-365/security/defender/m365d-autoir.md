---
title: Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender
description: Verschaffen Sie sich einen Überblick über automatisierte Untersuchungs- und Reaktionsfunktionen, auch selbstheilend genannt, in Microsoft 365 Defender
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, Selbstheilung
search.appverid: met150
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
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274568"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Wenn Ihre Organisation [Microsoft 365 Defender](microsoft-365-defender.md)verwendet, empfängt Ihr Sicherheitsteam eine Warnung im Microsoft 365 Security Center, wenn eine bösartige oder verdächtige Aktivität oder ein Artefakt erkannt wird. Angesichts des scheinbar nie endenden Bedrohungsflusses, der einfingen kann, stehen Sicherheitsteams häufig vor der Herausforderung, das hohe Benachrichtigungsvolumen zu bewältigen. Glücklicherweise umfasst Microsoft 365 Defender funktionen für die automatisierte Untersuchung und Reaktion (AIR), mit denen Ihr Sicherheitsbetriebsteam Bedrohungen effizienter und effektiver adressieren kann.

Dieser Artikel bietet eine Übersicht über AIR und enthält Links zu den nächsten Schritten und zusätzlichen Ressourcen.

> [!TIP]
> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Funktionsweise der automatisierten Untersuchung und Selbstheilung

Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsbetriebsteam, diese Warnungen zu betrachten und Schritte zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Automatisierte Untersuchungs- und Reaktionsfunktionen mit Selbstheilung in Microsoft 365 Defender kann helfen.

Sehen Sie sich das folgende Video an, um zu sehen, wie die Selbstheilung funktioniert: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender funktioniert die automatisierte Untersuchung und Reaktion mit Selbstheilungsfunktionen auf Allen Geräten, E-Mail-& und Identitäten.
 
> [!TIP]
> In diesem Artikel wird beschrieben, wie automatisierte Untersuchungen und Reaktionen funktionieren. Informationen zum Konfigurieren dieser Funktionen finden Sie unter [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Ihr eigener virtueller Analyst

Imagine einen virtuellen Analysten in Ihrem Sicherheitsteam der Stufe 1 oder Ebene 2 haben. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Analyst könnte 24 x 7 mit unbegrenzter Kapazität arbeiten und eine erhebliche Anzahl von Untersuchungen und Bedrohungsbehebungen übernehmen. Ein solcher virtueller Analytiker könnte die Reaktionszeit erheblich reduzieren und Ihr Sicherheitsteam für andere wichtige Bedrohungen oder strategische Projekte frei geben. Wenn dieses Szenario nach Science Fiction klingt, ist dies nicht der Fall! Ein solcher virtueller Analyst ist Teil Ihrer Microsoft 365 Defender Suite, und der Name ist *automatisierte Untersuchung und Antwort.*

Automatisierte Untersuchungs- und Reaktionsfunktionen ermöglichen Es Ihrem Sicherheitsteam, die Kapazität Ihrer Organisation zur Verarbeitung von Sicherheitswarnungen und Vorfällen erheblich zu erhöhen. Mit automatisierter Untersuchung und Reaktion können Sie die Kosten für den Umgang mit Untersuchungs- und Reaktionsaktivitäten reduzieren und das Beste aus Ihrer Bedrohungsschutzsuite nutzen. Automatisierte Untersuchungs- und Reaktionsfunktionen unterstützen Ihr Sicherheitsteam durch:

1. Bestimmen, ob eine Bedrohung Eine Aktion erfordert.
2. Durchführen (oder Empfehlen) der erforderlichen Korrekturaktionen.
3. Bestimmen, ob und welche weiteren Untersuchungen stattfinden sollen.
4. Wiederholen des Vorgangs für andere Warnungen.

## <a name="the-automated-investigation-process"></a>Der Prozess der automatischen Untersuchung

Eine Warnung erstellt einen Vorfall, der eine automatisierte Untersuchung starten kann. Die automatisierte Untersuchung führt zu einem Urteil für jedes Beweisstück. Die Urteile können lauten:
- *Bösartig*
- *Verdächtig* 
- *Keine Bedrohungen gefunden* 

Behebungsaktionen für bösartige oder verdächtige Entitäten werden identifiziert. Beispiele für Korrekturaktionen sind:

- Senden einer Datei in Quarantäne
- Beenden eines Prozesses
- Isolieren eines Geräts
- Blockieren einer URL 
- Andere Aktionen

Weitere Informationen finden Sie unter [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).

Je [nachdem, wie automatisierte Untersuchungs-](m365d-configure-auto-investigation-response.md) und Reaktionsfunktionen für Ihre Organisation konfiguriert sind, werden Korrekturaktionen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt. Alle Aktionen, ob ausstehend oder abgeschlossen, werden im [Aktionscenter aufgelistet.](m365d-action-center.md)

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine betroffene Entität an anderer Stelle gesehen wird, erweitert die automatisierte Untersuchung ihren Umfang, um diese Entität zu umfassen, und der Untersuchungsprozess wiederholt sich. 

In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale über Microsoft Defender for Identity, Microsoft Defender for Endpoint und Microsoft Defender für Office 365, wie in der folgenden Tabelle zusammengefasst: 

|Entitäten |Dienste für den Bedrohungsschutz  |
|:---------|:---------|
|Geräte (auch als Endpunkte oder Computer bezeichnet) |[Defender für Endpunkt](../defender-endpoint/automated-investigations.md) |      
|Lokale Active Directory-Benutzer, Entitätsverhalten und Aktivitäten     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|E-Mail-Inhalt (E-Mail-Nachrichten, die Dateien und URLs enthalten können)     |[Defender for Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Korrekturaktionen. Es hängt davon ab, wie die automatisierte Untersuchung und Reaktion für Ihre Organisation konfiguriert ist. Weitere [Informationen finden Sie unter Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).

## <a name="viewing-a-list-of-investigations"></a>Anzeigen einer Liste von Untersuchungen

Wenn Sie Untersuchungen anzeigen möchten, wechseln Sie zur **Seite Vorfälle.** Wählen Sie einen Vorfall aus, und wählen Sie dann die Registerkarte **Untersuchungen** aus. Weitere Informationen finden Sie unter [Details und Ergebnisse einer automatisierten Untersuchung.](m365d-autoir-results.md)


## <a name="next-steps"></a>Nächste Schritte

- [Sehen Sie sich die Voraussetzungen für eine automatisierte Untersuchung und Reaktion an.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurieren der automatisierten Untersuchung und Reaktion für Ihre Organisation](m365d-configure-auto-investigation-response.md)
- [Erfahren Sie mehr über das Info-Center](m365d-action-center.md)
