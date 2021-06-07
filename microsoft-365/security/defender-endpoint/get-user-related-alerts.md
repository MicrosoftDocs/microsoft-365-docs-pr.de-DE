---
title: API zum Abrufen von benutzerbezogenen Warnungen
description: Abrufen einer Sammlung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID mitHilfe von Microsoft Defender für Endpunkt.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Benutzer, verwandte, Warnungen
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769929"
---
# <a name="get-user-related-alerts-api"></a>API zum Abrufen von benutzerbezogenen Warnungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung
Ruft eine Sammlung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID ab.


## <a name="limitations"></a>Begrenzungen
1. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Alert.Read.All |    "Alle Warnungen lesen"
Anwendung |   Alert.ReadWrite.All |   "Alle Warnungen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Alert.Read | "Warnungen lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Alert.ReadWrite | "Warnungen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen". Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)
>- Die Antwort enthält nur Warnungen, die Geräten zugeordnet sind, auf die der Benutzer zugriff hat, basierend auf Gerätegruppeneinstellungen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/users/{id}/alerts
```

**Die ID ist nicht der vollständige UPN, sondern nur der Benutzername. (Beispielsweise zum Abrufen von Warnungen für user1@contoso.com verwenden /api/users/user1/alerts)**

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich und Benutzer vorhanden – 200 OK. Wenn der Benutzer nicht vorhanden – 404 Nicht gefunden. 


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
