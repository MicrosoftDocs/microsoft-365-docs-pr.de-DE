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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Erfahren Sie, wie Sie ihrem Microsoft 365 Business-Konto mehr als eine E-Mail-Adresse, den so genannten E-Mail-Alias, zugeordnet haben können. '
ms.openlocfilehash: 3c97640f4bb16876ec028a1af2b361a21a0decab
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126405"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="ee063-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ee063-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ee063-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="ee063-104">The admin center is changing.</span></span> <span data-ttu-id="ee063-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ee063-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
<span data-ttu-id="ee063-106">Dieser Artikel ist für Microsoft 365-Administratoren vorgesehen, die über Geschäftsabonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="ee063-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="ee063-107">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ee063-107">It's not for home users.</span></span>
  
<span data-ttu-id="ee063-108">Eine primäre E-Mail-Adresse in Microsoft 365 ist in der Regel die E-Mail-Adresse, die einem Benutzer zugewiesen wurde, als sein Konto erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ee063-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="ee063-109">Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee063-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="ee063-110">Sie können ihrem Microsoft 365 Business-Konto auch mehrere E-Mail-Adressen zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="ee063-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="ee063-111">Diese zusätzlichen Adressen werden als "Aliase" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ee063-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="ee063-112">Nehmen wir beispielsweise an, dass Jenna die E-Mail-Adresse jenna@contosoco.com hat, aber sie möchte auch E-Mails bei jen@contosoco.com empfangen, da einige Personen mit diesem Namen auf sie verweisen.</span><span class="sxs-lookup"><span data-stu-id="ee063-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="ee063-113">Sie können Aliase für sie erstellen, damit beide E-Mail-Adressen in Jennas Posteingang gehen.</span><span class="sxs-lookup"><span data-stu-id="ee063-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="ee063-114">Sie können bis zu 400 Aliase für einen Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="ee063-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="ee063-115">Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="ee063-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="ee063-116">Wenn Sie möchten, dass mehrere Personen E-Mails verwalten, die an eine einzelne E-Mail-Adresse wie info@NodPublishers.com oder sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="ee063-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="ee063-117">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="ee063-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="ee063-118">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="ee063-118">Add email aliases to a user</span></span>
<span data-ttu-id="ee063-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="ee063-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="ee063-120">Dazu müssen Sie [über Administratorberechtigungen](../add-users/about-admin-roles.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="ee063-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee063-121">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="ee063-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ee063-122">Wählen Sie **auf der Seite "Aktive** Benutzer" den Benutzer aus, > **E-Mail-Aliase verwalten.**</span><span class="sxs-lookup"><span data-stu-id="ee063-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="ee063-123">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ee063-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="ee063-124">Wählen **Sie +Hinzufügen eines Alias** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="ee063-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="ee063-125">Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ee063-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ee063-126">Der Einrichtungsvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="ee063-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ee063-127">Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="ee063-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ee063-128">Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.</span><span class="sxs-lookup"><span data-stu-id="ee063-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="ee063-129">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="ee063-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ee063-130">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="ee063-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ee063-131">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="ee063-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="ee063-132">Wenn Sie fertig sind, wählen Sie **"Änderungen speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="ee063-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="ee063-133">Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen.</span><span class="sxs-lookup"><span data-stu-id="ee063-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="ee063-134">Der Benutzer hat jetzt eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="ee063-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ee063-135">Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee063-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ee063-136">**Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="ee063-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ee063-137">Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft.</span><span class="sxs-lookup"><span data-stu-id="ee063-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ee063-138">Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ee063-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="ee063-139">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="ee063-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="ee063-140">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ee063-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="ee063-141">Wählen Sie neben **"Benutzername/E-Mail-Aliase"** die Option **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="ee063-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="ee063-142">Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ee063-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ee063-143">Der Einrichtungsvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="ee063-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ee063-144">Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="ee063-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ee063-145">Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.</span><span class="sxs-lookup"><span data-stu-id="ee063-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="ee063-146">Geben Sie im Textfeld unter **Alias** den ersten Teil des neuen E-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="ee063-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="ee063-147">Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee063-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="ee063-148">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ee063-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ee063-149">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="ee063-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ee063-150">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="ee063-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ee063-151">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="ee063-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="ee063-152">Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.</span><span class="sxs-lookup"><span data-stu-id="ee063-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="ee063-153">Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen.</span><span class="sxs-lookup"><span data-stu-id="ee063-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="ee063-154">Der Benutzer hat jetzt eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="ee063-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ee063-155">Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee063-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ee063-156">**Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="ee063-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ee063-157">Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft.</span><span class="sxs-lookup"><span data-stu-id="ee063-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ee063-158">Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ee063-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ee063-159">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="ee063-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="ee063-160">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ee063-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="ee063-161">Wählen Sie neben **"Benutzername/E-Mail-Aliase"** die Option **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="ee063-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="ee063-162">Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ee063-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ee063-163">Der Einrichtungsvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="ee063-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ee063-164">Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="ee063-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ee063-165">Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.</span><span class="sxs-lookup"><span data-stu-id="ee063-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="ee063-166">Geben Sie im Textfeld unter **Alias** den ersten Teil des neuen E-Mail-Alias ein.</span><span class="sxs-lookup"><span data-stu-id="ee063-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="ee063-167">Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee063-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="ee063-168">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ee063-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ee063-169">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="ee063-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ee063-170">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="ee063-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ee063-171">Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="ee063-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="ee063-172">Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.</span><span class="sxs-lookup"><span data-stu-id="ee063-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="ee063-173">Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen.</span><span class="sxs-lookup"><span data-stu-id="ee063-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="ee063-174">Der Benutzer hat jetzt eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="ee063-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ee063-175">Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee063-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ee063-176">**Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="ee063-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ee063-177">Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft.</span><span class="sxs-lookup"><span data-stu-id="ee063-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ee063-178">Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ee063-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="ee063-179">Haben Sie "Ein Parameter, der dem Parameternamen "EmailAddresses" entspricht, nicht gefunden?</span><span class="sxs-lookup"><span data-stu-id="ee063-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="ee063-180">Wenn die Fehlermeldung "Ein Parameter, der dem Parameternamen **"EmailAddresses"** entspricht, nicht gefunden wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ee063-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ee063-181">Der Einrichtungsvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="ee063-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ee063-182">Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="ee063-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ee063-183">Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.</span><span class="sxs-lookup"><span data-stu-id="ee063-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="ee063-184">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="ee063-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="ee063-185">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="ee063-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="ee063-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ee063-186">Related articles</span></span>

[<span data-ttu-id="ee063-187">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="ee063-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="ee063-188">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="ee063-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

