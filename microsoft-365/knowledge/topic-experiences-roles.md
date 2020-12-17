---
title: Rolle "Topic Experiences" (Vorschau)
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
description: Erfahren Sie mehr über Benutzerrollen in Thema Erfahrungen.
ms.openlocfilehash: ed4d40aa7bb91a85e28aba7ace99edf580c427a5
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698902"
---
# <a name="topic-experiences-roles-preview"></a>Rolle "Topic Experiences" (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).


Wenn Sie Themen Erfahrungen in Ihrer Microsoft 365-Umgebung verwenden, können Ihre Benutzer die folgenden Rollen haben:
-   Themenansicht
-   Thema Mitwirkender
-   Knowledge Manager
-   Wissens Administrator

## <a name="topic-viewer"></a>Themenansicht

Thema Viewer sind Benutzer in Ihrer Organisation, die hervorgehobene Themen in ihrer modernen SharePoint-Website und in der SharePoint-Suche anzeigen können. Sie können hervorgehobene Themen auswählen, um weitere Details dazu in einer Themen Seite anzuzeigen. 

Für die Themen Hervorhebungen und ihre Themenseiten, die für einen Themen Betrachter sichtbar sein sollen, muss der Benutzer:
-   Ihr Microsoft 365-Administrator erhält [eine Lizenz zum Thema Experiences License](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) .
-   Sie haben die Möglichkeit, über Sichtbarkeit für Themen zu verfügen. Dies erfolgt über den Knowledge-Administrator auf der Seite Einstellungen für Themen Erlebnisse im Microsoft 365 Admin Center.


## <a name="topic-contributors"></a>Thema Mitwirkende

Mitwirkende des Themas sind Benutzer in Ihrer Organisation, die nicht nur über Berechtigungen für die Themen Anzeige verfügen, sondern auch ein vorhandenes Thema bearbeiten oder ein neues Thema erstellen können. Sie haben eine wichtige Rolle in der manuellen "kuratierten" Informationen in einer Themen Seite (sowohl AI als auch manuell bereitgestellt), um ihre Qualität zu gewährleisten.

Benutzern, die über die Berechtigung "Thema mitwirken" verfügen, wird **auf den Themen** Seiten eine Schaltfläche angezeigt, die es Ihnen ermöglicht, ein Thema zu aktualisieren und zu veröffentlichen.

Ein Thema Mitwirkender kann auch ein neues Thema über die Themen Center-Website erstellen und veröffentlichen.

Um ein Thema erstellen und bearbeiten zu können, muss der Benutzer Folgendes tun:

-   Ihr Microsoft 365-Administrator erhält [eine Lizenz zum Thema Experiences License](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) .
-   [Berechtigungen zum Erstellen und Bearbeiten von Themen zugewiesen werden](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Dies erfolgt über den Knowledge-Administrator auf der Seite Einstellungen für Themen Erlebnisse im Microsoft 365 Admin Center.

## <a name="knowledge-managers"></a>Wissensmanager

Wissensmanager sind Benutzer, die Themen in Ihrer Organisation verwalten.  Die Themen Verwaltung erfolgt über die Seite Themen verwalten im Themen Center und ist nur für Wissensmanager sichtbar.

Auf der Seite Themen verwalten können ein Wissensmanager die folgenden Aufgaben ausführen:
-   Alle AI-vorgeschlagenen Themen anzeigen.
-   Überprüfen Sie die Themen, um zu bestätigen, dass Sie gültig sind.
-   Entfernen Sie Themen, die Sie nicht für Ihre Benutzer sichtbar machen möchten.


Darüber hinaus kann ein Knowledge Manager vorhandene Themen bearbeiten oder neue erstellen.

Um Themen verwalten zu können, muss der Benutzer folgende Aufgaben erfüllen:
-   Ihr Microsoft 365-Administrator erhält [eine Lizenz zum Thema Experiences License](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) .
-   [Berechtigungen zum Verwalten von Themen zugewiesen werden](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Dies erfolgt über den Knowledge-Administrator auf der Seite Einstellungen für Themen Erlebnisse im Microsoft 365 Admin Center.

Benutzer mit guten Gesamt Kenntnissen Ihres Unternehmens können gute Kandidaten für die Knowledge Manager-Rolle sein. Diese Personen verfügen möglicherweise nicht nur über das wissen, ob Themen gültig sind oder nicht, sondern kennen möglicherweise auch Personen innerhalb des Unternehmens, die sich auf diese Themen beziehen.


## <a name="knowledge-admins"></a>Wissens-Admins

Knowledge-Administratoren sind Administratoren, die Themen Erfahrungen in Ihrer Microsoft 365-Umgebung einrichten und konfigurieren. Sie verwalten auch die Einstellungen für das Thema Erfahrungen, nachdem die Einrichtung abgeschlossen wurde. Die Knowledge admin-Rolle erfordert, dass Sie ein Microsoft 365 Global-oder SharePoint-Administrator sind, da Setup und Verwaltung im Microsoft 365 Admin Center ausgeführt werden.
Während des Setups können Knowledge-Administratoren Themen Erfahrungen für folgende Aufgaben konfigurieren:

-   Wählen Sie aus, welche SharePoint-Websites für Themen gecrawlt werden sollen.
-   Wählen Sie aus, welche lizenzierten Benutzer Themen anzeigen können (Thema Betrachter).
-   Wählen Sie aus, welche Themen von der Identifizierung ausgeschlossen werden sollen.
-   Wählen Sie aus, mit welchen lizenzierten Benutzern Themen erstellt und bearbeitet werden können (Thema Mitwirkende).
-   Wählen Sie aus, welche lizenzierten Benutzer Themen verwalten können (Wissensmanager).
-   Nennen Sie das Thema Center.

Wissensmanager müssen in der Lage sein, mit allen thematischen Erfahrungen von Beteiligten in Ihrer Organisation zu koordinieren und zu wissen, wie Sie diese konfigurieren. Wenn beispielsweise ein neues Projekt vertrauliche Informationen enthält, muss der Knowledge Manager informiert werden, damit Sie sicherstellen können, dass die SharePoint-Website nicht für Themen gecrawlt wird oder bestimmte Themen Namen ausgeschlossen werden müssen.


## <a name="see-also"></a>Weitere Informationen:

