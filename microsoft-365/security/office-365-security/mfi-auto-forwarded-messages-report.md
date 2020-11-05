---
title: Einblick in automatisch weitergeleitete Nachrichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratoren können sich über den Bericht über automatisch weitergeleitete Nachrichten im Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920596"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Einblicke automatisch weitergeleiteter Nachrichten im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Die automatisch **weitergeleiteten Nachrichten** Insight im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten an, die von Ihrer Organisation automatisch an Empfänger in externen domänenweiter geleitet werden.

![Widget "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details zu automatisch weitergeleiteten Nachrichten

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout-Bereich angezeigt, der weitere Informationen zu den automatisch weitergeleiteten Nachrichten zeigt:

- **Nachrichten werden nach Weiterleitungs Methoden automatisch weitergeleitet** :

  - **Nachrichtenfluss Regeln**
  - **Nach Posteingangsregeln**
  - **Durch SMTP-Weiterleitung** : Diese Methode gibt die automatische Weiterleitung an, die Administratoren in einem Postfach konfigurieren können, wie unter [configure e-Mail-Weiterleitung für ein Postfach](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)beschrieben.
  - Einen Link zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report) für weitere Details.

- **Automatisch weitergeleitete Nachrichten nach Domänen und Benutzern** :

  - **Top 5-domänenweiter geleitet an**
  - **Neue Domänen (letzte Woche)**
  - **Die ersten 5 Weiterleitungs Benutzer**
  - **Neue Benutzer (letzte Woche)**
  - Einen Link zum [Weiterleitungs Änderungsbericht](mfi-new-users-forwarding-email.md#forwarding-modifications-report) für weitere Details.

![Details-Flyout für den Bericht "automatisch weitergeleitete Nachrichten" im Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insights

Basierend auf den Berichtsdaten werden zwei Erkenntnisse generiert:

- [Neue Benutzer, die e-Mails weiterleiten](mfi-new-users-forwarding-email.md)
- [Neue Domänen, die e-Mail weitergeleitet werden](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Weitere Informationen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
