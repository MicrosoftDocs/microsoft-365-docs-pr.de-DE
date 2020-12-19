---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: MTP, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719322"
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
[Erweiterte Suche-API](api-advanced-hunting.md) | Führen Sie erweiterte Jagd Abfragen aus.
[Vorfall-APIs](api-incident.md) | Auflisten und Aktualisieren von Vorfällen sowie anderer praktischer Aufgaben.

### <a name="endpoint-uris"></a>Endpunkt-URIs

Der Basis-URI für die beiden Haupt-APIs lautet: https://api.security.microsoft.com . Um eine bessere Leistung zu erzielen, verwenden Sie einen Server näher an Ihrem Standort:

- Vereinigte Staaten: API-US.Security.Microsoft.com
- Europa: API-EU.Security.Microsoft.com
- Vereinigtes Königreich: API-UK.Security.Microsoft.com

Token können durch den Zugriff erworben werden https://api.security.microsoft.com .

Alle APIs entlang des `/api` Pfads verwenden das [OData](https://docs.microsoft.com/odata/overview) -Protokoll, beispielsweise https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Zugreifen auf die Microsoft Threat Protection-APIs](api-access.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
