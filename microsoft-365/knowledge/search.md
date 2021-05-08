---
title: Verwenden der Microsoft Search zum Suchen von Themen in Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Erfahren Sie, wie Sie in Microsoft Viva nach Themen suchen können.
ms.openlocfilehash: 15b42c9d3689a73c865be53bb29f298fcbf896bd
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281042"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Verwenden der Microsoft Search zum Suchen von Themen in Microsoft Viva Topics

Während Benutzer von "Viva Topics" Themen über Themenhighlights auf ihren SharePoint finden können, können sie sie auch über Microsoft Search finden. 

## <a name="topic-answer"></a>Themenantwort

Wenn Sie in Microsoft Search nach einem bestimmten Thema suchen (z. B. "Saturn"), wenn ein Thema vorhanden ist und gefunden wird, wird das Ergebnis im #A0 angezeigt.

Die Antwort des Themas wird angezeigt:
- Themenname
- Alternative Namen: Alternative Namen oder Akronyme für das Thema.
- Definition: Beschreibung des Themas, die von der KI bereitgestellt oder manuell von einer Person hinzugefügt wurde.
- Vorgeschlagen oder angeheftet: Personen, die von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden
- Vorgeschlagene oder angeheftete Ressourcen: Dateien, Seiten oder Websites, die entweder von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden. 

   ![Thema in der Suche](../media/knowledge-management/search-topic-answer.png) 

Die Themenseite kann auch dann in den Suchergebnissen angezeigt werden, wenn die Antwortkarte des Themas nicht angezeigt wird.

In den Suchergebnissen in Word und PowerPoint wird auch die Themaantwort angezeigt, wenn eine gefunden wird.


## <a name="acronyms"></a>Akronyme

In "Viva Topics" können Sie ein Thema manuell bearbeiten, um ein Akronym als alternativen <b>Namen zu verwenden.</b> Auf diese Weise kann ein Benutzer, der nur nach dem Akronym des Themas sucht, die Themaantwort über Microsoft Search finden.

[Akronym Answers](/microsoftsearch/manage-acronyms) ist ein Feature, das über Microsoft Search bereitgestellt wird und separat von "Viva Topics" verwaltet wird.

## <a name="bookmarks-and-topics"></a>Lesezeichen und Themen

Lesezeichen sind ein Microsoft Search-Feature, das Personen dabei hilft, wichtige Websites und Tools schnell mit nur einer Suche zu finden (z. B. ein [Reisebuchungstool](/microsoftsearch/manage-bookmarks) auf einer externen Website außerhalb des Microsoft 365 Mandanten). Sie werden von Suchadministratoren im Microsoft 365 erstellt. 

Für Benutzer, die nach Informationen zum Buchen einer Arbeitsreise suchen:

- Wenn einige Benutzer den Namen des Reisetools kennen (z. B. "Concur"), ist es einfacher, ein Lesezeichen zu erstellen, um direkt zur externen Website zu wechseln.
- Erstellen Sie für Benutzer, die im Allgemeinen nach "Reisen" suchen, ein Thema unter "Reisen", das die informationen enthält, die sie erwarten. Erwägen Sie, einen Link zur externen Website Concur in der Beschreibung des Themas zu hinzufügen. Wenn der Link stattdessen zu einer internen Reisebuchungswebsite verwendet wird, die im Microsoft 365 gehostet wird, können Sie ihn den "angehefteten Ressourcen" hinzufügen.
 
### <a name="search-results-priority"></a>Priorität der Suchergebnisse 
 
Wenn ein Benutzer in der Benutzersuche nach einem Begriff wie "Reisen" sucht, werden suchergebnisse in der folgenden Priorität in Microsoft Search angezeigt.
1. Veröffentlichte oder bestätigte Themen 
2. Lesezeichen
3. Vorgeschlagene Themen
