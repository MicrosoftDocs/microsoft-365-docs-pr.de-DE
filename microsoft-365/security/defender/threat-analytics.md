---
title: Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen
ms.reviewer: ''
description: Erfahren Sie mehr über neue Bedrohungen und Angriffstechniken und wie Sie sie stoppen können. Bewerten Sie deren Auswirkungen auf Ihre Organisation und bewerten Sie die Resilienz Ihrer Organisation.
keywords: Bedrohungsanalyse, Risikobewertung, Microsoft 365 Defender, M365D, Risikominderungsstatus, sichere Konfiguration, Microsoft Defender für Office 365, Microsoft Defender für Office 365 Bedrohungsanalyse, MDO-Bedrohungsanalyse, integrierte MDE- und MDO-Bedrohungsanalysedaten, Integration von Bedrohungsanalysedaten, integrierte Microsoft 365 Defender Bedrohungsanalyse
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6de0cb646eb8c12e4863facdb42c1f9494120f9
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105656"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a>Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


Die Bedrohungsanalyse ist unsere produktinterne Threat Intelligence-Lösung von erfahrenen Microsoft-Sicherheitsexperten, die Sicherheitsteams dabei unterstützt, so effizient wie möglich zu sein, während sie sich neuen Bedrohungen gegenübersehen, einschließlich:

- Aktive Bedrohungsteilnehmer und ihre Kampagnen
- Beliebte und neue Angriffstechniken
- Kritische Sicherheitsrisiken
- Allgemeine Angriffsflächen
- Weit verbreitete Schadsoftware

Sehen Sie sich dieses kurze Video an, um mehr darüber zu erfahren, wie Bedrohungsanalysen Ihnen helfen können, die neuesten Bedrohungen nachzuverfolgen und zu beenden.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

Sie können auf die Bedrohungsanalyse entweder über die obere linke Seite der Navigationsleiste Microsoft 365 Sicherheitsportals oder über eine dedizierte Dashboardkarte zugreifen, die die wichtigsten Bedrohungen in Ihrer Organisation anzeigt. Wenn Sie Einblicke in aktive oder laufende Kampagnen erhalten und wissen, was mithilfe von Bedrohungsanalysen zu tun ist, können Sie Ihr Sicherheitsteam mit fundierten Entscheidungen ausstatten. 

![Abbildung des Dashboards für die Bedrohungsanalyse](../../media/threat-analytics/ta_inlandingpage_mtp.png)

_Zugriff auf Bedrohungsanalysen_

Mit komplexeren Angreifern und neuen Bedrohungen, die häufig und weit verbreitet auftreten, ist es wichtig, schnell zu sein:

- Erkennen und Reagieren auf neue Bedrohungen 
- Erfahren Sie, ob Sie derzeit angegriffen werden.
- Bewerten der Auswirkungen der Bedrohung auf Ihre Ressourcen
- Überprüfen Sie Ihre Resilienz gegenüber bedrohungen oder deren Gefährdung
- Identifizieren Sie die Maßnahmen zur Risikominderung, Wiederherstellung oder Verhinderung, die Sie ergreifen können, um die Bedrohungen zu beenden oder einzudämmen.

Jeder Bericht enthält eine Analyse einer nachverfolgten Bedrohung und umfassende Anleitungen zum Schutz vor dieser Bedrohung. Es enthält auch Daten aus Ihrem Netzwerk, die angeben, ob die Bedrohung aktiv ist und ob Sie über entsprechende Schutzmaßnahmen verfügen.

## <a name="view-the-threat-analytics-dashboard"></a>Anzeigen des Dashboards für die Bedrohungsanalyse

Im Dashboard für die Bedrohungsanalyse ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) werden die Berichte hervorgehoben, die für Ihre Organisation am relevantesten sind. Sie fasst die Bedrohungen in den folgenden Abschnitten zusammen:

- **Aktuelle Bedrohungen**– listet die zuletzt veröffentlichten oder aktualisierten Bedrohungsberichte sowie die Anzahl der aktiven und aufgelösten Warnungen auf.
- **Bedrohungen** mit hoher Auswirkung – listet die Bedrohungen auf, die die größten Auswirkungen auf Ihre Organisation haben. In diesem Abschnitt werden Bedrohungen mit der höchsten Anzahl aktiver und aufgelöster Warnungen zuerst aufgeführt.
- **Bedrohungszusammenfassung**: Bietet die Gesamtauswirkung aller nachverfolgten Bedrohungen, indem die Anzahl der Bedrohungen mit aktiven und aufgelösten Warnungen angezeigt wird.

Wählen Sie im Dashboard eine Bedrohung aus, um den Bericht für diese Bedrohung anzuzeigen.

![Screenshot des Dashboards für die Bedrohungsanalyse](../../media/threat-analytics/ta_dashboard_mtp.png)

_Dashboard für die Bedrohungsanalyse. Sie können auch auf das Suchsymbol klicken, um einen Schlüssel in einem Schlüsselwort im Zusammenhang mit dem Bericht zur Bedrohungsanalyse zu erhalten, den Sie lesen möchten._ 

## <a name="view-a-threat-analytics-report"></a>Anzeigen eines Berichts zur Bedrohungsanalyse

Jeder Bericht zur Bedrohungsanalyse enthält Informationen in mehreren Abschnitten: 

- [**Übersicht**](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [**Analystenbericht**](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [**Verwandte Vorfälle**](#related-incidents-view-and-manage-related-incidents)
- [**Betroffene Ressourcen**](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [**Verhinderte E-Mail-Versuche**](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [**Schutzmaßnahmen**](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Übersicht: Schnelles Verständnis der Bedrohung, Bewertung der Auswirkungen und Überprüfung der Verteidigung

Der Abschnitt **"Übersicht"** bietet eine Vorschau des detaillierten Analystenberichts. Außerdem werden Diagramme bereitgestellt, die die Auswirkungen der Bedrohung für Ihre Organisation und Ihre Gefährdung durch falsch konfigurierte und nicht gepatchte Geräte hervorheben.

![Abbildung des Übersichtsbereichs eines Berichts zur Bedrohungsanalyse](../../media/threat-analytics/ta_overview_mtp.png)

_Übersichtsabschnitt eines Berichts zur Bedrohungsanalyse_

#### <a name="assess-impact-on-your-organization"></a>Bewerten der Auswirkungen auf Ihre Organisation
Jeder Bericht enthält Diagramme, die Informationen über die Auswirkungen einer Bedrohung auf die Organisation bereitstellen:
- **Verwandte Vorfälle**– bietet eine Übersicht über die Auswirkungen der nachverfolgten Bedrohung für Ihre Organisation mit den folgenden Daten:
  - Anzahl der aktiven Warnungen und anzahl der aktiven Vorfälle, denen sie zugeordnet sind
  - Schweregrad der aktiven Vorfälle
- **Warnungen im Laufe** der Zeit – zeigt die Anzahl der **zugehörigen aktiven** und **aufgelösten** Warnungen im Laufe der Zeit an. Die Anzahl der aufgelösten Warnungen gibt an, wie schnell Ihre Organisation auf Warnungen im Zusammenhang mit einer Bedrohung reagiert. Im Idealfall sollten im Diagramm Warnungen angezeigt werden, die innerhalb weniger Tage aufgelöst wurden.
- **Betroffene Ressourcen**– zeigt die Anzahl der unterschiedlichen Geräte und E-Mail-Konten (Postfächer) an, denen derzeit mindestens eine aktive Warnung mit der nachverfolgten Bedrohung zugeordnet ist. Warnungen werden für Postfächer ausgelöst, die Bedrohungs-E-Mails empfangen haben. Überprüfen Sie sowohl die Organisations- als auch die Benutzerrichtlinien auf Außerkraftsetzungen, die die Zustellung von Bedrohungs-E-Mails verursachen.
- **Verhinderte E-Mail-Versuche**– zeigt die Anzahl der E-Mails aus den letzten sieben Tagen an, die entweder vor der Zustellung blockiert oder an den Junk-E-Mail-Ordner übermittelt wurden.

#### <a name="review-security-resilience-and-posture"></a>Überprüfen der Resilienz und des Sicherheitsstatus
Jeder Bericht enthält Diagramme, die einen Überblick darüber bieten, wie stabil Ihre Organisation gegen eine bestimmte Bedrohung ist:
- Status der **sicheren Konfiguration**– zeigt die Anzahl der Geräte mit falsch konfigurierten Sicherheitseinstellungen an. Wenden Sie die empfohlenen Sicherheitseinstellungen an, um die Bedrohung zu mindern. Geräte gelten als **sicher,** wenn _sie alle_ nachverfolgten Einstellungen angewendet haben.
- **Sicherheitsrisikopatchingstatus**– zeigt die Anzahl der anfälligen Geräte an. Wenden Sie Sicherheitsupdates oder Patches an, um von der Bedrohung ausgenutzte Sicherheitsrisiken zu beheben.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Analystenbericht: Abrufen von Experten-Einblicken von Microsoft-Sicherheitsexperten
Lesen Sie im Abschnitt **"Analystenbericht"** den detaillierten Expertenbericht. Die meisten Berichte enthalten detaillierte Beschreibungen von Angriffsketten, einschließlich Taktiken und Techniken, die dem MITRE ATT&CK-Framework zugeordnet sind, vollständige Listen mit Empfehlungen und leistungsstarke Anleitungen zur [Bedrohungssuche.](advanced-hunting-overview.md)

[Weitere Informationen zum Analystenbericht](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a>Verwandte Vorfälle: Anzeigen und Verwalten verwandter Vorfälle
Die Registerkarte **"Verwandte Vorfälle"** enthält die Liste aller Vorfälle im Zusammenhang mit der nachverfolgten Bedrohung. Sie können Vorfälle zuweisen oder Warnungen verwalten, die mit jedem Vorfall verknüpft sind. 

![Abbildung des Abschnitts zu verwandten Vorfällen eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_related_incidents_mtp.png)

_Abschnitt "Verwandte Vorfälle" eines Berichts zur Bedrohungsanalyse_

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a>Betroffene Ressourcen: Abrufen einer Liste betroffener Geräte und Postfächer
Eine Ressource gilt als betroffen, wenn sie von einer aktiven, nicht aufgelösten Warnung betroffen ist. Auf der Registerkarte **"Betroffene Objekte"** sind die folgenden Arten von betroffenen Ressourcen aufgeführt:
- **Betroffene Geräte**– Endpunkte mit nicht aufgelösten Microsoft Defender für Endpunkt-Warnungen. Diese Warnungen werden in der Regel bei Sichtung bekannter Bedrohungsindikatoren und -aktivitäten ausgelöst.
- **Betroffene Postfächer**– Postfächer, die E-Mail-Nachrichten empfangen haben, die Microsoft Defender für Office 365 Warnungen ausgelöst haben. Während die meisten Nachrichten, die Warnungen auslösen, in der Regel blockiert werden, können Richtlinien auf Benutzer- oder Organisationsebene Filter außer Kraft setzen.

![Abbildung des Abschnitts "Betroffene Ressourcen" eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_impacted_assets_mtp.png)

_Abschnitt "Betroffene Ressourcen" eines Bedrohungsanalyseberichts_

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a>Verhinderte E-Mail-Versuche: Blockierte oder Junk-Bedrohungs-E-Mails anzeigen
Microsoft Defender für Office 365 blockiert in der Regel E-Mails mit bekannten Bedrohungsindikatoren, einschließlich bösartiger Links oder Anlagen. In einigen Fällen senden proaktive Filtermechanismen, die auf verdächtige Inhalte prüfen, stattdessen Bedrohungs-E-Mails an den Junk-E-Mail-Ordner. In beiden Fällen ist die Wahrscheinlichkeit, dass Schadsoftwarecode auf dem Gerät gestartet wird, geringer.

Die Registerkarte **"Verhinderte E-Mail-Versuche" listet** alle E-Mails auf, die entweder vor der Zustellung blockiert oder von Microsoft Defender für Office 365 an den Junk-E-Mail-Ordner gesendet wurden. 

![Abbildung des Abschnitts "Verhinderte E-Mail-Versuche" eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

_Abschnitt "Verhinderte E-Mail-Versuche" eines Bedrohungsanalyseberichts_

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Gegenmaßnahmen: Überprüfen der Liste der Gegenmaßnahmen und des Status Ihrer Geräte
Überprüfen Sie im Abschnitt **"Gegenmaßnahmen"** die Liste der spezifischen Empfehlungen, die Sie bei der Verbesserung der Ausfallsicherheit Ihrer Organisation gegen die Bedrohung unterstützen können. Die Liste der nachverfolgten Gegenmaßnahmen umfasst:

- **Sicherheitsupdates**– Bereitstellung unterstützter Software-Sicherheitsupdates für Sicherheitsrisiken, die auf integrierten Geräten gefunden werden
- **Unterstützte Sicherheitskonfigurationen**
  - Aus der Cloud gelieferter Schutz  
  - Schutz vor potenziell unerwünschten Anwendungen (PUA)
  - Echtzeitschutz
 
Die Schadensbegrenzungsinformationen in diesem Abschnitt enthalten Daten aus [Bedrohungs- und Sicherheitsrisikomanagement,](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)die auch detaillierte Drilldowninformationen von verschiedenen Links im Bericht enthalten.

![Abbildung des Abschnitts "Risikominderungen" eines Bedrohungsanalyseberichts mit sicheren Konfigurationsdetails ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ Bild des Abschnitts "Risikominderungen" eines Bedrohungsanalyseberichts mit Sicherheitsrisikodetails](../../media/threat-analytics/ta_mitigations_mtp2.png)

_Abschnitt "Risikominderungen" eines Berichts zur Bedrohungsanalyse_

## <a name="additional-report-details-and-limitations"></a>Zusätzliche Berichtsdetails und Einschränkungen
>[!NOTE]
>Im Rahmen der einheitlichen Sicherheitsumgebung ist die Bedrohungsanalyse jetzt nicht nur für Microsoft Defender für Endpunkt, sondern auch für Microsoft Defender für Office E5-Lizenzinhaber verfügbar.
>Wenn Sie das Microsoft 365 Sicherheitsportal (Microsoft 365 Defender) nicht verwenden, können Sie auch die Berichtsdetails (ohne Microsoft Defender für Office Daten) im Microsoft Defender Security Center-Portal (Microsoft Defender für Endpunkt) anzeigen. 

Für den Zugriff auf den Bericht zur Bedrohungsanalyse benötigen Sie bestimmte Rollen und Berechtigungen. Weitere Informationen finden Sie [unter "Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung" für Microsoft 365 Defender.](custom-roles.md)
  - Um Warnungen, Vorfälle oder betroffene Ressourcendaten anzuzeigen, benötigen Sie Berechtigungen für Microsoft Defender für Office- oder Microsoft Defender für Endpunkt-Warnungsdaten oder beides.
  - Um verhinderte E-Mail-Versuche anzuzeigen, benötigen Sie Berechtigungen für Microsoft Defender für Office-Suchdaten. 
  - Zum Anzeigen von Gegenmaßnahmen benötigen Sie Berechtigungen zum Bedrohungs- und Sicherheitsrisikomanagement von Daten in Microsoft Defender für Endpunkt.

Beachten Sie beim Betrachten der Daten zur Bedrohungsanalyse die folgenden Faktoren:
- Diagramme enthalten nur Gegenmaßnahmen, die nachverfolgt werden. In der Berichtsübersicht finden Sie weitere Gegenmaßnahmen, die nicht in den Diagrammen angezeigt werden.
- Risikominderungen bieten keine Garantie für vollständige Resilienz. Die bereitgestellten Gegenmaßnahmen spiegeln die bestmöglichen Maßnahmen wider, die zur Verbesserung der Resilienz erforderlich sind.
- Geräte werden als "nicht verfügbar" gezählt, wenn sie keine Daten an den Dienst übertragen haben.
- Antivirusbezogene Statistiken basieren auf Microsoft Defender Antivirus Einstellungen. Geräte mit Antivirenlösungen von Drittanbietern können als "verfügbar gemacht" angezeigt werden.

## <a name="related-topics"></a>Ähnliche Themen
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Grundlegendes zum Abschnitt "Analystenbericht"](threat-analytics-analyst-reports.md)
- [Bewerten und Beheben von Sicherheitsschwächen und Gefährdungen](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
