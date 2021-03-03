---
title: Hinzufügen von Speicherplatz für Ihr Abonnement
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Dateispeicher in Ihrem Microsoft 365-Abonnement hinzufügen und reduzieren. Mit zusätzlichem Dateispeicher können Sie weitere Inhalte in SharePoint Online und OneDrive speichern.
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405888"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="5d6f1-104">Hinzufügen von Speicherplatz für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="5d6f1-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5d6f1-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-105">The admin center is changing.</span></span> <span data-ttu-id="5d6f1-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="5d6f1-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5d6f1-107">Wenn sich im Laufe der Zeit herausstellt, dass Sie nicht mehr über genügend Speicherplatz für Ihre SharePoint Online-Websitesammlungen verfügen, können Sie im Rahmen Ihres Abonnements zusätzlich weiteren Speicherplatz erwerben, wenn Sie gemäß Ihrem Plan dazu berechtigt sind. </span><span class="sxs-lookup"><span data-stu-id="5d6f1-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="5d6f1-108">Wenn der zusätzliche **Office 365-Dateispeicher** nicht in der Liste der verfügbaren Add-Ons angezeigt wird, bedeutet dies, dass Ihr Plan nicht berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="5d6f1-109">Weitere Informationen finden Sie unter [Ist mein Plan berechtigt?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="5d6f1-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="5d6f1-110">Wenn Sie Ihr Abonnement über Volumenlizenzierung oder einen CSP erworben haben, können Sie **Office 365 Extra File Storage** für Ihre Organisation nicht direkt von Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="5d6f1-111">Wenden Sie sich an Ihren Vertreter oder Partner, um Hilfe zu finden.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5d6f1-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="5d6f1-112">Before you begin</span></span>

<span data-ttu-id="5d6f1-113">Sie müssen ein globaler oder sharePoint-Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="5d6f1-114">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f1-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="5d6f1-115">Anzeigen des verfügbaren Speichers</span><span class="sxs-lookup"><span data-stu-id="5d6f1-115">View available storage</span></span>

1. <span data-ttu-id="5d6f1-116">Wechseln Sie im SharePoint Admin Center zur Seite <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Aktive</a> Websites, und melden Sie sich mit einem Konto an, das über [Administratorberechtigungen](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) für Ihre Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="5d6f1-117">Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="5d6f1-118">Wenn Ihre Organisation Multi-Geo in Office 365 konfiguriert hat, zeigt die Leiste auch die Speichermenge an, die an allen geografischen Standorten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="5d6f1-120">Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="5d6f1-121">Nachdem Sie ermittelt haben, wie viel Speicherplatz Sie verwenden, können Sie Speicherplatz für Ihr Abonnement hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="5d6f1-122">Um herauszufinden, wie viel das Hinzufügen von Speicherplatz kosten wird, führen Sie die Schritte in diesem Artikel aus, und überprüfen Sie die Preisinformationen, bevor Sie weitere Kaufen.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="5d6f1-123">Informationen zum Festlegen von Speichergrenzwerte für Websitesammlungen finden Sie [unter Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="5d6f1-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="5d6f1-124">Hinzufügen von Speicher zu Ihrem Abonnement</span><span class="sxs-lookup"><span data-stu-id="5d6f1-124">Add storage to your subscription</span></span>

<span data-ttu-id="5d6f1-125">Wenn Sie noch keinen zusätzlichen Speicher für Ihr Abonnement erworben haben, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="5d6f1-126">Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Abrechnungskaufdienste.</a></span><span class="sxs-lookup"><span data-stu-id="5d6f1-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="5d6f1-127">Suchen Sie unten auf der **Seite** Dienste kaufen im Abschnitt **Add-Ons** nach **Office 365 Extra File Storage,** und wählen Sie **Details aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="5d6f1-128">Wählen Sie auf der Seite Produktdetails die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="5d6f1-129">Wählen Sie bei Bedarf das Basisabonnement aus, und geben Sie die Speicheranzahl ein, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="5d6f1-130">Wählen **Sie Jetzt auschecken aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="5d6f1-131">Überprüfen Sie auf der Seite Wie sieht dies **aus?** die ausgewählte Speicheranzahl von Gigabyte aus, überprüfen Sie die Preisinformationen, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="5d6f1-132">Überprüfen Sie **auf der** Seite Bestellung abschließen die Gesamtsumme.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="5d6f1-133">Wenn Sie Änderungen vornehmen müssen, wählen Sie **Bearbeitungsreihenfolge aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="5d6f1-134">Wenn für die Bestellung eine Kreditwürdigkeitsprüfung erforderlich ist, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="5d6f1-135">Wenn Sie fertig sind, wählen Sie **Bestellung platzieren** \> **Wechseln zu Admin Home aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="5d6f1-136">Vergrößern oder Verkleinern des Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="5d6f1-136">Increase or decrease storage</span></span>

<span data-ttu-id="5d6f1-137">Wenn Sie bereits über das **Office 365 Extra File** Storage-Add-On zusätzlichen Dateispeicher erworben haben, können Sie diese Schritte ausführen, um den zusätzlichen Speicherplatz für Ihr Abonnement zu vergrößern oder zu verringern.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="5d6f1-138">Sie können den Speicher auf bis zu 1 Gigabyte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="5d6f1-139">Wenden Sie sich an den Support, um den zusätzlichen Speicherplatz [zu entfernen.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f1-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="5d6f1-140">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5d6f1-141">Wählen Sie **auf der** Registerkarte Produkte das Abonnement aus, das das **Office 365 Extra File Storage-Add-On** enthält.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="5d6f1-142">Wählen Sie auf der Seite Produktdetails im Abschnitt **Add-Ons** die Option **Add-Ons verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="5d6f1-143">Wählen Sie **im Bereich Add-Ons** verwalten in der Liste **Add-On** die Option **Office 365 Extra File Storage aus.**</span><span class="sxs-lookup"><span data-stu-id="5d6f1-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="5d6f1-144">Geben Sie **im** Textfeld Menge die Anzahl der GBs des Speicherplatzes ein, den Sie für das Abonnement wünschen.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="5d6f1-145">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="5d6f1-146">Bin ich im Rahmen meines Plans für Office 365 Extra File Storage berechtigt?</span><span class="sxs-lookup"><span data-stu-id="5d6f1-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="5d6f1-147">Office 365 Extra File Storage steht im Rahmen der folgenden Abonnements zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="5d6f1-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="5d6f1-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5d6f1-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="5d6f1-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="5d6f1-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="5d6f1-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5d6f1-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="5d6f1-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="5d6f1-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="5d6f1-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="5d6f1-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="5d6f1-153">Office für das Web mit SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="5d6f1-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="5d6f1-154">Office für das Web mit SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="5d6f1-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="5d6f1-155">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="5d6f1-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="5d6f1-156">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="5d6f1-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="5d6f1-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="5d6f1-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="5d6f1-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="5d6f1-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="5d6f1-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="5d6f1-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="5d6f1-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="5d6f1-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="5d6f1-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5d6f1-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="5d6f1-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="5d6f1-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="5d6f1-163">Office 365 Extra File Storage ist auch für GCC-, GCC High- und DOD-Pläne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d6f1-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="5d6f1-164">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5d6f1-164">Related content</span></span>

<span data-ttu-id="5d6f1-165">[Verwalten von Websitespeichergrenzwerte](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5d6f1-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="5d6f1-166">[Festlegen des Standardspeicherplatzes für #A0](https://docs.microsoft.com/onedrive/set-default-storage-space)(Artikel)</span><span class="sxs-lookup"><span data-stu-id="5d6f1-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>