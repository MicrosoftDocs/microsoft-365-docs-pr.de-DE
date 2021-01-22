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
ms.openlocfilehash: 48a0fe53cb92214d616887741c0c260edf1653c2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928986"
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
| `EmailId` | string | Eindeutige E-Mail- und Empfänger-ID |
| `NetworkMessageId` | string | Eindeutiger Bezeichner für die E-Mail, generiert von Microsoft 365 |
| `InternetMessageId` | string | Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird |
| `SenderMailFromAddress` | string | Absender-E-Mail-Adresse in der Kopfzeile "MAIL FROM", auch als Umschlagabsender oder als Return-Path-Adresse bezeichnet |
| `SenderFromAddress` | string | Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse |
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
| `PhishDetectionMethod` | string | Methode zum Erkennen der E-Mail als Phishing: Schädliche URL-Reputation, URL-Detonation sicherer Links, erweiterter Phishingfilter, allgemeiner Phishingfilter, Antis spoofing: Organisationsinternes Spoofing, Antis spoofing: externe Domäne, Domänen-Identitätswechsel, Benutzer-Identitätswechsel, Markenwechsel |
| `MalwareFilterVerdict` | string | Bewertung des E-Mail-Filterstapels, ob die E-Mail Schadsoftware enthält: Schadsoftware, keine Schadsoftware |
| `MalwareDetectionMethod` | string | Methode zum Erkennen von Schadsoftware in der E-Mail: Antischalwaremodul, Dateire reputation, sichere Anlagen |
| `EmailAction` | string | Letzte Aktion, die auf der Grundlage von Filter-Beurteilung, Richtlinien und Benutzeraktionen ausgeführt wird: Nachricht in den Junk-E-Mail-Ordner verschieben, X-Kopfzeile hinzufügen, Betreff ändern, Nachricht umleiten, Nachricht löschen, in Quarantäne senden, keine Aktion ausgeführt, BCC-Nachricht |
| `EmailActionPolicy` | string | Aktionsrichtlinie, die in Kraft getreten ist: Antispam-Hochsicherheit, Antispam, Antispam-Massen-E-Mail, Antispam-Phishing, Anti-Phishing-Domänenidentitätswechsel, Antiphishing-Benutzeridentitätswechsel, Antiphishing-Spoofing, Anti-Phishing-Grafik-Identitätswechsel, Antimalware, Sichere Anlagen, Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | string | Eindeutiger Bezeichner für die Richtlinie, welche die endgültige E-Mail-Aktion ermittelt hat |
| `AttachmentCount` | int | Anzahl der Anlagen in der E-Mail |
| `UrlCount` | int | Anzahl der eingebetteten URLs in der E-Mail |
| `EmailLanguage` | string | Erkannte Sprache des E-Mail-Inhalts |
| `OrgLevelAction` | string | Aktion, die für die E-Mail als Reaktion auf Übereinstimmungen mit einer auf Organisationsebene definierten Richtlinie ergriffen wird |
| `OrgLevelPolicy` | string | Organisationsrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `UserLevelAction` | string | Aktion, die für die E-Mail als Reaktion auf Übereinstimmungen mit einer vom Empfänger definierten Postfachrichtlinie ergriffen wurde |
| `UserLevelPolicy` | string | Endbenutzerpostfachrichtlinie, die die Aktion für die E-Mail ausgelöst hat |
| `Connectors` | string | Benutzerdefinierte Anweisungen, die den E-Mail-Fluss der Organisation und die Art und Weise definieren, wie die E-Mail geroutet wurde |
| `SenderDisplayName` | string | Name des Absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem Vor- oder Vornamen, einem Vornamen und einem Nachnamen oder Nachnamen |
| `SenderObjectId` | string |Eindeutige ID für das Konto des Absenders in Azure AD |
| `ThreatTypes` | string | Überprüfen sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält. |
| `ThreatNames` | string |Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| `DetectionMethods` | string | Methoden zum Erkennen von Schadsoftware, Phishing oder anderen Bedrohungen, die in der E-Mail gefunden werden |


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
