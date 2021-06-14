---
title: Erstellen einer Klassifizierungsanforderung
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Verwenden Sie die REST-API, um eine Anforderung zur Klassifizierung einer oder mehrerer Dateien mithilfe eines trainierten Dokumentverständnismodells zu erstellen.
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904213"
---
# <a name="create-classification-request"></a>Erstellen einer Klassifizierungsanforderung

Erstellt eine Anforderung zur Klassifizierung einer oder mehrere Dateien unter Verwendung des angewendeten Dokumentverständnismodells (siehe [Beispiel](rest-createclassificationrequest.md#examples)).

Der REST-Dienst in SharePoint Online (sowie in lokalen Bereitstellungen von SharePoint 2016 und höher) unterstützt die Zusammenfassung mehrerer Anforderungen. Anforderungen werden in einem einzelnen Dienstaufruf mithilfe der OData-Abfrageoption „$batch“ kombiniert. Diese Methode kann verwendet werden, um Arbeitselemente für Klassifizierungen für Hunderte von Dokumenten gleichzeitig in die Warteschlange zu stellen.

## <a name="http-request"></a>HTTP-Anforderung

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a>URI-Parameter

Keine

## <a name="request-headers"></a>Anforderungsheader

| Kopfzeile | Wert |
|--------|-------|
|Annehmen|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Die entsprechende Digest für die aktuelle Website|

## <a name="request-body"></a>Anforderungstext

|Name    |Typ   |Beschreibung |
|--------|-------|------------|
|_metadata|Zeichenfolge |Festlegen der Objekt-Metadaten auf dem SPO. Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|TargetSiteId|GUID|Die ID der Website, auf der sich die zu klassifizierende Datei befindet.|
|TargetWebId|GUID|Die ID des Web, auf der sich die zu klassifizierende Datei befindet.|
|TargetUniqueId|GUID|Die ID der zu klassifizierenden Datei.|

## <a name="responses"></a>Antworten

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|201 Erstellt| |Erfolg|

## <a name="examples"></a>Beispiele

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Eine Anforderung für die Klassifizierung einer Datei mit ID „e6cff8b7-c90c-4564-b5b8-033449090932“ in die Warteschlange stellen

#### <a name="sample-request"></a>Beispielanfrage

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Beispielantwort

**Statuscode:** 201

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
