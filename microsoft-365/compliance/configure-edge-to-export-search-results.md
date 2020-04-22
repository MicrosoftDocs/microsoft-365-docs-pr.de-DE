---
title: Verwenden des eDiscovery-Export Tools in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Sie müssen die ClickOnce-Unterstützung aktivieren, um die neueste Version von Microsoft Edge zum Herunterladen von Suchergebnissen aus der Inhaltssuche und von eDiscovery im Security and Compliance Center zu verwenden.
ms.openlocfilehash: c48e3fb04747306693364a2cdbc6f18047a0fd9e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632380"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="1c3b2-103">Verwenden des eDiscovery-Export Tools in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1c3b2-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="1c3b2-104">Aufgrund der letzten Änderungen an der neuesten Version von Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="1c3b2-105">Um das eDiscovery-Export Tool zum Herunterladen der Inhaltssuche oder der eDiscovery-Suchergebnisse weiter verwenden zu können, müssen Sie entweder [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) verwenden oder die ClickOnce-Unterstützung in der neuesten Version von Microsoft Edge aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="1c3b2-106">Aktivieren der ClickOnce-Unterstützung in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1c3b2-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="1c3b2-107">Wechseln Sie in Microsoft Edge zu **Edge://Flags/#Edge-Click-Once**.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="1c3b2-108">Wenn der vorhandene Wert in der Dropdownliste auf **Standard** oder **deaktiviert** festgelegt ist, ändern Sie ihn in **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="1c3b2-109">Scrollen Sie nach unten zum Browserfenster, und klicken Sie auf **neu** starten, um Edge neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="1c3b2-110">**Hinweis:** Organisationen können mithilfe von Gruppenrichtlinien die ClickOnce-Unterstützung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="1c3b2-111">Um zu überprüfen, ob eine Organisationsrichtlinie für die ClickOnce-Unterstützung vorhanden ist, wechseln Sie zu **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-111">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="1c3b2-112">Der folgende Screenshot zeigt, dass ClickOnce in der gesamten Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="1c3b2-113">Wenn dieser Richtlinienwert auf **false**festgelegt ist, müssen Sie einen Administrator in Ihrer Organisation kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="1c3b2-114">Installieren und Ausführen des eDiscovery-Export Tools</span><span class="sxs-lookup"><span data-stu-id="1c3b2-114">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="1c3b2-115">Klicken Sie auf der Flyout-Seite eines Exports in Inhaltssuche oder eines eDiscovery-Falls auf " **Ergebnisse herunterladen** ".</span><span class="sxs-lookup"><span data-stu-id="1c3b2-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Klicken Sie auf der Flyout-Seite auf Download Ergebnisse, um Suchergebnisse herunterzuladen.](../media/ClickOnceExport1.png)

2. <span data-ttu-id="1c3b2-117">Sie werden mit einer Bestätigung aufgefordert, das Tool zu starten, indem Sie auf **Öffnen**klicken.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Klicken Sie auf öffnen, um das eDiscovery-Export Tool zu starten](../media/ClickOnceimage4.png)

   <span data-ttu-id="1c3b2-119">Wenn das eDiscovery-Export Tool nicht installiert ist, werden Sie mit einer Sicherheitswarnung aufgefordert,</span><span class="sxs-lookup"><span data-stu-id="1c3b2-119">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Klicken Sie auf installieren, um das eDiscovery-Export Tool zu installieren](../media/ClickOnceimage5.png)

3. <span data-ttu-id="1c3b2-121">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-121">Click **Install**.</span></span> <span data-ttu-id="1c3b2-122">Nachdem die Installation erfolgt ist, wird das Export Tool automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="1c3b2-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="1c3b2-123">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1c3b2-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1c3b2-124">Exportieren von Inhaltssuchergebnissen </span><span class="sxs-lookup"><span data-stu-id="1c3b2-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="1c3b2-125">Aktivieren von testmarkierungen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1c3b2-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
