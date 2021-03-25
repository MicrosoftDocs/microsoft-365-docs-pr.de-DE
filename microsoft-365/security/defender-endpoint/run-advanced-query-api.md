---
title: Erweiterte Suche-API
ms.reviewer: ''
description: Erfahren Sie, wie Sie die erweiterte Such-API verwenden, um erweiterte Abfragen auf Microsoft Defender for Endpoint ausführen zu können. Erfahren Sie mehr über Einschränkungen, und sehen Sie sich ein Beispiel an.
keywords: apis, supported apis, advanced hunting, query
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
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200197"
---
# <a name="advanced-hunting-api"></a>Erweiterte Api für die Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Einschränkungen
1. Sie können nur eine Abfrage für Daten aus den letzten 30 Tagen ausführen.
2. Die Ergebnisse enthalten maximal 100.000 Zeilen.
3. Die Anzahl der Ausführungen ist pro Mandant begrenzt:
   - API-Aufrufe: Bis zu 45 Anrufe pro Minute.
   - Ausführungszeit: 10 Minuten Laufzeit pro Stunde und 3 Stunden Laufzeit pro Tag.
4. Die maximale Ausführungszeit einer einzelnen Anforderung beträgt 10 Minuten.
5. 429-Antwort stellt das Erreichen des Kontingentgrenzwerts entweder nach Anzahl der Anforderungen oder nach CPU dar. Lesen Sie den Antworttext, um zu verstehen, welcher Grenzwert erreicht wurde. 

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   AdvancedQuery.Read.All |    "Ausführen erweiterter Abfragen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | AdvancedQuery.Read | "Ausführen erweiterter Abfragen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).

## <a name="http-request"></a>HTTP-Anforderung
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert 
:---|:---
Authorization | Bearer {token}. **Erforderlich**.
Content-Type    | application/json

## <a name="request-body"></a>Anforderungstext
Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter | Typ    | Beschreibung
:---|:---|:---
Abfrage | Text |  Die abfrage, die ausgeführt werden soll. **Erforderlich**.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und _das QueryResponse-Objekt_ im Antworttext zurückgegeben.


## <a name="example"></a>Beispiel

Anforderung

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

Antwort

Nachfolgend sehen Sie ein Beispiel der Antwort.

>[!NOTE]
>Das hier gezeigte Antwortobjekt kann aus Kürze gekürzt werden. Von einem tatsächlichen Aufruf werden alle Eigenschaften zurückgegeben.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a>Verwandtes Thema
- [Einführung in Microsoft Defender for Endpoint-APIs](apis-intro.md)
- [Erweiterte Suche im Portal](advanced-hunting-query-language.md)
- [Erweiterte Suche mit PowerShell](run-advanced-query-sample-powershell.md)
