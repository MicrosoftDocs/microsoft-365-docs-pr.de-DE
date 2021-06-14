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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904210"
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
|ModelUniqueId|ja|Zeichenfolge|Die eindeutige ID der Modelldatei.|
TargetSiteUrl|ja|Zeichenfolge|Die vollständige URL der Zielbibliothekswebsite.|
TargetWebServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL aus dem Web für die Zielbibliothek.|
TargetLibraryServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL der Zielbibliothek.|
ViewOption|Nein|Zeichenfolge|Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.|

## <a name="response"></a>Antwort

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|200 OK| |Erfolg|


## <a name="examples"></a>Beispiele

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Entfernen eines Modells aus der Vertragsdokumentbibliothek in der Repository-Website

In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Beispielanfrage

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Beispielantwort

In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das auf die angegebenen Bibliotheken angewendet wird.

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
