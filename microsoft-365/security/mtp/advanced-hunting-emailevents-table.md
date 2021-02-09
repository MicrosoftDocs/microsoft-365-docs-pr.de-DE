---
title: Tabelle "EmailEvents" im Schema "Erweiterte Suche"
description: Informationen zu Ereignissen im Zusammenhang mit Microsoft 365-E-Mails in der Tabelle "EmailEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailEvents, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Malware-Bewert, Phishing-Bewert, Anlagenanzahl, Linkanzahl, URL-Anzahl
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
ms.openlocfilehash: f39e8f77a53b018fdf9c96981524e12f9aface65
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145043"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Ereignissen im Zusammenhang mit der Verarbeitung von E-Mails `EmailEvents` in Microsoft Defender für Office 365. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die E-Mail, generiert von Microsoft 365 |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `SenderMailFromAddress` | string | Absender-E-Mail-Adresse in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
| `SenderDisplayName` | string | Name des Absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem Vor- oder Vornamen, einem Vornamen und einem Nachnamen oder Nachnamen |
| `SenderObjectId` | string |Eindeutige ID für das Konto des Absenders in Azure AD |
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
| `PhishFilterVerdict` | string | Urteil des E-Mail-Filter-Stacks, ob es sich um eine Phishing-E-Mail handelt: Phish oder nicht-Phish |
| `PhishDetectionMethod` | string | Methode zum Erkennen der E-Mail als Phishing: Schädliche URL-Reputation, URL-Detonation sicherer Links, erweiterter Phishingfilter, allgemeiner Phishingfilter, Antis spoofing: Organisationsinternes Spoofing, Antis spoofing: externe Domäne, Domänen-Identitätswechsel, Benutzer-Identitätswechsel, Markenwechsel |
| `MalwareFilterVerdict` | string | Bewertung des E-Mail-Filterstapels, ob die E-Mail Schadsoftware enthält: Schadsoftware, keine Schadsoftware |
| `MalwareDetectionMethod` | string | Methode zum Erkennen von Schadsoftware in der E-Mail: Antischalwaremodul, Dateire reputation, sichere Anlagen |
| `ThreatTypes` | string | Überprüfen sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält. |
| `ThreatNames` | string |Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| `DetectionMethods` | string | Methoden zum Erkennen von Schadsoftware, Phishing oder anderen Bedrohungen, die in der E-Mail gefunden werden |
| `ConfidenceLevel` | string | Liste der Konfidenzstufen aller Spam- oder Phishingverdingungen. Bei Spam zeigt diese Spalte den SCL (Spam Confidence Level) an, der angibt, ob die E-Mail übersprungen wurde (-1), als kein Spam (0,1), als Spam mit moderatem Vertrauen (5,6) oder als Spam mit hoher Confidence (9) erkannt wurde. Bei Phishing zeigt diese Spalte an, ob die Konfidenzstufe "Hoch" oder "Niedrig" ist. |
| `EmailAction` | string | Letzte Aktion, die auf der Grundlage von Filter-Beurteilung, Richtlinien und Benutzeraktionen ausgeführt wird: Nachricht in den Junk-E-Mail-Ordner verschieben, X-Kopfzeile hinzufügen, Betreff ändern, Nachricht umleiten, Nachricht löschen, in Quarantäne senden, keine Aktion ausgeführt, BCC-Nachricht |
| `EmailActionPolicy` | string | Aktionsrichtlinie, die in Kraft getreten ist: Antispam-Hochsicherheit, Antispam, Antispam-Massen-E-Mail, Antispam-Phishing, Anti-Phishing-Domänenidentitätswechsel, Antiphishing-Benutzeridentitätswechsel, Antiphishing-Spoofing, Anti-Phishing-Grafik-Identitätswechsel, Antimalware, Sichere Anlagen, Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | string | Eindeutiger Bezeichner für die Richtlinie, welche die endgültige E-Mail-Aktion ermittelt hat |
| `AttachmentCount` | int | Anzahl der Anlagen in der E-Mail |
| `UrlCount` | int | Anzahl der eingebetteten URLs in der E-Mail |
| `EmailLanguage` | string | Erkannte Sprache des E-Mail-Inhalts |
| `Connectors` | string | Benutzerdefinierte Anweisungen, die den E-Mail-Fluss der Organisation und die Art und Weise definieren, wie die E-Mail geroutet wurde |
| `OrgLevelAction` | string | Aktion, die auf der E-Mail als Reaktion auf Übereinstimmungen mit einer auf Organisationsebene definierten Richtlinie ergriffen wird |
| `OrgLevelPolicy` | string | Organisationsrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `UserLevelAction` | string | Aktion, die für die E-Mail als Reaktion auf Übereinstimmungen mit einer vom Empfänger definierten Postfachrichtlinie ergriffen wird |
| `UserLevelPolicy` | string | Endbenutzerpostfachrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
