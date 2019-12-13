---
title: Tabelle "EmailEvents" im Schema "Erweiterte Suche"
description: Erfahren Sie mehr über die Ereignisse, die Office 365-E-Mails in der Tabelle "EmailEvents" des Schemas „Erweiterte Suche“ zugeordnet sind.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyber-Bedrohungen, Suche, Abfrage, Telemetrie, Schema-Referenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailEvents, Netzwerk-Nachrichten-ID, Absender, Empfänger, Anlage-ID, Name der Anlage, Malware-Beurteilung, Phishing-Beurteilung, Anlagenanzahl, Verknüpfungsanzahl, URL-Anzahl
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1f2deef2c9ffc26f604194ff2d27d5f094471021
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911143"
---
# <a name="emailevents"></a>EmailEvents

**Gilt für:**
- Microsoft-Bedrohungsschutz

[!include[Prerelease information](prerelease.md)]

Die `EmailEvents`-Tabelle im Schema [Erweiterte Suche](advanced-hunting-overview.md) enthält Informationen zu Ereignissen, denen die Verarbeitung von E-Mails auf Office 365 ATP angehört. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `EventTime` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `EmailId` | string | Eindeutige E-Mail- und Empfänger-ID |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die von Office 365 generierte E-Mail |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `SenderMailFromAddress` | string | Absender-E-Mail-Adresse in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromAddress` | string | Absender-E-Mail-Adresse in der Kopfzeile "FROM", die für E-Mail-Empfänger in ihren E-Mail-Clients sichtbar ist |
| `SenderMailFromDomain` | string | Absender-Domäne in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromDomain` | string | Absender-Domäne in der Kopfzeile "FROM", die für E-Mail-Empfänger in ihren E-Mail-Clients sichtbar ist |
| `SenderIPv4` | string | Die IPv4-Adresse des letzten feststellbaren E-Mail-Servers, der die Nachricht weitergeleitet hat |
| `SenderIPv6` | string | Die IPv6-Adresse des letzten feststellbaren E-Mail-Servers, der die Nachricht weitergeleitet hat |
| `RecipientEmailAddress` | string | E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste |
| `Subject` | string | Betreff der E-Mail |
| `EmailClusterId` | string | Bezeichner für die Gruppe von ähnlichen E-Mail-Nachrichten, die auf Basis der heuristischen Analyse ihrer Inhalte gruppiert sind |
| `EmailDirection` | string | Richtung der E-Mail in Bezug auf Ihr Netzwerk: eingehend, ausgehend, Intern |
| `DeliveryAction` | string | Zustellungsaktion der E-Mail: übermittelt, als Junk eingestuft, blockiert oder ersetzt |
| `DeliveryLocation` | string | Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente" |
| `PhishFilterVerdict` | string | Urteil des E-Mail-Filter-Stacks, ob es sich um eine Phishing-E-Mail handelt: Phish oder nicht-Phish |
| `PhishDetectionMethod` | string | Methode zum Erkennen einer E-Mail als Phish: bösartiger URL-Ruf, ATP-sichere Links-URL-Detonation, erweiterter Phish-Filter, allgemeiner Phish-Filter, Antispoofing: Intra-org, Anti-Spoof: externe Domäne, Domänenidentitätswechsel, Benutzeridentitätswechsel, Vortäuschen einer Marke |
| `MalwareFilterVerdict` | string | Urteil des E-Mail-Filter-Stacks, ob die E-Mail Malware enthält: Malware, nicht-Malware |
| `MalwareDetectionMethod` | string | Methode zum Erkennen von Schadsoftware in der E-Mail: Antimalware-Engine, Dateireputation, ATP-sichere Anlagen |
| `FinalEmailAction` | string | Letzte Aktion, die auf der Grundlage von Filter-Beurteilung, Richtlinien und Benutzeraktionen ausgeführt wird: Nachricht in den Junk-E-Mail-Ordner verschieben, X-Kopfzeile hinzufügen, Betreff ändern, Nachricht umleiten, Nachricht löschen, in Quarantäne senden, keine Aktion ausgeführt, BCC-Nachricht |
| `FinalEmailActionPolicy` | string | Aktionsrichtlinie, die in Kraft getreten ist: Antispam-Hochsicherheit, Antispam, Antispam-Massen-E-Mail, Antispam-Phishing, Anti-Phishing-Domänenidentitätswechsel, Antiphishing-Benutzeridentitätswechsel, Antiphishing-Spoofing, Anti-Phishing-Grafik-Identitätswechsel, Antimalware, Sichere Anlagen, Enterprise Transport Rules (ETR) |
| `FinalEmailActionPolicyGuid` | string | Eindeutiger Bezeichner für die Richtlinie, welche die endgültige E-Mail-Aktion ermittelt hat |
| `AttachmentCount` | int | Anzahl der Anlagen in der E-Mail |
| `UrlCount` | int | Anzahl der eingebetteten URLs in der E-Mail |
| `EmailLanguage` | string | Erkannte Sprache des E-Mail-Inhalts |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwendung von freigegebenen Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)