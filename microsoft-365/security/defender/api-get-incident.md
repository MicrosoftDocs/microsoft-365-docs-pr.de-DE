---
title: Vorfall-API abrufen
description: Erfahren Sie, wie Sie die API zum Abrufen von Vorfällen verwenden, um einen einzelnen Vorfall in Microsoft 365 Defender abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Datei, Hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289607"
---
# <a name="get-incident-information-api"></a>Api zum Abrufen von Vorfallinformationen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung

Ruft einen bestimmten Vorfall anhand seiner ID ab.

## <a name="limitations"></a>Einschränkungen

1. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. 

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Incident.Read.All | "Alle Vorfälle lesen"
Anwendung | Incident.ReadWrite.All | "Alle Vorfälle lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.Read | "Vorfälle lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | "Vorfälle lesen und schreiben"

> [!NOTE]
>
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
> - Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".
> - Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.

## <a name="http-request"></a>HTTP-Anforderung

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {token}. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Empty

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden 200 OK und die Vorfallentität im Antworttext zurückgegeben. Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
