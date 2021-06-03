---
title: Markieren von Dokumenten in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Das Markieren von Dokumenten in einem Prüfdateisatz trägt dazu bei, unnötige Inhalte zu entfernen und relevante Inhalte in einem Advanced eDiscovery Fall zu identifizieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736274"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Markieren von Dokumenten in einem Prüfdateisatz in Advanced eDiscovery

Das Organisieren von Inhalten in einem Prüfdateisatz ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abzuschließen. Dies umfasst Folgendes:

- Culling von unnötigen Inhalten

- Identifizieren relevanter Inhalte

- Identifizieren von Inhalten, die von einem Experten oder Anwalt überprüft werden müssen

Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Prüfdateisatz überprüfen, können ihre Ansichten zu den Inhalten mithilfe von Tags erfasst werden. Wenn z. B. der Zweck darin besteht, unnötige Inhalte zu entfernen, kann ein Benutzer Dokumente mit einem Tag wie z. B. "nicht reaktionsfähig" markieren. Nachdem Inhalte überprüft und markiert wurden, kann eine Prüfdateisatzsuche erstellt werden, um alle Inhalte auszuschließen, die als "nicht reaktionsfähig" gekennzeichnet sind. Dadurch werden die nicht reaktionsfähigen Inhalte aus den nächsten Schritten im eDiscovery-Workflow entfernt. Der Tagging-Bereich in einem Prüfdateisatz kann für jeden Fall angepasst werden, sodass die Tags den beabsichtigten Überprüfungsworkflow für den Fall unterstützen.

> [!NOTE]
> Der Bereich von Tags ist ein Advanced eDiscovery Fall. Das bedeutet, dass ein Fall nur einen Satz von Tags enthalten kann, die Prüfer zum Markieren von Dokumenten mit Prüfdateisatz verwenden können. Sie können keinen anderen Satz von Tags für die Verwendung in verschiedenen Prüfdateisätzen im selben Fall einrichten.

## <a name="tag-types"></a>Tagtypen

Advanced eDiscovery bietet zwei Arten von Tags:

- **Single Choice Tags:** Beschränkt Prüfer auf die Auswahl eines einzelnen Tags innerhalb einer Gruppe. Diese Arten von Tags können nützlich sein, um sicherzustellen, dass Prüfer keine widersprüchlichen Tags wie "reaktionsfähig" und "nicht reaktionsfähig" auswählen. Einzelne Auswahltags werden als Optionsfelder angezeigt.

- **Multiple Choice-Tags:** Rezensionen erlauben, mehrere Tags innerhalb einer Gruppe auszuwählen. Diese Arten von Tags werden als Kontrollkästchen angezeigt.

## <a name="tag-structure"></a>Tag-Struktur

Zusätzlich zu den Tagtypen kann die Struktur der Organisation von Tags im Tag-Bereich verwendet werden, um das Tagging von Dokumenten intuitiver zu gestalten. Tags sind nach Abschnitten gruppiert. Die Suche nach Prüfdateisatz unterstützt die Möglichkeit, nach Tag und Nach-Tag-Abschnitt zu suchen. Dies bedeutet, dass Sie eine Prüfdateisatzsuche erstellen können, um Dokumente abzurufen, die mit einem beliebigen Tag in einem Abschnitt markiert sind.

![Tag-Abschnitte im Tag-Bereich](../media/TagTypes.png)

Sie können Tags weiter organisieren, indem Sie sie in einem Abschnitt verschachteln. Wenn beispielsweise privilegierte Inhalte identifiziert und markiert werden sollen, kann die Schachtelung verwendet werden, um deutlich zu machen, dass ein Bearbeiter ein Dokument als "Privileged" markieren und den Typ der Berechtigung auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.

![Geschachtelte Tags in einem Tag-Abschnitt](../media/NestingTags.png)

## <a name="create-tags"></a>Erstellen von Tags

Bevor Sie Tags auf Dokumente im Prüfdateisatz anwenden, müssen Sie eine Tagstruktur erstellen.

1. Öffnen Sie einen Prüfdateisatz, navigieren Sie zur Befehlsleiste, und wählen Sie **Tag nach Abfrage** aus.

2. Wählen Sie im Bereich "Tagging" die Option **"Tag verwalten" aus.**

3. Wählen Sie **"Tag hinzufügen" aus.**

4. Geben Sie einen Taggruppentitel und eine optionale Beschreibung ein, und klicken Sie dann auf **"Speichern".**

5. Wählen Sie das Dropdownmenü mit drei Punkten neben dem Taggruppentitel aus, und klicken Sie auf das **Kontrollkästchen "Hinzufügen"** oder **auf die Schaltfläche "Option hinzufügen".**

6. Geben Sie einen Namen und eine Beschreibung für das Kontrollkästchen oder die Optionsschaltfläche ein.

7. Wiederholen Sie diesen Vorgang, um neue Tagabschnitte, Tagoptionen und Kontrollkästchen zu erstellen.

   ![Konfigurieren der Tagstruktur](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a>Anwenden von Tags

Wenn die Tagstruktur vorhanden ist, können Prüfer Tags auf Dokumente in einem Prüfdateisatz anwenden. Es gibt zwei verschiedene Möglichkeiten zum Anwenden von Tags:

- Tag-Dateien

- Tag nach Abfrage

### <a name="tag-files"></a>Tag-Dateien

Unabhängig davon, ob Sie ein einzelnes Element oder mehrere Elemente in einem Prüfdateisatz auswählen, können Sie Tags auf ihre Auswahl anwenden, indem Sie auf der Befehlsleiste auf **"Tag"-Dateien** klicken. Im Tagging-Bereich können Sie ein Tag auswählen, das automatisch auf die ausgewählten Dokumente angewendet wird.

![Markieren ausgewählter Dateien](../media/TagFile2.png)

> [!NOTE]
> Tags werden nur auf ausgewählte Elemente in der Liste der Elemente angewendet.

### <a name="tag-by-query"></a>Tag nach Abfrage

Mit tagging by query können Sie Tags auf alle Elemente anwenden, die von einer Filterabfrage angezeigt werden, die derzeit im Prüfdateisatz angewendet wird.

1. Heben Sie die Auswahl aller Elemente im Prüfdateisatz auf, wechseln Sie zur Befehlsleiste, und wählen Sie **Tag nach Abfrage** aus.

2. Wählen Sie im Tagging-Bereich das Tag aus, das Sie anwenden möchten.

3. Unter der Dropdownliste **"Tagauswahl"** gibt es drei Optionen, die festlegen, auf welche Elemente das Tag angewendet werden soll.

   - **Elemente, die mit der angewendeten Abfrage übereinstimmen:** Wendet Tags auf bestimmte Elemente an, die den Filterabfragebedingungen entsprechen.

   - **Zugeordnete Familienelemente einschließen:** Wendet Tags auf bestimmte Elemente an, die den Filterabfragebedingungen und den zugehörigen Familienelementen entsprechen. *Familienelemente* sind Elemente, die denselben FamilyId-Metadatenwert verwenden.  

   - **Zugeordnete Unterhaltungselemente einschließen:** Wendet Tags auf Elemente an, die den Filterabfragebedingungen und den zugehörigen Unterhaltungselementen entsprechen. *Unterhaltungselemente* sind Elemente, die dieselben ConversationId-Metadatenwerte verwenden.

   ![Tagauswahl](../media/TagByQuery2.png)

4. Klicken Sie auf **"Taggingauftrag starten",** um den Taggingauftrag auszulösen.

## <a name="tag-filter"></a>Tagfilter

Verwenden Sie den Tagfilter im Prüfdateisatz, um Elemente basierend auf der Markierung eines Elements schnell zu finden oder aus den Abfrageergebnissen auszuschließen. 

1. Wählen Sie **Filter** aus, um den Filterbereich zu erweitern.

2. Auswählen und Erweitern **von Elementeigenschaften.**

3. Scrollen Sie nach unten, um den Filter **"Tag"** zu suchen, aktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **"Fertig".**

4. Führen Sie einen der folgenden Schritte aus, um Elemente mit einem bestimmten Tag in eine Abfrage einzuschließen oder auszuschließen:

   - **Elemente einschließen:** Wählen Sie den Tagwert aus, und wählen Sie im Dropdownmenü **"Gleich"** aus.

      Oder

   - **Elemente ausschließen:** Wählen Sie den Tagwert aus, und wählen Sie **"Gleich" im** Dropdownmenü aus.

     ![Ausschließen von Elementen durch Tagfilter](../media/TagFilterExclude.png)

> [!NOTE]
> Aktualisieren Sie die Seite unbedingt, um sicherzustellen, dass der Tagfilter die neuesten Änderungen an der Tagstruktur anzeigt.
