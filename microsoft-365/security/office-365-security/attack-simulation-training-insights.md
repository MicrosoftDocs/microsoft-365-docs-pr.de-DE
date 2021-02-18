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
description: Administratoren können erfahren, wie sich die Schulung zur Angriffssimulation im Microsoft 365 Security Center auf Die Mitarbeiter auswirkt und einblicke aus Simulations- und Schulungsergebnissen gewinnen kann.
ms.technology: mdo
ms.openlocfilehash: 43319089f604d32bf295392dd223cf65af8bd4be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288657"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen

Im Rahmen der Schulung zur Angriffssimulation bietet Microsoft Ihnen Einblicke basierend auf den Ergebnissen von Simulationen und Schulungen, die die Mitarbeiter durch geführt haben. Diese Einblicke helfen Ihnen, über den Fortschritt der Bedrohungsbereitschaft Ihrer Mitarbeiter auf dem Laufenden zu bleiben, und empfehlen die nächsten Schritte, um Ihre Mitarbeiter und Ihre Umgebung besser auf Angriffe vorzubereiten.

Wir arbeiten kontinuierlich daran, die Einblicke zu erweitern, die Ihnen zur Verfügung stehen. Auswirkungen auf das Verhalten und empfohlene Aktionen sind derzeit verfügbar. To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Auswirkungen des Verhaltens auf die Compromise Rate

Auf der **Registerkarte "Übersicht"** des Angriffssimulationstrainings finden Sie die Auswirkungen des Verhaltens **auf die Karte mit der Angriffsrate.** Diese Karte zeigt, wie mitarbeiter mit den Simulationen, die Sie im Gegensatz zur vorhergesagten **Compromise Rate .** Sie können diese Erkenntnisse verwenden, um den Fortschritt der Bedrohungsbereitschaft der Mitarbeiter nachverfolgt, indem Sie mehrere Simulationen für die gleichen Gruppen von Mitarbeitern ausführen.

Im Diagramm sehen Sie:

- **Vorhergesagte Kompromissrate,** die die durchschnittliche Kompromissrate für Simulationen mit der gleichen Nutzlast für andere Microsoft 365-Mandanten widerspiegelt, die Attack Simulation Training verwenden.
- **Die tatsächliche Compromise Rate** gibt den Prozentsatz der Mitarbeiter an, die für die Simulation anfingen.

Darüber hinaus wird der Unterschied zwischen der tatsächlichen Anzahl der durch den Angriff gefährdeten Mitarbeiter und der `<number> less susceptible to phishing` vorhergesagten Kompromissrate widersprobiert. Diese Anzahl von Mitarbeitern ist in Zukunft weniger wahrscheinlich durch ähnliche Angriffe gefährdet, während sie im Gegensatz zur vorhergesagten Kompromissrate angibt, wie die Mitarbeiter insgesamt `<percent%> better than predicted rate` waren.

> [!div class="mx-imgBorder"]
> ![Übersicht über die Verhaltenswirkungskarte für das Training zur Angriffssimulation](../../media/attack-sim-preview-behavior-impact-card.png)

Klicken Sie zum Anzeigen eines detaillierten Berichts auf **"Simulationen anzeigen" und "Schulungseffizienzbericht".** Dieser Bericht enthält die gleichen Informationen mit zusätzlichem Kontext aus der Simulation selbst (z. B. Simulationstechnik und zielgruppe Benutzer insgesamt).

## <a name="recommended-actions"></a>Empfohlene Aktionen

Auf der [ **Registerkarte "Simulationen"**](https://security.microsoft.com/attacksimulator?viewid=simulations)werden Sie durch Auswählen einer Simulation zu den Simulationsdetails, wo Sie den Abschnitt "Empfohlene **Aktionen"** finden.

Im Abschnitt "Empfohlene Aktionen" finden Sie Details zu den Empfehlungen, die in [der Microsoft Secure Score verfügbar sind.](../mtp/microsoft-secure-score.md) Diese Empfehlungen basieren auf der Nutzlast, die in der Simulation verwendet wird, und helfen Ihnen, Ihre Mitarbeiter und Ihre Umgebung zu schützen. Wenn Sie auf die einzelnen Verbesserungsmaßnahmen klicken, werden Sie zu den Details der jeweiligen Verbesserungsaktion auf dem Konto f?2013 f?nen.

> [!div class="mx-imgBorder"]
> ![Abschnitt "Empfehlungsaktionen" zum Training zur Angriffssimulation](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Links zu verwandten Themen

[Erste Schritte mit dem Angriffssimulationstraining](attack-simulation-training-get-started.md)

[Erstellen einer Phishingangriffssimulation](attack-simulation-training.md)

[Erstellen einer Nutzlast für die Schulung Ihrer Mitarbeiter](attack-simulation-training-payloads.md)
