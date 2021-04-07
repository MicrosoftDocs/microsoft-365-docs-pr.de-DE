---
title: Schemareferenz für erweiterte Suche
description: Erfahren Sie mehr über die Tabellen im erweiterten Suchschema, um die Daten zu verstehen, auf die Sie Abfragen zur Bedrohungssuche ausführen können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Mdatp, microsoft defender atp, wdatp-Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten
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
ms.openlocfilehash: 38fe205227089acaec1ba0cbecffdfb76acf6a24
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615471"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Verstehen des erweiterten Jagdschemas in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Das [schema der erweiterten](advanced-hunting-overview.md) Suche besteht aus mehreren Tabellen, die entweder Ereignisinformationen oder Informationen zu Geräten und anderen Entitäten bereitstellen. Wenn Sie effektive Abfragen erstellen möchten, die sich über mehrere Tabellen erstrecken, müssen Sie die Tabellen und Spalten im Schema "Erweiterte Suche" kennen.

## <a name="get-schema-information-in-the-security-center"></a>Schemainformationen im Security Center erhalten
Verwenden Sie beim Erstellen von Abfragen die integrierte Schemareferenz, um schnell die folgenden Informationen zu jeder Tabelle im Schema zu erhalten:

- **Tabellenbeschreibung**– Typ der in der Tabelle enthaltenen Daten und der Quelle dieser Daten.
- **Spalten**– alle Spalten in der Tabelle.
- **Aktionstypen**– mögliche Werte in der Spalte, die `ActionType` die von der Tabelle unterstützten Ereignistypen darstellen. Dies wird nur für Tabellen bereitgestellt, die Ereignisinformationen enthalten.
- **Beispielabfrage**– Beispielabfragen, die zeigen, wie die Tabelle verwendet werden kann.

### <a name="access-the-schema-reference"></a>Zugreifen auf die Schemareferenz
Um schnell auf die Schemareferenz zu zugreifen, wählen Sie die Referenzaktion Anzeigen neben dem Tabellennamen in der Schemadarstellung aus.  Sie können auch **Schemaverweis auswählen,** um nach einer Tabelle zu suchen.

![Abbildung des Zugriffs auf in-Portal-Schemareferenz](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Informationen zu den Schematabellen

In der folgenden Referenz sind alle Tabellen im Schema für die erweiterte Suche aufgeführt. Jeder Tabellenname verweist auf eine Seite, auf der die Spaltennamen für diese Tabelle beschrieben werden.

Tabellen- und Spaltennamen werden auch im Microsoft Defender Security Center in der Schemadarstellung auf dem Bildschirm für die erweiterte Suche aufgeführt.

| Tabellenname | Beschreibung |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Warnungen im Microsoft Defender Security Center |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Geräteinformationen, einschließlich Betriebssysteminformationen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netzwerkeigenschaften von Geräten, einschließlich Adaptern, IP- und MAC-Adressen sowie verbundenen Netzwerken und Domänen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Prozesserstellung und zugehörige Ereignisse |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netzwerkverbindung und zugehörige Ereignisse |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dateierstellung und -änderung sowie andere Dateisystemereignisse |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Erstellen und Ändern von Registrierungseinträgen |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Anmeldungen und andere Authentifizierungsereignisse |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-Ladeereignisse |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Mehrere Ereignistypen, einschließlich Ereignisse, die von Sicherheitssteuerelementen wie Microsoft Defender Antivirus und Exploit-Schutz ausgelöst werden |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Zertifikatinformationen signierter Dateien, die von Zertifikatüberprüfungsereignissen auf Endpunkten erhalten wurden |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventar der auf Geräten installierten Software, einschließlich der Versionsinformationen und des End-of-Support-Status |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Softwarerisiken auf Geräten und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken adressiert haben |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Wissensdatenbank veröffentlichter Sicherheitsrisiken, einschließlich der Angabe, ob Exploitcode öffentlich verfügbar ist |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Beurteilungsereignisse im Bereich Bedrohungs- und Sicherheitsrisikoverwaltung, mit Angabe des Status verschiedener Sicherheitskonfigurationen auf Geräten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Wissensdatenbank zu verschiedenen Sicherheitskonfigurationen, die im Rahmen der Bedrohungs- und Sicherheitsrisikoverwaltung zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks. |

>[!TIP]
>Verwenden Sie die erweiterte Suche [in Microsoft 365 Defender,](/microsoft-365/security/defender/advanced-hunting-overview) um mithilfe von Daten von Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity nach Bedrohungen zu fahnen. [Microsoft 365 Defender aktivieren](/microsoft-365/security/defender/m365d-enable)<br><br>
Erfahren Sie mehr darüber, wie Sie Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint verschieben.](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
- [Änderungen des Erweiterten Datenschemas für die Suche](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
