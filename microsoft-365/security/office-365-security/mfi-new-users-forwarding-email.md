---
title: Einblick in E-Mail-Weiterleitung von neuen Benutzern
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
description: Administratoren erfahren, wie Sie mit den neuen Benutzern, die e-Mail-Einblicke im Security & Compliance Center weiterleiten, untersuchen können, wann Benutzer in Ihrer Organisation Nachrichten an neue domänenweiter leiten.
ms.openlocfilehash: 22bbd762b221fae151a489aa1e9485dfc7baf06a
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357273"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Neue Benutzer, die e-Mail-Insight im Security & Compliance Center weiterleiten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich mit der Weiterleitung von e-Mail-Nachrichten an externe Domänen beginnen.

Die **neuen Domänen, die als e-Mail-Insight weitergeleitet** werden, werden in der [Security & Compliance Center](https://protection.office.com) benachrichtigt, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe domänenweiter leiten. Diese Bedingung kann darauf hindeuten, dass kompromittierte Administratorkonten verwendet wurden, um die neuen Benutzer zu erstellen. Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).

Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, einschließlich eines Links zum [Weiterleiten von Änderungs Berichten](#forwarding-modifications-report) wie weiter unten in diesem Thema beschrieben.

![Details-Flyout, das angezeigt wird, nachdem Sie auf die neuen Benutzer weiterleiten von e-Mail Insight geklickt haben](../../media/mfi-new-users-forwarding-email-details.png)

Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.

Sie können auf den Link **Bericht mit Insight zugeordnet sehen** klicken, um zum **weiter Leitungs Änderungsbericht** zu wechseln, wie im nächsten Abschnitt beschrieben.

## <a name="forwarding-modifications-report"></a>Änderungsbericht wird weitergeleitet

Der **Bericht zum Weiterleiten von Änderungen** zeigt Details zu Nachrichten an, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:

- Neu erstellte Konten, die Nachrichten an externe domänenweiter leiten.
- Konten, die Nachrichten an externe domänenweiter leiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.

Diese Typen von weitergeleiteten Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf kompromittierte Konten hindeuten.

Der Bericht enthält Daten für bis zu 90 Tage. Standardmäßig zeigt der Berichtdaten für die letzten 7 Tage an.

Dieser Bericht ist nicht direkt im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) oder im [Dashboard Berichte](view-mail-flow-reports.md)verfügbar. Neben dem Klicken auf den Link **Bericht mit Insight zugeordnet** in den **neuen Benutzern, die e-Mail-** Einblicke weiterleiten, gelangen Sie in den Bericht über die folgenden Informationen:

- Klicken Sie auf den Link **Weiterleitungsbenachrichtigungen weiterleiten** in den Details der [neuen Domänen, die in e-Mail-Insight weitergeleitet werden](mfi-new-domains-being-forwarded-email.md).
- Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Berichtsansicht für den Weiterleitungs Änderungsbericht

Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:

- **Daten anzeigen für: neue Weiterleitungs Benutzer**:

  ![Ansicht "neue weiterleitende Benutzer" im Bericht "Weiterleiten von Änderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Daten anzeigen für: neue Weiterleitungs Domänen**:

  ![Ansicht "neu weitergeleitete Domänen" im Bericht zum Weiterleiten von Änderungen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detailtabellen Ansicht für den Weiterleitungs Änderungsbericht

Wenn Sie auf **Detailtabelle anzeigen** klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:

- **Daten anzeigen für: neue Weiterleitungs Benutzer**:

  - **Name**: die e-Mail-Adresse des Absenders.
  - **Weiterleitender Typ**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Termin Datum**

- **Daten anzeigen für: neue Weiterleitungs Domänen**:

  - **Name**: die e-Mail-Domäne des Absenders.
  - **Weiterleitender Typ**
  - **Empfängeradresse**
  - **Details**
  - **Count**
  - **Erstes Termin Datum**

Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.

Wenn Sie eine Zeile aus der Tabelle auswählen, wird ein **Detail** Flyout mit den folgenden Informationen angezeigt:

- **Name**: Dies ist entweder die e-Mail-Adresse des Absenders (von **Daten anzeigen für: neue Weiterleitungs Benutzer** anzeigen) oder die e-Mail-Domäne des Absenders (aus **Daten anzeigen für: neue Weiterleitungs Domänen** -Ansicht).
- **Weiterleitender Typ**
- **Empfänger**
- **Details**
- **Count**
- **Anfangstermin**
- **Empfehlung**: von hier aus können Sie auf den Link klicken, um den Benutzer im Microsoft 365 Admin Center zu verwalten.

![Details-Flyout aus der Detailtabelle der Ansicht neue weiterleitende Benutzer im Bericht zum Weiterleiten von Änderungen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
