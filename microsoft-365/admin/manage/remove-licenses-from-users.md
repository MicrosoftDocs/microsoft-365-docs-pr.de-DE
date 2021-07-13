---
title: Aufheben der Zuweisung von Benutzerlizenzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: Die Methode zum Aufheben der Zuweisung von Produktlizenzen hängt davon ab, ob Sie die Zuweisung von Lizenzen von bestimmten Benutzern oder von einem bestimmten Produkt aufheben.
ms.date: 06/07/2021
ms.openlocfilehash: 8a67d7e690ff07631f696a97d6ed59925bc871df
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392491"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="af20d-103">Aufheben der Zuweisung von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="af20d-103">Unassign licenses from users</span></span>

<span data-ttu-id="af20d-104">Sie können die Zuweisung von Lizenzen von Benutzern entweder auf der Seite **"Aktive Benutzer"** oder auf der Seite **"Lizenzen"** aufheben.</span><span class="sxs-lookup"><span data-stu-id="af20d-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="af20d-105">Die verwendete Methode hängt davon ab, ob Sie die Zuweisung von Produktlizenzen von bestimmten Benutzern aufheben oder die Zuweisung von Benutzerlizenzen für ein bestimmtes Produkt aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="af20d-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="af20d-106">Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="af20d-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="af20d-107">Sie können ein [Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.</span><span class="sxs-lookup"><span data-stu-id="af20d-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="af20d-108">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="af20d-108">Before you begin</span></span>

- <span data-ttu-id="af20d-109">Sie müssen ein globaler, Lizenz- und Benutzeradministrator sein, um die Zuweisung von Lizenzen aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="af20d-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="af20d-110">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="af20d-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="af20d-111">Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="af20d-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="af20d-112">Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="af20d-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="af20d-113">Wenn Sie ein Benutzerkonto löschen, ist die Lizenz sofort verfügbar, um es einer anderen Person zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="af20d-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="af20d-114">Verwenden der Seite "Lizenzen" zum Aufheben der Zuweisung von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="af20d-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="af20d-115">Wenn Sie die Seite **"Lizenzen"** verwenden, um die Zuweisung von Lizenzen aufzuheben, heben Sie die Zuweisung von Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer auf.</span><span class="sxs-lookup"><span data-stu-id="af20d-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af20d-116">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="af20d-117">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="af20d-118">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="af20d-119">Wählen Sie das Produkt aus, für das Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="af20d-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="af20d-120">Wählen Sie die Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="af20d-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="af20d-121">Wählen Sie **"Lizenzen aufheben" aus.**</span><span class="sxs-lookup"><span data-stu-id="af20d-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="af20d-122">Wählen Sie im Feld **"Lizenzen aufheben"** die Option **"Zuweisung aufheben"** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="af20d-123">Verwenden der Seite "Aktive Benutzer" zum Aufheben der Zuweisung von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="af20d-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="af20d-124">Wenn Sie die Seite **"Aktive Benutzer"** verwenden, um die Zuweisung von Lizenzen aufzuheben, heben Sie die Zuweisung von Produktlizenzen von Benutzern auf.</span><span class="sxs-lookup"><span data-stu-id="af20d-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="af20d-125">Aufheben der Zuweisung von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="af20d-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af20d-126">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="af20d-127">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="af20d-128">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="af20d-129">Wählen Sie die Zeile des Benutzers aus, für den Sie die Zuweisung einer Lizenz aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="af20d-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="af20d-130">Wählen Sie im rechten Fensterbereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="af20d-131">Erweitern Sie den Abschnitt **"Lizenzen",** deaktivieren Sie die Felder für die Lizenzen, die Sie die Zuweisung aufheben möchten, und wählen Sie dann **"Änderungen speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="af20d-132">Aufheben der Zuweisung von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="af20d-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af20d-133">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="af20d-134">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="af20d-135">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="af20d-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="af20d-136">Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="af20d-136">Select the circles next to the names of the users who you want to unassign licenses for.</span></span>
3. <span data-ttu-id="af20d-137">Wählen Sie oben **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-137">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="af20d-138">Wählen Sie im Bereich **"Produktlizenzen verwalten"** die Option **"Alle**  >  **Änderungen speichern aufheben"** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-138">In the **Manage product licenses** pane, select **Unassign all** > **Save changes**.</span></span>
5. <span data-ttu-id="af20d-139">Wählen Sie unten im Bereich **"Fertig"** aus.</span><span class="sxs-lookup"><span data-stu-id="af20d-139">At the bottom of the pane, select **Done**.</span></span>  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="af20d-140">Was geschieht mit den Daten eines Benutzers, wenn Sie seine Lizenz entfernen?</span><span class="sxs-lookup"><span data-stu-id="af20d-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="af20d-141">Wenn eine Lizenz von einem Benutzer entfernt wird, werden Exchange Onlinedaten, die diesem Konto zugeordnet sind, 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="af20d-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="af20d-142">Nach Ablauf der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="af20d-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="af20d-143">In OneDrive for Business gespeicherte Dateien werden nicht gelöscht, es sei denn, der Benutzer wird aus dem Microsoft 365 Admin Center gelöscht oder über die Active Directory-Synchronisierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="af20d-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="af20d-144">Weitere Informationen finden Sie unter [OneDrive Aufbewahrung und Löschung.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="af20d-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="af20d-145">Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mithilfe eines eDiscovery-Tools wie inhaltssuche oder Advanced eDiscovery durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="af20d-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="af20d-146">Weitere Informationen finden Sie unter "Durchsuchen getrennter oder nicht lizenzierter Postfächer" in der [Inhaltssuche in Microsoft 365.](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="af20d-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="af20d-147">Wenn Sie über ein Enterprise Abonnement verfügen, z. B. Office 365 Enterprise E3, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe [inaktiver Postfächer](../../compliance/inactive-mailboxes-in-office-365.md)beibehalten.</span><span class="sxs-lookup"><span data-stu-id="af20d-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="af20d-148">Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="af20d-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="af20d-149">Informationen dazu, wie Sie den Zugriff eines Benutzers auf Microsoft 365 Daten blockieren, nachdem die Lizenz entfernt wurde, und wie Sie danach Zugriff auf die Daten erhalten, finden Sie unter [Entfernen eines ehemaligen Mitarbeiters.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="af20d-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="af20d-150">Wenn Sie die Lizenz eines Benutzers entfernen und er weiterhin Office Apps installiert hat, werden in Office fehler [beim](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) Verwenden Office Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af20d-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af20d-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="af20d-151">Next steps</span></span>

<span data-ttu-id="af20d-152">Wenn Sie [die nicht verwendeten Lizenzen](../../managed-desktop/get-started/assign-licenses.md)nicht anderen Benutzern zuweisen möchten, sollten Sie [die Lizenzen aus Ihrem Abonnement entfernen,](../../commerce/licenses/buy-licenses.md) damit Sie nicht mehr Lizenzen bezahlen, als Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="af20d-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="af20d-153">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="af20d-153">Related content</span></span>

<span data-ttu-id="af20d-154">[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="af20d-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="af20d-155">[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="af20d-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="af20d-156">[Grundlegendes zu Abonnements und Lizenzen in Microsoft 365 for Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="af20d-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
