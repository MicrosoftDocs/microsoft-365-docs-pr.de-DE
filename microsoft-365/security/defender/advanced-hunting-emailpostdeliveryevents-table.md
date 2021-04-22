---
title: EmailPostDeliveryEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Aktionen nach der Zustellung für Microsoft 365-E-Mails finden Sie in der EmailPostDeliveryEvents-Tabelle des schemas für erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: 444af2441eef5a3720325656f996e6bcdb42937e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935473"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Aktionen nach der Zustellung, die für von `EmailPostDeliveryEvents` Microsoft 365 verarbeitete E-Mail-Nachrichten ergriffen werden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

Um weitere Informationen zu einzelnen E-Mail-Nachrichten zu erhalten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) , und die Tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) verwenden. Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutige ID für die von Microsoft 365 generierte E-Mail |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `Action` | string | Für die Entität ergriffene Aktion |
| `ActionType` | Zeichenfolge | Aktivitätstyp, der das Ereignis ausgelöst hat: Manuelle Korrektur, Phish ZAP, Schadsoftware-ZAP |
| `ActionTrigger` | Zeichenfolge | Gibt an, ob eine Aktion von einem Administrator ausgelöst wurde (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus, z. B. eine ZAP oder dynamische Zustellung |
| `ActionResult` | Zeichenfolge | Ergebnis der Aktion |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `DeliveryLocation` | string | Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente" |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |

## <a name="supported-event-types"></a>Unterstützte Ereignistypen
Diese Tabelle erfasst Ereignisse mit den folgenden `ActionType` Werten:

- **Manuelle Korrektur:** Ein Administrator hat manuell Eine E-Mail-Nachricht nach der Zugestellten an das Benutzerpostfach aktiviert. Dazu gehören Aktionen, die manuell über [den Bedrohungs-Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen von automatisierten Untersuchungs- und Reaktionsaktionen [(AIR) ergriffen werden.](m365d-autoir-actions.md)
- **Phish ZAP** – Die automatische Reinigung [(Zero-Hour Auto Purge, ZAP)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung Eine Phishing-E-Mail verwendet.
- **Schadsoftware ZAP** – Die automatische Reinigung (Zero-Hour Auto Purge, ZAP) hat eine E-Mail-Nachricht nach der Zustellung mit Schadsoftware gefunden.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
