---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie Vorfälle aus der Vorfallwarteschlange in Microsoft 365 Defender
keywords: Incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response
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
ms.openlocfilehash: 4d793d49d669510b722a72160ae396ee73ab9699
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028511"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorisieren von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten zu einem Vorfall. Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Produktsuite hat, nur als bösartig erkannt werden können. Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsstory, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und damit umzugehen.

In der **Vorfallswarteschlange** wird eine Sammlung von Vorfällen angezeigt, die geräte-, benutzer- und postfachübergreifend erstellt wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen. 

Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals [(](https://security.microsoft.com)security.microsoft.com ) von **Vorfällen & Warnungen > Vorfällen** in die Vorfallswarteschlange. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Vorfallwarteschlange":::

Der Abschnitt **"Letzte Vorfälle und Warnungen"** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und vorfälle, die in den letzten 24 Stunden erstellt wurden.

Standardmäßig zeigt die Vorfallwarteschlange im Microsoft 365 Defender-Portal Vorfälle an, die in den letzten sechs Monaten angezeigt wurden. Der letzte Vorfall befindet sich oben in der Liste, sodass Sie ihn zuerst sehen können.

Die Vorfallwarteschlange verfügt über anpassbare Spalten **(Spalten** auswählen), die Ihnen Einblicke in verschiedene Merkmale des Vorfalls oder die betroffenen Entitäten bieten. Auf diese Weise können Sie eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse treffen.

Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl der betroffenen Endpunkte, betroffenen Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.

Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*

> [!NOTE]
> Bei Vorfällen, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, wird ihr Name nicht geändert.

Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, die es Ihnen bei Anwendung ermöglichen, alle vorhandenen Vorfälle in Ihrer Umgebung umfassend zu durchlaufen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung zu konzentrieren. Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss. 

## <a name="available-filters"></a>Verfügbare Filter

In der Standardvorfallswarteschlange können Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie eine gefilterte Gruppe von Vorfällen anzeigen können. Hier ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

In dieser Tabelle sind die verfügbaren Filternamen aufgeführt.

| Filtername | Beschreibung |
|:-------|:-----|
| Zugewiesen an | Sie können Benachrichtigungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden. |
| Kategorien | Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren. |
| Klassifizierung | Filtern sie Vorfälle basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen. Zu den Werten gehören echte, falsche oder nicht festgelegte Warnungen. |
| Vertraulichkeit der Daten | Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten. Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren. <br><br> Gilt nur, wenn Microsoft Information Protection aktiviert ist.|
| Gerätegruppe | Filtern nach definierten Gerätegruppen. |
| Untersuchungsstatus | Filtern sie Vorfälle nach dem Status der automatischen Untersuchung.  |
| Mehrere Kategorien | Sie können festlegen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schäden verursachen können. |
| Mehrere Dienstquellen  | Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus verschiedenen Quellen enthalten (Microsoft Defender für Endpunkt, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365). |
| Betriebssystemplattform | Beschränken Sie die Vorfallwarteschlangenansicht nach Betriebssystem. |
| Dienstquellen | Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten. |
| Severity | Der Schweregrad eines Vorfalls ist ein Indikator für die Auswirkungen, die er auf Ihre Ressourcen haben kann. Je höher der Schweregrad, desto größer die Auswirkung und erfordert in der Regel die unmittelbarste Aufmerksamkeit. |
| Status | Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind. |
|||

## <a name="save-defined-filters-as-urls"></a>Speichern von definierten Filtern als URLs

Nachdem Sie einen nützlichen Filter in der Vorfallwarteschlange konfiguriert haben, können Sie die URL der Browserregisterkarte mit einem Lesezeichen versehen oder auf andere Weise als Link auf einer Webseite, einem Word-Dokument oder einem Ort Ihrer Wahl speichern. Dadurch erhalten Sie Mit-Klick-Zugriff auf wichtige Ansichten der Vorfallwarteschlange, z. B.:

- Neue Vorfälle
- Vorfälle mit hohem Schweregrad
- Nicht zugewiesene Vorfälle
- Vorfälle mit hohem Schweregrad, nicht zugewiesen
- Mir zugewiesene Vorfälle
- Mir zugewiesene Vorfälle und für Microsoft Defender für Endpunkt
- Vorfälle mit einem bestimmten Tag oder bestimmten Tags
- Vorfälle mit einer bestimmten Bedrohungskategorie
- Vorfälle mit einer bestimmten zugehörigen Bedrohung
- Vorfälle mit einem bestimmten Akteur

Nachdem Sie Ihre Liste nützlicher Filteransichten als URLs kompiliert und gespeichert haben, können Sie sie verwenden, um die Vorfälle in Ihrer Warteschlange schnell zu verarbeiten und zu priorisieren und für die nachfolgende Zuweisung und Analyse [zu verwalten.](manage-incidents.md)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie festgestellt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus und:

- [Verwalten Sie](manage-incidents.md) die Eigenschaften des Vorfalls für Tags, Zuweisung, sofortige Lösung für falsch positive Vorfälle und Kommentare.
- Beginnen Sie Ihre [Untersuchungen.](investigate-incidents.md)

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
