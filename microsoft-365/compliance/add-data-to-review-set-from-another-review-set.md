---
title: Hinzufügen von Daten aus einem Überprüfungssatz zu einem anderen Überprüfungssatz
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
description: Erfahren Sie, wie Sie Dokumente aus einem Überprüfungssatz auswählen und in einem anderen Satz in einem anderen Fall einzeln Advanced eDiscovery können.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285179"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Hinzufügen von Daten aus einem Prüfdateisatz zu einem anderen Prüfdateisatz

In einigen Fällen kann es erforderlich sein, Dokumente aus einem Überprüfungssatz auszuwählen und einzeln in einem anderen Überprüfungssatz zu arbeiten. Dies ist besonders hilfreich, wenn Sie Inhalte in einem Prüfdateisatz gefiltert haben und Analysen für die Teilmenge der Daten ausführen möchten.

Folgen Sie dem Workflow in diesem Artikel, um Inhalte aus einem Überprüfungssatz zu einem anderen hinzuzufügen.

## <a name="create-a-review-set"></a>Erstellen eines Überprüfungssatz

Bevor Sie beginnen, müssen Sie einen Überprüfungssatz erstellen, um die Daten hinzuzufügen.  Ein neuer Überprüfungssatz kann auf der Registerkarte **Überprüfungssätze** des Falls hinzugefügt werden. Weitere Informationen finden Sie unter [Create a review set](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Schritt 1: Identifizieren von Inhalten, die einem anderen Überprüfungssatz hinzugefügt werden sollen

Sie können Inhalte aus einem Prüfdateisatz zu einem anderen Prüfdateisatz hinzufügen, indem Sie bestimmte Dokumente im ursprünglichen Prüfdateisatz oder alle von der Prüfdateisatzabfrage zurückgegeben Elemente auswählen. Wenn Sie ausgewählte Elemente hinzufügen, wählen Sie die Elemente aus, wählen Sie **Aktion** aus, und wählen Sie dann Hinzufügen zu einem anderen **Überprüfungssatz aus.**

![Hinzufügen zu einem anderen Überprüfungssatz im Menü Aktion](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Schritt 2: Angeben von Optionen zum Hinzufügen zu einem anderen Überprüfungssatz

Wählen Sie auf der Flyoutseite Add **to another review set options** den Überprüfungssatz aus, dem Sie die Elemente hinzufügen möchten. Wählen Sie aus, ob **Alle Suchergebnisse oder ausgewählte** Elemente hinzugefügt werden **sollen.**  **Zusätzliche Informationen** bieten Optionen zum Hinzufügen aller Metadaten aus den Elementen  und zum Hinzufügen der Tags (durch Aktivieren des Kontrollkästchens Bezeichnungen) aus dem Quellüberprüfungssatz, wenn die Dokumente dem neuen Prüfsatz hinzugefügt werden.  

![Optionen zum Hinzufügen von Daten zu einem anderen Überprüfungssatz](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Nachdem Sie auf **Ok** geklickt haben, wird ein neuer Auftrag mit dem Namen **Hinzufügen** von Daten zu einem anderen Überprüfungssatz erstellt, um den Inhalt einem anderen Überprüfungssatz hinzuzufügen. Sie können zur Registerkarte **Aufträge wechseln** und den Fortschritt dieses Auftrags überwachen. Weitere Informationen finden Sie unter [Manage jobs](managing-jobs-ediscovery20.md).
