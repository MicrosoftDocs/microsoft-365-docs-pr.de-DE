---
title: Besuchen Sie das Aktionscenter, um Korrekturaktionen zu sehen
description: Verwenden des Aktionscenters zum Anzeigen von Details und Ergebnissen nach einer automatisierten Untersuchung
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: e51cc1d613e6f9e7ab96653692362ed7fe239e3e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274844"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Besuchen Sie das Aktionscenter, um Korrekturaktionen zu sehen

Während und nach einer automatisierten Untersuchung werden Abhilfemaßnahmen für Bedrohungserkennungen identifiziert. Abhängig von der jeweiligen Bedrohung und der Konfiguration [von Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) für Ihre Organisation werden einige Korrekturaktionen automatisch ausgeführt, und andere erfordern eine Genehmigung. Wenn Sie Teil des Sicherheitsbetriebsteams Ihrer Organisation sind, können Sie ausstehende und abgeschlossene Korrekturaktionen [im](manage-auto-investigation.md#remediation-actions) **Aktionscenter anzeigen.** 


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEU!) Ein einheitliches Aktionscenter


Wir freuen uns, ein neues, einheitliches Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Action Center in Microsoft 365 Security Center":::

In der folgenden Tabelle wird das neue, einheitliche Aktionscenter mit dem vorherigen Aktionscenter verglichen.

|Das neue, einheitliche Aktionscenter  |Das vorherige Aktionscenter  |
|---------|---------|
|Listet ausstehende und abgeschlossene Aktionen für Geräte und E-Mails an einem Speicherort auf. <br/>([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender for [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))|Listet ausstehende und abgeschlossene Aktionen für Geräte auf <br/> ([Nur Microsoft Defender for Endpoint)](microsoft-defender-endpoint.md)   |
|Befindet sich unter:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Befindet sich unter:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Wählen Sie im Microsoft 365 Sicherheitscenter die Option **Aktionscenter aus.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigieren zum Aktionscenter im Microsoft 365 Security Center"::: | Wählen Sie im Microsoft Defender Security Center Aktionscenter automatisierte  >  **Untersuchungen aus.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigieren zum Aktionscenter von der Microsoft Defender Security Center":::  |

Im einheitlichen Aktionscenter werden Korrekturaktionen in Defender for Endpoint und Defender for Office 365. Es definiert eine gemeinsame Sprache für alle Korrekturaktionen und bietet eine einheitliche Untersuchungserfahrung. 

Sie können das einheitliche Aktionscenter verwenden, wenn Sie über entsprechende Berechtigungen und mindestens eines der folgenden Abonnements verfügen:
- [Defender für Endpunkt](microsoft-defender-endpoint.md)
- [Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Weitere Informationen finden Sie unter [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Verwenden des Aktionscenters

So kommen Sie zum einheitlichen Aktionscenter im Microsoft 365 Security Center:
1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Aktionscenter aus.** 

Wenn Sie das Aktionscenter besuchen, werden zwei Registerkarten angezeigt: **Ausstehende Aktionen** und **Verlauf**. In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:

|Registerkarte  |Beschreibung  |
|---------|---------|
|**Ausstehend**     | Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern. Sie können Aktionen gleichzeitig genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie denselben Aktionstyp haben (z. B. **Quarantänedatei**). <br/>**TIPP:** Achten Sie darauf, ausstehende Aktionen so schnell wie möglich zu überprüfen und zu genehmigen [(oder](manage-auto-investigation.md) abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können. |
|**Verlauf**     | Dient als Überwachungsprotokoll für Aktionen, die ergriffen wurden, z. B.: <br/>– Abhilfemaßnahmen, die als Ergebnis automatisierter Untersuchungen ergriffen wurden <br>– Korrekturaktionen, die vom Sicherheitsbetriebsteam genehmigt wurden  <br/>– Befehle, die ausgeführt wurden, und Behebungsaktionen, die während Liveantwortsitzungen angewendet wurden  <br/>– Abhilfemaßnahmen, die von Bedrohungsschutzfeatures in Microsoft Defender Antivirus  <p>Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Rückgängig gemachte Aktionen](manage-auto-investigation.md#undo-completed-actions)).       |

Sie können Daten im Aktionscenter anpassen, sortieren, filtern und exportieren.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Spalten und Filter im Aktionscenter":::

- Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.
- Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzeigen zu können.
- Wählen Sie die Spalten aus, die Sie anzeigen möchten.
- Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein müssen.
- Verwenden Sie Filter, um nur die Elemente zu sehen, die Sie anzeigen möchten.
- Wählen **Sie Exportieren** aus, um Ergebnisse in eine .csv exportieren. 

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen und Genehmigen von Korrekturaktionen](manage-auto-investigation.md)
- [Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Behebung von Bedrohungen mit Microsoft Defender for Endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
