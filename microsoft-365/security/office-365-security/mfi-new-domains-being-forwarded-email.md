---
title: Einblick in E-Mails von neue Domänen, die weitergeleitet werden
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie den Einblick in die E-Mail-Weiterleitung neuer Domänen im E-Mail-Flussdashboard im Security & Compliance Center verwenden, um zu untersuchen, ob ihre Benutzer Nachrichten an externe Domänen weiterleiten, an die noch nie weitergeleitet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029858"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Neue Domänen, die E-Mail-Einblicke im Security & Compliance Center weitergeleitet werden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Es gibt gültige geschäftliche Gründe für die Weiterleitung von E-Mail-Nachrichten an externe Empfänger in bestimmten Domänen. Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an eine Domäne weiterleiten, an die niemand in Ihrer Organisation Nachrichten weitergeleitet hat (eine neue Domäne).

Diese Bedingung weist möglicherweise darauf hin, dass die Benutzerkonten gefährdet sind. Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)

Der **Einblick in die E-Mail-Weiterleitung** neuer Domänen im Security & Compliance [Center](https://protection.office.com) benachrichtigt Sie, wenn Benutzer in Ihrer Organisation Nachrichten an neue Domänen weiterleiten.

Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zurück zum [Weiterleitungsbericht.](view-mail-flow-reports.md#forwarding-report)

![Details-Flyout, das angezeigt wird, nachdem sie auf die E-Mail-Einblicke für neue Domänen geklickt haben](../../media/mfi-new-domains-being-forwarded-details.png)

Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top **insights" auf** "Alle einblicke" &**(** Berichtsdashboard oder ) geklickt \>  <https://protection.office.com/insightdashboard> haben.

Um die automatische Nachrichten weiterleitung an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen. Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
