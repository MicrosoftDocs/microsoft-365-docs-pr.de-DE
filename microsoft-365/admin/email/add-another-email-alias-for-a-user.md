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
description: 'Erfahren Sie, wie Sie mehr als eine E-Mail-Adresse, genannt E-Mail-Alias, mit Ihrem Microsoft 365 Business-Konto verknüpfen können. '
ms.openlocfilehash: 3c97640f4bb16876ec028a1af2b361a21a0decab
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126405"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="2fb6c-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2fb6c-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2fb6c-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-104">The admin center is changing.</span></span> <span data-ttu-id="2fb6c-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="2fb6c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
<span data-ttu-id="2fb6c-106">Dieser Artikel ist Microsoft 365-Administratoren bestimmt, die über Business-Abonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="2fb6c-107">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-107">It's not for home users.</span></span>
  
<span data-ttu-id="2fb6c-108">Eine primäre E-Mail-Adresse in Microsoft 365 ist normalerweise die E-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="2fb6c-109">Wenn der Benutzer eine E-Mail an eine andere Person senden, wird in E-Mail-Apps in der Regel seine primäre E-Mail-Adresse im Feld *Von* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="2fb6c-110">Sie können auch mehrere E-Mail-Adressen haben, die ihrem Microsoft 365 Business-Konto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="2fb6c-111">Diese zusätzlichen Adressen werden als „Aliase“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="2fb6c-112">Angenommen, Jenna hat die E-Mail-Adresse „jenna@contosoco.com“, möchte aber auch E-Mails unter „jen@contosoco.com“ empfangen, weil einige Leute sie mit diesem Namen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="2fb6c-113">Sie können Aliase für sie erstellen, sodass beide E-Mail-Adressen an Jennas Posteingang gehen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="2fb6c-114">Sie können bis zu 400 Aliase für einen Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="2fb6c-115">Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="2fb6c-116">Wenn Sie möchten, dass mehrere Personen E-Mails verwalten können, die an eine einzelne E-Mail-Adresse wie „info@NodPublishers.com“ oder „vertrieb@NodPublishers.com“ gesendet wurden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="2fb6c-117">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="2fb6c-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="2fb6c-118">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="2fb6c-118">Add email aliases to a user</span></span>
<span data-ttu-id="2fb6c-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb6c-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="2fb6c-120">Sie benötigen [Administrator-Berechtigungen](../add-users/about-admin-roles.md) zum Ausführen der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="2fb6c-121">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2fb6c-122">Wählen Sie auf der Seite **Aktive Benutzer** den Benutzer und dann **E-Mail-Aliase bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="2fb6c-123">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="2fb6c-124">Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="2fb6c-125">Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2fb6c-126">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2fb6c-127">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2fb6c-128">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="2fb6c-129">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2fb6c-130">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2fb6c-131">Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="2fb6c-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="2fb6c-132">Wenn Sie fertig sind, wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="2fb6c-133">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="2fb6c-134">Der Benutzer hat nun eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2fb6c-135">Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2fb6c-136">**Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="2fb6c-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2fb6c-137">Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2fb6c-138">Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="2fb6c-139">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="2fb6c-140">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="2fb6c-141">Wählen Sie neben **Benutzername / E-Mail-Aliase** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="2fb6c-142">Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2fb6c-143">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2fb6c-144">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2fb6c-145">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="2fb6c-146">Geben Sie im Textfeld unter **Alias** den ersten Teil der neuen E-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="2fb6c-147">Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="2fb6c-148">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2fb6c-149">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2fb6c-150">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2fb6c-151">Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="2fb6c-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="2fb6c-152">Wenn Sie fertig sind, wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="2fb6c-153">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="2fb6c-154">Der Benutzer hat nun eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2fb6c-155">Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2fb6c-156">**Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="2fb6c-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2fb6c-157">Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2fb6c-158">Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2fb6c-159">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="2fb6c-160">Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="2fb6c-161">Wählen Sie neben **Benutzername / E-Mail-Aliase** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="2fb6c-162">Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2fb6c-163">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2fb6c-164">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2fb6c-165">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="2fb6c-166">Geben Sie im Textfeld unter **Alias** den ersten Teil der neuen E-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="2fb6c-167">Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="2fb6c-168">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2fb6c-169">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2fb6c-170">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2fb6c-171">Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="2fb6c-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="2fb6c-172">Wenn Sie fertig sind, wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="2fb6c-173">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="2fb6c-174">Der Benutzer hat nun eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2fb6c-175">Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2fb6c-176">**Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="2fb6c-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="2fb6c-177">Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2fb6c-178">Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="2fb6c-179">Wurde die Fehlermeldung „Es wurde kein Parameter gefunden, der dem Parameternamen 'EmailAddresses' entspricht“ angezeigt?</span><span class="sxs-lookup"><span data-stu-id="2fb6c-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="2fb6c-180">Wenn die Fehlermeldung "**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2fb6c-181">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2fb6c-182">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2fb6c-183">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="2fb6c-184">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="2fb6c-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="2fb6c-185">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="2fb6c-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="2fb6c-186">Related articles</span></span>

[<span data-ttu-id="2fb6c-187">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="2fb6c-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="2fb6c-188">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="2fb6c-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

