---
title: Simulieren eines Phishingangriffs mit Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können lernen, wie Sie Phishingangriffe simulieren und ihre Benutzer mithilfe von Angriffssimulationsschulungen in Microsoft Defender für Office 365 zur Phishing-Verhinderung schulen.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878364"
---
# <a name="simulate-a-phishing-attack"></a>Simulieren eines Phishingangriffs

**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)

Mit der Angriffssimulationsschulung in Microsoft Defender für Office 365 können Sie gutartig Cyberangriffssimulationen in Ihrer Organisation ausführen, um Ihre Sicherheitsrichtlinien und -praktiken zu testen, sowie Ihre Mitarbeiter schulen, um ihr Bewusstsein zu erhöhen und ihre Anfälligkeit für Angriffe zu verringern. Dieser Artikel führt Sie durch die Erstellung eines simulierten Phishingangriffs mithilfe von Angriffssimulationsschulungen.

Informationen zu den ersten Schritten zum Angriffssimulationstraining finden Sie unter ["Erste Schritte mit dem Angriffssimulationstraining".](attack-simulation-training-get-started.md)

Um einen simulierten Phishingangriff zu starten, öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com/> ), wechseln Sie zu **E-Mail &** \> **Angriffssimulationstraining** für die Zusammenarbeit, und wechseln Sie zur Registerkarte **["Simulationen".](https://security.microsoft.com/attacksimulator?viewid=simulations)**

Wählen Sie unter **"Simulationen"** die Option **+Simulation starten** aus.

![Starten einer Simulationsschaltfläche im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> Zu jedem Zeitpunkt während der Simulationserstellung können Sie speichern und die Konfiguration der Simulation zu einem späteren Zeitpunkt fortsetzen.

## <a name="selecting-a-social-engineering-technique"></a>Auswählen eines Social Engineering-Verfahrens

Wählen Sie aus vier verschiedenen Techniken aus, die aus dem [MITRE ATT&CK® Framework](https://attack.mitre.org/techniques/enterprise/)zusammengestellt wurden. Für unterschiedliche Techniken stehen unterschiedliche Nutzlasten zur Verfügung:

- Die Erfassung von **Anmeldeinformationen** versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten Website mit Eingabefeldern weitergeleitet werden, um einen Benutzernamen und ein Kennwort zu übermitteln.
- **Eine Antischadsoftwareanlage** fügt einer Nachricht eine schädliche Anlage hinzu. Wenn der Benutzer die Anlage öffnet, wird beliebiger Code ausgeführt, der dem Angreifer hilft, das Zielgerät zu kompromittieren.
- **Der Link in der Anlage** ist eine Art von Hybridlösung für die Nutzung von Anmeldeinformationen. Ein Angreifer fügt eine URL in eine E-Mail-Anlage ein. Die URL in der Anlage folgt derselben Technik wie die Anmeldeinformationsernte.
- **Links zu Schadsoftware** führen beliebigen Code aus einer Datei aus, die in einem bekannten Dateifreigabedienst gehostet wird. Die an den Benutzer gesendete Nachricht enthält einen Link zu dieser schädlichen Datei. Öffnen Sie die Datei, und helfen Sie dem Angreifer, das Zielgerät zu kompromittiv zu gestalten.
- **Drive-by-URL** ist der Ort, an dem die schädliche URL in der Nachricht den Benutzer zu einer vertraut aussehenden Website führt, die automatisch Code auf dem Gerät des Benutzers ausführt und/oder installiert.

> [!TIP]
> Wenn Sie in der Beschreibung der einzelnen Techniken auf **"Details anzeigen"** klicken, werden weitere Informationen und die Simulationsschritte für die Technik angezeigt.
>
> ![Simulationsschritte zum Sammeln von Anmeldeinformationen innerhalb des Angriffssimulationstrainings im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-sim-steps.png)

Nachdem Sie die Technik ausgewählt und auf **"Weiter"** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.

## <a name="selecting-a-payload"></a>Auswählen einer Nutzlast

Als Nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutzlastkatalog auswählen.

Nutzlasten haben eine Reihe von Datenpunkten, die Ihnen bei der Auswahl helfen:

- **Die Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.
- **Die prognostizierte Kompromittierungsrate** prognostiziert den Prozentsatz der Personen, die durch diese Nutzlast kompromittiert werden, basierend auf verlaufsbasierten Daten für die Nutzlast in Microsoft Defender für Office 365 Kunden.
- **Gestartete Simulationen** zählen, wie oft diese Nutzlast in anderen Simulationen verwendet wurde.
- **Die Komplexität,** die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, die darauf hinweisen, dass es sich um einen Angriff handelt. Mehr Indikatoren führen zu einer geringeren Komplexität.
- **Quelle,** die über **Filter** verfügbar ist, gibt an, ob die Nutzlast auf Ihrem Mandanten erstellt wurde oder Teil des bereits vorhandenen Nutzlastkatalogs (global) von Microsoft ist.

![Ausgewählte Nutzlast im Angriffssimulationstraining im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-select-payload.png)

Wählen Sie eine Nutzlast aus der Liste aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen zu sehen.

Wenn Sie Ihre eigene Nutzlast erstellen möchten, lesen Sie ["Erstellen einer Nutzlast für Angriffssimulationsschulungen".](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Zielgruppenadressierung

Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen. Sie können **alle Benutzer in Ihrer Organisation oder** nur bestimmte Benutzer und Gruppen **einschließen.**

Wenn Sie sich dafür entscheiden, **nur bestimmte Benutzer und Gruppen einzuschließen,** können Sie die folgenden Aktionen ausführen:

- **Fügen Sie Benutzer hinzu,** mit denen Sie die Suche nach Ihrem Mandanten sowie erweiterte Such- und Filterfunktionen nutzen können, z. B. für Benutzer, die in den letzten 3 Monaten nicht für eine Simulation vorgesehen waren.

  ![Benutzerfilterung in Angriffssimulationsschulungen im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-user-targeting.png)

- **Mit dem Import aus CSV** können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.

## <a name="assigning-training"></a>Zuweisen von Schulungen

Es wird empfohlen, für jede Simulation Schulungen zuzuweisen, da Mitarbeiter, die eine Schulung durchlaufen, weniger anfällig für ähnliche Angriffe sind.

Sie können entweder auswählen, ob Ihnen Schulungen zugewiesen wurden, oder selbst Schulungskurse und Module auswählen.

Wählen Sie das **Fälligkeitsdatum** der Schulung aus, um sicherzustellen, dass die Mitarbeiter ihre Schulung zeitnah abschließen.

> [!NOTE]
> Wenn Sie selbst Kurse und Module auswählen möchten, können Sie weiterhin die empfohlenen Inhalte sowie alle verfügbaren Kurse und Module anzeigen.
>
> ![Hinzufügen empfohlener Schulungen innerhalb der Angriffssimulationsschulung im Microsoft 365 Defender-Portal](../../media/attack-sim-preview-add-training.png)

In den nächsten Schritten müssen Sie **Schulungen hinzufügen,** wenn Sie sich dafür entschieden haben, sie selbst auszuwählen, und Ihre Schulungszielseite anpassen. Sie können eine Vorschau der Schulungszielseite anzeigen und die Kopfzeile und den Textkörper ändern.

## <a name="launch-details-and-review"></a>Details zum Starten und Überprüfen

Nachdem alles konfiguriert ist, können Sie diese Simulation sofort starten oder für einen späteren Zeitpunkt planen. Sie müssen auch auswählen, wann diese Simulation beendet werden soll. Wir werden die Aufzeichnung der Interaktion mit dieser Simulation nach der ausgewählten Zeit beenden.

Aktivieren Sie die **Region unterstützende Zeitzonenzustellung,** um simulierte Angriffsmeldungen an Ihre Mitarbeiter während ihrer Arbeitszeiten basierend auf ihrer Region zu übermitteln.

Wenn Sie fertig sind, klicken Sie auf **"Weiter",** und überprüfen Sie die Details Ihrer Simulation. Klicken Sie auf **"Bearbeiten"** auf einen der Teile, um zurückzugehen und alle Details zu ändern, die geändert werden müssen. Nachdem Sie fertig sind, klicken Sie auf **"Absenden".**
