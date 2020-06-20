---
title: Hinzufügen von Daten aus einem Überprüfungs Sätze zu einem anderen Überprüfungs Satzes
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Hier erfahren Sie, wie Sie Dokumente aus einer Überprüfungsgruppe auswählen und mit diesen einzeln in einer anderen Gruppe in einem erweiterten eDiscovery-Fall arbeiten.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 433e59629ec40dbdf66b8daf6437ce84e41a3a33
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818602"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Hinzufügen von Daten zu einem Überprüfungs Satzes aus einer anderen Überprüfungsgruppe

In einigen Fällen kann es erforderlich sein, Dokumente aus einer Überprüfungsgruppe auszuwählen und einzeln in einem anderen Überprüfungs Satzes zu bearbeiten. Dies ist besonders nützlich, wenn Sie Inhalte in einem Überprüfungs Satz ausgemerzt haben und Analysen für die Teilmenge der Daten ausführen möchten.

Führen Sie den Workflow in diesem Artikel aus, um Inhalte aus einem Überprüfungs Satz zu einem anderen zu hinzufügen.

## <a name="create-a-review-set"></a>Erstellen eines Überprüfungs Satzes

Bevor Sie beginnen, müssen Sie eine Überprüfungsgruppe erstellen, der die Daten hinzugefügt werden sollen.  Auf der Registerkarte **Überprüfungs Sätze** der Groß-/Kleinschreibung kann ein neuer Überprüfungs Satz hinzugefügt werden. Weitere Informationen finden Sie unter [Erstellen eines Überprüfungs Satzes](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Schritt 1: Identifizieren von Inhalten, die zu einem anderen Überprüfungs Sätze hinzugefügt werden

Sie können Inhalte aus einer Überprüfungsgruppe hinzufügen, indem Sie bestimmte Dokumente in der Quell Überprüfungsgruppe auswählen oder indem Sie alle Elemente auswählen, die von der Abfrage zur Überprüfungs Menge zurückgegeben werden. Wenn Sie ausgewählte Elemente hinzufügen, wählen Sie die Elemente aus, wählen Sie **Aktion**aus, und wählen Sie dann **zu einem anderen Überprüfungs Satzes hinzufügen**aus.

![Zu einem anderen Überprüfungs Satzes hinzufügen](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Schritt 2: Angeben von Optionen für das Hinzufügen zu einer anderen Überprüfungsgruppe

Wählen Sie auf der Flyout-Seite **Add to other Review Sets Options** die Überprüfungsgruppe aus, der Sie die Elemente hinzufügen möchten. Wählen Sie aus, ob **alle Suchergebnisse** oder **ausgewählten Elemente**hinzugefügt werden sollen.  **Zusätzliche Informationen** bieten Optionen zum Einschließen aller Metadaten aus den Elementen und zum Einschließen der Tags (durch Aktivieren des Kontrollkästchens **Beschriftungen** ) aus dem Quell Überprüfungs Satzes, wenn die Dokumente zum neuen Überprüfungs Sätzen hinzugefügt werden.  

![Zu einem anderen Überprüfungs Satzes hinzufügen](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Nachdem Sie auf **OK**geklickt haben, wird ein neuer Auftrag (mit dem Namen **Hinzufügen von Daten zu einem anderen Überprüfungs Sätze**) erstellt, um den Inhalt zu einem anderen Überprüfungs Satzes hinzuzufügen. Sie können auf die Registerkarte **Aufträge** wechseln und den Status dieses Auftrags überwachen. Weitere Informationen finden Sie unter [Manage Jobs](managing-jobs-ediscovery20.md).
