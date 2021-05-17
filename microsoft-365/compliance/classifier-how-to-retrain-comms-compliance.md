---
title: Neutrainieren eines Klassifizierers in der Kommunikationscompliance
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
description: Erfahren Sie, wie Sie Feedback zu einem trainierbaren Klassifikator in der Kommunikationskonformität bereitstellen.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918146"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Neutrainieren eines Klassifizierers in der Kommunikationscompliance

Ein Microsoft 365 trainierbarer Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben. Nach der Ausbildung können Sie es verwenden, um Elemente für die Anwendung Office Vertraulichkeitsbezeichnungen, Kommunikationskonformitätsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien zu identifizieren.

In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifikatoren und einigen vordefinierten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bereitstellen.

Weitere Informationen zu den verschiedenen Typen von Klassifizierungen finden Sie [unter Learn about trainable classifiers](classifier-learn-about.md).

## <a name="permissions"></a>Berechtigungen

So greifen Sie auf Klassifikatoren im Microsoft 365 Compliance Center zu:

- Die Rolle des Complianceadministrators oder der Compliancedatenadministrator ist erforderlich, um einen Klassifizierer zu schulen.

Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierungen in den folgenden Szenarien verwenden zu können:

- Szenario der Kommunikationskonformitätsrichtlinie: Insider Risk Management Admin, Supervisory Review Administrator 

## <a name="overall-workflow"></a>Gesamtworkflow

> [!IMPORTANT]
> Sie geben Feedback in der Compliancelösung, die den Klassifizierungs-Klassifikator als Bedingung verwendet. **Wenn Sie nicht über eine Kommunikationskonformitätsrichtlinie verfügen, die einen Klassifikator als Bedingung verwendet, beenden Sie hier.**

Wenn Sie Ihre Klassifizierungen verwenden, können Sie die Genauigkeit der Klassifizierungen erhöhen, die sie machen. Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder nicht übereinstimmend identifiziert wurden. Nachdem Sie 30 Auswertungen für einen Klassifikator erstellt haben, wird dieses Feedback benötigt und automatisch neu trainiert.

Weitere Informationen zum allgemeinen Workflow zum Umschulungstraining eines Klassifikierers finden Sie unter [Prozessablauf zum Umschulungen eines Klassifizierers](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Ein Klassifikator muss bereits veröffentlicht und verwendet werden, bevor er umtrainiert werden kann.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>So umtrainieren Sie einen Klassifizierer in Kommunikationskonformitätsrichtlinien

1. Öffnen Sie die Kommunikationskonformitätsrichtlinie, die einen Klassifikator als Bedingung verwendet, und wählen Sie eines der identifizierten Elemente aus der **Liste Ausstehend** aus.
2. Wählen Sie die Auslassungs- und **Verbesserungsklassifikation aus.**
3. Wenn das **Element im Bereich** Detailliertes Feedback ein echtes Positives ist, wählen Sie Match **aus.**  Wenn das Element ein falsch positives Element ist, d. h. es wurde fälschlicherweise in die Kategorie eingeschlossen, wählen Sie **Keine Übereinstimmung aus.**
4. Wenn es einen anderen Klassifikator gibt, der für das Element geeigneter wäre, können Sie ihn in der Liste **Andere trainierbare Klassifikatoren** vorschlagen auswählen. Dadurch wird der andere Klassifikator ausgelöst, um das Element auszuwerten.

> [!TIP]
> Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann **detailliertes** Feedback in der Befehlsleiste bereitstellen auswählen.

5. Wählen **Sie Feedback senden** aus, um Ihre Bewertung der , Klassifizierungen zu senden und andere `match` `not a match` trainierbare Klassifikatoren vorschlagen. Wenn Sie einem Klassifikator 30 Feedbackinstanzen bereitgestellt haben, wird dieser automatisch umtrainiert. Eine Umschulung kann zwischen 1 und 4 Stunden dauern. Klassifizierungen können nur zweimal pro Tag umtrainiert werden.

> [!IMPORTANT]
> Diese Informationen werden an den Klassifikator in Ihrem Mandanten gesendet, **sie gehen nicht zurück zu Microsoft.**

6.  Öffnen Sie **die Seite Datenklassifizierung** im **Microsoft 365 Compliance Center**.
7. Öffnen **Sie Trainable-Klassifikatoren**.
8. Der Klassifikator, der in Ihrer Kommunikationskonformitätsrichtlinie verwendet wurde, wird unter der Überschrift **Neuschulung** angezeigt.

![Klassifizierung im Umschulungsstatus](../media/classifier-retraining.png)

9. Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifikator aus, um die Übersicht über die Umschulung zu öffnen.

![Übersicht über die Klassifizierer-Umschulungsergebnisse](../media/classifier-retraining-overview.png)

10. Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umtrainierten und aktuell veröffentlichten Versionen des Klassifizierungsklassifikierers.
11. Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **Erneut veröffentlichen aus.**
12. Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifikator in der Kommunikationskonformitätsschnittstelle senden und einen weiteren Umschulungszyklus starten oder nichts tun. In diesem Fall wird die aktuell veröffentlichte Version des Klassifizierungsmoduls weiterhin verwendet. 

## <a name="details-on-republishing-recommendations"></a>Details zur erneuten Veröffentlichen von Empfehlungen

Hier finden Sie ein wenig Informationen dazu, wie wir die Empfehlung formulieren, einen umtrainierten Klassifizierer erneut zu veröffentlichen oder weitere Umschulungen vorschlagen. Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierungen.

Nach einer Umschulung bewerten wir die Leistung des Klassifikierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierungsfeeders verwendet wurden. 

- Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.
- Bei benutzerdefinierten Modellen werden elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben, verwendet.

Wir vergleichen die Leistungszahlen für beide Gruppen von Elementen für den umtrainierten und veröffentlichten Klassifikator, um eine Empfehlung zur Verbesserung der Veröffentlichung zu geben. 

## <a name="see-also"></a>Siehe auch

- [Weitere Informationen zu trainierbaren Klassifizierern](classifier-learn-about.md)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)