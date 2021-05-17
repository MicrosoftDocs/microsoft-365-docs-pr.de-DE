---
title: Tabelle "EmailEvents" im Schema "Erweiterte Suche"
description: Informationen zu Ereignissen, die Microsoft 365 E-Mails zugeordnet sind, finden Sie in der EmailEvents-Tabelle des erweiterten Jagdschemas.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: 18d3d768b672364f730b042239ae9fa0042f95f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935485"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Ereignissen, die die Verarbeitung von E-Mails `EmailEvents` auf Microsoft Defender for Office 365. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutige ID für die E-Mail, generiert von Microsoft 365 |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `SenderMailFromAddress` | string | Absender-E-Mail-Adresse in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
| `SenderDisplayName` | string | Name des absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem vor- oder vornamen, einer mittleren Initiale und einem Nachnamen oder Nachnamen |
| `SenderObjectId` | Zeichenfolge |Eindeutige ID für das Konto des Absenders in Azure AD |
| `SenderMailFromDomain` | string | Absender-Domäne in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromDomain` | string | Absender-Domäne in der Kopfzeile "FROM", die für E-Mail-Empfänger in ihren E-Mail-Clients sichtbar ist |
| `SenderIPv4` | string | Die IPv4-Adresse des letzten feststellbaren E-Mail-Servers, der die Nachricht weitergeleitet hat |
| `SenderIPv6` | string | Die IPv6-Adresse des letzten feststellbaren E-Mail-Servers, der die Nachricht weitergeleitet hat |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `RecipientObjectId` | string | Eindeutige ID für den E-Mail-Empfänger in Azure AD |
| `Subject` | string | Betreff der E-Mail |
| `EmailClusterId` | string | Bezeichner für die Gruppe von ähnlichen E-Mail-Nachrichten, die auf Basis der heuristischen Analyse ihrer Inhalte gruppiert sind |
| `EmailDirection` | string | Richtung der E-Mail in Bezug auf Ihr Netzwerk: eingehend, ausgehend, Intern |
| `DeliveryAction` | string | Zustellungsaktion der E-Mail: übermittelt, als Junk eingestuft, blockiert oder ersetzt |
| `DeliveryLocation` | string | Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente" |
| `ThreatTypes` | string | Bestimmen Sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält. |
| `ThreatNames` | Zeichenfolge |Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| `DetectionMethods` | Zeichenfolge | Methoden zum Erkennen von Schadsoftware, Phishing oder anderen In der E-Mail gefundenen Bedrohungen |
| `ConfidenceLevel` | Zeichenfolge | Liste der Konfidenzstufen aller Spam- oder Phishingverdingungen. Für Spam zeigt diese Spalte die Spamsicherheitsstufe (Spam Confidence Level, SCL) an, die angibt, ob die E-Mail übersprungen wurde (-1), als kein Spam (0,1), als Spam mit moderatem Vertrauen (5,6) oder als Spam mit hoher Sicherheit (9) erkannt wurde. Bei Phishing wird in dieser Spalte angezeigt, ob die Konfidenzstufe "Hoch" oder "Niedrig" ist. |
| `EmailAction` | string | Letzte Aktion, die auf der Grundlage von Filter-Beurteilung, Richtlinien und Benutzeraktionen ausgeführt wird: Nachricht in den Junk-E-Mail-Ordner verschieben, X-Kopfzeile hinzufügen, Betreff ändern, Nachricht umleiten, Nachricht löschen, in Quarantäne senden, keine Aktion ausgeführt, BCC-Nachricht |
| `EmailActionPolicy` | string | Aktionsrichtlinie, die in Kraft getreten ist: Antispam-Hochsicherheit, Antispam, Antispam-Massen-E-Mail, Antispam-Phishing, Anti-Phishing-Domänenidentitätswechsel, Antiphishing-Benutzeridentitätswechsel, Antiphishing-Spoofing, Anti-Phishing-Grafik-Identitätswechsel, Antimalware, Sichere Anlagen, Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | string | Eindeutiger Bezeichner für die Richtlinie, welche die endgültige E-Mail-Aktion ermittelt hat |
| `AttachmentCount` | int | Anzahl der Anlagen in der E-Mail |
| `UrlCount` | int | Anzahl der eingebetteten URLs in der E-Mail |
| `EmailLanguage` | string | Erkannte Sprache des E-Mail-Inhalts |
| `Connectors` | Zeichenfolge | Benutzerdefinierte Anweisungen, die den E-Mail-Fluss der Organisation und die Art der E-Mail-Route definieren |
| `OrgLevelAction` | Zeichenfolge | Aktion für die E-Mail als Reaktion auf Übereinstimmungen mit einer auf Organisatorischer Ebene definierten Richtlinie |
| `OrgLevelPolicy` | Zeichenfolge | Organisationsrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `UserLevelAction` | Zeichenfolge | Aktion für die E-Mail als Reaktion auf Übereinstimmungen mit einer Postfachrichtlinie, die vom Empfänger definiert wurde |
| `UserLevelPolicy` | Zeichenfolge | Endbenutzerpostfachrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
