---
title: Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können erfahren, wie sich Angriffssimulationsschulungen im Microsoft 365 Defender-Portal auf Mitarbeiter auswirken und erkenntnisse aus Simulations- und Schulungsergebnissen gewinnen.
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878376"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen

**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)

Microsoft bietet Ihnen im Rahmen der Angriffssimulationsschulung Einblicke basierend auf den Ergebnissen von Simulationen und Schulungen, die Mitarbeiter durchlaufen haben. Diese Erkenntnisse helfen Ihnen, über den Fortschritt der Bedrohungsbereitschaft Ihrer Mitarbeiter auf dem Laufenden zu bleiben, und empfehlen die nächsten Schritte, um Ihre Mitarbeiter und Ihre Umgebung besser auf Angriffe vorzubereiten.

Wir arbeiten kontinuierlich daran, die Einblicke zu erweitern, die Ihnen zur Verfügung stehen. Verhaltensauswirkungen und empfohlene Aktionen sind derzeit verfügbar. Beginnen Sie mit [dem Angriffssimulationstraining im Microsoft 365 Defender-Portal.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Verhaltensauswirkungen auf die Gefährdungsrate

Auf der Registerkarte **"Übersicht"** des Angriffssimulationstrainings finden Sie die Auswirkungen auf das Verhalten auf die Karte mit **der Kompromittierungsrate.** Diese Karte zeigt, wie mitarbeiter mit den Simulationen vertraut waren, die Sie ausgeführt haben, im Gegensatz zur **prognostizierten Kompromittiertrate.** Sie können diese Erkenntnisse verwenden, um den Fortschritt der Bedrohungsbereitschaft der Mitarbeiter nachzuverfolgen, indem Sie mehrere Simulationen für dieselben Gruppen von Mitarbeitern ausführen.

Im Diagramm sehen Sie Folgendes:

- **Die prognostizierte Kompromittierungsrate,** die die durchschnittliche Kompromittierungsrate für Simulationen widerspiegelt, die dieselbe Nutzlast für andere Microsoft 365 Mandanten verwenden, die Angriffssimulationsschulungen verwenden.
- **Die tatsächliche Kompromittierungsrate** spiegelt den Prozentsatz der Mitarbeiter wider, die für die Simulation verantwortlich sind.

Darüber hinaus `<number> less susceptible to phishing` spiegelt den Unterschied zwischen der tatsächlichen Anzahl von Mitarbeitern, die durch den Angriff kompromittiert wurden, und der prognostizierten Gefährdungsrate wider. Diese Anzahl von Mitarbeitern wird in Zukunft mit geringerer Wahrscheinlichkeit durch ähnliche Angriffe kompromittiert, während sie zeigt, wie sich die Mitarbeiter insgesamt im Gegensatz zur `<percent%> better than predicted rate` prognostizierten Kompromissrate verhalten haben.

> [!div class="mx-imgBorder"]
> ![Übersicht über die Verhaltensauswirkungskarte für Angriffssimulationsschulungen](../../media/attack-sim-preview-behavior-impact-card.png)

Klicken Sie auf **"Simulationen und Schulungseffizienzbericht anzeigen",** um einen detaillierteren Bericht anzuzeigen. Dieser Bericht enthält die gleichen Informationen mit zusätzlichem Kontext aus der Simulation selbst (z. B. Simulationstechnik und Gesamtzahl der benutzerzielen).

## <a name="recommended-actions"></a>Empfohlene Aktionen

Wenn Sie auf der Registerkarte [ **"Simulationen"**](https://security.microsoft.com/attacksimulator?viewid=simulations)eine Simulation auswählen, gelangen Sie zu den Simulationsdetails, in denen Sie den Abschnitt **"Empfohlene Aktionen"** finden.

Der Abschnitt "Empfohlene Aktionen" enthält empfehlungen wie in [der Microsoft-Sicherheitsbewertung](../defender/microsoft-secure-score.md)verfügbar. Diese Empfehlungen basieren auf der Nutzlast, die in der Simulation verwendet wird, und helfen Ihnen, Ihre Mitarbeiter und Ihre Umgebung zu schützen. Wenn Sie auf jede Verbesserungsmaßnahme klicken, gelangen Sie zu den Details.

> [!div class="mx-imgBorder"]
> ![Abschnitt "Empfehlungsaktionen" zu Angriffssimulationsschulungen](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Links zu verwandten Themen

[Erste Schritte mit dem Angriffssimulationstraining](attack-simulation-training-get-started.md)

[Erstellen einer Phishingangriffssimulation](attack-simulation-training.md)

[Erstellen einer Nutzlast für die Schulung Ihrer Mitarbeiter](attack-simulation-training-payloads.md)
