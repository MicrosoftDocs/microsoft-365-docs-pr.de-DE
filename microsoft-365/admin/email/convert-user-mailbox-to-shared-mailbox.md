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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Hier erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das mehrere Benutzer zugreifen können. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521029"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="6a87d-103">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="6a87d-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="6a87d-104">Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6a87d-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="6a87d-105">Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6a87d-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="6a87d-106">Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach wieder in ein Benutzerpostfach (privat) konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6a87d-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="6a87d-107">**Hier sind einige wirklich wichtige Dinge, die Sie kennen müssen:**</span><span class="sxs-lookup"><span data-stu-id="6a87d-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="6a87d-108">Das Benutzerpostfach, das Sie konvertieren möchten, benötigt eine Lizenz, die ihm zugewiesen ist, bevor Sie es in ein freigegebenes Postfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6a87d-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="6a87d-109">Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a87d-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="6a87d-110">Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="6a87d-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="6a87d-111">Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="6a87d-112">Freigegebene Postfächer können bis zu 50 GB Daten haben, ohne dass Ihnen eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6a87d-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="6a87d-113">Um mehr Daten zu speichern, benötigen Sie eine Lizenz, die ihr zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6a87d-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="6a87d-114">Möglicherweise müssen Sie eine Reihe großer e-Mails (sprich diejenigen mit Anlagen) aus dem freigegebenen Postfach löschen, um es zu verkleinern, damit Sie die Lizenz entfernen können.</span><span class="sxs-lookup"><span data-stu-id="6a87d-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="6a87d-p104">Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="6a87d-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="6a87d-118">Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6a87d-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="6a87d-119">Verwenden der Exchange-Verwaltungskonsole zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="6a87d-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="6a87d-120">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="6a87d-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="6a87d-121">Wählen Sie **Empfänger** \> **Postfächer**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="6a87d-122">Wählen Sie das Benutzerpostfach aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-122">Select the user mailbox.</span></span> <span data-ttu-id="6a87d-123">Wählen Sie unter **in freigegebenes Postfach konvertieren die**Option **konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="6a87d-124">Wenn das Postfach kleiner als 50 GB ist, können Sie die [Lizenz vom Benutzer](../manage/remove-licenses-from-users.md)entfernen und nicht mehr bezahlen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="6a87d-125">Löschen Sie das Konto des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="6a87d-125">Don't delete the user's account.</span></span> <span data-ttu-id="6a87d-126">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="6a87d-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="6a87d-127">Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="6a87d-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="6a87d-128">Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters von Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="6a87d-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="6a87d-129">Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6a87d-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="6a87d-130">Verwenden des Microsoft 365 Admin Center zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="6a87d-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6a87d-131">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6a87d-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6a87d-132">Wählen Sie den Namen des Benutzers aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6a87d-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="6a87d-133">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="6a87d-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6a87d-134">Es ist nicht erforderlich, das Kennwort des Benutzers während der Post Fach Konvertierung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="6a87d-135">Wenn das Kennwort jedoch nicht zurückgesetzt wird, **Funktionieren der ursprüngliche Benutzername und das Kennwort** nach Abschluss der Post Fach Konvertierung weiterhin.</span><span class="sxs-lookup"><span data-stu-id="6a87d-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="6a87d-136">Wählen Sie auf der Registerkarte **e-Mail** unter **Weitere Aktionen**die Option **in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6a87d-137">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6a87d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6a87d-138">Wählen Sie den Benutzer aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6a87d-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="6a87d-139">Erweitern Sie im rechten Bereich die Option **e-Mail-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6a87d-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="6a87d-140">Wählen Sie neben **Weitere Einstellungen** **die Option in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6a87d-141">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6a87d-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6a87d-142">Wählen Sie den Benutzer aus, dessen Postfach Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6a87d-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="6a87d-143">Erweitern Sie im rechten Bereich die Option **e-Mail-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6a87d-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="6a87d-144">Wählen Sie neben **Weitere Einstellungen** **die Option in freigegebenes Postfach konvertieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="6a87d-145">Wenn das Postfach kleiner als 50 GB ist, können Sie [die Lizenz vom Benutzer entfernen](../manage/remove-licenses-from-users.md)und nicht mehr bezahlen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="6a87d-146">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="6a87d-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="6a87d-147">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="6a87d-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="6a87d-148">Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="6a87d-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="6a87d-149">Siehe [Entfernen eines ehemaligen Mitarbeiters von Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="6a87d-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="6a87d-150">Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6a87d-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a87d-151">Freigegebene Postfächer erfordern keine separate Lizenz.</span><span class="sxs-lookup"><span data-stu-id="6a87d-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="6a87d-152">Wenn Sie jedoch das in-situ-Archiv aktivieren oder ein in-situ-Archiv oder ein Beweissicherungsverfahren für ein freigegebenes Postfach bereitstellen möchten, müssen Sie dem Postfach Exchange Online Archivierungs-oder Exchange Online Plan 2-Lizenz einen Exchange Online Plan 1 mit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="6a87d-153">Konvertieren des Postfachs eines gelöschten Benutzers</span><span class="sxs-lookup"><span data-stu-id="6a87d-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="6a87d-p112">Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="6a87d-p112">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="6a87d-156">[Stellen Sie das Konto des Benutzers wieder her](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="6a87d-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="6a87d-157">Stellen Sie sicher, dass eine Microsoft 365-Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6a87d-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="6a87d-158">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="6a87d-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="6a87d-159">Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6a87d-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="6a87d-160">Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6a87d-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="6a87d-161">Nachdem das erledigt ist, können Sie die Lizenz aus dem Postfach des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="6a87d-162">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="6a87d-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="6a87d-163">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="6a87d-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="6a87d-164">Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a87d-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="6a87d-165">Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="6a87d-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="6a87d-166">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="6a87d-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="6a87d-167">Wählen Sie **Empfänger** \> **freigegeben**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="6a87d-168">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-168">Select the shared mailbox.</span></span> <span data-ttu-id="6a87d-169">Wählen Sie unter **Convert to Regular Mailbox die**Option **Convert**aus.</span><span class="sxs-lookup"><span data-stu-id="6a87d-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="6a87d-170">Wechseln Sie zurück zum Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6a87d-170">Go back to the admin center.</span></span> <span data-ttu-id="6a87d-171">Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6a87d-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="6a87d-172">Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="6a87d-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="6a87d-p116">Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.</span><span class="sxs-lookup"><span data-stu-id="6a87d-p116">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="6a87d-175">Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="6a87d-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="6a87d-176">Wenn sich dieses freigegebene Postfach in einer Hybridumgebung befindet, wird **dringend empfohlen** , das Benutzerpostfach wieder in ein lokales Postfach zu migrieren, das Benutzerpostfach in ein freigegebenes Postfach zu konvertieren und das freigegebene Postfach dann wieder in die Cloud zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6a87d-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="6a87d-177">Hier ist der Grund: Wenn Sie das Postfach in der Cloud konvertieren, kann es konvertiert werden, doch lokal ist das Postfach das Benutzerpostfach, da die neue Realität nicht wieder lokal synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a87d-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="6a87d-178">Normalerweise handelt es sich nicht um ein Problem, aber es gibt einige Szenarien, in denen die lokalen Attribute (die denken, dass das Postfach das Benutzerpostfach ist) die neuen Cloud-Versionen dieser Attribute überschreiben können und daher das Postfach möglicherweise wieder zurückkonvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a87d-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="6a87d-179">Dies ist ein Problem, da Benutzerpostfächer Lizenzen erfordern **oder nach 30 Tagen weich gelöscht werden**!</span><span class="sxs-lookup"><span data-stu-id="6a87d-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="6a87d-180">Wir haben die meisten der Gründe behandelt, warum dies geschieht, aber es kann immer noch passieren, obwohl selten.</span><span class="sxs-lookup"><span data-stu-id="6a87d-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="6a87d-181">Am besten ist es, sicher zu sein und das Postfach zurück in die lokale Umgebung zu versetzen, es zu konvertieren und dann das freigegebene Postfach wieder in die Cloud zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6a87d-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="6a87d-182">Diese empfohlene Lösung verstößt nicht gegen den Lizenzvertrag für Hybrid Umgebungen, da das vorhanden sein des Benutzerpostfachs lokal nur temporär ist.</span><span class="sxs-lookup"><span data-stu-id="6a87d-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="6a87d-183">Sie verletzen Ihre Lizenz, wenn Sie das Benutzerpostfach oder das freigegebene Postfach in Ihrer lokalen Organisation verwaltet haben und es nicht wieder in die Cloud zurückversetzen.</span><span class="sxs-lookup"><span data-stu-id="6a87d-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="6a87d-184">Wenn Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Empfängerverwaltung" sind, können Sie die Exchange-Verwaltungsshell verwenden, um ein Benutzerpostfach in ein freigegebenes Postfach lokal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6a87d-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="6a87d-185">Beispiel: `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="6a87d-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="6a87d-186">Sehen Sie sich die Problemumgehung in dieser Support Lösung für Instanzen an [, wenn freigegebene Postfächer unerwarteterweise in Benutzerpostfächer konvertiert werden](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="6a87d-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6a87d-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6a87d-187">Related articles</span></span>

[<span data-ttu-id="6a87d-188">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="6a87d-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6a87d-189">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="6a87d-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="6a87d-190">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="6a87d-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6a87d-191">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="6a87d-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="6a87d-192">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="6a87d-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
