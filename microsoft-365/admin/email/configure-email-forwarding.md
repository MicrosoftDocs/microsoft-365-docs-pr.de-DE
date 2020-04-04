---
title: Konfigurieren der E-Mail-Weiterleitung in Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Einrichten der e-Mail-Weiterleitung an ein oder mehrere e-Mail-Konten mit Office365.
ms.openlocfilehash: 963256aedb52ae0adf31790a74fbdb77ad2bb27e
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142527"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="fef04-103">Konfigurieren der E-Mail-Weiterleitung in Office 365</span><span class="sxs-lookup"><span data-stu-id="fef04-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="fef04-p101">[] Wenn Sie Administrator einer Office 365-Organisation sind, gibt es möglicherweise Bedingungen seitens des Unternehmens, was die Einrichtung von E-Mail-Weiterleitungen an das Postfach eines Benutzers betrifft. Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="fef04-p101">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="fef04-106">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="fef04-106">Configure email forwarding</span></span>

 <span data-ttu-id="fef04-107">Beachten Sie vor dem Einrichten der e-Mail-Weiterleitung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fef04-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="fef04-108">Nachdem Sie die e-Mail-Weiterleitung eingerichtet haben, werden nur **neue** e-Mails, die *an das Postfach* gesendet werden, weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fef04-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="fef04-109">Für die e-Mail-Weiterleitung muss das *von* -Konto über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="fef04-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="fef04-110">Wenn Sie die e-Mail-Weiterleitung einrichten, da der Benutzer Ihre Organisation verlassen hat, besteht eine andere Option darin, [Ihr Postfach in ein freigegebenes Postfach zu konvertieren](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="fef04-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="fef04-111">Auf diese Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fef04-111">This way several people can access it.</span></span> <span data-ttu-id="fef04-112">Ein freigegebenes Postfach darf jedoch nicht mehr als 50 GB betragen.</span><span class="sxs-lookup"><span data-stu-id="fef04-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="fef04-113">Sie müssen ein Exchange-Administrator oder globaler Administrator in Office 365 sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="fef04-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="fef04-114">Weitere Informationen finden Sie im Thema [zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fef04-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="fef04-115">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="fef04-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="fef04-116">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fef04-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="fef04-117">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fef04-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="fef04-118">Wählen Sie auf der Registerkarte **e-Mail** die Option **e-Mail-Weiterleitung verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="fef04-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="fef04-119">Wählen Sie auf der Seite e-Mail-Weiterleitung **alle an dieses Postfach gesendeten e-Mails weiterleiten**aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob eine Kopie der weitergeleiteten e-Mails aufbewahrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fef04-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fef04-120">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fef04-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fef04-121">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fef04-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="fef04-122">Um *an mehrere e-Mail-Adressen weiterzuleiten*, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fef04-122">*To forward to multiple email addresses*, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fef04-123">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fef04-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fef04-124">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="fef04-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fef04-125">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fef04-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fef04-126">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="fef04-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="fef04-127">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fef04-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fef04-128">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fef04-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fef04-129">Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="fef04-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fef04-130">Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fef04-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fef04-131">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fef04-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fef04-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fef04-132">Select **Save**.</span></span>
    
    <span data-ttu-id="fef04-133">Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fef04-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fef04-134">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fef04-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fef04-135">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="fef04-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fef04-136">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fef04-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fef04-137">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="fef04-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="fef04-138">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fef04-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fef04-139">Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fef04-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fef04-140">Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="fef04-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fef04-141">Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fef04-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fef04-142">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fef04-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fef04-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fef04-143">Select **Save**.</span></span>
    
    <span data-ttu-id="fef04-144">Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fef04-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fef04-145">Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fef04-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fef04-146">Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.</span><span class="sxs-lookup"><span data-stu-id="fef04-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fef04-147">Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fef04-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fef04-148">Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.</span><span class="sxs-lookup"><span data-stu-id="fef04-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
