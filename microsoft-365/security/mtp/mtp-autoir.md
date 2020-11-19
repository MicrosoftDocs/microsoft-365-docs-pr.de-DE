---
title: Automatische Untersuchung und Antwort in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über die automatisierten Ermittlungs-und Antwortfunktionen, die auch als Selbstheilung bezeichnet werden, in Microsoft 365 Defender
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, Selbstheilung
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356703"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatische Untersuchung und Antwort in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Möchten Sie Microsoft 365 Defender erfahren? Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [ihr Pilotprojekt in der Produktion ausführen](https://aka.ms/m365d-pilotplaybook).
>

Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Automatisierte Ermittlungs-und Antwortfunktionen mit Selbstheilung in Microsoft 365 Defender können helfen.

Sehen Sie sich das folgende Video an, um zu erfahren, wie die Selbstheilung funktioniert:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender funktioniert die automatische Untersuchung und Antwort mit Selbstheilungsfunktionen auf Ihren Geräten, e-Mail-& Inhalt und Identitäten. Microsoft 365 Defender vereint Funktionen von: 
- [Automatische Untersuchung und Korrektur in Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Automatische Untersuchung und Antwort in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Erkennung erweiterter Azure-Bedrohungen](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
In diesem Artikel wird beschrieben, wie automatisierte Untersuchungen und Antworten funktionieren. Informationen zum Konfigurieren dieser Funktionen finden Sie unter [Configure Automated Investigation and Response Capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).

## <a name="your-virtual-analyst"></a>Ihr virtueller Analyst

Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten. Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann. Wenn dieses Szenario wie Science Fiction klingt, ist es nicht! Ein solcher virtueller Analyst ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist die *Automatische Untersuchung und Antwort*.

Durch die automatische Untersuchung und Antwort kann Ihr Sicherheits Betriebsteam die Kapazität Ihres Unternehmens zur Bewältigung von Sicherheitswarnungen und Vorfällen drastisch erhöhen. Mit automatisierter Untersuchung und Antwort können Sie die Kosten für den Umgang mit Ermittlungs-und Korrekturmaßnahmen senken und ihre Bedrohungsschutz-Suite optimal nutzen. die automatische Untersuchung und Antwort hilft Ihrem Security Operations-Team mit:

1. Ermitteln, ob eine Bedrohung eine Aktion erfordert;
2. Durchführen (oder Empfehlen) aller erforderlichen Wartungsmaßnahmen;
3. Ermitteln, welche weiteren Untersuchungen stattfinden sollten und
4. Wiederholen des Vorgangs für andere Warnungen.

## <a name="the-automated-investigation-process"></a>Der Prozess der automatischen Untersuchung

**Warnung** > **Vorfall** > **automatische Untersuchung** > **Urteil** > **Wartungsaktion**

Bei einer ausgelösten Warnung wird ein Vorfall erstellt, der eine automatisierte Untersuchung starten kann. Diese Untersuchung kann zu einer oder mehreren Wartungsaktionen führen. In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale in Microsoft Defender for Identity, Microsoft Defender for Endpoint und Defender für Office 365, wie in der folgenden Tabelle zusammengefasst: 

|Entitäten |Dienste für den Bedrohungsschutz  |
|---------|---------|
|Geräte (auch als Endpunkte bezeichnet)     |[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-Mail-Inhalte (Dateien und Nachrichten in Postfächern)     |[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Bei jeder Untersuchung werden Urteile (*böswillige*, *verdächtige* oder *nicht gefundene Bedrohungen*) für jedes untersuchte Beweisstück generiert. Je nach Art der Bedrohung und dem daraus resultierenden Urteil werden Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation durchgeführt. Ausstehende und abgeschlossene Aktionen werden im [Info-Center](mtp-action-center.md) aufgelistet.

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt. 

> [!NOTE]
> Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Korrekturaktionen. Dies hängt davon ab, wie die automatische Untersuchung und Antwort für Ihre Organisation konfiguriert ist. Weitere Informationen finden Sie unter [Configure Automated Investigation and Response Capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen finden Sie unter Voraussetzungen für automatisierte Untersuchungen und Antworten in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurieren der automatischen Untersuchung und Reaktion für Ihre Organisation](mtp-configure-auto-investigation-response.md)
- [Erfahren Sie mehr über das Info-Center](mtp-action-center.md)
