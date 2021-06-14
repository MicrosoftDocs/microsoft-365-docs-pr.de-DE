---
title: Ein Modell erstellen
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
description: Verwenden Sie die REST-API, um ein Modell und den zugehörigen Inhaltstyp zu erstellen.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904222"
---
# <a name="create-model"></a>Ein Modell erstellen

Erstellt ein Modell und den zugehörigen Inhaltstyp. Beachten Sie, dass dies nur das Modell erstellt. Es muss noch im Inhaltscenter trainiert werden (siehe [Beispiel](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>HTTP-Anforderung

```
POST /_api/machinelearning/models HTTP/1.1
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
|_metadata|  |Festlegen der Objekt-Metadaten auf dem SPO. Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|Zeichenfolge|Die zugehörige Inhaltstypgruppe, die dem Modell zugeordnet ist. Standardmäßig auf „Intelligente Dokumentinhaltstypen“ festgelegt.|
|ContentTypeName|Zeichenfolge|Der zugehörige Inhaltstypname. Die erstellte Modelldatei wird den gleichen Namen haben.|

## <a name="responses"></a>Antworten

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|201 Erstellt| |Erfolg|

## <a name="examples"></a>Beispiele

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Erstellen eines neuen Dokumentverständnismodells mit Namen „Contoso-Vertrag“

#### <a name="sample-request"></a>Beispielanfrage

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a>Beispielantwort

**Statuscode:** 201

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
