---
title: Einblick und Bericht für SMTP-Authentifizierungsclients im Dashboard für den Nachrichtenfluss
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
description: Administratoren können erfahren, wie Sie den Einblick in die SMTP-Authentifizierung und den Bericht im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Absender in ihrer Organisation zu überwachen, die authentifizierte SMTP (SMTP AUTH) zum Senden von E-Mail-Nachrichten verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9050fd2c1bc3863a3bd78190cd5b27fda018479e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287797"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="a9e90-103">Einblick und Bericht für SMTP-Authentifizierungsclients im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a9e90-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a9e90-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="a9e90-104">**Applies to**</span></span>
- [<span data-ttu-id="a9e90-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a9e90-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a9e90-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="a9e90-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a9e90-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9e90-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a9e90-108">In den Einblicken der [](mail-flow-insights-v2.md) **SMTP-Authentifizierungsclients** im Nachrichtenflussdashboard und dem zugehörigen [SMTP-Authentifizierungsclientbericht](#smtp-auth-clients-report) im Security & Compliance Center wird die Verwendung des SMTP AUTH-Clientübermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation hervorgehoben. [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="a9e90-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="a9e90-109">Dieses Legacyprotokoll (das die Endpunkt-smtp.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch gefährdete Konten zum Senden von E-Mails.</span><span class="sxs-lookup"><span data-stu-id="a9e90-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="a9e90-110">Der Einblick und der Bericht ermöglichen es Ihnen, ungewöhnliche Aktivitäten für SMTP AUTH-E-Mail-Übermittlungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a9e90-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="a9e90-111">Außerdem werden die TLS-Verwendungsdaten für Clients oder Geräte mit SMTP AUTH angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9e90-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="a9e90-112">Das Widget gibt die Anzahl der Benutzer oder Dienstkonten an, die das SMTP-Authentifizierungsprotokoll in den letzten 7 Tagen verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="a9e90-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP-Authentifizierungsclients-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="a9e90-114">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout für **SMTP-Authentifizierungsclients** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9e90-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="a9e90-115">Das Flyout bietet eine aggregierte Ansicht der Verwendung und der Volumes von TLS für die letzte Woche.</span><span class="sxs-lookup"><span data-stu-id="a9e90-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Detailf flyout nach dem Klicken auf das Widget "SMTP-Authentifizierungsclients" im Nachrichtenflussdashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="a9e90-117">Sie können auf den Bericht **"SMTP-Authentifizierungsclients"** klicken, um zum Bericht "SMTP-Authentifizierungsclients" zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9e90-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="a9e90-118">SMTP-Auth-Clientbericht</span><span class="sxs-lookup"><span data-stu-id="a9e90-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a9e90-119">Berichtsansicht für den Bericht "SMTP-Authentifizierungsclients"</span><span class="sxs-lookup"><span data-stu-id="a9e90-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a9e90-120">Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt, die Daten sind jedoch für die letzten 90 Tage verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9e90-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="a9e90-121">Der Abschnitt "Übersicht" enthält die folgenden Diagramme:</span><span class="sxs-lookup"><span data-stu-id="a9e90-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="a9e90-122">**Daten nach:** Sendevolume anzeigen: Standardmäßig zeigt das Diagramm die Anzahl der SMTP-Authentifizierungsclientnachrichten an, die von allen Domänen gesendet wurden ( Daten anzeigen **für:** Alle Absenderdomänen sind standardmäßig ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="a9e90-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="a9e90-123">Sie können die Ergebnisse nach einer bestimmten Absenderdomäne filtern, indem Sie in der Dropdownliste auf "Daten anzeigen" klicken und die Absenderdomäne auswählen. </span><span class="sxs-lookup"><span data-stu-id="a9e90-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="a9e90-124">Wenn Sie auf einen bestimmten Datenpunkt (Tag) zeigen, wird die Anzahl der Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9e90-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Senden der Volumeansicht im Bericht "SMTP-Authentifizierungsclients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="a9e90-126">**Daten nach: TLS-Verwendung anzeigen:** Das Diagramm zeigt den Prozentsatz der TLS-Verwendung für alle NACHRICHTEN des SMTP-Authentifizierungsclients während des ausgewählten Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="a9e90-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="a9e90-127">In diesem Diagramm können Sie Benutzer und Systemkonten identifizieren und Maßnahmen ergreifen, die weiterhin ältere Versionen von TLS verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9e90-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![TLS-Verwendungsansicht im Bericht "SMTP-Authentifizierungsclients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="a9e90-129">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="a9e90-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9e90-130">Klicken **Sie auf "Anforderungsbericht",** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9e90-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a9e90-131">Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="a9e90-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a9e90-132">Detailtabelle für den Bericht "SMTP-Authentifizierungsclients"</span><span class="sxs-lookup"><span data-stu-id="a9e90-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a9e90-133">Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:</span><span class="sxs-lookup"><span data-stu-id="a9e90-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a9e90-134">**Daten anzeigen nach: Sendevolume:** Die folgenden Informationen sind in einer Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a9e90-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a9e90-135">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="a9e90-135">**Sender address**</span></span>
  - <span data-ttu-id="a9e90-136">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="a9e90-136">**Message count**</span></span>

  <span data-ttu-id="a9e90-137">Wenn Sie eine Zeile auswählen, werden die gleichen Details in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9e90-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="a9e90-138">**Anzeigen von Daten nach: TLS-Verwendung:** Die folgenden Informationen sind in einer Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a9e90-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a9e90-139">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="a9e90-139">**Sender address**</span></span>
  - <span data-ttu-id="a9e90-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9e90-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9e90-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9e90-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9e90-142">**TLS1,2 %**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9e90-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9e90-143">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="a9e90-143">**Message count**</span></span>

  <span data-ttu-id="a9e90-144"><sup>\*</sup> In dieser Spalte werden der Prozentsatz und die Anzahl der Nachrichten des Absenders angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9e90-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="a9e90-145">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="a9e90-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9e90-146">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9e90-146">If you select a row, similar details are shown in a flyout:</span></span>

![Detailf flyout aus der Detailtabelle der TLS-Verwendungsansicht im SMTP-Authentifizierungsclientbericht](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="a9e90-148">Klicken **Sie auf "Anforderungsbericht",** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9e90-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a9e90-149">Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="a9e90-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="a9e90-150">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="a9e90-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9e90-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a9e90-151">Related topics</span></span>

<span data-ttu-id="a9e90-152">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a9e90-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
