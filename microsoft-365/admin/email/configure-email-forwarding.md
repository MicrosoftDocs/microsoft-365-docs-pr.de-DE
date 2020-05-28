---
title: Konfigurieren der E-Mail-Weiterleitung
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Einrichten der e-Mail-Weiterleitung an ein oder mehrere e-Mail-Konten mit Office365.
ms.openlocfilehash: 72eca099f0c7e60efe8f616dfe23201cd46975cf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400124"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="f7ee6-103">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="f7ee6-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f7ee6-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-104">The admin center is changing.</span></span> <span data-ttu-id="f7ee6-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="f7ee6-106">Als Administrator einer Organisation haben Sie möglicherweise Unternehmens Anforderungen, um die e-Mail-Weiterleitung für das Postfach eines Benutzers einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="f7ee6-107">Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="f7ee6-108">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="f7ee6-108">Configure email forwarding</span></span>

 <span data-ttu-id="f7ee6-109">Beachten Sie vor dem Einrichten der e-Mail-Weiterleitung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f7ee6-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="f7ee6-110">Nachdem Sie die e-Mail-Weiterleitung eingerichtet haben, sind nur **neue** e-Mails, die an das Postfach " *von* " gesendet werden, in.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="f7ee6-111">Für die e-Mail-Weiterleitung muss das *von* -Konto über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="f7ee6-112">Wenn Sie die e-Mail-Weiterleitung einrichten, da der Benutzer Ihre Organisation verlassen hat, besteht eine andere Option darin, [Ihr Postfach in ein freigegebenes Postfach zu konvertieren](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="f7ee6-113">Auf diese Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-113">This way several people can access it.</span></span> <span data-ttu-id="f7ee6-114">Ein freigegebenes Postfach darf jedoch nicht mehr als 50 GB betragen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="f7ee6-115">Sie müssen ein Exchange-Administrator oder globaler Administrator in Microsoft 365 sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="f7ee6-116">Weitere Informationen finden Sie im Thema [zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f7ee6-117">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="f7ee6-118">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="f7ee6-119">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="f7ee6-120">Wählen Sie auf der Registerkarte **e-Mail** die Option **e-Mail-Weiterleitung verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="f7ee6-121">Wählen Sie auf der Seite e-Mail-Weiterleitung **alle an dieses Postfach gesendeten e-Mails weiterleiten**aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob eine Kopie der weitergeleiteten e-Mails aufbewahrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="f7ee6-122">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="f7ee6-123">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="f7ee6-124">Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="f7ee6-125">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="f7ee6-126">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="f7ee6-127">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="f7ee6-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="f7ee6-128">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="f7ee6-129">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="f7ee6-130">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="f7ee6-131">Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="f7ee6-132">Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="f7ee6-133">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="f7ee6-134">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-134">Select **Save**.</span></span>
    
    <span data-ttu-id="f7ee6-135">Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="f7ee6-136">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="f7ee6-137">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="f7ee6-138">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="f7ee6-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="f7ee6-139">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f7ee6-140">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="f7ee6-141">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="f7ee6-142">Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="f7ee6-143">Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="f7ee6-144">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="f7ee6-145">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-145">Select **Save**.</span></span>
    
    <span data-ttu-id="f7ee6-146">Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="f7ee6-147">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="f7ee6-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="f7ee6-148">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="f7ee6-149">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="f7ee6-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="f7ee6-150">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="f7ee6-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
