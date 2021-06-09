---
title: Grundlegendes zum Abschnitt "Analystenbericht" in der Bedrohungsanalyse
ms.reviewer: ''
description: Erfahren Sie mehr über den Analystenberichtsabschnitt jedes Berichts zur Bedrohungsanalyse. Erfahren Sie, wie sie Informationen zu Bedrohungen, Risikominderungen, Erkennungen, erweiterten Suchabfragen und mehr bereitstellt.
keywords: Analystenbericht, Bedrohungsanalyse, Erkennungen, erweiterte Suchabfragen, Risikominderungen,
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
ms.openlocfilehash: 2a442a642a71bd6bf3a52dbf3901c4367c2c10d8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844994"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Grundlegendes zum Analystenbericht in der Bedrohungsanalyse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Jeder [Bericht zur Bedrohungsanalyse](threat-analytics.md) enthält dynamische Abschnitte und einen umfassenden schriftlichen Abschnitt, der als _Analystenbericht_ bezeichnet wird. To access this section, open the report about the tracked threat and select the **Analyst report** tab.

![Abbildung des Abschnitts "Analystenbericht" eines Bedrohungsanalyseberichts](images/ta-analyst-report-small.png)

_Abschnitt "Analystenbericht" eines Berichts zur Bedrohungsanalyse_

## <a name="scan-the-analyst-report"></a>Überprüfen des Analystenberichts 
Jeder Abschnitt des Analystenberichts ist darauf ausgelegt, umsetzbare Informationen bereitzustellen. Obwohl Berichte variieren, enthalten die meisten Berichte die abschnitte, die in der folgenden Tabelle beschrieben sind.

| Abschnitt "Bericht" | Beschreibung |
|--|--|
| Kurzfassung | Übersicht über die Bedrohung, einschließlich wann sie zum ersten Mal gesehen wurde, ihre Motivationen, wichtige Ereignisse, wichtige Ziele und unterschiedliche Tools und Techniken. Anhand dieser Informationen können Sie weiter bewerten, wie Sie die Bedrohung im Kontext Ihrer Branche, Ihres geografischen Standorts und Ihres Netzwerks priorisieren können. |
| Analyse | Technische Informationen zu den Bedrohungen, einschließlich der Details eines Angriffs und der Art und Weise, wie Angreifer eine neue Technik oder Angriffsoberfläche nutzen können | 
| MITRE ATT&beobachtete CK-Techniken | Wie beobachtete Techniken dem [MITRE ATT&CK-Angriffsframework](https://attack.mitre.org/) zugeordnet werden | 
| [Schutzmaßnahmen](#apply-additional-mitigations) | Empfehlungen, die die Auswirkungen der Bedrohung beenden oder verringern können. Dieser Abschnitt enthält auch Gegenmaßnahmen, die im Rahmen des Berichts zur Bedrohungsanalyse nicht dynamisch nachverfolgt werden. |
| [Erkennungsdetails](#understand-how-each-threat-can-be-detected) | Spezifische und generische Erkennungen von Microsoft-Sicherheitslösungen, die Aktivitäten oder Komponenten anzeigen können, die mit der Bedrohung verbunden sind. | 
| [Erweiterte Suche](#find-subtle-threat-artifacts-using-advanced-hunting) | [Erweiterte Suchabfragen](advanced-hunting-overview.md) zum proaktiven Identifizieren möglicher Bedrohungsaktivitäten. Die meisten Abfragen werden zur Ergänzung von Erkennungen bereitgestellt, insbesondere für die Suche nach potenziell schädlichen Komponenten oder Verhaltensweisen, die nicht dynamisch als bösartig bewertet werden konnten. | 
| Informationsquellen | Microsoft- und Drittanbieterpublikationen, auf die von Analysten während der Erstellung des Berichts verwiesen wird. Der Inhalt der Bedrohungsanalyse basiert auf Daten, die von Microsoft-Experten überprüft wurden. Informationen aus öffentlich verfügbaren Drittanbieterquellen werden eindeutig als solche identifiziert. | 
| Änderungsprotokoll | Die Zeit, zu der der Bericht veröffentlicht wurde und wann erhebliche Änderungen am Bericht vorgenommen wurden. |

## <a name="apply-additional-mitigations"></a>Anwenden zusätzlicher Gegenmaßnahmen
Die Bedrohungsanalyse verfolgt den [Status von Sicherheitsupdates und sicheren Konfigurationen](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)dynamisch nach. Diese Informationen sind als Diagramme und Tabellen auf der Registerkarte **"Risikominderungen"** verfügbar.

Zusätzlich zu diesen nachverfolgten Gegenmaßnahmen werden im Analystenbericht auch Risikominderungen erläutert, die _nicht_ dynamisch überwacht werden. Hier sind einige Beispiele für wichtige Gegenmaßnahmen, die nicht dynamisch nachverfolgt werden:

- Blockieren von E-Mails mit _LNK-Anlagen_ oder anderen verdächtigen Dateitypen
- Zufällige Wahl von Kennwörtern für lokale Administratoren
- Informieren von Endbenutzern über Phishing-E-Mails und andere Bedrohungsvektoren
- Aktivieren bestimmter [Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)

Sie können zwar die Registerkarte **"Risikominderungen"** verwenden, um Ihren Sicherheitsstatus gegen eine Bedrohung zu bewerten, aber mit diesen Empfehlungen können Sie zusätzliche Schritte zur Verbesserung Ihres Sicherheitsstatus unternehmen. Lesen Sie sorgfältig alle Anleitungen zur Risikominderung im Analystenbericht, und wenden Sie sie nach Möglichkeit an.

## <a name="understand-how-each-threat-can-be-detected"></a>Verstehen, wie die einzelnen Bedrohungen erkannt werden können
Der Analystenbericht enthält auch die Erkennungsfunktionen von Microsoft Defender für Endpunkt Antivirus und _EDR_ (EDR).

### <a name="antivirus-detections"></a>Antiviruserkennungen
Diese Erkennungen sind auf Geräten verfügbar, auf denen [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) aktiviert ist. Wenn diese Erkennungen auf Geräten auftreten, die in Microsoft Defender für Endpunkt integriert wurden, lösen sie auch Warnungen aus, die die Diagramme im Bericht aufleuchten.

>[!NOTE]
>Der Analystenbericht listet auch generische Erkennungen auf, die neben Komponenten oder **Verhaltensweisen,** die für die nachverfolgte Bedrohung spezifisch sind, eine vielzahl von Bedrohungen identifizieren können. Diese generischen Erkennungen spiegeln sich in den Diagrammen nicht wider.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Warnungen zur Endpunkterkennung und -reaktion (EDR)
EDR Warnungen werden für Geräte ausgelöst, [die in Microsoft Defender für Endpunkt integriert](onboard-configure.md)sind. Diese Warnungen basieren in der Regel auf Sicherheitssignalen, die vom Microsoft Defender für Endpunkt-Sensor und anderen Endpunktfunktionen wie Antivirus, Netzwerkschutz, Manipulationsschutz gesammelt werden und als leistungsstarke Signalquellen dienen.

Wie die Liste der Antivirenerkennungen sind einige EDR Warnungen so konzipiert, dass verdächtiges Verhalten, das möglicherweise nicht mit der nachverfolgten Bedrohung in Verbindung gebracht wird, allgemein markiert wird. In solchen Fällen identifiziert der Bericht die Warnung eindeutig als "generisch" und hat keinen Einfluss auf die Diagramme im Bericht.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Suchen nach subtilen Bedrohungsartefakten mithilfe der erweiterten Suche
Während Erkennungen es Ihnen ermöglichen, die nachverfolgte Bedrohung automatisch zu erkennen und zu beenden, hinterlassen viele Angriffsaktivitäten subtile Spuren, die eine zusätzliche Überprüfung erfordern. Einige Angriffsaktivitäten weisen Verhaltensweisen auf, die auch normal sein können, sodass die dynamische Erkennung zu Betriebsgeräuschen oder sogar falsch positiven Ergebnissen führen kann.

[Die erweiterte Suche](advanced-hunting-overview.md) bietet eine Abfrageschnittstelle basierend auf der Kusto-Abfragesprache, die das Auffinden dezenter Indikatoren für Bedrohungsaktivitäten vereinfacht. Außerdem können Sie kontextbezogene Informationen anzeigen und überprüfen, ob Indikatoren mit einer Bedrohung verbunden sind.

Erweiterte Suchabfragen in den Analystenberichten wurden von Microsoft-Analysten überprüft und können im [Abfrage-Editor](https://securitycenter.windows.com/advanced-hunting)für die erweiterte Suche ausgeführt werden. Sie können die Abfragen auch verwenden, um [benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) zu erstellen, die Warnungen für zukünftige Übereinstimmungen auslösen.


## <a name="related-topics"></a>Verwandte Themen
- [Bedrohungsanalyse – Übersicht](threat-analytics.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md) 
- [Regeln für die benutzerdefinierte Erkennung](custom-detection-rules.md)