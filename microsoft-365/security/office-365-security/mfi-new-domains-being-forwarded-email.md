---
title: Neue Domänen werden weitergeleitet e-Mail Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie die neuen Domänen, die als e-Mail-Insight weitergeleitet werden, in der modernen Exchange-Verwaltungskonsole verwenden, um zu untersuchen, wann Benutzer in Ihrer Organisation Nachrichten an externe domänenweiter leiten, an die noch nie weitergeleitet wurde.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578394"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Neue Domänen werden weitergeleitet e-Mail-Insight im Security & Compliance Center

Obwohl Sie möglicherweise über gültige geschäftliche Gründe für die Weiterleitung von e-Mail-Nachrichten an externe Empfänger in bestimmten Domänen verfügen, ist es verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an externe domänenweiter leiten und niemand in der Organisation zuvor Nachrichten an diese domänenweiter geleitet hat (neue Domänen). Diese Bedingung kann darauf hindeuten, dass die Benutzerkonten kompromittiert sind. Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

Die **neuen Domänen, die in e-Mail-Insight weitergeleitet** werden, erhalten eine Benachrichtigung, wenn Benutzer in Ihrer Organisation Nachrichten an neue domänenweiter leiten.

Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.

![Neue Domänen werden weitergeleitet e-Mail Insight](../../media/mfi-new-domains-being-forwarded.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, darunter einen Link zurück zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report).

![Details-Flyout, das nach dem Klicken auf die weiterzuleitenden neuen Domänen angezeigt wird e-Mail Insight](../../media/mfi-new-domains-being-forwarded-details.png)

Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.

Um die automatische Weiterleitung von Nachrichten an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen. Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
