---
title: Übersicht – Erweiterte Suche
description: Erfahren Sie mehr über erweiterte Suchabfragen in Microsoft 365 und wie Sie diese verwenden, um Bedrohungen und Schwachstellen in Ihrem Netzwerk proaktiv zu ermitteln.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932274"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)
>

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv untersuchen, um Bedrohungsindikatoren und Entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht die nächtlose Suche nach bekannten und potenziellen Bedrohungen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um auf mutmaßliche Sicherheitsverletzungen, falsch konfigurierte Computer und andere Erkenntnisse zu prüfen und darauf zu reagieren.

Diese Funktion ähnelt der [erweiterten Suche in Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Diese Funktion ist im Microsoft 365 Security Center verfügbar und unterstützt Abfragen, die einen größeren Datensatz aus:

- Microsoft Defender für Endpunkt
- Microsoft Defender für Office 365
- Microsoft Cloud App-Sicherheit
- Microsoft Defender for Identity

Um die erweiterte Suche zu verwenden, [aktivieren Sie Microsoft 365 Defender](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Es wird empfohlen, mehrere Schritte zu unternehmen, um schnell mit der erweiterten Suche zu beginnen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Erlernen der Sprache** | Die erweiterte Suche basiert auf [der Kusto-Abfragesprache,](https://docs.microsoft.com/azure/kusto/query/)die die gleiche Syntax und dieselben Operatoren unterstützt. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Erfahren Sie, wie Sie die Abfrageergebnisse verwenden** | Erfahren Sie mehr über Diagramme und verschiedene Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren, einen Drilldown ausführen können, um vielfältigere Informationen zu erhalten und Reaktionsaktionen zu ergreifen. | - [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)<br>- [Ergreifen von Maßnahmen für Abfrageergebnisse](advanced-hunting-take-action.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Erfahren Sie, wo Sie beim Erstellen Ihrer Abfragen nach Daten suchen können. | - [Schemareferenz](advanced-hunting-schema-tables.md)<br>- [Übergang von Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md) |
| **Tipps und Beispiele für Experten erhalten** | Kostenloses Trainieren mit Handbüchern von Microsoft-Experten. Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | - [Expertenschulungen erhalten](advanced-hunting-expert-training.md)<br>- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)<br>- [Go hunt](advanced-hunting-go-hunt.md)<br>- [Suche nach Bedrohungen auf allen Geräten, E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md) |
| **Optimieren von Abfragen und Behandeln von Fehlern** | Hier erfahren Sie, wie Sie effiziente und fehlerfreie Abfragen erstellen. | - [Bewährte Methoden für Abfragen](advanced-hunting-best-practices.md)<br>- [Behandeln von Fehlern](advanced-hunting-errors.md) |
| **Erstellen von benutzerdefinierten Erkennungsregeln** | Hier erfahren Sie, wie Sie erweiterte Suchabfragen verwenden können, um Warnungen auszulösen und automatisch Antwortaktionen zu ergreifen. | - [Übersicht über benutzerdefinierte Erkennungen](custom-detections-overview.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="get-access"></a>Zugriff erhalten
Um die erweiterte Suche oder andere [Microsoft 365](microsoft-threat-protection.md) Defender-Funktionen zu verwenden, benötigen Sie eine entsprechende Rolle in Azure Active Directory. Außerdem wird Ihr Zugriff auf Endpunktdaten durch rollenbasierte Zugriffssteuerungseinstellungen (RBAC) in Microsoft Defender for Endpoint bestimmt. [Informationen zum Verwalten des Zugriffs auf Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datenaktualisierung und Aktualisierungshäufigkeit
Erweiterte Suchesdaten können in zwei verschiedene Typen unterteilt werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis- oder Aktivitätsdaten –** Füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinebewertungen auf. Die erweiterte Suche empfängt diese Daten unmittelbar nach der erfolgreichen Übertragung der Sensoren, die sie sammeln, an die entsprechenden Clouddienste. Beispielsweise können Sie Ereignisdaten von fehlerfreien Sensoren auf Arbeitsstationen oder Domänencontrollern direkt abfragen, nachdem sie in Microsoft Defender for Endpoint und Microsoft Defender for Identity verfügbar sind.
- **Entitätsdaten –** füllt Tabellen mit Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen als auch aus dynamischen Quellen, z. B. Active Directory-Einträgen und Ereignisprotokollen. Um neue Daten zur Verfügung zu stellen, werden Tabellen alle 15 Minuten mit neuen Informationen aktualisiert, und es werden Zeilen hinzugefügt, die möglicherweise nicht vollständig ausgefüllt sind. Alle 24 Stunden werden Daten konsolidiert, um einen Datensatz mit dem neuesten, umfassendsten Datensatz zu jeder Entität einfügen zu können.

## <a name="time-zone"></a>Zeitzone
Zeitinformationen bei der erweiterten Suche befinden sich in der UTC-Zeitzone.

## <a name="related-topics"></a>Verwandte Themen
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Erhalten Sie ein fachliches Training](advanced-hunting-expert-training.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)

