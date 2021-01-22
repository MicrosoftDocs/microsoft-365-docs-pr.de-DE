---
title: Datentabellen im Microsoft 365 Defender Advanced Hunting-Schema
description: Erfahren Sie mehr über die Tabellen im Schema "Erweiterte Suche", um die Daten zu verstehen, zu denen Sie Suchanfragen zur Bedrohungssuche ausführen können
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten
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
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925062"
---
# <a name="understand-the-advanced-hunting-schema"></a>Grundlegendes zum Schema "Erweiterte Suche"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das [Schema für die](advanced-hunting-overview.md) erweiterte Suche besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Geräten, Warnungen, Identitäten und anderen Entitätstypen bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="get-schema-information-in-the-security-center"></a>Schemainformationen im Security Center erhalten
Verwenden Sie beim Erstellen von Abfragen die integrierte Schemareferenz, um schnell die folgenden Informationen zu jeder Tabelle im Schema zu erhalten:

- **In Tabellen wird** der Typ der in der Tabelle enthaltenen Daten und die Quelle dieser Daten beschrieben.
- **Spalten**– alle Spalten in der Tabelle.
- **Aktionstypen**– mögliche Werte in der `ActionType` Spalte, die die von der Tabelle unterstützten Ereignistypen darstellen. Diese Informationen werden nur für Tabellen bereitgestellt, die Ereignisinformationen enthalten.
- **Beispielabfrage –** Beispielabfragen, die die Verwendung der Tabelle zeigen.

### <a name="access-the-schema-reference"></a>Zugreifen auf die Schemareferenz
Um schnell auf die Schemareferenz zu zugreifen, wählen Sie die **Verweisaktion** anzeigen neben dem Tabellennamen in der Schemadarstellung aus. Sie können auch einen **Schemaverweis auswählen,** um nach einer Tabelle zu suchen.   

![Abbildung des Zugriffs auf die In-Portal-Schemareferenz ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Informationen zu den Schematabellen
Im Folgenden sind alle Tabellen im Schema aufgelistet. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden. Tabellen- und Spaltennamen werden auch im Sicherheitscenter als Teil der Schemadarstellung auf dem Bildschirm "Erweiterte Suche" aufgeführt.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Warnungen von Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungs kategorisierung  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Dateibezogene Aktivitäten in Cloud-Apps und -Diensten |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Ereignisse im Zusammenhang mit Konten und Objekten in Office 365 und anderen Cloud-Apps und -Diensten |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Verschiedene Ereignistypen, einschließlich Ereignisse, die von Sicherheitssteuerelementen ausgelöst werden wie z. B. Windows Defender Antivirus und Exploit Protection |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Zertifikatinformationen zu signierten Dateien, die von Zertifikatüberprüfungsereignissen auf Endpunkten erhalten wurden |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-Ladeereignisse |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Computer-Informationen einschließlich Infos zum Betriebssystem |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse auf Geräten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netzwerkeigenschaften von Geräten, einschließlich physischer Adapter, IP- und MAC-Adressen, sowie verbundener Netzwerke und Domänen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks.  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventar der Software auf Geräten und aller bekannten Sicherheitsrisiken in diesen Softwareprodukten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informationen zu Dateien, die an E-Mails angefügt sind |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365-E-Mail-Ereignisse, einschließlich E-Mail-Übermittlung und Blockieren von Ereignissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die E-Mails an das Empfängerpostfach zugestellt hat |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informationen zu URLs in E-Mails |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Ereignisse, an denen ein lokales Domänencontroller beteiligt ist, auf dem Active Directory (AD) ausgeführt wird. In dieser Tabelle wird eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller behandelt. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Authentifizierungsereignisse für Active Directory und Microsoft Online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
