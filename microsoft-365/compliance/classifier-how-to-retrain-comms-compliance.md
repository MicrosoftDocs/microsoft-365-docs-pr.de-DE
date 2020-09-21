---
title: Vorgehensweise Umschulung einer Klassifizierung in Communications Compliance (Vorschau)
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
description: Hier erfahren Sie, wie Sie Feedback für eine Lernende Klassifizierung in Communications Compliance bereitstellen.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132324"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a>Vorgehensweise Umschulung einer Klassifizierung in Communications Compliance (Vorschau)

Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben. Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.

In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und einigen vorab ausgebildeten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bieten.

Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).

## <a name="permissions"></a>Berechtigungen

So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierungen zu:

- die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.

Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:

- Kommunikations Konformitätsrichtlinien Szenario: Administrator für Insider Risiko Management, Aufsichts Überprüfungs Administrator 

## <a name="overall-workflow"></a>Allgemeiner Workflow

> [!IMPORTANT]
> Sie geben Feedback in der kompatibilitätslösung an, die die Klassifizierung als Bedingung verwendet. **Wenn Sie keine Communications-Konformitätsrichtlinie haben, die eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**

Wenn Sie Ihre Klassifizierungen verwenden, möchten Sie möglicherweise die Genauigkeit der Klassifizierungen verbessern, die Sie vornehmen. Hierzu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder keine Übereinstimmung identifiziert wurden. Nachdem Sie 30 Auswertungen für eine Klassifizierung vorgenommen haben, wird dieses Feedback erstellt und automatisch umgeschult.

Weitere Informationen zum allgemeinen Workflow der Umschulung einer Klassifizierung finden Sie unter [Prozessablauf für die Umschulung einer Klassifizierung](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Eine Klassifizierung muss bereits veröffentlicht und verwendet werden, bevor Sie neu trainiert werden kann.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a>Vorgehensweise Umschulung einer Klassifizierung in Communication Compliance Policies (Preview)

1. Öffnen Sie die Kommunikations Konformitätsrichtlinie, die eine Klassifizierung als Bedingung verwendet, und wählen Sie eines der identifizierten Elemente aus der Liste **Ausstehend** aus.
2. Wählen Sie die Auslassungspunkte aus, und optimieren Sie die **Klassifizierung**.
3. Wählen Sie im **detailed Feedback** -Bereich, wenn das Element ein wahres positives Ergebnis ist, **übereinstimmen**aus.  Wenn es sich bei dem Element um ein falsch positives Ergebnis handelt, es in der Kategorie nicht korrekt enthalten war, wählen Sie **keine Übereinstimmung**aus.
4. Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, können Sie es in der Liste **andere Auszubildende Klassifizierer vorschlagen** auswählen. Dadurch wird die andere Klassifizierung ausgelöst, um das Element auszuwerten.

> [!TIP]
> Sie können gleichzeitig Feedback zu mehreren Elementen geben, indem Sie Sie alle auswählen und dann in der Befehlsleiste **ausführliches Feedback** auswählen.

5. Wählen Sie **Feedback senden** aus, um eine Bewertung `match` der `not a match` Klassifizierungen zu senden und andere Schulungs Klassifizierer vorzuschlagen. Wenn Sie 30 Instanzen von Feedback für eine Klassifizierung bereitgestellt haben, wird Sie automatisch umgeschult. Eine Umschulung kann von 1-4 Stunden dauern. Klassifizierungen können nur zweimal pro Tag umgeschult werden.

> [!IMPORTANT]
> Diese Informationen werden in Ihrem Mandanten an die Klassifizierung weitergeleitet, und **es geht nicht zurück zu Microsoft**.

6.  Öffnen Sie die Seite **Datenklassifizierung** im **Microsoft 365 Compliance Center**.
7. Offene **Schulungs Klassifizierer (Vorschau)**.
8. Die Klassifizierung, die in Ihrer Communications-Konformitätsrichtlinie verwendet wurde, wird unter der Überschrift " **Umschulung** " angezeigt.

![Klassifizierung in Umschulungs Status](../media/classifier-retraining.png)

9. Nachdem die Umschulung abgeschlossen ist, wählen Sie die Klassifizierung aus, um die Umschulungs Übersicht zu öffnen.

![Übersicht über Klassifizierungs-Umschulungs Ergebnisse](../media/classifier-retraining-overview.png)

10. Überprüfen Sie die empfohlene Aktion und die Vorhersage Vergleiche der umgeschulten und derzeit veröffentlichten Versionen der Klassifizierung.
11. Wenn Sie mit den Ergebnissen der Umschulung zufrieden waren, wählen Sie **erneut veröffentlichen**aus.
12. Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie der Klassifizierung in der Schnittstelle Communications Compliance zusätzliches Feedback geben und einen weiteren Umschulungs Zyklus starten oder nichts tun, wenn die aktuell veröffentlichte Version der Klassifizierung weiterhin verwendet wird. 

## <a name="details-on-republishing-recommendations"></a>Details zur erneuten Veröffentlichung von Empfehlungen

Hier finden Sie einige Informationen darüber, wie wir die Empfehlung zur erneuten Veröffentlichung einer umgeschulten Klassifizierung formulieren oder eine weitere Umschulung vorschlagen. Dies erfordert ein wenig tieferes Verständnis der Funktionsweise von Schulungs fähigen Klassifizierungen.

Nach einem umtrainieren bewerten wir die Leistung der Klassifizierung sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren der Klassifizierung verwendet wurden. 

- Für integrierte Modelle sind Elemente, die zum Trainieren der Klassifizierung verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.
- Für benutzerdefinierte Modelle werden im ursprünglichen Training verwendete Elemente von den Websites verwendet, die Sie zum Testen und überprüfen hinzugefügt haben.

Wir vergleichen die Leistungszahlen in beiden Elementgruppen für die umgeschulte und veröffentlichte Klassifizierung, um eine Empfehlung darüber zu geben, ob eine Verbesserung der erneuten Veröffentlichung vorliegt. 

## <a name="see-also"></a>Siehe auch

- [Informationen zu Schulungs Klassifizierern (Vorschau)](classifier-learn-about.md)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
