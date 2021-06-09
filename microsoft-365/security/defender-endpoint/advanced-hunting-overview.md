---
title: Übersicht über die erweiterte Suche in Microsoft Defender für Endpunkt
description: Verwenden von Funktionen zur Bedrohungssuche in Microsoft Defender für Endpunkt zum Erstellen von Abfragen, die Bedrohungen und Schwachstellen in Ihrem Netzwerk finden
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, MDATP, Microsoft Defender ATP, Microsoft Defender für Endpunkt, Wdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Zeitzone, UTC
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
ms.technology: mde
ms.openlocfilehash: 9f1934de8f710a21bc362e735bb6f1eab7a2d287
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845418"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Proaktive Suche nach Bedrohungen mit erweiterter Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und Entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht eine uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die erweiterte Suche und ein kurzes Lernprogramm zu erhalten, das Ihnen den schnellen Einstieg ermöglicht.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um nach verdächtigen Sicherheitsverletzungen, falsch konfigurierten Computern und anderen Ergebnissen zu suchen und dann darauf zu reagieren.

>[!TIP]
>Verwenden Sie [die erweiterte Suche in Microsoft 365 Defender,](/microsoft-365/security/defender/advanced-hunting-overview) um mithilfe von Daten von Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity nach Bedrohungen zu suchen. [Aktivieren Sie Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).<br><br>
Erfahren Sie mehr darüber, wie Sie Ihre Workflows für die erweiterte Suche von Microsoft Defender für Endpunkt zu Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)verschieben.

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Gehen Sie die folgenden Schritte durch, um Ihr erweitertes Suchwissen zu erweitern.

Es wird empfohlen, mehrere Schritte durchzugehen, um schnell mit der Verwendung der erweiterten Suche loszulegen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Erlernen der Sprache** | Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](/azure/kusto/query/)und unterstützt die gleiche Syntax und dieselben Operatoren. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Erfahren Sie, wie Sie die Abfrageergebnisse verwenden** | Erfahren Sie mehr über Diagramme und verschiedene Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren und einen Drilldown durchführen können, um umfassendere Informationen zu erhalten. | [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Erfahren Sie, wo Sie beim Erstellen von Abfragen nach Daten suchen können. | [Schemareferenz](advanced-hunting-schema-reference.md) |
| **Verwenden vordefinierter Abfragen** | Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | [Freigegebene Abfragen](advanced-hunting-shared-queries.md) |
| **Optimieren von Abfragen und Behandeln von Fehlern** | Verstehen, wie effiziente und fehlerfreie Abfragen erstellt werden. | - [Bewährte Methoden für Abfragen](advanced-hunting-best-practices.md)<br>- [Behandeln von Fehlern](advanced-hunting-errors.md) |
| **Erhalten Sie die umfassendste Abdeckung** | Verwenden Sie Überwachungseinstellungen, um eine bessere Datenabdeckung für Ihre Organisation bereitzustellen. | - [Erweitern der erweiterten Suchabdeckung](advanced-hunting-extend-data.md) |
| **Ausführen einer schnellen Untersuchung** | Führen Sie schnell eine erweiterte Suchabfrage aus, um verdächtige Aktivitäten zu untersuchen. | - [Schnelle Suche nach Entitäts- oder Ereignisinformationen mit *go hunt*](advanced-hunting-go-hunt.md) |
| **Bedrohungen enthalten und Kompromittierungen beheben** | Reagieren Sie auf Angriffe, indem Sie Dateien einschränken, die Ausführung von Apps einschränken und andere Aktionen ausführen. | - [Ergreifen von Maßnahmen für Abfrageergebnisse der erweiterten Suche](advanced-hunting-take-action.md) |
| **Erstellen benutzerdefinierter Erkennungsregeln** | Erfahren Sie, wie Sie abfragen erweiterte Suche verwenden können, um Warnungen auszulösen und reaktionsaktionen automatisch auszuführen. | - [Übersicht über benutzerdefinierte Erkennungen](overview-custom-detections.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Aktualität und Aktualisierungshäufigkeit von Daten

Erweiterte Suchdaten können in zwei verschiedene Typen kategorisiert werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis- oder Aktivitätsdaten**– füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinebewertungen. Die erweiterte Suche empfängt diese Daten fast unmittelbar nach den Sensoren, die sie sammeln, und überträgt sie erfolgreich an Defender für Endpunkt.
- **Entitätsdaten**– füllt Tabellen mit konsolidierten Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen Datenquellen als auch aus dynamischen Quellen, z. B. Active Directory-Einträgen und Ereignisprotokollen. Um neue Daten bereitzustellen, werden Tabellen alle 15 Minuten mit neuen Informationen aktualisiert, wobei Zeilen hinzugefügt werden, die möglicherweise nicht vollständig ausgefüllt sind. Alle 24 Stunden werden die Daten konsolidiert, um einen Datensatz einzufügen, der den neuesten, umfassendsten Datensatz zu jeder Entität enthält.

## <a name="time-zone"></a>Zeitzone

Zeitinformationen in der erweiterten Suche befinden sich derzeit in der UTC-Zeitzone.

## <a name="related-topics"></a>Verwandte Themen

- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
