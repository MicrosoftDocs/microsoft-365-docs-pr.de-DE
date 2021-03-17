---
title: In Exchange Online-Postfächern gespeicherte Inhalte
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
description: Von cloudbasierten Apps in Microsoft 365 erzeugte Inhalte werden gespeichert oder dem Exchange Online-Postfach eines Benutzers zugeordnet. Dieser Inhalt kann mithilfe von Microsoft eDiscovery-Tools durchsucht werden.
ms.openlocfilehash: 872e618486c273e07e8dcf98d61bbbb7d8f95051
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838612"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>In Exchange Online-Postfächern für eDiscovery gespeicherte Inhalte

Ein Postfach in Exchange Online wird hauptsächlich zum Speichern E-Mail-bezogener Elemente wie Nachrichten, Kalenderelemente, Aufgaben und Notizen verwendet. Dies ändert sich jedoch, da mehr cloudbasierte Apps ihre Daten auch im Postfach eines Benutzers speichern. Ein Vorteil des Speicherns von Daten in einem Postfach besteht in der Verwendung der Suchtools in der Inhaltssuche, core eDiscovery und Advanced eDiscovery zum Suchen, Anzeigen und Exportieren der Daten aus diesen cloudbasierten Apps. Die Daten aus einigen dieser Apps werden in ausgeblendeten Ordnern in einer nicht interpersonalen Nachrichtenunterstruktur (non-IPM) im Postfach gespeichert. Daten aus anderen cloudbasierten Apps werden möglicherweise nicht _im_  Postfach gespeichert, aber dem Postfach zugeordnet und in Suchabfragen zurückgegeben (wenn diese Daten mit der Suchabfrage übereinstimmen). Unabhängig davon, ob cloudbasierte Daten in einem Benutzerpostfach gespeichert oder diesem zugeordnet sind, werden die Daten in der Regel nicht in einem E-Mail-Client angezeigt, wenn ein Benutzer sein Postfach öffnet.

In der folgenden Tabelle sind die Apps aufgeführt, die Daten entweder einem cloudbasierten Postfach speichern oder nen. In der Tabelle wird auch der Inhaltstyp beschrieben, den jede App erzeugt.

|Microsoft 365-App|Beschreibung|
|:---------|:---------|
|Formulare|Formulare und Antworten auf ein Formular werden in Dateien gespeichert, die an E-Mail-Nachrichten angefügt sind, und in einem ausgeblendeten Ordner im Postfach des Benutzers gespeichert, der das Formular erstellt hat. Formulare, die vor April 2020 erstellt wurden, werden als PDF-Datei gespeichert. Formulare, die nach 2020 erstellt wurden, werden als JSON-Datei gespeichert.  Antworten auf ein Formular werden in einer CSV-Datei gespeichert. Wenn Sie Inhalte aus Formularen in einer #A0 exportieren, befinden sich diese Daten im Ordner **ApplicationDataRoot** in einem Unterordner namens mit der folgenden GUID (Globally Unique Identified): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**. |
|Microsoft 365-Gruppen|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden im Postfach gespeichert, das einer Microsoft 365-Gruppe zugeordnet ist.|
|Outlook/Exchange Online|E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden im Postfach eines Benutzers gespeichert.|
|Personen|Kontakte in der People-App (bei denen es sich um dieselben Kontakte handelt, auf die in Outlook zugegriffen werden kann) werden im Postfach eines Benutzers gespeichert.|
|Klassenzeitplan|Im Klassenzeitplan erstellte Pläne werden im Postfach der entsprechenden Microsoft 365-Gruppe gespeichert, das beim Erstellen eines neuen Plans bereitgestellt wird. Der Alias für das Gruppenpostfach ist der Name des Plans.|
|Skype for Business|Unterhaltungen in Skype for Business werden im Ordner Unterhaltungsverlauf im Postfach eines Benutzers gespeichert. Wenn das Postfach eines Teilnehmers einer Skype-Besprechung in das Aufbewahrungsverfahren einbehalten oder einer Aufbewahrungsrichtlinie zugewiesen ist, werden dateien, die einer Besprechung zugeordnet sind, im Teilnehmerpostfach aufbewahrt.|
|Sway|Sways werden als HTML-Datei gespeichert, die an eine E-Mail-Nachricht angefügt ist, und in einem ausgeblendeten Ordner im Postfach des Benutzers gespeichert, der den Sway erstellt hat. Wenn Sie Inhalte aus Sway in einer PST-Datei exportieren, befinden sich diese Daten im Ordner **ApplicationDataRoot** in einem Unterordner namens mit der folgenden GUID:  **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Aufgaben|Aufgaben in der Tasks-App (bei denen es sich um dieselben Aufgaben handelt, auf die in Outlook zugegriffen werden kann) werden im Postfach eines Benutzers gespeichert.|
|Teams|Unterhaltungen, die Teil eines Teams-Kanals sind, sind dem Teams-Postfach zugeordnet. Unterhaltungen, die Teil der Chatliste in Teams (auch *1 x N-Chats* genannt) sind dem Postfach der Benutzer zugeordnet, die am Chat teilnehmen. Außerdem sind Zusammenfassungsinformationen für Besprechungen und Anrufe in einem Teams-Kanal Postfächern von Benutzern zugeordnet, die sich an der Besprechung oder an einem Anruf einwählten. Wenn Sie also nach Teams-Inhalten suchen, würden Sie das Teams-Postfach nach Inhalten in Kanalunterhaltungen durchsuchen und Benutzerpostfächer nach Inhalten in 1 x N-Chats durchsuchen.|
|To-Do|Aufgaben (Aufgaben, *die* in Aufgabenlisten gespeichert werden) in der To-Do-App werden im Postfach eines Benutzers gespeichert.|
|Yammer|Unterhaltungen und Kommentare innerhalb einer Yammer-Community sind dem Microsoft 365-Gruppenpostfach sowie dem Benutzerpostfach des Autors und benannten Empfängern (@ erwähnten oder Cc'ed-Benutzern) zugeordnet. Private Nachrichten, die außerhalb einer Yammer gesendet werden, werden im Postfach der Benutzer gespeichert, die an der privaten Nachricht teilnehmen.|  
||||

> [!NOTE]
> Wenn zu diesem Zeitpunkt ein Haltebereich für ein Postfach (mithilfe von Archiven in Core eDiscovery- und Advanced eDiscovery-Fällen) platziert wird, werden Inhalte aus Forms und Sway nicht vom Haltebereich beibehalten.
