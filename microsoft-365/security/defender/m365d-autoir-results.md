---
title: Details und Ergebnisse einer automatisierten Untersuchung
description: Anzeigen der Ergebnisse und wichtigsten Ergebnisse der automatisierten Untersuchung in Microsoft 365 Defender
keywords: automatisch, Untersuchungen, Ergebnisse, analysieren, Details, Behebung, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2cc83e24d4dd81c9d2e972fa274b48fc3946532a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289727"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details und Ergebnisse einer automatisierten Untersuchung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Mit Microsoft 365 Defender, wenn eine [automatisierte Untersuchung](m365d-autoir.md) ausgeführt wird, sind Details zu dieser Untersuchung sowohl während als auch nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die [erforderlichen Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen. Diese Ansicht bietet Ihnen den aktuellen Status und die Möglichkeit, alle ausstehenden Aktionen zu genehmigen. 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Untersuchungsdetails":::

## <a name="new-unified-investigation-page"></a>(NEU!) Einheitliche Untersuchungsseite

Die Untersuchungsseite wurde kürzlich aktualisiert, um Informationen über Ihre Geräte, E-Mails und Zusammenarbeitsinhalte hinweg einzuschließen. Die neue, einheitliche Untersuchungsseite definiert eine gemeinsame Sprache und bietet eine einheitliche Oberfläche für automatische Untersuchungen in [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) und Microsoft Defender für [Office 365.](../office-365-security/defender-for-office-365.md) Um auf die einheitliche Untersuchungsseite zuzugreifen, wählen Sie den Link im gelben Banner aus, auf dem Sie sehen werden:

- Jede Untersuchungsseite im Office 365 Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) )
- Jede Untersuchungsseite im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
- Jede Vorfall- oder Info-Center-Erfahrung im Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) )

## <a name="open-the-investigation-details-view"></a>Öffnen der Anzeige mit Untersuchungsdetails

Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:

- [Auswählen eines Elements im Info-Center](#select-an-item-in-the-action-center)
- [Auswählen einer Untersuchung von einer Vorfalldetailsseite](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Auswählen eines Elements im Info-Center

Das verbesserte [Info-Center](m365d-action-center.md) ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) vereint [Korrekturaktionen](m365d-remediation-actions.md) auf Ihren Geräten, E-Mails & Inhalte für die Zusammenarbeit und Identitäten. Zu den aufgeführten Aktionen gehören Wartungsaktionen, die automatisch oder manuell durchgeführt wurden. Im Info-Center können Sie Aktionen anzeigen, die auf die Genehmigung warten, und Aktionen, die bereits genehmigt oder abgeschlossen wurden. Sie können auch zu weiteren Details navigieren, z. B. zu einer Untersuchungsseite.

> [!TIP]
> Sie müssen [über bestimmte Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks) verfügen, um Aktionen zu genehmigen, abzulehnen oder rückgängig zu machen.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie auf der Registerkarte **Ausstehend** oder **Verlauf** ein Element aus. Der Flyoutbereich wird geöffnet.

4. Überprüfen Sie die Informationen im Flyoutbereich, und führen Sie dann einen der folgenden Schritte aus:
   - Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.
   - Wählen Sie **"Gehe Auf Suche"** aus, um zur [erweiterten Suche](advanced-hunting-overview.md)zu gelangen.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öffnen einer Untersuchung von einer Vorfalldetailsseite

Verwenden Sie die Seite „Vorfalldetails“, um detaillierte Informationen zu einem Vorfall anzuzeigen, einschließlich ausgelöster Warnungen und Informationen zu betroffenen Geräten, Benutzerkonten oder Postfächern.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Vorfälle &**  >  **Warnungsvorfälle** aus. 

3. Wählen Sie ein Element in der Liste aus, und wählen Sie dann die **Seite "Vorfall öffnen"** aus.

4. Wählen Sie die Registerkarte **"Untersuchungen"** aus, und wählen Sie dann eine Untersuchung in der Liste aus. Der Flyoutbereich wird geöffnet.

5. Wählen Sie **die Seite "Untersuchung öffnen"** aus. 

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Vorfalldetails":::

## <a name="investigation-details"></a>Untersuchungsdetails

Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Untersuchungsdetails":::

In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen**, **Geräte**, **Identitäten**, **Wichtige Erkenntnisse**, **Entitäten**, **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.

> [!NOTE]
> Welche Registerkarten auf einer Untersuchungsdetailseite angezeigt werden, hängt davon ab, was Ihr Abonnement enthält. Wenn Ihr Abonnement beispielsweise Microsoft Defender für Office 365 Plan 2 nicht enthält, wird keine Registerkarte **"Postfächer"** angezeigt.

| Registerkarte | Beschreibung |
|:--------|:--------|
| **Untersuchungsdiagramm** | Bietet eine visuelle Darstellung der Untersuchung. Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.<br/>Sie können ein Element im Diagramm auswählen, um weitere Details anzuzeigen. Wenn Sie z. B. das **Symbol "Nachweis"** auswählen, gelangen Sie zur Registerkarte **"Nachweis",** auf der Sie erkannte Entitäten und deren Bewertungen sehen können. |
| **Benachrichtigungen** | Listet die mit der Untersuchung verbundenen Warnungen auf. Warnungen können von Bedrohungsschutzfeatures auf dem Gerät eines Benutzers, in Office Apps, Microsoft Cloud App Security und anderen Microsoft 365 Defender Features stammen.|
| **Geräte** | Listet die in der Untersuchung enthaltenen Geräte zusammen mit deren Korrekturstufe auf. (Korrekturstufen entsprechen [der Automatisierungsstufe für Gerätegruppen.)](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) |
| **Postfächer** |Listet Postfächer auf, die von erkannten Bedrohungen betroffen sind.  |
| **Benutzer**  | Listet Benutzerkonten auf, die von erkannten Bedrohungen betroffen sind. |
| **Beweise** | Listet Nachweise auf, die durch Warnungen oder Untersuchungen ausgelöst werden. Umfasst Bewertungen (*bösartig*, *verdächtig,* *unbekannt* oder *keine Bedrohungen gefunden*) und Den Wartungsstatus. |
| **Entities** | Enthält Details zu jeder analysierten Entität, einschließlich einer Bewertung für jeden Entitätstyp (*Bösartig,* *Verdächtig* oder *keine Bedrohungen gefunden*).|
|**Log** | Bietet eine chronologische, detaillierte Ansicht aller Untersuchungsaktionen, die nach dem Auslösen einer Warnung ausgeführt wurden.|
| **Verlauf ausstehender Aktionen** | Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), um ausstehende Aktionen zu genehmigen. |

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen und Genehmigen von Korrekturaktionen](m365d-autoir-actions.md)
- [Weitere Informationen zu Wartungsaktionen](m365d-remediation-actions.md)
