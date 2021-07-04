---
title: File-Ressourcentyp
description: Rufen Sie aktuelle Microsoft Defender für Endpunkt-Warnungen im Zusammenhang mit Dateien ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290015"
---
# <a name="file-resource-type"></a>File-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Stellt eine Dateientität in Defender für Endpunkt dar.

## <a name="methods"></a>Methoden

Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Datei abrufen](get-file-information.md) | [file](files.md) | Abrufen einer einzelnen Datei 
[Dateibezogene Warnungen auflisten](get-file-related-alerts.md) | [Warnung](alerts.md) Sammlung | Ruft [](alerts.md) die Warnungsentitäten ab, die der Datei zugeordnet sind.
[Dateibezogene Computer auflisten](get-file-related-machines.md) | [Computersammlung](machine.md) | Ruft [](machine.md) die Computerentitäten ab, die der Warnung zugeordnet sind.
[Dateistatistiken](get-file-statistics.md) | Statistikzusammenfassung | Ruft die Verbreitung für die angegebene Datei ab.


## <a name="properties"></a>Eigenschaften

|Eigenschaft | Typ | Beschreibung |
|:---|:---|:---|
|sha1 | Zeichenfolge | Sha1-Hash des Dateiinhalts |
|sha256 | Zeichenfolge | Sha256-Hash des Dateiinhalts |
|globalPrevalence | Nullable long | Dateiprävalenz in der gesamten Organisation |
|globalFirstObserved | DateTimeOffset | Zeitpunkt, zu dem die Datei zum ersten Mal beobachtet wurde |
|globalLastObserved | DateTimeOffset | Zeitpunkt, zu dem die Datei zuletzt beobachtet wurde |
|Größe | Nullable long | Größe der Datei |
|Filetype | Zeichenfolge | Typ der Datei |
|isPeFile | Boolesch | "true", wenn die Datei portierbar ist (z. B. "DLL", "EXE" usw.) |
|filePublisher | Zeichenfolge | Dateiherausgeber |
|fileProductName | Zeichenfolge | Produktname |
|Signer | Zeichenfolge | Dateisignierer |
|Emittenten | Zeichenfolge | Dateiaussteller |
|signerHash | Zeichenfolge | Hash des Signaturzertifikats |
|isValidCertificate | Boolesch | Wurde das Signaturzertifikat vom Microsoft Defender für Endpunkt-Agent erfolgreich überprüft? |
|determinationType | Zeichenfolge | Der Bestimmungstyp der Datei |
|determinationValue | Zeichenfolge | Ermittlungswert |

## <a name="json-representation"></a>JSON-Darstellung

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
