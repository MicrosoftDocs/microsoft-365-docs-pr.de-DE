---
title: Überprüfen von Korrekturmaßnahmen nach automatisierten Untersuchungen
description: Überprüfen und genehmigen (oder ablehnen) Korrekturaktionen nach einer automatisierten Untersuchung.
keywords: Autoir, automatisiert, Untersuchung, Erkennung, Korrektur, Aktion, ausstehend, genehmigt
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
ms.openlocfilehash: b0c983f4ba939cee6485570af774c8a728c73944
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274928"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Überprüfen von Korrekturmaßnahmen nach einer automatisierten Untersuchung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Wartungsaktionen

Wenn eine [automatisierte Untersuchung ausgeführt](automated-investigations.md) wird, wird für jeden untersuchten Nachweis ein Urteil generiert. Die Urteile können *"Bösartig",* *"Verdächtig"* oder *"Keine Bedrohungen" sein.* 

Abhängig von

- die Art der Bedrohung, 
- das resultierende Urteil und 
- Konfigurieren der Gerätegruppen Ihrer Organisation, [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) 

Behebungsaktionen können automatisch oder nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt werden. 

Hier ein paar Beispiele:

- **Beispiel 1:** Die Gerätegruppen von Fabrikam sind auf **Vollständig festgelegt –** Bedrohungen werden automatisch behoben (empfohlene Einstellung). In diesem Fall werden Korrekturaktionen automatisch für Artefakte ausgeführt, die nach einer automatisierten Untersuchung als bösartig betrachtet werden (siehe [Überprüfen abgeschlossener Aktionen](#review-completed-actions)).

- **Beispiel 2:** Contosos Geräte sind in einer Gerätegruppe enthalten, die für Semi festgelegt ist – erfordern die Genehmigung für alle **Korrekturen.** In diesem Fall muss das Sicherheitsteam von Contoso alle Abhilfemaßnahmen nach einer automatisierten Untersuchung überprüfen und genehmigen (siehe [Überprüfen ausstehender Aktionen](#review-pending-actions)).

- **Beispiel 3:** Tailspin Toys hat seine Gerätegruppen auf **Keine** automatisierte Antwort festgelegt (nicht empfohlen). In diesem Fall erfolgen keine automatisierten Untersuchungen. Es werden keine Korrekturaktionen ergriffen oder ausstehend, und es werden keine Aktionen im [Aktionscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) für ihre Geräte protokolliert (siehe [Verwalten von Gerätegruppen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).

Unabhängig davon, ob sie automatisch oder nach der Genehmigung ausgeführt wird, kann eine automatisierte Untersuchung zu einer oder mehreren der Abhilfemaßnahmen führen:
- Isolieren einer Datei
- Entfernen eines Registrierungsschlüssels 
- Kill a process 
- Beenden eines Diensts 
- Deaktivieren eines Treibers 
- Entfernen eines geplanten Vorgangs

## <a name="review-pending-actions"></a>Überprüfen ausstehender Aktionen

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Überprüfen Sie die Elemente auf der Registerkarte **Ausstehend.** 
4. Wählen Sie eine Aktion aus, um den Flyoutbereich zu öffnen.
5. Überprüfen Sie im Flyoutbereich die Informationen, und gehen Sie dann wie folgt vor:
   - Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.
   - Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.
   - Wählen **Sie Auf Die Suche gehen** aus, um zu Erweiterte Suche zu [wechseln.](advanced-hunting-overview.md) 

## <a name="review-completed-actions"></a>Überprüfen abgeschlossener Aktionen

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Überprüfen Sie die Elemente auf der **Registerkarte Verlauf.** 
4. Wählen Sie ein Element aus, um weitere Details zu dieser Korrekturaktion anzuzeigen.
 
## <a name="undo-completed-actions"></a>Rückgängig machen abgeschlossener Aktionen

Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung darstellt, können Sie die ergriffenen Korrekturaktionen rückgängig machen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden. Im Aktionscenter können Sie auf der Registerkarte **Verlauf** eine der folgenden Aktionen rückgängig machen:  

| Aktionsquelle | Unterstützte Aktionen |
|:---|:---|
| – Automatisierte Untersuchung <br/>- Microsoft Defender Antivirus <br/>– Manuelle Reaktionsaktionen | - Gerät isolieren <br/>- Einschränken der Codeausführung <br/>– Isolieren einer Datei <br/>- Entfernen eines Registrierungsschlüssels <br/>- Beenden eines Diensts <br/>- Deaktivieren eines Treibers <br/>– Entfernen eines geplanten Vorgangs |

### <a name="to-undo-multiple-actions-at-one-time"></a>So machen Sie mehrere Aktionen gleichzeitig rückgängig

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.
2. Wählen Sie **auf der Registerkarte** Verlauf die Aktionen aus, die Rückgängig gemacht werden sollen. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.
3. Wählen Sie im Flyoutbereich **Rückgängig aus.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne 

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.
2. Wählen Sie **auf der Registerkarte** Verlauf ein Element mit der Datei Aktionstyp Quarantäne **aus.**
3. Wählen Sie im Flyoutbereich **Anwenden auf X weitere** Instanzen dieser Datei aus, und wählen Sie dann Rückgängig **aus.**

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Automatisierungsebenen, automatisierte Untersuchungsergebnisse und resultierende Aktionen

Automatisierungsebenen wirken sich darauf aus, ob bestimmte Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden. Manchmal hat Ihr Sicherheitsteam je nach den Ergebnissen einer automatisierten Untersuchung weitere Schritte zu unternehmen. In der folgenden Tabelle sind automatisierungsstufen, Ergebnisse automatisierter Untersuchungen und die einzelnen Schritte zusammengefasst. 

|Gerätegruppeneinstellung | Automatisierte Untersuchungsergebnisse | Vorgehensweise |
|:---|:---|:---|
|**Vollständig – Automatische Behebung von Bedrohungen** (empfohlene Einstellung) |Für einen Beweis wird ein Urteil *von "Bösartig"* erreicht. <br/><br/>Entsprechende Korrekturaktionen werden automatisch ausgeführt. |[Überprüfen abgeschlossener Aktionen](#review-completed-actions) |
|**Vollständig – Automatische Behebung von Bedrohungen** |Ein *Verdächtiges-Urteil* wird für ein Beweisstück erreicht. <br/><br/>Behebungsaktionen stehen noch aus, damit die Genehmigung fortgesetzt wird. | [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions) |
|**Semi – Genehmigung für alle Korrekturen erforderlich**  |Für einen Beweis wird  ein Urteil *von "Bösartig"* oder "Verdächtig" erreicht. <br/><br/>Behebungsaktionen stehen noch aus, damit die Genehmigung fortgesetzt wird.  |[Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions) |
|**Semi – Erfordert die Genehmigung für die Korrektur von Kernordnern** |Für einen Beweis wird ein Urteil *von "Bösartig"* erreicht. <br/><br/>Wenn das Artefakt eine Datei oder ausführbare Datei ist und sich in einem Betriebssystemverzeichnis befindet, z. B. im Ordner Windows oder im Ordner "Programme", stehen Korrekturaktionen aus. <br/><br/>Wenn sich das Artefakt *nicht* in einem Betriebssystemverzeichnis befindet, werden korrekturaktionen automatisch ausgeführt. |1. [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)<br/><br/>2. [Überprüfen abgeschlossener Aktionen](#review-completed-actions) |
|**Semi – Erfordert die Genehmigung für die Korrektur von Kernordnern** |Ein *Verdächtiges-Urteil* wird für ein Beweisstück erreicht. <br/><br/>Korrekturaktionen stehen noch aus.  |[Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions).|
|**Semi – Genehmigung für nicht temporäre Ordnerbehebung erforderlich** |Für einen Beweis wird ein Urteil *von "Bösartig"* erreicht. <br/><br/>Wenn es sich bei dem Artefakt um eine Datei oder ausführbare Datei handelt, die sich nicht in einem temporären Ordner befindet, z. B. im Downloadordner oder temporären Ordner des Benutzers, stehen Korrekturaktionen aus. <br/><br/>Wenn es sich bei dem Artefakt um eine Datei oder ausführbare Datei *handelt,* die sich in einem temporären Ordner befindet, werden korrekturaktionen automatisch ausgeführt.  |1. [Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)<br/><br/>2. [Überprüfen abgeschlossener Aktionen](#review-completed-actions)  |
|**Semi – Genehmigung für nicht temporäre Ordnerbehebung erforderlich** |Ein *Verdächtiges-Urteil* wird für ein Beweisstück erreicht. <br/><br/>Korrekturaktionen stehen noch aus. |[Genehmigen (oder Ablehnen) ausstehender Aktionen](#review-pending-actions)  | 
|Eine der **Automatisierungsebenen "Vollständig"** oder **"Semi"** |Ein Urteil über *keine gefundenen Bedrohungen* wird für ein Beweisstück erreicht. <br/><br/>Es werden keine Korrekturaktionen und keine Aktionen ausstehend genehmigt. |[Anzeigen von Details und Ergebnissen von automatischen Untersuchungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Keine automatisierte Antwort** (nicht empfohlen)|Es werden keine automatisierten Untersuchungen ausgeführt, daher werden keine Urteile erreicht, und es werden keine Abhilfemaßnahmen ausgeführt oder warten auf die Genehmigung. |[Erwägen Sie das Einrichten oder Ändern Ihrer Gerätegruppen für die Verwendung der **Voll-** oder **Semiautomatisierung.**](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) |

In Microsoft Defender for Endpoint werden alle Urteile im [Aktionscenter nachverfolgt.](auto-investigation-action-center.md#new-a-unified-action-center)

## <a name="next-steps"></a>Nächste Schritte

- [Informationen zu Liveantwortfunktionen](live-response.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche](advanced-hunting-overview.md)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über automatisierte Untersuchungen](automated-investigations.md)
