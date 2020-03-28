---
title: Office 365 ATP-sichere Links für Teams, safelinks, sichere Links, blockieren schädlicher Links, Office 365 ATP, sichere Links für Teams, Beenden von Benutzern beim Klicken auf ungültige Links, böswillige Links
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams haben jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens. Unabhängig davon, ob Sie Chats mit 1-zu-1-Chats, zwischen Gruppen oder in Kanälen und Registerkarten verwenden, wenn Sie ein Abonnement für Office 365 ATP haben, haben Sie die Möglichkeit, dieses Sicherheitsfeature zu aktivieren und zu verwenden.
ms.openlocfilehash: 864b211a1f007a0f6bde83da12b61362b53bf041
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030140"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>Office 365 sichere Links in Microsoft Teams

> [!IMPORTANT]
> Dieses Feature befindet sich in der **öffentlichen Vorschau** für Kunden im Microsoft Teams Technology Adoption Program (Tap) zum 28. Februar 2020. Dieser Hinweis wird aus dem Artikel entfernt, wenn sichere Links für Teams häufiger verfügbar sind.

Microsoft Teams, eine Office 365 Cloud-basierte Anwendung zur Verwaltung ihrer Arbeit, verwendet bereits sichere Anlagen (für Office 365), hat aber jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens. Unabhängig davon, ob Chats mit 1-zu-1-Chats, zwischen Gruppen oder in Kanälen und Registerkarten verwendet werden, wenn Sie ein Abonnement für Office 365 ATP haben, können Sie diese Sicherheitsmaßnahme aktivieren und verwenden.

So funktioniert es: 

1. Wenn Sie die Teams-Anwendung starten, überprüfen Office 365, ob der Benutzer einer Organisation angehört, die über Office 365 ATP verfügt, und dass der Benutzer Teil einer aktiven Richtlinie für sichere Links ist, deren Schutz für Microsoft Teams aktiviert ist.

2. Wenn dies der Fall ist, werden URLs zum Zeitpunkt der Klickfunktion in Chats, Gruppenchats, Kanälen und Registerkarten für diesen Benutzer überprüft.
 
## <a name="what-will-users-experience"></a>Was werden Benutzer erfahren? 

Für alle geschützten Benutzer wird diese Erfahrung mit gefährlichen URLs verwendet: 

- Wenn auf den Link aus einer Microsoft Teams-Unterhaltung, einem Gruppenchat oder aus Kanälen geklickt wurde, wird eine Seite im Standardbrowser gerendert. Wenn auf der Registerkarte angeheftet auf den Link geklickt wurde, wird die Seite auf der Benutzeroberfläche von Teams auf dieser Registerkarte angezeigt, und die Option zum Öffnen im Browser wird aus Sicherheitsgründen deaktiviert.

- Dieser Benutzer wird vom Fortfahren mit der URL-Website blockiert.

Wenn der Benutzer, der den Link gesendet hat, nicht durch Office 365 ATP geschützt ist, kann er auf die URL auf seinem Computer klicken und die Problem Website beheben. Auf diese Weise ist es für Office 365 Administratoren doppelt wichtig, sich darüber bewusst zu sein, wer Ihre geschützten Benutzer sind und sein sollten.

![Eine sichere Links für Teams-Seite, die einen bösartigen Link meldet und die Übertragung auf die Seite blockiert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Wenn Sie auf dieser Seite in Microsoft Teams auf die Schaltfläche " *zurück* " klicken, wird diese geschlossen (oder es kann zu einer leeren Seite führen, wenn Benutzer schließen können). Durch Klicken auf den Link wird jedoch erneut die Zuverlässigkeit der Website bewertet, sodass diese Seite wieder angezeigt wird.

> [!NOTE]
>Einige Office 365 Administratoren aktivieren die Meldung **Continue Anyway** auf der Seite blockieren. Wenn jedoch sichere Links den Ruf einer Website misst und diese nicht mehr zur Verfügung stehen, sollte keine weitere durch Klick erfolgen. Es wird nicht empfohlen, dass Benutzer Sicherheitsmaßnahmen umgehen. Wägen Sie dies bitte auf ihre Überlegungen ab, bevor Sie Continue trotzdem aktivieren. 

