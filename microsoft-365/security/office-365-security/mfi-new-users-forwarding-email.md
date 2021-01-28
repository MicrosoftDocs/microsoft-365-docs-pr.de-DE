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
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="ed6a0-103">Neue Benutzer, die E-Mail-Einblicke im Security & Compliance Center weiterleiten</span><span class="sxs-lookup"><span data-stu-id="ed6a0-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ed6a0-104">Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich beginnen, E-Mail-Nachrichten an externe Domänen weiter zu senden.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="ed6a0-105">Die **neuen Domänen, die** E-Mail-Einblicke im Security & Compliance [Center](https://protection.office.com) erhalten, benachrichtigen Sie, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe Domänen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="ed6a0-106">Diese Bedingung könnte darauf hinweisen, dass zum Erstellen der neuen Benutzer gefährdete Administratorkonten verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="ed6a0-107">Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="ed6a0-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="ed6a0-108">Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="ed6a0-110">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zum Bericht über [Weiterleitungsänderungen,](#forwarding-modifications-report) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Details-Flyout, das angezeigt wird, nachdem sie auf den Einblick in die E-Mail-Weiterleitung durch neue Benutzer geklickt haben](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="ed6a0-112">Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top insights" **&** **(** Berichtsdashboard oder ) auf "Alle anzeigen" geklickt \>  haben. <https://protection.office.com/insightdashboard></span><span class="sxs-lookup"><span data-stu-id="ed6a0-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="ed6a0-113">Sie können auf den Link **"Bericht** mit Einblicken sehen" klicken, um zum Bericht über **Weiterleitungsänderungen** zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="ed6a0-114">Bericht über Weiterleitungsänderungen</span><span class="sxs-lookup"><span data-stu-id="ed6a0-114">Forwarding modifications report</span></span>

<span data-ttu-id="ed6a0-115">Der **Bericht über Weiterleitungsänderungen enthält** Details zu Nachrichten, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="ed6a0-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="ed6a0-116">Neu erstellte Konten, die Nachrichten an externe Domänen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="ed6a0-117">Konten, die Nachrichten an externe Domänen weiterleiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="ed6a0-118">Diese Art von weitergeleiteten Nachrichten kann ein Sicherheits- oder Compliancerisiko darstellen und auf gefährdete Konten hinweisen.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="ed6a0-119">Der Bericht enthält Daten für bis zu 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="ed6a0-120">Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="ed6a0-121">Dieser Bericht ist nicht direkt [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard oder im [Berichtsdashboard verfügbar.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="ed6a0-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="ed6a0-122">Zusätzlich zum Klicken  auf den Link "Bericht  mit Einblicken sehen" im E-Mail-Einblick "Neue Benutzer" erhalten Sie folgenden Zugriff auf den Bericht:</span><span class="sxs-lookup"><span data-stu-id="ed6a0-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="ed6a0-123">Klicken Auf den **Link "Weiterleitungsbenachrichtigungen melden"** in den Details der neuen Domänen, die weitergeleitet werden, E-Mail-Einblick. [](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="ed6a0-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="ed6a0-124">Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="ed6a0-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="ed6a0-125">Berichtsansicht für den Bericht über Weiterleitungsänderungen</span><span class="sxs-lookup"><span data-stu-id="ed6a0-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="ed6a0-126">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ed6a0-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ed6a0-127">**Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-127">**Show data for: New forwarding users**:</span></span>

  ![Ansicht "Neue Weiterleitungsbenutzer" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="ed6a0-129">**Anzeigen von Daten für: Neue Weiterleitungsdomänen:**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-129">**Show data for: New forwarding domains**:</span></span>

  ![Ansicht "Neue weitergeleitete Domänen" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="ed6a0-131">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="ed6a0-132">Detailtabelle für den Bericht "Weiterleitungsänderungen"</span><span class="sxs-lookup"><span data-stu-id="ed6a0-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="ed6a0-133">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="ed6a0-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ed6a0-134">**Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="ed6a0-135">**Name:** Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="ed6a0-136">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-136">**Forwarding type**</span></span>
  - <span data-ttu-id="ed6a0-137">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-137">**Recipient address**</span></span>
  - <span data-ttu-id="ed6a0-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-138">**Details**</span></span>
  - <span data-ttu-id="ed6a0-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-139">**Count**</span></span>
  - <span data-ttu-id="ed6a0-140">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-140">**First forward date**</span></span>

- <span data-ttu-id="ed6a0-141">**Daten anzeigen für: Neue Weiterleitungsdomänen:**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="ed6a0-142">**Name:** Die E-Mail-Domäne des Absenders.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="ed6a0-143">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-143">**Forwarding type**</span></span>
  - <span data-ttu-id="ed6a0-144">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-144">**Recipient address**</span></span>
  - <span data-ttu-id="ed6a0-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-145">**Details**</span></span>
  - <span data-ttu-id="ed6a0-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-146">**Count**</span></span>
  - <span data-ttu-id="ed6a0-147">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-147">**First forward date**</span></span>

<span data-ttu-id="ed6a0-148">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed6a0-149">Wenn Sie eine Zeile aus der Tabelle auswählen, wird ein **Flyout "Details"** mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ed6a0-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="ed6a0-150">**Name:** Dies ist entweder die E-Mail-Adresse des Absenders (aus Ansicht "Daten anzeigen **für:** Ansicht "Neue Weiterleitungsbenutzer") oder die E-Mail-Domäne des Absenders (aus Ansicht "Daten anzeigen für: Neue **Weiterleitungsdomänen").**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="ed6a0-151">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-151">**Forwarding type**</span></span>
- <span data-ttu-id="ed6a0-152">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-152">**Recipient**</span></span>
- <span data-ttu-id="ed6a0-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-153">**Details**</span></span>
- <span data-ttu-id="ed6a0-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-154">**Count**</span></span>
- <span data-ttu-id="ed6a0-155">**Anfangstermin**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-155">**Start date**</span></span>
- <span data-ttu-id="ed6a0-156">**Empfehlung:** Von hier aus können Sie auf den Link klicken, um den Benutzer im Microsoft 365 Admin Center zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ed6a0-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Details flyout from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="ed6a0-158">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="ed6a0-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed6a0-159">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ed6a0-159">Related topics</span></span>

<span data-ttu-id="ed6a0-160">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ed6a0-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
