---
title: Versionshinweise zur Microsoft Defender for Endpoint-API
description: Versionshinweise für Updates, die an den Microsoft Defender for Endpoint-APIs vorgenommen werden.
keywords: Microsoft Defender for Endpoint API Release Notes, mde, APIs, Microsoft Defender for Endpoint API, updates, notes, release
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5c8e9d8e1c8ec020b4d742f61d276c93f6730bec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245552"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Versionshinweise zur Microsoft Defender for Endpoint-API

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In den folgenden Informationen werden die an den Microsoft Defender for Endpoint-APIs vorgenommenen Updates und deren Datumsangaben aufgeführt.

> [!TIP]
> RSS-Feed: Erhalten Sie eine Benachrichtigung, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feedleser kopieren und einfügen:
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Versionshinweise – neueste bis älteste (dd.mm.yyyy)

### <a name="03052021"></a>03.05.2021

- Neue API hinzugefügt: [Methoden und Eigenschaften der Korrekturaktivität](get-remediation-methods-properties.md).

### <a name="10022021"></a>10.02.2021

- Neue API hinzugefügt: [Batchupdatewarnungen](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- Die Geschwindigkeitseinschränkungen für [die Erweiterte Suche-API](run-advanced-query-api.md) wurden von 15 auf 45 Anforderungen pro Minute aktualisiert.

### <a name="21012021"></a>21.01.2021

- Neue API hinzugefügt: [Suchen von Geräten nach Tag](machine-tags.md).
- Neue API hinzugefügt: [Import Indicators](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Aktualisierter Warnungsnachweis: Eigenschaften ***detectionStatus** _, _*_parentProcessFilePath_*_ und _ *_parentProcessFileName_** hinzugefügt.
- Entität [Warnung aktualisiert:](alerts.md) ***eigenschaft detectorId*** hinzugefügt.

### <a name="15122020"></a>15.12.2020

- Entität [Device aktualisiert:](machine.md) ***IpInterfaces-Liste*** hinzugefügt. Weitere [Informationen finden Sie unter Auflisten von Geräten](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Neue API hinzugefügt: [Gerätewert festlegen.](set-device-value.md)
- Entität [Device aktualisiert:](machine.md) ***deviceValue-Eigenschaft*** hinzugefügt.

### <a name="01092020"></a>01.09.2020

- Option hinzugefügt, um die Alert-Entität mit dem zugehörigen Nachweis zu erweitern. Weitere [Informationen finden Sie unter List Alerts](get-alerts.md).
