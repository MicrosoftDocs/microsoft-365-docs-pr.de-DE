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
description: Administratoren erfahren, wie Sie mithilfe der Neuen Domänen, die E-Mail-Einblicke erhalten, im Nachrichtenflussdashboard im Security & Compliance Center untersuchen, wann ihre Benutzer Nachrichten an externe Domänen weiterleiten, die noch nie weitergeleitet wurden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929348"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Neue Domänen, die E-Mail-Einblicke im Security & Compliance Center erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Es gibt gültige geschäftliche Gründe für die Weiterleitung von E-Mail-Nachrichten an externe Empfänger in bestimmten Domänen. Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich mit der Weiterleitung von Nachrichten an eine Domäne beginnen, an die in Ihrer Organisation niemals Nachrichten weitergeleitet wurden (eine neue Domäne).

Diese Bedingung kann darauf hinweisen, dass die Benutzerkonten gefährdet sind. Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie [Antworten auf ein gefährdetes E-Mail-Konto](responding-to-a-compromised-email-account.md).

Der **E-Mail-Einblick** in neue Domänen im [Security & Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn Benutzer in Ihrer Organisation Nachrichten an neue Domänen weiterleiten.

Diese Einsicht wird nur angezeigt, wenn das Problem erkannt wird, und sie wird auf der [Seite Weiterleitungsbericht](view-mail-flow-reports.md#forwarding-report) angezeigt.

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zurück zum [Weiterleitungsbericht.](view-mail-flow-reports.md#forwarding-report)

![Details-Flyout, das angezeigt wird, nachdem Sie auf die Neue Domänen geklickt haben, die E-Mail weitergeleitet werden](../../media/mfi-new-domains-being-forwarded-details.png)

Sie können auch zu dieser Detailseite gelangen,  wenn Sie den Einblick auswählen, nachdem Sie im Bereich Top **insights & (** **Reports** Dashboard or ) auf Alle anzeigen geklickt \>  <https://protection.office.com/insightdashboard> haben.

Um die automatische Nachrichten weiterleitung an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen. Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).