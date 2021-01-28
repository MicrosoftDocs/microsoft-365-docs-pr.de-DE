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
description: Administratoren können erfahren, wie Sie mithilfe des Einblicks "Neue Benutzer, die E-Mails weiterleiten" im Security & Compliance Center untersuchen können, wenn Benutzer in ihrer Organisation Nachrichten an neue Domänen weiterleiten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029870"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Neue Benutzer, die E-Mail-Einblicke im Security & Compliance Center weiterleiten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich beginnen, E-Mail-Nachrichten an externe Domänen weiter zu senden.

Die **neuen Domänen, die** E-Mail-Einblicke im Security & Compliance [Center](https://protection.office.com) erhalten, benachrichtigen Sie, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe Domänen weiterleiten. Diese Bedingung könnte darauf hinweisen, dass zum Erstellen der neuen Benutzer gefährdete Administratorkonten verwendet wurden. Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)

Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zum Bericht über [Weiterleitungsänderungen,](#forwarding-modifications-report) wie weiter unten in diesem Artikel beschrieben.

![Details-Flyout, das angezeigt wird, nachdem sie auf den Einblick in die E-Mail-Weiterleitung durch neue Benutzer geklickt haben](../../media/mfi-new-users-forwarding-email-details.png)

Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top insights" **&** **(** Berichtsdashboard oder ) auf "Alle anzeigen" geklickt \>  haben. <https://protection.office.com/insightdashboard>

Sie können auf den Link **"Bericht** mit Einblicken sehen" klicken, um zum Bericht über **Weiterleitungsänderungen** zu wechseln, wie im nächsten Abschnitt beschrieben.

## <a name="forwarding-modifications-report"></a>Bericht über Weiterleitungsänderungen

Der **Bericht über Weiterleitungsänderungen enthält** Details zu Nachrichten, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:

- Neu erstellte Konten, die Nachrichten an externe Domänen weiterleiten.
- Konten, die Nachrichten an externe Domänen weiterleiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.

Diese Art von weitergeleiteten Nachrichten kann ein Sicherheits- oder Compliancerisiko darstellen und auf gefährdete Konten hinweisen.

Der Bericht enthält Daten für bis zu 90 Tage. Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt.

Dieser Bericht ist nicht direkt [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard oder im [Berichtsdashboard verfügbar.](view-mail-flow-reports.md) Zusätzlich zum Klicken  auf den Link "Bericht  mit Einblicken sehen" im E-Mail-Einblick "Neue Benutzer" erhalten Sie folgenden Zugriff auf den Bericht:

- Klicken Auf den **Link "Weiterleitungsbenachrichtigungen melden"** in den Details der neuen Domänen, die weitergeleitet werden, E-Mail-Einblick. [](mfi-new-domains-being-forwarded-email.md)
- Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Berichtsansicht für den Bericht über Weiterleitungsänderungen

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**

  ![Ansicht "Neue Weiterleitungsbenutzer" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Anzeigen von Daten für: Neue Weiterleitungsdomänen:**

  ![Ansicht "Neue weitergeleitete Domänen" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detailtabelle für den Bericht "Weiterleitungsänderungen"

Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:

- **Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**

  - **Name:** Die E-Mail-Adresse des Absenders.
  - **Weiterleitungstyp**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Weiterleitungsdatum**

- **Daten anzeigen für: Neue Weiterleitungsdomänen:**

  - **Name:** Die E-Mail-Domäne des Absenders.
  - **Weiterleitungstyp**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Weiterleitungsdatum**

Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Wenn Sie eine Zeile aus der Tabelle auswählen, wird ein **Flyout "Details"** mit den folgenden Informationen angezeigt:

- **Name:** Dies ist entweder die E-Mail-Adresse des Absenders (aus Ansicht "Daten anzeigen **für:** Ansicht "Neue Weiterleitungsbenutzer") oder die E-Mail-Domäne des Absenders (aus Ansicht "Daten anzeigen für: Neue **Weiterleitungsdomänen").**
- **Weiterleitungstyp**
- **Empfänger**
- **Details**
- **Count**
- **Anfangstermin**
- **Empfehlung:** Von hier aus können Sie auf den Link klicken, um den Benutzer im Microsoft 365 Admin Center zu verwalten.

![Details flyout from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
