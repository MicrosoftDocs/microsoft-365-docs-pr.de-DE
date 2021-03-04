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
description: Erfahren Sie, wie Sie einem trainierbaren Klassifikator im Inhalts-Explorer Feedback geben.
ms.openlocfilehash: fabfe8e4df377c25012b358960d7f7ff7ff994bc
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423262"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Neutrainieren eines Klassifizierers im Inhalts-Explorer

Ein trainierbarer Microsoft 365-Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben. Nach der Ausbildung können Sie es verwenden, um Elemente für die Anwendung von Office-Vertraulichkeitsbezeichnungen, Richtlinien zur Kommunikationskonformität und Aufbewahrungsbezeichnungsrichtlinien zu identifizieren.

In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifikatoren und einigen vordefinierten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bereitstellen.

Weitere Informationen zu den verschiedenen Typen von Klassifizierungen finden Sie [unter Learn about trainable classifiers](classifier-learn-about.md).

Sehen Sie sich dieses Video an, um eine kurze Zusammenfassung des Optimierungs- und Umschulungsprozesses zu finden. Sie müssen weiterhin diesen vollständigen Artikel lesen, um die Details zu erhalten.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Berechtigungen

So greifen Sie auf Klassifikatoren im Microsoft 365 Compliance Center zu:

- Die Rolle des Complianceadministrators oder der Compliancedatenadministrator ist erforderlich, um einen Klassifizierer zu schulen.

Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierungen in den folgenden Szenarien verwenden zu können:

- Szenario der Aufbewahrungsbezeichnungsrichtlinie: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung" 

## <a name="overall-workflow"></a>Gesamtworkflow

> [!IMPORTANT]
> Sie geben Feedback im Inhalts-Explorer für die automatische Anwendung von Aufbewahrungsbezeichnungsrichtlinien auf Exchange-Elemente und verwenden den Klassifikator als Bedingung. **Wenn Sie nicht über eine Aufbewahrungsrichtlinie verfügen, die eine Aufbewahrungsbezeichnung automatisch auf Exchange-Elemente angewendet und einen Klassifizierungsaufbewahrungszeichen als Bedingung verwendet, beenden Sie hier.**

Wenn Sie Ihre Klassifizierungen verwenden, können Sie die Genauigkeit der Klassifizierungen erhöhen, die sie machen. Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder nicht übereinstimmend identifiziert wurden. Nachdem Sie 30 Auswertungen für einen Klassifikator erstellt haben, wird dieses Feedback benötigt und automatisch neu trainiert.

Weitere Informationen zum allgemeinen Workflow zum Umschulungstraining eines Klassifikierers finden Sie unter [Prozessablauf zum Umschulungen eines Klassifizierers](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Ein Klassifikator muss bereits veröffentlicht und verwendet werden, bevor er umtrainiert werden kann.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Neutrainieren eines Klassifizierers im Inhalts-Explorer

1. Melden Sie sich beim Microsoft 365 Compliance Center mit Dem Zugriff auf die Rolle des Complianceadministrators oder Sicherheitsadministrators an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Datenklassifizierung**  >  **Inhalts-Explorer**. 
2. Erweitern Sie **unter Filter on labels, info types, or categories list** **trainable classifiers**.

> [!IMPORTANT]
> Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift trainierbare Klassifizierungen angezeigt werden.

3. Wählen Sie den trainierbaren Klassifikator aus, den Sie in Der Aufbewahrungsbezeichnungsrichtlinie automatisch anwenden. Dies ist der trainierbare Klassifikator, zu dem Sie Feedback geben.

> [!NOTE]
> Wenn ein Element über einen Eintrag in der **Spalte** Aufbewahrungsbezeichnung verfügt, bedeutet dies, dass das Element als klassifiziert `match` wurde.  Wenn ein Element keinen Eintrag in der Spalte Aufbewahrungsbezeichnung **hat,** bedeutet dies, dass es als klassifiziert `close match` wurde. Sie können die Klassifiziergenauigkeit am besten verbessern, indem Sie Feedback zu Elementen `close match` bereitstellen. 

4. Wählen Sie ein Element aus, und öffnen Sie es.
 
 > [!TIP]
> Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann **in** der Befehlsleiste die Klassifizierung verbessern auswählen.

5. Wählen **Sie Feedback bereitstellen aus.**
6. Wenn das **Element im Bereich** Detailliertes Feedback ein echtes Positives ist, wählen Sie Match **aus.**  Wenn das Element ein falsch positives Element ist, d. h. es wurde fälschlicherweise in die Kategorie eingeschlossen, wählen Sie **Keine Übereinstimmung aus.**
7. Wenn es einen anderen Klassifikator gibt, der für das Element geeigneter wäre, können Sie ihn in der Liste **Andere trainierbare Klassifikatoren** vorschlagen auswählen. Dadurch wird der andere Klassifikator ausgelöst, um das Element auszuwerten.
8. Wählen **Sie Feedback senden** aus, um Ihre Bewertung der , Klassifizierungen zu senden und andere `match` `not a match` trainierbare Klassifikatoren vorschlagen. Wenn Sie einem Klassifikator 30 Feedbackinstanzen bereitgestellt haben, wird dieser automatisch umtrainiert. Eine Umschulung kann zwischen ein und vier Stunden dauern. Klassifizierungen können nur zweimal pro Tag umtrainiert werden.

> [!IMPORTANT]
> Diese Informationen werden an den Klassifikator in Ihrem Mandanten gesendet, **sie gehen nicht zurück zu Microsoft.**

9. Öffnen **Sie Trainable-Klassifikatoren**.
10. Der Klassifikator, der in Ihrer Kommunikationskonformitätsrichtlinie verwendet wurde, wird unter der Überschrift **Neuschulung** angezeigt.

![Klassifizierung im Umschulungsstatus](../media/classifier-retraining.png)

11. Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifikator aus, um die Übersicht über die Umschulung zu öffnen.

![Übersicht über die Klassifizierer-Umschulungsergebnisse](../media/classifier-retraining-overview.png)

12. Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umtrainierten und aktuell veröffentlichten Versionen des Klassifizierungsklassifikierers.
13. Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **Erneut veröffentlichen aus.**
14. Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifikator in der Kommunikationskonformitätsschnittstelle senden und einen weiteren Umschulungszyklus starten oder nichts tun. In diesem Fall wird die aktuell veröffentlichte Version des Klassifizierungsmoduls weiterhin verwendet. 

## <a name="details-on-republishing-recommendations"></a>Details zur erneuten Veröffentlichen von Empfehlungen

Hier finden Sie ein wenig Informationen dazu, wie wir die Empfehlung formulieren, einen umtrainierten Klassifizierer erneut zu veröffentlichen oder weitere Umschulungen vorschlagen. Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierungen.

Nach einer Umschulung bewerten wir die Leistung des Klassifikierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierungsfeeders verwendet wurden. 

- Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.
- Bei benutzerdefinierten Modellen werden elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben, verwendet.

Wir vergleichen die Leistungszahlen für beide Gruppen von Elementen für den umtrainierten und veröffentlichten Klassifikator, um eine Empfehlung zur Verbesserung der Veröffentlichung zu geben. 

## <a name="see-also"></a>Siehe auch

- [Weitere Informationen zu trainierbaren Klassifizierern](classifier-learn-about.md)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
