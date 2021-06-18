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
ms.openlocfilehash: c8e5c6a648f08aaba97fe05e19a5cfa0cada2174
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007009"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="5dd63-103">Zuweisen von Lizenzen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="5dd63-103">Assign licenses to users</span></span>

<span data-ttu-id="5dd63-104">Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="5dd63-105">Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="5dd63-106">Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="5dd63-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="5dd63-107">Sie können ein [Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="5dd63-108">[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="5dd63-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5dd63-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="5dd63-109">Before you begin</span></span>

- <span data-ttu-id="5dd63-110">Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="5dd63-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="5dd63-111">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5dd63-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="5dd63-112">Sie können [Microsoft 365-Lizenzen mit PowerShell zu Benutzerkonten zuweisen](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5dd63-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="5dd63-113">Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="5dd63-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="5dd63-114">Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5dd63-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="5dd63-115">Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="5dd63-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="5dd63-116">Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="5dd63-117">Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="5dd63-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="5dd63-118">Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5dd63-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5dd63-119">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5dd63-120">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5dd63-121">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="5dd63-122">Wählen Sie ein Produkt aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-122">Select a product.</span></span>
3. <span data-ttu-id="5dd63-123">Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="5dd63-124">Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="5dd63-125">Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="5dd63-126">Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="5dd63-127">Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="5dd63-128">Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können.</span><span class="sxs-lookup"><span data-stu-id="5dd63-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="5dd63-129">Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="5dd63-130">Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="5dd63-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5dd63-131">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5dd63-132">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5dd63-133">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="5dd63-134">Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="5dd63-135">Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="5dd63-136">Wählen Sie abschließend **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="5dd63-137">Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="5dd63-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="5dd63-138">Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="5dd63-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="5dd63-139">Zuweisen von Lizenzen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="5dd63-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5dd63-140">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5dd63-141">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5dd63-142">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="5dd63-143">Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="5dd63-144">Wählen Sie oben **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="5dd63-145">Wählen Sie im Bereich **Produktlizenzen verwalten** die Option **Weitere zuweisen: Vorhandene Lizenzen beibehalten und weitere zuweisen** \> **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5dd63-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="5dd63-146">Aktivieren Sie unter **Lizenzen** das Kontrollkästchen für die Lizenz(en), über die die ausgewählten Benutzer verfügen sollen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="5dd63-p107">Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Deaktivieren Sie die Kontrollkästchen für die Dienste, über die die Benutzer nicht verfügen sollen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-p107">By default, all services associated with those licenses are automatically assigned to the users. You can limit which services are available to the users. Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="5dd63-150">Wählen Sie unten im Bereich **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="5dd63-151">Möglicherweise müssen Sie zusätzliche Lizenzen erwerben, wenn Sie nicht über genügend Lizenzen für alle verfügen.</span><span class="sxs-lookup"><span data-stu-id="5dd63-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="5dd63-152">Wenn Sie Lizenzen für eine größere Anzahl an Benutzern zuweisen möchten, nutzen Sie [Lizenzen an Benutzer nach Gruppenmitgliedschaft in Azure Active Directory zuweisen](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="5dd63-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="5dd63-153">Zuweisen von Lizenzen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="5dd63-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5dd63-154">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5dd63-155">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5dd63-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5dd63-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="5dd63-157">Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="5dd63-158">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="5dd63-159">Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="5dd63-160">Zuweisen einer Lizenz an einen Gastbenutzer</span><span class="sxs-lookup"><span data-stu-id="5dd63-160">Assign a license to a guest user</span></span>

<span data-ttu-id="5dd63-161">Sie können Gastbenutzer einladen, mit Ihrer Organisation im Azure Active Directory Admin Center zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="5dd63-162">Informationen über Gastbenutzer finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="5dd63-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="5dd63-163">Wenn Sie keine Gastbenutzer haben, siehe [Schnellstart: Hinzufügen von Gastbenutzern zu Ihrem Verzeichnis im Azure-Portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="5dd63-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dd63-164">Sie müssen ein globaler Administrator sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="5dd63-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="5dd63-165">Wechseln Sie zu <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory Admin Center</a></span><span class="sxs-lookup"><span data-stu-id="5dd63-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="5dd63-166">Wählen Sie im Navigationsbereich **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="5dd63-167">Auf der Seite **Benutzer | Alle Benutzer (Vorschau)**, wählen Sie **Filter hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="5dd63-168">Wählen Sie im Menü **Feld auswählen** die Option **Benutzertyp**, und wählen Sie dann **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="5dd63-169">Wählen Sie im nächsten Menü **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="5dd63-170">Wählen Sie in der Liste der Ergebnisse den Benutzer aus, der eine Lizenz benötigt.</span><span class="sxs-lookup"><span data-stu-id="5dd63-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="5dd63-171">Wählen Sie unter **Verwalten** **Lizenzen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="5dd63-172">Wählen Sie **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="5dd63-173">Wählen Sie auf der Seite **Lizenzzuweisungen aktualisieren** das Produkt aus, für das Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd63-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="5dd63-174">Deaktivieren Sie auf der rechten Seite die Kontrollkästchen für alle Dienste, auf die der Gastbenutzer nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5dd63-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="5dd63-175">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5dd63-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dd63-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5dd63-176">Next steps</span></span>

<span data-ttu-id="5dd63-177">Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](../../business-video/employee-quick-setup.md) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="5dd63-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="5dd63-178">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5dd63-178">Related content</span></span>

<span data-ttu-id="5dd63-179">[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5dd63-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="5dd63-180">[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5dd63-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="5dd63-181">[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5dd63-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
