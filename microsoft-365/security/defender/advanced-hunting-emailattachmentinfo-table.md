---
title: Tabelle "EmailAttachmentInfo" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die in der Tabelle "EmailAttachmentInfo" des Schemas "Erweiterte Suche" enthaltenen Informationen zu Anlagen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware verdict
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 43e861d43e6e98f1e17d737f431bb72c42f3f4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065920"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Anlagen in E-Mails, die von `EmailAttachmentInfo` Microsoft Defender für Office 365 verarbeitet wurden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutige ID für die von Microsoft 365 generierte E-Mail |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
| `SenderDisplayName` | string | Name des absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem vor- oder vornamen, einer mittleren Initiale und einem Nachnamen oder Nachnamen |
| `SenderObjectId` | Zeichenfolge | Eindeutige ID für das Konto des Absenders in Azure AD |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `RecipientObjectId` | string | Eindeutige ID für den E-Mail-Empfänger in Azure AD |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileType` | string | Dateierweiterungstyp |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `ThreatTypes` | string | Bestimmen Sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält. |
| `ThreatNames` | Zeichenfolge | Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| `DetectionMethods` | Zeichenfolge | Methoden zum Erkennen von Schadsoftware, Phishing oder anderen In der E-Mail gefundenen Bedrohungen |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
