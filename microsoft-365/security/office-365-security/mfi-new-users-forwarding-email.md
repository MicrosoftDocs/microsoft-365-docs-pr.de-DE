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
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660017"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="823e4-103">Neue Benutzer, die e-Mail-Insight im Security & Compliance Center weiterleiten</span><span class="sxs-lookup"><span data-stu-id="823e4-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="823e4-104">Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich mit der Weiterleitung von e-Mail-Nachrichten an externe Domänen beginnen.</span><span class="sxs-lookup"><span data-stu-id="823e4-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="823e4-105">Die **neuen Domänen, die als e-Mail-Insight weitergeleitet** werden, werden in der [Security & Compliance Center](https://protection.office.com) benachrichtigt, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe domänenweiter leiten.</span><span class="sxs-lookup"><span data-stu-id="823e4-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="823e4-106">Diese Bedingung kann darauf hindeuten, dass kompromittierte Administratorkonten verwendet wurden, um die neuen Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="823e4-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="823e4-107">Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="823e4-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="823e4-108">Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="823e4-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="823e4-110">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, einschließlich eines Links zum [Weiterleiten von Änderungs Berichten](#forwarding-modifications-report) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="823e4-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf die neuen Benutzer weiterleiten von e-Mail Insight geklickt haben](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="823e4-112">Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.</span><span class="sxs-lookup"><span data-stu-id="823e4-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="823e4-113">Sie können auf den Link **Bericht mit Insight zugeordnet sehen** klicken, um zum **weiter Leitungs Änderungsbericht** zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="823e4-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="823e4-114">Änderungsbericht wird weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="823e4-114">Forwarding modifications report</span></span>

<span data-ttu-id="823e4-115">Der **Bericht zum Weiterleiten von Änderungen** zeigt Details zu Nachrichten an, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="823e4-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="823e4-116">Neu erstellte Konten, die Nachrichten an externe domänenweiter leiten.</span><span class="sxs-lookup"><span data-stu-id="823e4-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="823e4-117">Konten, die Nachrichten an externe domänenweiter leiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="823e4-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="823e4-118">Diese Typen von weitergeleiteten Nachrichten können ein Sicherheits-oder Konformitäts Risiko darstellen und möglicherweise auf kompromittierte Konten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="823e4-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="823e4-119">Der Bericht enthält Daten für bis zu 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="823e4-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="823e4-120">Standardmäßig zeigt der Berichtdaten für die letzten 7 Tage an.</span><span class="sxs-lookup"><span data-stu-id="823e4-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="823e4-121">Dieser Bericht ist nicht direkt im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) oder im [Dashboard Berichte](view-mail-flow-reports.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="823e4-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="823e4-122">Neben dem Klicken auf den Link **Bericht mit Insight zugeordnet** in den **neuen Benutzern, die e-Mail-** Einblicke weiterleiten, gelangen Sie in den Bericht über die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="823e4-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="823e4-123">Klicken Sie auf den Link **Weiterleitungsbenachrichtigungen weiterleiten** in den Details der [neuen Domänen, die in e-Mail-Insight weitergeleitet werden](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="823e4-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="823e4-124">Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="823e4-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="823e4-125">Berichtsansicht für den Weiterleitungs Änderungsbericht</span><span class="sxs-lookup"><span data-stu-id="823e4-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="823e4-126">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="823e4-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="823e4-127">**Daten anzeigen für: neue Weiterleitungs Benutzer**:</span><span class="sxs-lookup"><span data-stu-id="823e4-127">**Show data for: New forwarding users**:</span></span>

  ![Ansicht "neue weiterleitende Benutzer" im Bericht "Weiterleiten von Änderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="823e4-129">**Daten anzeigen für: neue Weiterleitungs Domänen**:</span><span class="sxs-lookup"><span data-stu-id="823e4-129">**Show data for: New forwarding domains**:</span></span>

  ![Ansicht "neu weitergeleitete Domänen" im Bericht zum Weiterleiten von Änderungen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="823e4-131">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="823e4-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="823e4-132">Detailtabellen Ansicht für den Weiterleitungs Änderungsbericht</span><span class="sxs-lookup"><span data-stu-id="823e4-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="823e4-133">Wenn Sie auf **Detailtabelle anzeigen** klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="823e4-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="823e4-134">**Daten anzeigen für: neue Weiterleitungs Benutzer**:</span><span class="sxs-lookup"><span data-stu-id="823e4-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="823e4-135">**Name**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="823e4-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="823e4-136">**Weiterleitender Typ**</span><span class="sxs-lookup"><span data-stu-id="823e4-136">**Forwarding type**</span></span>
  - <span data-ttu-id="823e4-137">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="823e4-137">**Recipient address**</span></span>
  - <span data-ttu-id="823e4-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="823e4-138">**Details**</span></span>
  - <span data-ttu-id="823e4-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="823e4-139">**Count**</span></span>
  - <span data-ttu-id="823e4-140">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="823e4-140">**First forward date**</span></span>

- <span data-ttu-id="823e4-141">**Daten anzeigen für: neue Weiterleitungs Domänen**:</span><span class="sxs-lookup"><span data-stu-id="823e4-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="823e4-142">**Name**: die e-Mail-Domäne des Absenders.</span><span class="sxs-lookup"><span data-stu-id="823e4-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="823e4-143">**Weiterleitender Typ**</span><span class="sxs-lookup"><span data-stu-id="823e4-143">**Forwarding type**</span></span>
  - <span data-ttu-id="823e4-144">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="823e4-144">**Recipient address**</span></span>
  - <span data-ttu-id="823e4-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="823e4-145">**Details**</span></span>
  - <span data-ttu-id="823e4-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="823e4-146">**Count**</span></span>
  - <span data-ttu-id="823e4-147">**Erstes Termin Datum**</span><span class="sxs-lookup"><span data-stu-id="823e4-147">**First forward date**</span></span>

<span data-ttu-id="823e4-148">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="823e4-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="823e4-149">Wenn Sie eine Zeile aus der Tabelle auswählen, wird ein **Detail** Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="823e4-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="823e4-150">**Name**: Dies ist entweder die e-Mail-Adresse des Absenders (von **Daten anzeigen für: neue Weiterleitungs Benutzer** anzeigen) oder die e-Mail-Domäne des Absenders (aus **Daten anzeigen für: neue Weiterleitungs Domänen** -Ansicht).</span><span class="sxs-lookup"><span data-stu-id="823e4-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="823e4-151">**Weiterleitender Typ**</span><span class="sxs-lookup"><span data-stu-id="823e4-151">**Forwarding type**</span></span>
- <span data-ttu-id="823e4-152">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="823e4-152">**Recipient**</span></span>
- <span data-ttu-id="823e4-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="823e4-153">**Details**</span></span>
- <span data-ttu-id="823e4-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="823e4-154">**Count**</span></span>
- <span data-ttu-id="823e4-155">**Anfangstermin**</span><span class="sxs-lookup"><span data-stu-id="823e4-155">**Start date**</span></span>
- <span data-ttu-id="823e4-156">**Empfehlung**: von hier aus können Sie auf den Link klicken, um den Benutzer im Microsoft 365 Admin Center zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="823e4-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Details-Flyout aus der Detailtabelle der Ansicht neue weiterleitende Benutzer im Bericht zum Weiterleiten von Änderungen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="823e4-158">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="823e4-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="823e4-159">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="823e4-159">Related topics</span></span>

<span data-ttu-id="823e4-160">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="823e4-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
