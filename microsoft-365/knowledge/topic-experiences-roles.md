---
title: Rollen "Themenerfahrungen" (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über Benutzerrollen in Themenerfahrungen.
ms.openlocfilehash: b649ea81d8e5b036e9332e9c87b67a951b5905a7
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975693"
---
# <a name="topic-experiences-roles-preview"></a>Rollen "Themenerfahrungen" (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex Private Preview vorgesehen. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).


Wenn Sie Themenerfahrungen in Ihrer Microsoft 365-Umgebung verwenden, können Ihre Benutzer die folgenden Rollen haben:
-   Themenanzeige
-   Mitwirkender des Themas
-   Knowledge Manager
-   Wissensadministrator

## <a name="topic-viewer"></a>Themenanzeige

Themenanzeigen sind Benutzer in Ihrer Organisation, die hervorgehobene Themen auf ihrer modernen SharePoint-Website und in der SharePoint-Suche anzeigen können. Sie können hervorgehobene Themen auswählen, um weitere Details zu diesen Themen auf einer Themenseite anzuzeigen. 

Damit Themenher highlights und ihre Themenseiten für einen Themenanzeiger sichtbar sind, muss der Benutzer:
-   [Erhalten Sie von ihrem](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) Microsoft 365-Administrator eine Lizenz für Themenerfahrungen.
-   Sie können Themen einsichten. Dies wird vom Wissensadministrator auf der Seite "Einstellungen für Themenerfahrungen" im Microsoft 365 Admin Center durchgeführt.


## <a name="topic-contributors"></a>Mitwirkende an Themen

Mitwirkende an Themen sind Benutzer in Ihrer Organisation, die nicht nur über Berechtigungen für die Themenanzeige verfügen, sondern auch ein vorhandenes Thema bearbeiten oder ein neues Thema erstellen können. Sie spielen eine wichtige Rolle beim manuellen "Aus curating" der Informationen auf einer Themenseite (sowohl ai als auch manuell bereitgestellt), um die Qualität sicherzustellen.

Benutzern mit Berechtigungen für mitwirkende Themen wird eine Schaltfläche "Bearbeiten" auf Themenseiten angezeigt, mit der sie ein Thema aktualisieren und veröffentlichen können. 

Ein Mitwirkender eines Themas kann auch ein neues Thema über seine Themencenterwebsite erstellen und veröffentlichen.

Um ein Thema erstellen und bearbeiten zu können, muss der Benutzer:

-   [Erhalten Sie von ihrem](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) Microsoft 365-Administrator eine Lizenz für Themenerfahrungen.
-   [Ihnen werden Berechtigungen zum Erstellen und Bearbeiten von Themen zugewiesen.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center) Dies wird vom Wissensadministrator auf der Seite "Einstellungen für Themen" im Microsoft 365 Admin Center durchgeführt.

## <a name="knowledge-managers"></a>Wissensmanager

Wissensmanager sind Benutzer, die Themen in Ihrer Organisation verwalten.  Die Themenverwaltung erfolgt über die Seite "Themen verwalten" im Themencenter und ist nur für Wissensmanager sichtbar.

Auf der Seite "Themen verwalten" können Wissensmanager die folgenden Aufgaben ausführen:
-   Zeigen Sie alle themen vorgeschlagenen AI-Themen an.
-   Überprüfen Sie die Themen, um zu bestätigen, dass sie gültig sind.
-   Entfernen Sie Themen, die Sie ihren Benutzern nicht sichtbar machen möchten.


Darüber hinaus kann ein Knowledge Manager vorhandene Themen bearbeiten oder neue erstellen.

Um Themen verwalten zu können, muss der Benutzer:
-   [Erhalten Sie von ihrem](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) Microsoft 365-Administrator eine Lizenz für Themenerfahrungen.
-   [Ihnen werden Berechtigungen zum Verwalten von Themen zugewiesen).](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center) Dies wird vom Wissensadministrator auf der Seite "Einstellungen für Themen" im Microsoft 365 Admin Center durchgeführt.

Benutzer mit einem guten Gesamtwissen über Ihr Unternehmen können gute Kandidaten für die Rolle des Knowledge Managers sein. Diese Personen verfügen möglicherweise nicht nur über das Wissen, ob Themen gültig sind oder nicht, sondern auch Personen innerhalb des Unternehmens, die mit diesen Themen in Verbindung stehen.


## <a name="knowledge-admins"></a>Wissensadministratoren

Wissensadministratoren sind Administratoren, die Themenerfahrungen in Ihrer Microsoft 365-Umgebung einrichten und konfigurieren. Sie verwalten auch die Einstellungen für "Themenerfahrungen", nachdem die Einrichtung abgeschlossen ist. Die Rolle des Wissensadministrators erfordert, dass Sie ein globaler Microsoft 365- oder -SharePoint-Administrator sind, da Setup und Verwaltung im Microsoft 365 Admin Center durchgeführt werden.
Während des Setups können Wissensadministratoren Die Themenerfahrungen für folgende Aufgaben konfigurieren:

-   Wählen Sie aus, welche SharePoint-Websites für Themen gecrawlt werden sollen.
-   Wählen Sie aus, welche lizenzierten Benutzer Themen (Themenanzeiger) anzeigen können.
-   Wählen Sie aus, welche Themen nicht identifiziert werden sollen.
-   Wählen Sie aus, welche lizenzierten Benutzer Themen erstellen und bearbeiten können (Mitwirkende an Themen).
-   Wählen Sie aus, welche lizenzierten Benutzer Themen (Wissensmanager) verwalten können.
-   Benennen Sie das Themencenter.

Wissensmanager müssen sich mit allen Projektbeteiligten in ihrer Organisation abstimmen können, um zu wissen, wie sie konfiguriert werden können. Wenn ein neues Projekt beispielsweise vertrauliche Informationen enthält, muss der Knowledge Manager informiert werden, damit er sicherstellen kann, dass die SharePoint-Website nicht nach Themen gecrawlt wird, oder bestimmte Themennamen müssen ausgeschlossen werden.


## <a name="see-also"></a>Weitere Informationen:

