---
title: Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Erfahren Sie, wie Sie mit Ihrem Microsoft 365 for Business-Konto mehr als eine e-Mail-Adresse namens "e-Mail-Alias" erhalten. '
ms.openlocfilehash: bab4ace6d497bac8892a29c76b6f2d05c4fa018f
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432325"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="d5110-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d5110-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d5110-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="d5110-104">The admin center is changing.</span></span> <span data-ttu-id="d5110-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d5110-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="d5110-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren, die über Geschäfts Abonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="d5110-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="d5110-107">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d5110-107">It's not for home users.</span></span>
  
<span data-ttu-id="d5110-108">Eine primäre e-Mail-Adresse in Microsoft 365 ist normalerweise die e-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d5110-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="d5110-109">Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5110-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="d5110-110">Sie können auch mehrere e-Mail-Adressen haben, die mit Ihrem Microsoft 365 for Business-Konto verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d5110-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="d5110-111">Diese zusätzlichen Adressen werden als "Aliase" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d5110-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="d5110-112">Angenommen, Jenna hat die e-Mail-Adresse Jenna@contosoco.com, aber Sie möchte auch eine e-Mail an Jen@contosoco.com empfangen, da einige Personen auf Sie mit diesem Namen Bezug nehmen.</span><span class="sxs-lookup"><span data-stu-id="d5110-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="d5110-113">Sie können Aliase für Sie erstellen, sodass beide e-Mail-Adressen zu Jennas Posteingang wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5110-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="d5110-114">Sie können bis zu 400 Aliase für einen Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5110-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="d5110-115">Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="d5110-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="d5110-116">Wenn Sie möchten, dass mehrere Personen e-Mails verwalten, die an eine einzelne e-Mail-Adresse wie Info@NodPublishers.com oder Sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="d5110-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="d5110-117">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="d5110-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="d5110-118">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="d5110-118">Add email aliases to a user</span></span>
<span data-ttu-id="d5110-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="d5110-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="d5110-120">Sie benötigen [Administratorberechtigungen](../add-users/about-admin-roles.md) , um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="d5110-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="d5110-121">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d5110-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d5110-122">Wählen Sie auf der Seite **aktive Benutzer** den Benutzer > **e-Mail-Aliase verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="d5110-123">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="d5110-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="d5110-124">Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="d5110-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="d5110-125">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d5110-126">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d5110-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d5110-127">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="d5110-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d5110-128">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d5110-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="d5110-129">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5110-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d5110-130">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="d5110-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d5110-131">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="d5110-131">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="d5110-132">Wenn Sie fertig sind, wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="d5110-133">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-133">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="d5110-134">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="d5110-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d5110-135">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="d5110-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d5110-136">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="d5110-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d5110-137">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="d5110-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d5110-138">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5110-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="d5110-139">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d5110-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="d5110-140">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5110-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d5110-141">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d5110-142">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d5110-143">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d5110-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d5110-144">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="d5110-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d5110-145">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d5110-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d5110-146">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="d5110-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d5110-147">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="d5110-147">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d5110-148">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d5110-149">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5110-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d5110-150">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="d5110-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d5110-151">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="d5110-151">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d5110-152">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d5110-153">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-153">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d5110-154">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="d5110-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d5110-155">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="d5110-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d5110-156">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="d5110-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d5110-157">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="d5110-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d5110-158">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5110-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d5110-159">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="d5110-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="d5110-160">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5110-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d5110-161">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d5110-162">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d5110-163">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d5110-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d5110-164">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="d5110-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d5110-165">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d5110-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d5110-166">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="d5110-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d5110-167">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="d5110-167">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d5110-168">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d5110-169">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5110-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d5110-170">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="d5110-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d5110-171">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="d5110-171">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d5110-172">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d5110-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d5110-173">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-173">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d5110-174">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="d5110-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d5110-175">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="d5110-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d5110-176">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="d5110-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d5110-177">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="d5110-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d5110-178">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5110-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="d5110-179">Haben Sie "ein Parameter kann nicht gefunden werden, der mit dem Parameternamen" Emails "übereinstimmt, erhalten?</span><span class="sxs-lookup"><span data-stu-id="d5110-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="d5110-180">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d5110-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d5110-181">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d5110-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d5110-182">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="d5110-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d5110-183">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d5110-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="d5110-184">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="d5110-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="d5110-185">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5110-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d5110-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d5110-186">Related articles</span></span>

[<span data-ttu-id="d5110-187">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="d5110-187">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="d5110-188">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="d5110-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

