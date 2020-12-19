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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719214"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Häufige Fehlercodes für Microsoft 365 Defender-Rest-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Fehlercodes werden möglicherweise von einem Vorgang in einer der Microsoft 365 Defender-APIs zurückgegeben. Jede Fehlerantwort enthält eine Fehlermeldung, die helfen kann, das Problem zu beheben. Die Spalte Fehlermeldung im Abschnitt Table enthält einige Beispiel Meldungen. Der Inhalt der tatsächlichen Nachrichten variiert je nach den Faktoren, die die Antwort ausgelöst haben. Variablen Inhalt wird in der Tabelle durch spitzen Klammern angegeben.

## <a name="error-codes"></a>Fehlercodes

Fehlercode | HTTP-Statuscode | Nachricht
-|-|-
BadRequest | BadRequest (400) | Fehlermeldung allgemeine ungültige Anforderung.
ODataError | BadRequest (400) | Ungültige OData-URI \<the specific error is specified\> -Abfrage.
InvalidInput | BadRequest (400) | Ungültige Eingabe \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Ungültiger Anforderungstext.
InvalidHashValue | BadRequest (400) | Der Hashwert \<the invalid hash\> ist ungültig.
InvalidDomainName | BadRequest (400) | Der Domänenname \<the invalid domain\> ist ungültig.
InvalidIpAddress | BadRequest (400) | Die IP-Adresse \<the invalid IP\> ist ungültig.
InvalidUrl | BadRequest (400) | \<the invalid URL\>Die URL ist ungültig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale Batchgröße überschritten. Empfangen: \<batch size received\> , zulässig: {Batchgröße zulässig}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> fehlt.
OsPlatformNotSupported | BadRequest (400) | Die Betriebssystemplattform \<the client OS Platform\> wird für diese Aktion nicht unterstützt.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wird auf Client Version \<supported client version\> und höher unterstützt.
Nicht autorisiert (Unauthorized) | Nicht autorisiert (401) | Nicht autorisiert (Unauthorized) <br /><br />*Hinweis: wird in der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*
Verboten (Forbidden) | Unzulässig (403) | Verboten (Forbidden) <br /><br />*Hinweis: gültiges Token, jedoch unzureichende Berechtigungen für die Aktion*.
DisabledFeature | Unzulässig (403) | Das Mandanten Feature ist nicht aktiviert.
DisallowedOperation | Unzulässig (403) | \<the disallowed operation and the reason\>.
NotFound | Nicht gefunden (404) | Fehlermeldung "allgemeine nicht gefunden".
ResourceNotFound | Nicht gefunden (404) | Ressource \<the requested resource\> wurde nicht gefunden.
InternalServerError | Interner Server Fehler (500) | *Hinweis: keine Fehlermeldung, wiederholen Sie den Vorgang, oder wenden Sie sich an Microsoft, wenn er nicht aufgelöst wird.*

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
> Bei den textparametern wird die Groß-/Kleinschreibung beachtet.

Wenn ein *InvalidRequestBody* -oder *MissingRequiredParameter* -Fehler auftritt, kann dies auf einen Tippfehler zurückzuführen sein. Lesen Sie in der API-Dokumentation nach, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.

## <a name="tracking-id"></a>Tracking-ID

Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung. Der Eigenschaften Name dieses Parameters ist *target*. Wenn Sie uns über einen Fehler kontaktieren, hilft uns das Anfügen dieser ID, die Ursache des Problems zu ermitteln.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Unterstützte Microsoft 365 Defender-APIs](api-supported.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
