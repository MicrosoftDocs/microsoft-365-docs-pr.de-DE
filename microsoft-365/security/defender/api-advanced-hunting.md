---
title: Microsoft 365 Defender advanced hunting API
description: Erfahren Sie, wie Sie erweiterte Suchabfragen mithilfe der erweiterten Such-API von Microsoft 365 Defender ausführen.
keywords: Erweiterte Suche, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066760"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

[Die erweiterte Suche](advanced-hunting-overview.md) ist ein Tool zur [Bedrohungssuche,](advanced-hunting-query-language.md) das speziell konstruierte Abfragen verwendet, um die letzten 30 Tage mit Ereignisdaten in Microsoft 365 Defender zu untersuchen. Sie können erweiterte Suchabfragen verwenden, um ungewöhnliche Aktivitäten zu untersuchen, mögliche Bedrohungen zu erkennen und sogar auf Angriffe zu reagieren. Mit der erweiterten Such-API können Sie Ereignisdaten programmgesteuert abfragen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuordnung

Die folgenden Bedingungen beziehen sich auf alle Abfragen.

1. Abfragen untersuchen und geben Daten aus den letzten 30 Tagen zurück.
2. Ergebnisse können bis zu 100.000 Zeilen zurückgeben.
3. Sie können bis zu 15 Anrufe pro Minute pro Mandant machen.
4. Sie haben 10 Minuten Laufzeit pro Stunde pro Mandant.
5. Sie haben vier Gesamtstunden Laufzeit pro Tag pro Mandant.
6. Wenn eine einzelne Anforderung länger als 10 Minuten ausgeführt wird, tritt ein Zeitfehler auf, und es wird ein Fehler zurückgegeben.
7. Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen `429` Laufzeit. Lesen Sie den Antworttext, um den grenzwert zu verstehen, den Sie erreicht haben. 

> [!NOTE]
> Alle oben aufgeführten Kontingente (z. B. 15 Anrufe pro Minute) sind pro Mandantengröße. Diese Kontingente sind das Minimum.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um die api für die erweiterte Suche aufrufen zu können. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender Protection APIs](api-access.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | AdvancedHunting.Read.All | Ausführen erweiterter Abfragen
Delegiert (Geschäfts-, Schul- oder Unikonto) | AdvancedHunting.Read | Ausführen erweiterter Abfragen

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer benötigt die AD-Rolle "Daten anzeigen"
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert
-|-
Authorization | Bearer {token} **Hinweis: erforderlich**
Content-Type | application/json

## <a name="request-body"></a>Anforderungstext

Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter | Typ | Beschreibung
-|-|-
Abfrage | Text | Die abfrage, die ausgeführt werden soll. **Hinweis: erforderlich**

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird `200 OK` ein _QueryResponse-Objekt_ im Antworttext zurückgegeben.

Das Antwortobjekt enthält drei Eigenschaften auf oberster Ebene:

1. Stats – Ein Wörterbuch mit Abfrageleistungsstatistiken.
2. Schema – Das Schema der Antwort, eine Liste der Name-Type für jede Spalte.
3. Ergebnisse – Eine Liste der erweiterten Jagdereignisse.

## <a name="example"></a>Beispiel

Im folgenden Beispiel sendet ein Benutzer die folgende Abfrage und empfängt ein API-Antwortobjekt mit `Stats` , `Schema` und `Results` .

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
- [Informationen zu API-Beschränkungen und -Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
