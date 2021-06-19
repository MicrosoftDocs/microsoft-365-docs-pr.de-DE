---
title: Versionshinweise zur Microsoft Defender für Endpunkt-API
description: Versionshinweise für Updates, die an den APIs des Microsoft Defender für Endpunkt-Satzes vorgenommen wurden.
keywords: Versionshinweise zur Microsoft Defender für Endpunkt-API, mde, APIs, Microsoft Defender für Endpunkt-API, Updates, Notizen, Release
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5e72db8d986ad096d6312f90530d9f9ff246afc3
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022294"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Versionshinweise zur Microsoft Defender für Endpunkt-API

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die folgenden Informationen enthalten die Aktualisierungen, die an den Microsoft Defender für Endpunkt-APIs vorgenommen wurden, und das Datum, an dem sie vorgenommen wurden.

> [!TIP]
> RSS-Feed: Erhalten Sie Benachrichtigungen, wenn diese Seite aktualisiert wird, indem Sie die folgende URL kopieren und in Ihren Feed-Reader einfügen:
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Versionshinweise – neueste bis älteste (dd.mm.yyyyy)

### <a name="06102021"></a>06.10.2021

- Neue Exportbewertungs-API-Methode – Delta Export Software _Vulnerabilities Assessment (JSON response)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md)hinzugefügt.

### <a name="05252021"></a>05.25.2021

- Neue API [Export-Bewertungsmethoden und -Eigenschaften pro Gerät](get-assessment-methods-properties.md)hinzugefügt.

### <a name="03052021"></a>03.05.2021

- Neue API hinzugefügt: [Korrekturaktivitätsmethoden und -eigenschaften.](get-remediation-methods-properties.md)

### <a name="10022021"></a>10.02.2021

- Neue API hinzugefügt: [Warnungen bei Batchaktualisierungen.](batch-update-alerts.md)

### <a name="25012021"></a>25.01.2021

- Aktualisierte Rateneinschränkungen für die API für [die erweiterte Suche](run-advanced-query-api.md) von 15 bis 45 Anforderungen pro Minute.

### <a name="21012021"></a>21.01.2021

- Neue API hinzugefügt: [Geräte nach Tag suchen.](machine-tags.md)
- Neue API hinzugefügt: [Import indicators](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Aktualisierter Warnungsnachweis: eigenschaften ***detectionStatus** _, _*_parentProcessFilePath_*_ und _ *_parentProcessFileName_** hinzugefügt.
- Aktualisierte [Warnungsentität:](alerts.md) ***die eigenschaft "detectorId"*** hinzugefügt.

### <a name="15122020"></a>15.12.2020

- Aktualisierte [](machine.md) Geräteentität: ***IpInterfaces-Liste*** hinzugefügt. Siehe ["Geräte auflisten".](get-machines.md)

### <a name="04112020"></a>04.11.2020

- Neue API hinzugefügt: [Gerätewert festlegen.](set-device-value.md)
- Aktualisierte [](machine.md) Geräteentität: ***deviceValue-Eigenschaft*** hinzugefügt.

### <a name="01092020"></a>01.09.2020

- Option zum Erweitern der Warnungsentität um die zugehörigen Nachweise hinzugefügt. Siehe ["Warnungen auflisten".](get-alerts.md)
