---
title: Bedrohungsschutzbericht in Microsoft Defender for Endpoint
description: Nachverfolgen von Warnungserkennungen, Kategorien und Schweregrad mithilfe des Bedrohungsschutzberichts
keywords: Warnungserkennung, Quelle, Warnung nach Kategorie, Warnungsschweregrad, Warnungsklassifizierung, Ermittlung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688981"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Bedrohungsschutzbericht in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Der Bericht zum Schutz vor Bedrohungen enthält informationen auf hoher Ebene zu in Ihrer Organisation generierten Warnungen. Der Bericht enthält Trendinformationen, die die Erkennungsquellen, Kategorien, Schweregrade, Status, Klassifizierungen und Ermittlungen von Warnungen über einen bestimmten Zeitraum hinweg anzeigen.

Das Dashboard ist in zwei Abschnitte unterteilt:

![Abbildung des Bedrohungsschutzberichts](images/threat-protection-reports.png)

Abschnitt | Beschreibung 
:---|:---
1 | Benachrichtigungstrends
2 | Warnungszusammenfassung

## <a name="alert-trends"></a>Warnungstrends
Standardmäßig werden in den Warnungstrends Warnungsinformationen aus dem 30-Tage-Zeitraum angezeigt, der am letzten ganztägigen Tag endet. Um eine bessere Perspektive für Trends in Ihrer Organisation zu gewinnen, können Sie den Berichtszeitraum optimieren, indem Sie den angezeigten Zeitraum anpassen. Wählen Sie einen Zeitraum aus den Dropdownoptionen aus, um den Zeitraum anzupassen:

- 30 Tage
- 3 Monate
- 6 Monate
- Benutzerdefiniert

>[!NOTE]
>Diese Filter werden nur auf den Abschnitt Warnungstrends angewendet. Der Abschnitt "Warnungszusammenfassung" hat keine Auswirkungen.


## <a name="alert-summary"></a>Warnungszusammenfassung
Während die Warnungstrends trendende Warnungsinformationen zeigen, werden in der Warnungszusammenfassung Benachrichtigungsinformationen angezeigt, die auf den aktuellen Tag begrenzt sind.

 Mit der Warnungszusammenfassung können Sie einen Drilldown zu einer bestimmten Warnwarteschlange mit dem entsprechenden Filter erstellen. Wenn Sie beispielsweise auf der Karte Erkennungsquellen auf die EDR-Leiste klicken, erhalten Sie die Benachrichtigungswarteschlange mit Ergebnissen, die nur Warnungen anzeigen, die von EDR-Erkennungen generiert wurden. 

>[!NOTE]
>Die im Zusammenfassungsabschnitt angezeigten Daten sind auf 180 Tage vor dem aktuellen Datum begrenzt. Wenn das heutige Datum beispielsweise der 5. November 2019 ist, werden die Daten im Zusammenfassungsabschnitt Zahlen vom 5. Mai 2019 bis zum 5. November 2019 widerspiegeln.<br>
> Der auf den Abschnitt Trends angewendete Filter wird nicht auf den Zusammenfassungsabschnitt angewendet. 

## <a name="alert-attributes"></a>Warnungsattribute
Der Bericht besteht aus Karten, die die folgenden Warnungsattribute anzeigen:

- **Erkennungsquellen**: enthält Informationen zu den Sensoren und Erkennungstechnologien, die die von Microsoft Defender for Endpoint zum Auslösen von Warnungen verwendeten Daten bereitstellen.

- **Bedrohungskategorien**: zeigt die Arten von Bedrohungs- oder Angriffsaktivitäten an, die Warnungen ausgelöst haben, und gibt mögliche Fokusbereiche für Ihre Sicherheitsvorgänge an.

- **Schweregrad**: zeigt den Schweregrad von Warnungen an, der die kollektiven potenziellen Auswirkungen von Bedrohungen für Ihre Organisation und die Reaktionsebene angibt, die für ihre Reaktion erforderlich ist.

- **Status**: zeigt den Auflösungsstatus von Warnungen an, der die Effizienz Ihrer manuellen Warnungsantworten und der automatisierten Korrektur angibt (sofern aktiviert). 

- **Klassifizierung & Bestimmung**: zeigt, wie Sie Warnungen bei der Lösung klassifiziert haben, ob Sie sie als tatsächliche Bedrohungen (echte Warnungen) oder als falsche Erkennungen (falsche Warnungen) klassifiziert haben. Diese Karten zeigen auch die Ermittlung aufgelöster Warnungen und bieten zusätzliche Einblicke, z. B. die Art der tatsächlich gefundenen Bedrohungen oder die legitimen Aktivitäten, die falsch erkannt wurden.


 

## <a name="filter-data"></a>Filtern von Daten

Verwenden Sie die bereitgestellten Filter, um Warnungen mit bestimmten Attributen ein- oder auszuschließen.

>[!NOTE]
>Diese Filter gelten **für alle** Karten im Bericht.

So zeigen Sie beispielsweise nur Daten zu Warnungen mit hohem Schweregrad an:

1. Wählen **Sie unter Filter > Schweregrad** die Option Hoch **aus.**
2. Stellen Sie sicher, dass alle anderen Optionen unter **Schweregrad** deaktiviert sind.
3. Wählen Sie **Anwenden** aus. 

## <a name="related-topic"></a>Verwandtes Thema
- [Bericht über Geräteintegität und -kompatibilität](machine-reports.md)
