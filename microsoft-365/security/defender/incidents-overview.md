---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, Benutzern und Postfächern im Microsoft 365 Defender-Portal angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reagieren, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028523"
---
# <a name="incidents-in-microsoft-365-defender"></a>Vorfälle in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Ein Vorfall in Microsoft 365 Defender ist eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs bilden. 

Microsoft 365 Dienste und Apps warnungen erstellen, wenn sie ein verdächtiges oder bösartiges Ereignis oder eine schädliche Aktivität erkennen. Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff. Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Entitätstypen verwendet, z. B. Geräte, Benutzer und Postfächer. Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten. 

Da es schwierig und zeitaufwändig sein kann, die einzelnen Warnungen zusammenzufassen, um Einblicke in einen Angriff zu erhalten, aggregiert Microsoft 365 Defender automatisch die Warnungen und die zugehörigen Informationen zu einem Vorfall.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="So korreliert Microsoft 365 Defender Ereignisse von Entitäten in einen Vorfall":::

Sehen Sie sich diese kurze Übersicht über Vorfälle in Microsoft 365 Defender (4 Minuten) an.

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Die Gruppierung verwandter Warnungen zu einem Vorfall bietet ihnen einen umfassenden Überblick über einen Angriff. Sie können z. B. Folgendes sehen:

- Wo der Angriff begonnen hat.
- Welche Taktiken verwendet wurden.
- Wie weit der Angriff auf Ihren Mandanten gestoßen ist.
- Der Umfang des Angriffs, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren. 
- Alle dem Angriff zugeordneten Daten.

Wenn [diese Option aktiviert](m365d-enable.md)ist, können Microsoft 365 Defender Warnungen durch Automatisierung und künstliche Intelligenz automatisch untersuchen und [beheben.](m365d-autoir.md) Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Vorfälle und Warnungen im Microsoft 365 Defender Portal

Sie verwalten Vorfälle aus **Vorfällen & Warnungen > Vorfällen** im Schnellstart des Microsoft 365 Defender-Portals ([security.microsoft.com](https://security.microsoft.com)). Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Defender-Portal":::

Wenn Sie einen Vorfallnamen auswählen, wird eine Zusammenfassung des Vorfalls angezeigt und der Zugriff auf Registerkarten mit zusätzlichen Informationen ermöglicht.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Seite &quot;Zusammenfassung&quot; für einen Vorfall im portal Microsoft 365 Defender":::

Die zusätzlichen Registerkarten für einen Vorfall sind:

- Warnungen 

  Alle Warnungen im Zusammenhang mit dem Vorfall und deren Informationen.

- Geräte

  Alle Geräte, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Benutzer

  Alle Benutzer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Postfächer

  Alle Postfächer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Untersuchungen

  Alle [automatisierten Untersuchungen,](m365d-autoir.md) die durch Warnungen im Vorfall ausgelöst wurden.

- Nachweise und Antworten

  Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen des Vorfalls.

- Graph (in der Vorschau)

  Abbildung der Verbindung von Warnungen mit den betroffenen Ressourcen in Ihrer Organisation.

Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten sowie die Registerkarten eines Vorfalls im portal Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Defender Portal":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Beispielworkflow für die Reaktion auf Vorfälle für Microsoft 365 Defender

Hier ist ein Beispielworkflow für die Reaktion auf Vorfälle in Microsoft 365 mit dem Microsoft 365 Defender-Portal.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Beispiel für einen Vorfallreaktionsworkflow für Microsoft 365":::

Identifizieren Sie fortlaufend die Vorfälle mit der höchsten Priorität für Analyse und Lösung in der Vorfallswarteschlange, und bereiten Sie sie für die Reaktion vor. Dies ist eine Kombination aus:

- [Ermittlung](incident-queue.md) der Vorfälle mit der höchsten Priorität durch Filtern und Sortieren der Vorfallswarteschlange.
- [Verwalten](manage-incidents.md) von Vorfällen durch Ändern ihres Titels, Zuweisen zu einem Analysten und Hinzufügen von Tags und Kommentaren.

1. Beginnen Sie für jeden Vorfall mit einer Untersuchung und Analyse von [Angriffen und Warnungen:](investigate-incidents.md)
 
   1. Sehen Sie sich die Zusammenfassung des Vorfalls an, um den Umfang und Schweregrad des Vorfalls und die betroffenen Entitäten zu verstehen (Registerkarte **"Zusammenfassung").**

   1. Beginnen Sie mit der Analyse der Warnungen, um deren Ursprung, Umfang und Schweregrad zu verstehen (Registerkarte **"Warnungen").**

   1. Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (registerkarten **"Geräte",** **"Benutzer"** und **"Postfächer").**

   1. Erfahren Sie, wie Microsoft 365 Defender [einige Warnungen automatisch aufgelöst](m365d-autoir.md) hat (Registerkarte **"Untersuchungen").**
   
   1. Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **"Nachweise und Reaktion").**

2. Führen Sie nach oder während Ihrer Analyse eine Eindämmung durch, um die zusätzlichen Auswirkungen des Angriffs und die Beseitigung der Sicherheitsrisiken zu verringern.

3. Wiederherstellen Sie nach dem Angriff so weit wie möglich, indem Sie Ihre Mandantenressourcen in den Zustand wiederherstellen, in dem sie sich vor dem Vorfall befanden.

4. [Beheben Sie](manage-incidents.md#resolve-an-incident) den Vorfall, und nehmen Sie sich Zeit, um nach dem Vorfall zu lernen:

   - Verstehen sie den Typ des Angriffs und seine Auswirkungen.
   - Untersuchen Sie den Angriff in [Threat Analytics](threat-analytics.md) und die Sicherheitscommunity nach einem Trend bei Sicherheitsangriffen.
   - Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre standardmäßigen Workflows, Prozesse, Richtlinien und Playbooks nach Bedarf zu aktualisieren.
   - Ermitteln Sie, ob Änderungen in Ihrer Sicherheitskonfiguration erforderlich sind, und implementieren Sie sie.

Wenn Sie noch keine Informationen zur Sicherheitsanalyse haben, lesen Sie die Einführung in die [Reaktion auf Ihren ersten Vorfall,](incidents-overview.md) um weitere Informationen zu erhalten und einen Beispielvorfall durchzugehen.

Weitere Informationen zur Behandlung von Sicherheitsvorfällen in Microsoft-Produkten finden Sie in [diesem Artikel.](/security/compass/incident-response-overview)

## <a name="example-security-operations-for-microsoft-365-defender"></a>Beispielsicherheitsvorgänge für Microsoft 365 Defender

Hier ist ein Beispiel für Sicherheitsvorgänge (SecOps) für Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ein Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender":::

Tägliche Aufgaben können Folgendes umfassen:

- [Verwalten von](manage-incidents.md) Vorfällen
- Überprüfen von [AIR-Aktionen (Automated Investigation and Response)](m365d-action-center.md) im Info-Center
- Überprüfen der neuesten [Bedrohungsanalyse](threat-analytics.md)
- [Reaktion auf](investigate-incidents.md) Vorfälle

Monatliche Aufgaben können Folgendes umfassen:

- Überprüfen von [AIR-Einstellungen](m365d-configure-auto-investigation-response.md)
- Überprüfen der [Sicherheitsbewertung](microsoft-secure-score-improvement-actions.md) und [& Sicherheitsrisikoverwaltung](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Berichterstellung für Ihre IT-Sicherheitsverwaltungskette

Vierteljährliche Aufgaben können einen Bericht und ein Briefing der Sicherheitsergebnisse an den Chief Information Security Officer (CISO) umfassen.

Jährliche Aufgaben können die Durchführung eines größeren Vorfalls oder einer Verletzungsübung umfassen, um Ihre Mitarbeiter, Systeme und Prozesse zu testen. 

Tägliche, monatliche, vierteljährliche und jährliche Aufgaben können verwendet werden, um Prozesse, Richtlinien und Sicherheitskonfigurationen zu aktualisieren oder zu verfeinern.

### <a name="secops-resources-across-microsoft-products"></a>SecOps-Ressourcen in microsoftweiten Produkten

Weitere Informationen zu SecOps in allen Microsoft-Produkten finden Sie in den folgenden Ressourcen:

- [Capabilities](/security/compass/security-operations-capabilities)
- [Bewährte Methoden](/security/compass/security-operations)
- [Videos und Folien](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a>Nächste Schritte

**Wenn Sie noch keine Informationen** zur Sicherheitsanalyse und zur Reaktion auf Sicherheitsvorfälle haben:

- Sehen Sie sich die [exemplarische Vorgehensweise zum Reagieren auf Ihren ersten Vorfall an,](first-incident-overview.md) um eine Führung durch einen typischen Prozess der Analyse, Behebung und Überprüfung nach dem Vorfall im Microsoft 365 Defender-Portal mit einem Beispielangriff zu erhalten.

**Wenn Sie Erfahrung** mit Sicherheitsanalysen und der Reaktion auf Vorfälle haben:

- Erste Schritte mit der Vorfallwarteschlange auf der Seite **"Vorfälle"** des Microsoft 365 Defender-Portals. Von hier aus haben Sie folgende Möglichkeiten:

  - Erfahren Sie, welche Vorfälle basierend auf dem Schweregrad und anderen Faktoren [priorisiert](incident-queue.md) werden sollten. 

  - [Verwalten Von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags und Kommentaren basierend auf Ihrem Vorfallverwaltungsworkflow.

  - Führen Sie [Untersuchungen](investigate-incidents.md) von Vorfällen durch.

- In diesen Playbooks zur Behandlung von [Sicherheitsvorfällen](/security/compass/incident-response-playbooks) finden Sie ausführliche Anleitungen für Phishing-, Kennwort-Spray- und App-Genehmigungs-Angriffe.

