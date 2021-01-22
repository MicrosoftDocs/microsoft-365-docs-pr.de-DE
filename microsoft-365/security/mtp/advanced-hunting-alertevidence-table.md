---
title: Tabelle "AlertEvidence" im Schema "Erweiterte Suche"
description: Informationen zu Warnungen in der Tabelle "AlertEvidence" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932304"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte – die Warnungen von `AlertEvidence` Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity zugeordnet sind. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `ServiceSource` | string | Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat |
| `EntityType` | string | Objekttyp, z. B. eine Datei, ein Prozess, ein Gerät oder ein Benutzer |
| `EvidenceRole` | string | Wie die Entität an einer Warnung beteiligt ist, die angibt, ob sie betroffen ist oder lediglich in Beziehung steht |
| `EvidenceDirection` | string | Gibt an, ob die Entität die Quelle oder das Ziel einer Netzwerkverbindung ist. |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld ist in der Regel nicht aufgefüllt– verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `FileSize` | int | Größe der Datei in Byte |
| `ThreatFamily` | string | Schadsoftwarefamilie, unter der die verdächtige oder schädliche Datei oder der Prozess klassifiziert wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutige ID für das Konto in Azure Active Directory |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `LocalIP` | string | DIE IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Office 365 generierte E-Mail |
| `EmailSubject` | string | Betreff der E-Mail |
| `ApplicationId` | string | Eindeutiger Bezeichner für die Anwendung |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ProcessCommandLine` | string | Befehlszeile zum Erstellen des neuen Prozesses |
| `AdditionalFields` | string | Zusätzliche Informationen zu dem Ereignis im JSON-Array-Format |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
