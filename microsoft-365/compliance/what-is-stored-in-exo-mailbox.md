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
description: Inhalte, die von cloudbasierten Apps in Microsoft 365 erstellt werden, werden gespeichert oder dem Postfach eines Benutzers Exchange Online zugeordnet. Diese Inhalte können mithilfe von Microsoft eDiscovery-Tools durchsucht werden.
ms.openlocfilehash: 975f4ac8be8c2cdeed8dea1d73699607662a1ce9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288143"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>In Exchange Online Postfächern für eDiscovery gespeicherte Inhalte

Ein Postfach in Exchange Online wird in erster Linie zum Speichern von E-Mail-bezogenen Elementen wie Nachrichten, Kalenderelementen, Aufgaben und Notizen verwendet. Dies ändert sich jedoch, da mehr cloudbasierte Apps ihre Daten auch im Postfach eines Benutzers speichern. Ein Vorteil beim Speichern von Daten in einem Postfach besteht darin, dass Sie die Suchtools in der Inhaltssuche, Core eDiscovery und Advanced eDiscovery verwenden können, um die Daten aus diesen cloudbasierten Apps zu suchen, anzuzeigen und zu exportieren. Die Daten aus einigen dieser Apps werden in ausgeblendeten Ordnern gespeichert, die sich in einer nicht-zwischenpersönlichen Nachrichtenunterstruktur (nicht IPM) im Postfach befinden. Daten aus anderen cloudbasierten Apps werden möglicherweise nicht _im_ Postfach gespeichert, sind aber dem Postfach _zugeordnet_ und werden in Suchvorgängen zurückgegeben (wenn diese Daten mit der Suchabfrage übereinstimmen). Unabhängig davon, ob cloudbasierte Daten in einem Benutzerpostfach gespeichert oder einem Benutzerpostfach zugeordnet sind, sind die Daten in der Regel nicht in einem E-Mail-Client sichtbar, wenn ein Benutzer sein Postfach öffnet.

In der folgenden Tabelle sind die Apps aufgeführt, die Daten entweder speichern oder einem cloudbasierten Postfach zuordnen. In der Tabelle wird auch der Inhaltstyp beschrieben, den die einzelnen Apps erzeugen.

<br>

****

|Microsoft 365-App|Beschreibung|
|---|---|
|Formen<sup>*</sup>|Formulare und Antworten auf ein Formular werden in Dateien gespeichert, die an E-Mail-Nachrichten angefügt sind, und in einem ausgeblendeten Ordner im Postfach des Benutzers, der das Formular erstellt hat. Formulare, die vor April 2020 erstellt wurden, werden als PDF-Datei gespeichert. Formulare, die nach 2020 erstellt wurden, werden als JSON-Datei gespeichert. Antworten auf ein Formular werden in einer CSV-Datei gespeichert. Wenn Sie Inhalte aus Formularen in einer PST-Datei exportieren, befinden sich diese Daten im Ordner **"ApplicationDataRoot"** in einem Unterordner mit der folgenden GUID (Globally Unique Identified): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Microsoft 365-Gruppen|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden in dem Postfach gespeichert, das einer Microsoft 365 Gruppe zugeordnet ist.|
|Outlook/Exchange Online|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden im Postfach eines Benutzers gespeichert.|
|Personen|Kontakte in der Kontakte-App (die die gleichen Kontakte wie die kontakte sind, auf die in Outlook zugegriffen werden kann) werden im Postfach eines Benutzers gespeichert.|
|Klassenzeitplan|Im Klassenzeitplan erstellte Pläne werden im Postfach der entsprechenden Microsoft 365-Gruppe gespeichert, die bereitgestellt wird, wenn ein neuer Plan erstellt wird. Der Alias für das Gruppenpostfach ist der Name des Plans.|
|Skype for Business|Unterhaltungen in Skype for Business werden im Ordner "Aufgezeichnete Unterhaltungen" im Postfach eines Benutzers gespeichert. Wenn das Postfach eines Teilnehmers einer Skype Besprechung in das Beweissicherungsverfahren versetzt oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden an eine Besprechung angefügte Dateien im Teilnehmerpostfach aufbewahrt.|
|Herrschaft<sup>*</sup>|Sways werden als HTML-Datei gespeichert, die an eine E-Mail-Nachricht angefügt ist und in einem ausgeblendeten Ordner im Postfach des Benutzers gespeichert wird, der das Sway erstellt hat. Wenn Sie Inhalte aus Sway in einer PST-Datei exportieren, befinden sich diese Daten im Ordner **"ApplicationDataRoot"** in einem Unterordner, der mit der folgenden GUID benannt ist: **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Aufgaben|Aufgaben in der Tasks-App (bei denen es sich um die gleichen Aufgaben wie die aufgaben handelt, auf die in Outlook zugegriffen werden kann) werden im Postfach eines Benutzers gespeichert.|
|Teams|Unterhaltungen, die Teil eines Teams Kanals sind, sind dem Teams Postfach zugeordnet. Unterhaltungen, die Teil der Chatliste in Teams (auch als *1 x N-Chats* bezeichnet) gehören, sind dem Postfach der Benutzer zugeordnet, die am Chat teilnehmen. Darüber hinaus werden zusammenfassende Informationen für Besprechungen und Anrufe in einem Teams Kanal Postfächern von Benutzern zugeordnet, die sich in die Besprechung oder den Anruf einwählten. Wenn Sie also nach Teams Inhalten suchen, würden Sie das Teams Postfach nach Inhalten in Kanalunterhaltungen durchsuchen und Benutzerpostfächer nach Inhalten in 1 x N-Chats durchsuchen.|
|To-Do|Aufgaben (so genannte *Aufgaben,* die in Aufgabenlisten gespeichert werden) in der To-Do App werden im Postfach eines Benutzers gespeichert.|
|Yammer|Unterhaltungen und Kommentare innerhalb einer Yammer Community sind dem Microsoft 365 Gruppenpostfach sowie dem Benutzerpostfach des Autors und allen benannten Empfängern (@erwähnten oder Cc'ed-Benutzern) zugeordnet. Private Nachrichten, die außerhalb einer Yammer Community gesendet werden, werden im Postfach der Benutzer gespeichert, die an der privaten Nachricht teilnehmen.|
|

> [!NOTE]
> <sup>*</sup>Wenn zu diesem Zeitpunkt ein Haltebereich für ein Postfach (mithilfe von Haltebereichen in Core eDiscovery oder Advanced eDiscovery Fällen) platziert wird, werden Inhalte dieser App nicht durch den Haltebereich beibehalten.
