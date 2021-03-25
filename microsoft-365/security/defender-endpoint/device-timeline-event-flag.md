---
title: Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen
description: Verwenden von Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen zum
keywords: Defender for Endpoint-Gerätezeitachse, Ereigniskennzeichen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165153"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Ereigniskennzeichen in der Zeitachse des Defender for Endpoint-Geräts helfen Ihnen beim Filtern und Organisieren bestimmter Ereignisse, wenn Sie potenzielle Angriffe untersuchen.

Die Zeitachse des Defender for Endpoint-Geräts bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die auf einem Gerät beobachtet werden. Diese Liste der Ereignisse bietet vollständige Sichtbarkeit aller Ereignisse, Dateien und IP-Adressen, die auf dem Gerät beobachtet werden. Die Liste kann manchmal langwierig sein. Gerätezeitachsenereigniskennzeichen helfen Ihnen beim Nachverfolgen von Ereignissen, die miteinander in Zusammenhang stehen könnten. 

Nachdem Sie eine Gerätezeitachse durchgegangen sind, können Sie die bestimmten Ereignisse, die Sie gekennzeichnet haben, sortieren, filtern und exportieren.

Während der Navigation auf der Gerätezeitachse können Sie nach bestimmten Ereignissen suchen und filtern. Sie können Ereigniskennzeichen festlegen, indem Sie: 

- Hervorheben der wichtigsten Ereignisse 
- Markieren von Ereignissen, die einen tiefen Eintauchen erfordern 
- Erstellen einer zeitplansreinen Verletzung



## <a name="flag-an-event"></a>Kennzeichnen eines Ereignisses
1. Suchen des Ereignisses, das Sie kennzeichnen möchten
2. Klicken Sie in der Spalte Flag auf das Kennzeichensymbol. 
![Abbildung des Gerätezeitachsenflags](images/device-flags.png)

## <a name="view-flagged-events"></a>Anzeigen gekennzeichneter Ereignisse  
1. Aktivieren Sie im Abschnitt **Zeitachsenfilter** **die Option Gekennzeichnete Ereignisse**.
2. Klicken Sie auf **Anwenden**. Es werden nur gekennzeichnete Ereignisse angezeigt.
Sie können zusätzliche Filter anwenden, indem Sie auf die Zeitleiste klicken. Dadurch werden nur Ereignisse vor dem gekennzeichneten Ereignis angezeigt.  
![Abbildung des Gerätezeitachsenflags mit Filter nach](images/device-flag-filter.png)
