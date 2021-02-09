---
title: Tabelle "EmailAttachmentInfo" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die in der Tabelle "EmailAttachmentInfo" des Schemas "Erweiterte Suche" enthaltenen Informationen zu Anlagen.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailAttachmentInfo, Netzwerk-Nachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Schadsoftware-Bewert
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145019"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Anlagen in E-Mails, die von `EmailAttachmentInfo` Microsoft Defender für Office 365 verarbeitet wurden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die E-Mail, generiert von Microsoft 365 |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
| `SenderDisplayName` | string | Name des Absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem Vor- oder Vornamen, einem Vornamen und einem Nachnamen oder Nachnamen |
| `SenderObjectId` | string | Eindeutige ID für das Konto des Absenders in Azure AD |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `RecipientObjectId` | string | Eindeutige ID für den E-Mail-Empfänger in Azure AD |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileType` | string | Dateierweiterungstyp |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MalwareFilterVerdict` | string | Bewertung des E-Mail-Filterstapels, ob die E-Mail Schadsoftware enthält: Schadsoftware, keine Schadsoftware |
| `MalwareDetectionMethod` | string | Methode zum Erkennen von Schadsoftware in der E-Mail: Antischalwaremodul, Dateire reputation, sichere Anlagen |
| `ThreatTypes` | string | Überprüfen sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält. |
| `ThreatNames` | string | Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| `DetectionMethods` | string | Methoden zum Erkennen von Schadsoftware, Phishing oder anderen Bedrohungen, die in der E-Mail gefunden werden |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
