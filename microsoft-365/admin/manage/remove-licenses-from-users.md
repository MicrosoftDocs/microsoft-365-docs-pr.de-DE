---
title: Aufheben der Zuweisung von Benutzerlizenzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Erfahren Sie, wie Sie die Zuweisung von Lizenzen von Benutzerkonten aufheben.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015935"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="439f4-103">Aufheben der Zuweisung von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="439f4-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="439f4-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="439f4-104">The admin center is changing.</span></span> <span data-ttu-id="439f4-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="439f4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="439f4-106">Sie können die Zuweisung von Lizenzen von Benutzern auf der Seite " **aktive Benutzer** " oder auf der Seite " **Lizenzen** " aufheben.</span><span class="sxs-lookup"><span data-stu-id="439f4-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="439f4-107">Die verwendete Methode hängt davon ab, ob Sie Produktlizenzen von bestimmten Benutzern aufheben oder die Zuweisung von Benutzerlizenzen von einem bestimmten Produkt aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="439f4-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="439f4-108">Before you begin</span></span>

- <span data-ttu-id="439f4-109">Zum Aufheben der Zuweisung von Lizenzen müssen Sie ein globaler, Lizenz-, Benutzer-Admin sein.</span><span class="sxs-lookup"><span data-stu-id="439f4-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="439f4-110">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="439f4-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="439f4-111">Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="439f4-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="439f4-112">Sie können auch [Benutzerkonten löschen](../add-users/delete-a-user.md) , denen eine Lizenz zugewiesen wurde, um Ihre Lizenz anderen Benutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="439f4-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="439f4-113">Wenn Sie ein Benutzerkonto löschen, ist Ihre Lizenz sofort verfügbar, um Sie einer anderen Person zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="439f4-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="439f4-114">Verwenden der Seite "Lizenzen" zum Aufheben der Zuweisung von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="439f4-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="439f4-115">Wenn Sie die Zuweisung von Lizenzen mithilfe der Seite **Lizenzen** aufheben, werden Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer aufheben.</span><span class="sxs-lookup"><span data-stu-id="439f4-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="439f4-116">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="439f4-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="439f4-117">Wählen Sie das Produkt aus, für das Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="439f4-118">Wählen Sie die Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="439f4-119">Wählen Sie Lizenzen für Aufheben der **Zuweisung**aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="439f4-120">**Wählen Sie**im Feld **Zuweisungs Lizenzen** aufheben aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="439f4-121">Verwenden der Seite "aktive Benutzer" zum Aufheben der Zuweisung von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="439f4-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="439f4-122">Wenn Sie die Zuweisung von Lizenzen mithilfe der Seite **aktive Benutzer** aufheben, heben Sie die Zuweisung von Produktlizenzen von Benutzern auf.</span><span class="sxs-lookup"><span data-stu-id="439f4-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="439f4-123">Aufheben der Zuweisung von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="439f4-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="439f4-124">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-125">Wählen Sie die Zeile des Benutzers aus, für den Sie die Zuweisung einer Lizenz aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="439f4-126">Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="439f4-127">Erweitern Sie den Abschnitt **Lizenzen** , deaktivieren Sie die Felder für die Lizenzen, die Sie aufheben möchten, und wählen Sie dann **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="439f4-128">Aufheben der Zuweisung von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="439f4-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="439f4-129">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-130">Wählen Sie den Benutzer aus, für den Sie die Zuweisung der Lizenz aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="439f4-131">Wählen Sie auf der rechten Seite in der Zeile **Produktlizenzen** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="439f4-132">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche in die Position aus für die Lizenz, die Sie dem Benutzer **aufheben** möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="439f4-133">Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, wird die Zuweisung dieser Lizenz und aller Dienste unter dieser Lizenz für diesen Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="439f4-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="439f4-134">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="439f4-135">Aufheben der Zuweisung von Lizenzen von einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="439f4-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="439f4-136">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-137">Wählen Sie den Benutzer aus, für den Sie die Zuweisung der Lizenz aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="439f4-138">Wählen Sie auf der rechten Seite in der Zeile **Produktlizenzen** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="439f4-139">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche in die Position aus für die Lizenz, die Sie dem Benutzer **aufheben** möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="439f4-140">Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, wird die Zuweisung dieser Lizenz und aller Dienste unter dieser Lizenz für diesen Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="439f4-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="439f4-141">Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="439f4-142">Aufheben der Zuweisung von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="439f4-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="439f4-143">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-144">Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="439f4-145">Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="439f4-146">Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="439f4-147">Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Schließen**ersetzen aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="439f4-148">Aufheben der Zuweisung von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="439f4-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="439f4-149">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-150">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Zuweisung aller Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="439f4-151">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="439f4-152">Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="439f4-153">Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Close** \> **Close**ersetzen aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="439f4-154">Aufheben der Zuweisung von Lizenzen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="439f4-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="439f4-155">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="439f4-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="439f4-156">Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Zuweisung aller Lizenzen aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="439f4-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="439f4-157">Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="439f4-158">Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="439f4-159">Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Close** \> **Close**ersetzen aus.</span><span class="sxs-lookup"><span data-stu-id="439f4-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="439f4-160">Was geschieht mit den Daten eines Benutzers, wenn er seine Lizenz entfernt?</span><span class="sxs-lookup"><span data-stu-id="439f4-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="439f4-161">Wenn eine Lizenz von einem Benutzer entfernt wird, werden Daten, die diesem Konto zugeordnet sind, 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="439f4-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="439f4-162">Nach Ablauf der 30-tägigen Kulanzzeit werden die Daten gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="439f4-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="439f4-163">In OneDrive für Unternehmen gespeicherte Dateien werden nicht gelöscht, es sei denn, der Benutzer wird aus dem Microsoft 365 Admin Center gelöscht oder durch Active Directory Synchronisierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="439f4-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="439f4-164">Weitere Informationen finden Sie unter [OneDrive Retention and Deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="439f4-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="439f4-165">Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mithilfe eines eDiscovery-Tools wie der Inhaltssuche oder Advanced eDiscovery durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="439f4-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="439f4-166">Weitere Informationen finden Sie unter "Durchsuchen von getrennten oder delizenzierten Postfächern" in der [Inhaltssuche in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="439f4-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="439f4-167">Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe [inaktiver Postfächer](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)beibehalten.</span><span class="sxs-lookup"><span data-stu-id="439f4-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="439f4-168">Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="439f4-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="439f4-169">Informationen darüber, wie Sie den Zugriff eines Benutzers auf Microsoft 365-Daten nach dem Entfernen Ihrer Lizenz und wie Sie später auf die Daten zugreifen können, finden Sie unter [Entfernen eines ehemaligen Mitarbeiters](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="439f4-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="439f4-170">Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden bei der Verwendung von Office-Apps nicht [lizenzierte Produkt-und Aktivierungsfehler in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="439f4-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="439f4-171">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="439f4-171">Next steps</span></span>

<span data-ttu-id="439f4-172">Wenn Sie nicht [die nicht verwendeten Lizenzen anderen Benutzern zuweisen](../../managed-desktop/get-started/assign-licenses.md)möchten, sollten Sie [die Lizenzen aus Ihrem Abonnement entfernen](../../commerce/licenses/buy-licenses.md) , damit Sie nicht mehr Lizenzen als erforderlich bezahlen.</span><span class="sxs-lookup"><span data-stu-id="439f4-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="439f4-173">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="439f4-173">Related content</span></span>

<span data-ttu-id="439f4-174">[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="439f4-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="439f4-175">[Zuweisen von Lizenzen zu Benutzern](assign-licenses-to-users.md) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="439f4-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="439f4-176">Grund [Legendes zu Abonnements und Lizenzen in Microsoft 365 for Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="439f4-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>