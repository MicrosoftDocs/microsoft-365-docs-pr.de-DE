---
title: In Exchange Online Postfächern gespeicherte Inhalte
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Daten, die von cloudbasierten apps in Microsoft 365 erstellt wurden, werden mit dem Exchange Online Postfach eines Benutzers gespeichert oder diesem zugeordnet.
ms.openlocfilehash: 946ad069a57e411c20d9b0a723d28dc03a4b094f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626281"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>In Exchange Online Postfächern gespeicherte Inhalte

Ein Postfach in Exchange Online dient hauptsächlich zum Speichern von e-Mail-bezogenen Elementen wie Nachrichten, Kalenderelementen, Aufgaben und Notizen. Dies ändert sich jedoch, da weitere Cloud-basierte apps Ihre Daten auch im Postfach eines Benutzers speichern. Ein Vorteil beim Speichern von Daten in einem Postfach besteht darin, dass Sie die Such Tools für die Inhaltssuche, die zentrale eDiscovery, die erweiterte eDiscovery und Daten Untersuchungen zum Suchen, anzeigen und Exportieren der Daten aus diesen cloudbasierten Apps verwenden können. Die Daten aus einigen dieser apps werden in ausgeblendeten Ordnern gespeichert, die sich in einer nicht-zwischenmenschlichen Nachricht (nicht-IPM) im Postfach befinden. Daten aus anderen cloudbasierten apps werden möglicherweise nicht _im_ Postfach gespeichert, aber mit dem Postfach _verknüpft_ und in Suchvorgängen zurückgegeben (wenn diese Daten mit der Suchabfrage übereinstimmen). Unabhängig davon, ob Cloud-basierte Daten in einem Benutzerpostfach gespeichert oder diesem zugeordnet sind, werden die Daten in der Regel nicht in einem e-Mail-Client angezeigt, wenn ein Benutzer sein Postfach öffnet.

In der folgenden Tabelle sind die apps aufgeführt, mit denen Daten einem cloudbasierten Postfach gespeichert oder zugeordnet werden. In der Tabelle wird auch der Inhaltstyp beschrieben, den jede APP erzeugt.

|Microsoft 365-App|Beschreibung|
|:---------|:---------|
|Forms|Formulare (als PDF-Datei gespeichert) und Antworten auf ein Formular (in einer CSV-Datei gespeichert) werden e-Mail-Nachrichten angefügt und in einem verborgenen Ordner im Postfach des Benutzers gespeichert, der das Formular erstellt hat. Wenn Sie Inhalte aus Formularen in einer PST-Datei exportieren, befinden sich diese Daten im Ordner **ApplicationDataRoot** in einem Unterordner namens mit der folgenden global eindeutigen Identifizierung (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Microsoft 365-Gruppen|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden in dem Postfach gespeichert, das einer Microsoft 365-Gruppe zugeordnet ist.|
|Outlook/Exchange Online|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden im Postfach eines Benutzers gespeichert.|
|Personen|Kontakte in der Personen-App (die dieselben Kontakte wie die in Outlook zugänglichen sind) werden im Postfach eines Benutzers gespeichert.|
|Klassen Zeitplan|Pläne, die im Klassen Zeitplan erstellt wurden, werden im Postfach der entsprechenden Microsoft 365-Gruppe gespeichert, die beim Erstellen eines neuen Plans bereitgestellt wird. Der Alias für das Gruppenpostfach ist der Name des Plans.|
|Skype for Business|Unterhaltungen in Skype for Business werden im Ordner "Unterhaltungsverlauf" im Postfach eines Benutzers gespeichert. Wenn das Postfach eines Teilnehmers einer Skype-Besprechung in das Beweissicherungsverfahren aufgenommen oder einer Aufbewahrungsrichtlinie zugewiesen wurde, werden Dateien, die einer Besprechung zugeordnet sind, im Postfach der Teilnehmer aufbewahrt.|
|Sway|Sways werden als HTML-Datei gespeichert, die an eine e-Mail-Nachricht angefügt und in einem verborgenen Ordner im Postfach des Benutzers gespeichert ist, der die Sway erstellt hat. Wenn Sie Inhalte aus Sway in einer PST-Datei exportieren, befinden sich diese Daten im **ApplicationDataRoot** -Ordner in einem Unterordner mit der folgenden GUID) **905fcf26-4eb7-48A0-9ff0-8dcc7194b5ba**.|
|Aufgaben|Aufgaben in der Aufgaben-app (bei denen es sich um dieselben Aufgaben handelt, die in Outlook verfügbar sind) werden im Postfach eines Benutzers gespeichert.|
|Teams|Unterhaltungen, die Teil eines Teams-Kanals sind, sind dem Postfach "Teams" zugeordnet. Unterhaltungen, die Teil der Chat Liste in Microsoft Teams (auch *1 x N-Chats*genannt) sind, sind dem Postfach der Benutzer zugeordnet, die am Chat teilnehmen. Außerdem werden zusammenfassende Informationen für Besprechungen und Anrufe in einem Teams-Kanal Postfächern von Benutzern zugeordnet, die sich in die Besprechung oder den Anruf eingewählt haben. Wenn Sie also nach Microsoft Teams-Inhalten suchen, suchen Sie im Teams-Postfach nach Inhalten in Kanal Unterhaltungen und Durchsuchen von Benutzerpostfächern nach Inhalten in 1 x N-Chats.| 
|To-Do|Aufgaben (" *to-DOS*", die in "to-do"-Listen gespeichert sind) in der to-do-App werden im Postfach eines Benutzers gespeichert.|
||||

> [!NOTE]
> Wenn ein Speicherplatz in einem Postfach (mithilfe von Haltebereichen in eDiscovery-und erweiterte eDiscovery-Fälle) abgelegt wird, werden Inhalte aus Formularen und Sway nicht durch den Haltestatus beibehalten. 
