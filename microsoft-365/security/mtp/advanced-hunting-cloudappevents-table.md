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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712486"
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
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ApplicationId` | string | Eindeutige ID für die Anwendung |
| `AccountObjectId` | string | Eindeutige ID für das Konto in Azure Active Directory |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `IsAdminOperation` | string | Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde |
| `DeviceType` | string | Gerätetyp basierend auf Zweck und Funktionalität, z. B. "Netzwerkgerät", "Workstation", "Server", "Mobile", "Spielekonsole" oder "Drucker" | 
| `OSPlatform` | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `IsAnonymousProxy` | string | Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört |
| `CountryCode` | string | Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist |
| `City` | string | Ort, in dem die Client-IP-Adresse geolokaliert ist |
| `Isp` | string | Internetdienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist |
| `UserAgent` | string | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung |
| `ActivityType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat |
| `ActivityObjects` | string | Liste der Objekte, z. B. Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren |
| `ObjectName` | string | Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ObjectType` | string | Objekttyp, z. B. eine Datei oder ein Ordner, auf den die aufgezeichnete Aktion angewendet wurde |
| `ObjectId` | string | Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ReportId` | string | Eindeutiger Bezeichner für das Ereignis |
| `RawEventData` | string | Unformatierte Ereignisinformationen aus der Quellanwendung oder dem Quelldienst im JSON-Format |
| `AdditionalFields` | string | Zusätzliche Informationen zur Entität oder zum Ereignis |


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
