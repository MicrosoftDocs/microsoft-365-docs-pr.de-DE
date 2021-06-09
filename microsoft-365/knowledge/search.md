---
title: Verwenden von Microsoft Search zum Suchen von Themen in Microsoft Viva Topics
ms.author: chuckedmonson
author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Erfahren Sie, wie Sie in Microsoft Viva nach Themen suchen können.
ms.openlocfilehash: bce9309d27b76854b927922f39389c18e1c09449
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844731"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Verwenden von Microsoft Search zum Suchen von Themen in Microsoft Viva Topics

Während Viva Topics-Benutzer Themen über Themenhighlights in ihren SharePoint-Websites finden, können sie sie auch über Microsoft Search finden. 

## <a name="topic-answer"></a>Themenantwort

Wenn Sie in Microsoft Search nach einem bestimmten Thema (z. B. "Saturn") suchen, wenn ein Thema vorhanden ist und gefunden wird, wird das Ergebnis im Vorschlagsformat für die Themenantwort angezeigt.

In der Themenantwort wird Folgendes angezeigt:
- Themenname
- Alternative Namen: Alternative Namen oder Akronyme für das Thema.
- Definition: Beschreibung des Themas, die von der KI bereitgestellt oder manuell von einer Person hinzugefügt wurde.
- Vorgeschlagene oder angeheftete Personen: Personen, die von KI vorgeschlagen oder von einer Person an das Thema angeheftet wurden
- Vorgeschlagene oder angeheftete Ressourcen: Dateien, Seiten oder Websites, die entweder von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden. 

   ![Thema in der Suche](../media/knowledge-management/search-topic-answer.png) 

Die Themenseite kann in den Suchergebnissen auch dann angezeigt werden, wenn die Themenantwortkarte nicht angezeigt wird.

In den Suchergebnissen in Word, PowerPoint, Outlook und Excel wird auch die Themenantwort angezeigt, wenn eine gefunden wird.


## <a name="acronyms"></a>Akronyme

In Viva Topics können Sie ein Thema manuell bearbeiten, um ein Akronym für es als <b>alternativen Namen</b>einzuschließen. Dadurch kann ein Benutzer, der nur mit dem Akronym des Themas sucht, die Themenantwort über Microsoft Search finden.

[Akronyme Antworten](/microsoftsearch/manage-acronyms) ist ein Feature, das über Microsoft Search bereitgestellt wird und separat von Viva Topics verwaltet wird.

## <a name="bookmarks-and-topics"></a>Lesezeichen und Themen

[Lesezeichen](/microsoftsearch/manage-bookmarks) sind ein Microsoft Search-Feature, mit dem Benutzer wichtige Websites und Tools schnell mit nur einer Suche finden können (z. B. ein Reisebuchungstool auf einer externen Website außerhalb ihres Microsoft 365 Mandanten). Sie werden von Suchadministratoren im Microsoft 365 Admin Center erstellt. 

Für Benutzer, die Informationen zum Buchen einer Reise für die Arbeit suchen:

- Wenn einige Benutzer den Namen des Reisetools (z. B. "Concur") kennen, ist es einfacher, ein Lesezeichen zu erstellen, um direkt zur externen Website zu wechseln.
- Für Benutzer, die im Allgemeinen nach "Reisen" suchen, erstellen Sie ein Thema zu "Reisen", das die informationen enthält, die sie erwarten. Erwägen Sie das Hinzufügen eines Links zur externen Parallel-Website in der Beschreibung des Themas. Wenn sich der Link stattdessen zu einer internen Reisebuchungswebsite befindet, die auf dem Microsoft 365 Mandanten gehostet wird, können Sie ihn den "angehefteten Ressourcen" hinzufügen.
 
### <a name="search-results-priority"></a>Priorität der Suchergebnisse 

Wenn ein Benutzer in der Suchumgebung nach einem Begriff wie "Reise" sucht, wird anstelle eines Themas ein Lesezeichen angezeigt, wenn ein Lesezeichen verfügbar ist.
