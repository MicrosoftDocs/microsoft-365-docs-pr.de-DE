---
title: Erweiterte Jagd-APIs
description: Informationen zum Ausführen erweiterter Suchabfragen mithilfe der Microsoft Threat Protection-API
keywords: Erweiterte Suche, APIs, API, MTP
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
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197809"
---
# <a name="advanced-hunting-apis"></a>Erweiterte Jagd-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="limitations"></a>Einschränkungen
1. Sie können nur eine Abfrage für Daten der letzten 30 Tage ausführen.
2. Die Ergebnisse umfassen maximal 100.000 Zeilen.
3. Die Anzahl der Ausführungen ist pro Mandanten limitiert: bis zu 10 Anrufe pro Minute, 10 Minuten Spielzeit stündlich und 4 Stunden Spielzeit pro Tag.
4. Die maximale Ausführungszeit einer einzelnen Anforderung beträgt 10 Minuten.
5. 429 Antwort stellt eine erreichende Kontingentgrenze nach der Anzahl der Anforderungen oder der CPU dar. Der 429-Antworttext gibt auch die Zeit an, bis das Kontingent erneuert wird. 


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [zugreifen auf die Microsoft Threat Protection-APIs](api-access.md) .

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   AdvancedHunting. Read. all |  ' Erweiterte Abfragen ausführen '
Delegiert (Geschäfts-, Schul- oder Unikonto) | AdvancedHunting. Read | ' Erweiterte Abfragen ausführen '

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.
>- Der Benutzer muss auf dem Gerät basierend auf Gerätegruppen Einstellungen Zugriff haben.

## <a name="http-request"></a>HTTP-Anforderung
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert 
:---|:---
Authorization | Bearer {Token}. **Erforderlich**.
Content-Type    | application/json

## <a name="request-body"></a>Anforderungstext
Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter | Typ    | Beschreibung
:---|:---|:---
Abfrage | Text |  Die auszuführende Abfrage. **Erforderlich**.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich verläuft, werden 200 OK und das _QueryResponse_ -Objekt im Antworttext zurückgegeben. <br><br>

Das Response-Objekt wird in drei Teile (Eigenschaften) aufgeteilt:<br>
1) ```Stats``` -Abfrage Leistungsstatistiken.<br>
2) ```Schema``` – Das Schema der Antwort, eine Liste von Name-Typ-Paaren für jede Spalte. <br>
3) ```Results``` -Eine Liste erweiterter Jagd Ereignisse.

## <a name="example"></a>Beispiel

Anforderung

Nachfolgend sehen Sie ein Beispiel der Anforderung.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Antwort

Nachfolgend sehen Sie ein Beispiel der Antwort.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Verwandtes Thema
- [Zugreifen auf die Microsoft Threat Protection-APIs](api-access.md)
