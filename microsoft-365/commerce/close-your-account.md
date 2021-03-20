---
title: Schließen Ihres Kontos
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihr Konto bei Microsoft schließen.
ms.openlocfilehash: 19e9a92a90f7c88cc150844ab451bc71d63e4c4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911662"
---
# <a name="close-your-account"></a><span data-ttu-id="6022e-103">Schließen Ihres Kontos</span><span class="sxs-lookup"><span data-stu-id="6022e-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6022e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="6022e-104">The admin center is changing.</span></span> <span data-ttu-id="6022e-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6022e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6022e-106">Wenn Sie Ihr Microsoft-Konto schließen, werden alle Informationen zu Ihrem Konto gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6022e-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="6022e-107">Diese Informationen umfassen Abonnements, Lizenzen, Zahlungsmethoden, Benutzer und Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="6022e-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6022e-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="6022e-108">Before you begin</span></span>

<span data-ttu-id="6022e-109">Bevor Sie diesen Vorgang starten, stellen Sie sicher, dass Sie alle Daten gesichert haben, die Sie beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6022e-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="6022e-110">Sie müssen ein globaler oder ein Rechnungsadministrator sein, um die in diesem Artikel beschriebenen Schritte durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="6022e-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="6022e-111">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6022e-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="6022e-112">Schritt 1: Löschen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="6022e-112">Step 1: Delete users</span></span>

<span data-ttu-id="6022e-113">Löschen Sie alle Benutzer mit Ausnahme eines globalen Administrators.</span><span class="sxs-lookup"><span data-stu-id="6022e-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="6022e-114">Der globale Administrator schließt die Schritte zum Schließen des Kontos.</span><span class="sxs-lookup"><span data-stu-id="6022e-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="6022e-115">Bevor Sie das Verzeichnis am Ende dieses Vorgangs löschen können, müssen Sie alle anderen Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="6022e-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="6022e-116">Wenn Benutzer lokal synchronisiert werden, deaktivieren Sie zuerst die Synchronisierung, und löschen Sie dann die Benutzer im Cloudverzeichnis mithilfe des Azure-Portals oder der Azure PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6022e-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="6022e-117">Informationen zum Löschen von Benutzern finden Sie unter <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Benutzerverwaltungsadministrator: Löschen eines oder mehrere Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6022e-117">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="6022e-118">Sie können auch das <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell-Cmdlet verwenden, um Benutzer massenlos zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6022e-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="6022e-119">Wenn Ihre Organisation Active Directory verwendet, das mit Microsoft Azure Active Directory (Azure AD) synchronisiert wird, löschen Sie stattdessen das Benutzerkonto aus Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6022e-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="6022e-120">Anweisungen finden Sie unter <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Massenlöschen von Benutzern in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="6022e-120">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="6022e-121">Schritt 2: Kündigen aller aktiven Abonnements</span><span class="sxs-lookup"><span data-stu-id="6022e-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="6022e-122">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="6022e-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="6022e-123">Suchen Sie **auf** der Registerkarte Produkte nach einem aktiven Abonnement.</span><span class="sxs-lookup"><span data-stu-id="6022e-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="6022e-124">Wählen Sie **Weitere Aktionen** (drei Punkte) und dann **Abonnement kündigen** aus.</span><span class="sxs-lookup"><span data-stu-id="6022e-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="6022e-125">Wählen Sie im Bereich **Abonnement kündigen** einen Grund aus, warum Sie kündigen.</span><span class="sxs-lookup"><span data-stu-id="6022e-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="6022e-126">Geben Sie optional Feedback.</span><span class="sxs-lookup"><span data-stu-id="6022e-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="6022e-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6022e-127">Select **Save**.</span></span>
5. <span data-ttu-id="6022e-128">Wiederholen Sie die Schritte 1 bis 4, um alle aktiven Abonnements zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="6022e-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="6022e-129">Schritt 3: Löschen aller deaktivierten Abonnements</span><span class="sxs-lookup"><span data-stu-id="6022e-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="6022e-130">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="6022e-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="6022e-131">Wählen Sie **auf der** Registerkarte Produkte ein deaktiviertes Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="6022e-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="6022e-132">Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnement- und** Zahlungseinstellungen Abonnement **löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="6022e-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="6022e-133">Wählen Sie **im Bereich** Abonnement löschen die Option Abonnement **löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="6022e-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="6022e-134">Wählen Sie **im Dialogfeld Abonnement** löschen die Option Ja **aus.**</span><span class="sxs-lookup"><span data-stu-id="6022e-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="6022e-135">Wiederholen Sie für jedes deaktivierte Abonnement die Schritte 3 bis 5, bis alle Abonnements gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="6022e-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="6022e-136">Wenn Sie ein deaktiviertes Abonnement nicht sofort löschen können, wenden <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">Sie sich an den Support.</a></span><span class="sxs-lookup"><span data-stu-id="6022e-136">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="6022e-137">Schritt 4: Deaktivieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6022e-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="6022e-138">Melden Sie sich mit einem globalen Administratorkonto beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="6022e-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="6022e-139">Informationen dazu, welche Rollen Sie haben, finden Sie unter [Überprüfen von Administratorrollen in Ihrer Organisation](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="6022e-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="6022e-140">Wechseln Sie zur **Seite**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Benutzer Aktive</a> Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6022e-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="6022e-141">Wählen **Sie Mehrstufige Authentifizierung aus.**</span><span class="sxs-lookup"><span data-stu-id="6022e-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="6022e-142">Deaktivieren Sie auf der Seite mehrstufige Authentifizierung alle Konten mit Ausnahme des globalen Administratorkontos, das Sie derzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="6022e-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="6022e-143">Sie können <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell auch verwenden, um die mehrstufige</a>Authentifizierung für mehrere Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6022e-143">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="6022e-144">Schritt 5: Löschen des Verzeichnisses in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6022e-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="6022e-145">Melden Sie sich mit einem globalen <a href="https://aad.portal.azure.com/" target="_blank">Administratorkonto</a> beim Azure AD Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="6022e-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="6022e-146">Wählen Sie **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="6022e-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6022e-147">Wechseln Sie zu der Organisation, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="6022e-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="6022e-148">Wählen **Sie Mandanten löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="6022e-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="6022e-149">Wenn in Ihrer Organisation eine oder mehrere Prüfungen nicht erfolgreich sind, wird ein Link zu weiteren Informationen zum Bestehen der Prüfungen sehen.</span><span class="sxs-lookup"><span data-stu-id="6022e-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="6022e-150">Nachdem Sie alle Prüfungen bestanden haben, wählen Sie **Löschen aus,** um den Vorgang zu abschließen.</span><span class="sxs-lookup"><span data-stu-id="6022e-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="6022e-151">Nachdem Sie diesen letzten Schritt abgeschlossen haben, wird Ihr Konto bei Microsoft geschlossen und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6022e-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>