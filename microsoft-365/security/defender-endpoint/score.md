---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungs-, Geräte- und Belichtungsergebnis ihrer Organisation nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200161"
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
[Belichtungsergebnis erhalten](get-exposure-score.md) | [Bewertung](score.md) | Hier erhalten Sie die belichtungsergebnis der Organisation.
[Sichern der Gerätepunktzahl](get-device-secure-score.md) | [Bewertung](score.md) | Holen Sie sich die sicherheitse Bewertung des Organisationsgeräts.
[Belichtungsergebnis nach Gerätegruppe auflisten](get-machine-group-exposure-score.md)| [Bewertung](score.md) | Noten nach Gerätegruppe auflisten.

## <a name="properties"></a>Eigenschaften

Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
Bewertung | Gleitkommawert mit doppelter Genauigkeit | Die aktuelle Bewertung.
Zeit | DateTime | Datum und Uhrzeit des Aufrufs dieser API.
RbacGroupName | String | Der Name der Gerätegruppe.
