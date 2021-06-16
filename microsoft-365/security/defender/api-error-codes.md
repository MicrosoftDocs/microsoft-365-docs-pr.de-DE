---
title: Häufige Fehlercodes Microsoft 365 Defender-REST-API
description: Erfahren Sie mehr über die allgemeinen Fehlercodes Microsoft 365 Defender REST-API
keywords: API, Fehler, Codes, häufige Fehler, Microsoft 365 Defender, API-Fehlercodes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: de24856e8ea7555a96de18cabca5ccadfe71b431
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930271"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Häufige Fehlercodes Microsoft 365 Defender-REST-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Fehlercodes können von einem Vorgang für eine der Microsoft 365 Defender-APIs zurückgegeben werden. Jede Fehlerantwort enthält eine Fehlermeldung, die bei der Behebung des Problems helfen kann. Die Fehlermeldungsspalte im Tabellenabschnitt enthält einige Beispielmeldungen. Der Inhalt der tatsächlichen Nachrichten variiert basierend auf den Faktoren, die die Antwort ausgelöst haben. Variabler Inhalt wird in der Tabelle durch eckige Klammern angegeben.

## <a name="error-codes"></a>Fehlercodes

Fehlercode | HTTP-Statuscode | Meldung
-|-|-
BadRequest | BadRequest (400) | Fehlermeldung "Allgemeine ungültige Anforderung".
ODataError | BadRequest (400) | Ungültige OData-URI-Abfrage. \<the specific error is specified\>
InvalidInput | BadRequest (400) | Ungültige Eingabe \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Der Hashwert \<the invalid hash\> ist ungültig.
InvalidDomainName | BadRequest (400) | Der Domänenname \<the invalid domain\> ist ungültig.
InvalidIpAddress | BadRequest (400) | Die IP-Adresse \<the invalid IP\> ist ungültig.
InvalidUrl | BadRequest (400) | DIE URL \<the invalid URL\> ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale Batchgröße überschritten. Received: \<batch size received\> , allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> fehlt.
OsPlatformNotSupported | BadRequest (400) | Die Betriebssystemplattform \<the client OS Platform\> wird für diese Aktion nicht unterstützt.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wird für clientversion \<supported client version\> und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisiert (401) | Nicht autorisiert (Unauthorized) <br /><br />*Hinweis: Wird in der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*
Verboten (Forbidden) | Forbidden (403) | Verboten (Forbidden) <br /><br />*Hinweis: Gültiges Token, aber unzureichende Berechtigung für die Aktion.*
DisabledFeature | Forbidden (403) | Mandantenfunktion ist nicht aktiviert.
DisallowedOperation | Forbidden (403) | \<the disallowed operation and the reason\>.
NotFound | Nicht gefunden (404) | Fehlermeldung "Allgemein nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Ressource \<the requested resource\> wurde nicht gefunden.
InternalServerError | Interner Serverfehler (500) | *Hinweis: Keine Fehlermeldung, wiederholen Sie den Vorgang, oder [wenden Sie sich an Microsoft,](/microsoft-365/business-video/get-help-support) wenn er nicht aufgelöst wird.*

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

## <a name="body-parameters"></a>Body parameters

> [!IMPORTANT]
> Bei Body-Parametern wird die Groß-/Kleinschreibung beachtet.

Wenn ein *InvalidRequestBody-* oder *MissingRequiredParameter-Fehler* auftritt, kann dies durch einen Tippfehler verursacht werden. Überprüfen Sie die API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="tracking-id"></a>Tracking-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung. Der Eigenschaftenname dieses Parameters ist *Ziel.* Wenn sie uns wegen eines Fehlers kontaktieren, hilft uns das Anhängen dieser ID, die Ursache des Problems zu finden.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Übersicht über Defender-APIs](api-overview.md)
- [Unterstützte Microsoft 365 Defender-APIs](api-supported.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
