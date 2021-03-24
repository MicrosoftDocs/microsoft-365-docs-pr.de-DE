---
title: AppFileEvents-Tabelle im schema für die erweiterte Suche
description: Informationen zu dateibezogenen Ereignissen im Zusammenhang mit Cloud-Apps und -Diensten finden Sie in der AppFileEvents-Tabelle des schemas für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AppFileEvents, Cloud App Security, MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063600"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu dateibezogenen Aktivitäten in Cloud-Apps und -Diensten, die von `AppFileEvents` Microsoft Cloud App Security überwacht werden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!WARNING]
>Diese Tabelle wird in Kürze eingestellt. Ab dem 7. März 2021 protokolliert die `AppFileEvents` Tabelle keine Datensätze mehr. Benutzer, die dateibezogene Aktivitäten in Clouddiensten am und über das datum hinausgehen, sollten stattdessen die [CloudAppEvents-Tabelle](advanced-hunting-cloudappevents-table.md) verwenden. <br><br>Achten Sie darauf, nach Abfragen und benutzerdefinierten Erkennungsregeln zu suchen, die weiterhin die Tabelle verwenden, und bearbeiten Sie `AppFileEvents` sie, um die Tabelle zu `CloudAppEvents` verwenden. Weitere Anleitungen zum Konvertieren betroffener Abfragen finden Sie unter [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde |
| `PreviousFileName` | Zeichenfolge | Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde |
| `PreviousFolderPath` | Zeichenfolge | Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde |
| `Protocol` | Zeichenfolge | Verwendetes Netzwerkprotokoll |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `AccountObjectId` | Zeichenfolge | Eindeutige ID für das Konto in Azure AD |
| `AccountDisplayName` | Zeichenfolge | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `DeviceType` | Zeichenfolge | Gerätetyp | 
| `OSPlatform` | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `Port` | Zeichenfolge | WÄHREND der Kommunikation verwendeter TCP-Port  |
| `DestinationDeviceName` | Zeichenfolge | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | Zeichenfolge | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | Zeichenfolge | Zielport der zugehörigen Netzwerkkommunikation |
| `Location` | Zeichenfolge | Stadt, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `Isp` | Zeichenfolge | Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
