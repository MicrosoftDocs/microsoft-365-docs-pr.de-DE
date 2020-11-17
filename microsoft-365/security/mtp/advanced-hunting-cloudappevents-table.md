---
title: CloudAppEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Ereignissen in Cloud-apps und-Diensten in der CloudAppEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud-App-Sicherheit, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087766"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Derzeit in der Vorschau verfügbar, `CloudAppEvents` enthält die Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schemainformationen zu Aktivitäten in verschiedenen Cloud-apps und-Diensten, insbesondere Microsoft Teams und Exchange Online. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Diese Tabelle wird erweitert, um weitere Aktivitäten einzubeziehen, die von Microsoft Cloud App Security überwacht werden. Schließlich enthält diese Tabelle die Dateiaktivität, die derzeit in der [AppFileEvents](advanced-hunting-appfileevents-table.md) -Tabelle gespeichert ist. Microsoft stellt zusätzliche Anleitungen bereit, wenn mehr Daten in diese Tabelle verschoben werden.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ApplicationId` | string | Eindeutiger Bezeichner für die Anwendung |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure Active Directory |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `IsAdminOperation` | string | Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde. |
| `DeviceType` | string | Gerätetyp basierend auf Zweck und Funktionalität, wie "Netzwerkgerät", "Workstation", "Server", "Mobil", "Spielekonsole" oder "Drucker" | 
| `OSPlatform` | string | Plattform des auf dem Gerät ausgeführten Betriebssystems. Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie wie Windows 10 und Windows 7. |
| `IPAddress` | string | Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet |
| `IsAnonymousProxy` | string | Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört. |
| `CountryCode` | string | Code mit zwei Buchstaben, der das Land angibt, in dem sich die IP-Adresse des Clients befindet |
| `City` | string | Ort, an dem die IP-Adresse des Clients geolokalisiert ist |
| `Isp` | string | Internet Dienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist |
| `UserAgent` | string | Informationen zum Benutzer-Agent über den Webbrowser oder eine andere Clientanwendung |
| `ActivityType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `ActivityObjects` | string | Liste der Objekte, wie Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren |
| `ObjectName` | string | Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ObjectType` | string | Typ des Objekts (beispielsweise eine Datei oder ein Ordner), auf das die aufgezeichnete Aktion angewendet wurde |
| `ObjectId` | string | Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde |
| `ReportId` | string | Eindeutiger Bezeichner für das Ereignis |
| `RawEventData` | string | Rohdaten von Ereignisinformationen aus der Quellanwendung oder dem Dienst im JSON-Format |
| `AdditionalFields` | string | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
