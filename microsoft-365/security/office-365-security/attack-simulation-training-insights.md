---
title: Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratoren können erfahren, wie die Angriffs Simulations Schulung im Microsoft 365-Sicherheitscenter Mitarbeiter betrifft und Einblicke aus Simulations-und Schulungs Ergebnissen gewinnen kann.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667595"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen

Im Rahmen des Angriffs simulationstrainings bietet Ihnen Microsoft Einblicke, die auf Ergebnissen von Simulationen und Schulungen basieren, die Mitarbeiter durchlaufen haben. Diese Erkenntnisse helfen Ihnen, sich über den Fortschritt der Gefahren Bereitschaft Ihrer Mitarbeiter auf dem Laufenden zu halten und weitere Schritte zur besseren Vorbereitung Ihrer Mitarbeiter und ihrer Umgebung auf Angriffe zu empfehlen.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Wir arbeiten kontinuierlich an der Erweiterung der Einblicke, die Ihnen zur Verfügung stehen. Die Auswirkungen auf das Verhalten und die empfohlenen Aktionen sind derzeit verfügbar. Um zu beginnen, fahren Sie mit dem Kopf zur [Angriffssimulation im Microsoft 365 Security Center fort](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Auswirkungen auf das Verhalten auf die Kompromiss Rate

Auf der Registerkarte " **Übersicht** " des Angriffs simulationstrainings erfahren Sie, wie sich die Auswirkungen auf die Karte mit **kompromittierenden Preisen Verhalten** . Diese Karte zeigt, wie Mitarbeiter mit den von Ihnen ausgeführten Simulationen im Gegensatz zur **prognostizierten Kompromiss Rate** umgehen. Sie können diese Einblicke verwenden, um den Fortschritt der Bedrohungs Bereitschaft von Mitarbeitern nachzuverfolgen, indem Sie mehrere Simulationen für dieselben Mitarbeitergruppen durchführen.

Im Diagramm können Sie Folgendes sehen:

- **Prognostizierte Kompromiss Rate** , die die durchschnittliche Kompromiss Rate für Simulationen unter Verwendung desselben Lasten Typs in anderen Microsoft 365-Mandanten widerspiegelt, die die Angriffs Simulations Schulung verwenden.
- " **Tatsächliche Kompromiss Rate** " gibt den Prozentsatz der Mitarbeiter an, die für die Simulation abgestürzt sind.

Darüber hinaus wird `<number> less susceptible to phishing` der Unterschied zwischen der tatsächlichen Anzahl von Mitarbeitern, die durch den Angriff gefährdet sind, und der prognostizierten Kompromiss Rate reflektiert. Die Wahrscheinlichkeit, dass diese Anzahl von Mitarbeitern in Zukunft durch ähnliche Angriffe gefährdet wird, zeigt an, `<percent%> better than predicted rate` wie die Mitarbeiter insgesamt im Gegensatz zur prognostizierten Kompromiss Rate gehandelt haben.

> [!div class="mx-imgBorder"]
> ![Übersicht über das Verhalten Impact Card on Attack Simulation Training](../../media/attack-sim-preview-behavior-impact-card.png)

Wenn Sie einen detaillierteren Bericht erhalten möchten, klicken Sie auf **Simulationen und Trainings Wirksamkeits Bericht anzeigen**. Dieser Bericht enthält dieselben Informationen mit zusätzlichem Kontext aus der Simulation selbst (beispielsweise die Simulationstechnik und die Zielgruppe der Gesamtbenutzer).

## <a name="recommended-actions"></a>Empfohlene Aktionen

Klicken Sie auf der [Registerkarte **Simulationen**](https://security.microsoft.com/attacksimulator?viewid=simulations)auf eine Simulation, und Sie gelangen zu den Simulationsdetails, auf denen Sie den Abschnitt **Empfohlene Aktionen** finden.

Im Abschnitt Empfohlene Aktionen werden Empfehlungen beschrieben, die in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)zur Verfügung stehen. Diese Empfehlungen basieren auf der in der Simulation verwendeten Nutzlast und helfen Ihnen beim Schutz Ihrer Mitarbeiter und ihrer Umgebung. Durch Klicken auf jede Verbesserungs Aktion gelangen Sie zu den Details.

> [!div class="mx-imgBorder"]
> ![Abschnitt "Empfehlungs Aktionen" bei Angriffs Simulationstraining](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Links zu verwandten Themen

**Angriffs Simulator** [Erstellen einer Phishing-Angriffssimulation](attack-simulation-training.md) und [Erstellen einer Nutzlast zur Schulung Ihrer Mitarbeiter](attack-simulation-training-payloads.md)
