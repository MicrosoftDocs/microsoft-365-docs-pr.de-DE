---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: Microsoft 365 Defender, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985084"
---
# <a name="supported-microsoft-365-defender-apis"></a>Unterstützte Microsoft 365 Defender-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="list-of-available-apis"></a>Liste der verfügbaren APIs

Artikel | Beschreibung
-|-
[Erweiterte Bedrohungssuche-API](api-advanced-hunting.md) | Führen Sie Abfragen für die erweiterte Suche aus.
[Vorfall-APIs](api-incident.md) | Auflisten und Aktualisieren von Vorfällen zusammen mit anderen praktischen Aufgaben.
[Streaming-API](streaming-api.md) (Vorschau) | Versenden Sie Echtzeitereignisse und -warnungen, sobald sie in einem einzelnen Datenstrom auftreten.

### <a name="endpoint-uris"></a>Endpunkt-URIs

Der Basis-URI für beide Haupt-APIs lautet: https://api.security.microsoft.com . Um eine bessere Leistung zu erzielen, verwenden Sie einen Server, der sich näher an Ihrem Geolocation befindet:

- Vereinigte Staaten: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Vereinigtes Königreich: api-uk.security.microsoft.com

Token können durch Zugriff auf abgerufen https://api.security.microsoft.com werden.

Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](/odata/overview) z. https://api.security.microsoft.com/api/incidents B. .

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender ÜBERSICHT ÜBER APIs](api-overview.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Streaming- API](../defender-endpoint/raw-data-export.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
