---
title: CloudAppEvents-Tabelle im schema der erweiterten Suche
description: Erfahren Sie mehr über Ereignisse aus Cloud-Apps und -Diensten in der CloudAppEvents-Tabelle des schemas für erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498676"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Aktivitäten in verschiedenen Cloud-Apps und -Diensten, die von Microsoft Cloud App Security abgedeckt werden, insbesondere `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams und SharePoint. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!IMPORTANT]
>Diese Tabelle enthält Informationen, die früher in der Tabelle verfügbar `AppFileEvents` waren. Ab dem 7. März 2021 sollten Benutzer, die dateibezogene Aktivitäten in Clouddiensten an und über dieses Datum hinaus durchsuchen, stattdessen die `CloudAppEvents` Tabelle verwenden. <br><br>Achten Sie darauf, nach Abfragen und benutzerdefinierten Erkennungsregeln zu suchen, die weiterhin die Tabelle verwenden, und bearbeiten Sie `AppFileEvents` sie, um die Tabelle zu `CloudAppEvents` verwenden. Weitere Anleitungen zum Konvertieren betroffener Abfragen finden Sie unter [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ApplicationId` | Zeichenfolge | Eindeutige ID für die Anwendung |
| `AccountObjectId` | Zeichenfolge | Eindeutige ID für das Konto in Azure Active Directory |
| `AccountDisplayName` | Zeichenfolge | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `IsAdminOperation` | Zeichenfolge | Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde |
| `DeviceType` | Zeichenfolge | Gerätetyp basierend auf Zweck und Funktionalität, z. B. "Netzwerkgerät", "Workstation", "Server", "Mobile", "Spielekonsole" oder "Drucker" | 
| `OSPlatform` | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7. |
| `IPAddress` | Zeichenfolge | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `IsAnonymousProxy` | Zeichenfolge | Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört |
| `CountryCode` | Zeichenfolge | Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist |
| `City` | Zeichenfolge | Ort, in dem die Client-IP-Adresse geolokaliert ist |
| `Isp` | Zeichenfolge | Internetdienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist |
| `UserAgent` | Zeichenfolge | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung |
| `ActivityType` | Zeichenfolge | Typ der Aktivität, die das Ereignis ausgelöst hat |
| `ActivityObjects` | Zeichenfolge | Liste der Objekte, z. B. Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren |
| `ObjectName` | Zeichenfolge | Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ObjectType` | Zeichenfolge | Objekttyp, z. B. eine Datei oder ein Ordner, auf den die aufgezeichnete Aktion angewendet wurde |
| `ObjectId` | Zeichenfolge | Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ReportId` | Zeichenfolge | Eindeutiger Bezeichner für das Ereignis |
| `RawEventData` | Zeichenfolge | Unformatierte Ereignisinformationen aus der Quellanwendung oder dem Quelldienst im JSON-Format |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
