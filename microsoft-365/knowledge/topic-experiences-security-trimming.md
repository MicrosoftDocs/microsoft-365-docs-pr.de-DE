---
title: Thema Experiences Security Trimming (Preview)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Übersicht über die Verwendung von Sicherheit zum Anzeigen von Themen.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698950"
---
# <a name="topic-experiences-security-trimming-preview"></a>Thema Experiences Security Trimming (Preview)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Thema Erlebnisse Benutzer können keine Informationen in Themen anzeigen, die durch die vorhandenen Office 365 Berechtigungen verhindert werden. Alle Elemente, die ein Benutzer auf einer Themen Seite sieht (beispielsweise SharePoint-Websites, Dokumente, Dateien), werden Informationen, die er bereits sehen darf. In den Themen Erfahrungen werden keine Änderungen an vorhandenen Berechtigungen vorgenommen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben

Wenn ein Thema über AI oder manuelle Kuration erstellt wird, kann es eine Beschreibung des Themas, Alternative Namen, Personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten. Wenn diese Informationen auf einer Themen Seite angezeigt werden, ist es möglich, dass zwei Benutzer, die dasselbe Thema anzeigen, nicht dieselben Informationen sehen.
  
Wenn beispielsweise der Benutzer 1 die Neptun-Themen Seite anzeigt, können diese möglicherweise angezeigt werden.

![Neptun-Thema für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wenn Benutzer 2 jedoch dieselbe Neptun-Themen Seite betrachtet, unterscheidet sich Ihre Ansicht von Benutzer 1.  Benutzer 2 kann die Produkt Übersichtsdatei der *GD-2000* im Abschnitt **fixierte Dateien und Seiten** der Seite Thema anzeigen, die nicht für Benutzer 1 angezeigt wird. 

![Neptun-Thema für Benutzer 2](../media/knowledge-management/user1-topic-view.png) </br> 

Der Unterschied, was Benutzer im selben Thema sehen können, liegt daran, dass Benutzer möglicherweise nicht über die Office 365 Berechtigungen zum Anzeigen einer verwandten Website oder Datei verfügen.  Thema Experiences respektiert die Berechtigungen, die für Elemente in einem Thema festgelegt sind, und kann den Zugriff darauf nicht ändern. In unserem Beispiel kann Benutzer 1 die Produkt Übersichtsdatei der *GD-2000* nicht in ihrer Themen Seite für Neptun anzeigen, da Benutzer 1 nicht über Office 365 Berechtigungen zum Anzeigen der Datei verfügt.

Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema anzuzeigen, damit es nützlich ist, ist das Thema für den Benutzer nicht verfügbar. In dieser Instanz wird dem Benutzer das markierte Thema nicht angezeigt. Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er hilfreich ist, kann das Thema jedoch sehen.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Thema Berechtigungen für Knowledge Manager und Thema Mitwirkende

Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, für die Sie Berechtigungen zum Anzeigen von Themen haben.

Auf ähnliche Weise können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Thema Mitwirkende – nur Informationen anzeigen, für die Sie Berechtigungen zum Anzeigen von Themen haben. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus manuell kuratierte Themen Informationen

Themen können Informationen enthalten, die von AI generiert werden, sowie Informationen, die von Mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.

 - Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.
 - Informationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für alle sichtbar, die das Thema sehen können.

In der folgenden Tabelle wird beschrieben, was Benutzer – Thema Betrachter, Mitwirkende und Wissensmanager – in einem bestimmten Thema basierend auf Ihren Berechtigungen sehen können.

|Thema-Element|Was Benutzer sehen können|
|:---------|:------------------|
|Name des Themas|Benutzer können den Thema Namen aller Themen im Thema Center anzeigen. Einige Themen sind möglicherweise nicht sichtbar, wenn Sie eine geringe Relevanz für den Benutzer haben.|
|Beschreibung des Themas|Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftete Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|




## <a name="see-also"></a>Weitere Informationen:

