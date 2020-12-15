---
title: Tabelle "EmailAttachmentInfo" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die in der Tabelle "EmailAttachmentInfo" des Schemas "Erweiterte Suche" enthaltenen Informationen zu Anlagen.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailAttachmentInfo, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Schadsoftware-Urteil
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6d88303b34f78abc857e9aec749bf2f58090f43a
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667649"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die `EmailAttachmentInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Anlagen in e-Mails, die von Microsoft Defender für Office 365 verarbeitet wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AttachmentId` | string | Eindeutiger Bezeichner für die E-Mail-Anlage |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Microsoft 365 generierte e-Mail |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileType` | string | Dateierweiterungstyp |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MalwareFilterVerdict` | string | Bewertung des E-Mail-Filterstapels, ob die E-Mail Schadsoftware enthält: Schadsoftware, keine Schadsoftware |
| `MalwareDetectionMethod` | string | Methode zum Erkennen von Schadsoftware in der e-Mail: Antischadsoftware-Modul, Datei Zuverlässigkeit, sichere Anlagen |
| `SenderDisplayName` | Zeichenfolge | Name des Absenders, der im Adressbuch angezeigt wird, normalerweise eine Kombination aus einem bestimmten oder Vornamen, einer mittleren Initiale und einem Nachnamen oder Familiennamen |
| `SenderObjectId` | Zeichenfolge | Eindeutiger Bezeichner für das Konto des Absenders in Azure AD |
| `ThreatTypes` | Zeichenfolge | Urteil aus dem e-Mail-Filter Stapel, ob die e-Mail Malware, Phishing oder andere Bedrohungen enthält |
| `ThreatNames` | Zeichenfolge | Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
