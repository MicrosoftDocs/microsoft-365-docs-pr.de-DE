---
title: Modell mit Batch anwenden
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
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286537"
---
# <a name="batch-apply-model"></a>Modell mit Batch anwenden

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
|__metadata|ja|Zeichenfolge|Festlegen der Objekt-Metadaten auf dem SPO. Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publikationen|ja|MachineLearningPublicationEntityData[]|Die Sammlung von MachineLearningPublicationEntityData, von denen jedes Element das Modell und die Zieldokumentbibliothek angibt.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Name | Erforderlich | Typ | Beschreibung |
|--------|-------|--------|------------|
|ModelUniqueId|ja|Zeichenfolge|Die eindeutige ID der Modelldatei.|
|TargetSiteUrl|ja|Zeichenfolge|Die vollständige URL der Zielbibliothekswebsite.|
|TargetWebServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL aus dem Web für die Zielbibliothek.|
|TargetLibraryServerRelativeUrl|ja|Zeichenfolge|Die relative Server-URL der Zielbibliothek.|
|ViewOption|Nein|Zeichenfolge|Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.|

## <a name="response"></a>Antwort

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|201 Erstellt||Dies ist eine benutzerdefinierte API, die das Anwenden eines Modells auf mehrere Dokumentbibliotheken unterstützt. Im Falle eines teilweisen Erfolgs könnte immer noch „201 erstellt“ zurückgegeben werden und der Aufrufer muss den Antworttext überprüfen, um zu verstehen, ob das Modell erfolgreich auf eine Dokumentbibliothek angewendet wurde.|

## <a name="response-body"></a>Antworttext

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|TotalSuccesses|Ganzzahl|Die Gesamtzahl eines Modells, das erfolgreich auf eine Dokumentbibliothek angewendet wurde.|
|TotalFailures|Ganzzahl|Die Gesamtzahl eines Modells, das nicht auf eine Dokumentbibliothek angewendet werden konnte.|
|Details|MachineLearningPublicationResult[]|Sie Sammlung von MachineLearningPublicationResult, von denen jedes Element das detaillierte Ergebnis der Anwendung des Modells in der Dokumentbibliothek angibt.|

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

**Statuscode:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
