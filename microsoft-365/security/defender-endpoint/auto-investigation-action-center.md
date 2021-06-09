---
title: Besuchen Sie das Info-Center, um Korrekturmaßnahmen anzuzeigen.
description: Verwenden des Info-Centers zum Anzeigen von Details und Ergebnissen nach einer automatisierten Untersuchung
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
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844910"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Besuchen Sie das Info-Center, um Korrekturmaßnahmen anzuzeigen.

Während und nach einer automatisierten Untersuchung werden Korrekturaktionen für bedrohungserkennungen identifiziert. Abhängig von der jeweiligen Bedrohung und der Konfiguration von [Microsoft Defender für Endpunkt](/windows/security/threat-protection) für Ihre Organisation werden einige Korrekturmaßnahmen automatisch ausgeführt, und andere erfordern eine Genehmigung. Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie ausstehende und abgeschlossene [Abhilfemaßnahmen](manage-auto-investigation.md#remediation-actions) im **Info-Center** anzeigen. 


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEU!) Ein einheitliches Info-Center


Wir freuen uns, ihnen ein neues, einheitliches Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Info-Center im Microsoft 365 Security Center":::

In der folgenden Tabelle wird das neue einheitliche Info-Center mit dem vorherigen Info-Center verglichen.

|Das neue, einheitliche Info-Center  |Das vorherige Info-Center  |
|---------|---------|
|Listet ausstehende und abgeschlossene Aktionen für Geräte und E-Mails an einem Ort auf. <br/>([Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) plus Microsoft Defender für [Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Listet ausstehende und abgeschlossene Aktionen für Geräte auf <br/> ( nur[Microsoft Defender für Endpunkt)](microsoft-defender-endpoint.md)   |
|Befindet sich unter:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Befindet sich unter:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Wählen Sie im Microsoft 365 Security Center **das Info-Center** aus. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigieren zum Info-Center im Microsoft 365 Security Center"::: | Wählen Sie im Microsoft Defender Security Center das  >  **Info-Center** für automatisierte Untersuchungen aus. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigieren zum Info-Center über die Microsoft Defender Security Center":::  |

Das einheitliche Info-Center vereint Korrekturaktionen für Defender für Endpunkt und Defender für Office 365. Es definiert eine gemeinsame Sprache für alle Korrekturmaßnahmen und bietet eine einheitliche Untersuchungserfahrung. 

Sie können das einheitliche Info-Center verwenden, wenn Sie über die entsprechenden Berechtigungen und eines oder mehrere der folgenden Abonnements verfügen:
- [Defender für Endpunkt](microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Weitere Informationen finden Sie unter ["Anforderungen".](/microsoft-365/security/mtp/prerequisites)

## <a name="using-the-action-center"></a>Verwenden des Info-Centers

So gelangen Sie zum einheitlichen Info-Center im verbesserten Microsoft 365 Security Center:
1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **das Info-Center** aus. 

Wenn Sie das Info-Center besuchen, werden zwei Registerkarten angezeigt: **ausstehende Aktionen** und **Verlauf.** In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:

|Registerkarte  |Beschreibung  |
|---------|---------|
|**Ausstehend**     | Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern. Sie können Aktionen einzeln genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie den gleichen Aktionstyp haben (z. B. **Quarantänedatei).** <br/>**TIPP:** Stellen Sie sicher, dass ausstehende Aktionen so schnell wie möglich [überprüft und genehmigt (oder abgelehnt)](manage-auto-investigation.md) werden, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können. |
|**Verlauf**     | Dient als Überwachungsprotokoll für ausgeführte Aktionen, z. B.: <br/>– Korrekturmaßnahmen, die als Ergebnis automatisierter Untersuchungen durchgeführt wurden <br>– Abhilfemaßnahmen, die von Ihrem Sicherheitsteam genehmigt wurden  <br/>– Befehle, die ausgeführt wurden, und Korrekturaktionen, die während der Live Response-Sitzungen angewendet wurden  <br/>– Abhilfemaßnahmen, die von Bedrohungsschutzfeatures in Microsoft Defender Antivirus  <p>Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Abgeschlossene Aktionen rückgängig machen).](manage-auto-investigation.md#undo-completed-actions)       |

Sie können Daten im Info-Center anpassen, sortieren, filtern und exportieren.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Spalten und Filter im Info-Center":::

- Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.
- Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzuzeigen.
- Wählen Sie die Spalten aus, die Sie anzeigen möchten.
- Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein sollen.
- Verwenden Sie Filter, um nur die Elemente anzuzeigen, die Sie sehen möchten.
- Wählen Sie **"Exportieren"** aus, um Ergebnisse in eine .csv Datei zu exportieren. 

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen und Genehmigen von Korrekturaktionen](manage-auto-investigation.md)
- [Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Beheben von Bedrohungen mit Microsoft Defender für Endpunkt](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
