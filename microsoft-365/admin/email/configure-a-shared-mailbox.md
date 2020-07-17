---
title: Konfigurieren von Einstellungen für freigegebene Postfächer
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
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten. Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen oder die Mitglieder.
ms.openlocfilehash: 3bde856f4db80192f5ed058a18c7942aa6a724b2
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739199"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="1cef4-104">Konfigurieren von Einstellungen für freigegebene Postfächer</span><span class="sxs-lookup"><span data-stu-id="1cef4-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="1cef4-105">Nachdem Sie [ein freigegebenes Postfach erstellt](create-a-shared-mailbox.md)haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten.</span><span class="sxs-lookup"><span data-stu-id="1cef4-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="1cef4-106">Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1cef4-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="1cef4-107">Ändern des Namens oder des e-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären e-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="1cef4-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-108">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-109">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-110">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-111">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** neben **Name, e-Mail, e-Mail-Aliase**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="1cef4-112">Geben Sie einen neuen Namen ein, oder fügen Sie einen weiteren Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cef4-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="1cef4-113">Wenn Sie die primäre e-Mail-Adresse ändern möchten, muss Ihr Postfach über mehr als einen e-Mail-Alias verfügen.</span><span class="sxs-lookup"><span data-stu-id="1cef4-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="1cef4-114">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="1cef4-115">Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden</span><span class="sxs-lookup"><span data-stu-id="1cef4-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="1cef4-116">Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um an Sie gesendete e-Mails weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1cef4-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="1cef4-117">Sie können die Nachrichten an eine beliebige gültige e-Mail-Adresse oder Verteilerliste weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="1cef4-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-118">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-119">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-120">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-121">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail Weiterleitung** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="1cef4-122">Legen Sie die Umschaltfläche **auf**ein und geben Sie eine e-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1cef4-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="1cef4-123">Es kann sich um eine beliebige gültige e-Mail-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="1cef4-123">It can be any valid email address.</span></span> <span data-ttu-id="1cef4-124">Um an mehrere Adressen weiterzuleiten, müssen Sie [eine Verteilergruppe](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.</span><span class="sxs-lookup"><span data-stu-id="1cef4-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="1cef4-125">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="1cef4-126">Senden von automatischen Antworten aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="1cef4-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-127">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-128">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-129">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-130">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **automatische Antworten** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="1cef4-131">Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1cef4-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="1cef4-132">Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten.</span><span class="sxs-lookup"><span data-stu-id="1cef4-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="1cef4-133">Sie können nur Text (keine Bilder) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1cef4-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="1cef4-134">Wenn Sie *auch* eine Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, die Antwort erhalten soll, und geben Sie den Text ein.</span><span class="sxs-lookup"><span data-stu-id="1cef4-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="1cef4-135">Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.</span><span class="sxs-lookup"><span data-stu-id="1cef4-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="1cef4-136">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="1cef4-137">Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="1cef4-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="1cef4-p108">Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="1cef4-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="1cef4-140">Wenn Sie zulassen möchten, dass alle Benutzer die gesendeten e-Mails anzeigen können, bearbeiten Sie im Admin Center die Einstellungen für freigegebene Postfächer, und wählen Sie **Gesendete Elemente** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="1cef4-141">Auswählen der apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft e-Mail verwenden kann</span><span class="sxs-lookup"><span data-stu-id="1cef4-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-142">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-143">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-144">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-145">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail apps** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="1cef4-146">Legen Sie die Umschaltfläche für alle apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden können, auf **ein** fest.</span><span class="sxs-lookup"><span data-stu-id="1cef4-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="1cef4-147">Legen Sie die Umschaltfläche für alle apps, die Sie nicht verwenden möchten, auf **Off** fest.</span><span class="sxs-lookup"><span data-stu-id="1cef4-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="1cef4-148">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="1cef4-149">Speichern eines freigegebenen Postfachs für das Beweissicherungsverfahren</span><span class="sxs-lookup"><span data-stu-id="1cef4-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="1cef4-150">Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="1cef4-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-151">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-152">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-153">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-154">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Bearbeitungs **Prozess halten** aus \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="1cef4-155">Legen Sie die Umschaltfläche **auf ein**fest.</span><span class="sxs-lookup"><span data-stu-id="1cef4-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="1cef4-156">Geben Sie optional eine Dauer, eine Notiz zum Haltestatus und eine URL mit weiteren Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="1cef4-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="1cef4-157">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="1cef4-158">Hinzufügen oder Entfernen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="1cef4-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-159">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-160">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-161">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-162">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und klicken Sie dann auf **Mitglieder** \> **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="1cef4-163">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1cef4-163">Do one of the following:</span></span>
   - <span data-ttu-id="1cef4-164">Klicken Sie zum Hinzufügen von Mitgliedern auf **Mitglieder hinzufügen**, suchen Sie nach einem Mitglied, das hinzugefügt werden soll, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="1cef4-165">Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Element zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="1cef4-166">Wählen Sie erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="1cef4-167">Hinzufügen oder Entfernen von Berechtigungen für Mitglieder</span><span class="sxs-lookup"><span data-stu-id="1cef4-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-168">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-169">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-170">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-171">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, **und wählen Sie dann Benutzer** \> **Berechtigungen anpassen**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="1cef4-172">Wählen Sie neben der Berechtigung, die Sie für ein Mitglied ändern möchten, die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="1cef4-173">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1cef4-173">Do one of the following:</span></span>
   - <span data-ttu-id="1cef4-174">Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie **Berechtigungen hinzufügen**, suchen oder Auswählen eines hinzuzufügenden Elements aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="1cef4-175">Wenn Sie die Berechtigung eines Mitglieds entfernen möchten, verwenden Sie das Suchfeld, um nach dem Mitglied zu suchen, falls erforderlich, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="1cef4-176">Wählen Sie erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="1cef4-177">Ein-oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste</span><span class="sxs-lookup"><span data-stu-id="1cef4-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="1cef4-178">Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, es erhält jedoch weiterhin e-Mail-Nachrichten, die an es gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cef4-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1cef4-179">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="1cef4-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="1cef4-180">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1cef4-181">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="1cef4-182">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **in globale Adresslisten** \> **Bearbeitung**anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="1cef4-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="1cef4-183">Legen Sie die Umschaltfläche **auf ein** oder **aus**fest.</span><span class="sxs-lookup"><span data-stu-id="1cef4-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="1cef4-184">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cef4-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1cef4-185">Wenn Sie ein freigegebenes Postfach aus der Adressliste ausblenden, ist es für neue freigegebene Post Fach Mitglieder unmöglich, das ausgeblendete Postfach Ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach erneut in der Adressliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1cef4-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="1cef4-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1cef4-186">Related articles</span></span>

[<span data-ttu-id="1cef4-187">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1cef4-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1cef4-188">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="1cef4-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="1cef4-189">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="1cef4-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="1cef4-190">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="1cef4-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="1cef4-191">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1cef4-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
