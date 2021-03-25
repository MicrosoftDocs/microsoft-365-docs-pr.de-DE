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
description: Administratoren können lernen, wie Sie Phishingangriffe simulieren und ihre Benutzer mithilfe von Attack Simulationsschulungen in Microsoft Defender für Office 365 zur Phishingprävention schulen.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206224"
---
# <a name="simulate-a-phishing-attack"></a>Simulieren eines Phishingangriffs

Mit Dem Training zur Angriffssimulation in Microsoft Defender für Office 365 können Sie in Ihrer Organisation gutartige Cyberangriffssimulationen ausführen, um Ihre Sicherheitsrichtlinien und -methoden zu testen und Ihre Mitarbeiter zu schulen, um ihr Bewusstsein zu erhöhen und ihre Anfälligkeit für Angriffe zu verringern. In diesem Artikel werden Sie durch das Erstellen eines simulierten Phishingangriffs mithilfe von Training zur Angriffssimulation erläutert.

Informationen zu den ersten Informationen zum Training zur Angriffssimulation finden Sie unter [Erste Schritte mit attack simulation training](attack-simulation-training-get-started.md).

Öffnen Sie zum Starten eines simulierten Phishingangriffs das [Microsoft 365 Security Center,](https://security.microsoft.com/)wechseln Sie zu **E-Mail & Zusammenarbeit** Attack simulation training, und wechseln Sie zur Registerkarte \>  [**Simulationen.**](https://security.microsoft.com/attacksimulator?viewid=simulations)

Wählen **Sie unter Simulationen** **die Option + Simulation starten aus.**

![Starten einer Simulationsschaltfläche im Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> Sie können die Simulation jederzeit während der Simulationserstellung speichern und schließen, um die Konfiguration der Simulation zu einem späteren Zeitpunkt fortzufahren.

## <a name="selecting-a-social-engineering-technique"></a>Auswählen einer Social Engineering-Technik

Wählen Sie aus vier verschiedenen Techniken aus, die aus dem [MITRE ATT&CK® werden.](https://attack.mitre.org/techniques/enterprise/) Unterschiedliche Nutzlasten stehen für verschiedene Techniken zur Verfügung:

- **Die Erfassung von** Anmeldeinformationen versucht, Anmeldeinformationen zu sammeln, indem Benutzer zu einer bekannten, aussehenden Website mit Eingabefeldern zum Übermitteln eines Benutzernamens und Kennworts aufgefordert werden.
- **Eine** Schadsoftwareanlage fügt einer Nachricht eine bösartige Anlage hinzu. Wenn der Benutzer die Anlage öffnet, wird beliebiger Code ausgeführt, mit dem der Angreifer das Gerät des Ziels gefährdet.
- **Link in attachment ist** eine Art hybrider Anmeldeinformationsernte. Ein Angreifer fügt eine URL in eine E-Mail-Anlage ein. Die URL in der Anlage folgt der gleichen Technik wie die Lese von Anmeldeinformationen.
- **Bei einem Link zu Schadsoftware** wird beliebiger Code aus einer Datei ausgeführt, die in einem bekannten Dateifreigabedienst gehostet wird. Die an den Benutzer gesendete Nachricht enthält einen Link zu dieser schädlichen Datei. Öffnen Sie die Datei, und helfen Sie dem Angreifer, das Gerät des Ziels zu gefährdet.
- **Die Drive-by-URL** führt den Benutzer mit der bösartigen URL in der Nachricht zu einer vertraut aussehenden Website, die im Hintergrund ausgeführt und/oder Codecode auf dem Gerät des Benutzers installiert.

> [!TIP]
> Wenn Sie in **der Beschreibung der** einzelnen Techniken auf Details anzeigen klicken, werden weitere Informationen sowie die Simulationsschritte für die Technik angezeigt.
>
> ![Simulationsschritte für die Anmeldeinformationsernte im Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

Nachdem Sie die Technik ausgewählt und auf **Weiter** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.

## <a name="selecting-a-payload"></a>Auswählen einer Nutzlast

Als Nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutzlastkatalog auswählen.

Nutzlasten verfügen über eine Reihe von Datenpunkten, die Ihnen bei der Auswahl helfen:

- **Die Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.
- **Die vorhergesagte Kompromissrate** prognostizieren den Prozentsatz der Personen, die von dieser Nutzlast basierend auf historischen Daten für die Nutzlast in Microsoft Defender für Office 365-Kunden gefährdet werden.
- **Gestartete Simulationen** zählen, wie oft diese Nutzlast in anderen Simulationen verwendet wurde.
- **Die** Komplexität , die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, in der der Hinweis darauf zielt, dass es sich um einen Angriff handelt. Weitere Indikatoren führen zu einer geringeren Komplexität.
- **Source**, die über **Filter** verfügbar ist, gibt an, ob die Nutzlast in Ihrem Mandanten erstellt wurde oder Teil des bereits vorhandenen Nutzlastkatalogs von Microsoft (global) ist.

![Ausgewählte Nutzlast im Training zur Angriffssimulation im Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

Wählen Sie eine Nutzlast aus der Liste aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen dazu anzuzeigen.

Wenn Sie Eine eigene Nutzlast erstellen möchten, lesen Sie [Create a payload for attack simulation training](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Zielgruppenadressierung

Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen. Sie können festlegen, **dass alle Benutzer in Ihrer** Organisation oder nur bestimmte Benutzer und Gruppen enthalten **sind.**

Wenn Sie nur bestimmte Benutzer und Gruppen enthalten **möchten,** können Sie folgendes:

- **Fügen Sie Benutzer** hinzu, mit denen Sie die Suche nach Ihrem Mandanten sowie erweiterte Such- und Filterfunktionen nutzen können, z. B. für Benutzer, die in den letzten 3 Monaten nicht auf eine Simulation ausgerichtet waren.
  ![Benutzerfilterung in Angriffssimulationsschulungen im Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)
- **Mit dem Import** aus csv können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.

## <a name="assigning-training"></a>Zuweisen von Schulungen

Es wird empfohlen, für jede Simulation Schulungen zuzuordnen, da Mitarbeiter, die eine Schulung durchgehen, weniger anfällig für ähnliche Angriffe sind.

Sie können entweder festlegen, dass Ihnen Schulungen zugewiesen werden, oder Sie können selbst Schulungskurse und Module auswählen.

Wählen Sie **das Fälligkeitsdatum der** Schulung aus, um sicherzustellen, dass die Mitarbeiter ihre Schulung zeitnah beenden.

> [!NOTE]
> Wenn Sie Kurse und Module selbst auswählen, können Sie weiterhin die empfohlenen Inhalte sowie alle verfügbaren Kurse und Module anzeigen.
>
> ![Hinzufügen empfohlener Schulungen in Angriffssimulationsschulungen im Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

In den nächsten Schritten müssen  Sie Schulungen hinzufügen, wenn Sie sich dafür entschieden haben, sie selbst auszuwählen, und Ihre Schulungslandeseite anpassen. Sie können eine Vorschau der Schulungslandeseite anzeigen und die Kopfzeile und den Textkörper ändern.

## <a name="launch-details-and-review"></a>Starten von Details und Überprüfen

Nachdem nun alles konfiguriert ist, können Sie diese Simulation sofort starten oder für einen späteren Zeitpunkt planen. Sie müssen auch auswählen, wann diese Simulation beendet werden soll. Wir beenden die Erfassung der Interaktion mit dieser Simulation nach dem ausgewählten Zeitpunkt.

**Aktivieren Sie die Bereitstellung von regionenbezogenen** Zeitzonen, um simulierte Angriffsnachrichten an Ihre Mitarbeiter während ihrer Arbeitszeit basierend auf ihrer Region zu senden.

Nachdem Sie fertig sind, klicken Sie auf **Weiter,** und überprüfen Sie die Details Ihrer Simulation. Klicken Sie **auf Bearbeiten** für einen der Teile, um zurück zu wechseln und alle Details zu ändern, die geändert werden müssen. Klicken Sie nach getaner Arbeit auf **Absenden**.
