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
ms.openlocfilehash: 0b6977efbd6041a11c67ed66c9b7ecc72a38bde4
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560375"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="abc6d-104">Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="abc6d-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="abc6d-105">Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="abc6d-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="abc6d-106">Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben.</span><span class="sxs-lookup"><span data-stu-id="abc6d-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="abc6d-107">In diesem Thema wird gezeigt, wie dies erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="abc6d-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="abc6d-108">Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="abc6d-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="abc6d-109">Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?</span><span class="sxs-lookup"><span data-stu-id="abc6d-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="abc6d-p103">Postfachberechtigungen ermöglichen es Ihnen, einem anderen Benutzer Lese-/Schreibzugriff auf ein Postfach zu gewähren. Möglicherweise finden Sie in den nachstehenden Artikeln die benötigte Hilfe zum Einrichten und Verwenden dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="abc6d-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="abc6d-112">**Einrichten der Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="abc6d-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="abc6d-p104">Der erste Schritt zum Einrichten von Berechtigungen ist die Entscheidung, welche Aktionen Sie dem anderen Benutzer im angegebenen Postfach erlauben möchten. Sie können einem Benutzer erlauben, E-Mails aus dem Postfach zu lesen, E-Mails im Auftrag eines anderen Benutzers zu senden und E-Mails so aussehen zu lassen, als ob sie über dieses Postfach gesendet wurden. In folgenden Artikeln finden Sie Informationen, wie die einzelnen Arten von Berechtigungen eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="abc6d-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="abc6d-116">Lesen von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="abc6d-117">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="abc6d-118">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="abc6d-119">**Ändern der Weitergabe:**</span><span class="sxs-lookup"><span data-stu-id="abc6d-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="abc6d-120">Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="abc6d-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="abc6d-121">**Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**</span><span class="sxs-lookup"><span data-stu-id="abc6d-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="abc6d-p105">Es gibt einige Möglichkeiten, wie Sie auf ein Postfach zugreifen können, nachdem Ihnen der Zugriff darauf gewährt wurde. Hilfe zu diesem Vorgang finden Sie in diesem Artikel: [Zugreifen auf das Postfach einer anderen Person](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="abc6d-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="abc6d-124">Die Berechtigungen können nur innerhalb des Mandanten in der aktuellen Organisation festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="abc6d-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="abc6d-125">Es ist nicht möglich, Postfachberechtigungen für Benutzer einzurichten, die nicht zum Mandanten gehören.</span><span class="sxs-lookup"><span data-stu-id="abc6d-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="abc6d-126">Senden von E-Mails aus dem Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="abc6d-127">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="abc6d-128">Wählen Sie den Namen des Benutzers (dem Sie eine Sendeberechtigung erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="abc6d-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="abc6d-129">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="abc6d-130">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="abc6d-131">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="abc6d-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="abc6d-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="abc6d-133">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="abc6d-134">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="abc6d-135">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="abc6d-136">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="abc6d-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="abc6d-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="abc6d-138">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="abc6d-139">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="abc6d-140">Wählen Sie neben **Senden als** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="abc6d-141">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann.</span><span class="sxs-lookup"><span data-stu-id="abc6d-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="abc6d-142">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="abc6d-143">Lesen von E-Mails im Postfach eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="abc6d-144">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="abc6d-145">Wählen Sie den Namen des Benutzers (für dessen Postfach Sie eine Leseerlaubnis erteilen möchten) aus, um seinen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="abc6d-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="abc6d-146">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="abc6d-147">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="abc6d-148">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="abc6d-149">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-149">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="abc6d-150">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="abc6d-151">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-151">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="abc6d-152">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-152">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="abc6d-153">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-153">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="abc6d-154">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-154">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="abc6d-155">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="abc6d-156">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-156">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="abc6d-157">Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-157">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="abc6d-158">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-158">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="abc6d-159">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-159">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="abc6d-160">Senden von E-Mails im Auftrag eines anderen Benutzers</span><span class="sxs-lookup"><span data-stu-id="abc6d-160">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="abc6d-161">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-161">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="abc6d-162">Wählen Sie den Namen des Benutzers (dem Sie eine Berechtigung zum **Senden im Auftrag von** erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="abc6d-162">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="abc6d-163">Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-163">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="abc6d-164">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-164">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="abc6d-165">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-165">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="abc6d-166">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-166">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="abc6d-167">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="abc6d-168">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-168">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="abc6d-169">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-169">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="abc6d-170">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-170">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="abc6d-171">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-171">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="abc6d-172">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="abc6d-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="abc6d-173">Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-173">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="abc6d-174">Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="abc6d-174">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="abc6d-175">Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abc6d-175">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="abc6d-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="abc6d-176">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="abc6d-177">Senden und Lesen von Outlook und Outlook im Web Business</span><span class="sxs-lookup"><span data-stu-id="abc6d-177">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="abc6d-p107">Möchten Sie wissen, wie Sie E-Mails aus dem Postfach eines anderen Benutzers senden können? Dann lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="abc6d-p107">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="abc6d-180">Verwalten der E-Mail- und Kalenderelemente einer anderen Person</span><span class="sxs-lookup"><span data-stu-id="abc6d-180">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="abc6d-181">Senden von E-Mails im Namen einer anderen Person oder Gruppe</span><span class="sxs-lookup"><span data-stu-id="abc6d-181">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
