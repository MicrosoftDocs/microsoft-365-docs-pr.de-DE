---
title: Unterstützte Microsoft Threat Protection-APIs
description: Unterstützte Microsoft Threat Protection-APIs
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203695"
---
# <a name="supported-microsoft-threat-protection-apis"></a>Unterstützte Microsoft Threat Protection-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft Threat Protection

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
