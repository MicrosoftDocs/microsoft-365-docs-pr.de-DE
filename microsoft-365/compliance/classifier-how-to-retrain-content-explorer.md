---
title: Neutrainieren eines Klassifizierers im Inhalts-Explorer
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Feedback an einen trainierbaren Klassifizierer im Inhalts-Explorer senden.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793064"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Neutrainieren eines Klassifizierers im Inhalts-Explorer

Ein Microsoft 365 trainierbarer Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben. Sobald Sie geschult sind, können Sie damit Elemente für die Anwendung von Office Vertraulichkeitsbezeichnungen, Kommunikationscompliancerichtlinien und Aufbewahrungsbezeichnungsrichtlinien identifizieren.

In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifizierern und einigen bereits trainierten Klassifizierern durch zusätzliches Feedback verbessern.

Weitere Informationen zu den verschiedenen Typen von Klassifizierern finden Sie unter [Informationen zu trainierbaren Klassifizierern.](classifier-learn-about.md)

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Optimierungs- und Umschulungsprozess zu geben. Sie müssen immer noch diesen vollständigen Artikel lesen, um die Details zu erhalten.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Berechtigungen

So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierer zu:

- Die Rolle "Complianceadministrator" oder "Compliancedatenadministrator" ist erforderlich, um einen Klassifizierer zu trainieren.

Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierer in diesen Szenarien zu verwenden:

- Szenario mit Aufbewahrungsbezeichnungsrichtlinien: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung" 

## <a name="overall-workflow"></a>Gesamter Workflow

> [!IMPORTANT]
> Sie geben im Inhalts-Explorer Feedback für die automatische Anwendung von Aufbewahrungsbezeichnungsrichtlinien auf Exchange Elemente und verwenden den Klassifizierer als Bedingung. **Wenn Sie keine Aufbewahrungsrichtlinie haben, die automatisch eine Aufbewahrungsbezeichnung auf Exchange Elemente anwendet und eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**

Wenn Sie Ihre Klassifizierer verwenden, sollten Sie die Genauigkeit der Klassifizierungen erhöhen, die sie erstellen. Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente erstellt wurden, die als Übereinstimmung oder nicht als Übereinstimmung identifiziert wurden. Nachdem Sie 30 Auswertungen für einen Klassifizierer durchgeführt haben, nimmt er dieses Feedback und trainiert sich automatisch neu.

Weitere Informationen zum allgemeinen Workflow der Umschulung eines Klassifizierers finden Sie unter [Prozessablauf für die Umschulung eines Klassifizierers.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Ein Klassifizierer muss bereits veröffentlicht und verwendet werden, bevor er umgeleitet werden kann.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Neutrainieren eines Klassifizierers im Inhalts-Explorer

1. Melden Sie sich bei Microsoft 365 Compliance Center mit Compliance-Administrator- oder Sicherheitsadministratorrollenzugriff an, und öffnen **Sie Microsoft 365 Compliance Center Data**  >  **classification**  >  **Content Explorer.** 
2. Erweitern Sie unter dem **Filter nach Bezeichnungen, Informationstypen oder Kategorienlisten** **trainierbare Klassifizierer.**

> [!IMPORTANT]
> Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift der trainierbaren Klassifizierer angezeigt werden.

3. Wählen Sie den trainierbaren Klassifizierer aus, den Sie bei der automatischen Anwendung der Aufbewahrungsbezeichnungsrichtlinie verwendet haben. Dies ist der trainierbare Klassifizierer, zu dem Sie Feedback geben.

> [!NOTE]
> Wenn ein Element einen Eintrag in der Spalte **"Aufbewahrungsbezeichnung"** aufweist, bedeutet dies, dass das Element als . `match`  Wenn ein Element keinen Eintrag in der Spalte **"Aufbewahrungsbezeichnung"** enthält, bedeutet dies, dass es als klassifiziert `close match` wurde. Sie können die Klassifizierergenauigkeit am besten verbessern, indem Sie Feedback zu `close match` Elementen bereitstellen. 

4. Wählen Sie ein Element aus, und öffnen Sie es.
 
 > [!TIP]
> Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann in der Befehlsleiste **"Klassifizierung verbessern"** auswählen.

5. Wählen Sie **"Feedback bereitstellen"** aus.
6. Wenn das Element ein echtes Positives ist, wählen Sie im Bereich **"Detailliertes Feedback"** die Option **"Übereinstimmung"** aus.  Wenn das Element ein falsch positives Ergebnis ist, d. h. es wurde nicht ordnungsgemäß in die Kategorie aufgenommen, wählen Sie **"Nicht übereinstimmend"** aus.
7. Wenn es einen anderen Klassifizierer gibt, der für das Element besser geeignet wäre, können Sie ihn aus der Liste **"Andere trainierbare Klassifizierer vorschlagen"** auswählen. Dadurch wird der andere Klassifizierer ausgelöst, um das Element auszuwerten.
8. Wählen Sie **"Feedback senden"** aus, um Ihre Auswertung der Klassifizierungen zu senden `match` und andere `not a match` trainierbare Klassifizierer vorzuschlagen. Wenn Sie 30 Instanzen von Feedback an einen Klassifizierer übermittelt haben, wird er automatisch neu trainiert. Die Umschulung kann zwischen 1 und 4 Stunden dauern. Klassifizierer können nur zweimal pro Tag trainiert werden.

> [!IMPORTANT]
> Diese Informationen werden an den Klassifizierer in Ihrem Mandanten weitergeleitet, **sie gehen nicht an Microsoft zurück.**

9. Öffnen **Sie trainierbare Klassifizierer.**
10. Der Klassifizierer, der in Ihrer Kommunikationscompliancerichtlinie verwendet wurde, wird unter der Überschrift **"Erneute Schulung"** angezeigt.

![Klassifizierer im Umschulungsstatus](../media/classifier-retraining.png)

11. Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifizierer aus, um die Übersicht über die Umschulung zu öffnen.

![Übersicht über die Klassifizierer-Neuschulungsergebnisse](../media/classifier-retraining-overview.png)

12. Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umgeleiteten und aktuell veröffentlichten Versionen des Klassifizierers.
13. Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **"Erneut veröffentlichen"** aus.
14. Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifizierer in der Benutzeroberfläche des Inhalts-Explorers senden und einen weiteren Umschulungszyklus starten oder nichts unternehmen, in diesem Fall wird die derzeit veröffentlichte Version des Klassifizierers weiterhin verwendet. 

## <a name="details-on-republishing-recommendations"></a>Details zu Empfehlungen zur erneuten Veröffentlichung

Hier finden Sie einige Informationen dazu, wie wir die Empfehlung formulieren, einen umgeleiteten Klassifizierer erneut zu veröffentlichen oder eine weitere Umschulung vorzuschlagen. Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierer.

Nach einer Neuschulung bewerten wir die Leistung des Klassifizierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierers verwendet wurden. 

- Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Von Microsoft zum Erstellen des Modells verwendeten Elemente.
- Bei benutzerdefinierten Modellen stammen die Elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben.

Wir vergleichen die Leistungsnummern für beide Gruppen von Elementen für den neu geschulten und veröffentlichten Klassifizierer, um eine Empfehlung zu geben, ob eine erneute Veröffentlichung verbessert werden konnte. 

## <a name="see-also"></a>Siehe auch

- [Weitere Informationen zu trainierbaren Klassifizierern](classifier-learn-about.md)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)