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
ms.openlocfilehash: c09047648f1d6bb6d68be78315a876be4998e595
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552434"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv prüfen, um interessante Indikatoren und Entitäten zu ermitteln. Der flexible Zugriff auf Daten ermöglicht eine uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Sie können die gleichen Abfragen für die Bedrohungssuche verwenden, um benutzerdefinierte Erkennungsregeln zu erstellen. Diese Regeln werden automatisch ausgeführt, um nach verschiedenen Ereignissen und Systemzuständen zu suchen, darunter mutmaßliche Sicherheitsvorfälle und falsch konfigurierte Computer, und auf diese zu reagieren.

Im Microsoft 365 Security Center unterstützt Advanced Hunting Abfragen, die Daten aus verschiedenen Arbeitsbereichen durchsuchen, einschließlich Daten zu Geräten, e-Mails, Apps und Identitäten von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP. Um die erweiterte Suche verwenden zu können, [aktivieren Sie Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Erste Schritte mit der erweiterten Suche

Es wird empfohlen, mehrere Schritte durchzugehen, um schnell mit der Verwendung der erweiterten Suche loszulegen.

| Lernziel | Beschreibung | Ressource |
|--|--|--|
| **Gespür für die Sprache** | Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/)und unterstützt dieselbe Syntax und dieselben Operatoren. Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen. | [Übersicht über die Abfragesprache](advanced-hunting-query-language.md) |
| **Informationen zur Verwendung der Abfrageergebnisse** | Hier finden Sie Informationen zu Diagrammen und verschiedenen Möglichkeiten zum Anzeigen oder Exportieren Ihrer Ergebnisse. Erfahren Sie, wie Sie Abfragen schnell optimieren, Drilldowns ausführen, um umfassendere Informationen zu erhalten, und Reaktions Aktionen durchführen können. | - [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)<br>- [Ausführen von Aktionen für Abfrageergebnisse](advanced-hunting-take-action.md) |
| **Grundlegendes zum Schema** | Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten. Auf diese Weise können Sie bestimmen, wo nach Daten gesucht wird und wie Sie Ihre Abfragen erstellen. | [Schemareferenz](advanced-hunting-schema-tables.md) |
| **Nutzen von vordefinierten Abfragen** | Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen. | - [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)<br>- [Go Hunt](advanced-hunting-go-hunt.md) |
| **Optimieren von Abfragen** | Erfahren Sie, wie Sie effiziente Abfragen und Abfragen erstellen, die Daten aus E-Mails und Geräten kombinieren. | - [Bewährte Methoden für Abfragen](advanced-hunting-shared-queries.md) <br>- [Jagd auf Geräte und e-Mails](advanced-hunting-best-practices.md) |
| **Erstellen benutzerdefinierter Erkennungsregeln** | Erfahren Sie, wie Sie erweiterte Jagd Abfragen verwenden können, um Warnungen auszulösen und Reaktions Aktionen automatisch anzuwenden. | - [Übersicht über benutzerdefinierte Erkennungen](custom-detections-overview.md)<br>- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) |

## <a name="get-access"></a>Zugriff abrufen
Um Advanced Hunting oder andere [Microsoft Threat Protection](microsoft-threat-protection.md) -Funktionen verwenden zu können, müssen Sie in Azure AD eine entsprechende Rolle zugewiesen haben. Beachten Sie, dass Ihr Zugriff auf Endpunkt Daten durch rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender ATP beeinflusst wird. [Lesen Sie mehr über die Verwaltung des Zugriffs auf Microsoft Threat Protection.](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datenaktualität und Aktualisierungshäufigkeit
Erweiterte Jagd Daten können in zwei verschiedene Typen kategorisiert werden, die jeweils unterschiedlich konsolidiert werden.

- **Ereignis-oder Aktivitätsdaten** – füllt Tabellen zu Warnungen, Sicherheitsereignissen, Systemereignissen und Routinetests auf. Advanced Hunting erhält diese Daten fast unmittelbar nach der erfolgreichen Übermittlung der Sensoren an die entsprechenden Cloud-Dienste. Beispielsweise können Sie mit dem Abfragen von Ereignisdaten von gesunden Sensoren auf Arbeitsstationen oder Domänencontrollern beginnen, fast unmittelbar nachdem Sie auf Microsoft Defender ATP und Azure ATP verfügbar sind.
- **Entitätsdaten** – füllt Tabellen mit konsolidierten Informationen zu Benutzern und Geräten auf. Diese Daten stammen sowohl aus relativ statischen Datenquellen wie Active Directory Einträgen als auch aus dynamischen Quellen wie Ereignisprotokollen. Um neue Daten bereitzustellen, werden Tabellen alle 15 Minuten mit neuen Informationen aktualisiert, wobei Zeilen hinzugefügt werden, die möglicherweise nicht vollständig aufgefüllt werden. Alle 24 Stunden werden Daten konsolidiert, um einen Datensatz einzufügen, der die neuesten, umfassendsten Datensätze zu jeder Entität enthält.

## <a name="related-topics"></a>Verwandte Themen
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Ausführen von Aktionen für Abfrageergebnisse](advanced-hunting-take-action.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
