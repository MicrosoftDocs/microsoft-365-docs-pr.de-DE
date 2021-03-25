---
title: Einblick in E-Mail-Weiterleitung von neuen Benutzern
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratoren erfahren, wie Sie mithilfe der Einblicke in die E-Mail-Weiterleitung neuer Benutzer im Security & Compliance Center untersuchen können, wann Benutzer in ihrer Organisation Nachrichten an neue Domänen weiterleiten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206194"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Neue Benutzer, die E-Mail-Einblicke im Security & Compliance Center weiterleiten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich mit der Weiterleitung von E-Mail-Nachrichten an externe Domänen beginnen.

Der **Einblick in** neue Domänen, die im Security & Compliance [Center](https://protection.office.com) weitergeleitet werden, benachrichtigt Sie, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe Domänen weiterleiten. Diese Bedingung könnte darauf hinweisen, dass zum Erstellen der neuen Benutzer gefährdete Administratorkonten verwendet wurden. Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie [Antworten auf ein gefährdetes E-Mail-Konto](responding-to-a-compromised-email-account.md).

Diese Einsicht wird nur angezeigt, wenn das Problem erkannt wird, und sie wird auf der [Seite Weiterleitungsbericht](view-mail-flow-reports.md#forwarding-report) angezeigt.

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zum Bericht über [Weiterleitungsänderungen,](#forwarding-modifications-report) wie weiter unten in diesem Artikel beschrieben.

![Details-Flyout, das nach dem Klicken auf die E-Mail-Einblicke für neue Benutzer angezeigt wird](../../media/mfi-new-users-forwarding-email-details.png)

Sie können auch zu dieser Detailseite gelangen,  wenn Sie den Einblick auswählen, nachdem Sie im Bereich Top **insights & (** **Reports** Dashboard or ) auf Alle anzeigen geklickt \>  <https://protection.office.com/insightdashboard> haben.

Sie können auf den Link **Bericht** mit Einblicken zugeordneten Bericht sehen klicken, um zum Bericht über **Weiterleitungsänderungen** zu wechseln, wie im nächsten Abschnitt beschrieben.

## <a name="forwarding-modifications-report"></a>Bericht über Weiterleitungsänderungen

Der **Bericht über Weiterleitungsänderungen** enthält Details zu Nachrichten, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:

- Neu erstellte Konten, die Nachrichten an externe Domänen weiterleiten.
- Konten, die Nachrichten an externe Domänen weiterleiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.

Diese Arten von weitergeleiteten Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf gefährdete Konten hinweisen.

Der Bericht enthält Daten für bis zu 90 Tage. Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt.

Dieser Bericht ist nicht direkt [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard oder im Berichtsdashboard [verfügbar.](view-mail-flow-reports.md) Zusätzlich zum Klicken auf den Link Bericht  mit **Einblicken** im Link Neue Benutzer, die E-Mail-Einblicke weiterleiten, erhalten Sie zu dem Bericht die folgenden Informationen:

- Klicken Sie auf den **Link Weiterleitungsbenachrichtigungen bericht** in den Details der [Neuen Domänen, die E-Mail-Einblick weitergeleitet werden.](mfi-new-domains-being-forwarded-email.md)
- Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Berichtsansicht für den Bericht "Weiterleitungsänderungen"

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für: Neue Weiterleitungsbenutzer**:

  ![Ansicht "Neue Weiterleitungsbenutzer" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Anzeigen von Daten für: Neue Weiterleitungsdomänen**:

  ![Ansicht "Neue weitergeleitete Domänen" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detailtabelle für den Bericht "Weiterleitungsänderungen"

Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:

- **Anzeigen von Daten für: Neue Weiterleitungsbenutzer**:

  - **Name**: Die E-Mail-Adresse des Absenders.
  - **Weiterleitungstyp**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Weiterleitungsdatum**

- **Anzeigen von Daten für: Neue Weiterleitungsdomänen**:

  - **Name**: Die E-Mail-Domäne des Absenders.
  - **Weiterleitungstyp**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Weiterleitungsdatum**

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Wenn Sie eine Zeile aus  der Tabelle auswählen, wird ein Details-Flyout mit den folgenden Informationen angezeigt:

- **Name**: Dies ist entweder die E-Mail-Adresse des Absenders (unter Anzeigen von Daten **für:** Ansicht Neue Weiterleitungsbenutzer) oder die E-Mail-Domäne des Absenders (unter Anzeigen von Daten für: Ansicht Neue **Weiterleitungsdomänen).**
- **Weiterleitungstyp**
- **Empfänger**
- **Details**
- **Count**
- **Anfangstermin**
- **Empfehlung**: Klicken Sie hier auf den Link, um den Benutzer im Microsoft 365 Admin Center zu verwalten.

![Details flyout aus der Detailtabelle der Ansicht Neue Weiterleitungsbenutzer im Bericht Weiterleitungsänderungen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).
