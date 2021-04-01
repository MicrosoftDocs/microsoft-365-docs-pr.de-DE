---
title: Duplizieren eines Modells in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Erfahren Sie, wie und warum Sie ein Modell in Microsoft SharePoint Syntex duplizieren können.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446035"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Duplizieren eines Modells in Microsoft SharePoint Syntex

Das Duplizieren eines Dokumentverständnismodells kann Ihnen Zeit und Mühe ersparen, wenn Sie ein neues Modell erstellen müssen und wissen, dass ein vorhandenes Modell dem, was Sie benötigen, sehr ähnlich ist.

Ein vorhandenes Modell mit dem Namen „Verträge“ klassifiziert zum Beispiel die gleichen Dateien, mit denen Sie arbeiten müssen. Ihr neues Modell wird einige der vorhandenen Daten extrahieren, muss aber aktualisiert werden, um einige zusätzliche Daten zu extrahieren. Anstatt ein neues Modell von Grund auf zu erstellen und zu trainieren, können Sie die Funktion „Modell duplizieren“ verwenden, um eine Kopie des Vertragsmodells zu erstellen, die auch alle zugehörigen Schulungselemente wie Beispieldateien und Entitätsextraktionsfunktionen kopiert.

Wenn Sie das Modell duplizieren, können Sie, nachdem Sie es umbenannt haben (z. B. in „Vertragsverlängerungen“), Aktualisierungen daran vornehmen. Sie können z. B. einige der vorhandenen extrahierten Felder entfernen, die Sie nicht benötigen, und dann das Modell trainieren, um ein neues zu extrahieren (z. B. „Verlängerungsdatum“).

## <a name="duplicate-a-model"></a>Ein Modell duplizieren

Führen Sie die folgenden Schritte aus, um ein Document Understanding Model zu duplizieren.

1. Wählen Sie im Inhaltscenter **Modelle** aus, um die Liste ihrer Modelle anzuzeigen.

2. Wählen Sie auf der Seite **Modelle** das Modell aus, das Sie duplizieren möchten.

3. Wählen Sie entweder über das Menüband oder über die Schaltfläche **Aktionen anzeigen** (neben dem Modellnamen) die Option **Duplizieren**.</br>

    ![Screenshot der Seite „Modelle“ mit einem ausgewählten Modell, bei dem die Optionen „Duplizieren“ hervorgehoben sind.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. Im Bedienfeld **Modell duplizieren**:

   a. Geben Sie unter **Name** den neuen Namen des Modells ein, das Sie duplizieren möchten.</br>

    ![Screenshot, der das Bedienfeld "Modell duplizieren" zeigt.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. Fügen Sie unter **Beschreibung** eine Beschreibung Ihres neuen Modells hinzu.

   c. (Optional) Wählen Sie unter **Erweiterte Einstellungen**, ob Sie einen vorhandenen [Inhaltstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) zuordnen möchten.

5. Wählen Sie **Duplizieren**.

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Ein Modell umbenennen](rename-a-model.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Beschreibungstypen](explanation-types-overview.md)

[Anwenden eines Modells](apply-a-model.md) 

[Barrierefreiheitsmodus für SharePoint Syntex](accessibility-mode.md)