---
title: Datentabellen im Schema "Erweiterte Suche" in Microsoft Threat Protection
description: Erfahren Sie mehr über die Tabellen im Schema "Erweiterte Suche", um die Daten zu verstehen, zu denen Sie Suchanfragen zur Bedrohungssuche ausführen können
keywords: erweiterte Suche, Suche nach Bedrohungen, Suche nach Cyberbedrohungen, Suche, Anfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten
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
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911102"
---
# <a name="understand-the-advanced-hunting-schema"></a>Grundlegendes zum Schema "Erweiterte Suche"

**Gilt für:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Das Schema ["Erweiterte Suche"](advanced-hunting-overview.md) besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Computern und Entitäten bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="schema-tables"></a>Schematabellen

Im Folgenden sind alle Tabellen im Schema aufgelistet. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden. Die Tabellen- und Spaltennamen werden außerdem im Sicherheitscenter als Bestandteil der Schemadarstellung in der Ansicht "Erweiterte Suche" aufgelistet.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | Computer-Informationen einschließlich Infos zum Betriebssystem |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | Netzwerkeigenschaften von Computern, einschließlich Adapter, IP- und Mac-Adressen sowie verbundene Netzwerke und Domänen |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | DLL-Ladeereignisse |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Verschiedene Ereignistypen, einschließlich Ereignisse, die von Sicherheitssteuerelementen ausgelöst werden wie z. B. Windows Defender Antivirus und Exploit Protection |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Office 365-E-Mail-Ereignisse, einschließlich E-Mail-Zustellung und Blockieren von Ereignissen |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informationen zu Dateien, die an Office 365-E-Mails angefügt sind |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informationen zu URLs in Office 365-E-Mails |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventar der Software auf Geräten sowie bekannte Sicherheitsrisiken in diesen Softwareprodukten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks.  |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
