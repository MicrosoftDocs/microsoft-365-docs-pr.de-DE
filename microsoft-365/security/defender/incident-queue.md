---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Filtern von Vorfällen aus der Vorfallwarteschlange in Microsoft 365 Defender
keywords: Vorfall, Warteschlange, Übersicht, Geräte, Identitäten, Benutzer, Postfach, E-Mail, Vorfälle
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
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887257"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorisieren von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten in einem Vorfall. Microsoft 365 Defender löst auch eindeutige Warnungen zu Aktivitäten aus, die nur als bösartig identifiziert werden können, wenn die End-to-End-Sichtbarkeit von Microsoft 365 Defender für die gesamte Produktsuite gilt. Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsgeschichte, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und zu umgehen.

Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die über Geräte, Benutzer und Postfächer hinweg erstellt wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen. 

Beim Schnellstart des  Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)) & Warnungen > Vorfällen in die Warteschleife.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

Standardmäßig werden in der Warteschlange für Vorfälle im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten sechs Monaten beobachtet wurden. Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.

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
| Mehrere Dienstquellen  | Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365). |
| Betriebssystemplattform | Beschränken Sie die Vorfallwarteschlange nach Betriebssystem. |
| Dienstquellen | Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten. |
| Severity | Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann. Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit. |
| Status | Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind. |
|||

## <a name="incident-response-workflow"></a>Workflow zur Reaktion auf Vorfälle

Hier ist der typische Workflow für die Reaktion auf Vorfälle:

1. Identifizieren und verdingen Sie die Vorfälle mit der höchsten Priorität für Untersuchung und Lösung.
2. Starten Sie für jeden Vorfall mit hoher Priorität eine [Untersuchung:](investigate-incidents.md)

   a. Zeigen Sie die Zusammenfassung des Vorfalls an, um den Umfang und den Schweregrad des Vorfalls sowie die betroffenen Entitäten zu verstehen (registerkarte **Zusammenfassung).**

   b. Schauen Sie sich die Warnungen an, um ihren Ursprung, Umfang und Schweregrad zu verstehen (registerkarte **Warnungen).**

   c. Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (die Registerkarten **Geräte,** **Benutzer** **und** Postfächer).

   d. Erfahren Sie, wie Microsoft 365 Defender einige Warnungen automatisch aufgelöst hat (registerkarte **Untersuchungen).**
   
   e. Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **Nachweis und** Antwort).

   Bei der Untersuchung sollten Sie sich um Dies sorgen:

   - Containment: Reduzierung zusätzlicher Auswirkungen auf Ihren Mandanten.
   - Auslöschung: Entfernen der Sicherheitsbedrohung.
   - Wiederherstellung: Wiederherstellen der Mandantenressourcen in dem Zustand, in dem sie sich vor dem Vorfall auf dem Computer begnauft haben.

3. Nachdem Sie den Vorfall behoben haben, nehmen Sie sich die Zeit für:

   - Verstehen sie den Typ des Angriffs und seine Auswirkungen.
   - Recherchieren Sie den Angriff in der Sicherheitsgemeinschaft auf einen Trend zu Sicherheitsangriffen.
   - Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre Standardworkflows und Playbooks nach Bedarf zu aktualisieren.
   - Bestimmen Sie, ob Änderungen in Ihrer Sicherheitslage erforderlich sind, und ergreifen Sie die Schritte, um sie zu implementieren.

Hier finden Sie eine Zusammenfassung des grundlegenden Prozesses.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Grundlegendes Verfahren zur Untersuchung von Vorfällen":::

## <a name="next-step"></a>Nächster Schritt

Nachdem Sie ermittelt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus, und beginnen Sie mit der [Untersuchung.](investigate-incidents.md)

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
