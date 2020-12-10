---
title: Simulieren eines Phishing-Angriffs mit Microsoft Defender für
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: In diesem Artikel erfahren Sie, wie Sie Phishing-Angriffe simulieren und Ihre Benutzer bei der Phishing-Prävention mit Angriffs Simulationstraining in Microsoft Defender für Office 365 Schulen.
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616104"
---
# <a name="simulate-a-phishing-attack"></a>Simulieren eines Phishing-Angriffs

Angriffs Simulator-Schulung über Microsoft Defender für Office 365 Sie können gutartige Cyber-Angriffssimulationen in Ihrer Organisation ausführen, um Ihre Sicherheitsrichtlinien und-Methoden zu testen und die Mitarbeiter Ihrer Organisation zu Schulen, um Ihr Bewusstsein zu schärfen und ihre Anfälligkeit für Angriffe zu verringern. Im folgenden wird erläutert, wie Sie einen Phishing-Angriff mithilfe von Attack Simulator Training simulieren.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Um einen simulierten Phishing-Angriff zu starten, navigieren Sie zum [Microsoft 365 Security Center](https://security.microsoft.com/). Klicken Sie unter **e-Mail-& Zusammenarbeit** auf **Angriff Simulator** und wechseln Sie zur Registerkarte [**Simulationen**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Wählen Sie unter **Simulationen** **die Option + Simulation starten** aus.

![Starten einer Schaltfläche "Simulation" im Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> Sie können während der Simulationserstellung jederzeit speichern und schließen, um die Konfiguration der Simulation zu einem späteren Zeitpunkt fortzusetzen.

## <a name="selecting-a-social-engineering-technique"></a>Auswählen einer Social Engineering-Technik

Wählen Sie aus vier verschiedenen Techniken aus, die von der [Mitra ATT&ck® Framework](https://attack.mitre.org/techniques/enterprise/)kuratiert wurden. Für unterschiedliche Techniken stehen unterschiedliche Nutzlasten zur Verfügung.

- Die Erfassung von **Anmelde** Informationen versucht, Anmeldeinformationen von Mitarbeitern zu sammeln, indem Sie Sie in eine bekannte Website mit Eingabefeldern zum Übermitteln eines Benutzernamens und Kennworts eintragen.
- **Schadsoftware** fügt eine böswillige Anlage zu einer Nachricht hinzu. Wenn diese Anlage geöffnet wird, führt Sie einen willkürlichen Code aus, der dem Angreifer dabei hilft, das Gerät des Ziels zu kompromittieren.
- **Link in Attachment** ist eine Art der Hybriden Anmeldeinformationen-Ernte. Ein Angreifer fügt eine URL in eine e-Mail-Anlage ein. Die URL innerhalb der Anlage folgt dem gleichen Verfahren wie das Sammeln von Anmeldeinformationen.
- **Mit Link zu Schadsoftware** wird ein beliebiger Code aus einer Datei ausgeführt, die auf einer bekannten Dateifreigabe Website gehostet wird. Ein Link zu dieser bösartigen Datei wird der Nachricht hinzugefügt, die an das Ziel gesendet wurde, und wenn Sie darauf klicken, wird die Datei ausgeführt, und der Angreifer kann das Ziel Gerät kompromittieren.

> [!TIP]
> Durch Klicken auf **Details anzeigen** in der Beschreibung jeder Technik werden weitere Informationen zur Technik sowie die Simulationsschritte für diese Technik angezeigt.
>
> ![Simulationsschritte für das Sammeln von Anmeldeinformationen im Angriffs Simulationstraining im Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

Nachdem Sie die Technik ausgewählt und auf **weiter** geklickt haben, geben Sie Ihrer Simulation einen Namen und optional eine Beschreibung.

## <a name="selecting-a-payload"></a>Auswählen einer Nutzlast

Als nächstes müssen Sie entweder eine Nutzlast aus dem bereits vorhandenen Nutz Last Katalog auswählen.

Bei der Auswahl von Nutzlasten stehen Ihnen mehrere Datenpunkte zur Verfügung:

- **Klickrate** zählt, wie viele Personen auf diese Nutzlast geklickt haben.
- **Prognostizierte Kompromiss Rate** prognostiziert den Prozentsatz der Personen, die von dieser Nutzlast aufgrund historischer Daten für diese Nutzlast in Microsoft Defender für Office 365 Kunden kompromittiert werden.
- **Gestartete Simulationen** zählt die Häufigkeit, mit der diese Nutzlast in anderen Simulationen verwendet wurde.
- Die **Komplexität**, die über **Filter** verfügbar ist, wird basierend auf der Anzahl der Indikatoren innerhalb der Nutzlast berechnet, die der Hinweis darauf abzielt, dass es sich um einen Angriff handelt. Mehr Indikatoren führen zu einer geringeren Komplexität.
- **Source**, verfügbar über **Filter**, gibt an, ob die Nutzlast auf Ihrem Mandanten erstellt wurde oder ein Bestandteil des bereits vorhandenen Payload-Katalogs (Global) von Microsoft ist.

![Ausgewählte Nutzlast innerhalb der Angriffs Simulations Schulung im Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

Wählen Sie in der Liste eine Nutzlast aus, um eine Vorschau der Nutzlast mit zusätzlichen Informationen anzuzeigen.

Wenn Sie eine eigene Nutzlast erstellen möchten, lesen Sie [Erstellen einer Nutzlast für die Angriffs Simulations Schulung](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Zielgruppenadressierung

Jetzt ist es an der Zeit, die Zielgruppe dieser Simulation auszuwählen. Sie können auswählen, dass **alle Benutzer in Ihrer Organisation eingeschlossen** oder **nur bestimmte Benutzer und Gruppen eingeschlossen** werden sollen.

Wenn Sie **nur bestimmte Benutzer und Gruppen einbeziehen** möchten, können Sie entweder Folgendes verwenden:

- **Fügen Sie Benutzer hinzu**, mit denen Sie die Suche für Ihren Mandanten sowie erweiterte Such-und Filterfunktionen nutzen können, beispielsweise für Benutzer, die in den letzten drei Monaten nicht auf eine Simulation ausgerichtet waren.
  ![Benutzer Filterung beim Angriffs Simulationstraining im Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)
- Mit dem **Import aus CSV** können Sie eine vordefinierte Gruppe von Benutzern für diese Simulation importieren.

## <a name="assigning-training"></a>Zuweisen von Schulungen

Es wird empfohlen, eine Schulung für jede Simulation zuzuweisen, da Mitarbeiter, die die Schulung durchlaufen, für ähnliche Angriffe unempfindlicher sind.

Sie können entweder eine Schulung für Sie festlegen oder selbst Schulungskurse und Module auswählen.

Wählen Sie das **Fälligkeitsdatum für Schulungen** aus, um sicherzustellen, dass Mitarbeiter die Schulung rechtzeitig abgeschlossen haben.

> [!NOTE]
> Wenn Sie Kurse und Module selbst auswählen, können Sie weiterhin den empfohlenen Inhalt sowie alle verfügbaren Kurse und Module anzeigen.
>
> ![Hinzufügen einer empfohlenen Schulung in der Schulung zur Angriffssimulation im Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

In den nächsten Schritten müssen Sie **Schulungen hinzufügen** , wenn Sie sich für die Auswahl entschieden haben, und passen Sie Ihre Schulungsziel Seite an. Sie können die Startseite der Schulung in einer Vorschau anzeigen und die Kopfzeile und den Textkörper ändern.

## <a name="launch-details-and-review"></a>Starten von Details und überprüfen

Nachdem alles konfiguriert wurde, können Sie diese Simulation sofort starten oder zu einem späteren Zeitpunkt planen. Sie müssen auch auswählen, wann diese Simulation beendet werden soll. Die Aufzeichnung der Interaktion mit dieser Simulation wird nach der ausgewählten Zeit angehalten.

**Aktivieren Sie die regionsbezogene Zustellungs Zeitzonen** , um simulierte Angriffsmeldungen an Ihre Mitarbeiter während der Arbeitszeit basierend auf Ihrer Region zu liefern.

Wenn Sie fertig sind, klicken Sie auf **weiter** , und überprüfen Sie die Details der Simulation. Klicken Sie auf **Bearbeiten** auf einem der Teile, um zurückzugehen, und ändern Sie alle Details, die geändert werden müssen. Klicken Sie nach Abschluss des Vorganges auf über **Mitteln**.
