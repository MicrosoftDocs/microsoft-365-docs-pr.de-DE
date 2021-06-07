---
title: Häufige Fehler der Microsoft Defender für Endpunkt-API
description: Liste der häufigsten Microsoft Defender für Endpunkt-API-Fehler mit Beschreibungen.
keywords: APIs, Microsoft Defender für Endpunkt-API, Fehler, Problembehandlung
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771009"
---
# <a name="common-rest-api-error-codes"></a>Häufige Rest-API-Fehlercodes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Die in der folgenden Tabelle aufgeführten Fehlercodes können von einem Vorgang für alle Microsoft Defender für Endpunkt-APIs zurückgegeben werden.
* Zusätzlich zum Fehlercode enthält jede Fehlerantwort eine Fehlermeldung, die bei der Behebung des Problems helfen kann.
* Die Nachricht ist ein Freitext, der geändert werden kann.
* Am unteren Rand der Seite finden Sie Antwortbeispiele.

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Fehlercode |HTTP-Statuscode |Message 
:---|:---|:---
BadRequest | BadRequest (400) | Fehlermeldung "Allgemeine ungültige Anforderung".
ODataError | BadRequest (400) | Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).
InvalidInput | BadRequest (400) | Ungültige Eingabe {die ungültige Eingabe}.
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Der Hashwert {der ungültige Hash} ist ungültig.
InvalidDomainName | BadRequest (400) | Der Domänenname {die ungültige Domäne} ist ungültig.
InvalidIpAddress | BadRequest (400) | Die IP-Adresse {die ungültige IP} ist ungültig.
InvalidUrl | BadRequest (400) | URL {die ungültige URL} ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale Batchgröße überschritten. Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter {der fehlende Parameter} fehlt.
OsPlatformNotSupported | BadRequest (400) | Os Platform {the client OS Platform} is not supported for this action.
ClientVersionNotSupported | BadRequest (400) | {Die angeforderte Aktion} wird für Clientversion {unterstützte Clientversion} und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisiert (401) | Nicht autorisiert (ungültiger oder abgelaufener Autorisierungsheader).
Verboten (Forbidden) | Forbidden (403) | Unzulässig (gültiges Token, aber unzureichende Berechtigung für die Aktion).
DisabledFeature | Forbidden (403) | Mandantenfunktion ist nicht aktiviert.
DisallowedOperation | Forbidden (403) | {der unzulässige Vorgang und der Grund}.
NotFound | Nicht gefunden (404) | Fehlermeldung "Allgemein nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Ressource {die angeforderte Ressource} wurde nicht gefunden.
InternalServerError | Interner Serverfehler (500) | (Keine Fehlermeldung, Vorgang wiederholen)
TooManyRequests | Zu viele Anforderungen (429) | Die Antwort stellt das Erreichen des Kontingentlimits entweder nach Anzahl der Anforderungen oder nach CPU dar.

## <a name="body-parameters-are-case-sensitive"></a>Bei Body-Parametern wird die Groß-/Kleinschreibung beachtet.

Bei den übermittelten Textkörperparametern wird derzeit die Groß-/Kleinschreibung beachtet.
<br>Wenn ein **InvalidRequestBody-** oder **MissingRequiredParameter-Fehler** auftritt, kann dies durch ein falsches Parameterhaupt- oder Kleinbuchstaben verursacht werden.
<br>Überprüfen Sie die API-Dokumentationsseite, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="correlation-request-id"></a>Korrelationsanforderungs-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.
<br>Der Eigenschaftenname dieses Parameters lautet "target".
<br>Wenn Sie uns bezüglich eines Fehlers kontaktieren, hilft das Anhängen dieser ID, die Ursache des Problems zu finden.

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
