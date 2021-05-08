---
title: Anzeigen der Details und Ergebnisse einer automatischen Untersuchung
description: Während und nach einer automatischen Untersuchung können Sie die Ergebnisse und die wichtigsten Erkenntnisse anzeigen.
keywords: automatisch, Untersuchungen, Ergebnisse, analysieren, Details, Behebung, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: c593dfe384649b1599d5c0bab8fa6a8204d105dc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274832"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Anzeigen der Details und Ergebnisse einer automatischen Untersuchung

**Gilt für:**
- Microsoft Defender für Endpunkt

Wenn eine automatisierte Untersuchung [](automated-investigations.md) mit Microsoft Defender for Endpoint ausgeführt wird, sind Details zu dieser Untersuchung sowohl während als auch nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen. Die Anzeige mit Untersuchungsdetails bieten Ihnen den aktuellen Status sowie die Möglichkeit, ausstehende Aktionen zu genehmigen. 

## <a name="new-unified-investigation-page"></a>(NEU!) Seite "Einheitliche Untersuchung"

Die Untersuchungsseite wurde kürzlich aktualisiert, um Informationen auf Ihren Geräten, E-Mail- und Zusammenarbeitsinhalten zu enthalten. Die neue, einheitliche Untersuchungsseite definiert eine gemeinsame Sprache und bietet eine einheitliche Erfahrung für automatische Untersuchungen in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) und Microsoft Defender für [Office 365.](/microsoft-365/security/office-365-security/office-365-atp) 

> [!TIP]
> Weitere Informationen zu den Änderungen finden Sie unter [(NEU!) Vereinheitlichte Untersuchungsseite](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Öffnen der Anzeige mit Untersuchungsdetails

Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:
- [Auswählen eines Elements im Info-Center](#select-an-item-in-the-action-center)
- [Auswählen einer Untersuchung von einer Vorfalldetailsseite](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Auswählen eines Elements im Info-Center

Im [verbesserten Aktionscenter](auto-investigation-action-center.md) werden [Korrekturaktionen](manage-auto-investigation.md#remediation-actions) auf Ihren Geräten, E-Mails und & und Identitäten vereint. Zu den aufgelisteten Aktionen gehören Korrekturaktionen, die automatisch oder manuell ausgeführt wurden. Im Aktionscenter können Sie Aktionen anzeigen, die auf genehmigungswarten, und Aktionen, die bereits genehmigt oder abgeschlossen wurden. Sie können auch zu weiteren Details navigieren, z. B. zu einer Untersuchungsseite.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Wählen Sie auf der Registerkarte **Ausstehend** oder **Verlauf** ein Element aus. Der Flyoutbereich wird geöffnet.
4. Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:
   - Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.
   - Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.
   - Wählen **Sie Auf Die Suche gehen** aus, um zu Erweiterte Suche zu [wechseln.](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öffnen einer Untersuchung von einer Vorfalldetailsseite

Verwenden Sie die Seite „Vorfalldetails“, um detaillierte Informationen zu einem Vorfall anzuzeigen, einschließlich ausgelöster Warnungen und Informationen zu betroffenen Geräten, Benutzerkonten oder Postfächern.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Incidents & Alerts**  >  **Incidents aus.** 
3. Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Seite Vorfall öffnen aus.**
4. Wählen Sie die **Registerkarte** Untersuchungen aus, und wählen Sie dann eine Untersuchung in der Liste aus. Der Flyoutbereich wird geöffnet.
5. Wählen **Sie Untersuchungsseite öffnen aus.** 

## <a name="investigation-details"></a>Untersuchungsdetails

Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen. Die Anzeige mit Untersuchungsdetails sieht wie in der folgenden Abbildung aus:

In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen**, **Geräte**, **Identitäten**, **Wichtige Erkenntnisse**, **Entitäten**, **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.

> [!NOTE]
> Welche Registerkarten auf einer Seite mit Denkdetails angezeigt werden, hängt davon ab, was Ihr Abonnement enthält. Wenn Ihr Abonnement z. B. Microsoft Defender für Office 365 Plan 2 nicht enthält, wird keine Registerkarte **Postfächer** angezeigt.

| Registerkarte | Beschreibung |
|:--------|:--------|
| **Untersuchungsdiagramm**   | Bietet eine visuelle Darstellung der Untersuchung. Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.<br/>Sie können ein Element im Diagramm auswählen, um weitere Details anzuzeigen. Wenn Sie z. B. das **Symbol Nachweis** auswählen, werden Sie zur Registerkarte **Nachweis** angezeigt, auf der Sie erkannte Entitäten und deren Urteile sehen können. |
| **Benachrichtigungen**    | Listet die mit der Untersuchung verbundenen Warnungen auf. Warnungen können von Bedrohungsschutzfeatures auf dem Gerät eines Benutzers, in Office Apps, Cloud App Security und anderen Funktionen Microsoft 365 werden.|
| **Geräte** | Listet die in der Untersuchung enthaltenen Geräte zusammen mit ihrer Behebungsstufe auf. (Korrekturstufen entsprechen der [Automatisierungsebene für Gerätegruppen.)](automation-levels.md) |
| **Postfächer** |Listet Postfächer auf, die von erkannten Bedrohungen betroffen sind.  |
| **Benutzer**  | Listet Benutzerkonten auf, die von erkannten Bedrohungen betroffen sind. |
| **Nachweise** | Listet Nachweise auf, die durch Warnungen/Untersuchungen ausgelöst wurden. Umfasst Urteile (*Bösartig*, *Verdächtig* oder *Keine Bedrohungen gefunden*) und den Behebungsstatus. |
| **Entities**  | Enthält Details zu jeder analysierten Entität, einschließlich eines Urteils für jeden Entitätstyp (*Bösartige* *,* Verdächtige oder Keine *gefundenen Bedrohungen*).|
|**Log**    | Bietet eine chronologische, detaillierte Ansicht aller Untersuchungsaktionen, die nach dem Auslösen einer Warnung ergriffen wurden.|
| **Ausstehende Aktionen** | Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), um ausstehende Aktionen zu genehmigen. |

## <a name="see-also"></a>Siehe auch

- [Überprüfen von Korrekturmaßnahmen nach einer automatisierten Untersuchung](manage-auto-investigation.md)
- [Anzeigen und Organisieren der Microsoft Defender for Endpoint Incidents-Warteschlange](view-incidents-queue.md)