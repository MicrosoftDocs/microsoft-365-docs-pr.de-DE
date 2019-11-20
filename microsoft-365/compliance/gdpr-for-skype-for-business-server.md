---
title: DSGVO für Skype for Business Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen in lokalen Installationen von Skype for Business Server und Lync Server umgehen.
ms.openlocfilehash: fb3789a6835a367d415e5c32eeec043add150724
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749767"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a>DSGVO für Skype for Business Server und Lync Server

Die meisten Daten von Skype for Business Server und Lync Server werden in Exchange Server gespeichert. Dazu gehören:

-   Aufgezeichnete Unterhaltungen

-   Voicemail-Benachrichtigungen und Transkriptionen

-   Besprechungseinladungen

Verwenden Sie die für [DSGVO für Exchange Server](gdpr-for-exchange-server.md) erläuterten Verfahren, um diese Arten von Daten für DSGVO-Anfragen zu finden, zu exportieren oder zu löschen.

Kontaktlisten werden in der SQL Server-Datenbank gespeichert. Sie können auf folgende Weise exportiert werden:

-   Endbenutzer selbst können die Kontakte exportieren, indem sie mit der rechten Maustaste auf den Gruppenkopf klicken und "Kopieren" auswählen. Dadurch werden alle Kontakte in dieser Gruppe in die Zwischenablage kopiert und können anschließend in jede beliebige Anwendung eingefügt werden.

-   Mit dem Cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) können Sie diese Daten exportieren.

In Besprechungen hochgeladene Inhalte (z. B. PowerPoint-Dateien oder Handzettel) oder in einer Besprechung generierte Inhalte (z. B. Whiteboard, Umfragen oder Fragen und Antworten) werden im Filer gespeichert. Diese Inhalte können auch exportiert werden, wenn sich Endbenutzer wieder bei einer Besprechung anmelden, die noch nicht abgelaufen ist, und hochgeladene Inhalte herunterladen oder im Falle von generierten Inhalten Screenshots erstellen.

MeetNow-Besprechungen, die sich nicht in Exchange-Kalender und Kontaktliste befinden, und Kontaktrechte (Familie, Kollegen usw.) sind in der Benutzerdatenbank. In Lync Server 2013 und höher können Sie diese Daten mit dem Cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) exportieren.
