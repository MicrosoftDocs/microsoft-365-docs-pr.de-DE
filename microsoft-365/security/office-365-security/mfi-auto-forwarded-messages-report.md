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
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Dashboard für den Nachrichtenfluss im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290633"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Einblick in automatisch weitergeleitete Nachrichten im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Der **Einblick** in automatisch weitergeleitete Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die automatisch von Ihrer Organisation an Empfänger in externen Domänen weitergeleitet werden. [](mail-flow-insights-v2.md)

![Widget für automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details zu automatisch weitergeleiteten Nachrichten

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyoutbereich mit weiteren Informationen zu den automatisch weitergeleiteten Nachrichten angezeigt:

- **Automatisch weitergeleitete Nachrichten durch Weiterleitungsmethoden:**

  - **Nach Nachrichtenflussregeln**
  - **Nach Posteingangsregeln**
  - **By SMTP forwarding:** This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Ein Link zum [Weiterleitungsbericht für](view-mail-flow-reports.md#forwarding-report) weitere Details.

- **Automatisch weitergeleitete Nachrichten von Domänen und Benutzern:**

  - **Die 5 am besten weitergeleiteten Domänen**
  - **Neue Domänen (letzte Woche)**
  - **Top-5-Weiterleitungsbenutzer**
  - **Neue Benutzer (letzte Woche)**
  - Eine Verknüpfung zum [Bericht über Weiterleitungsänderungen,](mfi-new-users-forwarding-email.md#forwarding-modifications-report) um weitere Details zu erhalten.

![Detailf flyout für den Bericht über automatisch weitergeleitete Nachrichten im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Einblicke

Basierend auf den Berichtsdaten werden zwei Einblicke generiert:

- [Neue Benutzer, die E-Mails weiterleiten](mfi-new-users-forwarding-email.md)
- [Neue Domänen, die per E-Mail weitergeleitet werden](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
