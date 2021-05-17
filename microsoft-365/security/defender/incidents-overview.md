---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen sie Vorfälle, die auf Geräten, Benutzern und Postfächern im Microsoft 365 Security Center angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reaktion, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
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
ms.openlocfilehash: 93751a8297e61a969e0049e27a847324a3d16872
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300013"
---
# <a name="incidents-in-microsoft-365-defender"></a>Vorfälle in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Bei einem Vorfall in Microsoft 365 Defender handelt es sich um eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs enthalten. 

Microsoft 365-Dienste und -Apps erstellen Warnungen, wenn sie ein verdächtiges oder böswilliges Ereignis oder eine Aktivität erkennen. Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff. Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Typen von Entitäten verwendet, z. B. Geräte, Benutzer und Postfächer. Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten. 

Da das Verbinden der einzelnen Warnungen, um Einblick in einen Angriff zu erhalten, eine Herausforderung und zeitaufwändige Aufgabe sein kann, aggregiert Microsoft 365 Defender die Warnungen und ihre zugehörigen Informationen automatisch zu einem Vorfall.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Korrelieren von Ereignissen von Entitäten zu einem Vorfall in Microsoft 365 Defender":::

Sehen Sie sich diese kurze Übersicht über Vorfälle in Microsoft 365 Defender (4 Minuten) an.

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Durch das Gruppieren verwandter Warnungen zu einem Vorfall erhalten Sie eine umfassende Ansicht eines Angriffs. Sie können z. B. folgende Informationen sehen:

- An der Stelle, an der der Angriff begonnen hat.
- Welche Taktiken verwendet wurden.
- Wie weit der Angriff in Ihren Mandanten gegangen ist.
- Der Umfang des Angriffs, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren. 
- Alle dem Angriff zugeordneten Daten.

Wenn [diese Option](m365d-enable.md)aktiviert ist, [](m365d-autoir.md) kann Microsoft 365 Defender Warnungen automatisch durch Automatisierung und künstliche Intelligenz untersuchen und auflösen. Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Vorfälle und Warnungen im Microsoft 365 Security Center

Sie verwalten Vorfälle aus Vorfällen **& Warnungen > Vorfällen** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)). Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Security Center":::

Wenn Sie einen Vorfallnamen auswählen, wird eine Zusammenfassung des Vorfalls und der Zugriff auf Registerkarten mit zusätzlichen Informationen angezeigt.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Zusammenfassungsseite für einen Vorfall im Microsoft 365 Security Center":::

Die zusätzlichen Registerkarten für einen Vorfall sind:

- Warnungen 

  Alle Warnungen im Zusammenhang mit dem Vorfall und deren Informationen.

- Geräte

  Alle Geräte, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Benutzer

  Alle Benutzer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Postfächer

  Alle Postfächer, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.

- Untersuchungen

  Alle [automatisierten Untersuchungen,](m365d-autoir.md) die durch Warnungen im Vorfall ausgelöst wurden.

- Nachweis und Antwort

  Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall.

- Graph (in der Vorschau)

  Eine Abbildung, die die Verbindung von Warnungen mit den in Ihrer Organisation betroffenen Ressourcen zeigt.

Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten und den Registerkarten eines Vorfalls im Microsoft 365 Security Center.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Security Center":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Beispielworkflow zur Reaktion auf Vorfälle für Microsoft 365 Defender

Hier ist ein Beispielworkflow für die Reaktion auf Vorfälle in Microsoft 365 mit dem Microsoft 365 Security Center.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Beispiel für einen Workflow zur Reaktion auf Vorfälle für Microsoft 365":::

Identifizieren Sie fortlaufend die Vorfälle mit der höchsten Priorität für die Analyse und Lösung in der Vorfallwarteschlange, und bereiten Sie sie für die Reaktion vor. Dies ist eine Kombination aus:

- [Triaging](incident-queue.md) zur Ermittlung der Vorfälle mit höchster Priorität durch Filtern und Sortieren der Vorfallwarteschlange.
- [Verwalten](manage-incidents.md) von Vorfällen durch Ändern des Titels, Zuweisen zu einem Analysten und Hinzufügen von Tags und Kommentaren.

1. Beginnen Sie für jeden Vorfall mit [einer Angriffs- und Warnungsuntersuchung und -analyse:](investigate-incidents.md)
 
   a. Zeigen Sie die Zusammenfassung des Vorfalls an, um den Umfang und den Schweregrad des Vorfalls sowie die betroffenen Entitäten zu verstehen (registerkarte **Zusammenfassung).**

   b. Beginnen Sie mit der Analyse der Warnungen, um ihren Ursprung, Umfang und Schweregrad zu verstehen (registerkarte **Warnungen).**

   c. Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (die Registerkarten **Geräte,** **Benutzer** **und** Postfächer).

   d. Erfahren Sie, wie Microsoft 365 Defender [einige](m365d-autoir.md) Warnungen automatisch aufgelöst hat (registerkarte **Untersuchungen).**
   
   e. Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **Nachweis und** Antwort).

2. Führen Sie nach oder während der Analyse ein Containment aus, um die zusätzlichen Auswirkungen des Angriffs und der Beseitigung der Sicherheitsbedrohung zu reduzieren.

3. Wiederherstellen Sie so weit wie möglich nach dem Angriff, indem Sie Ihre Mandantenressourcen in dem Zustand wiederherstellen, in dem sie sich vor dem Vorfall auf dem Konto hatten.

4. [Beheben](manage-incidents.md#resolve-incident) Sie den Vorfall, und nehmen Sie sich Zeit für das Lernen nach dem Vorfall:

   - Verstehen sie den Typ des Angriffs und seine Auswirkungen.
   - Forschen Sie den Angriff in [Threat Analytics](threat-analytics.md) und der Sicherheitsgemeinschaft nach einem Trend zu Sicherheitsangriffen.
   - Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre Standardworkflows, Prozesse, Richtlinien und Playbooks nach Bedarf zu aktualisieren.
   - Bestimmen Sie, ob Änderungen in Ihrer Sicherheitskonfiguration erforderlich sind, und implementieren Sie sie.

Wenn Sie mit der Sicherheitsanalyse [](incidents-overview.md) neu sind, lesen Sie die Einführung in die Reaktion auf Ihren ersten Vorfall, um weitere Informationen zu erhalten und einen Beispielvorfall zu durchschritten.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender

Im Folgenden finden Sie ein Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ein Beispiel für Sicherheitsvorgänge für Micosoft 365 Defender":::

Zu den täglichen Aufgaben gehören:

- [Verwalten von](manage-incidents.md) Vorfällen
- Überprüfen [automatisierter Untersuchungs- und Reaktionsaktionen im](m365d-action-center.md) Aktionscenter
- Überprüfen der neuesten [Bedrohungsanalyse](threat-analytics.md)
- [Reagieren auf](investigate-incidents.md) Vorfälle

Monatliche Aufgaben können Folgendes umfassen:

- Überprüfen [der AIR-Einstellungen](m365d-configure-auto-investigation-response.md)
- Überprüfen [der sicherheitssicheren Bewertung](microsoft-secure-score-improvement-actions.md) und & [Sicherheitsrisikoverwaltung](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Berichterstellung an Ihre IT-Sicherheitsverwaltungskette

Vierteljährliche Aufgaben können einen Bericht und ein Briefing der Sicherheitsergebnisse an den Chief Information Security Officer (CISO) enthalten.

Zu den jährlichen Aufgaben kann die Durchführung einer Größeren Vorfall- oder Verletzungsübung gehören, um Ihre Mitarbeiter, Systeme und Prozesse zu testen. 

Tägliche, monatliche, vierteljährliche und jährliche Aufgaben können verwendet werden, um Prozesse, Richtlinien und Sicherheitskonfigurationen zu aktualisieren oder zu verfeinern.

## <a name="next-steps"></a>Nächste Schritte

**Wenn Sie mit der Sicherheitsanalyse** und der Reaktion auf Vorfälle neu sind:

- Ein Beispiel [für](first-incident-overview.md) einen Angriff finden Sie in der exemplarischen Vorgehensweise Antworten auf Ihren ersten Vorfall, um einen geführten Rundgang durch einen typischen Analyse-, Behebungs- und Nachvorfallüberprüfungsprozess im Microsoft 365 Security Center zu erhalten.

**Wenn Sie Erfahrung mit der** Sicherheitsanalyse und der Reaktion auf Vorfälle haben:

- Beginnen Sie mit der Vorfallwarteschlange auf **der** Seite Vorfälle des Microsoft 365 Security Centers. Von hier aus haben Sie folgende Möglichkeiten:

  - Sehen Sie sich an, welche [Vorfälle](incident-queue.md) basierend auf dem Schweregrad und anderen Faktoren priorisiert werden sollen. 

  - [Verwalten von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags und Kommentaren basierend auf Ihrem Workflow für die Vorfallverwaltung.

  - Führen [Sie Untersuchungen](investigate-incidents.md) von Vorfällen durch.

- Ausführliche [Anleitungen für](https://docs.microsoft.com/security/compass/incident-response-playbooks) Phishing-, Kennwort-Spray- und App-Zustimmungszuserteilungsangriffe finden Sie in diesen Playbooks zur Reaktion auf Vorfälle.

