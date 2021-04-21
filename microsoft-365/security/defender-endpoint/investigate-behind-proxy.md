---
title: Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys
description: Erfahren Sie, wie Sie die erweiterte ÜBERWACHUNG auf HTTP-Ebene mithilfe von Netzwerkschutz in Microsoft Defender for Endpoint verwenden, der anstelle eines Proxys ein echtes Ziel zeigt.
keywords: Proxy, Netzwerkschutz, Weiterleitungsproxy, Netzwerkereignisse, Überwachung, Block, Domänennamen, Domäne
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47be07759a72a080a3687ed3bb50cef9d0a959b7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904046"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender for Endpoint unterstützt die Netzwerkverbindungsüberwachung von verschiedenen Ebenen des Netzwerkstapels. Ein anspruchsvoller Fall ist, wenn das Netzwerk einen Weiterleitungsproxy als Gateway zum Internet verwendet.

Der Proxy verhält sich so, als wäre er der Zielendpunkt.  In diesen Fällen überwachen einfache Netzwerkverbindungsmonitore die Verbindungen mit dem Proxy, der korrekt ist, aber einen niedrigeren Untersuchungswert hat. 

Defender for Endpoint unterstützt die erweiterte Überwachung auf HTTP-Ebene durch Netzwerkschutz. Wenn dies aktiviert ist, wird ein neuer Ereignistyp angezeigt, der die tatsächlichen Zieldomänennamen verfügbar macht.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Verwenden von Netzwerkschutz zum Überwachen der Netzwerkverbindung hinter einer Firewall
Die Überwachung der Netzwerkverbindung hinter einem Weiterleitungsproxy ist aufgrund zusätzlicher Netzwerkereignisse möglich, die aus dem Netzwerkschutz stammen. Um sie auf einer Gerätezeitachse anzuzeigen, aktivieren Sie den Netzwerkschutz (mindestens im Überwachungsmodus). 

Der Netzwerkschutz kann mithilfe der folgenden Modi gesteuert werden:

- **Blockieren** <br> Benutzer oder Apps werden an der Verbindung mit gefährlichen Domänen blockiert. Sie können diese Aktivität im Microsoft Defender Security Center sehen.
- **Audit** <br> Benutzer oder Apps werden nicht an der Verbindung mit gefährlichen Domänen blockiert. Diese Aktivität wird jedoch weiterhin im Microsoft Defender Security Center zu sehen sein.


Wenn Sie den Netzwerkschutz deaktivieren, werden Benutzer oder Apps nicht an der Verbindung mit gefährlichen Domänen blockiert. Es werden keine Netzwerkaktivitäten im Microsoft Defender Security Center zu sehen sein.

Wenn Sie dies nicht konfigurieren, wird die Netzwerksperrung standardmäßig deaktiviert.

Weitere Informationen finden Sie unter [Aktivieren des Netzwerkschutzes](enable-network-protection.md).

## <a name="investigation-impact"></a>Untersuchungswirkung
Wenn der Netzwerkschutz aktiviert ist, wird auf der Zeitachse eines Geräts angezeigt, dass die IP-Adresse den Proxy weiterhin darstellt, während die tatsächliche Zieladresse angezeigt wird.

![Abbildung von Netzwerkereignissen auf der Zeitachse des Geräts](images/atp-proxy-investigation.png)

Zusätzliche Ereignisse, die von der Netzwerkschutzebene ausgelöst werden, stehen nun zur Verfügung, um die tatsächlichen Domänennamen auch hinter einem Proxy zu verwenden.

Informationen des Ereignisses:

![Abbildung eines einzelnen Netzwerkereigniss](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Suche nach Verbindungsereignissen mithilfe der erweiterten Suche 
Alle neuen Verbindungsereignisse stehen Ihnen auch für die erweiterte Suche zur Verfügung. Da es sich bei diesen Ereignissen um Verbindungsereignisse handelt, finden Sie sie unter der Tabelle DeviceNetworkEvents unter dem `ConnecionSuccess` Aktionstyp.

Bei Verwendung dieser einfachen Abfrage werden alle relevanten Ereignisse angezeigt:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Abbildung der erweiterten Suchabfrage](images/atp-proxy-investigation-ah.png)

Sie können auch Ereignisse herausfiltern, die mit der Verbindung mit dem Proxy selbst verbunden sind. 

Verwenden Sie die folgende Abfrage, um die Verbindungen mit dem Proxy herausfiltern:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Verwandte Themen
- [Anwenden von Netzwerkschutz mit GP – Richtlinien-CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
