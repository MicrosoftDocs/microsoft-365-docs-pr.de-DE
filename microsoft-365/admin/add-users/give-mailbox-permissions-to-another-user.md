---
title: Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Erfahren Sie, wie Sie einem Benutzer die Berechtigung erteilen, auf das Postfach eines anderen Benutzers zuzugreifen. Damit erhält der Benutzer das Recht, E-Mails zu lesen und E-Mails aus dem Postfach des anderen Benutzers zu senden. '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780601"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="019ac-104">Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="019ac-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="019ac-105">Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="019ac-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="019ac-106">Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben.</span><span class="sxs-lookup"><span data-stu-id="019ac-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="019ac-107">In diesem Thema wird gezeigt, wie dies erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="019ac-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="019ac-108">Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="019ac-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="019ac-109">Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?</span><span class="sxs-lookup"><span data-stu-id="019ac-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="019ac-p103">Postfachberechtigungen ermöglichen es Ihnen, einem anderen Benutzer Lese-/Schreibzugriff auf ein Postfach zu gewähren. Möglicherweise finden Sie in den nachstehenden Artikeln die benötigte Hilfe zum Einrichten und Verwenden dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="019ac-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="019ac-112">**Einrichten der Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="019ac-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="019ac-p104">Der erste Schritt zum Einrichten von Berechtigungen ist die Entscheidung, welche Aktionen Sie dem anderen Benutzer im angegebenen Postfach erlauben möchten. Sie können einem Benutzer erlauben, E-Mails aus dem Postfach zu lesen, E-Mails im Auftrag eines anderen Benutzers zu senden und E-Mails so aussehen zu lassen, als ob sie über dieses Postfach gesendet wurden. In folgenden Artikeln finden Sie Informationen, wie die einzelnen Arten von Berechtigungen eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="019ac-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="019ac-116">Lesen von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="019ac-117">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="019ac-118">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="019ac-119">**Ändern der Weitergabe:**</span><span class="sxs-lookup"><span data-stu-id="019ac-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="019ac-120">Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="019ac-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="019ac-121">**Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**</span><span class="sxs-lookup"><span data-stu-id="019ac-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="019ac-p105">Es gibt einige Möglichkeiten, wie Sie auf ein Postfach zugreifen können, nachdem Ihnen der Zugriff darauf gewährt wurde. Hilfe zu diesem Vorgang finden Sie in diesem Artikel: [Zugreifen auf das Postfach einer anderen Person](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="019ac-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="019ac-124">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="019ac-125">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="019ac-126">Wählen Sie den Namen des Benutzers (dem Sie eine Sendeberechtigung erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="019ac-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="019ac-127">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="019ac-128">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="019ac-129">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="019ac-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="019ac-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="019ac-131">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="019ac-132">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="019ac-133">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="019ac-134">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="019ac-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="019ac-135">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="019ac-136">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="019ac-137">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="019ac-138">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="019ac-139">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="019ac-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="019ac-140">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="019ac-141">Lesen von E-Mails im Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="019ac-142">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="019ac-143">Wählen Sie den Namen des Benutzers (für dessen Postfach Sie eine Leseerlaubnis erteilen möchten) aus, um seinen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="019ac-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="019ac-144">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="019ac-145">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="019ac-146">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="019ac-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="019ac-148">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="019ac-149">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="019ac-150">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="019ac-151">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="019ac-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="019ac-153">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="019ac-154">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="019ac-155">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="019ac-156">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="019ac-157">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="019ac-158">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="019ac-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="019ac-159">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="019ac-160">Wählen Sie den Namen des Benutzers (dem Sie eine Berechtigung zum **Senden im Auftrag von** erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="019ac-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="019ac-161">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="019ac-162">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="019ac-163">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="019ac-164">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="019ac-165">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="019ac-166">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="019ac-167">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="019ac-168">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="019ac-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="019ac-170">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="019ac-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="019ac-171">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="019ac-172">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="019ac-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="019ac-173">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="019ac-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="019ac-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="019ac-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="019ac-175">Senden und Lesen von Outlook und Outlook im Web Business</span><span class="sxs-lookup"><span data-stu-id="019ac-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="019ac-p106">Möchten Sie wissen, wie Sie E-Mails aus dem Postfach eines anderen Benutzers senden können? Dann lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="019ac-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="019ac-178">Verwalten der E-Mail- und Kalenderelemente einer anderen Person</span><span class="sxs-lookup"><span data-stu-id="019ac-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="019ac-179">Senden von E-Mails im Namen einer anderen Person oder Gruppe</span><span class="sxs-lookup"><span data-stu-id="019ac-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
