---
title: Tabelle "EmailUrlInfo" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die URL- oder Linkinformationen in der Tabelle "EmailUrlInfo" des Schemas "Erweiterte Suche".
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailUrlInfo, Netzwerknachrichten-ID, URL, Link
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 46849aa81da5a615a5dff7c5e2ac28566443d3ee
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633519"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Gilt für:**
- Microsoft Threat Protection



Die Tabelle `EmailUrlInfo` im Schema [Erweiterte Suche](advanced-hunting-overview.md) enthält Informationen zu URLs in von Office 365 ATP verarbeiteten E-Mails und Anlagen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `UrlId` | string | Eindeutiger Bezeichner für die URL in der Betreffzeile, im Textkörper oder in der Anlage der E-Mail |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Microsoft 365 generierte e-Mail |
| `Url` | string | Vollständige URL in der Betreffzeile, im Textkörper oder in der Anlage der E-Mail |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
