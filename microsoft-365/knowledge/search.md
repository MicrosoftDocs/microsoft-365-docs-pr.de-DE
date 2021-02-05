---
title: Verwenden von Microsoft Search zum Suchen nach Themen in Microsoft Themen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Hier erfahren Sie, wie Sie in Microsoft Abt nach Themen suchen können.
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108299"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Verwenden von Microsoft Search zum Suchen nach Themen in Microsoft Themen

Während Benutzer von "Themen" Themen über Themenhighlights auf ihren SharePoint-Websites finden, können sie sie auch über Microsoft Search finden. 

## <a name="topic-answer"></a>Themaantwort

Wenn Sie in Microsoft Search nach einem bestimmten Thema (z. B. "Saturn") suchen, wird das Ergebnis im #A0 angezeigt, wenn ein Thema vorhanden ist und gefunden wird.

Die Antwort auf das Thema wird angezeigt:
- Themaname
- Alternative Namen: Alternative Namen oder Akronyme für das Thema.
- Definition: Beschreibung des Themas, das von AI bereitgestellt oder manuell von einer Person hinzugefügt wurde.
- Vorgeschlagene oder angeheftierte Personen: Personen, die von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden
- Vorgeschlagene oder angeheftete Ressourcen: Dateien, Seiten oder Websites, die entweder von AI vorgeschlagen oder von einer Person an das Thema angeheftet wurden. 

   ![Thema in der Suche](../media/knowledge-management/search-topic-answer.png) 

Die Themenseite kann auch dann in den Suchergebnissen angezeigt werden, wenn die Antwortkarte des Themas nicht angezeigt wird.


## <a name="acronyms"></a>Akronyme

In Thema Topics, you can manually edit a topic to include an acronym for it as an <b>Alternate Name</b>. Dadurch kann ein Benutzer, der nur nach dem Akronym des Themas sucht, die Antwort des Themas über Microsoft Search finden.

[Das Akronym "Antworten"](https://docs.microsoft.com/microsoftsearch/manage-acronyms) ist ein Feature, das über Microsoft Search bereitgestellt wird und separat von Themen zu Themen verwaltet wird.

## <a name="bookmarks-and-topics"></a>Lesezeichen und Themen

Lesezeichen sind ein Microsoft Search-Feature, mit dem Benutzer wichtige Websites und Tools schnell mit nur einer Suche finden können (z. B. ein [Reisebuchungstool](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) auf einer externen Website außerhalb ihres Microsoft 365-Mandanten). Sie werden von Suchadministratoren im Microsoft 365 Admin Center erstellt. 

Für Benutzer, die Informationen zum Buchen einer Reise für die Arbeit suchen:

- Wenn einige Benutzer den Namen des Reisetools kennen (z. B. "Concur"), ist es einfacher, ein Lesezeichen zu erstellen, um direkt zur externen Website zu wechseln.
- Für Benutzer, die im Allgemeinen nach "Reisen" suchen, erstellen Sie ein Thema auf "Reisen", das die Informationen enthält, die sie erwarten. Erwägen Sie das Hinzufügen eines Links zur externen Website "Concur" in der Beschreibung des Themas. Wenn es sich bei dem Link stattdessen um eine interne Reisebuchungswebsite handelt, die auf dem Microsoft 365-Mandanten gehostet wird, können Sie ihn den "angeheftetEn Ressourcen" hinzufügen.
 
### <a name="search-results-priority"></a>Priorität der Suchergebnisse 
 
Wenn ein Benutzer in der Benutzersuche nach einem Begriff wie "Reisen" sucht, werden suchergebnisse in Microsoft Search in der folgenden Priorität angezeigt:
1. Veröffentlichte oder bestätigte Themen 
2. Lesezeichen
3. Vorgeschlagene Themen 



