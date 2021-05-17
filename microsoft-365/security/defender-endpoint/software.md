---
title: Softwaremethoden und -eigenschaften
description: Ruft die aktuellsten Warnungen ab.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187198"
---
# <a name="software-resource-type"></a>Softwareressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Software auflisten](get-software.md) | Softwaresammlung | Listet das Inventar der Organisationssoftware auf.
[Software nach ID erhalten](get-software-by-id.md) | Software | Erhalten Sie eine bestimmte Software nach ihrer Software-ID.
[Softwareversionsverteilung auflisten](get-software-ver-distribution.md)| Verteilungssammlung | Listet die Softwareversionsverteilung nach Software-ID auf.
[Auflisten von Computern nach Software](get-machines-by-software.md)| MachineRef-Auflistung | Rufen Sie eine Liste der Geräte ab, die der Software-ID zugeordnet sind.
[Auflisten von Sicherheitsrisiken nach Software](get-vuln-by-software.md) | [Vulnerability-Auflistung](vulnerability.md) | Rufen Sie eine Liste der Sicherheitsrisiken ab, die der Software-ID zugeordnet sind.
[Fehlende KBs erhalten](get-missing-kbs-software.md) | KB-Auflistung | Erhalten einer Liste fehlender KBs, die der Software-ID zugeordnet sind

## <a name="properties"></a>Eigenschaften

Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | String | Software-ID
Name | String | Softwarename
Anbieter | String | Name des Softwareanbieters
Schwächen | Long | Anzahl der erkannten Sicherheitsrisiken
publicExploit | Boolescher Wert | Für einige der Sicherheitsrisiken ist ein öffentlicher Exploit vorhanden.
activeAlert | Boolescher Wert | Dieser Software ist eine aktive Warnung zugeordnet.
exposedMachines | Long | Anzahl der verfügbar gemachten Geräte
impactScore | Gleitkommawert mit doppelter Genauigkeit | Auswirkungen dieser Software auf die Belichtungswertung
