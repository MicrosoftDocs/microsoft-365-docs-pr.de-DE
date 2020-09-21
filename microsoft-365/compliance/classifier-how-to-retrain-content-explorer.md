---
title: Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)
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
description: Hier erfahren Sie, wie Sie Feedback für eine Lernende Klassifizierung im Inhalts-Explorer bereitstellen.
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132327"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)

Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben. Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.

In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und einigen vorab ausgebildeten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bieten.

Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).

## <a name="permissions"></a>Berechtigungen

So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierungen zu:

- die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.

Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:

- Richtlinien Szenario für Aufbewahrungs Bezeichnungen: Rollen für die Datensatzverwaltung und Aufbewahrungsverwaltung 

## <a name="overall-workflow"></a>Allgemeiner Workflow

> [!IMPORTANT]
> Sie geben Feedback im Inhalts-Explorer für automatisch anzuwendende Aufbewahrungs Bezeichnungsrichtlinien auf Exchange-Elemente und verwenden die Klassifizierung als Bedingung. **Wenn Sie keine Aufbewahrungsrichtlinie haben, die eine Aufbewahrungs Bezeichnung automatisch auf Exchange-Elemente anwendet und eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**

Wenn Sie Ihre Klassifizierungen verwenden, möchten Sie möglicherweise die Genauigkeit der Klassifizierungen verbessern, die Sie vornehmen. Hierzu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder keine Übereinstimmung identifiziert wurden. Nachdem Sie 30 Auswertungen für eine Klassifizierung vorgenommen haben, wird dieses Feedback erstellt und automatisch umgeschult.

Weitere Informationen zum allgemeinen Workflow der Umschulung einer Klassifizierung finden Sie unter [Prozessablauf für die Umschulung einer Klassifizierung](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Eine Klassifizierung muss bereits veröffentlicht und verwendet werden, bevor Sie neu trainiert werden kann.

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)

1. Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Data Classification**  >  **Content Explorer**. 
2. Erweitern Sie unter der Liste **Filtern nach Bezeichnungen, Informationstypen oder Kategorien** den Knoten erweiterbare **Klassifizierungen**.

> [!IMPORTANT]
> Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift "Auszubildende Klassifizierer" angezeigt werden.

3. Wählen Sie die Schulungs Klassifizierung aus, die Sie in der Richtlinie für die automatische Beibehaltung von Aufbewahrungs Bezeichnungen verwendet haben. Dies ist die schulungsable Klassifizierung, der Sie Feedback geben werden.

> [!NOTE]
> Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** einen Eintrag enthält, bedeutet dies, dass das Element als klassifiziert wurde `match` .  Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** keinen Eintrag enthält, bedeutet dies, dass es als klassifiziert wurde `close match` . Sie können die Klassifizierungs Genauigkeit am meisten verbessern, indem Sie Feedback zu Elementen bereitstellen `close match` . 

4. Wählen Sie ein Element aus, und öffnen Sie es.
 
 > [!TIP]
> Sie können gleichzeitig Feedback zu mehreren Elementen geben, indem Sie Sie alle auswählen und dann in der Befehlsleiste die Option **Klassifizierung verbessern** auswählen.

5. Wählen Sie **Feedback bereitstellen**aus.
6. Wählen Sie im **detailed Feedback** -Bereich, wenn das Element ein wahres positives Ergebnis ist, **übereinstimmen**aus.  Wenn es sich bei dem Element um ein falsch positives Ergebnis handelt, es in der Kategorie nicht korrekt enthalten war, wählen Sie **keine Übereinstimmung**aus.
7. Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, können Sie es in der Liste **andere Auszubildende Klassifizierer vorschlagen** auswählen. Dadurch wird die andere Klassifizierung ausgelöst, um das Element auszuwerten.
8. Wählen Sie **Feedback senden** aus, um eine Bewertung `match` der `not a match` Klassifizierungen zu senden und andere Schulungs Klassifizierer vorzuschlagen. Wenn Sie 30 Instanzen von Feedback für eine Klassifizierung bereitgestellt haben, wird Sie automatisch umgeschult. Eine Umschulung kann eine bis vier Stunden dauern. Klassifizierungen können nur zweimal pro Tag umgeschult werden.

> [!IMPORTANT]
> Diese Informationen werden in Ihrem Mandanten an die Klassifizierung weitergeleitet, und **es geht nicht zurück zu Microsoft**.

9. Offene **Schulungs Klassifizierer (Vorschau)**.
10. Die Klassifizierung, die in Ihrer Communications-Konformitätsrichtlinie verwendet wurde, wird unter der Überschrift " **Umschulung** " angezeigt.

![Klassifizierung in Umschulungs Status](../media/classifier-retraining.png)

11. Nachdem die Umschulung abgeschlossen ist, wählen Sie die Klassifizierung aus, um die Umschulungs Übersicht zu öffnen.

![Übersicht über Klassifizierungs-Umschulungs Ergebnisse](../media/classifier-retraining-overview.png)

12. Überprüfen Sie die empfohlene Aktion und die Vorhersage Vergleiche der umgeschulten und derzeit veröffentlichten Versionen der Klassifizierung.
13. Wenn Sie mit den Ergebnissen der Umschulung zufrieden waren, wählen Sie **erneut veröffentlichen**aus.
14. Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie der Klassifizierung in der Schnittstelle Communications Compliance zusätzliches Feedback geben und einen weiteren Umschulungs Zyklus starten oder nichts tun, wenn die aktuell veröffentlichte Version der Klassifizierung weiterhin verwendet wird. 

## <a name="details-on-republishing-recommendations"></a>Details zur erneuten Veröffentlichung von Empfehlungen

Hier finden Sie einige Informationen darüber, wie wir die Empfehlung zur erneuten Veröffentlichung einer umgeschulten Klassifizierung formulieren oder eine weitere Umschulung vorschlagen. Dies erfordert ein wenig tieferes Verständnis der Funktionsweise von Schulungs fähigen Klassifizierungen.

Nach einem umtrainieren bewerten wir die Leistung der Klassifizierung sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren der Klassifizierung verwendet wurden. 

- Für integrierte Modelle sind Elemente, die zum Trainieren der Klassifizierung verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.
- Für benutzerdefinierte Modelle werden im ursprünglichen Training verwendete Elemente von den Websites verwendet, die Sie zum Testen und überprüfen hinzugefügt haben.

Wir vergleichen die Leistungszahlen in beiden Elementgruppen für die umgeschulte und veröffentlichte Klassifizierung, um eine Empfehlung darüber zu geben, ob eine Verbesserung der erneuten Veröffentlichung vorliegt. 

## <a name="see-also"></a>Siehe auch

- [Informationen zu Schulungs Klassifizierern (Vorschau)](classifier-learn-about.md)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
