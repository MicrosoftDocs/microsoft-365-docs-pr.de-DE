---
title: Konfigurieren der Geräteermittlung
description: Informationen zum Konfigurieren der Geräteerkennung in Microsoft 365 Defender mithilfe der einfachen oder standardermittlung
keywords: Basic, Standard, Configure Endpoint Discovery, Device Discovery
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
ms.openlocfilehash: 0d722b4f4bef5b4d178edc5f2142c887690d4c63
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765251"
---
# <a name="configure-device-discovery"></a>Konfigurieren der Geräteermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

Die Ermittlung kann so konfiguriert werden, dass sie sich im Standard- oder Basismodus befindet. Verwenden Sie die Standardoption, um Aktiv nach Geräten in Ihrem Netzwerk zu suchen, wodurch die Ermittlung von Endpunkten besser gewährleistet und eine bessere Geräteklassifizierung ermöglicht wird. 

Sie können die Liste der Geräte anpassen, die zum Ausführen der Standarderkennung verwendet werden. Sie können entweder die Standarderkennung auf allen integrierten Geräten aktivieren, die diese Funktion auch unterstützen (derzeit nur Windows 10 Geräte), oder Sie können eine Teilmenge oder Teilmenge Ihrer Geräte auswählen, indem Sie ihre Gerätetags angeben. 


> [!IMPORTANT]
> Für die Vorschau müssen Sie zunächst die Vorschaufeatures in Microsoft Defender Security Center.
> Anschließend können Sie auf die Geräteermittlungskonfiguration im Microsoft 365 zugreifen. Die Liste der nicht verwalteten Geräte und Sicherheitsempfehlungen ist sowohl im Microsoft Defender Security Center als auch im Microsoft 365 Security Center verfügbar, während die Dashboardkacheln nur in Microsoft 365 Security Center verfügbar sind.


Gehen Sie in Microsoft 365 Security Center wie folgt vor:

1.  Navigieren Sie zu **Einstellungen > Geräteermittlung**.
2.  Wählen Sie den Suchmodus aus, der auf Ihren integrierten Geräten verwendet werden soll. 
3.  Wenn Sie die Standarderkennung verwenden möchten, wählen Sie aus, welche Geräte für die aktive Suche verwendet werden: alle Geräte oder eine Teilmenge, indem Sie ihre Gerätetags angeben.
4. Klicken Sie auf **Speichern**.


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Ausschließen, dass Geräte bei der Standarderkennung aktiv untersucht werden
Wenn ihr Netzwerk Geräte enthält, die nicht aktiv gescannt werden sollten (z. B. Geräte, die als Vorrichtungen für ein anderes Sicherheitstool verwendet werden), können Sie auch eine Liste von Ausschlüssen definieren, um zu verhindern, dass sie gescannt werden. Beachten Sie, dass Geräte weiterhin im Basisermittlungsmodus ermittelt werden können. Diese Geräte werden passiv erkannt, aber nicht aktiv untersucht. 

## <a name="select-networks-to-monitor"></a>Auswählen von Netzwerken, die überwacht werden sollen
 Microsoft Defender for Endpoint analysiert ein Netzwerk und ermittelt, ob es sich um ein Unternehmensnetzwerk handelt, das überwacht werden muss, oder um ein Nicht-Unternehmensnetzwerk, das ignoriert werden kann. Unternehmensnetzwerke werden in der Regel als überwacht ausgewählt. Sie können diese Entscheidung jedoch außer Kraft setzen, indem Sie sich für die Überwachung von Nicht-Unternehmensnetzwerken entscheiden, in denen integrierte Geräte gefunden werden. 

Sie können konfigurieren, wo die Geräteermittlung durchgeführt werden kann, indem Sie angeben, welche Netzwerke überwacht werden sollen. Wenn ein Netzwerk überwacht wird, kann die Geräteermittlung ausgeführt werden. 

Eine Liste der Netzwerke, in denen die Geräteerkennung durchgeführt werden kann, wird auf der Seite **Überwachte Netzwerke** angezeigt. 


>[!NOTE]
> Nur die 50 besten Netzwerke (je nach Anzahl der zugeordneten Geräte) stehen in der Netzwerkliste zur Verfügung. 


Die Liste der überwachten Netzwerke wird basierend auf der Gesamtzahl der Geräte sortiert, die in den letzten 7 Tagen im Netzwerk angezeigt wurden.


Sie können einen Filter anwenden, um einen der folgenden Netzwerkerkennungszustände anzeigen zu können:

- **Überwachte Netzwerke** – Netzwerke, in denen die Geräteerkennung durchgeführt wird.
- **Ignorierte Netzwerke:** Dieses Netzwerk wird ignoriert, und die Geräteermittlung wird nicht ausgeführt.
- **Alle** : Sowohl überwachte als auch ignorierte Netzwerke werden angezeigt. 


### <a name="configure-the-network-monitor-state"></a>Konfigurieren des Netzwerküberwachungsstatus
Sie steuern, wo die Geräteermittlung stattfindet. In überwachten Netzwerken wird die Geräteerkennung durchgeführt, und es handelt sich in der Regel um Unternehmensnetzwerke. Sie können auch netzwerke ignorieren oder nach dem Ändern eines Zustands die anfängliche Erkennungsklassifizierung auswählen. 

Wenn Sie die anfängliche Erkennungsklassifizierung auswählen, wird der standardmäßige Systemmonitorstatus angewendet. Wenn Sie den standardmäßigen Systemmonitorstatus auswählen, werden Netzwerke, die als Unternehmensnetzwerke identifiziert wurden, überwacht und als nicht unternehmensverbunden identifizierte Netzwerke automatisch ignoriert.
 
1. Wählen **Einstellungen > Geräteermittlung aus.**
2. Wählen **Sie Überwachte Netzwerke aus.** 
3. Zeigen Sie die Liste der Netzwerke an. 
4. Wählen Sie die drei Punkte neben dem Netzwerknamen aus. 
5. Wählen Sie aus, ob Sie die anfängliche Ermittlungsklassifizierung überwachen, ignorieren oder verwenden möchten. 
    
    > [!WARNING]
    >- Wenn Sie ein Netzwerk überwachen möchten, das von Microsoft Defender for Endpoint nicht als Unternehmensnetzwerk identifiziert wurde, kann dies zu einer Geräteerkennung außerhalb Ihres Unternehmensnetzwerks führen und daher heim- oder andere nicht unternehmensfreie Geräte erkennen. 
    > - Wenn Sie ein Netzwerk ignorieren, werden die Überwachung und das Ermitteln von Geräten in diesem Netzwerk beendet. Geräte, die bereits erkannt wurden, werden nicht aus dem Bestand entfernt, aber nicht mehr aktualisiert, und Die Details werden aufbewahrt, bis der Aufbewahrungszeitraum von Defender for Endpoint abläuft.
    > - Bevor Sie sich für die Überwachung von Nicht-Unternehmensnetzwerken entscheiden, müssen Sie sicherstellen, dass Sie dazu berechtigt sind. <br>


6. Bestätigen Sie, dass Sie die Änderung ändern möchten. 




## <a name="see-also"></a>Siehe auch
- [Übersicht über die Geräteermittlung](device-discovery.md)
- [Häufig gestellte Fragen zur Geräteerkennung](device-discovery-faq.md)