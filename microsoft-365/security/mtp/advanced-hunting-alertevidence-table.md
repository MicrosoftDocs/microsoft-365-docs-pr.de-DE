---
title: AlertEvidence-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Datei-, Netzwerkadresse, Benutzer-oder Geräteinformationen, die mit generierten Warnungen in der AlertEvidence-Tabelle des Advanced Hunting-Schemas verknüpft sind.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649511"
---
# <a name="alertevidence"></a>AlertEvidence

**Gilt für:**
- Microsoft Threat Protection

Die `AlertEvidence` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte –, die Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP zugeordnet sind. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `EntityType` | string | Objekttyp, beispielsweise eine Datei, ein Prozess, ein Gerät oder ein Benutzer |
| `EvidenceRole` | string | Wie die Entität an einer Warnung beteiligt ist und angibt, ob Sie betroffen ist oder lediglich mit ihr zusammenhängen soll |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `ThreatFamily` | string | Schadsoftware-Familie, unter der die verdächtige oder böswillige Datei oder der Prozess klassifiziert wurde |
| `EvidenceDirection` | string | Gibt an, ob es sich bei der Entität um die Quelle oder das Ziel einer Netzwerkverbindung handelt. |
| `AdditionalFields` | string | Weitere Informationen zum Ereignis im JSON-Array Format |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Jagd auf Geräte, e-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
