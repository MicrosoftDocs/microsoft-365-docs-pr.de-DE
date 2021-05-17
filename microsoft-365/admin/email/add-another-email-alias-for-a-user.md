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
ms.openlocfilehash: fd5fe2906335c8c2d1f41ac7643b7312138e15f5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241688"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="2feed-103">Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2feed-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="2feed-104">Dieser Artikel ist Microsoft 365-Administratoren bestimmt, die über Business-Abonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="2feed-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="2feed-105">Er gilt nicht für private Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2feed-105">It's not for home users.</span></span>
  
<span data-ttu-id="2feed-106">Eine primäre E-Mail-Adresse in Microsoft 365 ist normalerweise die E-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2feed-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="2feed-107">Wenn der Benutzer eine E-Mail an eine andere Person senden, wird in E-Mail-Apps in der Regel seine primäre E-Mail-Adresse im Feld *Von* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2feed-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="2feed-108">Sie können auch mehrere E-Mail-Adressen haben, die ihrem Microsoft 365 Business-Konto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2feed-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="2feed-109">Diese zusätzlichen Adressen werden als „Aliase“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2feed-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="2feed-110">Angenommen, Jenna hat die E-Mail-Adresse „jenna@contosoco.com“, möchte aber auch E-Mails unter „jen@contosoco.com“ empfangen, weil einige Leute sie mit diesem Namen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="2feed-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="2feed-111">Sie können Aliase für sie erstellen, sodass beide E-Mail-Adressen an Jennas Posteingang gehen.</span><span class="sxs-lookup"><span data-stu-id="2feed-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="2feed-p104">Sie können bis zu 400 Aliase für einen Benutzer erstellen. Es fallen keine zusätzlichen Gebühren oder Lizenzen an.</span><span class="sxs-lookup"><span data-stu-id="2feed-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="2feed-114">Wenn Sie möchten, dass mehrere Personen E-Mails verwalten können, die an eine einzelne E-Mail-Adresse wie „info@NodPublishers.com“ oder „vertrieb@NodPublishers.com“ gesendet wurden, erstellen Sie ein freigegebenes Postfach.</span><span class="sxs-lookup"><span data-stu-id="2feed-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="2feed-115">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="2feed-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="2feed-116">Hinzufügen von E-Mail-Aliasen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="2feed-116">Add email aliases to a user</span></span>

<span data-ttu-id="2feed-117">Sie benötigen [Administrator-Berechtigungen](../add-users/about-admin-roles.md) zum Ausführen der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="2feed-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="2feed-118">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="2feed-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2feed-119">Wählen Sie **auf der** Seite Aktive Benutzer den Benutzer > Benutzernamen **und E-Mail verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="2feed-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="2feed-120">Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2feed-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="2feed-121">Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="2feed-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="2feed-122">Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2feed-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2feed-123">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2feed-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2feed-124">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2feed-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2feed-125">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2feed-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="2feed-126">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2feed-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="2feed-127">Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden.</span><span class="sxs-lookup"><span data-stu-id="2feed-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="2feed-128">Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="2feed-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="2feed-129">Wenn Sie fertig sind, wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2feed-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="2feed-130">Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben.</span><span class="sxs-lookup"><span data-stu-id="2feed-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="2feed-131">Der Benutzer hat nun eine primäre Adresse und einen Alias.</span><span class="sxs-lookup"><span data-stu-id="2feed-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="2feed-132">Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.</span><span class="sxs-lookup"><span data-stu-id="2feed-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="2feed-133">**Wenn der Benutzer antwortet, hängt die *Von-Adresse* von ihrem Outlook ab. Outlook im Web verwendet den Alias, unter dem die E-Mail empfangen wurde (wir nennen dies das Ping-Pong-Prinzip). Outlook Desktop verwendet ihren primären E-Mail-Alias.**</span><span class="sxs-lookup"><span data-stu-id="2feed-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="2feed-134">Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen.</span><span class="sxs-lookup"><span data-stu-id="2feed-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="2feed-135">Wenn Eliza auf die Nachricht mit Outlook antwortet, wird ihre primäre E-Mail-Adresse als Eliza@NodPublishers.com, nicht als Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="2feed-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="2feed-136">Wurde die Fehlermeldung „Es wurde kein Parameter gefunden, der dem Parameternamen 'EmailAddresses' entspricht“ angezeigt?</span><span class="sxs-lookup"><span data-stu-id="2feed-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="2feed-137">Wenn die Fehlermeldung "**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2feed-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="2feed-138">Der Setupvorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="2feed-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="2feed-139">Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="2feed-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="2feed-140">Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.</span><span class="sxs-lookup"><span data-stu-id="2feed-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="2feed-141">Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?</span><span class="sxs-lookup"><span data-stu-id="2feed-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="2feed-142">Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.</span><span class="sxs-lookup"><span data-stu-id="2feed-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="2feed-143">Einfaches Senden von E-Mails von der Proxyadresse</span><span class="sxs-lookup"><span data-stu-id="2feed-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="2feed-144">Im April 2021 wird ein neues Feature ins Rollen gebracht, mit dem Benutzer bei der Verwendung von Outlook im Web einfach von ihren Aliasen senden können.</span><span class="sxs-lookup"><span data-stu-id="2feed-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="2feed-145">Wenn das Feature in einen Mandanten rollt, in dem der Mandantenadministrator das Cmdlet verwendet, erhalten Benutzer innerhalb des Mandanten Zugriff auf eine Liste von Kontrollkästchen, in denen jeder Eintrag einem Alias in den Einstellungen Outlook `Set-OrganizationConfig -SendFromAliasEnabled $true` entspricht.</span><span class="sxs-lookup"><span data-stu-id="2feed-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="2feed-146">Wenn Sie einen Alias auswählen, wird er im Dropdownmenü Von im Formular Verfassen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2feed-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="2feed-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="2feed-147">Related articles</span></span>

[<span data-ttu-id="2feed-148">Senden von E-Mail über eine andere Adresse</span><span class="sxs-lookup"><span data-stu-id="2feed-148">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="2feed-149">Ändern eines Benutzernamens und einer E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="2feed-149">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
