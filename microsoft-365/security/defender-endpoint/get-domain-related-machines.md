---
title: Abrufen der DOMÄNENbezogenen Computer-API
description: Erfahren Sie, wie Sie die API "Domänenbezogene Computer abrufen" verwenden, um Computer zu erhalten, die mit oder von einer Domäne in Microsoft Defender for Endpoint kommuniziert haben.
keywords: apis, graph api, supported apis, get, domain, related, devices
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166578"
---
# <a name="get-domain-related-machines-api"></a>Abrufen der DOMÄNENbezogenen Computer-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Ruft eine Sammlung von Computern [ab,](machine.md) die mit oder von einer bestimmten Domänenadresse kommuniziert haben.


## <a name="limitations"></a>Einschränkungen
1. Sie können auf Geräten abfragen, die zuletzt entsprechend Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.
2. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Machine.Read.All |  "Alle Computerprofile lesen"
Anwendung |   Machine.ReadWrite.All | "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.Read | "Computerinformationen lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Computerinformationen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)
>- Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen zugreifen kann (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).

## <a name="http-request"></a>HTTP-Anforderung
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich und Domäne vorhanden ist – 200 OK mit Liste der [Computerentitäten.](machine.md) Wenn domäne nicht vorhanden ist - 404 Nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
