---
title: Aufheben der Zuweisung von Benutzerlizenzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie, wie Sie lizenzen von Benutzerkonten wegzuweisen.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915194"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="553ef-103">Aufheben der Zuweisung von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="553ef-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="553ef-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="553ef-104">The admin center is changing.</span></span> <span data-ttu-id="553ef-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="553ef-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="553ef-106">Sie können lizenzen von Benutzern entweder auf der Seite **Aktive** Benutzer oder auf der Seite **Lizenzen zuweisen.**</span><span class="sxs-lookup"><span data-stu-id="553ef-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="553ef-107">Die methode, die Sie verwenden, hängt davon ab, ob Sie Produktlizenzen von bestimmten Benutzern oder Benutzerlizenzen von einem bestimmten Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="553ef-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="553ef-108">Before you begin</span></span>

- <span data-ttu-id="553ef-109">Sie müssen ein globaler, Lizenz-, Benutzeradministrator sein, um Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="553ef-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="553ef-110">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="553ef-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="553ef-111">Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="553ef-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="553ef-112">Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="553ef-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="553ef-113">Wenn Sie ein Benutzerkonto löschen, steht deren Lizenz sofort zur Verfügung, um sie einer anderen Person zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="553ef-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="553ef-114">Verwenden der Seite Lizenzen zum Ensign von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="553ef-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="553ef-115">Wenn Sie die Seite **Lizenzen** zum Zuweisen von Lizenzen verwenden, wird die Zuzuweisen von Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer entfernt.</span><span class="sxs-lookup"><span data-stu-id="553ef-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="553ef-116">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="553ef-117">Wählen Sie das Produkt aus, für das Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="553ef-118">Wählen Sie die Benutzer aus, für die Sie lizenzen nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="553ef-119">Wählen **Sie Lizenzen nicht zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="553ef-120">Wählen Sie **im Feld Lizenzen nicht zuweisen** die Option **Unassign aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="553ef-121">Verwenden der Seite Aktive Benutzer zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="553ef-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="553ef-122">Wenn Sie die Seite **Aktive Benutzer** verwenden, um lizenzen zuzuweisen, wird die Zuzuweisen von Produktlizenzen von Benutzern entfernt.</span><span class="sxs-lookup"><span data-stu-id="553ef-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="553ef-123">Zuweisen von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="553ef-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="553ef-124">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-125">Wählen Sie die Zeile des Benutzers aus, für den Sie die Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="553ef-126">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="553ef-127">Erweitern Sie **den Abschnitt Lizenzen,** löschen Sie die Felder für die Lizenzen, die Sie zuweisen möchten, und wählen Sie **Dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="553ef-128">Zuweisen von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="553ef-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="553ef-129">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-130">Wählen Sie den Benutzer aus, für den Sie die Lizenz nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="553ef-131">Wählen Sie auf der rechten Seite in der **Zeile Produktlizenzen** die Option **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="553ef-132">Wechseln Sie **im** Bereich Produktlizenzen  zur Aus-Position für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="553ef-133">Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="553ef-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="553ef-134">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="553ef-135">Zuweisen von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="553ef-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="553ef-136">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-137">Wählen Sie den Benutzer aus, für den Sie die Lizenz nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="553ef-138">Wählen Sie auf der rechten Seite in der **Zeile Produktlizenzen** die Option **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="553ef-139">Wechseln Sie **im** Bereich Produktlizenzen  zur Aus-Position für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="553ef-140">Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="553ef-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="553ef-141">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="553ef-142">Zuweisen von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="553ef-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="553ef-143">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-144">Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="553ef-145">Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="553ef-146">Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="553ef-147">Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen aus dem ausgewählten Benutzer entfernen, und wählen Sie dann **Schließen** \> **ersetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="553ef-148">Zuweisen von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="553ef-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="553ef-149">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-150">Wählen Sie die Felder neben den Namen der Benutzer aus, für die Sie alle Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="553ef-151">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="553ef-152">Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="553ef-153">Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen  aus dem ausgewählten Benutzer entfernen, und wählen Sie dann Schließen schließen \>  \> **ersetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="553ef-154">Zuweisen von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="553ef-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="553ef-155">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="553ef-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="553ef-156">Wählen Sie die Felder neben den Namen der Benutzer aus, für die Sie alle Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="553ef-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="553ef-157">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="553ef-158">Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="553ef-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="553ef-159">Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen  aus dem ausgewählten Benutzer entfernen, und wählen Sie dann Schließen schließen \>  \> **ersetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="553ef-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="553ef-160">Was geschieht mit den Daten eines Benutzers, wenn Sie die Lizenz entfernen?</span><span class="sxs-lookup"><span data-stu-id="553ef-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="553ef-161">Wenn eine Lizenz von einem Benutzer entfernt wird, werden daten, die diesem Konto zugeordnet sind, 30 Tage lang gespeichert.</span><span class="sxs-lookup"><span data-stu-id="553ef-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="553ef-162">Nach der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="553ef-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="553ef-163">In OneDrive for Business gespeicherte Dateien werden nur gelöscht, wenn der Benutzer aus dem Microsoft 365 Admin Center gelöscht oder über die Active #A0 entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="553ef-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="553ef-164">Weitere Informationen finden Sie unter [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="553ef-164">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="553ef-165">Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mit einem eDiscovery-Tool wie inhaltssuche oder advanced eDiscovery durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="553ef-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="553ef-166">Weitere Informationen finden Sie unter "Suchen getrennter oder nicht lizenzierter Postfächer" [in Der Inhaltssuche in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="553ef-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="553ef-167">Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe inaktiver [Postfächer beibehalten.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="553ef-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="553ef-168">Weitere Informationen finden Sie unter [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="553ef-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="553ef-169">Informationen zum Blockieren des Zugriffs eines Benutzers auf Microsoft 365-Daten nach dem Entfernen der Lizenz und zum anschließenden Zugriff auf die Daten finden Sie unter Entfernen eines ehemaligen [Mitarbeiters.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="553ef-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="553ef-170">Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden [unlizenzierte Produkt-](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) und Aktivierungsfehler in Office angezeigt, wenn sie Office-Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="553ef-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="553ef-171">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="553ef-171">Next steps</span></span>

<span data-ttu-id="553ef-172">Wenn Sie die nicht verwendeten Lizenzen nicht anderen Benutzern [](../../commerce/licenses/buy-licenses.md) erneut zuweisen [möchten,](../../managed-desktop/get-started/assign-licenses.md)sollten Sie die Lizenzen aus Ihrem Abonnement entfernen, damit Sie nicht für mehr Lizenzen bezahlen, als Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="553ef-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="553ef-173">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="553ef-173">Related content</span></span>

<span data-ttu-id="553ef-174">[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="553ef-174">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="553ef-175">[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="553ef-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="553ef-176">[Verstehen von Abonnements und Lizenzen in Microsoft 365 Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="553ef-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>