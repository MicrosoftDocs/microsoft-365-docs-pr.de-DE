---
title: Konfigurieren eines freigegebenen Postfachs
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
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten. Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen oder die Mitglieder.
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629047"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="16e00-104">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="16e00-104">Configure a shared mailbox</span></span>

<span data-ttu-id="16e00-105">Nachdem Sie [ein freigegebenes Postfach erstellt](create-a-shared-mailbox.md)haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten.</span><span class="sxs-lookup"><span data-stu-id="16e00-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="16e00-106">Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="16e00-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="16e00-107">Ändern des Namens oder des e-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären e-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="16e00-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-108">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-109">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-110">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-111">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** neben **Name, e-Mail, e-Mail-Aliase**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="16e00-112">Geben Sie einen neuen Namen ein, oder fügen Sie einen weiteren Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="16e00-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="16e00-113">Wenn Sie die primäre e-Mail-Adresse ändern möchten, muss Ihr Postfach über mehr als einen e-Mail-Alias verfügen.</span><span class="sxs-lookup"><span data-stu-id="16e00-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="16e00-114">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="16e00-115">Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden</span><span class="sxs-lookup"><span data-stu-id="16e00-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="16e00-116">Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um an Sie gesendete e-Mails weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="16e00-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="16e00-117">Sie können die Nachrichten an eine beliebige gültige e-Mail-Adresse oder Verteilerliste weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="16e00-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-118">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-119">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-120">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-121">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail Weiterleitung** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="16e00-122">Legen Sie die Umschaltfläche **auf**ein und geben Sie eine e-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="16e00-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="16e00-123">Es kann sich um eine beliebige gültige e-Mail-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="16e00-123">It can be any valid email address.</span></span> <span data-ttu-id="16e00-124">Um an mehrere Adressen weiterzuleiten, müssen Sie [eine Verteilergruppe](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.</span><span class="sxs-lookup"><span data-stu-id="16e00-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="16e00-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="16e00-126">Senden von automatischen Antworten aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="16e00-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-127">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-128">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-129">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-130">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **automatische Antworten** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="16e00-131">Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="16e00-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="16e00-132">Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten.</span><span class="sxs-lookup"><span data-stu-id="16e00-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="16e00-133">Sie können nur Text (keine Bilder) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="16e00-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="16e00-134">Wenn Sie *auch* eine Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, die Antwort erhalten soll, und geben Sie den Text ein.</span><span class="sxs-lookup"><span data-stu-id="16e00-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="16e00-135">Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.</span><span class="sxs-lookup"><span data-stu-id="16e00-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="16e00-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="16e00-137">Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="16e00-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="16e00-p108">Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="16e00-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="16e00-140">Wenn Sie zulassen möchten, dass alle Benutzer die gesendeten e-Mails anzeigen können, bearbeiten Sie im Admin Center die Einstellungen für freigegebene Postfächer, und wählen Sie **Gesendete Elemente** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="16e00-141">Auswählen der apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft e-Mail verwenden kann</span><span class="sxs-lookup"><span data-stu-id="16e00-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-142">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-143">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-144">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-145">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail apps** \> **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="16e00-146">Legen Sie die Umschaltfläche für alle apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden können, auf **ein** fest.</span><span class="sxs-lookup"><span data-stu-id="16e00-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="16e00-147">Legen Sie die Umschaltfläche für alle apps, die Sie nicht verwenden möchten, auf **Off** fest.</span><span class="sxs-lookup"><span data-stu-id="16e00-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="16e00-148">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="16e00-149">Speichern eines freigegebenen Postfachs für das Beweissicherungsverfahren</span><span class="sxs-lookup"><span data-stu-id="16e00-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="16e00-150">Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="16e00-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-151">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-152">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-153">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-154">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeitungs** **Prozess halten** \> aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="16e00-155">Legen Sie die Umschaltfläche **auf ein**fest.</span><span class="sxs-lookup"><span data-stu-id="16e00-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="16e00-156">Geben Sie optional eine Dauer, eine Notiz zum Haltestatus und eine URL mit weiteren Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="16e00-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="16e00-157">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="16e00-158">Hinzufügen oder Entfernen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="16e00-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-159">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-160">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-161">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-162">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und klicken Sie dann auf **Mitglieder** \> **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="16e00-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="16e00-163">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="16e00-163">Do one of the following:</span></span>
   - <span data-ttu-id="16e00-164">Klicken Sie zum Hinzufügen von Mitgliedern auf **Mitglieder hinzufügen**, suchen Sie nach einem Mitglied, das hinzugefügt werden soll, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="16e00-165">Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Element zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="16e00-166">Wählen Sie erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="16e00-167">Hinzufügen oder Entfernen von Berechtigungen für Mitglieder</span><span class="sxs-lookup"><span data-stu-id="16e00-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-168">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-169">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-170">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-171">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, **und wählen Sie dann Benutzer** \> **Berechtigungen anpassen**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="16e00-172">Wählen Sie neben der Berechtigung, die Sie für ein Mitglied ändern möchten, die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="16e00-173">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="16e00-173">Do one of the following:</span></span>
   - <span data-ttu-id="16e00-174">Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie **Berechtigungen hinzufügen**, suchen oder Auswählen eines hinzuzufügenden Elements aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="16e00-175">Wenn Sie die Berechtigung eines Mitglieds entfernen möchten, verwenden Sie das Suchfeld, um nach dem Mitglied zu suchen, falls erforderlich, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="16e00-176">Wählen Sie erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="16e00-177">Ein-oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste</span><span class="sxs-lookup"><span data-stu-id="16e00-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="16e00-178">Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, es erhält jedoch weiterhin e-Mail-Nachrichten, die an es gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="16e00-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="16e00-179">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16e00-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="16e00-180">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="16e00-181">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="16e00-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="16e00-182">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **in globale Adresslisten** \> **Bearbeitung**anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="16e00-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="16e00-183">Legen Sie die Umschaltfläche **auf ein** oder **aus**fest.</span><span class="sxs-lookup"><span data-stu-id="16e00-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="16e00-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16e00-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="16e00-185">Wenn Sie ein freigegebenes Postfach aus der Adressliste ausblenden, ist es für neue freigegebene Post Fach Mitglieder unmöglich, das ausgeblendete Postfach Ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach erneut in der Adressliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="16e00-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="16e00-186">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="16e00-186">Related articles</span></span>

[<span data-ttu-id="16e00-187">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="16e00-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="16e00-188">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="16e00-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="16e00-189">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="16e00-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="16e00-190">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="16e00-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="16e00-191">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="16e00-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
