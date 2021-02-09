---
title: Tabelle "EmailPostDeliveryEvents" im Schema "Erweiterte Suche"
description: Informationen zu Post-Delivery-Aktionen für Microsoft 365-E-Mails in der Tabelle "EmailPostDeliveryEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailPostDeliveryEvents, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Malware-Bewert, Phishing-Bewert, Anlagenanzahl, Linkanzahl, URL-Anzahl
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
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145499"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Aktionen nach der Zustellung, die für von `EmailPostDeliveryEvents` Microsoft 365 verarbeitete E-Mail-Nachrichten ergriffen werden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Um weitere Informationen zu einzelnen E-Mail-Nachrichten zu erhalten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) , und die Tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) verwenden. Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die E-Mail, generiert von Microsoft 365 |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `Action` | string | Für die Entität ergriffene Aktion |
| `ActionType` | string | Aktivitätstyp, der das Ereignis ausgelöst hat: Manuelle Wartung, Phish ZAP, Schadsoftware ZAP |
| `ActionTrigger` | string | Gibt an, ob eine Aktion von einem Administrator (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus ausgelöst wurde, z. B. eine ZAP- oder dynamische Übermittlung. |
| `ActionResult` | string | Ergebnis der Aktion |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `DeliveryLocation` | string | Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente" |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |

## <a name="supported-event-types"></a>Unterstützte Ereignistypen
In dieser Tabelle werden Ereignisse mit den folgenden Werten `ActionType` erfasst:

- **Manuelle Korrektur:** Ein Administrator hat manuell Aktionen für eine E-Mail-Nachricht nach derEn Zugestellt an das Benutzerpostfach ergreifen. Dazu gehören Aktionen, die manuell über [den Threat Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen von [automatisierten Untersuchungs- und Reaktionsaktionen (AIR) ergriffen werden.](mtp-autoir-actions.md)
- **Phish ZAP** – [Zap (Zero-hour Auto Purge)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung eine Aktion für eine Phishing-E-Mail-Nachricht ergreifen.
- **Schadsoftware ZAP** – Zap hat eine E-Mail-Nachricht, die nach der Zustellung Schadsoftware enthält, zur Nullstunde automatisch gelöscht.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
