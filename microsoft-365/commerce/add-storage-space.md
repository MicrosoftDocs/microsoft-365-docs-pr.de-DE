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
description: Erfahren Sie, wie Sie Dateispeicher in Ihrem Microsoft 365-Abonnement hinzufügen und reduzieren können. Mit zusätzlichem Dateispeicher können Sie mehr Inhalte in SharePoint Online und OneDrive speichern.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114907"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="c653b-104">Hinzufügen von Speicherplatz für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="c653b-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c653b-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="c653b-105">The admin center is changing.</span></span> <span data-ttu-id="c653b-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="c653b-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="c653b-107">Wenn sich im Laufe der Zeit herausstellt, dass Sie nicht mehr über genügend Speicherplatz für Ihre SharePoint Online-Websitesammlungen verfügen, können Sie im Rahmen Ihres Abonnements zusätzlich weiteren Speicherplatz erwerben, wenn Sie gemäß Ihrem Plan dazu berechtigt sind. </span><span class="sxs-lookup"><span data-stu-id="c653b-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="c653b-108">Wenn der zusätzliche Dateispeicher für **Office 365** nicht in der Liste der verfügbaren Add-Ons angezeigt wird, bedeutet dies, dass Ihr Plan nicht berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="c653b-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="c653b-109">Weitere Informationen finden Sie unter ["Ist mein Plan berechtigt?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="c653b-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="c653b-110">Wenn Sie Ihr Abonnement über Volumenlizenzierung oder einen CSP erworben haben, können Sie **Office 365 Zusätzlichen** Dateispeicher für Ihre Organisation nicht direkt von Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="c653b-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="c653b-111">Wenden Sie sich an Ihren Vertreter oder Partner, um Hilfe zu finden.</span><span class="sxs-lookup"><span data-stu-id="c653b-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c653b-112">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="c653b-112">Before you begin</span></span>

<span data-ttu-id="c653b-113">Sie müssen ein globaler oder ein SharePoint-Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="c653b-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="c653b-114">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c653b-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="c653b-115">Anzeigen des verfügbaren Speichers</span><span class="sxs-lookup"><span data-stu-id="c653b-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c653b-116">Wechseln Sie im SharePoint Admin Center zur Seite <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">"Aktive</a> Websites", und melden Sie sich mit einem Konto an, das über Administratorberechtigungen [für](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) Ihre Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="c653b-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="c653b-117">Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="c653b-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="c653b-118">Wenn Ihre Organisation Multi-Geo in Office 365 konfiguriert hat, zeigt die Leiste auch die Menge an Speicherplatz an, die an allen geografischen Standorten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c653b-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c653b-120">Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="c653b-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c653b-121">Melden Sie sich als globaler Administrator oder Als SharePoint-Administrator an, und wählen Sie dann die Kachel https://portal.office.de "Admin" aus, um das Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c653b-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c653b-122">Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie nicht über Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="c653b-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c653b-123">Wählen Sie im linken Bereich unter **Admin Center** **SharePoint aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c653b-124">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c653b-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c653b-125">Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c653b-126">Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="c653b-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c653b-128">Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="c653b-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c653b-129">Melden Sie sich als globaler Administrator oder Als SharePoint-Administrator an, und wählen Sie dann die Kachel https://login.partner.microsoftonline.cn/ "Admin" aus, um das Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c653b-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c653b-130">(Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie nicht über Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="c653b-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c653b-131">Wählen Sie im linken Bereich unter **Admin Center** **SharePoint aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c653b-132">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c653b-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c653b-133">Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c653b-134">Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="c653b-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c653b-136">Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="c653b-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="c653b-137">Nachdem Sie festgestellt haben, wie viel Speicherplatz Sie verwenden, können Sie Speicherplatz für Ihr Abonnement hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="c653b-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="c653b-138">Um herauszufinden, wie viel das Hinzufügen von Speicherplatz kosten wird, führen Sie die Schritte in diesem Artikel aus, und überprüfen Sie die Preisinformationen, bevor Sie den Kauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="c653b-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="c653b-139">Informationen zum Festlegen von Speichergrenzwerte für Websitesammlungen finden Sie unter ["Verwalten von Speichergrenzwerte für Websitesammlungen".](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="c653b-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="c653b-140">Hinzufügen von Speicher zu Ihrem Abonnement</span><span class="sxs-lookup"><span data-stu-id="c653b-140">Add storage to your subscription</span></span>

<span data-ttu-id="c653b-141">Wenn Sie noch keinen zusätzlichen Speicher für Ihr Abonnement erworben haben, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="c653b-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c653b-142">Wechseln Sie im Admin Center zur **Seite** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">"Abrechnungskaufdienste".</a></span><span class="sxs-lookup"><span data-stu-id="c653b-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="c653b-143">Wählen Sie unten auf der **Seite "Dienste** kaufen" die **Option "Add-Ons" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="c653b-144">Wählen **Sie Office 365 Zusätzlichen Dateispeicher aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="c653b-145">Wählen Sie auf der **Seite "Zusätzlicher Dateispeicher für Office 365"** (falls angezeigt) das Basisabonnement aus, und geben Sie dann die Anzahl der Gigabyte an Speicher ein, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c653b-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="c653b-146">Wählen **Sie "Jetzt auschecken" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="c653b-147">Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="c653b-148">Überprüfen Sie **auf der Seite "Bestellung** abschließen" den Gesamtwert.</span><span class="sxs-lookup"><span data-stu-id="c653b-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="c653b-149">Wenn Sie Änderungen vornehmen müssen, wählen Sie **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="c653b-150">Wenn für die Bestellung eine Bonitätsprüfung erforderlich ist, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="c653b-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="c653b-151">Wenn Sie fertig sind, wählen Sie **"Bestellung bestellen"** \> **auf "Admin Home" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c653b-152">Wechseln Sie im Admin  Center zur Seite "Abrechnungsabonnements". \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank"></a>  </span><span class="sxs-lookup"><span data-stu-id="c653b-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c653b-153">Wählen Sie **auf der** Seite "Abonnements" das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **"Add-Ons" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c653b-155">Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c653b-156">Wählen **Sie "Add-Ons kaufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-156">Select **Buy add-ons**.</span></span>

    ![Kaufen Sie den Link "Add-Ons" auf der Seite "Abonnements" im Admin Center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c653b-158">Bewegen Oder tippen **Sie auf** der Seite "Dienste kaufen" mit der Maus auf den zusätzlichen Dateispeicher für **Office 365,** und wählen Sie dann **"Jetzt kaufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c653b-159">Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls angezeigt, ein Basisabonnement aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c653b-160">Wählen **Sie "Jetzt auschecken" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c653b-161">Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c653b-162">Wählen Sie **auf der Seite "Bestellung abschließen"** die Option **"Bestellung bestellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c653b-163">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="c653b-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c653b-164">Wählen Sie **auf der** Seite "Abonnements" das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **"Add-Ons" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c653b-166">Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c653b-167">Wählen **Sie "Add-Ons kaufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-167">Select **Buy add-ons**.</span></span>

    ![Kaufen Sie den Link "Add-Ons" auf der Seite "Abonnements" im Admin Center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c653b-169">Bewegen Oder tippen **Sie auf** der Seite "Dienste kaufen" mit der Maus auf den zusätzlichen Dateispeicher für **Office 365,** und wählen Sie dann **"Jetzt kaufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c653b-170">Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls angezeigt, ein Basisabonnement aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c653b-171">Wählen **Sie "Jetzt auschecken" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c653b-172">Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c653b-173">Wählen Sie **auf der Seite "Bestellung abschließen"** die Option **"Bestellung bestellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="c653b-174">Vergrößern oder Verkleinern des Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="c653b-174">Increase or decrease storage</span></span>

<span data-ttu-id="c653b-175">Wenn Sie bereits zusätzlichen Dateispeicher über das **Office 365-Add-On** "Zusätzlicher Dateispeicher" erworben haben, können Sie die folgenden Schritte ausführen, um den zusätzlichen Speicherplatz für Ihr Abonnement zu vergrößern oder zu verringern.</span><span class="sxs-lookup"><span data-stu-id="c653b-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="c653b-176">Sie können den Speicher auf bis zu 1 Gigabyte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="c653b-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="c653b-177">Wenden Sie sich an den Support, um den zusätzlichen Speicherplatz [zu entfernen.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="c653b-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c653b-178">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="c653b-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="c653b-179">Wählen Sie **auf der** Registerkarte "Produkte" das Abonnement aus, das das **Office 365-Add-On "Zusätzlicher Dateispeicher"** enthält.</span><span class="sxs-lookup"><span data-stu-id="c653b-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="c653b-180">Wählen Sie auf der Seite "Produktdetails" im Abschnitt **"Add-Ons"** die Option **"Add-Ons verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="c653b-181">Wählen Sie **im Bereich "Add-Ons** verwalten" in der **Add-On-Liste** die Option **"Office 365 Zusätzlicher Dateispeicher" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="c653b-182">Geben Sie **im** Textfeld "Menge" die Anzahl der GBs an Speicherplatz ein, die Sie für das Abonnement wünschen.</span><span class="sxs-lookup"><span data-stu-id="c653b-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="c653b-183">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c653b-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c653b-184">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="c653b-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c653b-185">Wählen Sie **auf der** Seite "Abonnements" die **Option "Add-Ons" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c653b-187">Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c653b-188">Wählen **Sie unter Office 365 Zusätzlicher Dateispeicher** die Option **"Menge ändern" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c653b-190">Geben Sie im rechten Bereich die Gesamtzahl der benötigten Gigabyte ein, und wählen Sie **"Absenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c653b-191">Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="c653b-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c653b-192">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c653b-193">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="c653b-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c653b-194">Wählen Sie **auf der** Seite "Abonnements" die **Option "Add-Ons" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c653b-196">Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c653b-197">Wählen **Sie unter Office 365 Zusätzlicher Dateispeicher** die Option **"Menge ändern" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c653b-199">Geben Sie im rechten Bereich die Gesamtzahl der benötigten Gigabyte ein, und wählen Sie **"Absenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="c653b-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c653b-200">Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="c653b-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c653b-201">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="c653b-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="c653b-202">Bin ich im Rahmen meines Plans für Office 365 Extra File Storage berechtigt?</span><span class="sxs-lookup"><span data-stu-id="c653b-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="c653b-203">Office 365 Extra File Storage steht im Rahmen der folgenden Abonnements zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c653b-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="c653b-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c653b-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="c653b-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="c653b-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="c653b-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c653b-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="c653b-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="c653b-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="c653b-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c653b-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="c653b-209">Office für das Web mit SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="c653b-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="c653b-210">Office für das Web mit SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="c653b-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="c653b-211">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="c653b-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="c653b-212">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="c653b-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="c653b-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="c653b-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="c653b-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="c653b-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="c653b-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c653b-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="c653b-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="c653b-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="c653b-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c653b-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="c653b-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="c653b-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="c653b-219">Office 365 Zusätzlicher Dateispeicher ist auch für GCC-, GCC High- und DOD-Pläne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c653b-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="c653b-220">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="c653b-220">Related content</span></span>

<span data-ttu-id="c653b-221">[Verwalten von Websitespeichergrenzwerte](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="c653b-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="c653b-222">[Festlegen des Standardspeicherplatzes für #A0](https://docs.microsoft.com/onedrive/set-default-storage-space)(Artikel)</span><span class="sxs-lookup"><span data-stu-id="c653b-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
