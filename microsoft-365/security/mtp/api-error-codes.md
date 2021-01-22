---
title: Allgemeine Fehlercodes der Microsoft 365 Defender REST-API
description: Erfahren Sie mehr über die allgemeinen Fehlercodes der Microsoft 365 Defender REST-API.
keywords: API, Fehler, Codes, häufige Fehler, Mtp, API-Fehlercodes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928390"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Allgemeine Fehlercodes der Microsoft 365 Defender REST-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Fehlercodes können von einem Vorgang auf einer der Microsoft 365 Defender-APIs zurückgegeben werden. Jede Fehlerantwort enthält eine Fehlermeldung, die zur Behebung des Problems beitragen kann. Die Fehlermeldungsspalte im Tabellenabschnitt enthält einige Beispielmeldungen. Der Inhalt tatsächlicher Nachrichten variiert je nach den Faktoren, die die Antwort ausgelöst haben. Variabler Inhalt wird in der Tabelle durch spitze Klammern angegeben.

## <a name="error-codes"></a>Fehlercodes

Fehlercode | HTTP-Statuscode | Message
-|-|-
BadRequest | BadRequest (400) | Fehlermeldung "Allgemeine ungültige Anforderung".
ODataError | BadRequest (400) | Ungültige OData-URI-Abfrage. \<the specific error is specified\>
InvalidInput | BadRequest (400) | Ungültige \<the invalid input\> Eingabe.
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Hashwert \<the invalid hash\> ist ungültig.
InvalidDomainName | BadRequest (400) | Der \<the invalid domain\> Domänenname ist ungültig.
InvalidIpAddress | BadRequest (400) | Die \<the invalid IP\> IP-Adresse ist ungültig.
InvalidUrl | BadRequest (400) | Die URL \<the invalid URL\> ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Die maximale Batchgröße wurde überschritten. Received: \<batch size received\> , allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> fehlt.
OsPlatformNotSupported | BadRequest (400) | Die \<the client OS Platform\> Betriebssystemplattform wird für diese Aktion nicht unterstützt.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wird für die Clientversion \<supported client version\> und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisierte (401) | Nicht autorisiert (Unauthorized) <br /><br />*Hinweis: In der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*
Verboten (Forbidden) | Verboten (403) | Verboten (Forbidden) <br /><br />*Hinweis: Gültiges Token, aber unzureichende Berechtigung für die Aktion.*
DisabledFeature | Verboten (403) | Das Mandantenfeature ist nicht aktiviert.
DisallowedOperation | Verboten (403) | \<the disallowed operation and the reason\>.
NotFound | Nicht gefunden (404) | Fehlermeldung "Allgemein nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Ressource \<the requested resource\> wurde nicht gefunden.
InternalServerError | Interner Serverfehler (500) | *Hinweis: Keine Fehlermeldung, wiederholen Sie den Vorgang, oder wenden Sie sich an Microsoft, wenn er nicht aufgelöst wird*

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
> Bei Textparametern wird die Kleinschreibung beachtet.

Wenn ein Fehler *"InvalidRequestBody"* oder *"MissingRequiredParameter"* auftritt, kann er durch einen Tippfehler verursacht werden. Überprüfen Sie die API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="tracking-id"></a>Nachverfolgungs-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung. Der Eigenschaftenname dieses Parameters ist *Ziel.* Wenn Sie uns über einen Fehler kontaktieren, hilft uns das Anfügen dieser ID, die Ursache des Problems zu finden.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Unterstützte Microsoft 365 Defender-APIs](api-supported.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
