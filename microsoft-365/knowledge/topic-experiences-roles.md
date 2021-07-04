---
title: Themen zu Microsoft Viva – Rollen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Erfahren Sie mehr über Benutzerrollen in Viva Topics.
ms.openlocfilehash: 9f1d3667ee9eeb05201613c15dc360b2b006cecb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288071"
---
# <a name="microsoft-viva-topics-roles"></a>Themen zu Microsoft Viva – Rollen 

Wenn Sie Viva Topics in Ihrer Microsoft 365-Umgebung verwenden, können Ihre Benutzer die folgenden Rollen haben:

- Themenbetrachter
- Themenmitwirkender
- Wissensmanager
- Wissensadministrator

## <a name="topic-viewer"></a>Themenbetrachter

Themenbetrachter sind Benutzer in Ihrer Organisation, die Themen anzeigen können, die auf ihrer SharePoint modernen Website hervorgehoben sind, Microsoft Search über SharePoint und Office.com und das Themencenter. Sie können weitere Details zu einem Thema auf der Themenseite anzeigen. 

Damit Themenhervorhebungen und ihre Themenseiten für einen Themenbetrachter sichtbar sind, muss der Benutzer:

- Von ihrem Microsoft 365-Administrator [eine Viva Topics-Lizenz zugewiesen werden.](./set-up-topic-experiences.md#assign-licenses)
- Berechtigt sein, Themen sichtbar zu machen. Diese Aufgabe wird vom Wissensadministrator auf der Einstellungsseite von Viva Topics im Microsoft 365 Admin Center ausgeführt.

## <a name="topic-contributors"></a>Themenmitwirkende

Themenmitwirkende sind Benutzer in Ihrer Organisation, die nicht nur Rechte zum Betrachten von Themen haben, sondern auch ein vorhandenes Thema bearbeiten oder ein neues Thema erstellen können. Sie spielen eine wichtige Rolle beim manuellen "Kuratieren" der Informationen auf einer Themenseite (sowohl ki als auch manuell bereitgestellt), um ihre Qualität sicherzustellen.

Benutzern mit Themenmitwirkendenberechtigungen wird eine Schaltfläche **"Bearbeiten"** auf themenseitigen Seiten angezeigt, mit der sie Aktualisierungen an einem Thema vornehmen und ein Thema veröffentlichen können.

Ein Themenmitwirkender auch ein neues Thema im Themencenter erstellen und veröffentlichen.

Um ein Thema zu erstellen und zu bearbeiten, muss der Benutzer Folgendes tun:

- Von ihrem Microsoft 365-Administrator [eine Viva Topics-Lizenz zugewiesen werden.](./set-up-topic-experiences.md#assign-licenses)
- [Ihnen werden Berechtigungen zum Erstellen und Bearbeiten von Themen zugewiesen.](./topic-experiences-user-permissions.md) Diese Aufgabe wird vom Wissensadministrator auf der Einstellungsseite von Viva Topics im Microsoft 365 Admin Center ausgeführt.

## <a name="knowledge-managers"></a>Wissensmanager

Wissensmanager sind Benutzer, die Themen in Ihrer Organisation verwalten.  Die Themenverwaltung erfolgt über die Seite "Themen verwalten" im Themencenter und ist nur für Wissensmanager sichtbar.

Auf der Seite "Themen verwalten" können Wissensmanager die folgenden Aufgaben ausführen:

- KI-vorgeschlagene Themen anzeigen.
- Überprüfen Sie die Themen, um zu bestätigen, dass sie gültig sind.
- Entfernen Sie Themen, die Für Ihre Benutzer nicht sichtbar sein sollen.

Darüber hinaus kann ein Wissensmanager vorhandene Themen bearbeiten oder neue Themen erstellen.

Um Themen zu verwalten, muss der Benutzer Folgendes tun:

- Von ihrem Microsoft 365-Administrator [eine Viva Topics-Lizenz zugewiesen werden.](./set-up-topic-experiences.md#assign-licenses)
- [Berechtigungen zum Verwalten von Themen zugewiesen werden).](./topic-experiences-user-permissions.md) Diese Aufgabe wird vom Wissensadministrator auf der Einstellungsseite von Viva Topics im Microsoft 365 Admin Center ausgeführt.

Benutzer, die über ein gutes Gesamtwissen über Ihr Unternehmen verfügen, können gute Kandidaten für die Rolle des Wissensmanagers sein. Diese Personen verfügen möglicherweise nicht nur über das Wissen, um zu wissen, ob Themen gültig sind oder nicht, sondern sie kennen auch Personen innerhalb des Unternehmens, die mit diesen Themen in Zusammenhang stehen.

## <a name="knowledge-admins"></a>Wissensadministratoren

Wissensadministratoren sind Administratoren, die Viva Topics in Ihrer Microsoft 365 Umgebung einrichten und konfigurieren. Sie verwalten auch die Viva Topics-Einstellungen, nachdem die Einrichtung abgeschlossen ist. Die Rolle des Wissensadministrators erfordert, dass Sie ein Microsoft 365 globaler oder SharePoint-Administrator sind, da setup and management in der Microsoft 365 Admin Center erfolgt.
Während des Setups können Wissensadministratoren Viva Topics für Folgendes konfigurieren:

- Auszuwählen, welche SharePoint-Websites nach Themen durchforstet werden sollen.
- Auszuwählen, welche lizenzierten Benutzer Themen ansehen können (Themenbetrachter).
- Auszuwählen, welche Themen von der Suche ausgeschlossen werden sollen.
- Auszuwählen, welche lizenzierten Benutzer, die Themen erstellen und bearbeiten können (Themenmitwirkende).
- Auszuwählen, welche lizenzierten Benutzer, die Themen verwalten können (Wissensmanager).
- Benennen Sie das Themencenter.

Wissensmanager müssen in der Lage sein, sich mit allen Projektbeteiligten in ihrem Unternehmen zu koordinieren, um zu wissen, wie Viva Topics konfiguriert werden kann. Wenn z. B. ein neues Projekt vertrauliche Informationen enthält, muss der Wissensmanager informiert werden, damit er sicherstellen kann, dass die SharePoint Website nicht nach Themen durchforstet wird oder bestimmte Themennamen ausgeschlossen werden müssen.
