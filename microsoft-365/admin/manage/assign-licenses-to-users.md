---
title: Zuweisen von Lizenzen an Benutzer
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.date: 08/14/2020
ms.openlocfilehash: b5179006da896dbadab10d43a43b094acedcb806
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113985"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="d2de5-103">Zuweisen von Lizenzen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d2de5-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="d2de5-104">The admin center is changing.</span></span> <span data-ttu-id="d2de5-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="d2de5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="d2de5-106">Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="d2de5-107">Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="d2de5-108">[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="d2de5-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d2de5-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="d2de5-109">Before you begin</span></span>

- <span data-ttu-id="d2de5-110">Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="d2de5-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="d2de5-111">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d2de5-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="d2de5-112">Sie können [Lizenzen zu Benutzerkonten mit Office 365 PowerShell zuweisen](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="d2de5-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="d2de5-113">Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="d2de5-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="d2de5-114">Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d2de5-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="d2de5-115">Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="d2de5-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="d2de5-116">Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="d2de5-117">Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="d2de5-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="d2de5-118">Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2de5-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="d2de5-119">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d2de5-120">Wählen Sie ein Produkt aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-120">Select a product.</span></span>
3. <span data-ttu-id="d2de5-121">Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="d2de5-122">Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="d2de5-123">Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="d2de5-124">Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="d2de5-125">Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="d2de5-126">Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können.</span><span class="sxs-lookup"><span data-stu-id="d2de5-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="d2de5-127">Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="d2de5-128">Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="d2de5-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="d2de5-129">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d2de5-130">Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="d2de5-131">Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="d2de5-132">Wählen Sie abschließend **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="d2de5-133">Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="d2de5-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="d2de5-134">Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="d2de5-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="d2de5-135">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="d2de5-136">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-137">Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="d2de5-138">Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="d2de5-139">Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="d2de5-140">Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="d2de5-141">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="d2de5-142">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2de5-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="d2de5-143">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="d2de5-144">Wählen Sie am unteren Rand des Bereichs **Hinzufügen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="d2de5-145">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="d2de5-146">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-147">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="d2de5-148">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="d2de5-149">Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="d2de5-150">Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="d2de5-151">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="d2de5-152">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2de5-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="d2de5-153">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="d2de5-154">Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="d2de5-155">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="d2de5-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-157">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="d2de5-158">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="d2de5-159">Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="d2de5-160">Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="d2de5-161">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="d2de5-162">Sie können die für die Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2de5-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="d2de5-163">Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="d2de5-164">Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="d2de5-165">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="d2de5-166">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-167">Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="d2de5-168">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="d2de5-169">Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="d2de5-170">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="d2de5-171">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-172">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="d2de5-173">Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="d2de5-174">Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="d2de5-175">Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="d2de5-176">Sie können die für den Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2de5-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="d2de5-177">Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="d2de5-178">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="d2de5-179">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="d2de5-180">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d2de5-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d2de5-181">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="d2de5-182">Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="d2de5-183">Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="d2de5-184">Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d2de5-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="d2de5-185">Sie können die für den Benutzer verfügbaren Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2de5-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="d2de5-186">Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.</span><span class="sxs-lookup"><span data-stu-id="d2de5-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="d2de5-187">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="d2de5-188">Zuweisen einer Lizenz an einen Gastbenutzer</span><span class="sxs-lookup"><span data-stu-id="d2de5-188">Assign a license to a guest user</span></span>

<span data-ttu-id="d2de5-189">Sie können Gastbenutzer einladen, mit Ihrer Organisation im Azure Active Directory Admin Center zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-189">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="d2de5-190">Informationen über Gastbenutzer finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="d2de5-190">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="d2de5-191">Wenn Sie keine Gastbenutzer haben, siehe [Schnellstart: Hinzufügen von Gastbenutzern zu Ihrem Verzeichnis im Azure-Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="d2de5-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2de5-192">Sie müssen ein globaler Administrator sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d2de5-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="d2de5-193">Wechseln Sie zu <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory Admin Center</a></span><span class="sxs-lookup"><span data-stu-id="d2de5-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="d2de5-194">Wählen Sie im Navigationsbereich **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="d2de5-195">Auf der Seite **Benutzer | Alle Benutzer (Vorschau)**, wählen Sie **Filter hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="d2de5-196">Wählen Sie im Menü **Feld auswählen** die Option **Benutzertyp**, und wählen Sie dann **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="d2de5-197">Wählen Sie im nächsten Menü **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="d2de5-198">Wählen Sie in der Liste der Ergebnisse den Benutzer aus, der eine Lizenz benötigt.</span><span class="sxs-lookup"><span data-stu-id="d2de5-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="d2de5-199">Wählen Sie unter **Verwalten** **Lizenzen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="d2de5-200">Wählen Sie **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="d2de5-201">Wählen Sie auf der Seite **Lizenzzuweisungen aktualisieren** das Produkt aus, für das Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2de5-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="d2de5-202">Deaktivieren Sie auf der rechten Seite die Kontrollkästchen für alle Dienste, auf die der Gastbenutzer nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d2de5-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="d2de5-203">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d2de5-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2de5-204">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d2de5-204">Next steps</span></span>

<span data-ttu-id="d2de5-205">Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="d2de5-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="d2de5-206">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="d2de5-206">Related content</span></span>

<span data-ttu-id="d2de5-207">[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d2de5-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="d2de5-208">[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d2de5-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="d2de5-209">[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d2de5-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
