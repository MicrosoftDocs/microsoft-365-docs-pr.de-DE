---
title: Schemareferenz für die erweiterte Suche
description: Erfahren Sie mehr über die Tabellen im Schema für die erweiterte Suche, um die Daten zu verstehen, auf denen Sie Abfragen zur Bedrohungssuche ausführen können.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, MDATP, Microsoft Defender ATP, Microsoft Defender für Endpunkt, Wdatp-Suche, Abfrage, Telemetrie, Schemareferenz, kusto, Tabelle, Daten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: fcc7d96f51121824550128e89186074e1ebc3ce0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228879"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Grundlegendes zum Schema für die erweiterte Suche in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Das Schema für die [erweiterte Suche](advanced-hunting-overview.md) besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Geräten und anderen Entitäten bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="get-schema-information-in-the-security-center"></a>Abrufen von Schemainformationen im Security Center
Verwenden Sie beim Erstellen von Abfragen die integrierte Schemareferenz, um schnell die folgenden Informationen zu jeder Tabelle im Schema abzurufen:

- **Tabellenbeschreibung**– Typ der in der Tabelle enthaltenen Daten und die Quelle dieser Daten.
- **Spalten**– alle Spalten in der Tabelle.
- **Aktionstypen**– mögliche Werte in der `ActionType` Spalte, die die von der Tabelle unterstützten Ereignistypen darstellen. Dies wird nur für Tabellen bereitgestellt, die Ereignisinformationen enthalten.
- **Beispielabfrage**: Beispielabfragen, die angeben, wie die Tabelle verwendet werden kann.

### <a name="access-the-schema-reference"></a>Zugreifen auf die Schemareferenz
Um schnell auf den Schemaverweis zuzugreifen, wählen Sie die **Ansichtsverweisaktion** neben dem Tabellennamen in der Schemadarstellung aus. Sie können auch **einen Schemaverweis** auswählen, um nach einer Tabelle zu suchen.

![Abbildung des Zugriffs auf die Schemareferenz im Portal](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Lernen Sie die Schematabellen kennen

In der folgenden Referenz sind alle Tabellen im Schema für die erweiterte Suche aufgeführt. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden.

Tabellen- und Spaltennamen werden auch im Microsoft Defender Security Center in der Schemadarstellung auf dem Bildschirm "Erweiterte Suche" aufgeführt.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Warnungen zu Microsoft Defender Security Center |
| **[Deviceinfo](advanced-hunting-deviceinfo-table.md)** | Geräteinformationen, einschließlich Betriebssysteminformationen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netzwerkeigenschaften von Geräten, einschließlich Adaptern, IP- und MAC-Adressen sowie verbundenen Netzwerken und Domänen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-Ladeereignisse |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Mehrere Ereignistypen, einschließlich Ereignissen, die durch Sicherheitskontrollen ausgelöst werden, z. B. Microsoft Defender Antivirus und Exploit-Schutz |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Zertifikatinformationen zu signierten Dateien, die von Zertifikatüberprüfungsereignissen auf Endpunkten abgerufen wurden |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventar der auf Geräten installierten Software, einschließlich Deren Versionsinformationen und Status des Supportendes |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Auf Geräten gefundene Softwaresicherheitsrisiken und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken beheben |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks. |

>[!TIP]
>Verwenden Sie [die erweiterte Suche in Microsoft 365 Defender,](/microsoft-365/security/defender/advanced-hunting-overview) um mithilfe von Daten von Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity nach Bedrohungen zu suchen. [Microsoft 365 Defender aktivieren](/microsoft-365/security/defender/m365d-enable)<br><br>
Erfahren Sie mehr darüber, wie Sie Ihre Workflows für die erweiterte Suche von Microsoft Defender für Endpunkt in Microsoft 365 Defender [migrieren, wenn Sie Abfragen für die erweiterte Suche von Microsoft Defender für Endpunkt migrieren.](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
- [Änderungen des Datenschemas für die erweiterte Suche](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
