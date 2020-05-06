---
title: Verwalten von Self-Service-Käufen (Administratoren)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Administratoren können sich mit der Verwaltung von Self-Service-Käufen von Benutzern in Ihrer Organisation vertraut machen.
ms.openlocfilehash: 7074a829bed3e65a160a9a33afb4f2b130f6c8d1
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046180"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="5c20c-103">Self-Service-Einkäufe (Administrator) verwalten</span><span class="sxs-lookup"><span data-stu-id="5c20c-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="5c20c-104">Als Administrator können Sie Self-Service-Käufe anzeigen, die von Personen in Ihrer Organisation getätigt wurden.</span><span class="sxs-lookup"><span data-stu-id="5c20c-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="5c20c-105">Sie können das Produkt, den Käufer Namen, die erworbenen Abonnements, das Ablaufdatum, den Kaufpreis und die zugewiesenen Benutzer für jeden Self-Service-Einkauf sehen.</span><span class="sxs-lookup"><span data-stu-id="5c20c-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="5c20c-106">Wenn es für Ihre Organisation erforderlich ist, können Sie Self-Service-Einkauf pro Produkt über PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5c20c-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5c20c-107">Sie haben die gleichen Datenverwaltungsdienste und Zugriffsrichtlinien für Produkte, die über Self-Service Purchase oder zentral erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="5c20c-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="5c20c-108">Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="5c20c-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="5c20c-109">Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c20c-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="5c20c-110">Anzeigen von Self-Service-Abonnements</span><span class="sxs-lookup"><span data-stu-id="5c20c-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="5c20c-111">Wechseln Sie im Admin Center zur Seite **Fakturierung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .</span><span class="sxs-lookup"><span data-stu-id="5c20c-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="5c20c-112">Klicken Sie neben **Ergebnisse Verfeinern**in der Dropdownliste **Kontotyp** auf **Self-Service**.</span><span class="sxs-lookup"><span data-stu-id="5c20c-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="5c20c-113">Um weitere Details zu einem Abonnement anzuzeigen, wählen Sie eines aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5c20c-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="5c20c-114">Anzeigen, wer über Lizenzen für ein Self-Service-Abonnement für den Kauf verfügt</span><span class="sxs-lookup"><span data-stu-id="5c20c-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="5c20c-115">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="5c20c-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="5c20c-116">Klicken Sie auf das Filtersymbol, und wählen Sie dann **Self-Service**aus.</span><span class="sxs-lookup"><span data-stu-id="5c20c-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="5c20c-117">Wählen Sie ein Produkt aus, um den Personen zugewiesene Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c20c-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c20c-118">Wenn es mehrere Käufe für ein Produkt gibt, wird dieses Produkt nur einmal aufgeführt, und die Spalte **verfügbare Menge** zeigt die Summe aller Abonnements an, die für dieses Produkt erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="5c20c-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="5c20c-119">Die **Benutzer** Liste wird nach den Namen von Personen gruppiert, die Self-Service-Käufe getätigt haben.</span><span class="sxs-lookup"><span data-stu-id="5c20c-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="5c20c-120">Um eine Liste der Benutzer mit Lizenzen für diese Abonnements zu exportieren, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie dann **Benutzer exportieren**aus.</span><span class="sxs-lookup"><span data-stu-id="5c20c-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="5c20c-121">Deaktivieren oder Aktivieren von Self-Service-Käufen</span><span class="sxs-lookup"><span data-stu-id="5c20c-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="5c20c-122">Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5c20c-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="5c20c-123">Das **MSCommerce** PowerShell-Modul enthält einen Parameterwert für die **Richtlinien** -Nr für **AllowSelfServicePurchase** , mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können, und für welche Produkte.</span><span class="sxs-lookup"><span data-stu-id="5c20c-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="5c20c-124">Sie können das **MSCommerce** -PowerShell-Modul verwenden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="5c20c-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="5c20c-125">Anzeigen des Standardstatus des **AllowSelfServicePurchase** -Parameterwerts &mdash; , ob er nach Produkt aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="5c20c-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="5c20c-126">Anzeigen einer Liste der anwendbaren Produkte und der Aktivierung oder Deaktivierung von Self-Service-Käufen</span><span class="sxs-lookup"><span data-stu-id="5c20c-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="5c20c-127">Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es entweder zu aktivieren oder zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5c20c-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="5c20c-128">Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c20c-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="5c20c-129">Zentralisieren von Lizenzen unter einem einzelnen Abonnement</span><span class="sxs-lookup"><span data-stu-id="5c20c-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="5c20c-130">Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über vorhandene Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5c20c-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="5c20c-131">Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen.</span><span class="sxs-lookup"><span data-stu-id="5c20c-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="5c20c-132">Melden Sie sich mit ihrem globalen Administrator-oder abrechnungsadministrator Konto beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> an.</span><span class="sxs-lookup"><span data-stu-id="5c20c-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="5c20c-133">Wechseln Sie zur Seite **Abrechnungs** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Einkaufsdienste</a> .</span><span class="sxs-lookup"><span data-stu-id="5c20c-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="5c20c-134">Suchen und wählen Sie das Produkt aus, das Sie kaufen möchten, und wählen Sie dann **kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="5c20c-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="5c20c-135">Führen Sie die restlichen Schritte aus, um den Kauf abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5c20c-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="5c20c-136">Befolgen Sie die Schritte unter [anzeigen, wer über Lizenzen für ein Self-Service-Abonnement verfügt](#view-who-has-licenses-for-a-self-service-purchase-subscription) , um eine Liste der in Schritt 6 zu referenzierenden Benutzer zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="5c20c-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="5c20c-137">Zuweisen von Lizenzen zu allen Personen, die eine Lizenz im anderen Abonnement haben.</span><span class="sxs-lookup"><span data-stu-id="5c20c-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="5c20c-138">Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="5c20c-138">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="5c20c-139">Wenden Sie sich an die Person, die das Self-Service-Abonnement erworben hat, und bitten Sie Sie, diese zu stornieren.</span><span class="sxs-lookup"><span data-stu-id="5c20c-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="5c20c-140">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="5c20c-140">Need help?</span></span> <span data-ttu-id="5c20c-141">Kontaktieren Sie uns.</span><span class="sxs-lookup"><span data-stu-id="5c20c-141">Contact us.</span></span>

<span data-ttu-id="5c20c-142">Häufige Fragen zum Self-Service-Einkauf finden Sie unter [Self-Service Purchases FAQ](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5c20c-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="5c20c-143">Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, [wenden Sie sich an den Support](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="5c20c-143">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
