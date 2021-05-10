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
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
- PPM_jmueller
ms.reviewer: drjones
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Dateispeicher in Ihrem Abonnement hinzufügen und Microsoft 365 können. Mit zusätzlichem Dateispeicher können Sie weitere Inhalte in SharePoint Online und OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: 14f72f59493be04165f0e7b28f26b14f8ae01a08
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293679"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="f8d8e-104">Hinzufügen von Speicherplatz für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="f8d8e-104">Add storage space for your subscription</span></span>

<span data-ttu-id="f8d8e-105">Wenn sich im Laufe der Zeit herausstellt, dass Sie nicht mehr über genügend Speicherplatz für Ihre SharePoint Online-Websitesammlungen verfügen, können Sie im Rahmen Ihres Abonnements zusätzlich weiteren Speicherplatz erwerben, wenn Sie gemäß Ihrem Plan dazu berechtigt sind. </span><span class="sxs-lookup"><span data-stu-id="f8d8e-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="f8d8e-106">Wenn die Office 365 Zusätzliche Datei **Storage** in der Liste der verfügbaren Add-Ons nicht angezeigt wird, bedeutet dies, dass Ihr Plan nicht berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="f8d8e-107">Weitere Informationen finden Sie unter [Ist mein Plan berechtigt?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="f8d8e-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="f8d8e-108">Wenn Sie Ihr Abonnement über Volumenlizenzierung oder einen CSP erworben haben, können Sie Office 365 Zusätzliche Datei **Storage** für Ihre Organisation nicht direkt von Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="f8d8e-109">Wenden Sie sich an Ihren Vertreter oder Partner, um Hilfe zu finden.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8d8e-110">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f8d8e-110">Before you begin</span></span>

<span data-ttu-id="f8d8e-111">Sie müssen ein globaler oder SharePoint administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="f8d8e-112">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f8d8e-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="f8d8e-113">Anzeigen des verfügbaren Speichers</span><span class="sxs-lookup"><span data-stu-id="f8d8e-113">View available storage</span></span>

1. <span data-ttu-id="f8d8e-114">Wechseln Sie SharePoint Admin Center zur Seite <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Aktive</a> Websites, und melden Sie sich mit einem Konto an, das über [Administratorberechtigungen](/sharepoint/sharepoint-admin-role) für Ihre Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="f8d8e-115">Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="f8d8e-116">Wenn Ihre Organisation Multi-Geo in Office 365 konfiguriert hat, zeigt die Leiste auch die Speichermenge an, die an allen geografischen Standorten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Speicherleiste auf der Seite „Aktive Websites“](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="f8d8e-118">Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="f8d8e-119">Nachdem Sie ermittelt haben, wie viel Speicherplatz Sie verwenden, können Sie Speicherplatz für Ihr Abonnement hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="f8d8e-120">Um herauszufinden, wie viel das Hinzufügen von Speicherplatz kosten wird, führen Sie die Schritte in diesem Artikel aus, und überprüfen Sie die Preisinformationen, bevor Sie weitere Kaufen.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="f8d8e-121">Informationen zum Festlegen von Speichergrenzwerte für Websitesammlungen finden Sie [unter Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="f8d8e-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="f8d8e-122">Hinzufügen von Speicher zu Ihrem Abonnement</span><span class="sxs-lookup"><span data-stu-id="f8d8e-122">Add storage to your subscription</span></span>

<span data-ttu-id="f8d8e-123">Wenn Sie noch keinen zusätzlichen Speicher für Ihr Abonnement erworben haben, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="f8d8e-124">Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Abrechnungskaufdienste.</a></span><span class="sxs-lookup"><span data-stu-id="f8d8e-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="f8d8e-125">Suchen Sie unten auf **der** Seite Dienste kaufen im Abschnitt **Add-Ons** nach Office 365 **Zusätzliche Datei Storage**, und wählen Sie Details **aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="f8d8e-126">Wählen Sie auf der Seite Produktdetails die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="f8d8e-127">Wählen Sie bei Bedarf das Basisabonnement aus, und geben Sie die Speicheranzahl ein, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="f8d8e-128">Wählen **Sie Jetzt auschecken aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="f8d8e-129">Überprüfen Sie auf der Seite Wie sieht dies **aus?** die ausgewählte Speicheranzahl von Gigabyte aus, überprüfen Sie die Preisinformationen, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="f8d8e-130">Überprüfen Sie **auf der** Seite Bestellung abschließen die Gesamtsumme.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="f8d8e-131">Wenn Sie Änderungen vornehmen müssen, wählen Sie **Bearbeitungsreihenfolge aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="f8d8e-132">Wenn für die Bestellung eine Kreditwürdigkeitsprüfung erforderlich ist, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="f8d8e-133">Wenn Sie fertig sind, wählen Sie **Bestellung platzieren** \> **Wechseln zu Admin Home aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="f8d8e-134">Vergrößern oder Verkleinern des Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="f8d8e-134">Increase or decrease storage</span></span>

<span data-ttu-id="f8d8e-135">Wenn Sie bereits zusätzlichen Dateispeicher über das Office 365 Extra File Storage-Add-On erworben haben, können Sie diese Schritte ausführen, um den zusätzlichen Speicherplatz für Ihr Abonnement zu vergrößern oder zu verringern. </span><span class="sxs-lookup"><span data-stu-id="f8d8e-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="f8d8e-136">Sie können den Speicher auf bis zu 1 Gigabyte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="f8d8e-137">Wenden Sie sich an den Support, um den zusätzlichen Speicherplatz [zu entfernen.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8e-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="f8d8e-138">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f8d8e-139">Wählen Sie **auf der** Registerkarte Produkte das Abonnement aus, das Office 365 Zusätzliche **Datei Storage** enthält.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="f8d8e-140">Wählen Sie auf der Seite Produktdetails im Abschnitt **Add-Ons** die Option **Add-Ons verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="f8d8e-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="f8d8e-141">Wählen Sie **im Bereich Add-Ons** verwalten in der Liste **Add-On** die Option **Office 365 Extra File Storage** aus.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="f8d8e-142">Geben Sie **im** Textfeld Menge die Anzahl der GBs des Speicherplatzes ein, den Sie für das Abonnement wünschen.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="f8d8e-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="f8d8e-144">Bin ich im Rahmen meines Plans für Office 365 Extra File Storage berechtigt?</span><span class="sxs-lookup"><span data-stu-id="f8d8e-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="f8d8e-145">Office 365 Extra File Storage steht im Rahmen der folgenden Abonnements zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f8d8e-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="f8d8e-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="f8d8e-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="f8d8e-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="f8d8e-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="f8d8e-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="f8d8e-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="f8d8e-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="f8d8e-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="f8d8e-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="f8d8e-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="f8d8e-151">Office für das Web mit SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="f8d8e-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="f8d8e-152">Office für das Web mit SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="f8d8e-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="f8d8e-153">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="f8d8e-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="f8d8e-154">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="f8d8e-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="f8d8e-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="f8d8e-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="f8d8e-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="f8d8e-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="f8d8e-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f8d8e-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="f8d8e-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f8d8e-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="f8d8e-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f8d8e-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="f8d8e-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="f8d8e-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="f8d8e-161">Office 365 Zusätzliche Datei Storage ist auch für GCC, GCC High- und DOD-Pläne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f8d8e-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="f8d8e-162">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f8d8e-162">Related content</span></span>

<span data-ttu-id="f8d8e-163">[Verwalten von Websitespeichergrenzwerte](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f8d8e-163">[Manage site storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="f8d8e-164">[Festlegen des Standardspeicherplatzes für OneDrive Benutzer](/onedrive/set-default-storage-space)(Artikel)</span><span class="sxs-lookup"><span data-stu-id="f8d8e-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>