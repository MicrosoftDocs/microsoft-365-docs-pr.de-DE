---
title: Verwenden des eDiscovery-Exporttools in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Sie müssen die ClickOnce aktivieren, um die neueste Version von Microsoft Edge zum Herunterladen von Suchergebnissen aus der Inhaltssuche und eDiscovery im Security and Compliance Center zu verwenden.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546819"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="f437d-103">Verwenden des eDiscovery-Exporttools in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f437d-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="f437d-104">Als Ergebnis der letzten Änderungen an der neuesten Version von Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f437d-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="f437d-105">Um weiterhin das eDiscovery-Exporttool zum Herunterladen von Inhaltssuche- oder eDiscovery-Suchergebnissen zu verwenden, müssen Sie [entweder Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) verwenden oder ClickOnce-Unterstützung in der neuesten Version von Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f437d-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="f437d-106">Aktivieren ClickOnce Unterstützung in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f437d-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="f437d-107">Wechseln Microsoft Edge zu **edge://flags/#edge-click-once**.</span><span class="sxs-lookup"><span data-stu-id="f437d-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="f437d-108">Wenn der vorhandene Wert in der Dropdownliste auf **Standard** oder **Deaktiviert** festgelegt ist, ändern Sie ihn in **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="f437d-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Auswählen von Aktiviert in der Dropdownliste](../media/ClickOnceimage1.png)

3. <span data-ttu-id="f437d-110">Scrollen Sie nach unten im Browserfenster, und klicken Sie **auf Neu starten,** um Edge neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="f437d-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Klicken Sie auf Neustart](../media/ClickOnceimage2.png)

<span data-ttu-id="f437d-112">**Hinweis:** Organisationen können Gruppenrichtlinien verwenden, um ClickOnce zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f437d-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="f437d-113">Um zu überprüfen, ob eine Organisationsrichtlinie für ClickOnce ist, wechseln Sie **zu edge://policy**.</span><span class="sxs-lookup"><span data-stu-id="f437d-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="f437d-114">Der folgende Screenshot zeigt, ClickOnce in der gesamten Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f437d-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="f437d-115">Wenn dieser Richtlinienwert auf **false festgelegt** ist, müssen Sie sich an einen Administrator in Ihrer Organisation wenden.</span><span class="sxs-lookup"><span data-stu-id="f437d-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Liste der Edgeorganisationsrichtlinien](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="f437d-117">Installieren und Ausführen des eDiscovery-Exporttools</span><span class="sxs-lookup"><span data-stu-id="f437d-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="f437d-118">Klicken **Sie auf der** Flyoutseite eines Exports in der Inhaltssuche oder in einem eDiscovery-Fall auf Ergebnisse herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f437d-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Klicken Sie auf der Flyoutseite auf Ergebnisse herunterladen, um Suchergebnisse herunterzuladen.](../media/ClickOnceExport1.png)

2. <span data-ttu-id="f437d-120">Sie werden aufgefordert, eine Bestätigung zum Starten des Tools zu erhalten, klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="f437d-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Klicken Sie auf Öffnen, um das eDiscovery-Exporttool zu starten.](../media/ClickOnceimage4.png)

   <span data-ttu-id="f437d-122">Wenn das eDiscovery-Exporttool nicht installiert ist, werden Sie mit einer Sicherheitswarnung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f437d-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Klicken Sie auf Installieren, um das eDiscovery-Exporttool zu installieren.](../media/ClickOnceimage5.png)

3. <span data-ttu-id="f437d-124">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="f437d-124">Click **Install**.</span></span> <span data-ttu-id="f437d-125">Nach der Installation wird das Exporttool automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="f437d-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="f437d-126">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f437d-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="f437d-127">Exportieren von Inhaltssuchergebnissen </span><span class="sxs-lookup"><span data-stu-id="f437d-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="f437d-128">Aktivieren von Experimentflags in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f437d-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
