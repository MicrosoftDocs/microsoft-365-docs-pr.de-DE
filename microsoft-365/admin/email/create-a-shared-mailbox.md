---
title: Erstellen eines freigegebenen Postfachs
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Erstellen Sie ein freigegebenes Postfach, damit mehrere Benutzer in Ihrem Unternehmen die Verantwortung für das Lesen und Beantworten von E-Mails teilen, die an eine Adresse gesendet wurden.
ms.openlocfilehash: 270894da77d9ddf2b35187d8409cd2fd878b0e6d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253044"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="1ec03-103">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="1ec03-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="1ec03-104">Wenn Ihre Organisation eine Exchange-Hybridumgebung verwendet, sollten Sie das lokale Exchange Admin Center (EAC) zum Erstellen und Verwalten von freigegebenen Postfächern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec03-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="1ec03-105">Siehe [Erstellen freigegebener Postfächer im Exchange Admin Center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="1ec03-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="1ec03-106">Wenn Sie nicht sicher sind, ob Sie ein freigegebenes Postfach oder eine Office 365-Gruppe für Outlook erstellen sollten, finden Sie Informationen dazu unter [Vergleichen von Gruppen](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1ec03-106">If you're not sure if you should create a shared mailbox or an Office 365 Group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="1ec03-107">Bitte beachten Sie, dass es aktuell nicht möglich ist, ein freigegebenes Postfach zu einer Office 365-Gruppe zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="1ec03-107">Note that currently, it's not possible to migrate a shared mailbox to an Office 365 Group.</span></span> <span data-ttu-id="1ec03-108">Wenn Sie diese Funktion wünschen, teilen Sie uns dies mittels [Hier abstimmen](https://go.microsoft.com/fwlink/?linkid=871518) mit.</span><span class="sxs-lookup"><span data-stu-id="1ec03-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="1ec03-p103">Freigegebene Postfächer lassen sich auf einfache Weise erstellen, damit eine Gruppe von Personen E-Mails einer gemeinsamen E-Mail-Adresse wie "info@contoso.com" überwachen und senden kann. Wenn eine Person in der Gruppe auf eine Nachricht antwortet, die an das freigegebene Postfach gesendet wurde, wird als Absender der E-Mail das freigegebene Postfach angegeben, nicht der einzelne Benutzer. </span><span class="sxs-lookup"><span data-stu-id="1ec03-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="1ec03-111">Freigegebene Postfächer enthalten einen freigegebenen Kalender.</span><span class="sxs-lookup"><span data-stu-id="1ec03-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="1ec03-112">Viele kleine Unternehmen nutzen den freigegebenen Kalender gerne als zentralen Ort, an dem jeder Mitarbeiter seine Termine eintragen kann.</span><span class="sxs-lookup"><span data-stu-id="1ec03-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="1ec03-113">So können beispielsweise alle drei Personen, die Kundenbesuche durchführen, den freigegebenen Kalender anzeigen und darin ihre Termine eintragen. </span><span class="sxs-lookup"><span data-stu-id="1ec03-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="1ec03-114">Dies ist eine einfache Möglichkeit, um jeden über den jeweiligen Aufenthaltsort auf dem Laufenden zu halten.</span><span class="sxs-lookup"><span data-stu-id="1ec03-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="1ec03-115">Lesen Sie vor dem Erstellen eines freigegebenen Postfachs unbedingt [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="1ec03-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="1ec03-116">Erstellen eines freigegebenen Postfachs und Hinzufügen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="1ec03-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="1ec03-117">Melden Sie sich mit einem Office 365-Administratorkonto als globaler Administrator oder mit einem Exchange-Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="1ec03-117">Sign in with an Office 365 global admin account or Exchange admin account.</span></span> <span data-ttu-id="1ec03-118">Wenn die Meldung „**Sie haben keine Berechtigung für den Zugriff auf diese Seite oder die Ausführung dieser Aktion**“ angezeigt wird, sind Sie kein Administrator.</span><span class="sxs-lookup"><span data-stu-id="1ec03-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="1ec03-119">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="1ec03-120">Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041) zur Seite **Gruppen** \> **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="1ec03-121">Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627) zur Seite **Gruppen** \> **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="1ec03-122">Wählen Sie auf der Seite **Freigegebene Postfächer\*\*\*\*+ Postfach hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="1ec03-123">Geben Sie einen Namen für das freigegebene Postfach ein.</span><span class="sxs-lookup"><span data-stu-id="1ec03-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="1ec03-124">Der Assistent wählt dann die E-Mail-Adresse aus, die Sie aber bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1ec03-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Geben Sie Ihrem freigegebenen Postfach einen Namen.](../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="1ec03-126">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-126">Select **Add**.</span></span> <span data-ttu-id="1ec03-127">Es kann ein paar Minuten dauern, bevor Sie Mitglieder hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1ec03-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="1ec03-128">Wählen Sie unter **Nächste Schritte** die Option **Mitglieder zu diesem Postfach hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="1ec03-129">Mitglieder sind die Personen, denen ermöglich wird, die eingehenden E-Mails für dieses freigegebene Postfach und die ausgehenden Antworten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Wählen Sie „Mitglieder hinzufügen“ aus](../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="1ec03-131">Wählen Sie die Schaltfläche **+ Mitglieder hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-131">Select the **+Add members** button.</span></span> <span data-ttu-id="1ec03-132">Setzen Sie ein Häkchen neben diejenigen Personen, die dieses freigegebene Postfach nutzen sollen, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Weisen Sie dem freigegebenen Postfach Mitglieder zu](../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="1ec03-134">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-134">Select **Close**.</span></span>

<span data-ttu-id="1ec03-135">Sie haben ein freigegebenes Postfach, das einen freigegebenen Kalender enthält.</span><span class="sxs-lookup"><span data-stu-id="1ec03-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="1ec03-136">Fahren Sie jetzt mit dem nächsten Schritt fort: Blockieren der Anmeldung für das freigegebene Postfachkonto.</span><span class="sxs-lookup"><span data-stu-id="1ec03-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="1ec03-137">Blockieren der Anmeldung für das freigegebene Postfachkonto</span><span class="sxs-lookup"><span data-stu-id="1ec03-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="1ec03-138">Zu jedem freigegebenen Postfach gehört ein entsprechendes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="1ec03-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="1ec03-139">Haben Sie festgestellt, dass Sie beim Erstellen des freigegebenen Postfachs nicht zur Eingabe eines Kennworts aufgefordert wurden?</span><span class="sxs-lookup"><span data-stu-id="1ec03-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="1ec03-140">Das Konto verfügt über ein Kennwort, das jedoch vom System generiert wurde (unbekannt).</span><span class="sxs-lookup"><span data-stu-id="1ec03-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="1ec03-141">Sie sollten sich nicht mit dem Konto beim freigegebenen Postfach anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ec03-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="1ec03-142">Doch was passiert, wenn ein Administrator einfach das Kennwort für das freigegebene Postfachbenutzerkonto zurücksetzt?</span><span class="sxs-lookup"><span data-stu-id="1ec03-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="1ec03-143">Oder was passiert, wenn ein Angreifer Zugriff auf die Anmeldeinformationen des freigegebenen Postfachkontos erhält?</span><span class="sxs-lookup"><span data-stu-id="1ec03-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="1ec03-144">Dies würde dem Benutzerkonto ermöglichen, sich beim freigegebenen Postfach anzumelden und eine E-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="1ec03-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="1ec03-145">Um dies zu verhindern, müssen Sie die Anmeldung für das Konto blockieren, das dem freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ec03-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1ec03-146">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-146">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="1ec03-147">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="1ec03-148">Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise den Filter in **Nicht lizenzierte Benutzer**).</span><span class="sxs-lookup"><span data-stu-id="1ec03-148">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="1ec03-149">Wählen Sie den Benutzer aus, dessen Eigenschaftenbereich Sie öffnen möchten, und wählen Sie dann das Symbol **Diesen Benutzer blockieren** ![Screenshot des Symbols „Diesen Benutzer blockieren](../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="1ec03-149">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../media/block-user-icon.png).</span></span>

   <span data-ttu-id="1ec03-150">**Hinweis**: Wenn das Konto bereits blockiert ist, wird am oberen Rand **Anmeldung blockiert** angezeigt und das Symbol zeigt **Entsperren des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-150">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="1ec03-151">Wählen Sie im Bereich **Diesen Benutzer blockieren?** **Benutzer für die Anmeldung blockieren** aus und wählen Sie dann **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="1ec03-151">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1ec03-152">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="1ec03-153">Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise die Ansicht zu **Nicht lizenzierte Benutzer**) und wählen Sie dann das Konto aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-153">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="1ec03-154">Wählen Sie im Eigenschaften-Flyout **Anmeldung blockieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-154">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="1ec03-155">**Hinweis:** Wenn das Konto bereits blockiert wurde, zeigt die Schaltfläche **Anmeldung freigeben** an.</span><span class="sxs-lookup"><span data-stu-id="1ec03-155">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="1ec03-156">Vergewissern Sie sich, dass im Flyout-Menü **Anmeldestatus bearbeiten** die Option „Benutzer für die Anmeldung sperren“ aktiviert ist, wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-156">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1ec03-157">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="1ec03-158">Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise die Ansicht zu **Nicht lizenzierte Benutzer**) und wählen Sie dann das Konto aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-158">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="1ec03-159">Wählen Sie im Eigenschaften-Flyout **Anmeldung blockieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-159">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="1ec03-160">**Hinweis:** Wenn das Konto bereits blockiert wurde, zeigt die Schaltfläche **Anmeldung freigeben** an.</span><span class="sxs-lookup"><span data-stu-id="1ec03-160">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="1ec03-161">Vergewissern Sie sich, dass im Flyout-Menü **Anmeldestatus bearbeiten** die Option „Benutzer für die Anmeldung sperren“ aktiviert ist, wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-161">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="1ec03-162">Anweisungen dazu, wie Sie die-Anmeldung für-Konten mit Azure AD PowerShell (einschließlich vieler Konten gleichzeitig) blockieren können, finden Sie unter [Blockieren von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ec03-162">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="1ec03-163">Hinzufügen des freigegebenen Postfachs in Outlook</span><span class="sxs-lookup"><span data-stu-id="1ec03-163">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="1ec03-164">Wenn Sie in Ihrem Unternehmen die automatische Zuordnung aktiviert haben (wie es die meisten Benutzer standardmäßig tun), wird das freigegebene Postfach in der Outlook-App ihrer Benutzer automatisch angezeigt, nachdem sie Outlook geschlossen und erneut gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="1ec03-164">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="1ec03-165">Die automatische Zuordnung wird für das Postfach des Benutzers und nicht für das freigegebene Postfach festgelegt.  </span><span class="sxs-lookup"><span data-stu-id="1ec03-165">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="1ec03-166">Dies bedeutet: Wenn Sie über eine Sicherheitsgruppe zu verwalten versuchen, wer auf das freigegebene Postfach zugreifen darf, funktioniert die automatische Zuordnung nicht.</span><span class="sxs-lookup"><span data-stu-id="1ec03-166">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="1ec03-167">Deshalb müssen Sie zur Nutzung der automatischen Zuordnung Berechtigungen explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-167">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="1ec03-168">Die automatische Zuordnung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ec03-168">Automapping is on by default.</span></span> <span data-ttu-id="1ec03-169">Informationen zum Deaktivieren dieser Option finden Sie unter [Entfernen der automatischen Zuordnung für ein freigegebenes Postfach](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="1ec03-169">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="1ec03-170">Weitere Informationen zu in Outlook freigegebenen Postfächern finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="1ec03-170">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="1ec03-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Öffnen und Verwenden eines geteilten Postfachs in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="1ec03-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="1ec03-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a></span><span class="sxs-lookup"><span data-stu-id="1ec03-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="1ec03-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines geteilten Postfachs zu Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="1ec03-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="1ec03-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Öffnen eines freigegebenen Ordners oder Postfachs in Outlook für Mac</a></span><span class="sxs-lookup"><span data-stu-id="1ec03-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="1ec03-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Hinzufügen von Regeln zu einem freigegebenen Postfach</a></span><span class="sxs-lookup"><span data-stu-id="1ec03-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="1ec03-176">Verwenden eines geteilten Postfachs auf einem mobilen Gerät (Smartphone oder Tablet)</span><span class="sxs-lookup"><span data-stu-id="1ec03-176">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="1ec03-177">Sie können auf ein geteiltes Postfach auf einem mobilen Gerät auf zweierlei Arten zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="1ec03-177">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="1ec03-178">Fügen Sie das freigegebene Postfach in der <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook für iOS-App</a> oder der <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android Mobile-App</a> hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ec03-178">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="1ec03-179">Die entsprechenden Anleitungen finden Sie unter <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-179">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="1ec03-180">Öffnen Sie Ihren Browser, melden Sie sich bei Office 365 an und wechseln Sie dann zu Outlook im Web.</span><span class="sxs-lookup"><span data-stu-id="1ec03-180">Open your browser, sign in to Office 365, and then go to Outlook on the web.</span></span> <span data-ttu-id="1ec03-181">Von Outlook im Web aus können Sie auf das freigegebene Postfach zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-181">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="1ec03-182">Die entsprechenden Anleitungen finden Sie unter <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a>.</span><span class="sxs-lookup"><span data-stu-id="1ec03-182">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="1ec03-183">Verwenden des geteilten Kalenders</span><span class="sxs-lookup"><span data-stu-id="1ec03-183">Use the shared calendar</span></span>

<span data-ttu-id="1ec03-184">Beim Erstellen des freigegebenen Postfachs haben Sie automatisch einen freigegebenen Kalender erstellt.</span><span class="sxs-lookup"><span data-stu-id="1ec03-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="1ec03-185">Wir verwenden bevorzugt den freigegebenen Kalender des Postfachs statt eines SharePoint-Kalenders zum Nachverfolgen von Terminen und des Aufenthaltsorts von Personen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="1ec03-186">Ein freigegebener Kalender ist in Outlook integriert und ist viel einfacher zu verwenden als ein SharePoint-Kalender.</span><span class="sxs-lookup"><span data-stu-id="1ec03-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="1ec03-187">Wechseln Sie in der Outlook-App zur Kalenderansicht und wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="1ec03-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="1ec03-188">Wenn Sie Termine eingeben, kann diese jeder ansehen, der Mitglied des geteilten Postfachs ist.</span><span class="sxs-lookup"><span data-stu-id="1ec03-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="1ec03-189">Jedes Mitglied des geteilten Postfachs kann Termine im Kalender erstellen, sehen und verwalten, genau wie in seinem persönlichen Kalender.</span><span class="sxs-lookup"><span data-stu-id="1ec03-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="1ec03-190">Jedes Mitglied des geteilten Postfachs kann Änderungen im freigegebenen Kalender sehen.</span><span class="sxs-lookup"><span data-stu-id="1ec03-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1ec03-191">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1ec03-191">Related articles</span></span>

[<span data-ttu-id="1ec03-192">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1ec03-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1ec03-193">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="1ec03-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="1ec03-194">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="1ec03-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="1ec03-195">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="1ec03-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="1ec03-196">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1ec03-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





