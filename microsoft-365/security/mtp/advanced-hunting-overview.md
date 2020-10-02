---
title: Übersicht-Advanced Hunting
description: Erfahren Sie mehr über erweiterte Suchabfragen in Microsoft 365 und wie Sie diese verwenden, um Bedrohungen und Schwachstellen in Ihrem Netzwerk proaktiv zu ermitteln.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e586050465464def02c7787a5fb218b0b6071c7
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338473"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können proaktiv Ereignisse in Ihrem Netzwerk überprüfen, um Bedrohungs Indikatoren und Entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht eine uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um auf mutmaßliche Verstöße, falsch konfigurierte Computer und andere Ergebnisse zu prüfen und auf diese zu reagieren.

Diese Funktion ähnelt der [erweiterten Suche in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Diese Funktion steht im Microsoft 365 Security Center zur Verfügung und unterstützt Abfragen, die einen umfassenderen Datensatz aus folgenden Gründen überprüfen:

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App-Sicherheit
- Azure Advanced Threat Protection

Um die erweiterte Suche verwenden zu können, [aktivieren Sie Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Es empfiehlt sich, mehrere Schritte durchzugehen, um schnell mit Advanced Hunting zu beginnen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Erlernen der Sprache** | Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/)und unterstützt dieselbe Syntax und dieselben Operatoren. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Informationen zur Verwendung der Abfrageergebnisse** | Hier finden Sie Informationen zu Diagrammen und verschiedenen Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren, Drilldowns ausführen, um umfassendere Informationen zu erhalten, und Reaktions Aktionen durchführen können. | - [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)<br>- [Ausführen von Aktionen für Abfrageergebnisse](advanced-hunting-take-action.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Erfahren Sie, wo Sie beim Erstellen Ihrer Abfragen nach Daten suchen. | - [Schema Referenz](advanced-hunting-schema-tables.md)<br>- [Übergang von Microsoft Defender ATP](advanced-hunting-migrate-from-mdatp.md) |
| **Holen Sie sich Experten-Tipps und Beispiele** | Trainieren Sie kostenlos mit Anleitungen von Microsoft-Experten. Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | - [Experten-Schulungen erhalten](advanced-hunting-expert-training.md)<br>- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)<br>- [Go Hunt](advanced-hunting-go-hunt.md)<br>- [Jagen nach Bedrohungen auf Geräten, e-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md) |
| **Optimieren von Abfragen und behandeln von Fehlern** | Hier erfahren Sie, wie Sie effiziente und fehlerfreie Abfragen erstellen. | - [Bewährte Methoden für Abfragen](advanced-hunting-best-practices.md)<br>- [Behandeln von Fehlern](advanced-hunting-errors.md) |
| **Erstellen benutzerdefinierter Erkennungsregeln** | Erfahren Sie, wie Sie erweiterte Jagd Abfragen verwenden können, um Warnungen auszulösen und automatisch Reaktions Aktionen zu ergreifen. | - [Übersicht über benutzerdefinierte Erkennungen](custom-detections-overview.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="get-access"></a>Zugriff abrufen
Um Advanced Hunting oder andere [Microsoft Threat Protection](microsoft-threat-protection.md) -Funktionen verwenden zu können, benötigen Sie eine entsprechende Rolle in Azure Active Directory. Außerdem wird der Zugriff auf die Endpunkt Daten durch die Einstellungen für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) in Microsoft Defender ATP bestimmt. [Lesen Sie mehr über die Verwaltung des Zugriffs auf Microsoft Threat Protection.](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datenaktualität und Aktualisierungshäufigkeit
Erweiterte Jagd Daten können in zwei verschiedene Typen kategorisiert werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis-oder Aktivitätsdaten**– füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinetests auf. Advanced Hunting erhält diese Daten fast unmittelbar nach der erfolgreichen Übermittlung der Sensoren an die entsprechenden Cloud-Dienste. Beispielsweise können Sie Ereignisdaten von gesunden Sensoren auf Arbeitsstationen oder Domänencontrollern fast unmittelbar nach der Verfügbarkeit in Microsoft Defender ATP und Azure ATP Abfragen.
- **Entitätsdaten**– füllt Tabellen mit Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen Datenquellen als auch aus dynamischen Quellen wie Active Directory Einträgen und Ereignisprotokollen. Um neue Daten bereitzustellen, werden Tabellen alle 15 Minuten mit neuen Informationen aktualisiert, wobei Zeilen hinzugefügt werden, die möglicherweise nicht vollständig aufgefüllt wurden. Alle 24 Stunden werden Daten konsolidiert, um einen Datensatz einzufügen, der die neuesten, umfassendsten Datensätze zu jeder Entität enthält.

## <a name="time-zone"></a>Zeitzone
Zeit Informationen in Advanced Hunting befinden sich in der UTC-Zeitzone.

## <a name="related-topics"></a>Verwandte Themen
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Erhalten Sie ein fachliches Training](advanced-hunting-expert-training.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)

