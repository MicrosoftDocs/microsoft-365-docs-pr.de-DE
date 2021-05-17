---
title: Übersicht über die erweiterte Suche in Microsoft Defender for Endpoint
description: Verwenden von Funktionen zur Bedrohungssuche in Microsoft Defender for Endpoint zum Erstellen von Abfragen, die Bedrohungen und Schwächen in Ihrem Netzwerk finden
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, Microsoft Defender für Endpunkt, wdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Zeitzone, UTC
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
ms.openlocfilehash: 906ae4bdebcc46e210fa9c5dcb5387c880fdbb38
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939660"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Proaktive Suche nach Bedrohungen mit erweiterter Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und -entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht die ungesübte Suche nach bekannten und potenziellen Bedrohungen.

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die erweiterte Suche und ein kurzes Lernprogramm zu erhalten, mit dem Sie schnell beginnen können.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um nach verdächtigen Sicherheitsverletzungen, falsch konfigurierten Computern und anderen Erkenntnissen zu suchen und darauf zu reagieren.

>[!TIP]
>Verwenden Sie die erweiterte Suche [in Microsoft 365 Defender,](/microsoft-365/security/defender/advanced-hunting-overview) um Bedrohungen mithilfe von Daten von Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity zu finden. [Aktivieren sie Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).<br><br>
Erfahren Sie mehr darüber, wie Sie Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint verschieben.](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Gehen Sie durch die folgenden Schritte, um Ihr erweitertes Sucheswissen zu stufen.

Es wird empfohlen, mehrere Schritte durchzugehen, um schnell mit der Verwendung der erweiterten Suche loszulegen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Erlernen der Sprache** | Die erweiterte Suche basiert auf [der Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/)und unterstützt dieselbe Syntax und Operatoren. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Informationen zur Verwendung der Abfrageergebnisse** | Erfahren Sie mehr über Diagramme und verschiedene Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren und einen Drilldown ausführen können, um reichhaltigere Informationen zu erhalten. | [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Erfahren Sie, wo Sie beim Erstellen Ihrer Abfragen nach Daten suchen können. | [Schemareferenz](advanced-hunting-schema-reference.md) |
| **Verwenden vordefinierter Abfragen** | Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | [Freigegebene Abfragen](advanced-hunting-shared-queries.md) |
| **Optimieren von Abfragen und Behandeln von Fehlern** | Erfahren Sie, wie Sie effiziente und fehlerfreie Abfragen erstellen. | - [Bewährte Methoden für Abfragen](advanced-hunting-best-practices.md)<br>- [Behandeln von Fehlern](advanced-hunting-errors.md) |
| **So erhalten Sie die vollständigste Abdeckung** | Verwenden Sie Überwachungseinstellungen, um eine bessere Datenabdeckung für Ihre Organisation zu bieten. | - [Erweiterte Abdeckung der Suche erweitern](advanced-hunting-extend-data.md) |
| **Ausführen einer schnellen Untersuchung** | Führen Sie schnell eine erweiterte Suchabfrage aus, um verdächtige Aktivitäten zu untersuchen. | - [Schnelle Suche nach Entitäts- oder Ereignisinformationen mit *Go Hunt*](advanced-hunting-go-hunt.md) |
| **Enthalten von Bedrohungen und Adressrisiken** | Reagieren auf Angriffe durch Quarantinieren von Dateien, Einschränken der App-Ausführung und andere Aktionen | - [Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse](advanced-hunting-take-action.md) |
| **Erstellen von benutzerdefinierten Erkennungsregeln** | Erfahren Sie, wie Sie erweiterte Suchabfragen verwenden können, um Warnungen auszulösen und automatisch Reaktionsaktionen zu ergreifen. | - [Übersicht über benutzerdefinierte Erkennungen](overview-custom-detections.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Datenfrischheit und Aktualisierungshäufigkeit

Erweiterte Suchesdaten können in zwei unterschiedliche Typen kategorisiert werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis- oder Aktivitätsdaten –** füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinebewertungen auf. Die erweiterte Suche empfängt diese Daten fast unmittelbar nach der erfolgreichen Übertragung der Sensoren, die sie sammeln, an Defender for Endpoint.
- **Entitätsdaten**– füllt Tabellen mit konsolidierten Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen als auch aus dynamischen Quellen, z. B. Active Directory-Einträgen und Ereignisprotokollen. Um neue Daten zur Verfügung zu stellen, werden Tabellen alle 15 Minuten mit allen neuen Informationen aktualisiert, und es werden Zeilen hinzugefügt, die möglicherweise nicht vollständig gefüllt sind. Alle 24 Stunden werden Daten konsolidiert, um einen Datensatz mit dem neuesten, umfassendsten Datensatz zu den einzelnen Entitäten zu einfügen.

## <a name="time-zone"></a>Zeitzone

Zeitinformationen in der erweiterten Suche befinden sich derzeit in der UTC-Zeitzone.

## <a name="related-topics"></a>Verwandte Themen

- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
