---
title: Übersicht – Erweiterte Suche
description: Erfahren Sie mehr über erweiterte Suchabfragen in Microsoft 365 und wie Sie diese verwenden, um Bedrohungen und Schwachstellen in Ihrem Netzwerk proaktiv zu ermitteln.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, microsoft 365, Microsoft Threat Protection
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 0338e87c103bef0f12a45277a14152ef429d0067
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068311"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und -entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht die ungesübte Suche nach bekannten und potenziellen Bedrohungen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um nach verdächtigen Sicherheitsverletzungen, falsch konfigurierten Computern und anderen Erkenntnissen zu suchen und darauf zu reagieren.

Diese Funktion ähnelt der [erweiterten Suche in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). In Microsoft 365 Security Center verfügbar, unterstützt diese Funktion Abfragen, die einen umfassenderen Datensatz aus überprüfen:

- Microsoft Defender für Endpunkt
- Microsoft Defender für Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Um die erweiterte Suche zu verwenden, [aktivieren Sie Microsoft 365 Defender](m365d-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Es wird empfohlen, mehrere Schritte zu unternehmen, um schnell mit der erweiterten Suche zu beginnen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Erlernen der Sprache** | Die erweiterte Suche basiert auf [der Kusto-Abfragesprache](/azure/kusto/query/)und unterstützt dieselbe Syntax und Operatoren. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Informationen zur Verwendung der Abfrageergebnisse** | Erfahren Sie mehr über Diagramme und verschiedene Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren, einen Drilldown durchführen können, um reichhaltigere Informationen zu erhalten und Reaktionsaktionen zu ergreifen. | - [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)<br>- [Ergreifen von Aktionen für Abfrageergebnisse](advanced-hunting-take-action.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Erfahren Sie, wo Sie beim Erstellen Ihrer Abfragen nach Daten suchen können. | - [Schemareferenz](advanced-hunting-schema-tables.md)<br>- [Übergang von Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md) |
| **Erhalten von Expertentipps und Beispielen** | Kostenloses Trainieren mit Anleitungen von Microsoft-Experten. Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | - [Expertenschulungen erhalten](advanced-hunting-expert-training.md)<br>- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)<br>- [Auf Die Suche gehen](advanced-hunting-go-hunt.md)<br>- [Suche nach Bedrohungen auf allen Geräten, E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md) |
| **Optimieren von Abfragen und Behandeln von Fehlern** | Erfahren Sie, wie Sie effiziente und fehlerfreie Abfragen erstellen. | - [Bewährte Methoden für Abfragen](advanced-hunting-best-practices.md)<br>- [Behandeln von Fehlern](advanced-hunting-errors.md) |
| **Erstellen von benutzerdefinierten Erkennungsregeln** | Erfahren Sie, wie Sie erweiterte Suchabfragen verwenden können, um Warnungen auszulösen und automatisch Reaktionsaktionen zu ergreifen. | - [Übersicht über benutzerdefinierte Erkennungen](custom-detections-overview.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="get-access"></a>Zugriff erhalten
Um erweiterte Suche oder andere [Microsoft 365 Defender-Funktionen](microsoft-365-defender.md) zu verwenden, benötigen Sie eine entsprechende Rolle in Azure Active Directory. Außerdem wird Ihr Zugriff auf Endpunktdaten durch rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender for Endpoint bestimmt. [Informationen zum Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datenfrischheit und Aktualisierungshäufigkeit
Erweiterte Suchesdaten können in zwei unterschiedliche Typen kategorisiert werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis- oder Aktivitätsdaten –** füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinebewertungen auf. Die erweiterte Suche empfängt diese Daten fast unmittelbar nach der erfolgreichen Übertragung der Sensoren, die sie erfassen, an die entsprechenden Clouddienste. Beispielsweise können Sie Ereignisdaten von fehlerfreien Sensoren auf Arbeitsstationen oder Domänencontrollern unmittelbar abfragen, nachdem sie in Microsoft Defender for Endpoint und Microsoft Defender for Identity verfügbar sind.
- **Entitätsdaten**– füllt Tabellen mit Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen als auch aus dynamischen Quellen, z. B. Active Directory-Einträgen und Ereignisprotokollen. Um neue Daten zur Verfügung zu stellen, werden Tabellen alle 15 Minuten mit allen neuen Informationen aktualisiert, und es werden Zeilen hinzugefügt, die möglicherweise nicht vollständig gefüllt sind. Alle 24 Stunden werden Daten konsolidiert, um einen Datensatz mit dem neuesten, umfassendsten Datensatz zu den einzelnen Entitäten zu einfügen.

## <a name="time-zone"></a>Zeitzone
Zeitinformationen in der erweiterten Suche befinden sich in der UTC-Zeitzone.

## <a name="related-topics"></a>Verwandte Themen
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Erhalten Sie ein fachliches Training](advanced-hunting-expert-training.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)