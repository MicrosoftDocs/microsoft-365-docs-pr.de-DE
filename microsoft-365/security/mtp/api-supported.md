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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844960"
---
# <a name="supported-microsoft-365-defender-apis"></a>Unterstützte Microsoft 365 Defender-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


### <a name="end-point-uris"></a>Endpunkt-URIs:

- Der Dienst Basis-URI lautet: https://api.security.microsoft.com <br>

>[!NOTE]
>Um eine bessere Leistung zu erzielen, können Sie den Server näher an ihrem geografischen Standort verwenden:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - Die Ressource für die Token-Akquisition sollte wie folgt aussehen: https://api.security.microsoft.com

 - Alle APIs unter ```/api``` Path sind OData-APIs. e.g. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Liste der verfügbaren APIs:

Thema | Beschreibung
:---|:---
[Erweiterte Suche-API](api-advanced-hunting.md) | Ausführen erweiterter Jagd Abfragen aus der API.
[Vorfall-APIs](api-incident.md) | Führen Sie Vorfall bezogene API-Aufrufe wie: Listen Vorfälle, Update Vorfall und vieles mehr aus.
