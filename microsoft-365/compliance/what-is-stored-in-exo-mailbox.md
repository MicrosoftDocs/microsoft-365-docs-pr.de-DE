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
description: Daten, die von Cloud-basierten apps in Office 365 erstellt wurden, werden in der Microsoft-Cloud im Exchange Online Postfach eines Benutzers gespeichert.
ms.openlocfilehash: f9db94eebf855a2d8dcfee8897ca6171eabbc400
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597192"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>In Exchange Online Postfächern gespeicherte Inhalte

Ein Postfach in Exchange Online dient hauptsächlich zum Speichern von e-Mail-bezogenen Elementen wie Nachrichten, Kalenderelementen, Aufgaben und Notizen. Dies ändert sich jedoch, da mehr Cloud-basierte Office 365-apps auch Ihre Daten im Postfach eines Benutzers speichern. Ein Vorteil beim Speichern von Daten in einem Postfach besteht darin, dass Sie die Such Tools in der Inhaltssuche, eDiscovery, Advanced eDiscovery und Daten Untersuchungen zum Suchen, anzeigen und Exportieren der Daten aus diesen cloudbasierten Apps verwenden können. Die Daten aus einigen dieser apps werden in ausgeblendeten Ordnern gespeichert, die sich in einer nicht-zwischenmenschlichen Nachricht (nicht-IPM) im Postfach befinden. Dies bedeutet, dass die Daten aus der Sicht des Benutzers ausgeblendet werden, wenn Sie Outlook oder andere e-Mail-Clients verwenden, um auf Ihr Postfach zuzugreifen.

In der folgenden Tabelle sind die Office 365 apps aufgeführt, in denen Daten in einem cloudbasierten Postfach gespeichert werden. In der Tabelle wird auch der Inhaltstyp beschrieben, den jede APP speichert.

|Office 365-App  |Beschreibung  |
|:---------|:---------|
|Formulare     <br/> |Formulare (als PDF-Datei gespeichert) und Antworten auf ein Formular (in einer CSV-Datei gespeichert) werden e-Mail-Nachrichten angefügt und in einem verborgenen Ordner im Postfach des Benutzers gespeichert, der das Formular erstellt hat. Wenn Sie Inhalte aus Formularen in einer PST-Datei exportieren, befinden sich diese Daten im Ordner **ApplicationDataRoot** in einem Unterordner namens mit der folgenden global eindeutigen Identifizierung (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.        <br/> |
|Office 365-Gruppen    <br/>|  E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden in dem Postfach gespeichert, das einer Office 365 Gruppe zugeordnet ist.       <br/> |
|Outlook/Exchange Online<br/>|  E-Mail-Nachrichten, Kalenderelemente, Kontakte (Personen), Notizen und Aufgaben werden im Postfach eines Benutzers gespeichert.       <br/> |
|Personen    <br/> |  Kontakte in der Personen-App (die dieselben Kontakte wie die in Outlook zugänglichen sind) werden im Postfach eines Benutzers gespeichert.      <br/> |
|Klassen Zeitplan     <br/> |   Pläne, die im Klassen Zeitplan erstellt wurden, werden im Postfach der entsprechenden Office 365 Gruppe gespeichert, die beim Erstellen eines neuen Plans bereitgestellt wird. Der Alias für das Gruppenpostfach ist der Name des Plans.      <br/> |
|Skype for Business    <br/>  | Unterhaltungen in Skype for Business werden im Ordner "Unterhaltungsverlauf" im Postfach eines Benutzers gespeichert. Wenn das Postfach eines Teilnehmers einer Skype-Besprechung in das Beweissicherungsverfahren aufgenommen oder einer Aufbewahrungsrichtlinie zugewiesen wurde, werden Dateien, die einer Besprechung zugeordnet sind, im Postfach der Teilnehmer aufbewahrt.         <br/> |
|Sway     <br/> |  Sways werden als HTML-Datei gespeichert, die an eine e-Mail-Nachricht angefügt und in einem verborgenen Ordner im Postfach des Benutzers gespeichert ist, der die Sway erstellt hat. Wenn Sie Inhalte aus Sway in einer PST-Datei exportieren, befinden sich diese Daten im **ApplicationDataRoot** -Ordner in einem Unterordner mit der folgenden GUID) **905fcf26-4eb7-48A0-9ff0-8dcc7194b5ba**.       <br/> |
|Aufgaben    <br/> |  Aufgaben in der Aufgaben-app (bei denen es sich um dieselben Aufgaben handelt, die in Outlook verfügbar sind) werden im Postfach eines Benutzers gespeichert.       <br/> |
|Microsoft Teams    <br/>  |Unterhaltungen, die Teil eines Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Team zugeordnet ist. Unterhaltungen, die Teil der Chat Liste in Microsoft Teams (auch *1 x N-Chats*genannt) sind, werden im Postfach der Benutzer gespeichert, die am Chat teilnehmen. Außerdem werden zusammenfassende Informationen für Besprechungen und Anrufe in einem Teams-Kanal in den Postfächern von Benutzern gespeichert, die sich in die Besprechung oder den Anruf eingewählt haben. <br/> | 
|To-Do  <br/> | Aufgaben (" *to-DOS*", die in "to-do"-Listen gespeichert sind) in der to-do-App werden im Postfach eines Benutzers gespeichert.        <br/> |
||||

> [!NOTE]
> Wenn ein Speicherplatz in einem Postfach (mithilfe von Haltebereichen in eDiscovery-und erweiterte eDiscovery-Fälle) abgelegt wird, werden Inhalte aus Formularen und Sway nicht durch den Haltestatus beibehalten. 