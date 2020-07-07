---
title: Zuweisen von Lizenzen an Benutzer
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Benutzern Lizenzen zuweisen.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015947"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="f8da1-103">Zuweisen von Lizenzen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f8da1-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="f8da1-104">The admin center is changing.</span></span> <span data-ttu-id="f8da1-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f8da1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="f8da1-106">Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="f8da1-107">Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="f8da1-108">[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="f8da1-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8da1-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f8da1-109">Before you begin</span></span>

- <span data-ttu-id="f8da1-110">Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="f8da1-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="f8da1-111">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f8da1-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="f8da1-112">Sie können [Lizenzen zu Benutzerkonten mit Office 365 PowerShell zuweisen](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="f8da1-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="f8da1-113">Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="f8da1-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="f8da1-114">Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f8da1-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="f8da1-115">Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="f8da1-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="f8da1-116">Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="f8da1-117">Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="f8da1-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="f8da1-118">Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8da1-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="f8da1-119">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="f8da1-120">Wählen Sie ein Produkt aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-120">Select a product.</span></span>
3. <span data-ttu-id="f8da1-121">Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="f8da1-122">Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="f8da1-123">Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="f8da1-124">Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="f8da1-125">Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="f8da1-126">Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können.</span><span class="sxs-lookup"><span data-stu-id="f8da1-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="f8da1-127">Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="f8da1-128">Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="f8da1-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="f8da1-129">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="f8da1-130">Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="f8da1-131">Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="f8da1-132">Wählen Sie abschließend **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="f8da1-133">Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="f8da1-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="f8da1-134">Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="f8da1-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="f8da1-135">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="f8da1-136">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-137">Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="f8da1-138">Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="f8da1-139">Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f8da1-140">Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="f8da1-141">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="f8da1-142">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8da1-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="f8da1-143">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="f8da1-144">Wählen Sie am unteren Rand des Bereichs **Hinzufügen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="f8da1-145">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="f8da1-146">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-147">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="f8da1-148">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f8da1-149">Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f8da1-150">Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="f8da1-151">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="f8da1-152">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8da1-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="f8da1-153">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="f8da1-154">Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="f8da1-155">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="f8da1-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-157">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="f8da1-158">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f8da1-159">Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f8da1-160">Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="f8da1-161">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="f8da1-162">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8da1-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="f8da1-163">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="f8da1-164">Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="f8da1-165">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="f8da1-166">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-167">Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="f8da1-168">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="f8da1-169">Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="f8da1-170">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="f8da1-171">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-172">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="f8da1-173">Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="f8da1-174">Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="f8da1-175">Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="f8da1-176">Sie können die für den Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8da1-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="f8da1-177">Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="f8da1-178">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="f8da1-179">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8da1-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="f8da1-180">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f8da1-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f8da1-181">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="f8da1-182">Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="f8da1-183">Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8da1-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="f8da1-184">Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f8da1-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="f8da1-185">Sie können die für den Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8da1-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="f8da1-186">Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f8da1-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="f8da1-187">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8da1-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="f8da1-188">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f8da1-188">Next steps</span></span>

<span data-ttu-id="f8da1-189">Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="f8da1-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="f8da1-190">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f8da1-190">Related content</span></span>

<span data-ttu-id="f8da1-191">[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f8da1-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="f8da1-192">[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f8da1-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="f8da1-193">[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f8da1-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>