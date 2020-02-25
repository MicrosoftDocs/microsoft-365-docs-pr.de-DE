---
title: Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Hier erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das mehrere Benutzer zugreifen können. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253053"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="17414-103">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="17414-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="17414-104">Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten.</span><span class="sxs-lookup"><span data-stu-id="17414-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="17414-105">Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="17414-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="17414-106">Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach wieder in ein Benutzerpostfach (privat) konvertieren.</span><span class="sxs-lookup"><span data-stu-id="17414-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="17414-107">**Hier sind einige wirklich wichtige Dinge, die Sie kennen müssen:**</span><span class="sxs-lookup"><span data-stu-id="17414-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="17414-108">Das Benutzerpostfach, das Sie konvertieren möchten, benötigt eine Lizenz, die ihm zugewiesen ist, bevor Sie es in ein freigegebenes Postfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="17414-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="17414-109">Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17414-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="17414-110">Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="17414-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="17414-111">Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="17414-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="17414-p103">Freigegebene Postfächer können bis zu 50 GB an Daten aufweisen, ohne dass eine Lizenz zugewiesen werden muss. Wenn eine größere Datenmenge gespeichert werden muss, muss eine Lizenz zugewiesen werden. Möglicherweise müssen Sie eine Reihe großer E-Mails (z. B. Dokumente mit Anlagen) aus dem freigegebenen Postfach löschen, um die Datenmenge zu verringern, damit Sie die Lizenz entfernen können.</span><span class="sxs-lookup"><span data-stu-id="17414-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="17414-p104">Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="17414-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="17414-118">Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="17414-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="17414-119">Verwenden der Exchange-Verwaltungskonsole zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="17414-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="17414-120">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="17414-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="17414-121">Wählen Sie **Empfänger** \> **Postfächer**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="17414-122">Wählen Sie das Benutzerpostfach aus.</span><span class="sxs-lookup"><span data-stu-id="17414-122">Select the user mailbox.</span></span> <span data-ttu-id="17414-123">Wählen Sie unter **in freigegebenes Postfach konvertieren die**Option **konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="17414-124">Wenn das Postfach kleiner als 50 GB ist, können Sie die [Lizenz vom Benutzer](../manage/remove-licenses-from-users.md) entfernen, damit keine Kosten mehr anfallen.</span><span class="sxs-lookup"><span data-stu-id="17414-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="17414-125">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="17414-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="17414-126">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="17414-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="17414-127">Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="17414-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="17414-128">Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters aus Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="17414-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="17414-129">Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="17414-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="17414-130">Verwenden des Microsoft 365 Admin Center zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="17414-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17414-131">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="17414-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="17414-132">Wählen Sie den Namen des Benutzers aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="17414-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="17414-133">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="17414-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="17414-134">Es ist nicht erforderlich, das Kennwort des Benutzers während der Post Fach Konvertierung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="17414-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="17414-135">Wenn das Kennwort jedoch nicht zurückgesetzt wird, **Funktionieren der ursprüngliche Benutzername und das Kennwort** nach Abschluss der Post Fach Konvertierung weiterhin.</span><span class="sxs-lookup"><span data-stu-id="17414-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="17414-136">Wählen Sie auf der Registerkarte **e-Mail** unter **Weitere Aktionen**die Option **in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17414-137">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="17414-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="17414-138">Wählen Sie den Benutzer aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="17414-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="17414-139">Erweitern Sie im rechten Bereich die Option **e-Mail-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="17414-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="17414-140">Wählen Sie neben **Weitere Einstellungen** **die Option in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="17414-141">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="17414-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="17414-142">Wählen Sie den Benutzer aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="17414-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="17414-143">Erweitern Sie im rechten Bereich die Option **e-Mail-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="17414-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="17414-144">Wählen Sie neben **Weitere Einstellungen** **die Option in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="17414-145">Wenn das Postfach kleiner als 50 GB ist, können Sie [die Lizenz vom Benutzer entfernen](../manage/remove-licenses-from-users.md)und nicht mehr bezahlen.</span><span class="sxs-lookup"><span data-stu-id="17414-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="17414-146">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="17414-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="17414-147">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="17414-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="17414-148">Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="17414-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="17414-149">Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters aus Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="17414-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="17414-150">Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="17414-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="17414-151">Konvertieren des Postfachs eines gelöschten Benutzers</span><span class="sxs-lookup"><span data-stu-id="17414-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="17414-p111">Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="17414-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="17414-154">[Stellen Sie das Konto des Benutzers wieder her](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="17414-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="17414-155">Stellen Sie sicher, dass ihm eine Office 365-Lizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="17414-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="17414-156">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="17414-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="17414-157">Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="17414-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="17414-158">Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="17414-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="17414-159">Nachdem das erledigt ist, können Sie die Lizenz aus dem Postfach des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="17414-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="17414-160">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="17414-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="17414-161">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="17414-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="17414-162">Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="17414-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="17414-163">Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="17414-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="17414-164">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="17414-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="17414-165">Wählen Sie **Empfänger** \> **freigegeben**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="17414-166">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="17414-166">Select the shared mailbox.</span></span> <span data-ttu-id="17414-167">Wählen Sie unter **Convert to Regular Mailbox die**Option **Convert**aus.</span><span class="sxs-lookup"><span data-stu-id="17414-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="17414-168">Wechseln Sie zurück zum Admin Center.</span><span class="sxs-lookup"><span data-stu-id="17414-168">Go back to the admin center.</span></span> <span data-ttu-id="17414-169">Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="17414-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="17414-170">Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="17414-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="17414-p115">Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.</span><span class="sxs-lookup"><span data-stu-id="17414-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="17414-173">Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="17414-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="17414-174">Wenn sich dieses freigegebene Postfach in einer Hybridumgebung befindet, wird **dringend empfohlen** , das Benutzerpostfach wieder in ein lokales Postfach zu migrieren, das Benutzerpostfach in ein freigegebenes Postfach zu konvertieren und das freigegebene Postfach dann wieder in die Cloud zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="17414-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="17414-175">Hier ist der Grund: Wenn Sie das Postfach in der Cloud konvertieren, kann es konvertiert werden, doch lokal ist das Postfach das Benutzerpostfach, da die neue Realität nicht wieder lokal synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="17414-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="17414-176">Normalerweise handelt es sich nicht um ein Problem, aber es gibt einige Szenarien, in denen die lokalen Attribute (die denken, dass das Postfach das Benutzerpostfach ist) die neuen Cloud-Versionen dieser Attribute überschreiben können und daher das Postfach möglicherweise wieder zurückkonvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="17414-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="17414-177">Dies ist ein Problem, da Benutzerpostfächer Lizenzen erfordern **oder nach 30 Tagen weich gelöscht werden**!</span><span class="sxs-lookup"><span data-stu-id="17414-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="17414-178">Wir haben die meisten der Gründe behandelt, warum dies geschieht, aber es kann immer noch passieren, obwohl selten.</span><span class="sxs-lookup"><span data-stu-id="17414-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="17414-179">Am besten ist es, sicher zu sein und das Postfach zurück in lokal zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="17414-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="17414-180">Wenn Sie Teil der Organisationsverwaltung oder der Empfängerverwaltung sind, können Sie die Exchange-Verwaltungsshell verwenden, um ein Benutzerpostfach in ein freigegebenes Postfach lokal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="17414-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="17414-181">Beispiel: `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="17414-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="17414-182">Weitere Informationen finden Sie unter Problemumgehung in dieser Support Lösung für Instanzen [, wenn freigegebene Postfächer unerwarteterweise in Benutzerpostfächer konvertiert werden](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di) .</span><span class="sxs-lookup"><span data-stu-id="17414-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="17414-183">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="17414-183">Related articles</span></span>

[<span data-ttu-id="17414-184">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="17414-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="17414-185">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="17414-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="17414-186">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="17414-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="17414-187">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="17414-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="17414-188">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="17414-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
