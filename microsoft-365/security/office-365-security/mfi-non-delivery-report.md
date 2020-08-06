---
title: Unzustellbarkeitsbericht im Nachrichtenübermittlungs-Dashboard
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
description: Administratoren können erfahren, wie Sie den Bericht über Unzustellbarkeits Informationen im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.openlocfilehash: d45382ab5c7e0d0a73487740544f20b9c25a3ad1
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577420"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="68cc4-103">Unzustellbarkeitsbericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="68cc4-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="68cc4-104">Der **Unzustellbarkeitsbericht** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zeigt die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch bekannt als Unzustellbarkeitsberichte oder Bounce-Nachrichten) für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="68cc4-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="68cc4-105">Dieser Bericht zeigt die Details von Unzustellbarkeitsberichten an, damit Sie Probleme mit der e-Mail-Zustellung beheben können.</span><span class="sxs-lookup"><span data-stu-id="68cc4-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget "nicht Zustellungsbericht" im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="68cc4-107">Berichtsansicht für Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="68cc4-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="68cc4-108">Wenn Sie auf das Widget **nicht Zustellungsbericht** klicken, gelangen Sie zum **Unzustellbarkeitsbericht**.</span><span class="sxs-lookup"><span data-stu-id="68cc4-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="68cc4-109">Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68cc4-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="68cc4-110">Wenn Sie auf **Daten anzeigen für**klicken, können Sie einen bestimmten Fehlercode aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="68cc4-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="68cc4-111">Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe (Fehlercode) an einem bestimmten Tag im Diagramm zeigen, wird die Gesamtzahl der Nachrichten für den Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68cc4-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Berichtsansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="68cc4-113">Detailtabellen Ansicht für den Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="68cc4-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="68cc4-114">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="68cc4-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="68cc4-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="68cc4-115">**Date**</span></span>
- <span data-ttu-id="68cc4-116">**Code für Unzustellbarkeitsberichte**</span><span class="sxs-lookup"><span data-stu-id="68cc4-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="68cc4-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="68cc4-117">**Count**</span></span>
- <span data-ttu-id="68cc4-118">**Beispiel Meldungen**: die Nachrichten-IDs einer Stichprobe betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="68cc4-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="68cc4-119">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="68cc4-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="68cc4-120">Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="68cc4-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="68cc4-121">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="68cc4-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="68cc4-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="68cc4-122">**Date**</span></span>
- <span data-ttu-id="68cc4-123">**Unzustellbarkeitsbericht Code**: Sie können auf den Link klicken, um weitere Informationen zu den Ursachen und Lösungen für den spezifischen Fehlercode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68cc4-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="68cc4-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="68cc4-124">**Count**</span></span>
- <span data-ttu-id="68cc4-125">**Beispiel Meldungen**: Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der betroffenen Nachrichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68cc4-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Detail Flyout nach dem Auswählen einer Zeile in der Detailtabellen Ansicht im Unzustellbarkeitsbericht](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="68cc4-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="68cc4-127">Related topics</span></span>

<span data-ttu-id="68cc4-128">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="68cc4-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
