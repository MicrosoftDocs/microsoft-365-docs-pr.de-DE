---
title: Erweiterte Suche-API
ms.reviewer: ''
description: Erfahren Sie, wie Sie die API für die erweiterte Suche verwenden, um erweiterte Abfragen auf Microsoft Defender für Endpunkt auszuführen. Informieren Sie sich über Einschränkungen, und sehen Sie sich ein Beispiel an.
keywords: APIs, unterstützte APIs, erweiterte Suche, Abfrage
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
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772401"
---
# <a name="advanced-hunting-api"></a>API für die erweiterte Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Begrenzungen

1. Sie können nur eine Abfrage für Daten aus den letzten 30 Tagen ausführen.

2. Die Ergebnisse umfassen maximal 100.000 Zeilen.

3. Die Anzahl der Ausführungen ist pro Mandant begrenzt:
   - API-Aufrufe: bis zu 45 Aufrufe pro Minute, bis zu 1500 Aufrufe pro Stunde.
   - Ausführungszeit: 10 Minuten Laufzeit pro Stunde und 3 Stunden Laufzeit pro Tag.

4. Die maximale Ausführungszeit einer einzelnen Anforderung beträgt 10 Minuten.

5. 429-Antworten stellen das Erreichen des Kontingentlimits entweder nach Anzahl der Anforderungen oder nach CPU dar. Lesen Sie den Antworttext, um zu verstehen, welcher Grenzwert erreicht wurde. 

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   AdvancedQuery.Read.All |    "Ausführen erweiterter Abfragen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | AdvancedQuery.Read | "Ausführen erweiterter Abfragen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert 
:---|:---
Authorization | Bearer {token}. **Erforderlich**.
Content-Type    | application/json

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter | Typ    | Beschreibung
:---|:---|:---
Abfrage | Text |  Die auszuführende Abfrage. **Erforderlich**.

## <a name="response"></a>Antwort

Bei erfolgreicher Ausführung gibt die Methode das Objekt 200 OK und das _QueryResponse-Objekt_ im Antworttext zurück.


## <a name="example"></a>Beispiel

##### <a name="request"></a>Anforderung

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

##### <a name="response"></a>Antwort

Nachfolgend sehen Sie ein Beispiel der Antwort.

>[!NOTE]
>Das hier gezeigte Antwortobjekt ist möglicherweise aus Platzgründen abgeschnitten. Von einem tatsächlichen Aufruf werden alle Eigenschaften zurückgegeben.

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

## <a name="related-topics"></a>Verwandte Themen

- [Einführung in microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche über das Portal](advanced-hunting-query-language.md)
- [Erweiterte Bedrohungssuche mit PowerShell](run-advanced-query-sample-powershell.md)
