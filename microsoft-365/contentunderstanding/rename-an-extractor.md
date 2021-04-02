---
title: Extraktor in Microsoft SharePoint Syntex umbenennen
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
description: Erfahren Sie, wie und warum Sie einen Extraktor in Microsoft SharePoint Syntex umbenennen.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445996"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Extraktor in Microsoft SharePoint Syntex umbenennen

Irgendwann müssen Sie möglicherweise einen Extraktor umbenennen, wenn Sie auf ein extrahiertes Datenfeld mit einem anderen Namen verweisen möchten. Beispielsweise beschließt Ihre Organisation, Änderungen an ihren Vertragsdokumenten vorzunehmen, und bezeichnet "Käufer" in ihren Dokumenten als "Kunden". Wenn Sie in Ihrem Modell ein Feld "Käufer" extrahiert haben, können Sie es in "Kunde" umbenennen.

Wenn Sie Ihr aktualisiertes Modell mit Ihrer SharePoint-Dokumentbibliothek synchronisieren, wird in Ihrer Dokumentbibliotheksansicht eine neue Spalte "Kunde" angezeigt. In Ihrer Ansicht wird die Spalte "Käufer" für frühere Aktivitäten beibehalten, die neue Spalte "Kunde" wird jedoch für alle neuen Dokumente aktualisiert, die von Ihrem Modell verarbeitet werden. 

> [!IMPORTANT]
>  Stellen Sie sicher, dass Sie Ihr aktualisiertes Modell mit den Dokumentbibliotheken synchronisieren, in denen Sie es zuvor angewendet haben, damit der neue Spaltenname angezeigt wird. 

## <a name="rename-an-extractor"></a>Umbenennen eines Extraktors

Führen Sie die folgenden Schritte aus, um einen Entitätsextraktor umzubenennen.

1. Wählen Sie im Inhaltscenter **Modelle** aus, um die Liste ihrer Modelle anzuzeigen.

2. Wählen Sie auf der Seite **Modelle** in der Spalte **Name** das Modell aus, für das Sie einen Extraktor umbenennen möchten.

3. Wählen Sie unter **Entitätsextraktoren** den Namen des Extraktors aus, den Sie umbenennen möchten, und wählen Sie dann **Umbenennen** aus.</br>

    ![Screenshot des Abschnitts "Entitätsextraktoren" mit einem ausgewählten Extraktor mit hervorgehobener Option "Umbenennen".](../media/content-understanding/entity-extractor-rename.png) </br>

4. Im Bereich **Entitätsextraktor umbenennen**:

   a. Geben Sie unter **Neuer Name** den neuen Namen des Extraktors ein.</br>

    ![Screenshot mit dem Entitätsextraktions-Bedienfeld.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (Optional) Wählen Sie unter **Erweiterte Einstellungen**, ob Sie eine vorhandene Sitespalte zuordnen möchten.

5. Wählen Sie **Umbenennen** aus.

## <a name="see-also"></a>Siehe auch
[Erstellen eines Extraktors](create-an-extractor.md)

[Erstellen einer Klassifizierung](create-a-classifier.md)

[Ein Modell umbenennen](rename-a-model.md)

[Beschreibungstypen](explanation-types-overview.md)

[Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors](leverage-term-store-taxonomy.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Anwenden eines Modells](apply-a-model.md) 
