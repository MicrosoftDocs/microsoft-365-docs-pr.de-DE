---
title: Erstellen einer Nutzlast für das Training zur Angriffssimulation
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können erfahren, wie Sie benutzerdefinierte Nutzlasten für das Training zur Angriffssimulation in Microsoft Defender für Office 365 erstellen.
ms.openlocfilehash: e3285b99d5b64255b9fdbda8c76b6f133aa013b2
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870863"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen

Microsoft bietet einen robusten Nutzlastkatalog für verschiedene Social -Engineering-Techniken, die Sie mit Ihrer Angriffssimulationsschulung koppeln können. Möglicherweise möchten Sie jedoch benutzerdefinierte Nutzlasten erstellen, die für Ihre Organisation besser funktionieren. In diesem Artikel wird beschrieben, wie Sie eine Nutzlast in der Angriffssimulationsschulung in Microsoft Defender für Office 365 erstellen.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

You can create a payload by clicking on **Create a payload** in either the dedicated [ **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the simulation creation [wizard](attack-simulation-training.md#selecting-a-payload).

Im ersten Schritt des Assistenten müssen Sie einen Nutzlasttyp auswählen. **Derzeit ist nur E-Mail verfügbar.**

Wählen Sie als Nächstes eine zugeordnete Technik aus. Weitere Informationen zu Techniken finden Sie unter ["Auswählen einer Social Engineering-Technik".](attack-simulation-training.md#selecting-a-social-engineering-technique)

Benennen Sie im nächsten Schritt Ihre Nutzlast. Optional können Sie ihm eine Beschreibung geben.

## <a name="configure-payload"></a>Konfigurieren der Nutzlast

Jetzt ist es an der Zeit, Ihre Nutzlast zu erstellen. Geben Sie den Namen, die E-Mail-Adresse und den Betreff der E-Mail im Abschnitt **"Absenderdetails"** ein. Wählen Sie eine Phishing-URL aus der bereitgestellten Liste aus. Diese URL wird später in den Nachrichtentext eingebettet.

> [!TIP]
> Sie können eine interne E-Mail für den Absender Ihrer Nutzlast auswählen, wodurch die Nutzlast als von einem anderen Mitarbeiter des Unternehmens stammt. Dies erhöht die Anfälligkeit für die Nutzlast und trägt dazu bei, die Mitarbeiter über das Risiko interner Bedrohungen zu informieren.

Zum Erstellen Ihrer Nutzlast steht ein Rich-Text-Editor zur Verfügung. Sie können auch eine E-Mail importieren, die Sie zuvor erstellt haben. Wenn Sie den Textkörper der E-Mail erstellen, nutzen Sie die dynamischen Tags, um die E-Mail an Ihre Ziele zu personalisieren.  Klicken **Sie auf den Link "Phishing",** um die zuvor ausgewählte Phishing-URL dem Nachrichtentext hinzuzufügen.

![Phishinglink und dynamische Tags, die in der Nutzlasterstellung für Microsoft Defender für Office 365 hervorgehoben sind](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Um Zeit zu sparen, aktivieren Sie die Option, um alle Links in der E-Mail-Nachricht durch **den Phishinglink zu ersetzen.**

Nachdem Sie die Nutzlast nach Ihren Wünschen erstellen möchten, klicken Sie auf **"Weiter".**

## <a name="adding-indicators"></a>Hinzufügen von Indikatoren

Indikatoren helfen Mitarbeitern bei der Angriffssimulation, den Hinweis zu verstehen, nach dem sie bei zukünftigen Angriffen suchen können. Klicken Sie zu Beginn auf **"Indikator hinzufügen".**

Wählen Sie in der Dropdownliste einen Indikator aus, den Sie verwenden möchten. Diese Liste ist so krümmt, dass sie die häufigsten Hinweise enthält, die in Phishing-E-Mail-Nachrichten angezeigt werden. Stellen Sie nach der Auswahl sicher, dass die Anzeigeplatzierung im Textkörper der E-Mail festgelegt **ist,** und klicken Sie auf **"Text auswählen".** Markieren Sie den Teil Ihrer Nutzlast, in dem dieser Indikator angezeigt wird, und klicken Sie auf **"Auswählen".**

![Hervorgehobener Text im Nachrichtentext, der einem Indikator im Angriffssimulationstraining hinzugefügt werden soll](../../media/attack-sim-preview-select-text.png)

Fügen Sie eine benutzerdefinierte Beschreibung hinzu, um den Indikator zu beschreiben, und klicken Sie in den Vorschauframe des Indikators, um eine Vorschau des Indikators anzuzeigen. Klicken Sie anschließend auf **"Hinzufügen".** Wiederholen Sie diese Schritte, bis Sie alle Indikatoren in Ihrer Nutzlast abgedeckt haben.

## <a name="review-payload"></a>Nutzlast überprüfen

Sie sind damit fertig, Ihre Nutzlast zu erstellen. Jetzt ist es an der Zeit, die Details zu überprüfen und eine Vorschau Ihrer Nutzlast anzuzeigen. Die Vorschau enthält alle Von Ihnen erstellten Indikatoren. In diesem Schritt können Sie jeden Teil der Nutzlast bearbeiten. Sobald sie erfüllt ist, **übermitteln Sie** Ihre Nutzlast.

> [!IMPORTANT]
> Nutzlasten, die Sie erstellt haben, haben **den Mandanten** als Quelle. Stellen Sie beim Auswählen von Nutzlasten sicher, dass Sie den Mandanten nicht **herausfiltern.**

## <a name="related-links"></a>Verwandte Links

[Erste Schritte mit dem Training zur Angriffssimulation](attack-simulation-training-get-started.md)

[Erstellen einer Phishingangriffssimulation](attack-simulation-training.md)

[Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen](attack-simulation-training-insights.md)
