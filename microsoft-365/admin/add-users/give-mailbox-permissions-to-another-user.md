---
title: Erteilen von Postfachberechtigungen für einen anderen Benutzer in Office 365 – Administratorhilfe
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Erfahren Sie, wie Sie einem Benutzer die Berechtigung erteilen, auf das Postfach eines anderen Benutzers zuzugreifen. Damit erhält der Benutzer das Recht, E-Mails zu lesen und E-Mails aus dem Postfach des anderen Benutzers zu senden. '
ms.openlocfilehash: 695068d2002b20637b6df6a2514b74828f273965
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151347"
---
# <a name="give-mailbox-permissions-to-another-user-in-office-365---admin-help"></a><span data-ttu-id="71fc8-104">Erteilen von Postfachberechtigungen für einen anderen Benutzer in Office 365 – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="71fc8-104">Give mailbox permissions to another user in Office 365 - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="71fc8-105">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="71fc8-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="71fc8-106">Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="71fc8-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="71fc8-107">Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben.</span><span class="sxs-lookup"><span data-stu-id="71fc8-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="71fc8-108">In diesem Thema wird gezeigt, wie dies erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="71fc8-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="71fc8-109">Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="71fc8-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="71fc8-110">Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?</span><span class="sxs-lookup"><span data-stu-id="71fc8-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="71fc8-p103">Postfachberechtigungen ermöglichen es Ihnen, einem anderen Benutzer Lese-/Schreibzugriff auf ein Postfach zu gewähren. Möglicherweise finden Sie in den nachstehenden Artikeln die benötigte Hilfe zum Einrichten und Verwenden dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="71fc8-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="71fc8-113">**Einrichten der Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="71fc8-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="71fc8-p104">Der erste Schritt zum Einrichten von Berechtigungen ist die Entscheidung, welche Aktionen Sie dem anderen Benutzer im angegebenen Postfach erlauben möchten. Sie können einem Benutzer erlauben, E-Mails aus dem Postfach zu lesen, E-Mails im Auftrag eines anderen Benutzers zu senden und E-Mails so aussehen zu lassen, als ob sie über dieses Postfach gesendet wurden. In folgenden Artikeln finden Sie Informationen, wie die einzelnen Arten von Berechtigungen eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="71fc8-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="71fc8-117">Lesen von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-117">Read email from another user's mailbox</span></span>](https://support.office.com/article/Read-email-from-another-user-s-mailbox-in-Office-365-cb3b6a8a-c6e8-4342-803c-3e54b6428cc2?#bkmk_reademailanotheruser)
    
- [<span data-ttu-id="71fc8-118">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-118">Send email from another user's mailbox</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
    
- [<span data-ttu-id="71fc8-119">Senden von E-Mails im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-119">Send email on behalf of a user</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
    
 <span data-ttu-id="71fc8-120">**Ändern der Weitergabe:**</span><span class="sxs-lookup"><span data-stu-id="71fc8-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="71fc8-121">Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="71fc8-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="71fc8-122">**Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**</span><span class="sxs-lookup"><span data-stu-id="71fc8-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="71fc8-p105">Es gibt einige Möglichkeiten, wie Sie auf ein Postfach zugreifen können, nachdem Ihnen der Zugriff darauf gewährt wurde. Hilfe zu diesem Vorgang finden Sie in diesem Artikel: [Zugreifen auf das Postfach einer anderen Person](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="71fc8-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="71fc8-125">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71fc8-126">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="71fc8-127">Wählen Sie den Namen des Benutzers (dem Sie eine Sendeberechtigung erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="71fc8-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="71fc8-128">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="71fc8-129">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="71fc8-130">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="71fc8-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="71fc8-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71fc8-132">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="71fc8-133">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="71fc8-134">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="71fc8-135">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="71fc8-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="71fc8-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71fc8-137">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="71fc8-138">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="71fc8-139">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="71fc8-140">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="71fc8-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="71fc8-141">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="71fc8-142">Lesen von E-Mails im Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71fc8-143">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="71fc8-144">Wählen Sie den Namen des Benutzers (für dessen Postfach Sie eine Leseerlaubnis erteilen möchten) aus, um seinen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="71fc8-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="71fc8-145">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="71fc8-146">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="71fc8-147">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="71fc8-148">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71fc8-149">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="71fc8-150">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="71fc8-151">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="71fc8-152">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="71fc8-153">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71fc8-154">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="71fc8-155">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="71fc8-156">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="71fc8-157">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="71fc8-158">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="71fc8-159">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="71fc8-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71fc8-160">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="71fc8-161">Wählen Sie den Namen des Benutzers (dem Sie eine Berechtigung zum **Senden im Auftrag von** erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="71fc8-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="71fc8-162">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="71fc8-163">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="71fc8-164">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="71fc8-165">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71fc8-166">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="71fc8-167">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="71fc8-168">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="71fc8-169">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="71fc8-170">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71fc8-171">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="71fc8-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="71fc8-172">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="71fc8-173">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="71fc8-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="71fc8-174">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71fc8-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="71fc8-175">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71fc8-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="71fc8-176">Senden und Lesen von Outlook und Outlook im Web Business</span><span class="sxs-lookup"><span data-stu-id="71fc8-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="71fc8-p106">Möchten Sie wissen, wie Sie E-Mails aus dem Postfach eines anderen Benutzers senden können? Dann lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="71fc8-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="71fc8-179">Verwalten der E-Mail- und Kalenderelemente einer anderen Person</span><span class="sxs-lookup"><span data-stu-id="71fc8-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="71fc8-180">Senden von E-Mails im Namen einer anderen Person oder Gruppe</span><span class="sxs-lookup"><span data-stu-id="71fc8-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
