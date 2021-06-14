---
title: UpdateModelSettings
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
description: Verwenden Sie die REST-API, um die verfügbaren Modelleinstellungen für ein SharePoint Syntex-Dokumentverständnismodell zu aktualisieren.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904228"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell (siehe [Beispiel](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI-Parameter

Keine

## <a name="request-headers"></a>Anforderungsheader

| Kopfzeile | Wert |
|--------|-------|
|Annehmen|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Die entsprechende Digest für die aktuelle Website.|

## <a name="request-body"></a>Anforderungstext

|Name    |Typ   |Beschreibung |
|--------|-------|-------|
|ModelSettings|Zeichenfolge|JSON der Modelleinstellungen.|
|Beschreibung|string|Die Modellbeschreibung.|
|RetentionLabel| |Info für die zugehörige Bezeichnung (Bezeichnungs-ID und Name).|

## <a name="responses"></a>Antworten

| Name   | Typ  | Beschreibung|
|--------|-------|------------|
|200 OK| |Erfolg|

## <a name="examples"></a>Beispiele

### <a name="update-model-settings-for-contoso-contract"></a>Aktualisieren der Modelleinstellungen für Contoso-Vertrag

In diesem Beispiel werden die Modellbeschreibung und die Aufbewahrungsbezeichnung „Standard-Aufbewahrung“ aktualisiert. Die ID der Aufbewahrungsbezeichnung ist `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Beispielanfrage

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Beispielantwort

**Statuscode:** 200

## <a name="see-also"></a>Siehe auch

[Syntex-Dokumentverständnismodell-REST-API](syntex-model-rest-api.md)
