---
title: Aufheben der Zuweisung von Benutzerlizenzen
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: Erfahren Sie, wie Sie lizenzen von Benutzerkonten wegzuweisen.
ms.date: 07/01/2020
ms.openlocfilehash: 550136c2cfa8d81a31e52a4313dc9c967a55d56e
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398193"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="9cf42-103">Aufheben der Zuweisung von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="9cf42-103">Unassign licenses from users</span></span>

<span data-ttu-id="9cf42-104">Sie können lizenzen von Benutzern entweder auf der Seite **Aktive** Benutzer oder auf der Seite **Lizenzen zuweisen.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="9cf42-105">Die methode, die Sie verwenden, hängt davon ab, ob Sie Produktlizenzen von bestimmten Benutzern oder Benutzerlizenzen von einem bestimmten Produkt zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf42-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf42-106">Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder zuweisen, das von einem Benutzer in Ihrer Organisation erworben wurde.</span><span class="sxs-lookup"><span data-stu-id="9cf42-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="9cf42-107">Sie können [ein Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9cf42-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9cf42-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="9cf42-108">Before you begin</span></span>

- <span data-ttu-id="9cf42-109">Sie müssen ein globaler, Lizenz-, Benutzeradministrator sein, um Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9cf42-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="9cf42-110">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9cf42-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="9cf42-111">Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9cf42-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="9cf42-112">Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="9cf42-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="9cf42-113">Wenn Sie ein Benutzerkonto löschen, steht deren Lizenz sofort zur Verfügung, um sie einer anderen Person zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="9cf42-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="9cf42-114">Verwenden der Seite Lizenzen zum Ensign von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="9cf42-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="9cf42-115">Wenn Sie die Seite **Lizenzen** zum Zuweisen von Lizenzen verwenden, wird die Zuzuweisen von Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer entfernt.</span><span class="sxs-lookup"><span data-stu-id="9cf42-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cf42-116">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="9cf42-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cf42-117">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungslizenzen.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cf42-118">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungslizenzen.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="9cf42-119">Wählen Sie das Produkt aus, für das Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf42-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="9cf42-120">Wählen Sie die Benutzer aus, für die Sie lizenzen nicht mehr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf42-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="9cf42-121">Wählen **Sie Lizenzen nicht zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="9cf42-122">Wählen Sie **im Feld Lizenzen nicht zuweisen** die Option **Unassign aus.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="9cf42-123">Verwenden der Seite Aktive Benutzer zum Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="9cf42-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="9cf42-124">Wenn Sie die Seite **Aktive Benutzer** verwenden, um lizenzen zuzuweisen, wird die Zuzuweisen von Produktlizenzen von Benutzern entfernt.</span><span class="sxs-lookup"><span data-stu-id="9cf42-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="9cf42-125">Zuweisen von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="9cf42-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cf42-126">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="9cf42-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cf42-127">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite Aktive  > **Benutzer** abrechnung.</span><span class="sxs-lookup"><span data-stu-id="9cf42-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cf42-128">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite Aktive  > **Benutzer** abrechnung.</span><span class="sxs-lookup"><span data-stu-id="9cf42-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="9cf42-129">Wählen Sie die Zeile des Benutzers aus, für den Sie die Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf42-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="9cf42-130">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="9cf42-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="9cf42-131">Erweitern Sie **den Abschnitt Lizenzen,** löschen Sie die Felder für die Lizenzen, die Sie zuweisen möchten, und wählen Sie **Dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="9cf42-132">Zuweisen von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="9cf42-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cf42-133">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="9cf42-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cf42-134">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite Aktive  > **Benutzer** abrechnung.</span><span class="sxs-lookup"><span data-stu-id="9cf42-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cf42-135">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite Aktive  > **Benutzer** abrechnung.</span><span class="sxs-lookup"><span data-stu-id="9cf42-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="9cf42-136">Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf42-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="9cf42-137">Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="9cf42-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="9cf42-138">Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9cf42-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9cf42-139">Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen aus dem ausgewählten Benutzer entfernen, und wählen Sie dann **Schließen** \> **ersetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="9cf42-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="9cf42-140">Was geschieht mit den Daten eines Benutzers, wenn Sie die Lizenz entfernen?</span><span class="sxs-lookup"><span data-stu-id="9cf42-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="9cf42-141">Wenn eine Lizenz von einem Benutzer entfernt wird, werden daten, die diesem Konto zugeordnet sind, 30 Tage lang gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9cf42-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="9cf42-142">Nach der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9cf42-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="9cf42-143">In OneDrive for Business gespeicherte Dateien werden nur gelöscht, wenn der Benutzer aus dem Microsoft 365 Admin Center gelöscht oder über die Active #A0 entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="9cf42-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="9cf42-144">Weitere Informationen finden Sie unter [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="9cf42-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="9cf42-145">Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mit einem eDiscovery-Tool wie inhaltssuche oder advanced eDiscovery durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="9cf42-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="9cf42-146">Weitere Informationen finden Sie unter "Suchen getrennter oder nicht lizenzierter Postfächer" [in Der Inhaltssuche in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="9cf42-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="9cf42-147">Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe inaktiver [Postfächer beibehalten.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9cf42-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="9cf42-148">Weitere Informationen finden Sie unter [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="9cf42-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="9cf42-149">Informationen zum Blockieren des Zugriffs eines Benutzers auf Microsoft 365-Daten nach dem Entfernen der Lizenz und zum anschließenden Zugriff auf die Daten finden Sie unter Entfernen eines ehemaligen [Mitarbeiters.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="9cf42-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="9cf42-150">Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden [unlizenzierte Produkt-](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) und Aktivierungsfehler in Office angezeigt, wenn sie Office-Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="9cf42-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9cf42-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9cf42-151">Next steps</span></span>

<span data-ttu-id="9cf42-152">Wenn Sie die nicht verwendeten Lizenzen nicht anderen Benutzern [](../../commerce/licenses/buy-licenses.md) erneut zuweisen [möchten,](../../managed-desktop/get-started/assign-licenses.md)sollten Sie die Lizenzen aus Ihrem Abonnement entfernen, damit Sie nicht für mehr Lizenzen bezahlen, als Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="9cf42-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="9cf42-153">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9cf42-153">Related content</span></span>

<span data-ttu-id="9cf42-154">[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9cf42-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="9cf42-155">[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9cf42-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="9cf42-156">[Verstehen von Abonnements und Lizenzen in Microsoft 365 Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9cf42-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>