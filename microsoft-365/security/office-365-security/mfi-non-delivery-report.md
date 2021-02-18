---
title: Unzustellungsbericht im Nachrichtenflussdashboard
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
description: Administratoren können erfahren, wie Sie den Bericht über Unzustellbarkeitsdetails im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um die am häufigsten aufgetretenen Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsnachrichten bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287889"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="95008-103">Unzustellungsbericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="95008-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95008-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="95008-104">**Applies to**</span></span>
- [<span data-ttu-id="95008-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="95008-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="95008-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="95008-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="95008-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95008-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="95008-108">Der  Unzustellbarkeitsbericht [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt die häufigsten Fehlercodes in Unzustellbarkeitsberichten (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet) für Benutzer in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="95008-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="95008-109">Dieser Bericht enthält die Details von Unzustellungsberichten, damit Sie Probleme mit der Zustellung von E-Mails beheben können.</span><span class="sxs-lookup"><span data-stu-id="95008-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Unzustellungsbericht-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="95008-111">Berichtsansicht für den Unzustellungsbericht</span><span class="sxs-lookup"><span data-stu-id="95008-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="95008-112">Wenn Sie auf das **Widget "Unzustellungsbericht"** klicken, werden Sie zum Unzustellungsbericht **angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="95008-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="95008-113">Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95008-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="95008-114">Wenn Sie auf **"Daten anzeigen" klicken,** können Sie in der Dropdownliste einen bestimmten Fehlercode auswählen.</span><span class="sxs-lookup"><span data-stu-id="95008-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="95008-115">Wenn Sie an einem bestimmten Tag im Diagramm auf eine bestimmte Farbe (Fehlercode) zeigen, wird die Gesamtanzahl der Meldungen für den Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95008-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Berichtsansicht im Bericht "Nicht akzeptierte Domäne"](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="95008-117">Detailtabelle für den Unzustellungsbericht</span><span class="sxs-lookup"><span data-stu-id="95008-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="95008-118">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="95008-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="95008-119">**Date**</span><span class="sxs-lookup"><span data-stu-id="95008-119">**Date**</span></span>
- <span data-ttu-id="95008-120">**Unzustellungsberichtscode**</span><span class="sxs-lookup"><span data-stu-id="95008-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="95008-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="95008-121">**Count**</span></span>
- <span data-ttu-id="95008-122">**Beispielmeldungen:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="95008-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="95008-123">Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="95008-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="95008-124">Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**</span><span class="sxs-lookup"><span data-stu-id="95008-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="95008-125">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="95008-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="95008-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="95008-126">**Date**</span></span>
- <span data-ttu-id="95008-127">**Unzustellungsberichtscode:** Klicken Sie auf den Link, um weitere Informationen zu den Ursachen und Lösungen für den jeweiligen Fehlercode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95008-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="95008-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="95008-128">**Count**</span></span>
- <span data-ttu-id="95008-129">**Beispielmeldungen:** Sie können auf "Beispielmeldungen **anzeigen"** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="95008-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Details flyout after selecting a row in Details table view in the Non-delivery report](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="95008-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="95008-131">Related topics</span></span>

<span data-ttu-id="95008-132">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="95008-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
