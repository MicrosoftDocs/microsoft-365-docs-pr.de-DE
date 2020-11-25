---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Filtern von Vorfällen aus der Vorfall Warteschlange in Microsoft 365 Defender
keywords: Vorfall, Warteschlange, Übersicht, Geräte, Identitäten, Benutzer, Postfach, E-Mail, Vorfälle
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
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409255"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorisieren von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten zu einem einzigen Vorfall. Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die nur als böswillig identifiziert werden können, wenn die End-to-End-Sichtbarkeit vorliegt, die Microsoft 365 Defender über das gesamte Anwesen und die Produktsuite verfügt. Diese Ansicht verleiht Ihrem Security Operations Analyst eine umfassendere Angriffs Geschichte, die Ihnen hilft, komplexe Bedrohungen in der gesamten Organisation besser zu verstehen und zu bewältigen.


In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

Standardmäßig zeigt die Warteschlange im Microsoft 365 Security Center Vorfälle an, die in den letzten 30 Tagen angezeigt wurden. Der letzte Vorfall befindet sich am Anfang der Liste, sodass Sie ihn zuerst sehen können.

Die Vorfall Warteschlange macht anpassbare Spalten verfügbar, mit denen Sie die verschiedenen Merkmale des Vorfalls oder die enthaltenen Entitäten sichtbar machen können. Auf diese Weise können Sie eine fundierte Entscheidung in Bezug auf die Priorisierung von Vorfällen für die Verarbeitung treffen.

Um eine zusätzliche Sichtbarkeit auf einen Blick zu erhalten, werden bei der automatischen Benennung von Ereignissen Vorfall Namen basierend auf Warnungs Attributen generiert, beispielsweise die Anzahl betroffener Endpunkte, betroffene Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.

Beispiel: *mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*

> [!NOTE]
> Bei Vorfällen, die vor dem Rollout der automatischen Vorfall Benennung vorhanden waren, wird der Name nicht geändert.

Die Vorfall Warteschlange macht auch mehrere Filteroptionen verfügbar, die Ihnen bei Anwendung die Möglichkeit bieten, eine umfassende Bereinigung aller vorhandenen Vorfälle in Ihrer Umgebung durchzuführen oder sich auf ein bestimmtes Szenario oder eine Bedrohung konzentrieren. Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss. 

## <a name="available-filters"></a>Verfügbare Filter

### <a name="assigned-to"></a>Zugewiesen an
Sie können festlegen, dass Warnungen angezeigt werden, die Ihnen zugewiesen sind oder die von Automatisierung behandelt werden.

### <a name="categories"></a>Kategorien
Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffs Komponenten zu konzentrieren. 

### <a name="classification"></a>Klassifizierung
Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen. Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.

### <a name="data-sensitivity"></a>Vertraulichkeit der Daten
Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten. Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.

>[!NOTE]
>Gilt nur, wenn Microsoft Information Protection aktiviert ist.

### <a name="device-group"></a>Gerätegruppe
Filtern nach definierten Gerätegruppen.

### <a name="investigation-state"></a>Untersuchungs Zustand
Filtern von Vorfällen nach dem Status der automatischen Untersuchung. 

### <a name="multiple-categories"></a>Mehrere Kategorien 
Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden anrichten können. 

### <a name="multiple-service-sources"></a>Mehrere Dienstquellen 
Filtern, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).

### <a name="os-platform"></a>Betriebssystemplattform
Einschränken der Vorfall Warteschlangenansicht nach Betriebssystem.

### <a name="service-sources"></a>Dienstquellen
Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten. 

### <a name="severity"></a>Severity
Der Schweregrad eines Vorfalls deutet auf die Auswirkungen hin, die er auf Ihre Objekte haben kann. Je höher der Schweregrad, desto größer ist die Auswirkung und erfordert in der Regel die unmittelbarste Aufmerksamkeit. 

### <a name="status"></a>Status
Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.




## <a name="next-steps"></a>Nächste Schritte
Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.
- [Untersuchen von Vorfällen](investigate-incidents.md)


## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
