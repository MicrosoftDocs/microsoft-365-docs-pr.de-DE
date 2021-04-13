---
title: Nachverfolgen und Reagieren auf neue Bedrohungen mit Microsoft Defender for Endpoint Threat Analytics
ms.reviewer: ''
description: Erfahren Sie mehr über neue Bedrohungen und Angriffstechniken und deren Beenden. Bewerten Sie ihre Auswirkungen auf Ihre Organisation und bewerten Sie Die Ausfallsicherheit Ihrer Organisation.
keywords: Bedrohungsanalyse, Risikobewertung, Betriebssystemminderung, Mikrocodeminderung, Risikominderungsstatus
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
ms.openlocfilehash: 61b6b0c19730045468c77e5f24bf18470aa5dbd5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688261"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a>Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Da anspruchsvollere Gegner und neue Bedrohungen häufig und weit verbreitet entstehen, ist es wichtig, schnell in der Lage zu sein:

- Bewerten der Auswirkungen neuer Bedrohungen
- Überprüfen Der Ausfallsicherheit gegenüber oder der Gefährdung der Bedrohungen
- Identifizieren der Aktionen, die Sie zum Beenden oder Eindähen der Bedrohungen ergreifen können

Die Bedrohungsanalyse ist eine Reihe von Berichten von Microsoft-Sicherheitsexperten, die die relevantesten Bedrohungen abdecken, einschließlich:

- Aktive Bedrohungsakteure und ihre Kampagnen
- Beliebte und neue Angriffstechniken
- Kritische Sicherheitsrisiken
- Allgemeine Angriffsoberflächen
- Verbreitete Schadsoftware

Jeder Bericht enthält eine detaillierte Analyse einer Bedrohung und umfassende Anleitungen zum Schutz vor dieser Bedrohung. Es enthält auch Daten aus Ihrem Netzwerk, die angeben, ob die Bedrohung aktiv ist und ob Sie über entsprechende Schutzmaßnahmen verfügen.

Sehen Sie sich dieses kurze Video an, um mehr darüber zu erfahren, wie Sie mithilfe von Bedrohungsanalysen die neuesten Bedrohungen nachverfolgen und beenden können.
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a>Anzeigen des Dashboards für die Bedrohungsanalyse

Das Dashboard für die Bedrohungsanalyse ist ein hervorragender Ausgangspunkt, um zu den Berichten zu kommen, die für Ihre Organisation am relevantesten sind. Es fasst die Bedrohungen in den folgenden Abschnitten zusammen:

- **Neueste Bedrohungen**– listet die zuletzt veröffentlichten Bedrohungsberichte sowie die Anzahl der Geräte mit aktiven und aufgelösten Warnungen auf.
- **Bedrohungen mit hoher** Auswirkung – listet die Bedrohungen auf, die die höchsten Auswirkungen auf die Organisation hatten. In diesem Abschnitt werden Bedrohungen nach der Anzahl der Geräte mit aktiven Warnungen enteilt.
- **Bedrohungszusammenfassung**– zeigt die Gesamtwirkung von nachverfolgten Bedrohungen, indem die Anzahl der Bedrohungen mit aktiven und aufgelösten Warnungen angezeigt wird.

Wählen Sie eine Bedrohung aus dem Dashboard aus, um den Bericht für diese Bedrohung anzuzeigen.

![Abbildung eines Dashboards für die Bedrohungsanalyse](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a>Anzeigen eines Berichts zur Bedrohungsanalyse

Jeder Bericht zur Bedrohungsanalyse enthält Informationen in drei Abschnitten: **Overview**, **Analyst report** und **Mitigations**.

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Übersicht: Schnelles Verständnis der Bedrohung, Bewerten der Auswirkungen und Überprüfen der Abwehr

Der **Abschnitt Übersicht** bietet eine Vorschau des detaillierten Analystenberichts. Außerdem enthält sie Diagramme, die die Auswirkungen der Bedrohung für Ihre Organisation und Ihre Gefährdung durch falsch konfigurierte und nicht gepatchte Geräte hervorheben.

![Abbildung des Abschnitts "Übersicht" eines Berichts zur Bedrohungsanalyse ](images/ta-overview.png)
 _(Übersicht) eines Berichts zur Bedrohungsanalyse_

#### <a name="assess-the-impact-to-your-organization"></a>Bewerten der Auswirkungen auf Ihre Organisation
Jeder Bericht enthält Diagramme, die Informationen zu den organisatorischen Auswirkungen einer Bedrohung liefern sollen:
- **Geräte mit Warnungen**– zeigt die aktuelle Anzahl unterschiedlicher Geräte an, die von der Bedrohung betroffen sind. Ein Gerät wird als **Aktiv** kategorisiert, wenn dieser Bedrohung mindestens  eine Warnung zugeordnet ist, und **Resolved,** wenn alle Warnungen im Zusammenhang mit der Bedrohung auf dem Gerät aufgelöst wurden.
- **Geräte mit Warnungen im** Laufe der Zeit – zeigt die Anzahl unterschiedlicher Geräte mit **aktiven** und **aufgelösten** Warnungen im Laufe der Zeit an. Die Anzahl der aufgelösten Warnungen gibt an, wie schnell Ihre Organisation auf Warnungen reagiert, die einer Bedrohung zugeordnet sind. Idealerweise sollte das Diagramm Warnungen anzeigen, die innerhalb weniger Tage aufgelöst wurden.

#### <a name="review-security-resilience-and-posture"></a>Überprüfen der Ausfallsicherheit und -haltung
Jeder Bericht enthält Diagramme, die einen Überblick darüber bieten, wie widerstandsfähig Ihre Organisation gegen eine bestimmte Bedrohung ist:
- **Sicherheitskonfigurationsstatus**: Zeigt die Anzahl der Geräte an, die die empfohlenen Sicherheitseinstellungen angewendet haben, um die Bedrohung zu mindern. Geräte gelten als **sicher,** wenn sie _alle_ nachverfolgten Einstellungen angewendet haben.
- **Status des Sicherheitsrisikopatchings**– Zeigt die Anzahl der Geräte an, auf die Sicherheitsupdates oder Patches angewendet wurden, die Sicherheitsrisiken ausnutzen, die von der Bedrohung ausgenutzt wurden.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Analystenbericht: Experten-Einblick von Microsoft-Sicherheitsforschern erhalten
Wechseln Sie zum **Abschnitt Analyst report,** um die detaillierten Experten-Schreibzugriffe zu lesen. Die meisten Berichte enthalten detaillierte Beschreibungen von Angriffsketten, einschließlich Taktiken und Techniken, die dem MITRE ATT&CK-Framework zugeordnet sind, umfassende Empfehlungen und leistungsstarke Anleitungen zur [Bedrohungssuche.](advanced-hunting-overview.md)

[Weitere Informationen zum Analystenbericht](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Gegenmaßnahmen: Überprüfen der Liste der Gegenmaßnahmen und des Status Ihrer Geräte
Überprüfen Sie **im Abschnitt** Gegenmaßnahmen die Liste der spezifischen Empfehlungen für Aktionen, die Ihnen helfen können, Ihre Ausfallsicherheit gegenüber der Bedrohung zu erhöhen. Die Liste der nachverfolgten Gegenmaßnahmen umfasst:

- **Sicherheitsupdates**– Bereitstellung von Sicherheitsupdates oder Patches für Sicherheitsrisiken
- **Microsoft Defender Antivirus-Einstellungen**
  - Security Intelligence Version
  - In der Cloud zugestellter Schutz  
  - Schutz potenziell unerwünschter Anwendungen (PUA)
  - Echtzeitschutz
 
Informationen zur Risikominderung in [](next-gen-threat-and-vuln-mgt.md)diesem Abschnitt enthalten Daten aus der Bedrohungs- und Sicherheitsrisikoverwaltung, die auch detaillierte Drilldowninformationen aus verschiedenen Links im Bericht enthält.

![Abbildung des Abschnitts "Gegenmaßnahmen" eines Berichts "Risikoanalysemaßnahmen" eines ](images/ta-mitigations.png)
 _Berichts zur Bedrohungsanalyse_

## <a name="additional-report-details-and-limitations"></a>Zusätzliche Berichtsdetails und Einschränkungen
Beachten Sie bei der Verwendung der Berichte Folgendes: 

- Die Daten werden basierend auf ihrem rollenbasierten Zugriffssteuerungsbereich (RBAC) bereichiert. Sie sehen den Status von Geräten in [Gruppen, auf die Sie zugreifen können.](machine-groups.md)
- Diagramme spiegeln nur nachverfolgte Gegenmaßnahmen wider. Überprüfen Sie die Berichtsübersicht auf zusätzliche Gegenmaßnahmen, die nicht in den Diagrammen angezeigt werden.
- Gegenmaßnahmen garantieren keine vollständige Ausfallsicherheit. Die bereitgestellten Gegenmaßnahmen spiegeln die bestmöglichen Maßnahmen wider, die zur Verbesserung der Ausfallsicherheit erforderlich sind.
- Geräte werden als "nicht verfügbar" gezählt, wenn sie keine Daten an den Dienst übermittelt haben.
- Antivirusbezogene Statistiken basieren auf Microsoft Defender Antivirus-Einstellungen. Geräte mit Antivirenlösungen von Drittanbietern können als "verfügbar" angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen
- [Proaktives Aufsuchen von Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Verstehen des Abschnitts "Analystenbericht"](threat-analytics-analyst-reports.md)
- [Bewerten und Beheben von Sicherheitsschwächen und -risiken](next-gen-threat-and-vuln-mgt.md)