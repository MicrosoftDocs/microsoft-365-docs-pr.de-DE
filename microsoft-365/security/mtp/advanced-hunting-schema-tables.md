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
ms.openlocfilehash: 3509bc5031ed83785c2b0de4c0711d04f5d5ac56
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327018"
---
# <a name="understand-the-advanced-hunting-schema"></a>Grundlegendes zum Schema "Erweiterte Suche"

**Gilt für:**
- Microsoft Threat Protection

Das Schema ["Erweiterte Suche"](advanced-hunting-overview.md) besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Computern und Entitäten bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

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
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse |
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
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informationen zu URLs in Microsoft 365-e-Mails |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Von Active Directory aufgezeichnete Authentifizierungsereignisse und andere Microsoft Online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Abfrageaktivitäten, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden |




## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
