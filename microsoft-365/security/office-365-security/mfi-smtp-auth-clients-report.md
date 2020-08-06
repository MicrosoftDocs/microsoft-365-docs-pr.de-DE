---
title: Einblicke und Berichte von SMTP-Authentifizierungsclients im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie die SMTP-Authentifizierungs Einblicke und den Bericht im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um e-Mail-Absender in Ihrer Organisation zu überwachen, die authentifizierte SMTP (SMTP-Authentifizierung) zum Senden von e-Mail-Nachrichten verwenden.
ms.openlocfilehash: afdcf01260dd6dfcaf6b53d107e5addd007b1fb3
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577235"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="06cca-103">Einblicke und Berichte von SMTP-Authentifizierungsclients im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="06cca-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="06cca-104">Die Einblicke der **SMTP-Authentifizierungsclients** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) und den zugeordneten [SMTP-Authentifizierungsclients](#smtp-auth-clients-report) zeigen die Verwendung des SMTP-Authentifizierungs Client-Übermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="06cca-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="06cca-105">Dieses Legacy Protokoll (das den Endpunkt SMTP.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch kompromittierte Konten zum Senden von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="06cca-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="06cca-106">Die Einblicke und der Bericht ermöglichen es Ihnen, nach ungewöhnlichen Aktivitäten für SMTP-e-Mail-Übermittlungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="06cca-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="06cca-107">Außerdem werden die TLS-Nutzungsdaten für Clients oder Geräte mithilfe der SMTP-Authentifizierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06cca-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="06cca-108">Das Widget gibt die Anzahl der Benutzer oder Dienstkonten an, die in den letzten 7 Tagen das SMTP-Authentifizierungsprotokoll verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="06cca-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP-Authentifizierungsclients-Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="06cca-110">Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout für **SMTP-Authentifizierungsclients** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06cca-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="06cca-111">Das Flyout bietet eine aggregierte Ansicht der TLS-Nutzung und-Volumes für die letzte Woche.</span><span class="sxs-lookup"><span data-stu-id="06cca-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Details-Flyout nach dem Klicken auf das SMTP-Authentifizierungsclients-Widget im Nachrichtenfluss-Dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="06cca-113">Sie können auf den Link **SMTP AUTH Clients Report** klicken, um zum Bericht SMTP AUTH Clients zu wechseln, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06cca-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="06cca-114">SMTP-Auth-Clientbericht</span><span class="sxs-lookup"><span data-stu-id="06cca-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="06cca-115">Berichtsansicht für den Bericht "SMTP AUTH Clients"</span><span class="sxs-lookup"><span data-stu-id="06cca-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="06cca-116">Standardmäßig zeigt der Berichtdaten für die letzten 7 Tage an, aber Daten sind für die letzten 90 Tage verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06cca-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="06cca-117">Der Overview-Abschnitt enthält die folgenden Diagramme:</span><span class="sxs-lookup"><span data-stu-id="06cca-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="06cca-118">**Daten nach: Sending Volume**: Standardmäßig zeigt das Diagramm die Anzahl von SMTP-AUTH-Client Nachrichten an, die von allen Domänen gesendet wurden (**Daten anzeigen für: alle Absenderdomänen** sind standardmäßig ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="06cca-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="06cca-119">Sie können die Ergebnisse auf eine bestimmte Absenderdomäne filtern, indem Sie in der Dropdownliste auf **Daten für anzeigen** und die Absenderdomäne auswählen klicken.</span><span class="sxs-lookup"><span data-stu-id="06cca-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="06cca-120">Wenn Sie auf einen bestimmten Datenpunkt (Tag) zeigen, wird die Anzahl der Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06cca-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Senden der Volumen Ansicht im Bericht "SMTP AUTH Clients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="06cca-122">**Daten nach: TLS Usage**: das Diagramm zeigt den Prozentsatz der TLS-Nutzung für alle SMTP-AUTH-Client Nachrichten während des ausgewählten Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="06cca-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="06cca-123">Dieses Diagramm ermöglicht es Ihnen, Benutzer und Systemkonten zu identifizieren und zu ergreifen, die noch ältere Versionen von TLS verwenden.</span><span class="sxs-lookup"><span data-stu-id="06cca-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![TLS-Verwendungs Ansicht im Bericht SMTP AUTH Clients im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="06cca-125">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="06cca-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="06cca-126">Klicken Sie auf **Anforderungsbericht** , um eine detailliertere Version des Berichts in einer e-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="06cca-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="06cca-127">Sie können den Datumsbereich und die Empfänger angeben, um den Bericht zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="06cca-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="06cca-128">Tabellenansicht "Details" für den Bericht "SMTP AUTH Clients"</span><span class="sxs-lookup"><span data-stu-id="06cca-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="06cca-129">Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:</span><span class="sxs-lookup"><span data-stu-id="06cca-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="06cca-130">**Daten anzeigen nach: Sending Volume**: die folgenden Informationen werden in einer Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06cca-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="06cca-131">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="06cca-131">**Sender address**</span></span>
  - <span data-ttu-id="06cca-132">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="06cca-132">**Message count**</span></span>

  <span data-ttu-id="06cca-133">Wenn Sie eine Zeile auswählen, werden dieselben Details in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06cca-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="06cca-134">**Daten nach: TLS-Verwendung anzeigen**: die folgenden Informationen werden in einer Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06cca-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="06cca-135">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="06cca-135">**Sender address**</span></span>
  - <span data-ttu-id="06cca-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06cca-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="06cca-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06cca-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="06cca-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06cca-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="06cca-139">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="06cca-139">**Message count**</span></span>

  <span data-ttu-id="06cca-140"><sup>\*</sup>In dieser Spalte werden sowohl der Prozentsatz als auch die Anzahl der Nachrichten des Absenders angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06cca-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="06cca-141">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="06cca-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="06cca-142">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06cca-142">If you select a row, similar details are shown in a flyout:</span></span>

![Details-Flyout aus der Detailtabelle der TLS-Einsatzansicht im SMTP-AUTH-Client-Bericht](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="06cca-144">Klicken Sie auf **Anforderungsbericht** , um eine detailliertere Version des Berichts in einer e-Mail-Nachricht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="06cca-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="06cca-145">Sie können den Datumsbereich und die Empfänger angeben, um den Bericht zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="06cca-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="06cca-146">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="06cca-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="06cca-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="06cca-147">Related topics</span></span>

<span data-ttu-id="06cca-148">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="06cca-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
