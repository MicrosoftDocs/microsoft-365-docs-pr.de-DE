---
title: Überprüfen von Korrekturaktionen nach automatisierten Untersuchungen
description: Überprüfen und genehmigen (oder ablehnen) Sie Abhilfemaßnahmen nach einer automatisierten Untersuchung.
keywords: autoir, automatisch, Untersuchung, Erkennung, Korrektur, Aktion, ausstehend, genehmigt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 410972bd823c3a3c4fda53cacc225014d83f3457
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844010"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Überprüfen von Korrekturaktionen nach einer automatisierten Untersuchung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Wartungsaktionen

Wenn eine [automatisierte Untersuchung](automated-investigations.md) ausgeführt wird, wird für jeden untersuchten Nachweis eine Bewertung generiert. Bewertungen können *bösartig,* *verdächtig* oder *keine Bedrohungen gefunden* werden. 

Je

- die Art der Bedrohung, 
- die resultierende Bewertung und 
- Wie die [Gerätegruppen](/microsoft-365/security/defender-endpoint/machine-groups) Ihrer Organisation konfiguriert sind, 

Wartungsaktionen können automatisch oder nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt werden. 

Hier ein paar Beispiele:

- **Beispiel 1:** Die Gerätegruppen von Fabrikam werden auf **"Vollständig"** festgelegt – Bedrohungen werden automatisch behoben (die empfohlene Einstellung). In diesem Fall werden Korrekturmaßnahmen automatisch für Artefakte ausgeführt, die nach einer automatisierten Untersuchung als bösartig eingestuft werden (siehe ["Abgeschlossene Aktionen überprüfen").](#review-completed-actions)

- **Beispiel 2:** Die Geräte von Contoso sind in einer Gerätegruppe enthalten, die auf **"Semi" festgelegt ist. Es ist eine Genehmigung für alle Korrekturen erforderlich.** In diesem Fall muss das Sicherheitsteam von Contoso alle Korrekturaktionen nach einer automatisierten Untersuchung überprüfen und genehmigen (siehe ["Ausstehende Aktionen überprüfen").](#review-pending-actions)

- **Beispiel 3:** Tailspin Toys hat ihre Gerätegruppen auf **"Keine automatisierte Antwort"** festgelegt (nicht empfohlen). In diesem Fall treten keine automatisierten Untersuchungen auf. Es werden keine Korrekturmaßnahmen ausgeführt oder ausstehend, und es werden keine Aktionen im [Info-Center](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) für ihre Geräte protokolliert (siehe ["Verwalten von Gerätegruppen").](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)

Unabhängig davon, ob sie automatisch oder nach Genehmigung durchgeführt wird, kann eine automatisierte Untersuchung zu einer oder mehreren der Korrekturaktionen führen:
- Isolieren einer Datei
- Entfernen eines Registrierungsschlüssels 
- Beenden eines Prozesses 
- Beenden eines Diensts 
- Deaktivieren eines Treibers 
- Entfernen einer geplanten Aufgabe

## <a name="review-pending-actions"></a>Überprüfen ausstehender Aktionen

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Überprüfen Sie die Elemente auf der Registerkarte **"Ausstehend".** 
4. Wählen Sie eine Aktion aus, um den Flyoutbereich zu öffnen.
5. Überprüfen Sie im Flyoutbereich die Informationen, und führen Sie dann einen der folgenden Schritte aus:
   - Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.
   - Wählen Sie **"Gehe Auf Suche"** aus, um zur [erweiterten Suche](advanced-hunting-overview.md)zu gelangen. 

## <a name="review-completed-actions"></a>Überprüfen abgeschlossener Aktionen

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Überprüfen Sie die Elemente auf der Registerkarte **"Verlauf".** 
4. Wählen Sie ein Element aus, um weitere Details zu dieser Korrekturaktion anzuzeigen.
 
## <a name="undo-completed-actions"></a>Abgeschlossene Aktionen rückgängigmachen

Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung ist, können Sie die durchgeführten Abhilfemaßnahmen rückgängigmachen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden. Im Info-Center können Sie auf der Registerkarte **"Verlauf"** eine der folgenden Aktionen rückgängigmachen:  

| Aktionsquelle | Unterstützte Aktionen |
|:---|:---|
| – Automatisierte Untersuchung <br/>- Microsoft Defender Antivirus <br/>– Manuelle Reaktionsaktionen | – Gerät isolieren <br/>– Einschränken der Codeausführung <br/>– Isolieren einer Datei <br/>– Entfernen eines Registrierungsschlüssels <br/>- Beenden eines Diensts <br/>– Deaktivieren eines Treibers <br/>- Entfernen einer geplanten Aufgabe |

### <a name="to-undo-multiple-actions-at-one-time"></a>So machen Sie mehrere Aktionen gleichzeitig rückgängig

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **"Verlauf"** die Aktionen aus, die Sie rückgängig machen möchten. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.
3. Wählen Sie im Flyoutbereich **"Rückgängig"** aus.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei aus der Quarantäne auf mehreren Geräten 

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **Verlauf** ein Element mit dem Aktionstyp **Quarantänedatei** aus.
3. Wählen Sie im Flyoutbereich **"Auf X weitere Instanzen dieser Datei anwenden"** und dann **"Rückgängig"** aus.

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Automatisierungsstufen, automatisierte Untersuchungsergebnisse und resultierende Aktionen

Automatisierungsstufen wirken sich darauf aus, ob bestimmte Korrekturmaßnahmen automatisch oder nur nach der Genehmigung ausgeführt werden. Manchmal muss Ihr Sicherheitsteam je nach den Ergebnissen einer automatisierten Untersuchung weitere Schritte ausführen. In der folgenden Tabelle sind Automatisierungsstufen, Ergebnisse automatisierter Untersuchungen und die jeweiligen Aktionen zusammengefasst. 

|Gerätegruppeneinstellung | Automatisierte Untersuchungsergebnisse | Vorgehensweise |
|:---|:---|:---|
|**Vollständig – Bedrohungen automatisch beheben** (empfohlene Einstellung) |Für einen Nachweis *wird* eine Bewertung des Böswilligen erzielt. <br/><br/>Geeignete Korrekturmaßnahmen werden automatisch ausgeführt. |[Überprüfen abgeschlossener Aktionen](#review-completed-actions) |
|**Vollständig – Bedrohungen automatisch beheben** |Für einen Nachweis wird eine Bewertung des *Verdächtigen* erreicht. <br/><br/>Korrekturaktionen müssen noch genehmigt werden, um fortzufahren. | [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions) |
|**Semi – Genehmigung für jede Korrektur erforderlich**  |Eine Bewertung von *"Bösartig"* oder *"Verdächtig"* wird für einen Nachweis getroffen. <br/><br/>Korrekturaktionen müssen noch genehmigt werden, um fortzufahren.  |[Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions) |
|**Semi – Genehmigung für Kernordner-Korrektur erforderlich** |Für einen Nachweis *wird* eine Bewertung des Böswilligen erzielt. <br/><br/>Wenn es sich bei dem Artefakt um eine Datei oder ausführbare Datei handelt und sich in einem Betriebssystemverzeichnis befindet, z. B. im Ordner Windows oder im Ordner "Programmdateien", stehen Korrekturaktionen noch aus. <br/><br/>Wenn sich das Artefakt *nicht* in einem Betriebssystemverzeichnis befindet, werden korrekturmaßnahmen automatisch ausgeführt. |1. [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)<br/><br/>2. [Überprüfen abgeschlossener Aktionen](#review-completed-actions) |
|**Semi – Genehmigung für Kernordner-Korrektur erforderlich** |Für einen Nachweis wird eine Bewertung des *Verdächtigen* erreicht. <br/><br/>Korrekturaktionen stehen noch aus.  |[Genehmigen (oder ablehnen) ausstehender Aktionen.](#review-pending-actions)|
|**Semi – Genehmigung für Nicht-Temp-Ordner-Korrektur erforderlich** |Für einen Nachweis *wird* eine Bewertung des Böswilligen erzielt. <br/><br/>Wenn es sich bei dem Artefakt um eine Datei oder ausführbare Datei handelt, die sich nicht in einem temporären Ordner befindet, z. B. der Downloadordner des Benutzers oder der temporäre Ordner, stehen Korrekturaktionen an. <br/><br/>Wenn es sich bei dem Artefakt um eine Datei oder ausführbare Datei *handelt,* die sich in einem temporären Ordner befindet, werden korrekturmaßnahmen automatisch ausgeführt.  |1. [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)<br/><br/>2. [Überprüfen abgeschlossener Aktionen](#review-completed-actions)  |
|**Semi – Genehmigung für Nicht-Temp-Ordner-Korrektur erforderlich** |Für einen Nachweis wird eine Bewertung des *Verdächtigen* erreicht. <br/><br/>Korrekturaktionen stehen noch aus. |[Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)  | 
|Eine der **Automatisierungsebenen "Vollständig"** oder **"Semi"** |Für einen Nachweis wird die Bewertung *"Keine Bedrohungen gefunden"* erreicht. <br/><br/>Es werden keine Korrekturmaßnahmen ausgeführt, und es stehen keine Aktionen zur Genehmigung aus. |[Anzeigen von Details und Ergebnissen von automatischen Untersuchungen](/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Keine automatisierte Antwort** (nicht empfohlen)|Es werden keine automatisierten Untersuchungen ausgeführt, daher werden keine Bewertungen erreicht, und es werden keine Korrekturmaßnahmen ausgeführt oder auf die Genehmigung gewartet. |[Erwägen Sie das Einrichten oder Ändern Ihrer Gerätegruppen, um die **vollständige** oder **semi-Automatisierung** zu verwenden.](/microsoft-365/security/defender-endpoint/machine-groups) |

In Microsoft Defender für Endpunkt werden alle Bewertungen im [Info-Center](auto-investigation-action-center.md#new-a-unified-action-center)nachverfolgt.

## <a name="next-steps"></a>Nächste Schritte

- [Erfahren Sie mehr über die Funktionen für Liveantworten](live-response.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über automatisierte Untersuchungen](automated-investigations.md)
