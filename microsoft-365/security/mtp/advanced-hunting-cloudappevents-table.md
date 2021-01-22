---
title: Tabelle "CloudAppEvents" im Schema "Erweiterte Suche"
description: Informationen zu Ereignissen von Cloud-Apps und -Diensten in der Tabelle "CloudAppEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928453"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Derzeit in der Vorschau verfügbar, enthält die Tabelle im Schema für die erweiterte Suche Informationen zu Aktivitäten in verschiedenen Cloud-Apps und -Diensten, insbesondere `CloudAppEvents` Microsoft Teams und Exchange Online. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Diese Tabelle wird erweitert, um weitere Aktivitäten zu enthalten, die von Microsoft Cloud App Security überwacht werden. Schließlich enthält diese Tabelle Dateiaktivität, die derzeit in der Tabelle ["AppFileEvents" gespeichert](advanced-hunting-appfileevents-table.md) ist. Microsoft stellt zusätzliche Anleitungen zur Verfügung, wenn mehr Daten zu dieser Tabelle bewegt werden.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Aktivitätstyp, der das Ereignis ausgelöst hat |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ApplicationId` | string | Eindeutiger Bezeichner für die Anwendung |
| `AccountObjectId` | string | Eindeutige ID für das Konto in Azure Active Directory |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `IsAdminOperation` | string | Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde |
| `DeviceType` | string | Gerätetyp basierend auf Zweck und Funktionalität, z. B. "Netzwerkgerät", "Arbeitsstation", "Server", "Mobil", "Spielekonsole" oder "Drucker" | 
| `OSPlatform` | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `IsAnonymousProxy` | string | Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört |
| `CountryCode` | string | Aus zwei Buchstaben bestehter Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist |
| `City` | string | Ort, in dem die Client-IP-Adresse geolokaliert ist |
| `Isp` | string | Internetdienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist |
| `UserAgent` | string | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung |
| `ActivityType` | string | Aktivitätstyp, der das Ereignis ausgelöst hat |
| `ActivityObjects` | string | Liste der Objekte, z. B. Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren |
| `ObjectName` | string | Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ObjectType` | string | Objekttyp, z. B. eine Datei oder ein Ordner, auf den die aufgezeichnete Aktion angewendet wurde |
| `ObjectId` | string | Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ReportId` | string | Eindeutiger Bezeichner für das Ereignis |
| `RawEventData` | string | Unformatierte Ereignisinformationen aus der Quellanwendung oder dem Quelldienst im JSON-Format |
| `AdditionalFields` | string | Zusätzliche Informationen über die Entität oder das Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
