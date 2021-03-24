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
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062023"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorisieren von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einem Vorfall. Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die nur aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Immobilie und Produktsuite verfügt, als bösartig identifiziert werden können. Diese Ansicht bietet Ihrem Sicherheitsbetriebsanalysten die umfassendere Angriffsgeschichte, die ihnen hilft, komplexe Bedrohungen in der gesamten Organisation besser zu verstehen und zu umgehen.


In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten 30 Tagen angezeigt wurden. Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.

Die Vorfallwarteschlange macht anpassbare Spalten verfügbar, die Ihnen Einblick in unterschiedliche Merkmale des Vorfalls oder der enthaltenen Entitäten bieten. Dies hilft Ihnen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen zu treffen.

Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.

Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*

> [!NOTE]
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, werden nicht geändert.

Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie bei Anwendung eine umfassende Auswahl aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung konzentrieren können. Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss. 

## <a name="available-filters"></a>Verfügbare Filter

### <a name="assigned-to"></a>Zugewiesen an
Sie können Warnungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden.

### <a name="categories"></a>Categories
Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren. 

### <a name="classification"></a>Klassifizierung
Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen. Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.

### <a name="data-sensitivity"></a>Vertraulichkeit der Daten
Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten. Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.

>[!NOTE]
>Gilt nur, wenn Microsoft Information Protection aktiviert ist.

### <a name="device-group"></a>Gerätegruppe
Nach definierten Gerätegruppen filtern.

### <a name="investigation-state"></a>Untersuchungsstatus
Filtern von Vorfällen nach dem Status der automatisierten Untersuchung. 

### <a name="multiple-categories"></a>Mehrere Kategorien 
Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können. 

### <a name="multiple-service-sources"></a>Mehrere Dienstquellen 
Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365).

### <a name="os-platform"></a>Betriebssystemplattform
Beschränken Sie die Vorfallwarteschlange nach Betriebssystem.

### <a name="service-sources"></a>Dienstquellen
Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten. 

### <a name="severity"></a>Severity
Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann. Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit. 

### <a name="status"></a>Status
Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.




## <a name="next-steps"></a>Nächste Schritte
Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.
- [Untersuchen von Vorfällen](investigate-incidents.md)


## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
