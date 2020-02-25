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
description: 'Erfahren Sie, wie Sie mit Ihrem Office 365 für Unternehmen-Konto mehrere e-Mail-Adressen namens "e-Mail-Alias" erhalten. '
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253098"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="98df8-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="98df8-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="98df8-104">Dieser Artikel ist für Office 365 Administratoren mit Geschäfts Abonnements gedacht.</span><span class="sxs-lookup"><span data-stu-id="98df8-104">This article is for Office 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="98df8-105">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="98df8-105">It's not for home users.</span></span>
  
<span data-ttu-id="98df8-106">Eine primäre e-Mail-Adresse in Office 365 ist normalerweise die e-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="98df8-106">A primary email address in Office 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="98df8-107">Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98df8-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="98df8-108">Benutzer können auch mehrere E-Mail-Adressen haben, die ihrem Office 365 Business-Konto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="98df8-108">They can also have more than one email address associated with their Office 365 for business account.</span></span> <span data-ttu-id="98df8-109">Diese zusätzlichen Adressen werden als "Aliase" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="98df8-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="98df8-110">Angenommen, Jenna hat die e-Mail-Adresse Jenna@contosoco.com, aber Sie möchte auch eine e-Mail an Jen@contosoco.com empfangen, da einige Personen auf Sie mit diesem Namen Bezug nehmen.</span><span class="sxs-lookup"><span data-stu-id="98df8-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="98df8-111">Sie können Aliase für Sie erstellen, sodass beide e-Mail-Adressen zu Jennas Posteingang wechseln.</span><span class="sxs-lookup"><span data-stu-id="98df8-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="98df8-112">Sie können bis zu 400 Aliase für einen Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="98df8-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="98df8-113">Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="98df8-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="98df8-114">Wenn Sie möchten, dass mehrere Personen e-Mails verwalten, die an eine einzelne e-Mail-Adresse wie Info@NodPublishers.com oder Sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="98df8-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="98df8-115">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="98df8-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="98df8-116">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="98df8-116">Add email aliases to a user</span></span>
<span data-ttu-id="98df8-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="98df8-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="98df8-118">Sie benötigen [Administratorberechtigungen](../add-users/about-admin-roles.md) , um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="98df8-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98df8-119">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="98df8-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="98df8-120">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="98df8-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="98df8-121">Wählen Sie auf der Seite **aktive Benutzer** den Benutzer > **e-Mail-Aliase verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="98df8-122">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="98df8-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="98df8-123">Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="98df8-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="98df8-124">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98df8-125">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="98df8-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98df8-126">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="98df8-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98df8-127">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="98df8-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="98df8-128">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="98df8-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98df8-129">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="98df8-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98df8-130">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="98df8-130">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 
  
     
5. <span data-ttu-id="98df8-131">Wenn Sie fertig sind, wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="98df8-132">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="98df8-133">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="98df8-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98df8-134">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="98df8-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98df8-135">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="98df8-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98df8-136">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="98df8-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98df8-137">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98df8-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="98df8-138">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="98df8-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="98df8-139">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="98df8-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="98df8-140">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="98df8-141">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98df8-142">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="98df8-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98df8-143">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="98df8-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98df8-144">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="98df8-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="98df8-145">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="98df8-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="98df8-146">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="98df8-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="98df8-147">Wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98df8-148">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="98df8-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98df8-149">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="98df8-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98df8-150">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="98df8-150">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="98df8-151">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="98df8-152">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="98df8-153">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="98df8-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98df8-154">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="98df8-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98df8-155">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="98df8-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98df8-156">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="98df8-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98df8-157">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98df8-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98df8-158">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="98df8-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="98df8-159">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="98df8-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="98df8-160">Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="98df8-161">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98df8-162">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="98df8-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98df8-163">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="98df8-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98df8-164">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="98df8-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="98df8-165">Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="98df8-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="98df8-166">Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="98df8-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="98df8-167">Wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98df8-168">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="98df8-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98df8-169">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="98df8-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98df8-170">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="98df8-170">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="98df8-171">Wenn Sie fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="98df8-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="98df8-172">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Office 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="98df8-173">Der Benutzer verfügt nun über eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="98df8-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98df8-174">Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.</span><span class="sxs-lookup"><span data-stu-id="98df8-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98df8-175">**Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="98df8-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98df8-176">Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an.</span><span class="sxs-lookup"><span data-stu-id="98df8-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98df8-177">Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98df8-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="98df8-178">Haben Sie "ein Parameter kann nicht gefunden werden, der mit dem Parameternamen" Emails "übereinstimmt, erhalten?</span><span class="sxs-lookup"><span data-stu-id="98df8-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="98df8-179">Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="98df8-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98df8-180">Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="98df8-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98df8-181">Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="98df8-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98df8-182">Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="98df8-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="98df8-183">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="98df8-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="98df8-184">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="98df8-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="98df8-185">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="98df8-185">Related articles</span></span>

[<span data-ttu-id="98df8-186">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="98df8-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="98df8-187">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="98df8-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

