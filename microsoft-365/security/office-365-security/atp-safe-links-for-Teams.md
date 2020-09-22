---
title: ATP-sichere Links für Teams, safelinks, sichere Links, blockieren schädlicher Links, Office 365 ATP, sichere Links für Teams, Beenden von Benutzern beim Klicken auf ungültige Links, böswillige Links
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
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198751"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Sichere Links in Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Dieses Feature befindet sich in der **öffentlichen Vorschau** für Kunden im Microsoft Teams Technology Adoption Program (Tap) zum 28. Februar 2020. Dieser Hinweis wird aus dem Artikel entfernt, wenn sichere Links für Teams häufiger verfügbar sind.

Microsoft Teams, eine in Microsoft cloudbasierten Anwendung zur Verwaltung ihrer Arbeit, verwendet bereits sichere Anlagen (für Office 365), hat aber jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens. Unabhängig davon, ob Sie Chats, Gruppenchats, Kanäle oder Registerkarten verwenden, wenn Sie über ein Abonnement für Office 365 ATP verfügen, können Sie diese Sicherheitsmaßnahme aktivieren und verwenden. Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

So funktioniert es:

1. Wenn Sie die Teams-Anwendung starten, überprüft Microsoft 365, um sicherzustellen, dass der Benutzer zu einer Organisation gehört, die über Office 365 ATP verfügt, und dass der Benutzer Teil einer aktiven Richtlinie für sichere Links ist, deren Schutz für Microsoft Teams aktiviert ist.

2. Wenn dies der Fall ist, werden URLs zum Zeitpunkt der Klickfunktion in Chats, Gruppenchats, Kanälen und Registerkarten für diesen Benutzer überprüft.

## <a name="what-will-users-experience"></a>Was werden Benutzer erfahren?

Für alle geschützten Benutzer wird diese Erfahrung mit gefährlichen URLs verwendet:

- Wenn auf den Link aus einer Microsoft Teams-Unterhaltung, einem Gruppenchat oder aus Kanälen geklickt wurde, wird eine Seite im Standardbrowser gerendert. Wenn auf der Registerkarte angeheftet auf den Link geklickt wurde, wird die Seite auf der Benutzeroberfläche von Teams auf dieser Registerkarte angezeigt, und die Option zum Öffnen im Browser wird aus Sicherheitsgründen deaktiviert.

- Dieser Benutzer wird vom Fortfahren mit der URL-Website blockiert.

Wenn der Benutzer, der den Link gesendet hat, nicht durch Office 365 ATP geschützt ist, kann er auf die URL auf seinem Computer klicken und die Problem Website beheben. Auf diese Weise ist es für Administratoren doppelt wichtig, sich darüber bewusst zu sein, wer Ihre geschützten Benutzer sind und sein sollten.

![Eine sichere Links für Teams-Seite, die einen bösartigen Link meldet und die Übertragung auf die Seite blockiert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Wenn Sie auf dieser Seite in Microsoft Teams auf die Schaltfläche " *zurück* " klicken, wird diese geschlossen (oder es kann zu einer leeren Seite führen, wenn Benutzer schließen können). Durch Klicken auf den Link wird jedoch erneut die Zuverlässigkeit der Website bewertet, sodass diese Seite wieder angezeigt wird.

> [!NOTE]
> Einige Microsoft 365-Administratoren aktivieren die Meldung **Continue Anyway** auf der Seite blockieren. Wenn jedoch sichere Links den Ruf einer Website misst und diese nicht mehr zur Verfügung stehen, sollte keine weitere durch Klick erfolgen. Es wird nicht empfohlen, dass Benutzer Sicherheitsmaßnahmen umgehen. Wägen Sie dies bitte auf ihre Überlegungen ab, bevor Sie Continue trotzdem aktivieren.
