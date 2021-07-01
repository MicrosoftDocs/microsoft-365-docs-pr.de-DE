---
title: Datentabellen im Schema für die erweiterte Suche Microsoft 365 Defender
description: Erfahren Sie mehr über die Tabellen im Schema "Erweiterte Suche", um die Daten zu verstehen, zu denen Sie Suchanfragen zur Bedrohungssuche ausführen können
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberrisiken, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten
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
ms.openlocfilehash: 50a221a65c8264d816de958ec74fa99e9e6db762
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53225992"
---
# <a name="understand-the-advanced-hunting-schema"></a>Grundlegendes zum Schema "Erweiterte Suche"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das Schema für die [erweiterte Suche](advanced-hunting-overview.md) besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Geräten, Warnungen, Identitäten und anderen Entitätstypen bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="get-schema-information-in-the-security-center"></a>Abrufen von Schemainformationen im Security Center
Verwenden Sie beim Erstellen von Abfragen die integrierte Schemareferenz, um schnell die folgenden Informationen zu jeder Tabelle im Schema abzurufen:

- **Tabellenbeschreibung**– Typ der in der Tabelle enthaltenen Daten und die Quelle dieser Daten.
- **Spalten**– alle Spalten in der Tabelle.
- **Aktionstypen**– mögliche Werte in der `ActionType` Spalte, die die von der Tabelle unterstützten Ereignistypen darstellen. Diese Informationen werden nur für Tabellen bereitgestellt, die Ereignisinformationen enthalten.
- **Beispielabfrage**: Beispielabfragen, die angeben, wie die Tabelle verwendet werden kann.

### <a name="access-the-schema-reference"></a>Zugreifen auf die Schemareferenz
Um schnell auf den Schemaverweis zuzugreifen, wählen Sie die **Ansichtsverweisaktion** neben dem Tabellennamen in der Schemadarstellung aus. Sie können auch **einen Schemaverweis** auswählen, um nach einer Tabelle zu suchen.

![Abbildung des Zugriffs auf die Schemareferenz im Portal](../../media/mtp-ah/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Lernen Sie die Schematabellen kennen
Im Folgenden sind alle Tabellen im Schema aufgelistet. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden. Tabellen- und Spaltennamen werden auch im Sicherheitscenter als Teil der Schemadarstellung auf dem Bildschirm "Erweiterte Suche" aufgeführt.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Warnungen von Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungskategorisierung  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Ereignisse, die Konten und Objekte in Office 365 und anderen Cloud-Apps und -Diensten betreffen |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Verschiedene Ereignistypen, einschließlich Ereignisse, die von Sicherheitssteuerelementen ausgelöst werden wie z. B. Windows Defender Antivirus und Exploit Protection |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Zertifikatinformationen zu signierten Dateien, die von Zertifikatüberprüfungsereignissen auf Endpunkten abgerufen wurden |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-Ladeereignisse |
| **[Deviceinfo](advanced-hunting-deviceinfo-table.md)** | Computer-Informationen einschließlich Infos zum Betriebssystem |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse auf Geräten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netzwerkeigenschaften von Geräten, einschließlich physischer Adapter, IP- und MAC-Adressen sowie verbundener Netzwerke und Domänen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks.  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventar der auf Geräten installierten Software, einschließlich Deren Versionsinformationen und Status des Supportendes |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Auf Geräten gefundene Softwaresicherheitsrisiken und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken beheben |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informationen zu Dateien, die an E-Mails angefügt sind |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 E-Mail-Ereignisse, einschließlich E-Mail-Zustellungs- und Blockierungsereignissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die E-Mails an das Empfängerpostfach übermittelt hat |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informationen zu URLs in E-Mails |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Ereignisse, die einen lokalen Domänencontroller betreffen, auf dem Active Directory (AD) ausgeführt wird. Diese Tabelle enthält eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Authentifizierungsereignisse in Active Directory und Microsoft-Onlinediensten |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
