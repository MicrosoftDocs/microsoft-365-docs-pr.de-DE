---
title: Softwaremethoden und -eigenschaften
description: Ruft die wichtigsten warnungen der letzten Zeit ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771403"
---
# <a name="software-resource-type"></a>Softwareressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Software auflisten](get-software.md) | Softwaresammlung | Auflisten des Softwarebestands der Organisation.
[Software nach ID erhalten](get-software-by-id.md) | Software | Rufen Sie eine bestimmte Software anhand ihrer Software-ID ab.
[Softwareversionsverteilung auflisten](get-software-ver-distribution.md)| Distributionssammlung | Auflisten der Softwareversionsverteilung nach Software-ID.
[Auflisten von Computern nach Software](get-machines-by-software.md)| MachineRef-Sammlung | Rufen Sie eine Liste der Geräte ab, die der Software-ID zugeordnet sind.
[Auflisten von Sicherheitsrisiken nach Software](get-vuln-by-software.md) | [Sammlung von Sicherheitsrisiken](vulnerability.md) | Rufen Sie eine Liste der Sicherheitsrisiken ab, die der Software-ID zugeordnet sind.
[Fehlende KBs erhalten](get-missing-kbs-software.md) | KB-Auflistung | Abrufen einer Liste fehlender KBs, die der Software-ID zugeordnet sind

## <a name="properties"></a>Eigenschaften

Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | String | Software-ID
Name | String | Softwarename
Anbieter | String | Name des Softwareanbieters
Schwächen | Long | Anzahl der entdeckten Sicherheitsrisiken
publicExploit | Boolesch | Öffentliche Exploits sind für einige der Sicherheitsrisiken vorhanden
activeAlert | Boolesch | Dieser Software ist eine aktive Warnung zugeordnet.
exposedMachines | Long | Anzahl der verfügbar gemachten Geräte
impactScore | Gleitkommawert mit doppelter Genauigkeit | Auswirkung dieser Software auf die Belichtungsbewertung
