---
title: Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über die automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender, die auch selbsterklingend genannt werden.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Problembehebung, Selbstbehebung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930330"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Funktionsweise der automatischen Untersuchung und Selbsthilfe

Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsteam, diese Warnungen zu betrachten und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Automatisierte Untersuchungs- und Reaktionsfunktionen mit Selbsterl sung in Microsoft 365 Defender können hilfreich sein.

Sehen Sie sich das folgende Video an, um zu sehen, wie die Selbstrehung funktioniert:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender funktioniert die automatisierte Untersuchung und Reaktion mit Selbsterklingungsfunktionen auf Ihren Geräten, E-Mail& Inhalten und Identitäten.
 
> [!TIP]
> In diesem Artikel wird die Funktionsweise der automatischen Untersuchung und Reaktion beschrieben. Informationen zum Konfigurieren dieser Funktionen finden Sie unter [Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Ihr eigener virtueller Analyst

Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten. Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann. Wenn dieses Szenario nach Science Fiction klingt, ist dies nicht der Fall! Ein solcher virtueller Analyst ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist eine *automatisierte Untersuchung und Reaktion.*

Die automatisierte Untersuchung und Reaktion ermöglicht es Ihrem Sicherheitsteam, die Kapazität Ihrer Organisation für die Verarbeitung von Sicherheitswarnungen und Vorfällen erheblich zu erhöhen. Mit einer automatisierten Untersuchung und Reaktion können Sie die Kosten für den Umgang mit Untersuchungs- und Korrekturaktivitäten reduzieren und Ihre Bedrohungsschutzsuite voll auslasten. Automatisierte Untersuchung und Reaktion hilft Ihrem Sicherheitsteam durch:

1. Ermitteln, ob eine Bedrohung eine Aktion erfordert;
2. Durchführen (oder Empfehlen) aller erforderlichen Wartungsmaßnahmen;
3. Ermitteln, welche weiteren Untersuchungen stattfinden sollten und
4. Wiederholen des Vorgangs für andere Warnungen.

## <a name="the-automated-investigation-process"></a>Der Prozess der automatischen Untersuchung

**Warnung** > **Vorfall** > **automatische Untersuchung** > **Urteil** > **Wartungsaktion**

Eine ausgelöste Warnung erstellt einen Vorfall, der eine automatisierte Untersuchung starten kann. Diese Untersuchung kann zu einer oder mehreren Wartungsaktionen führen. In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale in Microsoft Defender for Identity, Microsoft Defender für Endpoint und Defender für Office 365, wie in der folgenden Tabelle zusammengefasst: 

|Entitäten |Dienste für den Bedrohungsschutz  |
|---------|---------|
|Geräte (auch als Endpunkte bezeichnet)     |[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-Mail-Inhalte (Dateien und Nachrichten in Postfächern)     |[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Jede Untersuchung generiert Für jeden untersuchten Beweis eine Prüfung *(* Bösartig *,* verdächtig oder keine Bedrohungen gefunden). Je nach Art der Bedrohung und der resultierenden Bekündung werden Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. Ausstehende und abgeschlossene Aktionen werden im [Info-Center](mtp-action-center.md) aufgelistet.

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt. 

> [!NOTE]
> Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Abhilfemaßnahmen. Dies alles hängt davon ab, wie die automatisierte Untersuchung und Reaktion für Ihre Organisation konfiguriert ist. Weitere [Informationen finden Sie unter Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Nächste Schritte

- [Sehen Sie sich die Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender an.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurieren der automatisierten Untersuchung und Reaktion für Ihre Organisation](mtp-configure-auto-investigation-response.md)
- [Erfahren Sie mehr über das Info-Center](mtp-action-center.md)
