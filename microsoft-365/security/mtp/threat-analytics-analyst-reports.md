---
title: Verstehen des Abschnitts "Analystenbericht" in der Bedrohungsanalyse
ms.reviewer: ''
description: Erfahren Sie mehr über den Abschnitt "Analystenbericht" jedes Berichts zur Bedrohungsanalyse. Erfahren Sie, wie sie Informationen zu Bedrohungen, Risikominderungen, Erkennungen, Abfragen zur erweiterten Suche und vielem mehr bietet.
keywords: Analystenbericht, Bedrohungsanalyse, Erkennungen, erweiterte Suchabfragen, Gegenmaßnahmen,
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167561"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Verstehen des Analystenberichts in der Bedrohungsanalyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Jeder [Bericht zur Bedrohungsanalyse](threat-analytics.md) enthält dynamische Abschnitte und einen umfassenden schriftlichen Abschnitt, der als _Analystenbericht bezeichnet wird._ Öffnen Sie den Bericht über die nachverfolgte Bedrohung, und wählen Sie die Registerkarte **"Analystenbericht"** aus, um auf diesen Abschnitt zu zugreifen.

![Abbildung des Abschnitts "Analystenbericht" eines Berichts zur Bedrohungsanalyse](../../media/threat-analytics/ta_analystreport_mtp.png)

_Abschnitt "Analystenbericht" eines Berichts zur Bedrohungsanalyse_

## <a name="scan-the-analyst-report"></a>Überprüfen des Analystenberichts 
Jeder Abschnitt des Analystenberichts dient zur Bereitstellung von Informationen mit Aktionen. Während die Berichte variieren, enthalten die meisten Berichte die in der folgenden Tabelle beschriebenen Abschnitte.

| Abschnitt "Report" | Beschreibung |
|--|--|
| Kurzfassung | Übersicht über die Bedrohung, einschließlich des Ersten Sehens, ihrer Motivationen, wichtiger Ereignisse, wichtiger Ziele und unterschiedlicher Tools und Techniken. Sie können diese Informationen verwenden, um weiter zu bewerten, wie die Bedrohung im Kontext Ihrer Branche, Ihres geografischen Standorts und Ihres Netzwerks priorisiert wird. |
| Analyse | Technische Informationen zu den Bedrohungen, einschließlich der Details eines Angriffs und dazu, wie Angreifer eine neue Technik oder Angriffsfläche nutzen können | 
| BEOBACHTETe MITRE ATT&-CK-Techniken | Zuordnung beobachteter Techniken zum [MITRE ATT&CK-Angriffsframework](https://attack.mitre.org/) | 
| [Gegenmaßnahmen](#apply-additional-mitigations) | Empfehlungen, mit deren Hilfe die Auswirkungen der Bedrohung beendet oder reduziert werden können. Dieser Abschnitt enthält auch Gegenmaßnahmen, die nicht dynamisch als Teil des Berichts zur Bedrohungsanalyse nachverfolgt werden. |
| [Erkennungsdetails](#understand-how-each-threat-can-be-detected) | Spezifische und generische Erkennungen von Microsoft-Sicherheitslösungen, die Aktivitäten oder Komponenten im Zusammenhang mit der Bedrohung verfügbar machen können. | 
| [Erweiterte Suche](#find-subtle-threat-artifacts-using-advanced-hunting) | [Erweiterte Suchabfragen zur](advanced-hunting-overview.md) proaktiven Identifizierung möglicher Bedrohungsaktivitäten. Die meisten Abfragen werden bereitgestellt, um Erkennungen zu ergänzen, insbesondere für die Suche nach potenziell schädlichen Komponenten oder Verhaltensweisen, die nicht dynamisch als bösartig bewertet werden konnten. | 
| Informationsquellen | Microsoft- und Drittanbieterpublikationen, auf die von Analysten während der Erstellung des Berichts verwiesen wird. Die Inhalte der Bedrohungsanalyse basieren auf Daten, die von Microsoft-Forschungsexperten überprüft wurden. Informationen aus öffentlich verfügbaren Drittanbieterquellen werden eindeutig als solche identifiziert. | 
| Änderungsprotokoll | Der Zeitpunkt der Veröffentlichung des Berichts und der Zeitpunkt, zu dem wesentliche Änderungen am Bericht vorgenommen wurden. |

## <a name="apply-additional-mitigations"></a>Anwenden zusätzlicher Gegenmaßnahmen
Die Bedrohungsanalyse verfolgt den [Status von Sicherheitsupdates und sicheren Konfigurationen dynamisch nach.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Diese Informationen sind als Diagramme und Tabellen auf der Registerkarte **"Gegenmaßnahmen"** verfügbar.

Zusätzlich zu diesen nachverfolgten Gegenmaßnahmen werden im Analystenbericht auch Gegenmaßnahmen behandelt, die _nicht_ dynamisch überwacht werden. Hier sind einige Beispiele für wichtige Gegenmaßnahmen, die nicht dynamisch nachverfolgt werden:

- Blockieren von E-Mails _mit LNK-Anlagen_ oder anderen verdächtigen Dateitypen
- Zufällige Lokale Administratorkennwörter
- Informieren von Endbenutzern über Phishing-E-Mails und andere Bedrohungsvektoren
- Aktivieren bestimmter Regeln [zur Reduzierung der Angriffsfläche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Sie können zwar  die Registerkarte "Gegenmaßnahmen" verwenden, um Ihre Sicherheitslage gegen eine Bedrohung zu bewerten, aber mit diesen Empfehlungen können Sie zusätzliche Schritte zur Verbesserung Ihrer Sicherheitslage unternehmen. Lesen Sie sorgfältig alle Anleitungen zur Risikominderung im Analystenbericht, und wenden Sie sie wann immer möglich an.

## <a name="understand-how-each-threat-can-be-detected"></a>Verstehen, wie jede Bedrohung erkannt werden kann
Der Analystenbericht bietet auch die Erkennungen von Microsoft Defender for Endpoint Antivirus- und Endpunkterkennungs- und _-reaktionsfunktionen_ (Endpoint Detection and Response, EDR).

### <a name="antivirus-detections"></a>Antiviruserkennungen
Diese Erkennungen sind auf Geräten verfügbar, auf den [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) aktiviert ist. Wenn diese Erkennungen auf Geräten auftreten, die in Microsoft Defender for Endpoint onboarded wurden, lösen sie auch Warnungen aus, die die Diagramme im Bericht aufleuchten.

>[!NOTE]
>Der Analystenbericht listet außerdem **generische** Erkennungen auf, die eine vielzahl von Bedrohungen sowie Komponenten oder Verhaltensweisen für die verfolgte Bedrohung identifizieren können. Diese generischen Erkennungen spiegeln sich nicht in den Diagrammen wider.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Endpunkterkennungs- und -reaktionswarnungen (Endpoint Detection and Response, EDR)
EDR-Warnungen werden für Geräte [ausgelöst, die in Microsoft Defender for Endpoint integrierte Geräte sind.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Diese Warnungen beruhen im Allgemeinen auf Sicherheitssignalen, die vom Microsoft Defender für Endpunktsensor erfasst werden, und anderen Endpunktfunktionen, z. B. Antivirus, Netzwerkschutz, Manipulationsschutz, die als leistungsstarke Signalquellen dienen.

Wie die Liste der Antivirenerkennungen sind einige EDR-Warnungen darauf ausgelegt, verdächtiges Verhalten allgemein zu kennzeichnen, das möglicherweise nicht mit der nachverfolgten Bedrohung verknüpft ist. In solchen Fällen identifiziert der Bericht die Warnung eindeutig als "generisch" und hat keinen Einfluss auf die Diagramme im Bericht.

### <a name="email-related-detections-and-mitigations"></a>E-Mail-bezogene Erkennungen und Gegenmaßnahmen
E-Mail-bezogene Erkennungen und Gegenmaßnahmen von Microsoft Defender für Office 365 sind zusätzlich zu den bereits von Microsoft Defender für Endpoint verfügbaren Endpunktdaten in Analystenberichten enthalten. 

Informationen zu verhinderten E-Mail-Versuchen geben Ihnen Einblicke, ob Ihre Organisation Ziel der Bedrohung war, die im Analystenbericht angegangen wurde, auch wenn der Angriff effektiv blockiert wurde, bevor er zugestellt oder an den Junk-E-Mail-Ordner zugestellt wurde.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Suchen nach subtilen Bedrohungsartefakten mithilfe der erweiterten Suche
Während Erkennungen es Ihnen ermöglichen, die nachverfolgte Bedrohung automatisch zu identifizieren und zu beenden, hinterlassen viele Angriffsaktivitäten subtile Ablaufverfolgungen, die zusätzliche Überprüfung erfordern. Einige Angriffsaktivitäten weisen Verhaltensweisen auf, die auch normal sein können, sodass die dynamische Erkennung zu Betriebsgeräuschen oder sogar zu falsch positiven Ergebnisse führen kann.

[Die erweiterte Suche](advanced-hunting-overview.md) bietet eine Abfrageschnittstelle auf der Grundlage der Kusto-Abfragesprache, die die Suche nach subtilen Indikatoren für Bedrohungsaktivitäten vereinfacht. Außerdem können Sie kontextbezogene Informationen anzeigen und überprüfen, ob Indikatoren mit einer Bedrohung verbunden sind.

Erweiterte Suchabfragen in den Analystenberichten wurden von Microsoft Analysten überprüft und sind bereit für Sie, im [Advanced Hunting Query Editor ausgeführt zu werden.](https://security.microsoft.com/advanced-hunting) Sie können die Abfragen auch verwenden, um benutzerdefinierte Erkennungsregeln [zu](custom-detection-rules.md) erstellen, die Warnungen für zukünftige Übereinstimmungen auslösen.


>[!NOTE]
> Die Bedrohungsanalyse ist auch in [Microsoft Defender for Endpoint verfügbar.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Es verfügt jedoch nicht über die Datenintegration zwischen Microsoft Defender für Office und Microsoft Defender for Endpoint, die Microsoft 365 Defender Threat Analytics hat.


## <a name="related-topics"></a>Verwandte Themen
- [Bedrohungsanalyse – Übersicht](threat-analytics.md)
- [Proaktives Aufsuchen von Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md)
