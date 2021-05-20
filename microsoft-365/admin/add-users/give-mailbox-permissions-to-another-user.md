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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Einem Benutzer das Recht geben, auf das Postfach eines anderen Benutzers zuzugreifen, wodurch der Benutzer E-Mails aus dem Postfach des anderen Benutzers lesen und senden kann.
ms.openlocfilehash: 3514be02f2ef82b727edfcf86c0bd3f6b8515510
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535962"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="fb283-103">Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="fb283-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="fb283-104">Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fb283-104">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="fb283-105">Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben.</span><span class="sxs-lookup"><span data-stu-id="fb283-105">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="fb283-106">In diesem Thema wird gezeigt, wie dies erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb283-106">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="fb283-107">Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="fb283-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="fb283-108">Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?</span><span class="sxs-lookup"><span data-stu-id="fb283-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="fb283-p102">Postfachberechtigungen ermöglichen es Ihnen, einem anderen Benutzer Lese-/Schreibzugriff auf ein Postfach zu gewähren. Möglicherweise finden Sie in den nachstehenden Artikeln die benötigte Hilfe zum Einrichten und Verwenden dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="fb283-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="fb283-111">**Einrichten der Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="fb283-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="fb283-p103">Der erste Schritt zum Einrichten von Berechtigungen ist die Entscheidung, welche Aktionen Sie dem anderen Benutzer im angegebenen Postfach erlauben möchten. Sie können einem Benutzer erlauben, E-Mails aus dem Postfach zu lesen, E-Mails im Auftrag eines anderen Benutzers zu senden und E-Mails so aussehen zu lassen, als ob sie über dieses Postfach gesendet wurden. In folgenden Artikeln finden Sie Informationen, wie die einzelnen Arten von Berechtigungen eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="fb283-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="fb283-115">Lesen von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="fb283-116">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="fb283-117">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="fb283-118">**Ändern der Weitergabe:**</span><span class="sxs-lookup"><span data-stu-id="fb283-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="fb283-119">Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="fb283-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="fb283-120">**Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**</span><span class="sxs-lookup"><span data-stu-id="fb283-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="fb283-p104">Es gibt einige Möglichkeiten, wie Sie auf ein Postfach zugreifen können, nachdem Ihnen der Zugriff darauf gewährt wurde. Hilfe zu diesem Vorgang finden Sie in diesem Artikel: [Zugreifen auf das Postfach einer anderen Person](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="fb283-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="fb283-123">Die Berechtigungen können nur innerhalb des Mandanten in der aktuellen Organisation festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb283-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="fb283-124">Es ist nicht möglich, Postfachberechtigungen für Benutzer einzurichten, die nicht zum Mandanten gehören.</span><span class="sxs-lookup"><span data-stu-id="fb283-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="fb283-125">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb283-126">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="fb283-127">Wählen Sie den Namen des Benutzers (dem Sie eine Sendeberechtigung erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fb283-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="fb283-128">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="fb283-129">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="fb283-130">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="fb283-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="fb283-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb283-132">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="fb283-133">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="fb283-134">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="fb283-135">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="fb283-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="fb283-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb283-137">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="fb283-138">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="fb283-139">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="fb283-140">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="fb283-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="fb283-141">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="fb283-142">Lesen von E-Mails im Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb283-143">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="fb283-144">Wählen Sie den Namen des Benutzers (für dessen Postfach Sie eine Leseerlaubnis erteilen möchten) aus, um seinen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fb283-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="fb283-145">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="fb283-146">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="fb283-147">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="fb283-148">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="fb283-149">Die Berechtigungen **Lesen** und **Verwalten** werden als Berechtigung **Vollzugriff** bezeichnet, wenn sie im Exchange Admin Center erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="fb283-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="fb283-150">Die Berechtigung "Vollzugriff" gewährt nicht die Berechtigung **Senden als** oder **Senden im Auftrag**.</span><span class="sxs-lookup"><span data-stu-id="fb283-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb283-151">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="fb283-152">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="fb283-153">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="fb283-154">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="fb283-155">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb283-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="fb283-157">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="fb283-158">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="fb283-159">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="fb283-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="fb283-161">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="fb283-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb283-162">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="fb283-163">Wählen Sie den Namen des Benutzers (dem Sie eine Berechtigung zum **Senden im Auftrag von** erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fb283-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="fb283-164">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="fb283-165">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="fb283-166">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="fb283-167">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb283-168">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="fb283-169">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="fb283-170">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="fb283-171">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="fb283-172">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb283-173">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="fb283-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="fb283-174">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="fb283-175">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fb283-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="fb283-176">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb283-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="fb283-177">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb283-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="fb283-178">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="fb283-178">Related content</span></span>
  
<span data-ttu-id="fb283-179">[Verwalten der E-Mail- und Kalenderelemente einer anderen Person](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fb283-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>
    
<span data-ttu-id="fb283-180">[Senden von E-Mails im Namen einer anderen Person oder Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fb283-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>

<span data-ttu-id="fb283-181">[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="fb283-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

