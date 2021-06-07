---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungsbewertung Ihrer Organisation, die Sicherheitsbewertung des Geräts und die Belichtungsbewertung nach Gerätegruppe ab.
keywords: APIs, Graph-API, unterstützte APIs, Bewertung, Belichtungsbewertung, Sicherheitsbewertung des Geräts, Belichtungsbewertung nach Gerätegruppe
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771429"
---
# <a name="score-resource-type"></a>Score-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Erhalten des Gefährdungsscores](get-exposure-score.md) | [Bewertung](score.md) | Rufen Sie die Belichtungsbewertung der Organisation ab.
[Sicherheitsbewertung des Geräts erhalten](get-device-secure-score.md) | [Bewertung](score.md) | Rufen Sie die Sicherheitsbewertung des Unternehmensgeräts ab.
[Belichtungsbewertung nach Gerätegruppe auflisten](get-machine-group-exposure-score.md)| [Bewertung](score.md) | Auflisten von Bewertungen nach Gerätegruppe.

## <a name="properties"></a>Eigenschaften

Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
Bewertung | Gleitkommawert mit doppelter Genauigkeit | Die aktuelle Bewertung.
Zeit | DateTime | Datum und Uhrzeit des Aufrufs dieser API.
RbacGroupName | String | Der Name der Gerätegruppe.
