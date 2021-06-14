---
title: Modell anwenden
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
description: Verwenden Sie die REST-API, um ein Dokumentverständnismodell auf eine oder mehrere Bibliotheken anzuwenden.
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904266"
---
# <a name="apply-model"></a>Modell anwenden

Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es) (siehe [Beispiel](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|201 Erstellt| |Beachten Sie: Da diese API das Anwenden von Modellen auf mehrere Bibliotheken unterstützt, kann ein 201 zurückgegeben werden, auch wenn das Anwenden des Modells auf eine der Bibliotheken fehlschlägt. <br>Überprüfen Sie den Antworttext, um zu verstehen, ob das Modell erfolgreich auf alle angegebenen Bibliotheken angewendet wurde. Weitere Details finden Sie im [Anforderungstext](rest-applymodel-method.md#request-body).|

## <a name="examples"></a>Beispiele

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Anwenden eines Modells auf die Vertragsdokumentbibliothek in der Repository-Website

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
