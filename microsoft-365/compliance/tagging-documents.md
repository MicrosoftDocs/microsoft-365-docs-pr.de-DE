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
description: Das Markieren von Dokumenten in einem Überprüfungssatz hilft, unnötige Inhalte zu entfernen und relevante Inhalte in einem Advanced eDiscovery identifizieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285281"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Markieren von Dokumenten in einem Überprüfungssatz in Advanced eDiscovery

Das Organisieren von Inhalten in einem Überprüfungssatz ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abschließen zu können. Dies umfasst Folgendes:

- Culling unnecessary content

- Identifizieren relevanter Inhalte
 
- Identifizieren von Inhalten, die von einem Experten oder einem Anwalt überprüft werden müssen

Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Bewertungssatz überprüfen, können ihre Ansichten zu den Inhalten mithilfe von Tags erfasst werden. Wenn beispielsweise die Absicht besteht, nicht benötigte Inhalte zu markieren, kann ein Benutzer Dokumente mit einem Tag markieren, z. B. "nicht reaktionsfähig". Nachdem Inhalte überprüft und markiert wurden, kann eine Überprüfungssatzsuche erstellt werden, um alle Inhalte auszuschließen, die als "nicht reaktionsfähig" gekennzeichnet sind, wodurch dieser Inhalt aus den nächsten Schritten im eDiscovery-Workflow entfernt wird. Der Tagbereich kann für jeden Fall angepasst werden, damit die Tags den beabsichtigten Überprüfungsworkflow unterstützen können.

## <a name="tag-types"></a>Tagtypen

Advanced eDiscovery bietet zwei Arten von Tags:

- **Tags mit einer einzelnen** Auswahl – Schränkt Benutzer ein, ein einzelnes Tag innerhalb einer Gruppe auszuwählen. Dies kann hilfreich sein, um sicherzustellen, dass Benutzer keine in Konflikt enden Tags auswählen, z. B. "reaktionsfähig" und "nicht reaktionsfähig". Diese werden als Optionsfelder angezeigt.

- **Tags mit mehreren** Auswahlmöglichkeiten : Benutzern die Auswahl mehrerer Tags innerhalb einer Gruppe ermöglichen. Diese werden als Kontrollkästchen angezeigt.

## <a name="tag-structure"></a>Tagstruktur

Zusätzlich zu den Tagtypen kann die Struktur der Tags im Tagbereich verwendet werden, um das Tagging von Dokumenten intuitiver zu gestalten. Tags werden nach Abschnitten unterteilt. Die Überprüfungssatzsuche unterstützt die Möglichkeit, nach Tag und Nach-Tag-Abschnitt zu suchen. Dies bedeutet, dass Sie eine Überprüfungssatzsuche erstellen können, um Dokumente abzurufen, die mit einem beliebigen Tag in einem Abschnitt markiert sind.

![Markierungsabschnitte im Tagbereich](../media/Tagtypes.png)

Tags können weiter organisiert werden, indem sie in einem Abschnitt geschachtelt werden. Wenn beispielsweise die Absicht besteht, privilegierte Inhalte zu identifizieren und zu kennzeichnen, kann mit der Verschachtelung klar gemacht werden, dass ein Benutzer ein Dokument als "Privileged" kennzeichnen und den Berechtigungstyp auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.

![Geschachtelte Tags in einem Tag-Abschnitt](../media/Nestingtags.png)

## <a name="applying-tags"></a>Anwenden von Tags

Es gibt mehrere Möglichkeiten, ein Tag auf Inhalte anzuwenden.

### <a name="tagging-a-single-document"></a>Taggen eines einzelnen Dokuments

Wenn Sie ein Dokument in einem Überprüfungssatz anzeigen, können Sie die Tags anzeigen, die eine Überprüfung verwenden kann, indem Sie auf **Tagging-Bereich klicken.**

![Klicken Sie auf Tag-Bereich, um den Tagbereich anzeigen zu können.](../media/Singledoctag.png)

Auf diese Weise können Sie Tags auf das im Viewer angezeigte Dokument anwenden.

### <a name="bulk-tagging"></a>Massentagging

Massentagging kann durch Auswählen mehrerer Dateien im Ergebnisraster und anschließendes Verwenden der Tags im **Tagging-Bereich** wie das Markieren einzelner Dokumente durchgeführt werden. Das Massenentfing kann durch zweimalige Auswahl von Tags durchgeführt werden. Der erste Klick wird das Tag anwenden, und die zweite Auswahl stellt sicher, dass das Tag für alle ausgewählten Dateien gelöscht wird.

![Screenshot eines automatisch generierten Mobiltelefons Beschreibung](../media/Bulktag.png)

> [!NOTE]
> Beim Massentaging zeigt der Taggingbereich eine Anzahl von Dateien an, die für jedes Tag im Bereich markiert sind.

### <a name="tagging-in-other-review-panels"></a>Tagging in anderen Überprüfungspanels

Beim Überprüfen von Dokumenten können Sie die anderen Überprüfungspanels verwenden, um andere Merkmale von Dokumenten im Ergebnisraster zu überprüfen. Dies umfasst das Überprüfen anderer verwandter Dokumente, E-Mail-Threads, beinahe doppelter Objekte und Hashduplizierter. Wenn Sie z. B. verwandte Dokumente  überprüfen (mithilfe des Überprüfungspanels für die Dokumentfamilie), können Sie die Überprüfungszeit erheblich reduzieren, indem Sie verwandte Dokumente in Massen taggen. Wenn beispielsweise eine E-Mail-Nachricht mehrere Anlagen enthält und Sie sicherstellen möchten, dass die gesamte Familie konsistent markiert ist.

Hier erfahren Sie beispielsweise, wie Sie den **Tagging-Bereich** anzeigen, wenn Sie den Überprüfungsbereich für die **Dokumentfamilie** verwenden:

1. Wenn der Überprüfungsbereich für ein ausgewähltes Dokument geöffnet ist (z. B. wenn die Liste der zugehörigen Inhalte im Überprüfungsfenster Dokumentfamilie angezeigt wird, klicken Sie im Überprüfungsbereich Dokumentfamilie auf **Dokumente** markieren. 

   Der Taggingbereich wird als Popupfenster angezeigt.

2. Wählen Sie ein oder mehrere Tags aus, um das ausgewählte Dokument anzuwenden. 

3. Um alle Dokumente zu kennzeichnen,  wählen Sie alle Dokumente im Bereich Dokumentfamilie aus, klicken Sie auf **Dokumente markieren,** und wählen Sie dann die Tags aus, die auf die gesamte Dokumentfamilie angewendet werden.

![Screenshot eines automatisch generierten Social Media-Beitrags Beschreibung](../media/Relatedtag.png)
