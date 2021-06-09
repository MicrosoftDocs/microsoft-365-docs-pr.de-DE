---
title: Untersuchen von Vorfällen in Microsoft Defender für Endpunkt
description: Anzeigen zugehöriger Warnungen, Verwalten des Vorfalls und Anzeigen von Warnungsmetadaten, die Ihnen bei der Untersuchung eines Vorfalls helfen
keywords: untersuchen, Vorfall, Warnungen, Metadaten, Risiko, Erkennungsquelle, betroffene Geräte, Muster, Korrelation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845078"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Untersuchen von Vorfällen in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Untersuchen Sie Vorfälle, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten, und sammeln Sie Nachweise, um sie zu beheben. 

Wenn Sie einen Vorfall untersuchen, sehen Sie Folgendes:
- Vorfalldetails
- Vorfallkommentare und -aktionen
- Registerkarten (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a>Analysieren von Vorfalldetails 
Klicken Sie auf einen Vorfall, um den **Vorfallbereich anzuzeigen.** Wählen Sie **die Seite "Vorfall öffnen"** aus, um die Vorfalldetails und zugehörige Informationen (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm) anzuzeigen. 

![Abbildung der Vorfalldetails1](images/atp-incident-details.png)

### <a name="alerts"></a>Warnungen
Sie können die Warnungen untersuchen und sehen, wie sie in einem Vorfall miteinander verknüpft wurden. Warnungen werden basierend auf den folgenden Gründen zu Vorfällen gruppiert:
- Automatisierte Untersuchung – Die automatisierte Untersuchung hat die verknüpfte Warnung ausgelöst, während die ursprüngliche Warnung untersucht wurde. 
- Dateimerkmale – Die der Warnung zugeordneten Dateien weisen ähnliche Merkmale auf.
- Manuelle Zuordnung – Ein Benutzer hat die Warnungen manuell verknüpft
- Proximate Zeit : Die Warnungen wurden innerhalb eines bestimmten Zeitrahmens auf demselben Gerät ausgelöst.
- Gleiche Datei : Die mit der Warnung verbundenen Dateien sind identisch
- Gleiche URL : Die URL, die die Warnung ausgelöst hat, ist identisch.

![Abbildung der Registerkarte "Warnungen" mit der Seite "Vorfalldetails" mit den Gründen, warum die Warnungen in diesem Vorfall miteinander verknüpft wurden](images/atp-incidents-alerts-reason.png)

Sie können auch eine Warnung verwalten und Warnungsmetadaten zusammen mit anderen Informationen anzeigen. Weitere Informationen finden Sie unter [Untersuchen von Warnungen.](investigate-alerts.md) 

### <a name="devices"></a>Geräte
Sie können auch die Geräte untersuchen, die Teil eines bestimmten Vorfalls sind oder mit einem bestimmten Vorfall in Zusammenhang stehen. Weitere Informationen finden Sie unter [Untersuchen von Geräten.](investigate-machines.md)

![Abbildung der Registerkarte "Geräte" auf der Seite "Vorfalldetails"](images/atp-incident-device-tab.png)

### <a name="investigations"></a>Untersuchungen
Wählen Sie **"Untersuchungen" aus,** um alle automatischen Untersuchungen anzuzeigen, die vom System als Reaktion auf die Vorfallwarnungen gestartet wurden.

![Abbildung der Registerkarte "Untersuchungen" auf der Seite "Vorfalldetails"](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>Durchgehen des Nachweises
Microsoft Defender für Endpunkt untersucht automatisch alle von den Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Autoresponse und Informationen zu den wichtigen Dateien, Prozessen, Diensten und mehr bereit. 

Jede der analysierten Entitäten wird als infiziert, behoben oder verdächtig gekennzeichnet. 

![Abbildung der Registerkarte "Nachweise" auf der Seite "Vorfalldetails"](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>Visualisieren zugehöriger Cybersicherheitsbedrohungen 
Microsoft Defender für Endpunkt aggregiert die Bedrohungsinformationen in einem Vorfall, damit Sie die Muster und Korrelationen sehen können, die von verschiedenen Datenpunkten ausgehen. Sie können diese Korrelation über das Vorfalldiagramm anzeigen.

### <a name="incident-graph"></a>Vorfalldiagramm
Der **Graph** beschreibt den Cybersicherheitsangriff. Beispielsweise wird gezeigt, was der Einstiegspunkt war, welcher Indikator für Kompromittierung oder Aktivität auf welchem Gerät beobachtet wurde. Etc.

![Abbildung des Vorfalldiagramms](images/atp-incident-graph-tab.png)

Sie können auf die Kreise im Vorfalldiagramm klicken, um die Details der schädlichen Dateien, die zugehörigen Dateierkennungen, die Anzahl der Instanzen weltweit anzuzeigen, ob sie in Ihrer Organisation beobachtet wurde, falls ja, wie viele Instanzen es gab.

![Abbildung der Vorfalldetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>Verwandte Themen
- [Vorfallswarteschlange](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Untersuchen von Vorfällen in Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Verwalten von Microsoft Defender für Endpunkt-Vorfällen](/microsoft-365/security/defender-endpoint/manage-incidents)
