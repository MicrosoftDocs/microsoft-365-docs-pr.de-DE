---
title: Microsoft Viva Topics Security Trimming
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Übersicht über die Verwendung von Sicherheit zum Anzeigen von Themen.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939623"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva Topics Security Trimming 

Benutzer von "Viva Topics" können keine Informationen in Themen anzeigen, die von ihren vorhandenen Office 365-Berechtigungen nicht angezeigt werden können. Alles, was ein Benutzer auf einer Themenseite sieht (z. B. SharePoint-Websites, Dokumente, Dateien), sind Informationen, die er bereits sehen darf. Bei "Viva Topics" werden keine Änderungen an vorhandenen Berechtigungen vorgenommen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben

Wenn ein Thema über KI oder manuelle Kuration erstellt wird, kann es eine Beschreibung des Themas, alternative Namen, Personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten. Wenn diese Informationen auf einer Themenseite angezeigt werden, kann es sein, dass zwei Benutzer, die dasselbe Thema anzeigen, die gleichen Informationen nicht sehen.
  
Wenn Benutzer 1 z. B. die Themenseite "Neptune" aufruft, wird möglicherweise diese Ansicht der Themenseite angezeigt.

![Thema "Neptun" für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wenn Benutzer 2 jedoch dieselbe Seite des Themas "Neptune" betrachtet, unterscheidet sich ihre Ansicht von Benutzer 1.  Benutzer 2 kann die *Dg-2000-Produktübersichtsdatei* im Abschnitt Angeheftet Dateien und Seiten der Themenseite anzeigen, die für Benutzer 1 nicht angezeigt wird.  

![Thema "2" für "2"](../media/knowledge-management/user1-topic-view.png) </br> 

Der Unterschied bei den Benutzern in demselben Thema liegt daran, dass Benutzer möglicherweise nicht über die Office 365-Berechtigungen zum Anzeigen einer verwandten Website oder Datei verfügen.  Viva Topics respektiert die Berechtigungen, die für Elemente in einem Thema festgelegt sind, und kann den Zugriff darauf nicht ändern. In unserem Beispiel kann Benutzer 1 die *DG-2000-Produktübersichtsdatei* nicht auf ihrer Themenseite für "Neptune" anzeigen, da Benutzer 1 nicht über Office 365-Berechtigungen zum Anzeigen der Datei verfügt.

Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema zu sehen, damit es nützlich ist, steht das Thema dem Benutzer nicht zur Verfügung. In diesem Fall wird dem Benutzer das hervorgehobene Thema nicht angezeigt. Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er nützlich ist, kann das Thema sehen.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Themenberechtigungen für Wissensmanager und Mitwirkende von Themen

Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, die sie in Themen anzeigen können.

Ebenso können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Mitwirkende – nur Informationen anzeigen, die sie in Themen anzeigen können. 


## <a name="ai-versus-manually-curated-topic-information"></a>Informationen zu AI und manuell kuratierten Themen

Themen können informationen enthalten, die durch KI generiert werden, und Informationen, die von Themenwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet werden.

 - Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf die Quellinhalte haben.
 - Themenbeschreibung und Personeninformationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für alle Personen sichtbar, die das Thema sehen können.
 - Dateien, Seiten und Websites sind nur für Benutzer sichtbar, die über Berechtigungen für die Quellinhalte verfügen, unabhängig davon, ob sie manuell von AI hinzugefügt oder hinzugefügt wurden.

In der folgenden Tabelle wird beschrieben, was Benutzer – Themenbetrachter, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.

|Themaelement|Was Benutzer sehen können|
|:---------|:------------------|
|Themaname|Benutzer können den Themanamen von Themen im Themencenter sehen. Einige Themen sind möglicherweise nicht sichtbar, wenn Benutzer nicht über Berechtigungen für den Quellinhalt verfügen oder eine geringe Relevanz für den Benutzer haben.|
|Beschreibung des Themas|VON AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftierte Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|




## <a name="see-also"></a>Weitere Informationen:

