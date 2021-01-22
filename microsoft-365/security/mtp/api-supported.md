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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926198"
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
[Vorfall-APIs](api-incident.md) | Auflisten und Aktualisieren von Vorfällen sowie anderer praktischer Aufgaben.

### <a name="endpoint-uris"></a>Endpunkt-URIs

Der Basis-URI für beide haupt-APIs ist: https://api.security.microsoft.com . Um eine bessere Leistung zu erzielen, verwenden Sie einen Server, der näher an Ihrem Geografischen Standort ist:

- Usa: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Vereinigtes Königreich: api-uk.security.microsoft.com

Token können durch Zugriff auf erworben https://api.security.microsoft.com werden.

Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](https://docs.microsoft.com/odata/overview) z. B. https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Zugreifen auf die Microsoft Threat Protection-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
- [Fehlercodes verstehen](api-error-codes.md)
