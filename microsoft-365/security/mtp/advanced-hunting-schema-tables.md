---
title: Datentabellen im Schema "Erweiterte Suche" in Microsoft Threat Protection
description: Erfahren Sie mehr über die Tabellen im Schema "Erweiterte Suche", um die Daten zu verstehen, zu denen Sie Suchanfragen zur Bedrohungssuche ausführen können
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten
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
ms.openlocfilehash: 0cb275584acfc2ea0d2a2969694ee189f48a875d
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046045"
---
# <a name="understand-the-advanced-hunting-schema"></a>Grundlegendes zum Schema "Erweiterte Suche"

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das [Erweiterte Jagd](advanced-hunting-overview.md) Schema besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Geräten, Warnungen, Identitäten und anderen Entitätstypen bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="get-schema-information-in-the-security-center"></a>Abrufen von Schemainformationen im Sicherheitscenter
Verwenden Sie beim Erstellen von Abfragen die integrierte Schemareferenz, um schnell die folgenden Informationen zu jeder Tabelle im Schema abzurufen:

- **Tabellenbeschreibung** – der Typ der in der Tabelle enthaltenen Daten und die Quelle dieser Daten.
- **Spalten** – alle Spalten in der Tabelle.
- **Aktionstypen** – mögliche Werte in der `ActionType` Spalte, die die von der Tabelle unterstützten Ereignistypen darstellen. Dies wird nur für Tabellen bereitgestellt, die Ereignisinformationen enthalten.
- **Beispielabfrage** – Beispielabfragen, die die Verwendung der Tabelle kennzeichnen.

### <a name="access-the-schema-reference"></a>Zugreifen auf die Schemareferenz
Um schnell auf die Schemareferenz zuzugreifen, wählen Sie in der Schemadarstellung die Aktion **Verweis anzeigen** neben dem Tabellennamen aus. Sie können auch **Schema Referenz** auswählen, um nach einer Tabelle zu suchen.   

![Abbildung mit dem Zugriff auf die in-Portal-Schemareferenz ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>Schematabellen
Im Folgenden sind alle Tabellen im Schema aufgelistet. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden. Die Tabellen- und Spaltennamen werden außerdem im Sicherheitscenter als Bestandteil der Schemadarstellung in der Ansicht "Erweiterte Suche" aufgelistet.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP, einschließlich schwere Informationen und Bedrohungs Kategorisierung  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Dateibezogene Aktivitäten in Cloud-apps und-Diensten |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Verschiedene Ereignistypen, einschließlich Ereignisse, die von Sicherheitssteuerelementen ausgelöst werden wie z. B. Windows Defender Antivirus und Exploit Protection |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Zertifikatinformationen für signierte Dateien, die von Zertifikat Überprüfungs Ereignissen an Endpunkten abgerufen werden |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-Ladeereignisse |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Computer-Informationen einschließlich Infos zum Betriebssystem |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse auf Geräten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netzwerkeigenschaften von Computern, einschließlich Adapter, IP- und Mac-Adressen sowie verbundene Netzwerke und Domänen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks.  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventar der Software auf Geräten sowie bekannte Sicherheitsrisiken in diesen Softwareprodukten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informationen zu an e-Mails angeschlossenen Dateien |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | E-Mail-Ereignisse von Microsoft 365, einschließlich e-Mail-Zustellung und Blockierungs Ereignisse |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die e-Mails an das Empfängerpostfach übermittelt hat |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informationen zu URLs in e-Mails |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Authentifizierungsereignisse für Active Directory und Microsoft Online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Abfrageaktivitäten, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
