---
title: Sicherheitstrimmerung für Microsoft -Themen
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
description: Übersicht über die Verwendung von Sicherheitseinstellungen zum Anzeigen von Themen.
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107518"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Sicherheitstrimmerung für Microsoft -Themen 

Benutzer von "Themen" können keine Informationen in Themen anzeigen, die von ihren vorhandenen Office 365-Berechtigungen nicht angezeigt werden können. Alles, was einem Benutzer auf einer Themenseite angezeigt wird (z. B. SharePoint-Websites, Dokumente, Dateien), sind Informationen, die er bereits sehen darf. In Themen werden keine änderungen an vorhandenen Berechtigungen vorgenommen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben

Wenn ein Thema mithilfe von KI oder manueller Curation erstellt wird, kann es eine Beschreibung des Themas, alternative Namen, personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten. Wenn diese Informationen auf einer Themenseite angezeigt werden, werden zwei Benutzern, die dasselbe Thema anzeigen, die gleichen Informationen nicht angezeigt.
  
Wenn Benutzer 1 z. B. die Themenseite "Untere" aufruft, wird möglicherweise diese Ansicht der Themenseite angezeigt.

![Thema "1" für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wenn Benutzer 2 jedoch auf derselben Seite des Themas "Untere" sucht, unterscheidet sich die Ansicht von Benutzer 1.  Benutzer 2 kann die *Dg-2000-Produktübersichtsdatei* im Abschnitt "Angeheftierte Dateien und Seiten" der Themenseite anzeigen, die für Benutzer 1 nicht angezeigt wird.  

![Thema "1" für Benutzer 2](../media/knowledge-management/user1-topic-view.png) </br> 

Der Unterschied, was Benutzern im gleichen Thema angezeigt wird, liegt daran, dass Benutzer möglicherweise nicht über die Office 365-Berechtigungen zum Anzeigen einer verwandten Website oder Datei verfügen.  Unter "Themen" werden die Berechtigungen respektiert, die für Elemente in einem Thema festgelegt sind, und der Zugriff auf sie kann nicht geändert werden. In unserem Beispiel kann Benutzer 1 die *Dg-2000-Produktübersichtsdatei* auf der Themenseite für Ihn nicht anzeigen, da Benutzer 1 nicht über Office 365-Berechtigungen zum Anzeigen der Datei verfügt.

Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema zu sehen, damit es nützlich ist, steht das Thema dem Benutzer nicht zur Verfügung. In diesem Fall wird dem Benutzer das hervorgehobene Thema nicht angezeigt. Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er nützlich ist, kann das Thema sehen.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Themenberechtigungen für Wissensmanager und Mitwirkende von Themen

Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, für die sie in Themen berechtigt sind.

Ebenso können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Thementeilnehmer – nur Informationen anzeigen, für die sie über Berechtigungen zum Anzeigen in Themen verfügen. 


## <a name="ai-versus-manually-curated-topic-information"></a>Ai im Vergleich zu manuell behandelten Themeninformationen

Themen können informationen enthalten, die von AI generiert werden, sowie Informationen, die von Themen mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.

 - Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.
 - Informationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für jeden sichtbar, der das Thema sehen kann.

In der folgenden Tabelle wird beschrieben, was Benutzer – Themenanzeiger, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.

|Themaelement|Was Benutzer sehen können|
|:---------|:------------------|
|Themaname|Benutzer können den Themennamen aller Themen im Themencenter sehen. Einige Themen sind möglicherweise nicht sichtbar, wenn sie eine geringe Relevanz für den Benutzer haben.|
|Themenbeschreibung|Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftierte Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|




## <a name="see-also"></a>Weitere Informationen:

