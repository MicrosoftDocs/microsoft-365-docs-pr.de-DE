---
title: Erstellen einer Nutzlast für Angriffssimulationsschulungen
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können erfahren, wie Sie benutzerdefinierte Nutzlasten für Angriffssimulationsschulungen in Microsoft Defender für Office 365 erstellen.
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878760"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen

**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)

Microsoft bietet einen robusten Nutzlastkatalog für verschiedene Social Engineering-Techniken, die sie mit Ihrem Angriffssimulationstraining kombinieren können. Möglicherweise möchten Sie jedoch benutzerdefinierte Nutzlasten erstellen, die für Ihre Organisation besser funktionieren. In diesem Artikel wird beschrieben, wie Sie eine Nutzlast im Angriffssimulationstraining in Microsoft Defender für Office 365 erstellen.

Sie können eine Nutzlast erstellen, indem Sie auf der [Registerkarte "Dedizierte **Nutzlasten"**](https://security.microsoft.com/attacksimulator?viewid=payload) oder im [Simulationserstellungs-Assistenten](attack-simulation-training.md#selecting-a-payload)auf **"Nutzlast** erstellen" klicken.

Im ersten Schritt des Assistenten müssen Sie einen Nutzlasttyp auswählen. **Derzeit ist nur E-Mail verfügbar.**

Wählen Sie als Nächstes eine zugeordnete Technik aus. Weitere Informationen zu Techniken finden Sie unter ["Auswählen einer Technik für Social Engineering".](attack-simulation-training.md#selecting-a-social-engineering-technique)

Benennen Sie im nächsten Schritt Ihre Nutzlast. Optional können Sie ihr eine Beschreibung geben.

## <a name="configure-payload"></a>Konfigurieren der Nutzlast

Jetzt ist es an der Zeit, Ihre Nutzlast zu erstellen. Geben Sie im Abschnitt **"Absenderdetails"** den Namen, die E-Mail-Adresse und den Betreff der E-Mail ein. Wählen Sie eine Phishing-URL aus der bereitgestellten Liste aus. Diese URL wird später in den Textkörper der Nachricht eingebettet.

> [!TIP]
> Sie können eine interne E-Mail für den Absender Ihrer Nutzlast auswählen, wodurch die Nutzlast so angezeigt wird, dass sie von einem anderen Mitarbeiter des Unternehmens stammt. Dies erhöht die Anfälligkeit für die Nutzlast und hilft mitarbeitern, das Risiko interner Bedrohungen zu erkennen.

Zum Erstellen Ihrer Nutzlast steht ein Rich-Text-Editor zur Verfügung. Sie können auch eine E-Mail importieren, die Sie zuvor erstellt haben. Wenn Sie den Textkörper der E-Mail erstellen, nutzen Sie die **dynamischen Tags,** um die E-Mail an Ihre Ziele zu personalisieren. Klicken Sie auf den **Phishing-Link,** um die zuvor ausgewählte Phishing-URL zum Nachrichtentext hinzuzufügen.

![Phishing-Link und dynamische Tags, die in der Nutzlasterstellung für Microsoft Defender für Office 365 hervorgehoben sind](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Um Zeit zu sparen, aktivieren Sie die Option, **alle Links in der E-Mail-Nachricht durch den Phishinglink** zu ersetzen.

Nachdem Sie die Nutzlast nach Ihren Wünschen erstellt haben, klicken Sie auf **"Weiter".**

## <a name="adding-indicators"></a>Hinzufügen von Indikatoren

Indikatoren helfen Mitarbeitern, die die Angriffssimulation durchlaufen, die Hinweise zu verstehen, nach denen sie bei zukünftigen Angriffen suchen können. Klicken Sie zunächst auf **"Indikator hinzufügen".**

Wählen Sie in der Dropdownliste einen Indikator aus, den Sie verwenden möchten. Diese Liste wird so zusammengestellt, dass sie die häufigsten Hinweise enthält, die in Phishing-E-Mail-Nachrichten angezeigt werden. Stellen Sie nach der Auswahl sicher, dass die Platzierung des Indikators auf **"Vom Textkörper" der E-Mail** festgelegt ist, und klicken Sie auf **"Text auswählen".** Markieren Sie den Teil Ihrer Nutzlast, in dem dieser Indikator angezeigt wird, und klicken Sie auf **"Auswählen".**

![Hervorgehobener Text im Nachrichtentext, der einem Indikator im Angriffssimulationstraining hinzugefügt werden soll](../../media/attack-sim-preview-select-text.png)

Fügen Sie eine benutzerdefinierte Beschreibung hinzu, um den Indikator zu beschreiben, und klicken Sie auf den Vorschauframe des Indikators, um eine Vorschau des Indikators anzuzeigen. Klicken Sie anschließend auf **"Hinzufügen".** Wiederholen Sie diese Schritte, bis Sie alle Indikatoren in Ihrer Nutzlast abgedeckt haben.

## <a name="review-payload"></a>Überprüfen der Nutzlast

Sie haben die Erstellung Ihrer Nutzlast abgeschlossen. Jetzt ist es an der Zeit, die Details zu überprüfen und eine Vorschau Ihrer Nutzlast anzuzeigen. Die Vorschau enthält alle Indikatoren, die Sie erstellt haben. Sie können jeden Teil der Nutzlast in diesem Schritt bearbeiten. Sobald Sie zufrieden sind, können Sie Ihre Nutzlast **übermitteln.**

> [!IMPORTANT]
> Nutzlasten, die Sie erstellt haben, verfügen über **"Mandant"** als Quelle. Stellen Sie beim Auswählen von Nutzlasten sicher, dass Sie den **Mandanten** nicht herausfiltern.

## <a name="related-links"></a>Verwandte Links

[Erste Schritte mit dem Angriffssimulationstraining](attack-simulation-training-get-started.md)

[Erstellen einer Phishingangriffssimulation](attack-simulation-training.md)

[Gewinnen Sie Erkenntnisse durch Angriffssimulationsschulungen](attack-simulation-training-insights.md)
