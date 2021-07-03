---
title: Konfigurieren der Geräteermittlung
description: Erfahren Sie, wie Sie die Geräteermittlung in Microsoft 365 Defender mithilfe der Einfach- oder Standardermittlung konfigurieren.
keywords: einfach, Standard, Endpunktermittlung konfigurieren, Geräteermittlung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ee56ed2949ea72771d8f08570d4352dbe7548d52
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286945"
---
# <a name="configure-device-discovery"></a>Konfigurieren der Geräteermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

Die Ermittlung kann so konfiguriert werden, dass sie sich im Standard- oder Standardmodus befindet. Verwenden Sie die Standardoption, um Geräte in Ihrem Netzwerk aktiv zu finden, wodurch die Ermittlung von Endpunkten besser gewährleistet und eine umfassendere Geräteklassifizierung bereitgestellt wird. 

Sie können die Liste der Geräte anpassen, die für die Standardermittlung verwendet werden. Sie können entweder die Standardermittlung auf allen integrierten Geräten aktivieren, die diese Funktion ebenfalls unterstützen (derzeit – nur Windows 10 Geräte) oder eine Teilmenge oder Teilmengen Ihrer Geräte auswählen, indem Sie deren Gerätetags angeben.

> [!IMPORTANT]
> Für die Vorschau müssen Sie zuerst die Vorschaufeatures in Microsoft Defender Security Center aktivieren.
> Anschließend können Sie auf die Geräteermittlungskonfiguration im Microsoft 365 Security Center zugreifen. Die Liste der nicht verwalteten Geräte und Sicherheitsempfehlungen wird sowohl in Microsoft Defender Security Center als auch in Microsoft 365 Security Center verfügbar sein, während die Dashboardkacheln nur in Microsoft 365 Security Center verfügbar sind.

Führen Sie die folgenden Konfigurationsschritte im Microsoft 365 Security Center aus:

1. Navigieren Sie zu **Einstellungen > Geräteermittlung.**
2. Wählen Sie den Ermittlungsmodus aus, der auf Ihren integrierten Geräten verwendet werden soll.
3. Wenn Sie sich für die Verwendung der Standardermittlung entschieden haben, wählen Sie aus, welche Geräte für die aktive Untersuchung verwendet werden sollen: alle Geräte oder auf einer Teilmenge, indem Sie deren Gerätetags angeben.
4. Klicken Sie auf **Speichern**.

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Ausschließen, dass Geräte bei der Standardermittlung aktiv untersucht werden

Wenn in Ihrem Netzwerk Geräte vorhanden sind, die nicht aktiv gescannt werden sollten (z. B. Geräte, die alsPots für ein anderes Sicherheitstool verwendet werden), können Sie auch eine Liste von Ausschlüssen definieren, um zu verhindern, dass sie gescannt werden. Beachten Sie, dass Geräte weiterhin im Basic-Ermittlungsmodus ermittelt werden können. Diese Geräte werden passiv erkannt, aber nicht aktiv untersucht. 

## <a name="select-networks-to-monitor"></a>Auswählen von Netzwerken, die überwacht werden sollen

 Microsoft Defender für Endpunkt analysiert ein Netzwerk und ermittelt, ob es sich um ein Unternehmensnetzwerk handelt, das überwacht werden muss, oder um ein Nicht-Unternehmensnetzwerk, das ignoriert werden kann. Unternehmensnetzwerke werden in der Regel für die Überwachung ausgewählt. Sie können diese Entscheidung jedoch außer Kraft setzen, indem Sie auswählen, dass Nicht-Unternehmensnetzwerke überwacht werden, in denen integrierte Geräte gefunden werden. 

Sie können konfigurieren, wo die Geräteermittlung durchgeführt werden kann, indem Sie angeben, welche Netzwerke überwacht werden sollen. Wenn ein Netzwerk überwacht wird, kann die Geräteermittlung für es ausgeführt werden. 

Eine Liste der Netzwerke, in denen die Geräteermittlung durchgeführt werden kann, wird auf der Seite **"Überwachte Netzwerke"** angezeigt. 

> [!NOTE]
> Nur die 50 wichtigsten Netzwerke (entsprechend der Anzahl der zugeordneten Geräte) sind in der Netzwerkliste verfügbar. 

Die Liste der überwachten Netzwerke wird basierend auf der Gesamtzahl der Geräte sortiert, die in den letzten 7 Tagen im Netzwerk angezeigt wurden.

Sie können einen Filter anwenden, um einen der folgenden Netzwerkermittlungszustände anzuzeigen:

- **Überwachte Netzwerke** – Netzwerke, in denen die Geräteermittlung durchgeführt wird.
- **Ignorierte Netzwerke–** Dieses Netzwerk wird ignoriert, und die Geräteermittlung wird nicht ausgeführt.
- **Alle** – sowohl überwachte als auch ignorierte Netzwerke werden angezeigt.

### <a name="configure-the-network-monitor-state"></a>Konfigurieren des Netzwerküberwachungsstatus

Sie steuern, wo die Geräteermittlung stattfindet. Überwachte Netzwerke sind der Ort, an dem die Geräteermittlung durchgeführt wird und in der Regel Unternehmensnetzwerke sind. Sie können auch auswählen, ob Netzwerke ignoriert oder die klassifizierung für die erste Ermittlung ausgewählt werden soll, nachdem Sie einen Status geändert haben.

Wenn Sie die anfängliche Ermittlungsklassifizierung auswählen, müssen Sie den standardmäßigen systembasierten Netzwerküberwachungsstatus anwenden. Das Auswählen des standardmäßigen systembasierten Netzwerküberwachungsstatus bedeutet, dass Netzwerke, die als Unternehmensnetzwerke identifiziert wurden, überwacht und als nicht unternehmenseigene Netzwerke identifiziert werden, automatisch ignoriert werden.

1. Wählen Sie **Einstellungen > Geräteermittlung aus.**
2. Wählen Sie **überwachte Netzwerke** aus.
3. Zeigen Sie die Liste der Netzwerke an.
4. Wählen Sie die drei Punkte neben dem Netzwerknamen aus.
5. Wählen Sie aus, ob Sie die anfängliche Ermittlungsklassifizierung überwachen, ignorieren oder verwenden möchten.

    > [!WARNING]
    >
    > - Wenn Sie sich für die Überwachung eines Netzwerks entscheiden, das von Microsoft Defender für Endpunkt nicht als Unternehmensnetzwerk identifiziert wurde, kann dies zu einer Geräteermittlung außerhalb Ihres Unternehmensnetzwerks führen und kann daher private oder andere Nicht-Unternehmensgeräte erkennen.
    > - Wenn Sie ein Netzwerk ignorieren, wird die Überwachung und Ermittlung von Geräten in diesem Netzwerk beendet. Geräte, die bereits ermittelt wurden, werden nicht aus dem Bestand entfernt, aber nicht mehr aktualisiert, und Details werden bis zum Ablauf des Datenaufbewahrungszeitraums von Defender für Endpunkt aufbewahrt.
    > - Bevor Sie sich für die Überwachung von Nicht-Unternehmensnetzwerken entscheiden, müssen Sie sicherstellen, dass Sie dazu berechtigt sind.

6. Vergewissern Sie sich, dass Sie die Änderung vornehmen möchten. 

## <a name="explore-devices-in-the-network"></a>Erkunden von Geräten im Netzwerk

Sie können die folgende erweiterte Suchabfrage verwenden, um mehr Kontext zu jedem in der Netzwerkliste beschriebenen Netzwerknamen zu erhalten. Die Abfrage listet alle integrierten Geräte auf, die innerhalb der letzten 7 Tage mit einem bestimmten Netzwerk verbunden waren.

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a>Weitere Informationen:

- [Übersicht über die Geräteermittlung](device-discovery.md)
- [Häufig gestellte Fragen zur Geräteermittlung](device-discovery-faq.md)
