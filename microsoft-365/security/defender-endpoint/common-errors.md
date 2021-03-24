---
title: Häufige Microsoft Defender ATP-API-Fehler
description: Liste der häufigen Microsoft Defender ATP-API-Fehler mit Beschreibungen.
keywords: apis, mdatp api, errors, troubleshooting
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
ms.technology: mde
ms.openlocfilehash: ddbbe07bc477ae3a5016feb795b5bad5ed82a30a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064376"
---
# <a name="common-rest-api-error-codes"></a>Häufige Rest-API-Fehlercodes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Die in der folgenden Tabelle aufgeführten Fehlercodes können von einem Vorgang für eine beliebige Microsoft Defender for Endpoint-APIs zurückgegeben werden.
* Zusätzlich zum Fehlercode enthält jede Fehlerantwort eine Fehlermeldung, mit der das Problem behoben werden kann.
* Die Nachricht ist ein Freitext, der geändert werden kann.
* Unten auf der Seite finden Sie Antwortbeispiele.

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Fehlercode |HTTP-Statuscode |Message 
:---|:---|:---
BadRequest | BadRequest (400) | Fehlermeldung "Allgemeine ungültige Anforderung".
ODataError | BadRequest (400) | Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).
InvalidInput | BadRequest (400) | Ungültige Eingabe {ungültige Eingabe}.
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Der Hashwert {der ungültige Hash} ist ungültig.
InvalidDomainName | BadRequest (400) | Der Domänenname {die ungültige Domäne} ist ungültig.
InvalidIpAddress | BadRequest (400) | Die IP-Adresse {die ungültige IP} ist ungültig.
InvalidUrl | BadRequest (400) | URL {die ungültige URL} ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Die maximale Batchgröße wurde überschritten. Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter {der fehlende Parameter} fehlt.
OsPlatformNotSupported | BadRequest (400) | Die Betriebssystemplattform {die Clientbetriebssystemplattform} wird für diese Aktion nicht unterstützt.
ClientVersionNotSupported | BadRequest (400) | {Die angeforderte Aktion} wird für die Clientversion {unterstützte Clientversion} und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisierter Benutzer (401) | Nicht autorisiert (ungültiger oder abgelaufener Autorisierungsheader).
Verboten (Forbidden) | Verboten (403) | Verboten (gültiges Token, aber unzureichende Berechtigung für die Aktion).
DisabledFeature | Verboten (403) | Das Mandantenfeature ist nicht aktiviert.
DisallowedOperation | Verboten (403) | {der unzulässige Vorgang und der Grund}.
NotFound | Nicht gefunden (404) | Fehlermeldung "Allgemein nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Ressource {die angeforderte Ressource} wurde nicht gefunden.
InternalServerError | Interner Serverfehler (500) | (Keine Fehlermeldung, wiederholen Sie den Vorgang)
TooManyRequests | Zu viele Anforderungen (429) | Die Antwort stellt das Erreichen des Kontingentgrenzwerts entweder nach Anzahl der Anforderungen oder nach CPU dar.

## <a name="body-parameters-are-case-sensitive"></a>Bei Textparametern wird die Kleinschreibung beachtet.

Bei den übermittelten Textparametern wird derzeit die Kleinschreibung beachtet.
<br>Wenn ein **InvalidRequestBody-** oder **MissingRequiredParameter-Fehler** aufgetreten ist, kann dies durch ein falsches Parameterhaupt- oder Kleinbuchstaben verursacht werden.
<br>Überprüfen Sie die Seite API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="correlation-request-id"></a>Korrelationsanforderungs-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.
<br>Der Eigenschaftenname dieses Parameters ist "target".
<br>Wenn Sie uns über einen Fehler kontaktieren, hilft das Anfügen dieser ID, die Ursache des Problems zu finden.

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
