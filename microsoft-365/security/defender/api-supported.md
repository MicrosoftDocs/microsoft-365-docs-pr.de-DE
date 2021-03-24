---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: MTP, APIs, API
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
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060804"
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
[Erweiterte Suche-API](api-advanced-hunting.md) | Führen Sie Erweiterte Suchabfragen aus.
[Vorfall-APIs](api-incident.md) | Auflisten und Aktualisieren von Vorfällen sowie andere praktische Aufgaben.

### <a name="endpoint-uris"></a>Endpunkt-URIs

Der Basis-URI für beide Haupt-APIs ist: https://api.security.microsoft.com . Verwenden Sie für eine bessere Leistung einen Server, der näher an Ihrer Geolocation ist:

- Usa: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Vereinigtes Königreich: api-uk.security.microsoft.com

Token können durch Zugriff auf erworben https://api.security.microsoft.com werden.

Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](/odata/overview) z. B. https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Zugreifen auf die Microsoft Threat Protection-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und -Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)