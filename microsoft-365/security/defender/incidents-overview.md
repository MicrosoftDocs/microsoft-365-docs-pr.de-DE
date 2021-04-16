---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, bei Benutzern und in Postfächern auftreten.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861623"
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

Wenn [diese Option](m365d-enable.md)aktiviert ist, kann Microsoft 365 Defender Warnungen automatisch durch Automatisierung und künstliche Intelligenz untersuchen und auflösen. Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben. 

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

  Alle automatisierten Untersuchungen, die durch Warnungen im Vorfall ausgelöst wurden.

- Nachweis und Antwort

  Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall.

Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten und den Registerkarten eines Vorfalls im Microsoft 365 Security Center.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Security Center":::

## <a name="next-step"></a>Nächster Schritt

In der Warteschleife auf der **Seite** Vorfälle werden die neuesten Vorfälle aufgeführt. Hier haben Sie folgende Möglichkeiten:

- Sehen Sie sich an, welche [Vorfälle](incident-queue.md) basierend auf dem Schweregrad und anderen Faktoren priorisiert werden sollen. 
- Führen Sie eine [Untersuchung](investigate-incidents.md) eines Vorfalls durch.
- [Verwalten von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags für Ihren Workflow für die Vorfallverwaltung.
