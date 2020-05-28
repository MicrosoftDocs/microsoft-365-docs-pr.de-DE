---
title: Schließen Ihres Kontos
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihr Konto bei Microsoft schließen.
ms.openlocfilehash: f399a1ba4d67abf5982c111e9b915f02324150a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402178"
---
# <a name="close-your-account"></a><span data-ttu-id="3e97f-103">Schließen Ihres Kontos</span><span class="sxs-lookup"><span data-stu-id="3e97f-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3e97f-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="3e97f-104">The admin center is changing.</span></span> <span data-ttu-id="3e97f-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3e97f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3e97f-106">Wenn Sie Ihr Microsoft-Konto schließen, werden alle Informationen zu Ihrem Konto gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3e97f-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="3e97f-107">Diese Informationen umfassen Abonnements, Lizenzen, Zahlungsmethoden, Benutzer und Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="3e97f-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="3e97f-108">Bevor Sie diesen Prozess starten, müssen Sie sicherstellen, dass alle Daten gesichert werden, die Sie beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="3e97f-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="3e97f-109">Schritt 1: Löschen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="3e97f-109">Step 1: Delete users</span></span>

<span data-ttu-id="3e97f-110">Löschen Sie alle Benutzer mit Ausnahme eines globalen Administrators, der die Schritte zum Schließen des Kontos abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="3e97f-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="3e97f-111">Bevor Sie das Verzeichnis am Ende dieses Prozesses löschen können, müssen Sie alle anderen Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="3e97f-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="3e97f-112">Wenn Benutzer lokal synchronisiert werden, deaktivieren Sie zunächst die Synchronisierung, und löschen Sie dann die Benutzer im Cloud-Verzeichnis mithilfe des Azure-Portals oder der Azure PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3e97f-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="3e97f-113">Informationen zum Löschen von Benutzern finden Sie unter <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Benutzer Verwaltungs Administrator: Löschen eines oder mehrerer Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="3e97f-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="3e97f-114">Sie können auch das Cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell verwenden, um Benutzer in Massen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3e97f-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="3e97f-115">Wenn Ihre Organisation Active Directory verwendet, die mit Azure AD synchronisiert werden, löschen Sie stattdessen das Benutzerkonto aus Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3e97f-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="3e97f-116">Anweisungen finden Sie unter <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Massenlöschung von Benutzern in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="3e97f-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="3e97f-117">Schritt 2: Abbrechen aller aktiven Abonnements</span><span class="sxs-lookup"><span data-stu-id="3e97f-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="3e97f-118">Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .</span><span class="sxs-lookup"><span data-stu-id="3e97f-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="3e97f-119">Wenn sich die Liste Abonnements in der **Tabellen** Ansicht befindet, wählen Sie auf der rechten Seite **Karten**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="3e97f-120">Suchen Sie ein aktives Abonnement, und wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Abonnement kündigen**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="3e97f-121">Befolgten Sie die Anweisungen, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3e97f-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="3e97f-122">Wiederholen Sie die Schritte 1 bis 4, um alle aktiven Abonnements abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="3e97f-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="3e97f-123">Schritt 3: Löschen aller deaktivierten Abonnements</span><span class="sxs-lookup"><span data-stu-id="3e97f-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="3e97f-124">Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .</span><span class="sxs-lookup"><span data-stu-id="3e97f-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="3e97f-125">Wenn sich die Liste Abonnements in der **Tabellen** Ansicht befindet, wählen Sie auf der rechten Seite **Karten**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="3e97f-126">Wählen Sie neben **Abonnementstatus**die Option **deaktiviert**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="3e97f-127">Suchen Sie nach einem deaktivierten Abonnement, und wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="3e97f-128">Aktivieren Sie im Dialogfeld **Abonnement löschen** das Kontrollkästchen **Ich verstehe den Einfluss** , und wählen Sie dann **Abonnement löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="3e97f-129">Wiederholen Sie für jedes deaktivierte Abonnement die Schritte 4 und 5, bis alle Abonnements gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="3e97f-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="3e97f-130">Schritt 4: Deaktivieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3e97f-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="3e97f-131">Wechseln Sie im Admin Center zur Seite **Benutzer**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktive Benutzer</a> .</span><span class="sxs-lookup"><span data-stu-id="3e97f-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="3e97f-132">Wählen Sie die mehrstufige **Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="3e97f-133">Deaktivieren Sie auf der Seite mehrstufige Authentifizierung alle Konten mit Ausnahme des globalen Administratorkontos, das Sie derzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e97f-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="3e97f-134">Sie können auch <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell verwenden, um die mehrstufige Authentifizierung für mehrere Benutzer zu deaktivieren</a>.</span><span class="sxs-lookup"><span data-stu-id="3e97f-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="3e97f-135">Schritt 5: Löschen des Verzeichnisses in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3e97f-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="3e97f-136">Melden Sie sich beim <a href="https://aad.portal.azure.com/" target="_blank">Azure AD Admin Center</a> mit einem globalen Administrator Konto an.</span><span class="sxs-lookup"><span data-stu-id="3e97f-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="3e97f-137">Wählen Sie **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="3e97f-138">Wechseln Sie zu dem Verzeichnis, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3e97f-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="3e97f-139">Wählen Sie **Verzeichnis löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="3e97f-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="3e97f-140">Wenn Ihr Verzeichnis mindestens eine Überprüfung ausfällt, wird ein Link zu weiteren Informationen zum übergeben der Prüfungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e97f-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="3e97f-141">Nachdem Sie alle Prüfungen übergeben haben, wählen Sie **Delete** aus, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3e97f-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="3e97f-142">Nachdem Sie diesen letzten Schritt abgeschlossen haben, wird Ihr Konto bei Microsoft geschlossen und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3e97f-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
