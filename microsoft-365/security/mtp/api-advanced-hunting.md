---
title: Microsoft 365 Defender Advanced Hunting API
description: Hier erfahren Sie, wie Sie erweiterte Jagd Abfragen mit der erweiterten Jagd-API von Microsoft 365 Defender ausführen können.
keywords: Erweiterte Suche, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719380"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced Hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

[Advanced Hunting](advanced-hunting-overview.md) ist ein Tool zur Gefahren Suche, das [speziell konstruierte Abfragen](advanced-hunting-query-language.md) verwendet, um die letzten 30 Tage der Ereignisdaten in Microsoft 365 Defender zu untersuchen. Sie können erweiterte Jagd Abfragen verwenden, um ungewöhnliche Aktivitäten zu prüfen, mögliche Bedrohungen zu erkennen und sogar auf Angriffe zu reagieren. Die erweiterte Jagd-API ermöglicht das Programmgesteuertes von Abfrageereignis Daten.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuteilung

Die folgenden Bedingungen beziehen sich auf alle Abfragen.

1. Abfragen erforschen und Zurückgeben von Daten aus den letzten 30 Tagen.
2. Ergebnisse können bis zu 100.000 Zeilen zurückgeben.
3. Sie können bis zu 10 Anrufe pro Minute pro Mandant vornehmen.
4. Sie haben 10 Minuten Spielzeit pro Stunde pro Mandant.
5. Sie verfügen über vier Gesamtstunden des laufenden Zeit Tages pro Mandant.
6. Wenn eine einzelne Anforderung länger als 10 Minuten ausgeführt wird, tritt ein Timeout auf, und es wird ein Fehler zurückgegeben.
7. Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen Laufzeit. Der Antworttext enthält die Zeit, bis das von Ihnen erreichte Kontingent zurückgesetzt wird.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um die erweiterte Jagd-API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender Protection APIs](api-access.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | AdvancedHunting. Read. all | Ausführen erweiterter Abfragen
Delegiert (Geschäfts-, Schul- oder Unikonto) | AdvancedHunting. Read | Ausführen erweiterter Abfragen

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.
>- Der Benutzer muss auf dem Gerät basierend auf Gerätegruppen Einstellungen Zugriff haben.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert
-|-
Authorization | Bearer {Token} **Hinweis: erforderlich**
Content-Type | application/json

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter | Typ | Beschreibung
-|-|-
Abfrage | Text | Die auszuführende Abfrage. **Hinweis: erforderlich**

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich verläuft, gibt Sie `200 OK` ein _QueryResponse_ -Objekt im Antworttext zurück.

Das Response-Objekt enthält drei Eigenschaften der obersten Ebene:

1. Stats-ein Wörterbuch der Abfrage Leistungsstatistik.
2. Schema – das Schema der Antwort, eine Liste mit Name-Type-Paaren für jede Spalte.
3. Ergebnisse – eine Liste erweiterter Jagd Ereignisse.

## <a name="example"></a>Beispiel

Im folgenden Beispiel sendet ein Benutzer die Abfrage unten und empfängt ein API-Antwortobjekt mit `Stats` , `Schema` und `Results` .

### <a name="query"></a>Abfrage

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response-Objekt

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

## <a name="related-articles"></a>Verwandte Artikel

- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
