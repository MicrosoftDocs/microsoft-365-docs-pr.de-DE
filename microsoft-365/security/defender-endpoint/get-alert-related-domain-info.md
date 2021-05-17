---
title: Erhalten von Informationen zu Benachrichtigungen zu Domänen
description: Rufen Sie alle Domänen im Zusammenhang mit einer bestimmten Warnung mithilfe von Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get alert information, alert information, related domain
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200413"
---
# <a name="get-alert-related-domain-information-api"></a>Abrufen der Benachrichtigungsdomäneninformations-API

**Gilt für:** 
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Ruft alle Domänen im Zusammenhang mit einer bestimmten Warnung ab.


## <a name="limitations"></a>Einschränkungen
1. Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.
2. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | URL. Read.All | 'UrLs lesen'
Delegiert (Geschäfts-, Schul- oder Unikonto) | URL. Read.All | 'UrLs lesen'

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)
>- Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich und Warnung und Domäne vorhanden sind – 200 OK. Wenn die Warnung nicht gefunden wurde – 404 Nicht gefunden.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
