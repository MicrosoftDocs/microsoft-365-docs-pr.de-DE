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
ms.openlocfilehash: 1739923c95b42f192bb2e285245f72c3e09e1c30
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925928"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Verwenden der Microsoft Search zum Suchen von Themen in Microsoft Viva Topics

Während Benutzer von "Viva Topics" Themen über Themenhighlights auf ihren SharePoint-Websites finden können, können sie sie auch über Microsoft Search finden. 

## <a name="topic-answer"></a>Themenantwort

Wenn Sie in Microsoft Search nach einem bestimmten Thema suchen (z. B. "Saturn"), wenn ein Thema vorhanden ist und gefunden wird, wird das Ergebnis im #A0 angezeigt.

Die Antwort des Themas wird angezeigt:
- Themaname
- Alternative Namen: Alternative Namen oder Akronyme für das Thema.
- Definition: Beschreibung des Themas, das von AI bereitgestellt oder manuell von einer Person hinzugefügt wurde.
- Vorgeschlagen oder angeheftet: Personen, die von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden
- Vorgeschlagene oder angeheftete Ressourcen: Dateien, Seiten oder Websites, die entweder von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden. 

   ![Thema in der Suche](../media/knowledge-management/search-topic-answer.png) 

Die Themenseite kann auch dann in den Suchergebnissen angezeigt werden, wenn die Antwortkarte des Themas nicht angezeigt wird.


## <a name="acronyms"></a>Akronyme

In "Viva Topics" können Sie ein Thema manuell bearbeiten, um ein Akronym als alternativen <b>Namen zu verwenden.</b> Auf diese Weise kann ein Benutzer, der nur nach dem Akronym des Themas sucht, die Themaantwort über Microsoft Search finden.

[Akronym Answers](/microsoftsearch/manage-acronyms) ist ein Feature, das über Microsoft Search bereitgestellt wird und separat von "Viva Topics" verwaltet wird.

## <a name="bookmarks-and-topics"></a>Lesezeichen und Themen

Lesezeichen sind ein Microsoft Search-Feature, das Personen dabei hilft, wichtige Websites und Tools schnell mit nur einer Suche zu finden (z. B. ein [Reisebuchungstool](/microsoftsearch/manage-bookmarks) auf einer externen Website außerhalb ihres Microsoft 365-Mandanten). Sie werden von Suchadministratoren im Microsoft 365 Admin Center erstellt. 

Für Benutzer, die nach Informationen zum Buchen einer Arbeitsreise suchen:

- Wenn einige Benutzer den Namen des Reisetools kennen (z. B. "Concur"), ist es einfacher, ein Lesezeichen zu erstellen, um direkt zur externen Website zu wechseln.
- Erstellen Sie für Benutzer, die im Allgemeinen nach "Reisen" suchen, ein Thema unter "Reisen", das die informationen enthält, die sie erwarten. Erwägen Sie, einen Link zur externen Website Concur in der Beschreibung des Themas zu hinzufügen. Wenn der Link stattdessen zu einer internen Reisebuchungswebsite verwendet wird, die auf dem Microsoft 365-Mandanten gehostet wird, können Sie ihn den "angehefteten Ressourcen" hinzufügen.
 
### <a name="search-results-priority"></a>Priorität der Suchergebnisse 
 
Wenn ein Benutzer in der Benutzersuche nach einem Begriff wie "Reisen" sucht, werden suchergebnisse in der folgenden Priorität in Microsoft Search angezeigt.
1. Veröffentlichte oder bestätigte Themen 
2. Lesezeichen
3. Vorgeschlagene Themen