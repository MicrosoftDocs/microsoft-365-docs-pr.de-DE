---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungs-, Geräte- und Belichtungsergebnis ihrer Organisation nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
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
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500952"
---
# <a name="score-resource-type"></a>Bewertungsressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Erhalten des Gefährdungsscores](get-exposure-score.md) | [Bewertung](score.md) | Hier erhalten Sie die belichtungsergebnis der Organisation.
[Sicherheitsbewertung des Geräts erhalten](get-device-secure-score.md) | [Bewertung](score.md) | Holen Sie sich die sicherheitse Bewertung des Organisationsgeräts.
[Belichtungsergebnis nach Gerätegruppe auflisten](get-machine-group-exposure-score.md)| [Bewertung](score.md) | Noten nach Gerätegruppe auflisten.

## <a name="properties"></a>Eigenschaften

Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
Bewertung | Gleitkommawert mit doppelter Genauigkeit | Die aktuelle Bewertung.
Zeit | DateTime | Datum und Uhrzeit des Aufrufs dieser API.
RbacGroupName | Zeichenfolge | Der Name der Gerätegruppe.
