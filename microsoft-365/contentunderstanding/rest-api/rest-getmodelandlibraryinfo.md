---
title: Modell- und Bibliotheksinformationen abrufen
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
description: Verwenden Sie die REST-API, um Informationen über das Modell abzurufen und die Bibliothek, auf die es angewendet wurde.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904225"
---
# <a name="get-model-and-library-information"></a>Modell- und Bibliotheksinformationen abrufen

Ruft Informationen ab über das Modell und die Bibliothek, auf die es angewendet wurde (siehe [Beispiel](rest-getmodelandlibraryinfo.md#examples)).

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a>URI-Parameter

| Name | In | Erforderlich | Typ | Beschreibung |
|--------|-------|--------|------------|
|ModelUniqueId|Abfrage|True|GUID|Die eindeutige ID der Modelldatei.|

## <a name="request-headers"></a>Anforderungsheader

| Kopfzeile | Wert |
|--------|-------|
|Annehmen|application/json;odata=verbose|


## <a name="request-body"></a>Anforderungstext

| Name | Erforderlich | Typ | Beschreibung |
|--------|-------|--------|------------|
|ModelUniqueId|ja|Zeichenfolge|Die eindeutige ID der Modelldatei.|
|TargetSiteUrl|ja|Zeichenfolge|Die vollständige URL der Zielbibliothekswebsite.|
|TargetWebServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL aus dem Web für die Zielbibliothek.|
|TargetLibraryServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL der Zielbibliothek.|
|TargetLibraryRemoved|ja|int|Die Kennzeichnung, die angibt, ob die Zielbibliothek entfernt wurde oder nicht.|

## <a name="response"></a>Antwort

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|200 OK| |Erfolg|
|201 Erstellt| |Beachten Sie: Da diese API das Anwenden von Modellen auf mehrere Bibliotheken unterstützt, kann ein 201 zurückgegeben werden, auch wenn das Anwenden des Modells auf eine der Bibliotheken fehlschlägt. <br>Überprüfen Sie den Antworttext, um zu verstehen, ob das Modell erfolgreich auf alle angegebenen Bibliotheken angewendet wurde. Weitere Details finden Sie im [Anforderungstext](rest-getmodelandlibraryinfo.md#request-body).|

## <a name="examples"></a>Beispiele

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a>Abrufen von Informationen über das Vertragsmodell und die vorbereitete Dokumentenbibliothek in der Repository-Website

In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Beispielanfrage

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a>Beispielantwort

**Statuscode:** 200

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
