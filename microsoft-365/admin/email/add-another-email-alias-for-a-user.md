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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Erfahren Sie, wie Sie mit Ihrem Microsoft 365 for Business-Konto mehr als eine e-Mail-Adresse namens "e-Mail-Alias" erhalten. '
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140512"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="76686-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="76686-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="76686-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="76686-104">The admin center is changing.</span></span> <span data-ttu-id="76686-105">Wenn Ihre Erfahrung nicht mit den hier dargestellten Details übereinstimmt, lesen Sie [Informationen zum neuen Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="76686-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="76686-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren, die über Geschäfts Abonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="76686-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="76686-107">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="76686-107">It's not for home users.</span></span>
  
<span data-ttu-id="76686-108">Eine primäre e-Mail-Adresse in Microsoft 365 ist normalerweise die e-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="76686-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="76686-109">Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76686-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="76686-110">Sie können auch mehrere e-Mail-Adressen haben, die mit Ihrem Microsoft 365 for Business-Konto verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="76686-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="76686-111">Diese zusätzlichen Adressen werden als "Aliase" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="76686-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="76686-112">Angenommen, Jenna hat die e-Mail-Adresse Jenna@contosoco.com, aber Sie möchte auch eine e-Mail an Jen@contosoco.com empfangen, da einige Personen auf Sie mit diesem Namen Bezug nehmen.</span><span class="sxs-lookup"><span data-stu-id="76686-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="76686-113">Sie können Aliase für Sie erstellen, sodass beide e-Mail-Adressen zu Jennas Posteingang wechseln.</span><span class="sxs-lookup"><span data-stu-id="76686-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="76686-114">Sie können bis zu 400 Aliase für einen Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="76686-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="76686-115">Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="76686-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="76686-116">Wenn Sie möchten, dass mehrere Personen e-Mails verwalten, die an eine einzelne e-Mail-Adresse wie Info@NodPublishers.com oder Sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="76686-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="76686-117">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="76686-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="76686-118">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="76686-118">Add email aliases to a user</span></span>
<span data-ttu-id="76686-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="76686-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="76686-120">Sie benötigen [Administratorberechtigungen](../add-users/about-admin-roles.md) , um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="76686-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="76686-121">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="76686-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="76686-122">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="76686-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="76686-123">Wählen Sie auf der Seite **aktive Benutzer** den Benutzer > **e-Mail-Aliase verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="76686-124">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="76686-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="76686-125">Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="76686-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="76686-126">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="76686-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="76686-127">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="76686-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="76686-128">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="76686-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="76686-129">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="76686-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="76686-130">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="76686-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="76686-131">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="76686-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="76686-132">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="76686-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="76686-133">Wenn Sie fertig sind, wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="76686-134">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="76686-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="76686-135">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="76686-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="76686-136">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="76686-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="76686-137">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="76686-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="76686-138">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="76686-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="76686-139">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76686-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="76686-140">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="76686-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="76686-141">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="76686-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="76686-142">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="76686-143">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="76686-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="76686-144">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="76686-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="76686-145">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="76686-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="76686-146">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="76686-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="76686-147">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="76686-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="76686-148">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="76686-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="76686-149">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="76686-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="76686-150">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="76686-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="76686-151">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="76686-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="76686-152">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="76686-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="76686-153">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="76686-154">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="76686-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="76686-155">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="76686-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="76686-156">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="76686-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="76686-157">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="76686-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="76686-158">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="76686-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="76686-159">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76686-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="76686-160">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="76686-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="76686-161">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="76686-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="76686-162">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="76686-163">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="76686-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="76686-164">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="76686-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="76686-165">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="76686-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="76686-166">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="76686-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="76686-167">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="76686-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="76686-168">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="76686-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="76686-169">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="76686-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="76686-170">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="76686-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="76686-171">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="76686-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="76686-172">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="76686-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="76686-173">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="76686-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="76686-174">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="76686-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="76686-175">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="76686-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="76686-176">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="76686-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="76686-177">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="76686-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="76686-178">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="76686-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="76686-179">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76686-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="76686-180">Haben Sie "ein Parameter kann nicht gefunden werden, der mit dem Parameternamen" Emails "übereinstimmt, erhalten?</span><span class="sxs-lookup"><span data-stu-id="76686-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="76686-181">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="76686-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="76686-182">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="76686-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="76686-183">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="76686-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="76686-184">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="76686-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="76686-185">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="76686-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="76686-186">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="76686-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="76686-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="76686-187">Related articles</span></span>

[<span data-ttu-id="76686-188">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="76686-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="76686-189">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="76686-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

