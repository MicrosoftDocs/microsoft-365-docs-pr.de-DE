---
title: Einblick in automatisch weitergeleitete Nachrichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206404"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Einblicke in automatisch weitergeleitete Nachrichten im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Der **Einblick** in automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die automatisch von Ihrer Organisation an Empfänger in externen Domänen weitergeleitet werden. [](mail-flow-insights-v2.md)

![Widget für automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details zu automatisch weitergeleiteten Nachrichten

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyoutbereich angezeigt, der weitere Informationen zu den automatisch weitergeleiteten Nachrichten enthält:

- **Automatisch weitergeleitete Nachrichten durch Weiterleitungsmethoden**:

  - **Nach Nachrichtenflussregeln**
  - **Nach Posteingangsregeln**
  - **By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Ein Link zum [Weiterleitungsbericht für](view-mail-flow-reports.md#forwarding-report) weitere Details.

- **Automatisch weitergeleitete Nachrichten von Domänen und Benutzern**:

  - **Die 5 am besten weitergeleiteten Domänen**
  - **Neue Domänen (letzte Woche)**
  - **Die 5 besten Weiterleitungsbenutzer**
  - **Neue Benutzer (letzte Woche)**
  - Ein Link zum [Bericht "Weiterleitungsänderungen" für](mfi-new-users-forwarding-email.md#forwarding-modifications-report) weitere Details.

![Details zum Flyout für den Bericht über automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Einblicke

Basierend auf den Berichtsdaten werden zwei Einblicke generiert:

- [Neue Benutzer, die E-Mails weiterleiten](mfi-new-users-forwarding-email.md)
- [Neue Domänen, die E-Mails weitergeleitet werden](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).