---
title: Unzustellbarkeitsbericht im Nachrichtenübermittlungs-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Bericht über Unzustellbarkeits Informationen im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877681"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="ec49c-103">Unzustellbarkeitsbericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ec49c-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ec49c-104">Der **Unzustellbarkeitsbericht** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) zeigt die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch bekannt als Unzustellbarkeitsberichte oder Bounce-Nachrichten) für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ec49c-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="ec49c-105">Dieser Bericht zeigt die Details von Unzustellbarkeitsberichten an, damit Sie Probleme mit der e-Mail-Zustellung beheben können.</span><span class="sxs-lookup"><span data-stu-id="ec49c-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget "nicht Zustellungsbericht" im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="ec49c-107">Berichtsansicht für Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="ec49c-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="ec49c-108">Wenn Sie auf das Widget **nicht Zustellungsbericht** klicken, gelangen Sie zum **Unzustellbarkeitsbericht**.</span><span class="sxs-lookup"><span data-stu-id="ec49c-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="ec49c-109">Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec49c-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="ec49c-110">Wenn Sie auf **Daten anzeigen für** klicken, können Sie einen bestimmten Fehlercode aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="ec49c-110">If you click **Show data for** , you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="ec49c-111">Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe (Fehlercode) an einem bestimmten Tag im Diagramm zeigen, wird die Gesamtzahl der Nachrichten für den Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec49c-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Berichtsansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="ec49c-113">Detailtabellen Ansicht für den Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="ec49c-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="ec49c-114">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec49c-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ec49c-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="ec49c-115">**Date**</span></span>
- <span data-ttu-id="ec49c-116">**Code für Unzustellbarkeitsberichte**</span><span class="sxs-lookup"><span data-stu-id="ec49c-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="ec49c-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="ec49c-117">**Count**</span></span>
- <span data-ttu-id="ec49c-118">**Beispiel Meldungen** : die Nachrichten-IDs einer Stichprobe betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="ec49c-118">**Sample messages** : The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="ec49c-119">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.</span><span class="sxs-lookup"><span data-stu-id="ec49c-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ec49c-120">Klicken Sie auf **Anforderungs Download** , um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="ec49c-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ec49c-121">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec49c-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="ec49c-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="ec49c-122">**Date**</span></span>
- <span data-ttu-id="ec49c-123">**Unzustellbarkeitsbericht Code** : Sie können auf den Link klicken, um weitere Informationen zu den Ursachen und Lösungen für den spezifischen Fehlercode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec49c-123">**Non-delivery report code** : You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="ec49c-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="ec49c-124">**Count**</span></span>
- <span data-ttu-id="ec49c-125">**Beispiel Meldungen** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der betroffenen Nachrichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec49c-125">**Sample messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Detail Flyout nach dem Auswählen einer Zeile in der Detailtabellen Ansicht im Unzustellbarkeitsbericht](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="ec49c-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ec49c-127">Related topics</span></span>

<span data-ttu-id="ec49c-128">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ec49c-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
