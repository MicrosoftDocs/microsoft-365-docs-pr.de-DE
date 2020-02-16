---
title: Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge
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
ROBOTS: NOINDEX, NOFOLLOW
description: Sie müssen die ClickOnce-Unterstützung aktivieren, um Microsoft Edge zum Exportieren von Suchergebnissen aus der Inhaltssuche und von eDiscovery im Security and Compliance Center zu verwenden.
ms.openlocfilehash: db70b4cdbc57f519db3b6b962eb8aa43585ba335
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078570"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="e77f3-103">Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e77f3-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="e77f3-104">Aufgrund der letzten Änderungen an Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e77f3-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="e77f3-105">Um das eDiscovery-Export Tool Microsoft Office 365 zum Herunterladen von Inhaltssuche oder eDiscovery-Suchergebnissen weiterhin zu verwenden, müssen Sie entweder [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) verwenden oder die ClickOnce-Unterstützung in Microsoft Edge aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e77f3-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="e77f3-106">Vorgehensweise Aktivieren der ClickOnce-Unterstützung in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e77f3-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="e77f3-107">Navigieren Sie in Microsoft Edge zu **Edge://Flags/#Edge-Click-Once**.</span><span class="sxs-lookup"><span data-stu-id="e77f3-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="e77f3-108">Wenn der vorhandene Wert in der Dropdownliste auf **Standard** oder **deaktiviert** festgelegt ist, ändern Sie ihn in **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="e77f3-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="e77f3-109">Scrollen Sie nach unten zum Browserfenster, und klicken Sie auf **neu** starten, um Edge neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="e77f3-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="e77f3-110">**Hinweis:** Organisationen können mithilfe von Gruppenrichtlinien die ClickOnce-Unterstützung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e77f3-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="e77f3-111">Um zu überprüfen, ob eine Organisationsrichtlinie für die ClickOnce-Unterstützung vorhanden ist, navigieren Sie zu **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="e77f3-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="e77f3-112">Der folgende Screenshot zeigt, dass ClickOnce in der gesamten Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e77f3-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="e77f3-113">Wenn dieser Richtlinienwert auf **false**festgelegt ist, müssen Sie einen Administrator in Ihrer Organisation kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="e77f3-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="e77f3-114">Installieren und Ausführen des Office 365 eDiscovery-Export Tools</span><span class="sxs-lookup"><span data-stu-id="e77f3-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="e77f3-115">Klicken Sie auf der Flyout-Seite eines Exports in Inhaltssuche oder eines eDiscovery-Falls auf " **Ergebnisse herunterladen** ".</span><span class="sxs-lookup"><span data-stu-id="e77f3-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Klicken Sie auf der Flyout-Seite auf Download Ergebnisse, um Suchergebnisse herunterzuladen.](../media/ClickOnceExport1.png)

2. <span data-ttu-id="e77f3-117">Sie werden mit einer Bestätigung aufgefordert, das Tool zu starten, indem Sie auf **Öffnen**klicken.</span><span class="sxs-lookup"><span data-stu-id="e77f3-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Klicken Sie auf öffnen, um das eDiscovery-Export Tool zu starten](../media/ClickOnceimage4.png)

   <span data-ttu-id="e77f3-119">Wenn das Microsoft Office-eDiscovery-Export Tool 365 nicht installiert ist, werden Sie mit einer Sicherheitswarnung aufgefordert,</span><span class="sxs-lookup"><span data-stu-id="e77f3-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Klicken Sie auf installieren, um das eDiscovery-Export Tool zu installieren](../media/ClickOnceimage5.png)

3. <span data-ttu-id="e77f3-121">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="e77f3-121">Click **Install**.</span></span> <span data-ttu-id="e77f3-122">Nachdem die Installation erfolgt ist, wird das Export Tool automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="e77f3-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="e77f3-123">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e77f3-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="e77f3-124">Exportieren von Inhaltssuchergebnissen </span><span class="sxs-lookup"><span data-stu-id="e77f3-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="e77f3-125">Aktivieren von testmarkierungen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e77f3-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
