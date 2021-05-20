---
title: Zuweisen von Lizenzen an Benutzer
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Weisen Sie Lizenzen zu, je nachdem, ob Sie bestimmten Benutzern Produktlizenzen oder Benutzerlizenzen für ein bestimmtes Produkt zuweisen möchten.
ms.date: 04/26/2021
ms.openlocfilehash: 707c1c952aa737f0aa91d886e9fa304eabe26321
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537535"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="82c2b-103">Zuweisen von Lizenzen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="82c2b-103">Assign licenses to users</span></span>

<span data-ttu-id="82c2b-104">Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="82c2b-105">Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="82c2b-106">Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="82c2b-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="82c2b-107">Sie können ein [Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="82c2b-108">[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="82c2b-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82c2b-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="82c2b-109">Before you begin</span></span>

- <span data-ttu-id="82c2b-110">Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="82c2b-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="82c2b-111">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="82c2b-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="82c2b-112">Sie können [Microsoft 365-Lizenzen mit PowerShell zu Benutzerkonten zuweisen](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="82c2b-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="82c2b-113">Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="82c2b-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="82c2b-114">Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="82c2b-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="82c2b-115">Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="82c2b-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="82c2b-116">Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="82c2b-117">Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="82c2b-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="82c2b-118">Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c2b-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="82c2b-119">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="82c2b-120">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="82c2b-121">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="82c2b-122">Wählen Sie ein Produkt aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-122">Select a product.</span></span>
3. <span data-ttu-id="82c2b-123">Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="82c2b-124">Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="82c2b-125">Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="82c2b-126">Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="82c2b-127">Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="82c2b-128">Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können.</span><span class="sxs-lookup"><span data-stu-id="82c2b-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="82c2b-129">Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="82c2b-130">Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="82c2b-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="82c2b-131">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="82c2b-132">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="82c2b-133">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="82c2b-134">Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="82c2b-135">Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="82c2b-136">Wählen Sie abschließend **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="82c2b-137">Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="82c2b-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="82c2b-138">Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="82c2b-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="82c2b-139">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="82c2b-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="82c2b-140">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="82c2b-141">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="82c2b-142">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="82c2b-143">Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="82c2b-144">Wählen Sie oben die drei Punkte (weitere Aktionen) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-144">At the top, select the three dots (more actions), then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="82c2b-145">Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="82c2b-146">Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="82c2b-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="82c2b-147">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="82c2b-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="82c2b-148">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="82c2b-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="82c2b-149">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="82c2b-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="82c2b-150">Wählen Sie am unteren Rand des Bereichs **Hinzufügen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  


> [!NOTE]
> <span data-ttu-id="82c2b-151">Wenn Sie Lizenzen für eine größere Anzahl an Benutzern zuweisen möchten, nutzen Sie [Lizenzen an Benutzer nach Gruppenmitgliedschaft in Azure Active Directory zuweisen](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="82c2b-151">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="82c2b-152">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="82c2b-152">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="82c2b-153">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="82c2b-154">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="82c2b-155">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="82c2b-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="82c2b-156">Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-156">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="82c2b-157">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-157">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="82c2b-158">Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-158">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="82c2b-159">Zuweisen einer Lizenz an einen Gastbenutzer</span><span class="sxs-lookup"><span data-stu-id="82c2b-159">Assign a license to a guest user</span></span>

<span data-ttu-id="82c2b-160">Sie können Gastbenutzer einladen, mit Ihrer Organisation im Azure Active Directory Admin Center zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-160">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="82c2b-161">Informationen über Gastbenutzer finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="82c2b-161">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="82c2b-162">Wenn Sie keine Gastbenutzer haben, siehe [Schnellstart: Hinzufügen von Gastbenutzern zu Ihrem Verzeichnis im Azure-Portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="82c2b-162">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82c2b-163">Sie müssen ein globaler Administrator sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="82c2b-163">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="82c2b-164">Wechseln Sie zu <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory Admin Center</a></span><span class="sxs-lookup"><span data-stu-id="82c2b-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="82c2b-165">Wählen Sie im Navigationsbereich **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-165">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="82c2b-166">Auf der Seite **Benutzer | Alle Benutzer (Vorschau)**, wählen Sie **Filter hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-166">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="82c2b-167">Wählen Sie im Menü **Feld auswählen** die Option **Benutzertyp**, und wählen Sie dann **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-167">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="82c2b-168">Wählen Sie im nächsten Menü **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-168">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="82c2b-169">Wählen Sie in der Liste der Ergebnisse den Benutzer aus, der eine Lizenz benötigt.</span><span class="sxs-lookup"><span data-stu-id="82c2b-169">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="82c2b-170">Wählen Sie unter **Verwalten** **Lizenzen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-170">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="82c2b-171">Wählen Sie **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-171">Select **Assignments**.</span></span>
9. <span data-ttu-id="82c2b-172">Wählen Sie auf der Seite **Lizenzzuweisungen aktualisieren** das Produkt aus, für das Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="82c2b-172">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="82c2b-173">Deaktivieren Sie auf der rechten Seite die Kontrollkästchen für alle Dienste, auf die der Gastbenutzer nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="82c2b-173">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="82c2b-174">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="82c2b-174">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="82c2b-175">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="82c2b-175">Next steps</span></span>

<span data-ttu-id="82c2b-176">Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](../../business-video/employee-quick-setup.md) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="82c2b-176">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="82c2b-177">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="82c2b-177">Related content</span></span>

<span data-ttu-id="82c2b-178">[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="82c2b-178">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="82c2b-179">[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="82c2b-179">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="82c2b-180">[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="82c2b-180">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
