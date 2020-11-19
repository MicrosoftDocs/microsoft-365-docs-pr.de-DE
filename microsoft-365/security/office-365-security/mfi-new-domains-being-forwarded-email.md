---
title: Einblick in E-Mails von neue Domänen, die weitergeleitet werden
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie die neuen Domänen, die als e-Mail-Insight weitergeleitet werden, im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um zu untersuchen, wann Ihre Benutzer Nachrichten an externe domänenweiter leiten, an die noch nie weitergeleitet wurden.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356943"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Neue Domänen werden weitergeleitet e-Mail-Insight im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Es gibt gültige geschäftliche Gründe für die Weiterleitung von e-Mail-Nachrichten an externe Empfänger in bestimmten Domänen. Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an eine Domäne weiterleiten, in der niemand in Ihrer Organisation Nachrichten an (eine neue Domäne) weitergeleitet hat.

Diese Bedingung deutet möglicherweise darauf hin, dass die Benutzerkonten gefährdet sind. Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).

Die **neuen Domänen, die als e-Mail-Insight weitergeleitet** werden, werden vom [Security & Compliance Center](https://protection.office.com) benachrichtigt, wenn Benutzer in Ihrer Organisation Nachrichten an neue domänenweiter leiten.

Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, darunter einen Link zurück zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report).

![Details-Flyout, das nach dem Klicken auf die weiterzuleitenden neuen Domänen angezeigt wird e-Mail Insight](../../media/mfi-new-domains-being-forwarded-details.png)

Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.

Um die automatische Weiterleitung von Nachrichten an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen. Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
