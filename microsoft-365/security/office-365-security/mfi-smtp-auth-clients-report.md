---
title: Einblick und Bericht von SMTP-Authentifizierungsclients im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den SMTP-Authentifizierungs-Einblick und -Bericht im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Absender in ihrer Organisation zu überwachen, die authentifizierte SMTP (SMTP AUTH) zum Senden von E-Mail-Nachrichten verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204131"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="8e0d0-103">Smtp-Authentifizierungsclients: Einblick und Bericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8e0d0-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8e0d0-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-104">**Applies to**</span></span>
- [<span data-ttu-id="8e0d0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e0d0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8e0d0-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8e0d0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8e0d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e0d0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8e0d0-108">Die Einblicke der **SMTP-Authentifizierungsclients** im Nachrichtenflussdashboard und dem zugehörigen [SMTP-Authentifizierungsclientbericht](#smtp-auth-clients-report) im Security & Compliance Center unterstreichen die Verwendung des SMTP AUTH-Clientübermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation. [](mail-flow-insights-v2.md) [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="8e0d0-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="8e0d0-109">Dieses Legacyprotokoll (das die Endpunkt-smtp.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch gefährdete Konten zum Senden von E-Mails.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="8e0d0-110">Mit dem Einblick und dem Bericht können Sie nach ungewöhnlichen Aktivitäten für SMTP-AUTH-E-Mail-Übermittlungen suchen.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="8e0d0-111">Außerdem werden die TLS-Verwendungsdaten für Clients oder Geräte mit SMTP AUTH angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="8e0d0-112">Das Widget gibt die Anzahl der Benutzer oder Dienstkonten an, die das SMTP-Authentifizierungsprotokoll in den letzten 7 Tagen verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP-Auth-Clients-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="8e0d0-114">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout für **SMTP-Authentifizierungsclients** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="8e0d0-115">Das Flyout bietet eine aggregierte Ansicht der TLS-Nutzung und der Volumes für die letzte Woche.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Details flyout nach dem Klicken auf das SMTP Auth-Clients-Widget im Nachrichtenflussdashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="8e0d0-117">Sie können auf den **Link SMTP-Authentifizierungsclients klicken,** um zum SMTP-Authentifizierungsclientbericht zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="8e0d0-118">SMTP-Auth-Clientbericht</span><span class="sxs-lookup"><span data-stu-id="8e0d0-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="8e0d0-119">Berichtsansicht für den SMTP-Authentifizierungsclientbericht</span><span class="sxs-lookup"><span data-stu-id="8e0d0-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="8e0d0-120">Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt, daten sind jedoch für die letzten 90 Tage verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="8e0d0-121">Der Abschnitt Übersicht enthält die folgenden Diagramme:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="8e0d0-122">**Daten anzeigen nach:** Sendevolume : Standardmäßig zeigt das Diagramm die Anzahl der SMTP Auth-Clientnachrichten an, die von allen Domänen gesendet wurden ( Daten anzeigen **für: Alle** Absenderdomänen sind standardmäßig ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="8e0d0-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="8e0d0-123">Sie können die Ergebnisse in eine bestimmte  Absenderdomäne filtern, indem Sie in der Dropdownliste auf Daten für anzeigen klicken und die Absenderdomäne auswählen.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="8e0d0-124">Wenn Sie auf einen bestimmten Datenpunkt (Tag) zeigen, wird die Anzahl der Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Senden der Volumeansicht im BERICHT SMTP-Authentifizierungsclients im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="8e0d0-126">**Daten anzeigen nach: TLS-Verwendung**: Das Diagramm zeigt den Prozentsatz der TLS-Nutzung für alle SMTP-Authentifizierungsclientnachrichten während des ausgewählten Zeitraums an.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="8e0d0-127">In diesem Diagramm können Sie Benutzer und Systemkonten identifizieren und aktionen, die noch ältere Versionen von TLS verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![TLS-Verwendungsansicht im SMTP-Authentifizierungsclientbericht im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="8e0d0-129">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8e0d0-130">Klicken **Sie auf Bericht anfordern,** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="8e0d0-131">Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="8e0d0-132">Detailtabelle für den SMTP-Authentifizierungsclientbericht</span><span class="sxs-lookup"><span data-stu-id="8e0d0-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="8e0d0-133">Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8e0d0-134">**Daten anzeigen nach: Sendevolume**: Die folgenden Informationen werden in einer Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="8e0d0-135">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-135">**Sender address**</span></span>
  - <span data-ttu-id="8e0d0-136">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-136">**Message count**</span></span>

  <span data-ttu-id="8e0d0-137">Wenn Sie eine Zeile auswählen, werden dieselben Details in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="8e0d0-138">**Daten anzeigen nach: TLS-Verwendung**: Die folgenden Informationen werden in einer Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="8e0d0-139">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-139">**Sender address**</span></span>
  - <span data-ttu-id="8e0d0-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e0d0-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="8e0d0-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e0d0-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="8e0d0-142">**TLS1,2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e0d0-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="8e0d0-143">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-143">**Message count**</span></span>

  <span data-ttu-id="8e0d0-144"><sup>\*</sup> Diese Spalte zeigt sowohl den Prozentsatz als auch die Anzahl der Nachrichten vom Absender an.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="8e0d0-145">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8e0d0-146">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-146">If you select a row, similar details are shown in a flyout:</span></span>

![Details flyout aus der Detailtabelle der TLS-Verwendungsansicht im BERICHT SMTP-Authentifizierungsclients](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="8e0d0-148">Klicken **Sie auf Bericht anfordern,** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="8e0d0-149">Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="8e0d0-150">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="8e0d0-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e0d0-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8e0d0-151">Related topics</span></span>

<span data-ttu-id="8e0d0-152">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8e0d0-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
