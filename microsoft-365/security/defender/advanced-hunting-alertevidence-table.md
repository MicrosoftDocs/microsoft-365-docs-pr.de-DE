---
title: AlertEvidence-Tabelle im schema der erweiterten Suche
description: Informationen zu Den Warnungen zugeordneten Informationen in der AlertEvidence-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: 7b1f581e1cfc8345df6e7b8053621cf46110c355
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499892"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu verschiedenen Entitäten ( Dateien, IP-Adressen, URLs, Benutzer oder Geräte), die Warnungen von `AlertEvidence` Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity zugeordnet sind. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `ServiceSource` | Zeichenfolge | Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat |
| `EntityType` | Zeichenfolge | Objekttyp, z. B. eine Datei, ein Prozess, ein Gerät oder ein Benutzer |
| `EvidenceRole` | Zeichenfolge | Wie die Entität an einer Warnung beteiligt ist, die angibt, ob sie betroffen ist oder nur im Zusammenhang steht |
| `EvidenceDirection` | Zeichenfolge | Gibt an, ob die Entität die Quelle oder das Ziel einer Netzwerkverbindung ist |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht aufgefüllt– verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `FileSize` | int | Größe der Datei in Bytes |
| `ThreatFamily` | Zeichenfolge | Schadsoftwarefamilie, unter der die verdächtige oder schädliche Datei oder der Prozess klassifiziert wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `AccountObjectId` | Zeichenfolge | Eindeutige ID für das Konto in Azure Active Directory |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `DeviceId` | Zeichenfolge | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `LocalIP` | string | IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Office 365 generierte E-Mail |
| `EmailSubject` | string | Betreff der E-Mail |
| `ApplicationId` | string | Eindeutige ID für die Anwendung |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ProcessCommandLine` | Zeichenfolge | Befehlszeile zum Erstellen des neuen Prozesses |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |
| `RegistryKey` |Zeichenfolge | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` |Zeichenfolge | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` |Zeichenfolge | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
