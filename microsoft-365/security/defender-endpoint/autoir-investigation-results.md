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
ms.openlocfilehash: a10442bc9d92bb6004149180da30b86b646dd5de
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290159"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Anzeigen der Details und Ergebnisse einer automatischen Untersuchung

**Gilt für:**
- Microsoft Defender für Endpunkt

Wenn eine [automatisierte Untersuchung](automated-investigations.md) ausgeführt wird, sind bei Microsoft Defender für Endpunkt Details zu dieser Untersuchung sowohl während als auch nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen. Die Anzeige mit Untersuchungsdetails bieten Ihnen den aktuellen Status sowie die Möglichkeit, ausstehende Aktionen zu genehmigen. 

## <a name="new-unified-investigation-page"></a>(NEU!) Einheitliche Untersuchungsseite

Die Untersuchungsseite wurde kürzlich aktualisiert, um Informationen über Ihre Geräte, E-Mails und Zusammenarbeitsinhalte hinweg einzuschließen. Die neue, einheitliche Untersuchungsseite definiert eine gemeinsame Sprache und bietet eine einheitliche Oberfläche für automatische Untersuchungen in [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) und Microsoft Defender für [Office 365.](/microsoft-365/security/office-365-security/office-365-atp) 

> [!TIP]
> Weitere Informationen zu änderungen finden Sie unter [(NEU!) Einheitliche Untersuchungsseite](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Öffnen der Anzeige mit Untersuchungsdetails

Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:

- [Auswählen eines Elements im Info-Center](#select-an-item-in-the-action-center)
- [Auswählen einer Untersuchung von einer Vorfalldetailsseite](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Auswählen eines Elements im Info-Center

Das verbesserte [Info-Center](auto-investigation-action-center.md) vereint [Korrekturaktionen](manage-auto-investigation.md#remediation-actions) auf Ihren Geräten, E-Mail-& Inhalte für die Zusammenarbeit und Identitäten. Zu den aufgeführten Aktionen gehören Wartungsaktionen, die automatisch oder manuell durchgeführt wurden. Im Info-Center können Sie Aktionen anzeigen, die auf die Genehmigung warten, und Aktionen, die bereits genehmigt oder abgeschlossen wurden. Sie können auch zu weiteren Details navigieren, z. B. zu einer Untersuchungsseite.

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

## <a name="investigation-details"></a>Untersuchungsdetails

Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen. Die Anzeige mit Untersuchungsdetails sieht wie in der folgenden Abbildung aus:

In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen**, **Geräte**, **Identitäten**, **Wichtige Erkenntnisse**, **Entitäten**, **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.

> [!NOTE]
> Welche Registerkarten auf einer Untersuchungsdetailseite angezeigt werden, hängt davon ab, was Ihr Abonnement enthält. Wenn Ihr Abonnement beispielsweise Microsoft Defender für Office 365 Plan 2 nicht enthält, wird keine Registerkarte **"Postfächer"** angezeigt.

| Registerkarte | Beschreibung |
|:--------|:--------|
| **Untersuchungsdiagramm** | Bietet eine visuelle Darstellung der Untersuchung. Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.<br/>Sie können ein Element im Diagramm auswählen, um weitere Details anzuzeigen. Wenn Sie z. B. das **Symbol "Nachweis"** auswählen, gelangen Sie zur Registerkarte **"Nachweis",** auf der Sie erkannte Entitäten und deren Bewertungen sehen können. |
| **Benachrichtigungen** | Listet die mit der Untersuchung verbundenen Warnungen auf. Warnungen können von Bedrohungsschutzfeatures auf dem Gerät eines Benutzers, in Office Apps, Cloud App Security und anderen Microsoft 365 Defender Features stammen.|
| **Geräte** | Listet die in der Untersuchung enthaltenen Geräte zusammen mit deren Korrekturstufe auf. (Korrekturstufen entsprechen der [Automatisierungsstufe für Gerätegruppen.)](automation-levels.md) |
| **Postfächer** |Listet Postfächer auf, die von erkannten Bedrohungen betroffen sind.  |
| **Benutzer**  | Listet Benutzerkonten auf, die von erkannten Bedrohungen betroffen sind. |
| **Beweise** | Listet die von Warnungen/Untersuchungen erhobenen Nachweise auf. Umfasst Bewertungen (*bösartig,* *verdächtig* oder *keine Bedrohungen gefunden*) und Wartungsstatus. |
| **Entities** | Enthält Details zu jeder analysierten Entität, einschließlich einer Bewertung für jeden Entitätstyp (*Bösartig,* *Verdächtig* oder *keine Bedrohungen gefunden*).|
|**Log** | Bietet eine chronologische, detaillierte Ansicht aller Untersuchungsaktionen, die nach dem Auslösen einer Warnung ausgeführt wurden.|
| **Ausstehende Aktionen** | Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), um ausstehende Aktionen zu genehmigen. |

## <a name="see-also"></a>Weitere Informationen:

- [Überprüfen von Korrekturaktionen nach einer automatisierten Untersuchung](manage-auto-investigation.md)
- [Anzeigen und Organisieren der Vorfallswarteschlange für Microsoft Defender für Endpunkt](view-incidents-queue.md)