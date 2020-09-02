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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie den Dateispeicher in Ihrem Microsoft 365-Abonnement hinzufügen und reduzieren. Bei zusätzlichem Dateispeicher können Sie weitere Inhalte in SharePoint Online und OneDrive speichern.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324468"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="7b3f4-104">Hinzufügen von Speicherplatz für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="7b3f4-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7b3f4-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-105">The admin center is changing.</span></span> <span data-ttu-id="7b3f4-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7b3f4-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="7b3f4-107">Wenn sich im Laufe der Zeit herausstellt, dass Sie nicht mehr über genügend Speicherplatz für Ihre SharePoint Online-Websitesammlungen verfügen, können Sie im Rahmen Ihres Abonnements zusätzlich weiteren Speicherplatz erwerben, wenn Sie gemäß Ihrem Plan dazu berechtigt sind. </span><span class="sxs-lookup"><span data-stu-id="7b3f4-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="7b3f4-108">Wenn in der Liste der verfügbaren Add-ons der **Office 365 zusätzliche Dateispeicherung** nicht angezeigt wird, bedeutet dies, dass Ihr Plan nicht berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="7b3f4-109">Weitere Informationen finden Sie unter [ist mein Plan berechtigt?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="7b3f4-110">Wenn Sie Ihr Abonnement über Volumenlizenzierung oder einen CSP erworben haben, können Sie **Office 365 zusätzlichen Dateispeicher** für Ihre Organisation nicht direkt von Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="7b3f4-111">Wenden Sie sich an Ihren Vertreter oder Partner, um Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7b3f4-112">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="7b3f4-112">Before you begin</span></span>

<span data-ttu-id="7b3f4-113">Sie müssen ein globaler oder SharePoint-Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="7b3f4-114">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7b3f4-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="7b3f4-115">Anzeigen des verfügbaren Speichers</span><span class="sxs-lookup"><span data-stu-id="7b3f4-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b3f4-116">Wechseln Sie im SharePoint Admin Center zur Seite <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">aktive Websites</a> , und melden Sie sich mit einem Konto an, das über [Administratorberechtigungen](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) für Ihre Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="7b3f4-117">In der oberen rechten Ecke der Seite sehen Sie, wie viel Speicherplatz für alle Websites verwendet wird, und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="7b3f4-118">Wenn in Ihrer Organisation Multi-Geo in Office 365 konfiguriert wurde, zeigt der Balken auch die Menge an Speicherplatz an, die für alle geografischen Standorte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Speicher Leiste auf der Seite "aktive Websites"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="7b3f4-120">Der verwendete Speicher umfasst keine Änderungen, die innerhalb der letzten 24-48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b3f4-121">Melden Sie sich bei https://portal.office.de als globaler oder SharePoint-Administrator an, und wählen Sie dann die Kachel admin aus, um das Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="7b3f4-122">Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie über keine Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="7b3f4-123">Wählen Sie im linken Bereich unter **Admin Center**die Option **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="7b3f4-124">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="7b3f4-125">Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="7b3f4-126">In der oberen rechten Ecke der Seite sehen Sie, wie viel Speicherplatz für alle Websites verwendet wird, und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Speicher Leiste auf der Seite "aktive Websites"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="7b3f4-128">Der verwendete Speicher umfasst keine Änderungen, die innerhalb der letzten 24-48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b3f4-129">Melden Sie sich bei https://login.partner.microsoftonline.cn/ als globaler oder SharePoint-Administrator an, und wählen Sie dann die Kachel admin aus, um das Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="7b3f4-130">(Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie über keine Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="7b3f4-131">Wählen Sie im linken Bereich unter **Admin Center**die Option **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="7b3f4-132">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="7b3f4-133">Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="7b3f4-134">In der oberen rechten Ecke der Seite sehen Sie, wie viel Speicherplatz für alle Websites verwendet wird, und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Speicher Leiste auf der Seite "aktive Websites"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="7b3f4-136">Der verwendete Speicher umfasst keine Änderungen, die innerhalb der letzten 24-48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="7b3f4-137">Nachdem Sie festgestellt haben, wie viel Speicherplatz Sie verwenden, können Sie Speicherplatz für Ihr Abonnement hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="7b3f4-138">Um herauszufinden, wie viel Speicherplatz hinzugefügt werden kann, befolgen Sie die Schritte in diesem Artikel, und überprüfen Sie die Preisinformationen vor dem Kauf.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="7b3f4-139">Informationen zum Festlegen von Speichergrenzwerten für Websitesammlungen finden Sie unter [Manage Site Collection Storage Limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="7b3f4-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="7b3f4-140">Hinzufügen von Speicher zu Ihrem Abonnement</span><span class="sxs-lookup"><span data-stu-id="7b3f4-140">Add storage to your subscription</span></span>

<span data-ttu-id="7b3f4-141">Wenn Sie noch keinen zusätzlichen Speicherplatz für Ihr Abonnement erworben haben, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b3f4-142">Wechseln Sie im Admin Center zur Seite **Abrechnungs** - \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Einkaufsdienste</a> .</span><span class="sxs-lookup"><span data-stu-id="7b3f4-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="7b3f4-143">Wählen Sie unten auf der Seite " **Einkaufsdienste** " **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="7b3f4-144">Wählen Sie **Office 365 zusätzlichen Dateispeicher**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="7b3f4-145">Wählen Sie auf der Seite **zusätzliche Dateispeicher Office 365** , falls angezeigt, das Basisabonnement aus, und geben Sie dann die Anzahl von Gigabyte Speicher ein, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="7b3f4-146">Wählen Sie **jetzt Auschecken aus**.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="7b3f4-147">Überprüfen Sie auf der Seite **wie sieht** das aus? die Anzahl von Gigabytes Speicher, die Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="7b3f4-148">Überprüfen Sie auf der Seite **vollständige Bestellung** die Summe.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="7b3f4-149">Wenn Sie Änderungen vornehmen müssen, wählen Sie **Bestellung bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="7b3f4-150">Wenn für die Bestellung eine Bonitätsprüfung erforderlich ist, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="7b3f4-151">Wenn Sie fertig sind, klicken Sie auf **Bestellung aufgeben** , \> **um zu admin Home zu wechseln**.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b3f4-152">Wechseln Sie im Admin Center zur Seite **Abrechnungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a> .  </span><span class="sxs-lookup"><span data-stu-id="7b3f4-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7b3f4-153">Wählen Sie auf der Seite **Abonnements** das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7b3f4-155">Wenn **Add-ons**nicht angezeigt werden und Ihr Abonnement über einen Partner erworben wurde, wählen Sie **Volume Licensing Service Center (VLSC)** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7b3f4-156">Wählen Sie **Add-ons kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-156">Select **Buy add-ons**.</span></span>

    ![Link "Add-ons kaufen" auf der Seite "Abonnements" des Admin Centers.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="7b3f4-158">Klicken Sie auf der Seite " **Dienste kaufen** " mit der Maus oder tippen Sie auf **Office 365 zusätzlichen Dateispeicher**, und wählen Sie dann **Jetzt kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="7b3f4-159">Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls dies angezeigt wird, ein Basisabonnement aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="7b3f4-160">Wählen Sie **jetzt Auschecken aus**.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="7b3f4-161">Überprüfen Sie auf der Seite **wie sieht** das aus? die Anzahl von Gigabytes Speicher, die Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="7b3f4-162">Wählen Sie auf der Seite **vollständige Bestellung** die Option **Bestellung platzieren**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b3f4-163">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7b3f4-164">Wählen Sie auf der Seite **Abonnements** das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7b3f4-166">Wenn **Add-ons**nicht angezeigt werden und Ihr Abonnement über einen Partner erworben wurde, wählen Sie **Volume Licensing Service Center (VLSC)** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7b3f4-167">Wählen Sie **Add-ons kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-167">Select **Buy add-ons**.</span></span>

    ![Link "Add-ons kaufen" auf der Seite "Abonnements" des Admin Centers.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="7b3f4-169">Klicken Sie auf der Seite " **Dienste kaufen** " mit der Maus oder tippen Sie auf **Office 365 zusätzlichen Dateispeicher**, und wählen Sie dann **Jetzt kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="7b3f4-170">Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls dies angezeigt wird, ein Basisabonnement aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="7b3f4-171">Wählen Sie **jetzt Auschecken aus**.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="7b3f4-172">Überprüfen Sie auf der Seite **wie sieht** das aus? die Anzahl von Gigabytes Speicher, die Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="7b3f4-173">Wählen Sie auf der Seite **vollständige Bestellung** die Option **Bestellung platzieren**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="7b3f4-174">Vergrößern oder Verkleinern des Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="7b3f4-174">Increase or decrease storage</span></span>

<span data-ttu-id="7b3f4-175">Wenn Sie bereits über das **Office 365 extra File Storage** -Add-on zusätzlichen Dateispeicher erworben haben, können Sie diese Schritte verwenden, um den zusätzlichen Speicherplatz für Ihr Abonnement zu erweitern oder zu verringern.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="7b3f4-176">Sie können den Speicher auf so niedrig wie 1 Gigabyte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="7b3f4-177">Wenn Sie den gesamten zusätzlichen Speicherplatz entfernen möchten, [wenden Sie sich](../admin/contact-support-for-business-products.md)an den Support.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b3f4-178">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="7b3f4-179">Wählen Sie auf der Registerkarte **Produkte** das Abonnement aus, das das Add-on für **Office 365 zusätzlichen Dateispeicher** enthält.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="7b3f4-180">Wählen Sie auf der Seite Produkt Details im Abschnitt **Add-ons** die Option **Add-ons verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="7b3f4-181">Wählen Sie im Bereich **Add-ons verwalten** in der **Add-on-** Liste **Office 365 zusätzlichen Dateispeicher**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="7b3f4-182">Geben Sie im Textfeld **Menge** die Anzahl der GBs des Speicherplatzes ein, den Sie für das Abonnement benötigen.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="7b3f4-183">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b3f4-184">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7b3f4-185">Wählen Sie auf der Seite **Abonnements** die Option **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7b3f4-187">Wenn **Add-ons**nicht angezeigt werden und Ihr Abonnement über einen Partner erworben wurde, wählen Sie **Volume Licensing Service Center (VLSC)** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7b3f4-188">Wählen Sie unter **Office 365 zusätzlicher Dateispeicher**die Option **Menge ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="7b3f4-190">Geben Sie im rechten Bereich die Gesamtanzahl von Gigabytes ein, die Sie benötigen, und wählen Sie dann **Absenden**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="7b3f4-191">Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="7b3f4-192">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b3f4-193">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7b3f4-194">Wählen Sie auf der Seite **Abonnements** die Option **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7b3f4-196">Wenn **Add-ons**nicht angezeigt werden und Ihr Abonnement über einen Partner erworben wurde, wählen Sie **Volume Licensing Service Center (VLSC)** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7b3f4-197">Wählen Sie unter **Office 365 zusätzlicher Dateispeicher**die Option **Menge ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="7b3f4-199">Geben Sie im rechten Bereich die Gesamtanzahl von Gigabytes ein, die Sie benötigen, und wählen Sie dann **Absenden**aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="7b3f4-200">Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="7b3f4-201">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="7b3f4-202">Bin ich im Rahmen meines Plans für Office 365 Extra File Storage berechtigt?</span><span class="sxs-lookup"><span data-stu-id="7b3f4-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="7b3f4-203">Office 365 Extra File Storage steht im Rahmen der folgenden Abonnements zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="7b3f4-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="7b3f4-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="7b3f4-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="7b3f4-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="7b3f4-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="7b3f4-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="7b3f4-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="7b3f4-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="7b3f4-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="7b3f4-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="7b3f4-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="7b3f4-209">Office für das Internet mit SharePoint-Plan 1</span><span class="sxs-lookup"><span data-stu-id="7b3f4-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="7b3f4-210">Office für das Internet mit SharePoint-Plan 2</span><span class="sxs-lookup"><span data-stu-id="7b3f4-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="7b3f4-211">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="7b3f4-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="7b3f4-212">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="7b3f4-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="7b3f4-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="7b3f4-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="7b3f4-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="7b3f4-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="7b3f4-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="7b3f4-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="7b3f4-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="7b3f4-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="7b3f4-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b3f4-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="7b3f4-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="7b3f4-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="7b3f4-219">Office 365 zusätzliche Dateispeicherung steht auch für gcc-, gcc-High-und DoD-Pläne zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7b3f4-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="7b3f4-220">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="7b3f4-220">Related content</span></span>

<span data-ttu-id="7b3f4-221">[Verwalten von Websitespeicher Grenzwerten](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="7b3f4-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="7b3f4-222">[Festlegen des Standardspeicher Platzes für OneDrive-Benutzer](https://docs.microsoft.com/onedrive/set-default-storage-space)(Artikel)</span><span class="sxs-lookup"><span data-stu-id="7b3f4-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
