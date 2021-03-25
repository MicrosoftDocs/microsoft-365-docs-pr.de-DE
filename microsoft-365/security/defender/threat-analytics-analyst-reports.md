---
title: Verstehen des Abschnitts "Analystenbericht" in der Bedrohungsanalyse
ms.reviewer: ''
description: Erfahren Sie mehr über den Abschnitt "Analystenbericht" jedes Berichts zur Bedrohungsanalyse. Erfahren Sie, wie sie Informationen zu Bedrohungen, Risikominderungen, Erkennungen, erweiterten Suchabfragen und vielem mehr bietet.
keywords: analyst report, threat analytics, detections, advanced hunting queries, mitigations,
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc534b7bec27784ccf25f92ab0282fdbecdc9196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066735"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Verstehen des Analystenberichts in der Bedrohungsanalyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Jeder [Bericht zur Bedrohungsanalyse](threat-analytics.md) enthält dynamische Abschnitte und einen umfassenden schriftlichen Abschnitt namens _Analystenbericht._ Öffnen Sie den Bericht über die nachverfolgte Bedrohung, und wählen Sie die Registerkarte **Analystenbericht** aus, um auf diesen Abschnitt zu zugreifen.

![Abbildung des Abschnitts "Analystenbericht" eines Berichts zur Bedrohungsanalyse](../../media/threat-analytics/ta_analystreport_mtp.png)

_Abschnitt "Analystenbericht" eines Berichts zur Bedrohungsanalyse_

## <a name="scan-the-analyst-report"></a>Überprüfen des Analystenberichts 
Jeder Abschnitt des Analystenberichts ist darauf ausgelegt, aktionenfähige Informationen zur Verfügung zu stellen. Während die Berichte variieren, enthalten die meisten Berichte die in der folgenden Tabelle beschriebenen Abschnitte.

| Abschnitt "Bericht" | Beschreibung |
|--|--|
| Kurzfassung | Übersicht über die Bedrohung, einschließlich wann sie zum ersten Mal gesehen wurde, deren Motivationen, wichtigen Ereignissen, wichtigen Zielen und unterschiedlichen Tools und Techniken. Mithilfe dieser Informationen können Sie die Priorisierung der Bedrohung im Kontext Ihrer Branche, Ihres geografischen Standorts und Ihres Netzwerks weiter bewerten. |
| Analyse | Technische Informationen zu den Bedrohungen, einschließlich der Details eines Angriffs und darüber, wie Angreifer eine neue Technik oder Angriffsfläche nutzen können | 
| MITRE ATT&CK-Techniken beobachtet | Zuordnung beobachteter Techniken zum [MITRE ATT&CK-Angriffsframework](https://attack.mitre.org/) | 
| [Gegenmaßnahmen](#apply-additional-mitigations) | Empfehlungen, mit deren Hilfe die Auswirkungen der Bedrohung beendet oder reduziert werden können. Dieser Abschnitt enthält auch Risikominderungen, die im Rahmen des Berichts zur Bedrohungsanalyse nicht dynamisch nachverfolgt werden. |
| [Erkennungsdetails](#understand-how-each-threat-can-be-detected) | Spezifische und generische Erkennungen, die von Microsoft-Sicherheitslösungen bereitgestellt werden, die mit der Bedrohung verbundene Aktivitäten oder Komponenten darstellen können. | 
| [Erweiterte Suche](#find-subtle-threat-artifacts-using-advanced-hunting) | [Erweiterte Suchabfragen zum](advanced-hunting-overview.md) proaktiven Identifizieren möglicher Bedrohungsaktivitäten. Die meisten Abfragen werden bereitgestellt, um Erkennungen zu ergänzen, insbesondere zum Auffinden potenziell schädlicher Komponenten oder Verhaltensweisen, die nicht dynamisch als schädlich bewertet werden konnten. | 
| Informationsquellen | Microsoft und Drittanbieterpublikationen, auf die analysten während der Erstellung des Berichts verwiesen haben. Inhalte der Bedrohungsanalyse basieren auf Daten, die von Microsoft-Forschern überprüft wurden. Informationen aus öffentlich verfügbaren Drittanbieterquellen werden eindeutig als solche identifiziert. | 
| Änderungsprotokoll | Der Zeitpunkt der Veröffentlichung des Berichts und der Zeitpunkt, zu dem wesentliche Änderungen am Bericht vorgenommen wurden. |

## <a name="apply-additional-mitigations"></a>Anwenden zusätzlicher Gegenmaßnahmen
Die Bedrohungsanalyse verfolgt dynamisch [den Status von Sicherheitsupdates und sicheren Konfigurationen.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Diese Informationen sind als Diagramme und Tabellen auf der Registerkarte **Gegenmaßnahmen** verfügbar.

Zusätzlich zu diesen nachverfolgten Gegenmaßnahmen werden im Analystenbericht auch Risikominderungen behandelt, die _nicht_ dynamisch überwacht werden. Im Folgenden finden Sie einige Beispiele für wichtige Gegenmaßnahmen, die nicht dynamisch nachverfolgt werden:

- Blockieren von E-Mails mit _.lnk-Anlagen_ oder anderen verdächtigen Dateitypen
- Randomize local administrator passwords
- Informieren von Endbenutzern über Phishing-E-Mails und andere Bedrohungsvektoren
- Aktivieren bestimmter [Regeln zur Reduzierung der Angriffsfläche](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Sie können zwar die Registerkarte **Gegenmaßnahmen** verwenden, um Ihre Sicherheitslage gegenüber einer Bedrohung zu bewerten, aber mit diesen Empfehlungen können Sie zusätzliche Schritte zur Verbesserung Ihrer Sicherheitslage unternehmen. Lesen Sie sorgfältig alle Anleitungen zur Risikominderung im Analystenbericht, und wenden Sie sie wann immer möglich an.

## <a name="understand-how-each-threat-can-be-detected"></a>Verstehen, wie jede Bedrohung erkannt werden kann
Der Analystenbericht enthält außerdem die Erkennungen  von Microsoft Defender for Endpoint Antivirus- und Endpunkterkennungs- und -reaktionsfunktionen (EDR).

### <a name="antivirus-detections"></a>Antiviruserkennungen
Diese Erkennungen sind auf Geräten verfügbar, auf [deren Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) aktiviert ist. Wenn diese Erkennungen auf Geräten auftreten, die in Microsoft Defender for Endpoint onboarded wurden, lösen sie auch Warnungen aus, die die Diagramme im Bericht aufscheinen.

>[!NOTE]
>Der Analystenbericht  listet außerdem generische Erkennungen auf, mit denen eine vielzahl von Bedrohungen sowie Komponenten oder Verhaltensweisen identifiziert werden können, die für die verfolgte Bedrohung spezifisch sind. Diese generischen Erkennungen spiegeln sich nicht in den Diagrammen wider.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Endpunkterkennungs- und Reaktionswarnungen (EDR)
EDR-Warnungen werden für Geräte [ausgelöst, die in Microsoft Defender for Endpoint onboarded sind.](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Diese Warnungen beruhen im Allgemeinen auf Sicherheitssignalen, die vom Microsoft Defender for Endpoint-Sensor und anderen Endpunktfunktionen gesammelt werden , z. B. Antivirus, Netzwerkschutz, Manipulationsschutz, die als leistungsfähige Signalquellen dienen.

Wie die Liste der Antivirenerkennungen sind einige EDR-Warnungen so konzipiert, dass verdächtiges Verhalten, das möglicherweise nicht der nachverfolgten Bedrohung zugeordnet ist, allgemein kennzeichnen. In solchen Fällen identifiziert der Bericht die Warnung eindeutig als "generisch" und hat keinen Einfluss auf die Diagramme im Bericht.

### <a name="email-related-detections-and-mitigations"></a>E-Mail-bezogene Erkennungen und Gegenmaßnahmen
E-Mail-bezogene Erkennungen und Risikominderungen von Microsoft Defender für Office 365 sind zusätzlich zu den bereits von Microsoft Defender for Endpoint verfügbaren Endpunktdaten in Analystenberichten enthalten. 

Informationen zu verhinderten E-Mail-Versuchen geben Ihnen Einblicke, ob Ihre Organisation ein Ziel der Bedrohung war, die im Analystenbericht in Angriff genommen wurde, auch wenn der Angriff vor der Zustellung effektiv blockiert oder an den Junk-E-Mail-Ordner zugestellt wurde.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Suchen nach subtilen Bedrohungsartefakten mithilfe der erweiterten Suche
Während Erkennungen es Ihnen ermöglichen, die nachverfolgte Bedrohung automatisch zu identifizieren und zu beenden, hinterlassen viele Angriffsaktivitäten feine Spuren, die eine zusätzliche Überprüfung erfordern. Einige Angriffsaktivitäten weisen Verhaltensweisen auf, die auch normal sein können, sodass die dynamische Erkennung zu Betriebsgeräuschen oder sogar zu falsch positiven Effekten führen kann.

[Die erweiterte Suche](advanced-hunting-overview.md) bietet eine Abfrageschnittstelle, die auf Kusto Query Language basiert und die Suche nach subtilen Indikatoren der Bedrohungsaktivität vereinfacht. Außerdem können Sie kontextbezogene Informationen anzeigen und überprüfen, ob Indikatoren mit einer Bedrohung verbunden sind.

Erweiterte Suchabfragen in den Analystenberichten wurden von Microsoft-Analysten überprüft und können im Editor für erweiterte [Suchabfragen ausgeführt werden.](https://security.microsoft.com/advanced-hunting) Sie können die Abfragen auch verwenden, um benutzerdefinierte Erkennungsregeln [zu](custom-detection-rules.md) erstellen, die Warnungen für zukünftige Übereinstimmungen auslösen.


>[!NOTE]
> Die Bedrohungsanalyse ist auch in [Microsoft Defender for Endpoint verfügbar.](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Es verfügt jedoch nicht über die Datenintegration zwischen Microsoft Defender for Office und Microsoft Defender for Endpoint, über die Microsoft 365 Defender Threat Analytics verfügt.


## <a name="related-topics"></a>Verwandte Themen
- [Bedrohungsanalyse – Übersicht](threat-analytics.md)
- [Proaktives Aufsuchen von Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Regeln für die benutzerdefinierte Erkennung](custom-detection-rules.md)