---
title: File-Ressourcentyp
description: Abrufen der letzten Microsoft Defender for Endpoint-Warnungen im Zusammenhang mit Dateien.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199981"
---
# <a name="file-resource-type"></a>File-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Stellen Sie eine Dateientität in Defender for Endpoint dar.

## <a name="methods"></a>Methoden
Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Datei herunterladen](get-file-information.md) | [file](files.md) | Herunterladen einer einzelnen Datei 
[Auflisten dateibezogener Warnungen](get-file-related-alerts.md) | [Warnung](alerts.md) Sammlung | Get the [alert](alerts.md) entities that are associated with the file.
[Auflisten dateibezogener Computer](get-file-related-machines.md) | [Computersammlung](machine.md) | Get the [machine](machine.md) entities associated with the alert.
[Dateistatistiken](get-file-statistics.md) | Zusammenfassung der Statistik | Ruft die Verbreitung für die angegebene Datei ab.


## <a name="properties"></a>Eigenschaften
|Eigenschaft | Typ    |   Beschreibung |
|:---|:---|:---|
|sha1 | String | Sha1-Hash des Dateiinhalts |
|sha256 | String | Sha256-Hash des Dateiinhalts |
|globalPrevalence | Nullable long | Dateiprävalenz in der gesamten Organisation |
|globalFirstObserved | DateTimeOffset | Erstes Mal, wenn die Datei beobachtet wurde |
|globalLastObserved | DateTimeOffset | Letztes Mal, wenn die Datei beobachtet wurde |
|Größe | Nullable long | Größe der Datei |
|fileType | String | Dateityp |
|isPeFile | Boolescher Wert | true, wenn die Datei portierbar ist (z. B. "DLL", "EXE"usw.) |
|filePublisher | String | Dateiherausgeber |
|fileProductName | String | Produktname |
|Signer | String | Datei signer |
|Issuer | String | Dateiherausgeber |
|signerHash | String | Hash des Signaturzertifikats |
|isValidCertificate | Boolescher Wert | Wurde das Signaturzertifikat vom Microsoft Defender for Endpoint-Agent erfolgreich überprüft |
|determinationType | String | Der Bestimmungstyp der Datei |
|determinationValue | String | Ermittlungswert |


## <a name="json-representation"></a>Json-Darstellung

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
