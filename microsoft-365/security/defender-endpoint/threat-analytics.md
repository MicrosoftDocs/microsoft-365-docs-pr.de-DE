---
title: Nachverfolgen und Reagieren auf neue Bedrohungen mit Microsoft Defender für Endpunkt-Bedrohungsanalyse
ms.reviewer: ''
description: Verstehen sie neue Bedrohungen und Angriffstechniken und wie Sie sie stoppen können. Bewerten Sie deren Auswirkungen auf Ihre Organisation und bewerten Sie die Resilienz Ihrer Organisation.
keywords: Bedrohungsanalyse, Risikobewertung, BS-Risikominderung, Mikrocode-Risikominderung, Risikominderungsstatus
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63303f9eacd25a8de1c7154ac66c73578bfd495a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924455"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a>Nachverfolgen und Reagieren auf neue Bedrohungen durch Bedrohungsanalyse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mit komplexeren Angreifern und neuen Bedrohungen, die häufig und weit verbreitet auftreten, ist es wichtig, schnell zu sein:

- Bewerten der Auswirkungen neuer Bedrohungen
- Überprüfen Sie Ihre Resilienz gegenüber bedrohungen oder deren Gefährdung
- Identifizieren Sie die Aktionen, die Sie ausführen können, um die Bedrohungen zu beenden oder einzudämmen.

Bei der Bedrohungsanalyse handelt es sich um eine Reihe von Berichten von erfahrenen Microsoft-Sicherheitsexperten, die die relevantesten Bedrohungen abdecken, einschließlich:

- Aktive Bedrohungsteilnehmer und ihre Kampagnen
- Beliebte und neue Angriffstechniken
- Kritische Sicherheitsrisiken
- Allgemeine Angriffsflächen
- Weit verbreitete Schadsoftware

Jeder Bericht enthält eine detaillierte Analyse einer Bedrohung und umfassende Anleitungen zum Schutz vor dieser Bedrohung. Es enthält auch Daten aus Ihrem Netzwerk, die angeben, ob die Bedrohung aktiv ist und ob Sie über entsprechende Schutzmaßnahmen verfügen.

Sehen Sie sich dieses kurze Video an, um mehr darüber zu erfahren, wie Bedrohungsanalysen Ihnen helfen können, die neuesten Bedrohungen nachzuverfolgen und zu beenden.
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a>Anzeigen des Dashboards für die Bedrohungsanalyse

Das Dashboard für die Bedrohungsanalyse ist ein guter Ausgangspunkt für den Zugriff auf die Berichte, die für Ihre Organisation am relevantesten sind. Sie fasst die Bedrohungen in den folgenden Abschnitten zusammen:

- **Aktuelle Bedrohungen**– listet die zuletzt veröffentlichten Bedrohungsberichte sowie die Anzahl der Geräte mit aktiven und aufgelösten Warnungen auf.
- **Bedrohungen** mit hoher Auswirkung – listet die Bedrohungen auf, die die größten Auswirkungen auf die Organisation hatten. In diesem Abschnitt werden Bedrohungen anhand der Anzahl der Geräte mit aktiven Warnungen bewertet.
- Zusammenfassung der **Bedrohungen**– zeigt die Gesamtauswirkungen von nachverfolgten Bedrohungen, indem die Anzahl der Bedrohungen mit aktiven und aufgelösten Warnungen angezeigt wird.

Wählen Sie im Dashboard eine Bedrohung aus, um den Bericht für diese Bedrohung anzuzeigen.

![Abbildung eines Dashboards für die Bedrohungsanalyse](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a>Anzeigen eines Berichts zur Bedrohungsanalyse

Jeder Bericht zur Bedrohungsanalyse enthält Informationen in drei Abschnitten: **Übersicht,** **Analystenbericht** und **Risikominderungen.**

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Übersicht: Schnelles Verständnis der Bedrohung, Bewertung der Auswirkungen und Überprüfung von Schutzmaßnahmen

Der Abschnitt **"Übersicht"** bietet eine Vorschau des detaillierten Analystenberichts. Außerdem werden Diagramme bereitgestellt, die die Auswirkungen der Bedrohung für Ihre Organisation und Ihre Gefährdung durch falsch konfigurierte und nicht gepatchte Geräte hervorheben.

![Abbildung des Übersichtsbereichs eines Berichts zur Bedrohungsanalyse ](images/ta-overview.png)
 _( Übersicht) eines Berichts zur Bedrohungsanalyse_

#### <a name="assess-the-impact-to-your-organization"></a>Bewerten der Auswirkungen auf Ihre Organisation
Jeder Bericht enthält Diagramme, die Informationen über die Auswirkungen einer Bedrohung auf die Organisation bereitstellen:
- **Geräte mit Warnungen**– zeigt die aktuelle Anzahl der unterschiedlichen Geräte an, die von der Bedrohung betroffen sind. Ein Gerät wird als **"Aktiv"** kategorisiert, wenn dieser Bedrohung mindestens eine Warnung zugeordnet ist, und **"Behoben",** wenn *alle* Warnungen, die der Bedrohung auf dem Gerät zugeordnet sind, aufgelöst wurden.
- **Geräte mit Warnungen im Laufe** der Zeit – zeigt die Anzahl unterschiedlicher Geräte mit **aktiven** und **aufgelösten** Warnungen im Laufe der Zeit an. Die Anzahl der aufgelösten Warnungen gibt an, wie schnell Ihre Organisation auf Warnungen reagiert, die mit einer Bedrohung verbunden sind. Im Idealfall sollten im Diagramm Warnungen angezeigt werden, die innerhalb weniger Tage aufgelöst wurden.

#### <a name="review-security-resilience-and-posture"></a>Überprüfen der Resilienz und des Sicherheitsstatus
Jeder Bericht enthält Diagramme, die einen Überblick darüber bieten, wie stabil Ihre Organisation gegen eine bestimmte Bedrohung ist:
- **Sicherheitskonfigurationsstatus**– zeigt die Anzahl der Geräte an, die die empfohlenen Sicherheitseinstellungen angewendet haben, die dazu beitragen können, die Bedrohung zu mindern. Geräte gelten als **sicher,** wenn _sie alle_ nachverfolgten Einstellungen angewendet haben.
- **Sicherheitsrisikopatchingstatus**– zeigt die Anzahl der Geräte an, die Sicherheitsupdates oder Patches angewendet haben, die von der Bedrohung ausgenutzte Sicherheitsrisiken beheben.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Analystenbericht: Abrufen von Experten-Einblicken von Microsoft-Sicherheitsexperten
Gehen Sie zum Abschnitt **"Analystenbericht",** um den detaillierten Experten-Schreibvorgang zu lesen. Die meisten Berichte enthalten detaillierte Beschreibungen der Angriffsketten, einschließlich Taktiken und Techniken, die dem MITRE ATT&CK-Framework zugeordnet sind, vollständige Listen mit Empfehlungen und leistungsstarke Anleitungen zur [Bedrohungssuche.](advanced-hunting-overview.md)

[Weitere Informationen zum Analystenbericht](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Gegenmaßnahmen: Überprüfen der Liste der Gegenmaßnahmen und des Status Ihrer Geräte
Überprüfen Sie im Abschnitt **"Gegenmaßnahmen"** die Liste der spezifischen Empfehlungen, die Sie bei der Verbesserung der Ausfallsicherheit Ihrer Organisation gegen die Bedrohung unterstützen können. Die Liste der nachverfolgten Gegenmaßnahmen umfasst:

- **Sicherheitsupdates**– Bereitstellung von Sicherheitsupdates oder Patches für Sicherheitsrisiken
- **Microsoft Defender Antivirus Einstellungen**
  - Security Intelligence-Version
  - Aus der Cloud gelieferter Schutz  
  - Schutz vor potenziell unerwünschten Anwendungen (PUA)
  - Echtzeitschutz
 
Informationen zur Risikominderung in diesem Abschnitt enthalten Daten aus [Bedrohungs- und Sicherheitsrisikomanagement,](next-gen-threat-and-vuln-mgt.md)die auch detaillierte Drilldowninformationen von verschiedenen Links im Bericht enthalten.

![Abbildung des Abschnitts "Risikominderungen" eines ](images/ta-mitigations.png)
 _Abschnitts "Gegenmaßnahmen" eines Bedrohungsanalyseberichts_

## <a name="additional-report-details-and-limitations"></a>Zusätzliche Berichtsdetails und Einschränkungen
Beachten Sie bei der Verwendung der Berichte Folgendes: 

- Daten werden basierend auf Ihrem Rollenbasierten Zugriffssteuerungsbereich (RBAC) bereichsbasiert. Sie sehen den Status von Geräten in [Gruppen, auf die Sie zugreifen können.](machine-groups.md)
- Diagramme enthalten nur Gegenmaßnahmen, die nachverfolgt werden. In der Berichtsübersicht finden Sie weitere Gegenmaßnahmen, die nicht in den Diagrammen angezeigt werden.
- Risikominderungen bieten keine Garantie für vollständige Resilienz. Die bereitgestellten Gegenmaßnahmen spiegeln die bestmöglichen Maßnahmen wider, die zur Verbesserung der Resilienz erforderlich sind.
- Geräte werden als "nicht verfügbar" gezählt, wenn sie keine Daten an den Dienst übertragen haben.
- Antivirusbezogene Statistiken basieren auf Microsoft Defender Antivirus Einstellungen. Geräte mit Antivirenlösungen von Drittanbietern können als "verfügbar gemacht" angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Grundlegendes zum Abschnitt "Analystenbericht"](threat-analytics-analyst-reports.md)
- [Bewerten und Beheben von Sicherheitsschwächen und Gefährdungen](next-gen-threat-and-vuln-mgt.md)
