---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
description: Analysieren Sie Vorfälle in Bezug auf Geräte, Nutzer und Postfächer.
keywords: Vorfall, Vorfälle, Rechner, Geräte, Nutzer, Identitäten, Post, E-Mail, Postfach, Untersuchung, Graph, Beweise
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846748"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Untersuchen von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**

- Microsoft 365 Defender

Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Beweise aus ihren Geräten, Benutzern und Postfächern, damit Sie einen umfassenden Einblick in die gesamte Bandbreite eines Angriffs erhalten.

Untersuchen Sie die Warnmeldungen, die Ihr Netzwerk betreffen, verstehen Sie, was sie bedeuten, und stellen Sie die mit den Vorfällen verbundenen Beweise zusammen, damit Sie einen wirksamen Plan zur Behebung erstellen können.

## <a name="investigate-an-incident"></a>Untersuchung eines Vorfalls

1. Wählen Sie einen Vorfall aus der Vorfallwarteschlange aus. <BR> Ein Seitenbereich wird geöffnet und zeigt eine Vorschau wichtiger Informationen wie Status, Schweregrad, Kategorien und betroffene Entitäten an.

    ![Bild eines Seitenbereichs](../../media/incident-side-panel.png)

2. Wählen Sie **Vorfallseite öffnen**. <BR> Dadurch wird die Vorfall Seite geöffnet, auf der Sie weitere Informationen zu Vorfalldetails, Kommentaren und Aktionen, Registerkarten (Übersicht, Warnungen, Geräte, Benutzer, Untersuchungen, Beweise) finden.

3. Überprüfen Sie die Warnungen, Geräte, Nutzer und anderen Entitäten, die an dem Vorfall beteiligt sind.

## <a name="incident-overview"></a>Vorfall Übersicht

Auf der Übersichtsseite erhalten Sie einen Überblick über die wichtigsten Informationen zu dem Vorfall.

![Abbildung der Vorfallübersichtsseite](../../media/incidents-overview.png)

Die Angriffskategorien bieten eine visuelle und numerische Ansicht, wie fortgeschritten der Angriff für die killkette ist. Wie bei anderen Microsoft-Sicherheitsprodukten wird Microsoft 365 Defender an das [Mitra ATT&CK &trade; ](https://attack.mitre.org/) -Framework angepasst.

Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind. Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.

Die Zeitleiste für Warnungen bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie in die Gründe, aus denen diese Warnungen mit diesem Vorfall verknüpft sind.

Und schließlich finden Sie im Abschnitt "Nachweise" eine Zusammenfassung der Anzahl der in den Vorfall einbezogenen Artefakte und ihres Behebungsstatus, sodass Sie sofort erkennen können, ob eine Maßnahme erforderlich ist.

Diese Übersicht kann bei der ersten Analyse des Vorfalls hilfreich sein, indem sie einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.

## <a name="alerts"></a>Warnungen

Sie können alle Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesen anzeigen, beispielsweise den Schweregrad, Entitäten, die an der Warnung beteiligt waren, die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender für Office 365) und den Grund, warum Sie miteinander verknüpft wurden.

![Abbildung der Seite mit Vorfallbenachrichtigungen](../../media/incident-alerts.png)

Standardmäßig sind die Warnungen chronologisch geordnet, damit Sie zunächst sehen können, wie sich der Angriff im Laufe der Zeit abgespielt hat. Durch Klicken auf jede Warnung gelangen Sie zur entsprechenden Benachrichtigungsseite, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können.

## <a name="devices"></a>Geräte

Auf der Registerkarte „Geräte“ werden alle Geräte aufgelistet, zu denen Warnungen bezüglich des Vorfalls angezeigt werden.

Wenn Sie auf den Namen des Rechners klicken, auf dem der Angriff ausgeführt wurde, gelangen Sie zur Seite "Rechner", auf der Sie Warnungen und verwandte Ereignisse zur Vereinfachung der Untersuchung anzeigen können.

![Abbildung der Registerkarte "Rechner" eines Vorfalls](../../media/incident-machines.png)

Durch Auswahl der Registerkarte Zeitachse können Sie durch die Zeitachse der Rechner scrollen und alle Ereignisse und Verhaltensweisen, die auf dem Rechner beobachtet wurden, in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgegebenen Warnungen.

## <a name="users"></a>Nutzer

Anzeigen von Nutzern, die als Bestandteil von oder mit einem bestimmten Vorfall verbunden sind.

Durch Klicken auf den Nutzernamen gelangen Sie zur Cloud App Security-Seite des Nutzers, auf der weitere Untersuchungen durchgeführt werden können.

![Abbildung der Registerkarte "Nutzer" eines Vorfalls](../../media/incident-users.png)

## <a name="mailboxes"></a>Postfächer

Untersuchen Sie Postfächer, bei denen festgestellt wurde, dass sie Teil eines Vorfalls sind oder sich auf einen Vorfall beziehen. Für weitere Ermittlungsaufgaben wird durch Auswahl der e-Mail-bezogenen Warnung Microsoft Defender für Office 365 geöffnet, in dem Sie Korrekturaktionen ausführen können.

![Abbildung des Postfachregisters eines Vorfalls](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Untersuchungen

Wählen Sie unter **suchungen** aus, um alle automatisierten Untersuchungen anzuzeigen, die von Warnungen in diesem Vorfall ausgelöst wurden. In den Untersuchungen werden Korrekturaktionen durchgeführt oder auf die Analysten Genehmigung für Aktionen gewartet, je nachdem, wie Sie Ihre automatisierten Untersuchungen so konfiguriert haben, dass Sie in Microsoft Defender für Endpoint und Defender für Office 365 ausgeführt werden.

![Abbildung der Registerkarte "Untersuchungen“ eines Vorfalls](../../media/incident-investigations.png)

Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten. Wenn im Rahmen der Untersuchung noch Aktionen zur Genehmigung ausstehen, werden diese auf der Registerkarte Ausstehende Aktionen angezeigt. Maßnahmen im Rahmen der Vorgehensweise bei der Problembehebung.

## <a name="evidence"></a>Beweis

Microsoft 365 Defender untersucht automatisch alle unterstützten Ereignisse der Vorfälle und verdächtigen Entitäten in den Warnungen und bietet Ihnen autoresponse und Informationen über wichtige Dateien, Prozesse, Dienste, e-Mails und vieles mehr. Dies hilft, potenzielle Bedrohungen im Vorfall schnell zu erkennen und zu blockieren.

![Abbildung der Registerkarte "Beweise" eines Vorfalls](../../media/incident-evidence.png)

Jede der analysierten Entitäten wird mit einem Urteil (Bösartig, Verdächtig, Sauber) sowie einem Behebungsstatus gekennzeichnet. Dies hilft Ihnen dabei, den Behebungsstatus des gesamten Vorfalls zu verstehen und zu ermitteln, welche weiteren Schritte zur Behebung des Vorfalls unternommen werden können.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Verwalten von Vorfällen](manage-incidents.md)

