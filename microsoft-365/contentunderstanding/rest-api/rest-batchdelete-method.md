---
title: BatchDelete
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
description: Verwenden Sie die REST-API, um ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken zu entfernen.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177237"
---
# <a name="batchdelete"></a>BatchDelete

Entfernt ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken. Beachten Sie, dass das Modell von allen Bibliotheken entfernt werden muss, bevor es gelöscht werden kann (siehe [Beispiel](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>URI-Parameter

Keine

## <a name="request-headers"></a>Anforderungsheader

| Kopfzeile | Wert |
|--------|-------|
|Annehmen|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Der entsprechende Digest für die aktuelle Website.|

## <a name="request-body"></a>Anforderungstext

| Name | Erforderlich | Typ | Beschreibung |
|--------|-------|--------|------------|
|Publikationen|ja|MachineLearningPublicationEntityData[]|Die Sammlung von MachineLearningPublicationEntityData, von denen jedes Element das Modell und die Zieldokumentbibliothek angibt.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Name | Erforderlich | Typ | Beschreibung |
|--------|-------|--------|------------|
|ModelUniqueId|ja|Zeichenfolge|Die eindeutige ID der Modelldatei.|
|TargetSiteUrl|ja|Zeichenfolge|Die vollständige URL der Zielbibliothekswebsite.|
|TargetWebServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL aus dem Web für die Zielbibliothek.|
|TargetLibraryServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL der Zielbibliothek.|

## <a name="response"></a>Antwort

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|200 OK||Dies ist ein benutzerdefiniertes API, um das Entfernen eines Modells aus einer Mehrfach-Dokumentbibliothek zu unterstützen. Im Falle eines Teilerfolgs könnte immer noch „200 OK“ zurückgegeben werden und der Aufrufer muss den Antworttext untersuchen, um zu verstehen, ob das Modell erfolgreich aus einer Dokumentbibliothek entfernt wurde.|

## <a name="response-body"></a>Antworttext
| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|TotalSuccesses|Ganzzahl|Die Gesamtzahl eines Modells, das erfolgreich aus einer Dokumentbibliothek entfernt wurde.|
|TotalFailures|Ganzzahl|Die Gesamtzahl eines Modells, das nicht aus einer Dokumentbibliothek entfernt werden konnte.|
|Details|MachineLearningPublicationResult[]|Die Sammlung von MachineLearningPublicationResult, von denen jedes Element das detaillierte Ergebnis der Entfernung des Modells aus der Dokumentbibliothek angibt.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult
| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|StatusCode|Ganzzahl|Der HTTP-Statuscode.|
|ErrorMessage|Zeichenfolge|Die Fehlermeldung, welche erläutert, was beim Anwenden des Modells auf die Dokumentbibliothek falsch ist.|
|Veröffentlichung|MachineLearningPublicationEntityData|Es gibt die Modellinformation und die Zieldokumentbibliothek an.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Name | Typ | Beschreibung |
|--------|--------|------------|
|ModelUniqueId|Zeichenfolge|Die eindeutige ID der Modelldatei.|
|TargetSiteUrl|Zeichenfolge|Die vollständige URL der Zielbibliothekswebsite.|
|TargetWebServerRelativeUrl|Zeichenfolge|Die relative Server-URL aus dem Web für die Zielbibliothek.|
|TargetLibraryServerRelativeUrl|Zeichenfolge|Die relative Server-URL der Zielbibliothek.|

## <a name="examples"></a>Beispiele

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Entfernen eines Modells aus der Vertragsdokumentbibliothek in der Repository-Website

In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Beispielanfrage

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a>Beispielantwort

In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das aus den angegebenen Bibliotheken entfernt wird.

**Statuscode:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
