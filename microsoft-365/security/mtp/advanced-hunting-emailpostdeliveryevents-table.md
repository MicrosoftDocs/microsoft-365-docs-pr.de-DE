---
title: EmailPostDeliveryEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Post Zustellungs Aktionen, die in Microsoft 365-e-Mails in der EmailPostDeliveryEvents-Tabelle des Advanced Hunting-Schemas ausgeführt wurden
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailPostDeliveryEvents, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Schadsoftware, Phishing-Urteil, ANLAGENANZAHL, Link Anzahl, URL-Anzahl
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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198013"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `EmailPostDeliveryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Post Zustellungs Aktionen für e-Mail-Nachrichten, die von Microsoft 365 verarbeitet wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.

Wenn Sie weitere Informationen zu einzelnen e-Mail-Nachrichten erhalten möchten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) Tabellen verwenden [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `EventId` | string | Eindeutiger Bezeichner für das Ereignis |
| `NetworkMessageId` | Zeichenfolge | Eindeutiger Bezeichner für die von Microsoft 365 generierte e-Mail |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `Action` | string | Für die Entität ausgeführte Aktion |
| `ActionType` | Zeichenfolge | Typ der Aktivität, die das Ereignis ausgelöst hat: manuelle Korrektur, Phishing-zap, Malware-zap |
| `ActionTrigger` | Zeichenfolge | Gibt an, ob eine Aktion von einem Administrator (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus wie zap oder dynamische Zustellung ausgelöst wurde. |
| `ActionResult` | Zeichenfolge | Ergebnis der Aktion |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `DeliveryLocation` | string | Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente" |

## <a name="supported-event-types"></a>Unterstützte Ereignistypen
In dieser Tabelle werden Ereignisse mit den folgenden `ActionType` Werten erfasst:

- **Manuelle Korrektur** : ein Administrator hat manuell eine Aktion für eine e-Mail-Nachricht durchgeführt, nachdem er an das Benutzerpostfach übermittelt wurde. Dies umfasst Aktionen, die manuell über den [Threat Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen für [automatisierte Ermittlungs-und Antwort Aktionen (Air)](mtp-autoir-actions.md)ausgeführt werden.
- **Phishing zap** – [Zero-Hour Auto Purge (zap)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung Aktionen für eine Phishing-e-Mail durchgeführt.
- **Malware zap** – Zero-Hour Auto Purge (zap) hat eine Aktion für eine e-Mail-Nachricht gefunden, die Schadsoftware nach der Zustellung enthält.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
