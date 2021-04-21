---
title: Untersuchen von Vorfällen in Microsoft Defender for Endpoint
description: Siehe zugeordnete Warnungen, Verwalten des Vorfalls und Anzeigen von Warnungsmetadaten zur Untersuchung eines Vorfalls
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
ms.openlocfilehash: 1d8f4452273047684a30db3b18d1281f40f46378
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903298"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Untersuchen von Vorfällen in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Untersuchen Sie Vorfälle, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten, und ermitteln Sie Nachweise, um sie zu beheben. 

Wenn Sie einen Vorfall untersuchen, sehen Sie:
- Vorfalldetails
- Vorfallkommentare und -aktionen
- Registerkarten (Warnungen, Geräte, Untersuchungen, Nachweise, Graph)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a>Analysieren von Vorfalldetails 
Klicken Sie auf einen Vorfall, um den Bereich **Vorfall anzuzeigen.** Wählen **Sie Seite Vorfall öffnen aus,** um die Vorfalldetails und zugehörige Informationen (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm) anzuzeigen. 

![Abbildung der Vorfalldetails1](images/atp-incident-details.png)

### <a name="alerts"></a>Warnungen
Sie können die Warnungen untersuchen und sehen, wie sie in einem Vorfall miteinander verknüpft wurden. Warnungen werden basierend auf den folgenden Gründen in Vorfälle eingeteilt:
- Automatisierte Untersuchung – Die automatisierte Untersuchung löste die verknüpfte Warnung während der Untersuchung der ursprünglichen Warnung aus. 
- Dateimerkmale : Die dateien, die der Warnung zugeordnet sind, haben ähnliche Merkmale.
- Manuelle Zuordnung : Ein Benutzer hat die Warnungen manuell verknüpft.
- Proximatzeit – Die Warnungen wurden auf dem gleichen Gerät innerhalb eines bestimmten Zeitrahmens ausgelöst.
- Gleiche Datei : Die Dateien, die der Warnung zugeordnet sind, sind identisch.
- Gleiche URL – Die URL, die die Warnung ausgelöst hat, ist identisch.

![Abbildung der Registerkarte "Warnungen" mit der Seite "Vorfalldetails" mit den Gründen, aus denen die Warnungen in diesem Vorfall verknüpft wurden](images/atp-incidents-alerts-reason.png)

Sie können auch eine Warnung verwalten und Benachrichtigungsmetadaten zusammen mit anderen Informationen anzeigen. Weitere Informationen finden Sie unter [Untersuchen von Warnungen](investigate-alerts.md). 

### <a name="devices"></a>Geräte
Sie können auch die Geräte untersuchen, die Teil oder im Zusammenhang mit einem bestimmten Vorfall sind. Weitere Informationen finden Sie unter [Untersuchen von Geräten](investigate-machines.md).

![Abbildung der Registerkarte "Geräte" auf der Seite "Details zu Vorfällen"](images/atp-incident-device-tab.png)

### <a name="investigations"></a>Untersuchungen
Wählen **Sie Untersuchungen** aus, um alle automatischen Untersuchungen anzuzeigen, die vom System als Reaktion auf die Vorfallwarnungen gestartet wurden.

![Abbildung der Registerkarte "Untersuchungen" auf der Seite "Details zu Vorfällen"](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>Durch die Nachweise
Microsoft Defender for Endpoint untersucht automatisch alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Autoresponse und Informationen zu wichtigen Dateien, Prozessen, Diensten und mehr zur Verfügung. 

Jede der analysierten Entitäten wird als infiziert, behoben oder verdächtig gekennzeichnet. 

![Abbildung der Registerkarte "Nachweise" auf der Seite "Details zu Vorfällen"](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>Visualisieren zugeordneter Cybersicherheitsbedrohungen 
Microsoft Defender for Endpoint aggregiert die Bedrohungsinformationen in einem Vorfall, sodass Sie die Muster und Korrelationen aus verschiedenen Datenpunkten sehen können. Sie können diese Korrelation über das Vorfalldiagramm anzeigen.

### <a name="incident-graph"></a>Vorfalldiagramm
The **Graph** tells the story of the cybersecurity attack. Beispielsweise wird gezeigt, was der Einstiegspunkt war, welcher Indikator für Einemeindung oder Aktivität auf welchem Gerät beobachtet wurde. usw.

![Abbildung des Vorfalldiagramms](images/atp-incident-graph-tab.png)

Sie können auf die Kreise im Vorfalldiagramm klicken, um die Details der schädlichen Dateien, die zugehörigen Dateierkennungen, die Anzahl der Instanzen weltweit anzuzeigen, ob sie in Ihrer Organisation beobachtet wurden, wenn ja, wie viele Instanzen.

![Abbildung von Vorfalldetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>Verwandte Themen
- [Vorfallswarteschlange](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Untersuchen von Vorfällen in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Verwalten von Microsoft Defender for Endpoint-Vorfällen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
