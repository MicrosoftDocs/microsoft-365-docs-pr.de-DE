---
title: DeviceTvmSoftwareInventory-Tabelle im schema der erweiterten Suche
description: Informationen zum Inventar der Software auf Ihren Geräten finden Sie in der DeviceTvmSoftwareInventory-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 4d3aa317e3013e6fe8452bfbfd759bc1f003cd6f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065928"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


Die Tabelle im Schema für die erweiterte Suche enthält das Inventar & Threat & Vulnerability Management der software, die derzeit auf Geräten in Ihrem Netzwerk installiert ist, einschließlich Der Ende `DeviceTvmSoftwareInventory` der Supportinformationen. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Sie können z. B. nach Ereignissen suchen, die Geräte enthalten, die mit einer derzeit anfälligen Softwareversion installiert sind. Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

>[!NOTE]
> The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table. Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Vulnerablität zu informieren oder nach anfälligen Geräten zu fahnen.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `OSVersion` | string | Die Version des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `OSArchitecture` | string | Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `SoftwareVendor` | string | Name des Softwareanbieters |
| `SoftwareName` | string | Name des Softwareprodukts |
| `SoftwareVersion` | string | Versionsnummer des Softwareprodukts |
| `EndOfSupportStatus` | string | Gibt die Lebenszyklusphase des Softwareprodukts relativ zum angegebenen End-of-Support (EOS) oder End-of-Life (EOL)-Datum an. |
| `EndOfSupportDate` | Zeichenfolge | End-of-Support (EOS) oder End-of-Life (EOL) des Softwareprodukts |



## <a name="related-topics"></a>Verwandte Themen

- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
