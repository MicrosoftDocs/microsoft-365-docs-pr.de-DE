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
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150255"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="bb70b-103">Neue Benutzer, die E-Mail-Einblicke im Security & Compliance Center weiterleiten</span><span class="sxs-lookup"><span data-stu-id="bb70b-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bb70b-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="bb70b-104">**Applies to**</span></span>
- [<span data-ttu-id="bb70b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bb70b-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="bb70b-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="bb70b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bb70b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb70b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bb70b-108">Es ist verdächtig, wenn neue Benutzerkonten in Ihrer Organisation plötzlich mit der Weiterleitung von E-Mail-Nachrichten an externe Domänen beginnen.</span><span class="sxs-lookup"><span data-stu-id="bb70b-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="bb70b-109">Die **neuen Domänen, die** E-Mail-Einblicke im Security & Compliance [Center](https://protection.office.com) erhalten, benachrichtigen Sie, wenn neu erstellte Benutzer in Ihrer Organisation Nachrichten an externe Domänen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="bb70b-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="bb70b-110">Diese Bedingung könnte darauf hinweisen, dass zum Erstellen der neuen Benutzer gefährdete Administratorkonten verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="bb70b-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="bb70b-111">Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="bb70b-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="bb70b-112">Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb70b-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mail-Weiterleitung von neuen Benutzern](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="bb70b-114">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zum Bericht über [Weiterleitungsänderungen,](#forwarding-modifications-report) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb70b-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Details-Flyout, das angezeigt wird, nachdem sie auf den Einblick für die Weiterleitung von E-Mails durch neue Benutzer geklickt haben](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="bb70b-116">Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top insights" **&** **(** Berichtsdashboard oder ) auf "Alle anzeigen" geklickt \>  haben. <https://protection.office.com/insightdashboard></span><span class="sxs-lookup"><span data-stu-id="bb70b-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="bb70b-117">Sie können auf den **Link** "Bericht mit Einblicken sehen" klicken, um zum Bericht über **Weiterleitungsänderungen** zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb70b-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="bb70b-118">Bericht über Weiterleitungsänderungen</span><span class="sxs-lookup"><span data-stu-id="bb70b-118">Forwarding modifications report</span></span>

<span data-ttu-id="bb70b-119">Der **Bericht über Weiterleitungsänderungen enthält** Details zu Nachrichten, die automatisch von Absendern in Ihrer Organisation weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="bb70b-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="bb70b-120">Neu erstellte Konten, die Nachrichten an externe Domänen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="bb70b-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="bb70b-121">Konten, die Nachrichten an externe Domänen weiterleiten, die noch nie von anderen Absendern in Ihrer Organisation weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="bb70b-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="bb70b-122">Diese Arten von weitergeleiteten Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf gefährdete Konten hinweisen.</span><span class="sxs-lookup"><span data-stu-id="bb70b-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="bb70b-123">Der Bericht enthält Daten für bis zu 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="bb70b-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="bb70b-124">Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb70b-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="bb70b-125">Dieser Bericht ist nicht direkt [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard oder im [Berichtsdashboard verfügbar.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="bb70b-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="bb70b-126">Zusätzlich zum Klicken  auf den Link "Bericht  mit Einblicken sehen" im E-Mail-Einblick "Neue Benutzer" erhalten Sie folgenden Zugriff auf den Bericht:</span><span class="sxs-lookup"><span data-stu-id="bb70b-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="bb70b-127">Klicken Auf den **Link "Weiterleitungsbenachrichtigungen melden"** in den Details der neuen Domänen, die weitergeleitet werden, E-Mail-Einblick. [](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="bb70b-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="bb70b-128">Öffnen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="bb70b-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="bb70b-129">Berichtsansicht für den Bericht über Weiterleitungsänderungen</span><span class="sxs-lookup"><span data-stu-id="bb70b-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="bb70b-130">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bb70b-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bb70b-131">**Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="bb70b-131">**Show data for: New forwarding users**:</span></span>

  ![Ansicht "Neue Weiterleitungsbenutzer" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="bb70b-133">**Daten anzeigen für: Neue Weiterleitungsdomänen:**</span><span class="sxs-lookup"><span data-stu-id="bb70b-133">**Show data for: New forwarding domains**:</span></span>

  ![Ansicht "Neue weitergeleitete Domänen" im Bericht "Weiterleitungsänderungen"](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="bb70b-135">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="bb70b-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="bb70b-136">Detailtabelle für den Bericht "Weiterleitungsänderungen"</span><span class="sxs-lookup"><span data-stu-id="bb70b-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="bb70b-137">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="bb70b-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bb70b-138">**Anzeigen von Daten für: Neue Weiterleitungsbenutzer:**</span><span class="sxs-lookup"><span data-stu-id="bb70b-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="bb70b-139">**Name**: Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="bb70b-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="bb70b-140">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="bb70b-140">**Forwarding type**</span></span>
  - <span data-ttu-id="bb70b-141">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="bb70b-141">**Recipient address**</span></span>
  - <span data-ttu-id="bb70b-142">**Details**</span><span class="sxs-lookup"><span data-stu-id="bb70b-142">**Details**</span></span>
  - <span data-ttu-id="bb70b-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="bb70b-143">**Count**</span></span>
  - <span data-ttu-id="bb70b-144">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="bb70b-144">**First forward date**</span></span>

- <span data-ttu-id="bb70b-145">**Daten anzeigen für: Neue Weiterleitungsdomänen:**</span><span class="sxs-lookup"><span data-stu-id="bb70b-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="bb70b-146">**Name:** Die E-Mail-Domäne des Absenders.</span><span class="sxs-lookup"><span data-stu-id="bb70b-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="bb70b-147">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="bb70b-147">**Forwarding type**</span></span>
  - <span data-ttu-id="bb70b-148">**Empfängeradresse**</span><span class="sxs-lookup"><span data-stu-id="bb70b-148">**Recipient address**</span></span>
  - <span data-ttu-id="bb70b-149">**Details**</span><span class="sxs-lookup"><span data-stu-id="bb70b-149">**Details**</span></span>
  - <span data-ttu-id="bb70b-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="bb70b-150">**Count**</span></span>
  - <span data-ttu-id="bb70b-151">**Erstes Weiterleitungsdatum**</span><span class="sxs-lookup"><span data-stu-id="bb70b-151">**First forward date**</span></span>

<span data-ttu-id="bb70b-152">Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="bb70b-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bb70b-153">Wenn Sie eine Zeile aus der Tabelle auswählen, wird ein **Flyout "Details"** mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bb70b-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="bb70b-154">**Name:** Dies ist entweder die E-Mail-Adresse des Absenders (aus Ansicht "Daten anzeigen **für:** Neue Weiterleitungsbenutzer") oder die E-Mail-Domäne des Absenders (aus Ansicht "Daten anzeigen für: Neue **Weiterleitungsdomänen").**</span><span class="sxs-lookup"><span data-stu-id="bb70b-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="bb70b-155">**Weiterleitungstyp**</span><span class="sxs-lookup"><span data-stu-id="bb70b-155">**Forwarding type**</span></span>
- <span data-ttu-id="bb70b-156">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="bb70b-156">**Recipient**</span></span>
- <span data-ttu-id="bb70b-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="bb70b-157">**Details**</span></span>
- <span data-ttu-id="bb70b-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="bb70b-158">**Count**</span></span>
- <span data-ttu-id="bb70b-159">**Anfangstermin**</span><span class="sxs-lookup"><span data-stu-id="bb70b-159">**Start date**</span></span>
- <span data-ttu-id="bb70b-160">**Empfehlung:** Von hier aus können Sie auf den Link klicken, um den Benutzer im Microsoft 365 Admin Center zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="bb70b-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Details flyout from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="bb70b-162">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="bb70b-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb70b-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bb70b-163">Related topics</span></span>

<span data-ttu-id="bb70b-164">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bb70b-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
