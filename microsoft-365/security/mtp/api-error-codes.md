---
title: Häufige Fehlercodes für Microsoft 365 Defender-Rest-API
description: Informationen zu den allgemeinen Fehlercodes von Microsoft 365 Defender-Rest-API
keywords: API, Fehler, Codes, häufige Fehler, MTP, API-Fehlercodes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846008"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Häufige Fehlercodes für Microsoft 365 Defender-Rest-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Die in der folgenden Tabelle aufgelisteten Fehlercodes werden möglicherweise von einem Vorgang in einer der Microsoft 365 Defender-APIs zurückgegeben.

Jede Fehlerantwort enthält eine Fehlermeldung, die zur Lösung des Problems beitragen kann.

Die Nachricht ist ein freier Text, der geändert werden kann.

Unten auf der Seite befinden sich Antwort Beispiele.

Fehlercode |HTTP-Statuscode |Message 
:---|:---|:---
BadRequest | BadRequest (400) | Fehlermeldung allgemeine ungültige Anforderung.
ODataError | BadRequest (400) | Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).
InvalidInput | BadRequest (400) | Ungültige Eingabe {ungültige Eingabe}.
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Der Hashwert {der ungültige Hash} ist ungültig.
InvalidDomainName | BadRequest (400) | Der Domänenname {ungültige Domäne} ist ungültig.
InvalidIpAddress | BadRequest (400) | IP-Adresse {Ungültige IP} ist ungültig.
InvalidUrl | BadRequest (400) | URL {die ungültige URL} ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale Batchgröße überschritten. Empfangen: {Batchgröße empfangen}, zulässig: {Batchgröße zulässig}.
MissingRequiredParameter | BadRequest (400) | Parameter {der fehlende Parameter} fehlt.
OsPlatformNotSupported | BadRequest (400) | Betriebssystemplattform {die Client Betriebssystem-Plattform} wird für diese Aktion nicht unterstützt.
ClientVersionNotSupported | BadRequest (400) | {Die angeforderte Aktion} wird auf Client Version {unterstützte Client Version} und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisiert (401) | Nicht autorisiert (in der Regel ungültige oder abgelaufene Autorisierungs Kopfzeile).
Verboten (Forbidden) | Unzulässig (403) | Unzulässig (gültiges Token, jedoch unzureichende Berechtigung für die Aktion).
DisabledFeature | Unzulässig (403) | Das Mandanten Feature ist nicht aktiviert.
DisallowedOperation | Unzulässig (403) | {der nicht zulässige Vorgang und der Grund}.
NotFound | Nicht gefunden (404) | Fehlermeldung "allgemeine nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Resource {die angeforderte Ressource} wurde nicht gefunden.
InternalServerError | Interner Server Fehler (500) | (Keine Fehlermeldung, wiederholen Sie den Vorgang, oder kontaktieren Sie uns, wenn er nicht aufgelöst wird)

## <a name="body-parameters-are-case-sensitive"></a>Bei den textparametern wird die Groß-/Kleinschreibung beachtet

Bei den übermittelten textparametern wird die Groß-/Kleinschreibung beachtet.
<br>Wenn ein **InvalidRequestBody** -oder **MissingRequiredParameter** -Fehler auftritt, kann dies auf einen falschen Parameter Capital oder einen Kleinbuchstaben zurückzuführen sein.
<br>Es wird empfohlen, die API-Dokumentationsseite zu überprüfen und zu überprüfen, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="correlation-request-id"></a>Korrelations Anforderungs-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.
<br>Der Eigenschaften Name dieses Parameters lautet "target".
<br>Wenn Sie uns über einen Fehler kontaktieren, wird das Anfügen dieser ID dazu beitragen, die Ursache des Problems zu ermitteln.

## <a name="examples"></a>Beispiele

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

