---
title: Erstellen eines freigegebenen Postfachs
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Erstellen Sie ein freigegebenes Postfach, damit mehrere Benutzer in Ihrem Unternehmen die Verantwortung für das Lesen und Beantworten von E-Mails teilen, die an eine Adresse gesendet wurden.
ms.openlocfilehash: 6fff7b1eaa73944bc4dd744046ad97ee9d2379b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393187"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="6b7be-103">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="6b7be-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="6b7be-104">Wenn Ihre Organisation eine Exchange-Hybridumgebung verwendet, sollten Sie das lokale Exchange Admin Center (EAC) zum Erstellen und Verwalten von freigegebenen Postfächern verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="6b7be-105">Siehe [Erstellen freigegebener Postfächer im Exchange Admin Center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="6b7be-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="6b7be-106">Wenn Sie nicht sicher sind, ob Sie ein freigegebenes Postfach oder eine Microsoft 365-Gruppe für Outlook erstellen sollten, finden Sie Informationen dazu unter [Vergleichen von Gruppen](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6b7be-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="6b7be-107">Beachten Sie, dass es aktuell nicht möglich ist, ein freigegebenes Postfach zu einer Microsoft 365-Gruppe zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6b7be-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="6b7be-108">Wenn Sie diese Funktion wünschen, teilen Sie uns dies mittels [Hier abstimmen](https://go.microsoft.com/fwlink/?linkid=871518) mit.</span><span class="sxs-lookup"><span data-stu-id="6b7be-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="6b7be-p103">Freigegebene Postfächer lassen sich auf einfache Weise erstellen, damit eine Gruppe von Personen E-Mails einer gemeinsamen E-Mail-Adresse wie "info@contoso.com" überwachen und senden kann. Wenn eine Person in der Gruppe auf eine Nachricht antwortet, die an das freigegebene Postfach gesendet wurde, wird als Absender der E-Mail das freigegebene Postfach angegeben, nicht der einzelne Benutzer. </span><span class="sxs-lookup"><span data-stu-id="6b7be-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="6b7be-p104">Freigegebene Postfächer enthalten einen freigegebenen Kalender! Viele kleine Unternehmen nutzen den freigegebenen Kalender gerne als zentralen Ort, an dem jeder Mitarbeiter seine Termine eintragen kann. So können beispielsweise alle drei Personen, die Kundenbesuche durchführen, den freigegebenen Kalender nutzen und darin ihre Termine eintragen. Dies ist eine einfache Möglichkeit, um jeden über den jeweiligen Aufenthaltsort auf dem Laufenden zu halten.</span><span class="sxs-lookup"><span data-stu-id="6b7be-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="6b7be-115">Lesen Sie vor dem Erstellen eines freigegebenen Postfachs unbedingt [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="6b7be-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="6b7be-116">Erstellen eines freigegebenen Postfachs und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="6b7be-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="6b7be-117">Melden Sie sich mit einem globalen Administrator oder mit einem Exchange-Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="6b7be-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="6b7be-118">Wenn die Meldung „**Sie haben keine Berechtigung für den Zugriff auf diese Seite oder die Ausführung dieser Aktion**“ angezeigt wird, sind Sie kein Administrator.</span><span class="sxs-lookup"><span data-stu-id="6b7be-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="6b7be-119">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="6b7be-120">Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041) zur Seite **Gruppen** \> **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="6b7be-121">Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627) zur Seite **Gruppen** \> **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="6b7be-122">Wählen Sie auf der Seite **Freigegebene Postfächer\*\*\*\*+ Postfach hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="6b7be-123">Geben Sie einen Namen für das freigegebene Postfach ein.</span><span class="sxs-lookup"><span data-stu-id="6b7be-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="6b7be-124">Der Assistent wählt dann die E-Mail-Adresse aus, die Sie aber bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="6b7be-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Geben Sie Ihrem freigegebenen Postfach einen Namen.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="6b7be-126">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-126">Select **Add**.</span></span> <span data-ttu-id="6b7be-127">Es kann ein paar Minuten dauern, bevor Sie Mitglieder hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="6b7be-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="6b7be-128">Wählen Sie unter **Nächste Schritte** die Option **Mitglieder zu diesem Postfach hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="6b7be-129">Mitglieder sind die Personen, denen ermöglich wird, die eingehenden E-Mails für dieses freigegebene Postfach und die ausgehenden Antworten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6b7be-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Wählen Sie „Mitglieder hinzufügen“ aus](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="6b7be-131">Wählen Sie die Schaltfläche **+ Mitglieder hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-131">Select the **+Add members** button.</span></span> <span data-ttu-id="6b7be-132">Setzen Sie ein Häkchen neben diejenigen Personen, die dieses freigegebene Postfach nutzen sollen, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Weisen Sie dem freigegebenen Postfach Mitglieder zu](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="6b7be-134">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-134">Select **Close**.</span></span>

<span data-ttu-id="6b7be-135">Sie haben ein freigegebenes Postfach, das einen freigegebenen Kalender enthält.</span><span class="sxs-lookup"><span data-stu-id="6b7be-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="6b7be-136">Fahren Sie jetzt mit dem nächsten Schritt fort: Blockieren der Anmeldung für das freigegebene Postfachkonto.</span><span class="sxs-lookup"><span data-stu-id="6b7be-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="6b7be-137">Welche Berechtigungen sollten Sie verwenden?</span><span class="sxs-lookup"><span data-stu-id="6b7be-137">Which permissions should you use?</span></span>

<span data-ttu-id="6b7be-138">Sie können die folgenden Berechtigungen mit einem freigegebenen Postfach verwenden:</span><span class="sxs-lookup"><span data-stu-id="6b7be-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="6b7be-139">**Vollzugriff**: Die Berechtigung „Vollzugriff“ ermöglicht es einem Benutzer, das freigegebene Postfach zu öffnen und als Besitzer dieses Postfachs zu agieren.</span><span class="sxs-lookup"><span data-stu-id="6b7be-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="6b7be-140">Nach dem Zugriff auf das freigegebene Postfach kann ein Benutzer Kalenderelemente erstellen, E-Mails lesen, anzeigen, löschen und ändern sowie Tasks und Kalenderkontakte erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b7be-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="6b7be-141">Ein Benutzer mit der Berechtigung "Vollzugriff" kann jedoch keine E-Mails über das freigegebene Postfach senden, außer er hat auch die Berechtigung "Senden als" oder "Senden im Auftrag von".</span><span class="sxs-lookup"><span data-stu-id="6b7be-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="6b7be-142">**Senden als**: Die Berechtigung „Senden als“ ermöglicht es einem Benutzer, die Identität des freigegebenen Postfachs beim Senden einer E-Mail zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6b7be-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="6b7be-143">Wenn Katerina sich beispielsweise beim freigegebenen Postfach „Marketingabteilung“ anmeldet und eine E-Mail sendet, sieht es so aus, als wäre die Nachricht von der Marketingabteilung gesendet worden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="6b7be-144">**Senden im Auftrag von**: Die Berechtigung „Senden im Auftrag von“ ermöglicht es einem Benutzer, E-Mails im Namen des freigegebenen Postfachs zu senden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="6b7be-145">Beispiel: John meldet sich beim freigegebenen Postfach des Empfangs in Gebäude 32 an und sendet eine E-Mail. Dem Empfänger wird angezeigt, dass John sie im Auftrag des Empfangs in Gebäude 32 gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="6b7be-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="6b7be-146">Sie können „Senden im Auftrag von“-Berechtigungen nicht über das EAC erteilen, sondern müssen das Cmdlet **Set-Mailbox** mit dem Parameter _GrantSendonBehalf_ verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="6b7be-147">Verwenden des EAC zum Bearbeiten der Stellvertretung für das freigegebene Postfach</span><span class="sxs-lookup"><span data-stu-id="6b7be-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="6b7be-148">Navigieren Sie in der EAC zu **Empfänger** \> **Freigegeben**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="6b7be-149">Wählen Sie das gewünschte freigegebene Postfach und dann **Bearbeiten** ![Bearbeiten-Symbol](../../media/ITPro-EAC-EditIcon.png) aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="6b7be-150">Wählen Sie **Postfachstellvertretung**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="6b7be-151">Wählen Sie zum Erteilen oder Entziehen von Vollzugriff oder „Senden als“-Berechtigungen die Option **Hinzufügen**![Hinzufügen-Symbol](../../media/ITPro-EAC-AddIcon.png) oder **Entfernen**![Entfernen-Symbol](../../media/ITPro-EAC-RemoveIcon.gif) und dann die Benutzer aus, für die Sie die Berechtigungen erteilen bzw. entziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="6b7be-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6b7be-p115">Die Vollzugriff-Berechtigung ermöglicht es einem Benutzer, das Postfach zu öffnen und Elemente darin zu erstellen oder zu ändern. Die "Senden als"-Berechtigung ermöglicht es Benutzern, bei denen es sich nicht um den Postfachbesitzer handelt, E-Mails von dem freigegebenen Postfach zu senden. Beide Berechtigungen sind für erfolgreiche freigegebene Postfächer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b7be-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="6b7be-155">Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6b7be-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="6b7be-156">Blockieren der Anmeldung für das freigegebene Postfachkonto</span><span class="sxs-lookup"><span data-stu-id="6b7be-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="6b7be-157">Zu jedem freigegebenen Postfach gehört ein entsprechendes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="6b7be-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="6b7be-158">Haben Sie festgestellt, dass Sie beim Erstellen des freigegebenen Postfachs nicht zur Eingabe eines Kennworts aufgefordert wurden?</span><span class="sxs-lookup"><span data-stu-id="6b7be-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="6b7be-159">Das Konto verfügt über ein Kennwort, das jedoch vom System generiert wurde (unbekannt).</span><span class="sxs-lookup"><span data-stu-id="6b7be-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="6b7be-160">Sie sollten sich nicht mit dem Konto beim freigegebenen Postfach anmelden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="6b7be-161">Doch was passiert, wenn ein Administrator einfach das Kennwort für das freigegebene Postfachbenutzerkonto zurücksetzt?</span><span class="sxs-lookup"><span data-stu-id="6b7be-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="6b7be-162">Oder was passiert, wenn ein Angreifer Zugriff auf die Anmeldeinformationen des freigegebenen Postfachkontos erhält?</span><span class="sxs-lookup"><span data-stu-id="6b7be-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="6b7be-163">Dies würde dem Benutzerkonto ermöglichen, sich beim freigegebenen Postfach anzumelden und eine E-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="6b7be-164">Um dies zu verhindern, müssen Sie die Anmeldung für das Konto blockieren, das dem freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6b7be-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6b7be-165">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6b7be-166">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6b7be-167">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

1. <span data-ttu-id="6b7be-168">Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise den Filter in **Nicht lizenzierte Benutzer**).</span><span class="sxs-lookup"><span data-stu-id="6b7be-168">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

1. <span data-ttu-id="6b7be-169">Wählen Sie den Benutzer aus, dessen Eigenschaftenbereich Sie öffnen möchten, und wählen Sie dann das Symbol **Diesen Benutzer blockieren** ![Screenshot des Symbols „Diesen Benutzer blockieren](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="6b7be-169">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="6b7be-170">**Hinweis**: Wenn das Konto bereits blockiert ist, wird am oberen Rand **Anmeldung blockiert** angezeigt und das Symbol zeigt **Entsperren des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-170">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

1. <span data-ttu-id="6b7be-171">Wählen Sie im Bereich **Diesen Benutzer blockieren?** **Benutzer für die Anmeldung blockieren** aus und wählen Sie dann **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="6b7be-171">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

<span data-ttu-id="6b7be-172">Anweisungen dazu, wie Sie die-Anmeldung für-Konten mit Azure AD PowerShell (einschließlich vieler Konten gleichzeitig) blockieren können, finden Sie unter [Blockieren von Benutzerkonten mit Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b7be-172">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="6b7be-173">Hinzufügen des freigegebenen Postfachs in Outlook</span><span class="sxs-lookup"><span data-stu-id="6b7be-173">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="6b7be-174">Wenn Sie in Ihrem Unternehmen die automatische Zuordnung aktiviert haben (wie es die meisten Benutzer standardmäßig tun), wird das freigegebene Postfach in der Outlook-App ihrer Benutzer automatisch angezeigt, nachdem sie Outlook geschlossen und erneut gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="6b7be-174">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="6b7be-175">Die automatische Zuordnung wird für das Postfach des Benutzers und nicht für das freigegebene Postfach festgelegt.  </span><span class="sxs-lookup"><span data-stu-id="6b7be-175">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="6b7be-176">Dies bedeutet: Wenn Sie über eine Sicherheitsgruppe zu verwalten versuchen, wer auf das freigegebene Postfach zugreifen darf, funktioniert die automatische Zuordnung nicht.</span><span class="sxs-lookup"><span data-stu-id="6b7be-176">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="6b7be-177">Deshalb müssen Sie zur Nutzung der automatischen Zuordnung Berechtigungen explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6b7be-177">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="6b7be-178">Die automatische Zuordnung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b7be-178">Automapping is on by default.</span></span> <span data-ttu-id="6b7be-179">Informationen zum Deaktivieren dieser Option finden Sie unter [Entfernen der automatischen Zuordnung für ein freigegebenes Postfach](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6b7be-179">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6b7be-180">Weitere Informationen zu in Outlook freigegebenen Postfächern finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="6b7be-180">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="6b7be-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Öffnen und Verwenden eines geteilten Postfachs in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="6b7be-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="6b7be-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a></span><span class="sxs-lookup"><span data-stu-id="6b7be-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="6b7be-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines geteilten Postfachs zu Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="6b7be-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="6b7be-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Öffnen eines freigegebenen Ordners oder Postfachs in Outlook für Mac</a></span><span class="sxs-lookup"><span data-stu-id="6b7be-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="6b7be-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Hinzufügen von Regeln zu einem freigegebenen Postfach</a></span><span class="sxs-lookup"><span data-stu-id="6b7be-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="6b7be-186">Verwenden eines geteilten Postfachs auf einem mobilen Gerät (Smartphone oder Tablet)</span><span class="sxs-lookup"><span data-stu-id="6b7be-186">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="6b7be-187">Sie können auf ein geteiltes Postfach auf einem mobilen Gerät auf zweierlei Arten zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="6b7be-187">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="6b7be-188">Fügen Sie das freigegebene Postfach in der <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook für iOS-App</a> oder der <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android Mobile-App</a> hinzu.</span><span class="sxs-lookup"><span data-stu-id="6b7be-188">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="6b7be-189">Die entsprechenden Anleitungen finden Sie unter <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-189">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="6b7be-190">Öffnen Sie Ihren Browser, melden Sie sich an und wechseln Sie dann zu Outlook im Web.</span><span class="sxs-lookup"><span data-stu-id="6b7be-190">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="6b7be-191">Von Outlook im Web aus können Sie auf das freigegebene Postfach zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6b7be-191">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="6b7be-192">Die entsprechenden Anleitungen finden Sie unter <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a>.</span><span class="sxs-lookup"><span data-stu-id="6b7be-192">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6b7be-193">Das freigegebene Postfach kann nur zur Outlook für iOS-App oder zur mobilen Outlook für Android-App hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6b7be-193">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="6b7be-194">Verwenden des geteilten Kalenders</span><span class="sxs-lookup"><span data-stu-id="6b7be-194">Use the shared calendar</span></span>

<span data-ttu-id="6b7be-p120">Beim Erstellen des freigegebenen Postfachs haben Sie automatisch auch einen freigegebenen Kalender erstellt. Wir verwenden bevorzugt den freigegebenen Kalender des Postfachs statt eines SharePoint-Kalenders zum Nachverfolgen von Terminen und des Aufenthaltsorts von Personen. Ein freigegebener Kalender ist in Outlook integriert und ist viel einfacher zu verwenden als ein SharePoint-Kalender.</span><span class="sxs-lookup"><span data-stu-id="6b7be-p120">When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="6b7be-198">Wechseln Sie in der Outlook-App zur Kalenderansicht und wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="6b7be-198">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="6b7be-199">Wenn Sie Termine eingeben, kann diese jeder ansehen, der Mitglied des geteilten Postfachs ist.</span><span class="sxs-lookup"><span data-stu-id="6b7be-199">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="6b7be-200">Jedes Mitglied des geteilten Postfachs kann Termine im Kalender erstellen, sehen und verwalten, genau wie in seinem persönlichen Kalender.</span><span class="sxs-lookup"><span data-stu-id="6b7be-200">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="6b7be-201">Jedes Mitglied des geteilten Postfachs kann Änderungen im freigegebenen Kalender sehen.</span><span class="sxs-lookup"><span data-stu-id="6b7be-201">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="6b7be-202">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6b7be-202">Related content</span></span>

<span data-ttu-id="6b7be-203">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b7be-203">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="6b7be-204">[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b7be-204">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6b7be-205">[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b7be-205">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6b7be-206">[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b7be-206">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6b7be-207">[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b7be-207">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>