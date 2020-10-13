---
title: AlertEvidence-Tabelle im Advanced Hunting-Schema
description: Informationen zu den Warnungen in der AlertEvidence-Tabelle des erweiterten Jagd Schemas finden Sie hier.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, alertinfo, Warnung, Entitäten, Evidence, File, IP-Adresse, Gerät, Computer, Benutzer, Konto
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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430163"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `AlertEvidence` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte –, die Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP zugeordnet sind. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `ServiceSource` | string | Produkt oder Dienst, der die Warnungsinformationen bereitgestellt hat |
| `EntityType` | string | Objekttyp, beispielsweise eine Datei, ein Prozess, ein Gerät oder ein Benutzer |
| `EvidenceRole` | string | Wie die Entität an einer Warnung beteiligt ist und angibt, ob Sie betroffen ist oder lediglich mit ihr zusammenhängen soll |
| `EvidenceDirection` | string | Gibt an, ob es sich bei der Entität um die Quelle oder das Ziel einer Netzwerkverbindung handelt. |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht aufgefüllt, wenn es verfügbar ist, verwenden Sie die SHA1-Spalte. |
| `FileSize` | int | Größe der Datei in Bytes |
| `ThreatFamily` | string | Schadsoftware-Familie, unter der die verdächtige oder böswillige Datei oder der Prozess klassifiziert wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure Active Directory |
| `DeviceId` | string | Eindeutiger Bezeichner für das Gerät im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `LocalIP` | string | IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Office 365 generierte E-Mail |
| `EmailSubject` | string | Betreff der E-Mail |
| `ApplicationId` | string | Eindeutiger Bezeichner für die Anwendung |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ProcessCommandLine` | string | Befehlszeile, die zum Erstellen des neuen Prozesses verwendet wird |
| `AdditionalFields` | string | Weitere Informationen zum Ereignis im JSON-Array Format |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
