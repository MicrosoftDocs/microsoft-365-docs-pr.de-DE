---
title: Konfigurieren der Einstellungen für das freigegebene Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Erstellen Sie ein freigegebenes Postfach, und konfigurieren Sie einige Einstellungen für die Benutzer, z. B. E-Mail-Weiterleitung und automatische Antworten.
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393991"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="873a7-103">Konfigurieren der Einstellungen für das freigegebene Postfach</span><span class="sxs-lookup"><span data-stu-id="873a7-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="873a7-104">Nachdem Sie [ein freigegebenes Postfach erstellt](create-a-shared-mailbox.md)haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, z. B. die E-Mail-Weiterleitung und automatische Antworten.</span><span class="sxs-lookup"><span data-stu-id="873a7-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="873a7-105">Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="873a7-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="873a7-106">Ändern des Namens oder des E-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="873a7-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="873a7-107">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-108">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann neben **Name, E-Mail, E-Mail-Aliase** **bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="873a7-109">Geben Sie einen neuen Namen ein, oder fügen Sie einen weiteren Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="873a7-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="873a7-110">Wenn Sie die primäre E-Mail-Adresse ändern möchten, muss Ihr Postfach über mehrere E-Mail-Aliase verfügen.</span><span class="sxs-lookup"><span data-stu-id="873a7-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="873a7-111">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="873a7-112">Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden</span><span class="sxs-lookup"><span data-stu-id="873a7-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="873a7-113">Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um E-Mails weiterzuleiten, die an das freigegebene Postfach gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="873a7-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="873a7-114">Sie können die Nachrichten an eine beliebige gültige E-Mail-Adresse oder Verteilerliste weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="873a7-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="873a7-115">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-116">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Weiterleitung** \> **bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="873a7-117">Legen Sie die Umschaltfläche auf **"Ein"** fest, und geben Sie eine E-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="873a7-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="873a7-118">Dabei kann es sich um eine beliebige gültige E-Mail-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="873a7-118">It can be any valid email address.</span></span> <span data-ttu-id="873a7-119">Um an mehrere Adressen weiterzuleiten, müssen Sie [eine Verteilergruppe](/office365/admin/setup/create-distribution-lists) für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.</span><span class="sxs-lookup"><span data-stu-id="873a7-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="873a7-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="873a7-121">Senden von automatischen Antworten aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="873a7-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="873a7-122">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-123">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Automatische Antworten** \> **bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="873a7-124">Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="873a7-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="873a7-p105">Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="873a7-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="873a7-127">Wenn Sie *auch* eine Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, wen Sie die Antwort erhalten möchten, und geben Sie den Text ein.</span><span class="sxs-lookup"><span data-stu-id="873a7-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="873a7-128">Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.</span><span class="sxs-lookup"><span data-stu-id="873a7-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="873a7-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="873a7-130">Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="873a7-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="873a7-p107">Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="873a7-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="873a7-133">Wenn Sie zulassen möchten, dass jeder die gesendete E-Mail sehen kann, bearbeiten Sie im Admin Center die Einstellungen für das freigegebene Postfach, und wählen Sie **"Gesendete Elemente** \> **bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="873a7-134">Auswählen der Apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft-E-Mails verwenden kann</span><span class="sxs-lookup"><span data-stu-id="873a7-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="873a7-135">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-136">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Apps** \> **bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="873a7-137">Legen Sie die Umschaltfläche für alle Apps **auf "Ein"** fest, mit denen Mitglieder auf das freigegebene Postfach zugreifen können sollen.</span><span class="sxs-lookup"><span data-stu-id="873a7-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="873a7-138">Legen Sie die Umschaltfläche für apps, die sie nicht verwenden sollen, auf **"Aus"** fest.</span><span class="sxs-lookup"><span data-stu-id="873a7-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="873a7-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="873a7-140">Aktivieren der Beweissicherung für ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="873a7-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="873a7-141">Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [Erstellen eines Beweissicherungsverfahrens.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="873a7-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="873a7-142">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-143">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann  \> **"Beweissicherungsverfahren" aus.**</span><span class="sxs-lookup"><span data-stu-id="873a7-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="873a7-144">Legen Sie die Umschaltfläche auf **"Ein"** fest.</span><span class="sxs-lookup"><span data-stu-id="873a7-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="873a7-145">Geben Sie optional eine Dauer, einen Hinweis zum Haltebereich und eine URL mit weiteren Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="873a7-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="873a7-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="873a7-147">Hinzufügen oder Entfernen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="873a7-147">Add or remove members</span></span>

1. <span data-ttu-id="873a7-148">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-149">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Mitglieder** \> **bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="873a7-150">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="873a7-150">Do one of the following:</span></span>
   - <span data-ttu-id="873a7-151">Wählen Sie zum Hinzufügen von Mitgliedern **"Mitglieder hinzufügen"** aus, suchen Sie nach einem hinzuzufügenden Mitglied oder wählen Sie es aus, und wählen Sie dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="873a7-152">Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="873a7-153">Wählen Sie noch mal **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="873a7-154">Hinzufügen oder Entfernen von Berechtigungen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="873a7-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="873a7-155">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-156">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Die  \> **Berechtigungen "Elemente anpassen"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="873a7-157">Wählen Sie **"Bearbeiten"** neben der Berechtigung aus, die Sie für ein Mitglied ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="873a7-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="873a7-158">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="873a7-158">Do one of the following:</span></span>
   - <span data-ttu-id="873a7-159">Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie **"Berechtigungen hinzufügen"** aus, suchen Oder wählen Sie ein hinzuzufügende Mitglied aus, und wählen Sie dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="873a7-160">Um die Berechtigung aus einem Mitglied zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="873a7-161">Wählen Sie noch mal **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="873a7-162">Ein- oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste</span><span class="sxs-lookup"><span data-stu-id="873a7-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="873a7-163">Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, aber es erhält weiterhin E-Mails, die an das Postfach gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="873a7-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="873a7-164">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="873a7-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="873a7-165">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **in der globalen Adressliste** "Bearbeiten" die Option \> **"Anzeigen"** aus.</span><span class="sxs-lookup"><span data-stu-id="873a7-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="873a7-166">Legen Sie die Umschaltfläche auf **"Ein"**  oder **"Aus"** fest.</span><span class="sxs-lookup"><span data-stu-id="873a7-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="873a7-167">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="873a7-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="873a7-168">Das Ausblenden eines freigegebenen Postfachs aus der Adressliste macht es für neue freigegebene Postfachmitglieder unmöglich, das ausgeblendete Postfach zu ihrem Outlook Profil hinzuzufügen, bis das freigegebene Postfach wieder in der Adressliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="873a7-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="873a7-169">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="873a7-169">Related content</span></span>

<span data-ttu-id="873a7-170">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="873a7-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="873a7-171">[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="873a7-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="873a7-172">[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="873a7-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="873a7-173">[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="873a7-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="873a7-174">[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="873a7-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>