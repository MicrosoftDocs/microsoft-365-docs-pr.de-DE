---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Filtern von Vorfällen aus der Vorfallwarteschlange in Microsoft 365 Defender
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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636266"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorisieren von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten in einem Vorfall. Microsoft 365 Defender löst außerdem eindeutige Warnungen für Aktivitäten aus, die nur aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Produktsuite verfügt, als bösartig identifiziert werden können. Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsgeschichte, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und zu umgehen.

Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die über Geräte, Benutzer und Postfächer hinweg erstellt wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen. 

Sie erhalten die Vorfallwarteschlange von **Incidents & alerts > Incidents** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)). Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

Der Abschnitt Neueste Vorfälle und **Warnungen** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und Vorfälle, die in den letzten 24 Stunden erstellt wurden.

Standardmäßig werden in der Warteschleife im Microsoft 365 Sicherheitscenter Vorfälle angezeigt, die in den letzten sechs Monaten angezeigt wurden. Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.

Die Vorfallwarteschlange verfügt über anpassbare Spalten **(wählen** Sie Spalten auswählen) aus, die Ihnen Einblicke in verschiedene Merkmale des Vorfalls oder der betroffenen Entitäten bieten. Dies hilft Ihnen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse zu treffen.

Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.

Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*

> [!NOTE]
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, werden nicht geändert.

Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie bei Anwendung eine umfassende Auswahl aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung konzentrieren können. Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss. 

## <a name="available-filters"></a>Verfügbare Filter

In der Standardwarteschlange für Vorfälle können Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie einen gefilterten Satz von Vorfällen anzeigen können. Hier ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

In dieser Tabelle sind die verfügbaren Filternamen aufgeführt.

| Filtername | Beschreibung |
|:-------|:-----|
| Zugewiesen an | Sie können Warnungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden. |
| Kategorien | Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren. |
| Klassifizierung | Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen. Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt. |
| Vertraulichkeit der Daten | Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten. Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren. <br><br> Gilt nur, wenn Microsoft Information Protection aktiviert ist.|
| Gerätegruppe | Nach definierten Gerätegruppen filtern. |
| Untersuchungsstatus | Filtern von Vorfällen nach dem Status der automatisierten Untersuchung.  |
| Mehrere Kategorien | Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können. |
| Mehrere Dienstquellen  | Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus verschiedenen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365). |
| Betriebssystemplattform | Beschränken Sie die Vorfallwarteschlange nach Betriebssystem. |
| Dienstquellen | Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten. |
| Severity | Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann. Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit. |
| Status | Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind. |
|||

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie ermittelt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus, und:

- [Verwalten](manage-incidents.md) Sie die Eigenschaften des Vorfalls für Tags, Zuordnung, sofortige Lösung für falsch positive Vorfälle und Kommentare.
- Beginnen Sie ihre [Untersuchungen](investigate-incidents.md).

## <a name="see-also"></a>Sehen Sie ebenfalls
- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
